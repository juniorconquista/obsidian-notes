# Plano de Migração — v1 → v2

## Visão Geral

Migrar a lógica real de negócio do projeto v1 (`face-id-swap-webview`) para o v2 (`face-id-swap-webview-v2`), que já possui a UI pronta com feature-based design, React Query, Axios e Zustand.

O v1 usa Redux, React Router, styled-components e uma arquitetura baseada em steps dinâmicos vindos da API. O v2 tem telas estáticas com dados mockados. A migração consiste em conectar o v2 à API real e replicar a lógica de negócio do v1.

---

## Arquitetura v1 (referência)

### Fluxo principal
1. `InitialPage` → lê query params (`?product=X&token=Y`) → navega para `/form`
2. `FormPage` → busca token → busca steps da API → renderiza step por tipo
3. Cada step é salvo via `Service.saveStep()` → API retorna próximo step

### Step types do v1
| Tipo | Componente v1 | Feature v2 |
|------|--------------|------------|
| `READ` | `StepRead` (termos + checkbox) | `features/terms` |
| `FORM` | `StepForm` | (futuro) |
| `IMAGE` | `StepImage` | `features/document` |
| `SELFIE` | `StepSelfie` | `features/document` |
| `DECISION` | `StepDecision` | `features/document` |
| `LIVENESS_3D_AWS` | `StepLivenessAWS` | `features/liveness` |
| `LIVENESS_3D_REACT` | `StepLivenessReact` | `features/liveness` |
| `LIVENESS_3D` | inline em FormPage | `features/liveness` |
| `CONFIRMATION` | `StepConfirmation` | `features/result` |
| `SUCCESS` | `StepSuccess` | `features/result` |

### Endpoints da API (v1)
| Método | Endpoint | Uso |
|--------|----------|-----|
| `POST` | `/token-history-onboarding-sdk/{clientId}` | Obter/validar token |
| `GET` | `/onboarding/token-search/{token}` | Buscar onboarding por token |
| `GET` | `/product-params-first-step-onboarding/{clientId}` | Obter primeiro step + tema |
| `PUT` | `/history-onboarding-step/{token}` | Salvar step e receber próximo |
| `POST` | `/onboarding/step-search` | Buscar step por alias |
| `POST` | `/service-field` | Chamar serviço de campo |

### Tipos principais (v1 `types.d.ts`)
- `Form` = `{ countSteps, steps: FormStep[] }`
- `FormStep` = `{ step, stepName, type, fields: FormField[], goBack, ... }`
- `FormField` = `{ field, label, type, value, required, visible, ... }`
- `FormInfo` = `{ tokenOnboarding, productName }`
- `Theme` = `{ logo, primaryColor, backgroundColor, ... }`

---

## Etapas de Migração

### ✅ Etapa 1 — Termos de Uso (READ step) — CONCLUÍDA

- [x] **1.1** — Tipos da API (`src/shared/types/api.ts`)
- [x] **1.2** — Serviços da API (`onboarding-service.ts` + React Query hooks)
- [x] **1.3** — Onboarding store (Zustand: `form`, `formInfo`, `activeStepId`, `currentFieldIndex`)
- [x] **1.4** — Bootstrap (`useBootstrap`: query params → searchByToken → getFirstStep → navegação por `numberSteps`)
- [x] **1.5** — TermsScreen dinâmico (HTML da API, checkboxes dinâmicos, `saveStep`, filtro de fields CHECKBOX)
- [x] **1.6** — Tratamento de erros (interceptor axios → `kyc:error` event, toast via sonner)
- [x] **1.7** — Workaround API: `termsCompleted` para esconder botão voltar no step DECISION

---

### ✅ Etapa 2 — Seleção e Captura de Documentos (DECISION + IMAGE) — CONCLUÍDA

- [x] **2.1** — DocumentTypeScreen dinâmico (botões BUTTON da API, `saveStep`, `nextStepId`, `docSubmissionInstructions`)
- [x] **2.2** — DocumentCaptureScreen: captura real (câmera nativa `getUserMedia`, crop viewfinder, rotação 270° RG/RNE)
- [x] **2.3** — Upload de arquivo (PNG/JPG/PDF, validação por `field.uploads`, conversão PDF→imagem com `pdfjs-dist`)
- [x] **2.4** — DocumentPreviewScreen: envio real (`saveStep` com imagem base64, multi-field RG frente/verso)
- [x] **2.5** — Navegação entre steps (`activeStepId` → `nextStepId` → `stepTypeToScreen`)
- [x] **2.6** — Validação de qualidade (resolução mínima 400x300)
- [x] **2.7** — Face detection no documento (FaceDetector API nativa + fallback skin-tone canvas, bloqueia envio se não detecta rosto)
- [x] **2.8** — Crop CNH em PDF (quadrante superior-esquerdo — TODO: revisar se template mudar)
- [x] **2.9** — Resize de imagem (max 800x700 para uploads)

---

### ✅ Etapa 3 — Liveness (LIVENESS_3D_AWS) — CONCLUÍDA
> Integrar AWS FaceLivenessDetector real no lugar da simulação

**O que o v1 faz:**
1. Step `LIVENESS_3D_AWS` contém field `session_id_liveness_3d_aws` com o session ID
2. Mostra tela de instruções antes do liveness ("Foto para Verificação")
3. Usa `@aws-amplify/ui-react-liveness` → `FaceLivenessDetector`
4. Dicionário pt-BR completo para todas as mensagens
5. `handleAnalysisComplete` → para câmera → `saveStep()`
6. `handleLivenessError` → toast erro + retry
7. Step `LIVENESS_3D_REACT` usa `face-api.js` com pose detection (olhar esquerda/direita, sorrir, piscar)
8. Step `LIVENESS_3D` usa liveness inline com `serviceField` calls

**Implementado:**
- [x] **3.1** — Instalado `aws-amplify`, `@aws-amplify/ui-react`, `@aws-amplify/ui-react-liveness`
- [x] **3.2** — Amplify configurado no boot (`src/shared/lib/amplify.ts`) com Identity Pool via `window.__ENV__` (runtime inject)
  - `configureAmplify()` + `prefetchCredentials()` no `main.tsx`
  - Runtime env helper (`src/shared/utils/runtime-env.ts`) para ler de `window.__ENV__` com fallback para `import.meta.env`
  - `public/env-config.js` para desenvolvimento local (gitignored)
  - Tipos declarados em `vite-env.d.ts`
- [x] **3.3** — LivenessCaptureScreen: lê `session_id_liveness_3d_aws` do step field via `activeStep`
  - Session ID em state local (`activeSessionId`) para poder limpar em caso de erro
  - `useEffect` sincroniza quando o step data chega atrasado
- [x] **3.4** — `FaceLivenessDetector` integrado com dicionário pt-BR (`src/features/liveness/liveness-dictionary.ts`)
  - `disableStartScreen={true}` (usamos nossa própria tela de instruções)
  - Tema Amplify customizado com cores da API
  - CSS overrides (`liveness-overrides.css`): botão cancel escondido, hints estilizados, progress bar
- [x] **3.5** — `handleAnalysisComplete` → para câmera → `saveStep()` via React Query → navega próximo step
- [x] **3.6** — `handleLivenessError`:
  - Limpa session ID (desmonta FaceLivenessDetector, mostra loader)
  - Toast contextual (timeout vs erro genérico)
  - Navega para instruções + busca novo session ID via `searchByToken`
  - Melhoria sobre v1: v1 ficava preso no loader após erro, v2 permite retry com session ID novo
- [x] **3.7** — LivenessInstructionsScreen funcional com navegação para liveness
  - `activeStepId` setado no bootstrap para garantir session ID disponível
- [ ] **3.8** — (Futuro) StepLivenessReact: pose detection com `face-api.js` + `serviceField`

---

### ✅ Etapa 4 — Sucesso, Confirmação e Comunicação com Host — CONCLUÍDA

**Implementado:**
- [x] **4.1** — Host bridge service centralizado (`src/shared/lib/host-bridge.ts`)
  - `notifyStepStatus()` — status por step via `window.top.postMessage`
  - `notifySuccess()` — sucesso para React Native, Flutter e iframe
  - Payloads idênticos à v1 (backwards compatible)
- [x] **4.2** — Hook `useHostNotifier` — notifica host automaticamente a cada mudança de screen
- [x] **4.3** — Integrado no `App.tsx`
- [x] **4.4** — SuccessScreen dinâmico:
  - Lê fields da API: `success_text` (mensagem), `success_image` (imagem customizada), `success_button` (botão com redirect), `success_loading` (spinner)
  - Imagem da API substitui checkmark animado quando disponível
  - Botão com label e redirect da API quando disponível
  - Header usa `stepName` e `countSteps` da API
- [x] **4.5** — StepConfirmation: chama `saveStep()` automaticamente ao montar (finaliza onboarding no backend)
  - Chama `notifySuccess()` do host bridge
- [x] **4.6** — Redirect URL e close window:
  - `success_text` com `value` (URL) → `window.parent.location.replace(url)`
  - `success_reload` com `value` → `window.close()`
  - `success_button` → botão que redireciona ao clicar
- [ ] **4.7** — ⚠️ **Testar integração postMessage** em ambiente real (React Native, Flutter, iframe)

---

### ✅ Etapa 5 — Tema Dinâmico e Personalização — CONCLUÍDA

**Implementado:**
- [x] **5.1** — Theme store (`src/shared/stores/theme-store.ts`) com defaults que espelham o design original
- [x] **5.2** — Bootstrap captura `style` da API (tanto `searchByToken` quanto `getFirstStep`)
- [x] **5.3** — Validação de logo URL (testa se carrega antes de exibir, fallback SVG Veritas)
- [x] **5.4** — CSS Custom Properties via `useThemeVariables` hook:
  - `--kyc-primary-color` (header, botões, checkboxes, ícones)
  - `--kyc-bg-color` (fundo das páginas)
  - `--kyc-button-content-color` (texto botões, ícones header)
  - `--kyc-primary-text-color`, `--kyc-secondary-text-color`
  - `--kyc-input-bg-color`, `--kyc-input-label-color`, `--kyc-input-text-color`
  - `--kyc-font-family`
- [x] **5.5** — Defaults setados no CSS (`:root` em `theme.css`) para evitar flash antes do JS
- [x] **5.6** — Logo dinâmico no `KycHeader` (`<img>` da API ou SVG Veritas fallback)
- [x] **5.7** — `hideHeader` e `headerTransparent` suportados no `KycHeader`
- [x] **5.8** — Google Fonts dinâmico: carrega font da API via `<link>` injetado no `<head>`
  - Fontes suportadas: Arial, Inter, League Spartan, Poppins, Roboto, Space Grotesk, Ubuntu
- [x] **5.9** — Todas as cores hardcoded `#000005` substituídas por `var(--kyc-primary-color)` nos componentes

---

### ⬜ Etapa 6 — Funcionalidades Adicionais
> Features da v1 que não se encaixam nas etapas anteriores

- [x] **6.1** — `stepSearch` no bootstrap: quando URL tem `?serviceAlias=X` ou `?fieldAlias=Y`, chama `stepSearch` antes do fluxo normal. Navega direto ao step retornado. Fallback para `searchByToken` se falhar
- [ ] **6.2** — `StepForm`: formulários dinâmicos com fields de input (TEXT, SELECT, etc.)
- [ ] **6.3** — `StepSelfie`: câmera frontal com auto-captura via `face-api.js`
- [ ] **6.4** — `serviceField`: chamada de serviço por campo (usado em FORM e LIVENESS_3D_REACT)
- [ ] **6.5** — `StepOCR`: captura com OCR via `tesseract.js`
- [ ] **6.6** — `checkIfImageIsValid`: validação de URL de imagem (usado para secondaryLogo)
- [x] **6.7** — ~~Validação avançada de imagem~~ — código morto na v1 (funções definidas mas nunca chamadas). Não precisa migrar

---

## Decisões de Arquitetura

| Aspecto | v1 | v2 |
|---------|----|----|
| State management | Redux (store/form, store/navigation, store/theme) | Zustand (kyc-store, onboarding-store) |
| API calls | Axios direto em `Service.ts` | Axios + React Query hooks |
| Routing | React Router (`/`, `/form`) | State machine no Zustand (sem router) |
| Styling | styled-components | Tailwind + inline styles |
| Step rendering | Dinâmico por `type` em FormPage | Telas fixas nas features |
| Liveness | AWS Amplify FaceLivenessDetector | AWS Amplify FaceLivenessDetector + retry automático com novo session ID |
| Toasts | react-toastify | sonner |
| PDF processing | react-pdf + pdfjs | pdfjs-dist v6 (com crop CNH e proteção contra PDF com senha) |
| Face detection | @tensorflow-models/face-detection (conflito com Amplify) | FaceDetector API nativa + fallback skin-tone canvas (sem conflito TensorFlow) |
| Host communication | postMessage espalhado em FormPage + StepSuccess | Centralizado em `host-bridge.ts` + `useHostNotifier` |
| Theming | Redux + styled-components ThemeProvider | Zustand `theme-store` + CSS Custom Properties + Google Fonts dinâmico |
| Testes | Nenhum | Vitest + Testing Library (43 arquivos, 255 testes) |
| Validação de imagem | Nenhuma antes do envio | Resolução mínima + face detection + resize antes do envio |

## Cobertura de Testes

O projeto possui **43 arquivos de teste** com **255 testes unitários e de integração**, cobrindo:

| Camada | Arquivos | Testes | O que cobre |
|--------|----------|--------|-------------|
| Utilitários | 7 | 52 | encrypt, error, url, step-to-screen, field-to-variant, image-processing, runtime-env |
| Stores (Zustand) | 3 | 25 | kyc-store, onboarding-store, theme-store |
| Services | 1 | 9 | onboarding-service (5 endpoints mockados) |
| Hooks | 5 | 26 | useBootstrap, useErrorListener, useHostNotifier, useOnboarding, useThemeVariables |
| Lib | 3 | 20 | axios interceptors, host-bridge, query-client |
| Componentes React | 22 | 118 | Todas as telas, header, shell, botões, ilustrações, capture, liveness |
| Dicionários | 1 | 4 | liveness-dictionary pt-BR |
| App/Providers | 3 | 12 | App routing, Slide, AppProvider |

**Stack de testes:** Vitest + @testing-library/react + @testing-library/user-event + jsdom

---

## Variáveis de Ambiente

```env
VITE_API_BASE_URL=/api          # Base URL da API (proxy em dev)
VITE_ENCRYPT_KEY=               # Chave de encriptação para Validation-Token
```

---

## Progresso Geral

| Etapa | Status | Descrição |
|-------|--------|-----------|
| 1 | ✅ Concluída | Termos de Uso — API real, saveStep, checkboxes dinâmicos |
| 2 | ✅ Concluída | Documentos — DECISION + IMAGE, captura, upload, PDF, face detection |
| 3 | ✅ Concluída | Liveness — AWS FaceLivenessDetector, dicionário pt-BR, retry com novo session ID |
| 4 | ✅ Concluída | Sucesso dinâmico, StepConfirmation, host bridge, redirect/close. Falta testar postMessage em ambiente real |
| 5 | ✅ Concluída | Tema — CSS Variables, logo dinâmico, Google Fonts, hideHeader, headerTransparent |
| 6 | ⬜ Pendente | Extras — StepForm, StepSelfie, serviceField, OCR |


## Solicitação de criação de repositórios  
  
Grupo: `SWAP / Engineering / Risk And Compliance / Face ID Swap`  
  
### Repositórios existentes  
| Repositório | Descrição |  
|---|---|  
| Face ID Swap Backend | API do onboarding KYC |  
| Face ID Swap Webview | Webview v1 (legado) |  
  
### Novos repositórios a criar  
  
| Repositório                       | Descrição                                      | Linguagem  | Publicação                             |     |
| --------------------------------- | ---------------------------------------------- | ---------- | -------------------------------------- | --- |
| **Face ID Swap SDK Web**          | SDK para integração via iframe e Web Component | TypeScript | npm (`@swap/kyc-web`)                  |     |
| **Face ID Swap SDK React Native** | SDK para integração em apps React Native       | TypeScript | npm (`@swap/kyc-react-native`)         |     |
| **Face ID Swap SDK Flutter**      | SDK para integração em apps Flutter            | Dart       | [pub.dev](http://pub.dev) (`swap_kyc`) |     |
  
### Estrutura final do grupo



## Por que 4 repositórios separados?

### 1. Webview V2 — deploy independente

A webview é uma **aplicação web completa** (React + Vite) que gera um build estático deployado como URL. Os SDKs são **bibliotecas** que outros projetos instalam como dependência. São artefatos com ciclos de vida, pipelines e processos de release completamente diferentes:

- Webview: `pnpm build` → deploy em servidor/CDN
- SDKs: `pnpm build` → publish no npm/pub.dev

Misturar no mesmo repo significa que um hotfix na webview dispara CI dos SDKs sem necessidade, e vice-versa.

### 2. SDK Web vs SDK React Native — ecossistemas diferentes

| | SDK Web | SDK React Native |
|---|---|---|
| **Runtime** | Browser (iframe, postMessage) | React Native (WebView nativo, bridge JS) |
| **Dependência** | Nenhuma | `react-native-webview` |
| **Testes** | jsdom | Emulador Android/iOS |
| **Quem usa** | Dev frontend web | Dev mobile RN |
| **Consumidor** | Sites, SPAs, portais | Apps React Native |

Um dev web que instala `@swap/kyc-web` não precisa ter React Native no `node_modules`. Se estivessem no mesmo pacote, um importava dependências do outro sem necessidade.

### 3. SDK Flutter — linguagem diferente

Flutter usa **Dart**, não TypeScript. Publica no **pub.dev**, não no npm. Tem toolchain próprio (`dart`, `flutter test`, `flutter pub publish`). Não há código compartilhado com os pacotes JS — juntar num monorepo só adiciona complexidade ao CI sem benefício.

### 4. Versionamento independente

Cada SDK evolui no seu ritmo:

- Corrigiu um bug na webview? Release da webview. SDKs não mudam.
- Adicionou feature no SDK Web? Release do SDK Web. Flutter e RN não mudam.
- Atualizou `react-native-webview`? Release do SDK RN. Os outros não são impactados.

Num repo único, qualquer mudança em qualquer pacote gera ruído nos outros — PRs misturados, changelogs poluídos, tags de versão confusas.

### 5. Permissões e ownership

Cada repo pode ter owners diferentes:
- **Webview V2** → time de frontend KYC
- **SDK Web** → time de frontend KYC
- **SDK React Native** → time mobile (RN)
- **SDK Flutter** → time mobile (Flutter)

### Resumo

| Critério | Repo único | 4 repos |
|---|---|---|
| CI/CD | Complexo (multi-linguagem, multi-target) | Simples e focado |
| Versionamento | Acoplado | Independente |
| Dependências | Poluídas (Dart + RN + Web juntos) | Limpo por projeto |
| Ownership | Difícil de separar | Claro por repo |
| Publicação | npm + pub.dev no mesmo pipeline | Cada um publica no seu registry |
| Impacto de mudança | Toca tudo | Só o que mudou |
