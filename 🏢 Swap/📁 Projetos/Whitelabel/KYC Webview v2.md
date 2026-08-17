# KYC Webview v2 — Apresentação para Stakeholders

## TL;DR

A v2 é uma **reescrita completa** da webview de onboarding KYC, mantendo **100% de compatibilidade** com os contratos de comunicação existentes (React Native, Flutter, iframe). O fluxo principal (Termos → Documento → Liveness → Sucesso) está **100% funcional** com a API real, com melhorias significativas de UX, confiabilidade e qualidade de código.

---

## 1. O que mudou: v1 vs v2

### Stack Técnico

| | v1 | v2 |
|---|---|---|
| **State** | Redux (3 stores separados) | Zustand (2 stores, 50% menos boilerplate) |
| **API** | Axios cru espalhado | React Query + Axios centralizado |
| **Routing** | React Router (URLs) | State machine Zustand (sem URLs expostas) |
| **Estilos** | styled-components | Tailwind + CSS Variables dinâmicas |
| **UI** | Custom + Material UI | Radix UI + shadcn/ui (acessível) |
| **Animações** | Nenhuma | Framer Motion (transições 60fps) |
| **Toasts** | react-toastify | Sonner |
| **PDF** | react-pdf | pdfjs-dist v6 |
| **Face detection** | TensorFlow (conflitava com Amplify) | FaceDetector API nativa + fallback canvas |
| **Testes** | **Nenhum** | **255 testes (43 arquivos)** |

---

## 2. Bugs corrigidos / Melhorias sobre a v1

### 2.1 — Face detection antes do envio (NOVO)

**v1:** O front enviava a imagem do documento direto para o backend sem nenhuma validação. Se o documento não tivesse rosto visível, o backend rejeitava e o usuário tinha que refazer tudo.

**v2:** Antes de enviar qualquer imagem:
1. Verifica resolução mínima (400x300px)
2. Detecta rosto no documento via FaceDetector API ou análise de pixels
3. Se não detectar rosto → **bloqueia o envio** e avisa o usuário na hora
4. Redimensiona para max 800x700px (payload menor, upload mais rápido)

**Resultado:** Menos chamadas desnecessárias ao backend, feedback instantâneo ao usuário.

### 2.2 — Liveness: recovery de erro (BUG FIX)

**v1:** Quando o liveness falhava (timeout, erro de câmera), o usuário **ficava preso no loader** sem conseguir tentar novamente. Precisava recarregar a página.

**v2:**
1. Limpa session ID → desmonta o FaceLivenessDetector imediatamente
2. Mostra toast contextual ("Tempo esgotado" vs "Erro genérico")
3. Busca **novo session ID** automaticamente via `searchByToken`
4. Redireciona para tela de instruções → usuário pode tentar novamente

### 2.3 — Face detection sem conflito TensorFlow (BUG FIX)

**v1:** Usava `@tensorflow-models/face-detection` que **conflitava com o TensorFlow interno** do AWS FaceLivenessDetector ("kernel already registered").

**v2:** Sistema dual sem TensorFlow:
1. **Primário:** FaceDetector API nativa do browser (Chrome 70+, Edge, Opera)
2. **Fallback:** Análise de skin-tone pixels via Canvas (browsers sem FaceDetector)
3. Em caso de erro → retorna `true` para não bloquear o usuário

### 2.4 — Retomada de onboarding (MELHORIA)

**v1:** Se o usuário saísse no meio do fluxo, perdia todo o progresso.

**v2:** O bootstrap detecta automaticamente:
- Status `IN_PROCESS` → retoma do step exato onde parou
- Procura o step pendente nos campos da API
- Marca termos como completos se já passaram
- Funciona com `stepSearch` para deep links (`?serviceAlias=X`)

### 2.5 — PDF com senha (MELHORIA)

**v1:** Se o usuário tentasse enviar um PDF com senha, o processamento falhava silenciosamente.

**v2:** Detecta PDF protegido e mostra mensagem clara: _"O arquivo possui senha. Envie um arquivo sem senha."_

### 2.6 — Erros de rede centralizados (MELHORIA)

**v1:** Cada componente tratava erros de forma independente, inconsistente.

**v2:** Interceptor Axios centralizado:
- `401` → evento `kyc:error` com variante `token-expired`
- `ERR_NETWORK` → evento `kyc:error` com variante `no-connection`
- Hook `useErrorListener` captura e navega para tela de erro contextual
- Tela de erro com ilustrações específicas (WiFi off, documento com X)

---

## 3. Melhorias de UX

### 3.1 — Transições animadas
Todas as telas têm transições suaves com Framer Motion (slide left/right, fade in/out). A v1 não tinha nenhuma animação.

### 3.2 — Tela de sucesso com confetti
Animação de confetti com 28 partículas coloridas caindo. Campos dinâmicos da API (imagem, botão, mensagem, redirect).

### 3.3 — Scroll indicator nos termos
Indicador animado de "role para baixo" que desaparece quando o usuário scrolla. Só aparece se o conteúdo for scrollável.

### 3.4 — Preview com zoom
DocumentPreviewScreen com botão de zoom que abre a imagem em tela cheia. Alerta visual para verificar nitidez antes de confirmar.

### 3.5 — Captura de documento
- Overlay com cantos de moldura (corners brancos)
- Labels "Frente" / "Verso" para CNH
- Labels rotacionados para RG/carteira
- Viewfinder simulado quando câmera não disponível
- Botão de upload para documento digital (quando a API permite)

### 3.6 — Tema dinâmico completo
- 10 CSS custom properties controladas pela API
- Google Fonts carregadas dinamicamente (7 fontes suportadas)
- Logo da API com validação (fallback SVG se URL quebrada)
- `hideHeader` e `headerTransparent` suportados
- Sem flash de tema padrão (CSS defaults em `:root`)

---

## 4. Comunicação com Host Apps

**100% backward compatible** com v1. Payloads idênticos.

| Bridge | Método | Quando |
|--------|--------|--------|
| React Native | `window.ReactNativeWebView.postMessage()` | Sucesso |
| Flutter | `window.flutter_inappwebview.callHandler()` | Sucesso |
| iframe | `window.parent.postMessage()` | Sucesso + cada step |
| Top frame | `window.top.postMessage()` | Cada mudança de step |

Centralizado em `host-bridge.ts` + `useHostNotifier` hook (v1 tinha isso espalhado em 3+ arquivos).

---

## 5. Cobertura de Testes

A v1 **não tinha nenhum teste**. A v2 tem:

| Tipo | Quantidade | Cobertura |
|------|-----------|-----------|
| **Testes unitários** | 110 | Utils, stores, services, lib |
| **Testes de componente** | 118 | Todas as telas e componentes |
| **Testes de hook** | 26 | Bootstrap, error, notifier, theme, onboarding |
| **Total** | **255 testes em 43 arquivos** | — |

**Frameworks:** Vitest + React Testing Library + jsdom

**O que testamos:**
- Cada variante de erro (generic, token-expired, finished, no-connection)
- Fluxo completo do bootstrap (com/sem token, resume, stepSearch)
- Todas as variantes de documento (CNH, RG frente/verso, carteira, single)
- Stores: set, reset, derived state, imutabilidade
- Services: todos os 5 endpoints mockados com cenários de erro
- Interceptors Axios (401, rede)
- Host bridge (React Native, Flutter, iframe)
- Tema dinâmico (CSS vars, Google Fonts, logo validation)
- Checkboxes dinâmicos, botão disabled/enabled
- Zoom de preview, upload de arquivo

---

## 6. Progresso do Plano de Migração

| Etapa | Status | Descrição |
|-------|--------|-----------|
| 1 | ✅ | Termos de Uso — API real, saveStep, checkboxes dinâmicos |
| 2 | ✅ | Documentos — DECISION + IMAGE, captura, upload, PDF, face detection |
| 3 | ✅ | Liveness — AWS FaceLivenessDetector, pt-BR, retry com novo session ID |
| 4 | ✅ | Sucesso — dinâmico, host bridge, redirect/close |
| 5 | ✅ | Tema — CSS Variables, logo, Google Fonts, hideHeader |
| 6 | 🔶 Parcial | stepSearch ✅ · StepForm ⬜ · StepSelfie ⬜ · serviceField ⬜ · OCR ⬜ |

### O que falta na Etapa 6 (funcionalidades adicionais):

| Item | Prioridade | Complexidade | Descrição |
|------|-----------|-------------|-----------|
| StepForm | Alta | Média | Formulários dinâmicos (TEXT, SELECT, etc.) |
| serviceField | Alta | Média | Chamada de serviço por campo (usado em FORM e LIVENESS_3D_REACT) |
| StepSelfie | Média | Média | Câmera frontal com auto-captura via face-api.js |
| StepLivenessReact | Baixa | Alta | Pose detection (olhar esquerda/direita, sorrir, piscar) |
| StepOCR | Baixa | Alta | Captura com OCR via tesseract.js |

### Pendência de validação:
- [ ] **4.7** — Testar integração postMessage em ambiente real (React Native, Flutter, iframe)

---

## 7. Números

| Métrica | v1 | v2 |
|---------|----|----|
| Testes | 0 | 255 |
| Arquivos de teste | 0 | 43 |
| Validação de imagem pré-envio | Nenhuma | Resolução + face detection + resize |
| Recovery de liveness | Preso no loader | Retry automático com novo session ID |
| Animações | 0 | Todas as telas |
| CSS custom properties | 0 | 10 variáveis temáticas |
| Google Fonts dinâmicas | 0 | 7 fontes suportadas |
| Host bridges suportados | 3 (espalhados) | 3 (centralizados) |
| Workarounds de API documentados | 0 | 3 (com TODO para remover quando API corrigir) |
