# Análise Geral — swap-expenses-web

> Documento consolidado de auditoria técnica. Levantamento factual do estado atual do repositório — pontos fortes, fracos e métricas medidas. Não faz recomendação de direção; apresenta as evidências para embasar decisões de quem lê.
>
> Data: 2026-08-14 · Escopo: arquitetura, qualidade de código, regras de negócio no front, performance.
> Stack: Next.js 15.5.7 (App Router) · React 19 · TypeScript strict · Mantine 8 + Tailwind 4 · TanStack Query 5 · NextAuth v5 (beta) · CASL · XState · SDK gerado por Kubb/OpenAPI · Sentry.
> Tamanho: ~1.945 arquivos TS/TSX · 26 features · SDK gerado com 923 arquivos.

---

## 1. Sumário

Estado geral por eixo, com base nas evidências das seções seguintes. As cores indicam a **condição atual medida**, não um julgamento sobre qual caminho seguir.

| Eixo | Condição | Evidência resumida |
|---|---|---|
| Arquitetura de base | 🟢 Sólida | Núcleo sessão/server-actions/data-fetching com decisões deliberadas; prefetch SSR idiomático; layouts de alto nível são Server Components |
| Consistência / duplicação | 🟡 Irregular | Forks copy-paste (`distribution`↔`benefit`, 3× `imports-table`), estrutura de features desigual (2/26 completas), 3 gerações de HTTP client coexistindo |
| SDK / codegen | 🟡 Frágil | 268 hooks gerados dead code; merge "último vence" (21 schemas); patch por regex sobre TS gerado; regeneração dispara build completo |
| Over-engineering / dead code | 🟡 Presente | XState para wizard (~580 l onde `use-steps` resolve em 45); `TableGeneric`/`PagePolicies`/`list-old` sem uso; 2 clients HTTP mortos; utils de moeda duplicados |
| Segurança | 🔴 Pendências | Segredo commitado no `Dockerfile`; regras de compliance/elegibilidade decididas no cliente |
| Testes | 🔴 Ausente | Cobertura ≈ 0% (1 teste unitário morto, sem runner; 2 specs E2E) em 1.945 arquivos |
| Performance | 🟡 Otimizável | First Load JS medido: 382 kB base / 440–576 kB por rota (alvo Next ≈ 130 kB). Sem bug arquitetural; otimizações padrão não ligadas |
| Documentação | 🟢 Forte | 34 docs, índice mestre, protocolo de implementação, catálogo de landmines |

**Fatos de maior peso:**

- **Base técnica consistente**: o padrão de sessão/server-actions/data-fetching resolve problemas reais de Next.js (erros escondidos em prod, refresh concorrente, hidratação SSR) com implementação correta.
- **Débito concentrado e nomeável**: duplicação por copy-paste, camada HTTP fragmentada com migrações incompletas, e ausência de testes automatizados.
- **Pendências urgentes independentes de qualquer direção**: segredo commitado, regras de compliance no cliente, cobertura de testes ≈ 0%.

---

## 2. Pontos fortes

1. **Documentação de arquitetura excepcional** — 34 docs em `docs/` com índice mestre (`INDEX.md`), mapa de repo (`REPO_MAP.md`), protocolo de implementação e catálogo de armadilhas (`gotchas/landmines.md`, L1–L12). Raro e valioso.
2. **Núcleo de sessão/data-fetching bem arquitetado**:
   - `createServerAction` (`src/lib/server-actions/create-server-action.ts:153`) converte 4xx em dados serializáveis e re-lança 5xx — resolve o problema real do React que esconde mensagens de erro em produção.
   - Singleflight de refresh de token + `auth = cache()` — dedup correto de refresh concorrente.
   - Factories `createQueryHook`/`createMutationHook` com overloads tipados que fazem unwrap automático do `ServerActionResult`.
3. **Rotas paralelas/interceptadas idiomáticas** — `@modal`/`@drawer`/`@drawerDetails` + `(.)` + `default.tsx` consistente onde existe.
4. **Disciplina de tipos na superfície** — `strict: true`, **zero `@ts-ignore`** em código não-gerado, `next.config.ts` sem `ignoreBuildErrors`/`ignoreDuringBuilds` (build barra erros de tipo).
5. **Duas camadas de autz conceitualmente corretas** — route-policies ("posso acessar a rota?") vs CASL ("posso executar a ação?"); `evaluate-policy.ts` puro e testável.
6. **Infra sã** — QueryClient global bem configurado (`staleTime 60s`, dehydrate de pending queries), layout privado é Server Component, Docker multi-stage/standalone/não-root, `.env` gitignored.

---

## 3. Pontos fracos por severidade

### 🔴 Crítico

- **Segredo commitado** — `Dockerfile:45` tem `ENV SENTRY_AUTH_TOKEN=sntrys_...` real, em texto plano, no git desde o commit `69dfeeb6`. Rotacionar + mover para secret de build.
- **Cobertura de testes ≈ 0%** — 1 teste unitário (morto: importa `@/test-utils` inexistente, sem runner instalado — nem vitest nem jest no `package.json`) + 2 specs E2E, em 1.945 arquivos. QA é manual. Sem rede de segurança para refatorar nada.

### 🟡 Alto

- **Duplicação massiva por copy-paste** (maior débito de código):
  - `distribution` ↔ `benefit/pma/distribution`: fork inteiro (máquinas XState, forms, steppers, schemas), já divergindo (`min(0)` vs `min(1)`).
  - `recharges` ↔ `benefit/pma/recharge`: outro fork completo.
  - **Três `imports-table.tsx`** (people/users/organizations, ~750 linhas cada = 2.282 linhas). Diff people↔users é ~40 linhas — e já divergiram em bugs de paginação.
  - `table-body-loading.tsx` reimplementado em ~23 features.
- **Fragmentação de HTTP client — 3 gerações vivas + SDK** — `old/` (1 uso), `v1/` (15 arquivos ativos, código quente), `v2/` (2), `get-api.ts`, `client.ts` (312 linhas, **morto** como executor — só o tipo `ApiException` é consumido), `with-api-client.ts`. O padrão "novo" (`withApiClient`) é **construído em cima do "legado"** (`ky-adapter.ts → getApi()`) — sem caminho de deprecação limpo. `create-server-action.ts` precisa mapear **4 shapes de erro diferentes** por causa disso.
- **`strict: true` na fachada, `any` por baixo — ~306–361 ocorrências** — o TS não é suprimido (0 `@ts-ignore`), é evadido via `any`. O `.oxlintrc.json` desliga justamente as regras que pegariam: `typescript/no-explicit-any: off`, `no-unused-vars: off`, `react-hooks/exhaustive-deps: off`. Só a categoria `correctness` é erro.
- **Pipeline de codegen frágil (~8 scripts de patch)** — para o Kubb produzir output usável: merge "último-vence" com colisões silenciosas, regex que reescreve tipos TS gerados (`patch-org-types.js`, depende de nomes de alias exatos), `sed` para remover extensões `.ts`, `git restore` de `ProblemDetails.ts` porque o codegen o sobrescreve errado. `.backup` dos specs commitados. Qualquer mudança de naming no backend ou upgrade do Kubb pode quebrar silenciosamente.

### 🟢 Médio

- **`src/components` vaza domínio** — 8–11 arquivos "compartilhados" importam de `features/`; vários são features renomeadas (`Drawer/expense-details.tsx` 423L, `Modal/change-limit.tsx`, `Drawer/transaction-details.tsx`). Inversão de dependência. Além disso, 32 imports de `features/ → @/app` (domínio dependendo da camada de rotas).
- **Inconsistência estrutural entre features** — só 2/26 têm estrutura completa; `benefit` é mini-monorepo aninhado; `approvals`/`rules`/`imports` são "features ocas" (só componentes); **0 barrels** em features (sem fronteira de módulo); código morto versionado (`distribution/list-old.tsx`, `recharges` com dois entrypoints).
- **Autz route↔CASL é código morto especulativo** — `requireAbility` e `requireAssignedProduct` tipados e testados mas **nenhuma policy os usa**. `RouteGuard` é client-side only → proteção puramente UX; o gate real precisa estar na API.
- **Arquivos gigantes** — modais de 930/874/679 linhas, `taxas/page.tsx` (812L, parcialmente stub comentado), `PagePolicies/policies.ts` (6.212L). Rotas não são finas.
- **Higiene** — 82 `console.*` (alguns em auth de produção), `next-auth` em **beta** em produção, `npm ci --legacy-peer-deps`, pre-commit roda `npm run build` completo (lento), typos (`@swap/expanses-web`, `SelectOrganizarion.tsx`), README de `src/http` descreve arquivos inexistentes e chama código morto de "CRÍTICO".

---

## 4. Regras de negócio no front-end (que deveriam ser backend-authoritative)

O padrão de fundo: a fonte da verdade sobre **saldo, limite, elegibilidade, maioridade/KYC e status de KYB/aprovação** está duplicada ou originada no cliente. Risco duplo: **manipulação client-side** (a barreira é só `disabled`/`refine`) e **divergência** quando a regra muda (exige deploy do front). Vários pontos têm TODO do próprio time reconhecendo que deveriam ir ao backend.

### 🔴 Compliance / elegibilidade decidida no cliente

1. **Maioridade (KYC) calculada no cliente** — `src/utils/validate-is-not-adult.ts` faz `idade < 18` com relógio local e decide o payload: `motherName: validateIsNotAdult(...) ? motherName : null` em `features/organizations/model/mapFormToDTO.tsx:54` (e 76, 104, 306) e `features/people/model/mapFormToDTO.tsx`. O front decide se envia campo de compliance obrigatório para menores.
2. **Mock de KYB para "passar na validação"** — `src/features/organizations/model/v1-revenue-mocks.ts` injeta faturamento fictício só p/ satisfazer o contrato; comentário admite "Enforced backend-side em despesas-api KybRequestedEventHandler".
3. **"PF só pode selecionar Benefícios"** — superRefine em `organizations-create-schema.ts:63` (elegibilidade de produto por tipo de pessoa).
4. **Elegibilidade de distribuição no front (provisório)** — `benefit/pma/distribution/.../organization-transfer-list.tsx:39` lista todas as orgs como stopgap; TODO explícito de trocar por `useGetEligibleLimitOrganizationsAsync` quando o backend implementar.
5. **Status de KYB/aprovação derivado no front** — `table-body-organizations/index.tsx:355,412` (TODOs "Passar para o backend v1"); aprovação de despesa gated por string PT-BR `"Justificativa Pendente"` / `"Aprovação Pendente"` (`approvals` + `expenses`), acoplando fluxo a labels traduzidos.

### 🟡 Regras financeiras / limites duplicados no cliente

6. **Validação de saldo na distribuição** — `distribution-form.ts:62` soma itens e valida `totalInReais <= availableBalance` no Zod (duplicado em `benefit/pma`). Pré-validação de UX ok; única barreira = contornável.
7. **Cálculo de novo limite reparseando string formatada** — `components/Modal/change-limit.tsx:74` desfaz `"R$ 2.958,29"` com regex e subtrai (frágil a locale/arredondamento).
8. **Semântica de "saque" montada no front** — `manage-cards/components/hero.tsx` traduz "reduzir limite" em `createDistributionOrder({ isWithdraw: true })`.
9. **Thresholds/prazos hardcoded** — data de corte `new Date("2026-06-01")` (`table-body-organizations:63`, com TODO); teto de 10 cartões virtuais (`shared/forms/people/schema.tsx:53`); máx. R$ 1.000.000 de recarga; vencimento de boleto = `createdAt + 24h` no front; política de gastos com obrigatoriedade condicional (`create-policies-schema.ts:73`).

### ✅ Aceitável (formato/apresentação — não confundir)

- Validação de CPF/CNPJ (dígito verificador), e-mail, telefone, formato de nome — validação de formato duplicada no front como UX é padrão.
- `fromCents`/`toCents`, somas para exibir total, pintar de vermelho — apresentação.
- Máquinas XState de distribuição — só navegação de wizard (steps/visitados/erros), não decisão de negócio.

---

## 5. Performance

O usuário relata "portal lento, loadings dessincronizados". **Nenhum problema é arquitetural profundo** — são inconsistência de aplicação + otimizações triviais nunca ligadas.

### Causa dos "loadings dessincronizados"

- **303 checagens `isLoading/isPending` + 314 Skeleton/Loader, contra 7 `Suspense` boundaries.** Cada componente gerencia loading isoladamente, sem coordenação → cada caixa aparece/some no próprio tempo. É exatamente o sintoma relatado.

### Causas de re-fetch e flicker (loading duplo)

- **Query-key mismatch servidor↔cliente (landmine L8, confirmado)** — servidor (`extract-search-params.ts:26`) usa `orderBy: "Name"`; cliente (`use-pagination-params.ts:16`) usa fallback `"name"`. `"Name" ≠ "name"` na queryKey → o cliente ignora o prefetch e re-busca. A lista aparece pronta, pisca e recarrega. (Também há conversão página base-1↔base-0 que precisa bater.)
- **Waterfalls no cliente** — ex. `manage-cards` prefetcha só os cards; `useGetPersonById` não é prefetchado → cascata sempre no cliente.
- **Só 21 de 75 páginas prefetcham** — as demais buscam 100% no cliente após render.

### Números reais do build de produção (`next build`, 2026-08-14)

O build passou (exit 0, 60 páginas). Dados concretos que confirmam o diagnóstico:

- **First Load JS compartilhado por todas as rotas: 382 kB.** Baseline alto — toda página parte disso antes do próprio código.
- **Maior chunk compartilhado: 158 kB = Sentry** (`chunks/d10200fae21aa57d.js`, confirmado por inspeção de strings). Carregado em 100% das rotas.
- **Middleware: 193 kB** — pesado; roda em toda navegação (tenant + cookie + auth).
- **Faker vaza para o cliente — confirmado no build**: existe um chunk cliente (`chunks/4d5a1a1a852f9755.js`, ~81 kB) contendo faker. Não é teoria: está no bundle emitido.
- **First Load JS por rota chega a 543–576 kB** nas rotas quentes: `/` (543), `/expenses` (559), `/organizations/create` (565), `/people/create` (576), `/users/create` (568). Total de JS estático emitido: **~8 MB**.
- **CSS compartilhado: 52 kB** em todas as rotas.

Referência: o Next considera "verde" First Load JS abaixo de ~130 kB. Este projeto parte de **382 kB de baseline** e a maioria das telas fica entre **440–576 kB** — 3–4× o alvo. É consistente com a lentidão percebida no first load. As causas listadas abaixo são de configuração/bundling (baseline + splitting), não de estrutura de código.

### Causas de bundle grande / first load lento

- **Zero code splitting** — `next/dynamic` = 0 usos. Modais de 900L, tabelas de 750L, gráficos: tudo no bundle inicial (visível nas rotas `/create` em ~576 kB).
- **`next.config.ts` sem otimização** — falta `optimizePackageImports` (Mantine + `@tabler/icons-react` se beneficiam muito), sem config de `images`. Maior ROI, menor esforço.
- **Faker (4.9 MB) no bundle de produção** — `@faker-js/faker` em `dependencies`, importado via barrel por `lib/faker/index.ts` → `use-organization-data.tsx` (aparente código morto).
- **Libs redundantes** — `recharts` como dep direta com 0 imports (só `@mantine/charts`); `date-fns` + `dayjs` coexistem.

### ✅ O que está bem feito

- Layout privado é Server Component; QueryClient global bem configurado; padrão prefetch + HydrationBoundary idiomático onde aplicado; retry config sã.
- **Atenção isolada:** segundo `QueryClient` criado em `PagePoliciesWrapper.tsx` (cache separado, inconsistente).

---

## 6. Ações mapeadas (inventário)

Correções identificadas para os achados, com esforço estimado. Os itens **Imediatos** (segurança/compliance) aplicam-se independentemente da direção adotada; os demais são o roteiro caso o código seja mantido/evoluído. Não constituem recomendação de trajetória — são o custo mapeado de cada correção.

### Imediato (bloqueadores de segurança/compliance — valem em qualquer cenário)

| # | Ação | Esforço |
|---|---|---|
| 1 | Rotacionar Sentry token e removê-lo do `Dockerfile` (mover p/ secret de build) | Baixo |
| 2 | Garantir que o backend revalida compliance/elegibilidade (itens 1–5 da seção 4); front vira pré-validação de UX | Médio (coord. c/ backend) |

### Curto prazo (ganho rápido de performance e higiene)

| # | Ação | Esforço |
|---|---|---|
| 3 | `optimizePackageImports` no `next.config` (Mantine, tabler icons) | Baixo |
| 4 | Remover faker do bundle prod (mover p/ devDeps ou substituir por `Math.random`) + remover código morto | Baixo |
| 5 | Remover libs redundantes (`recharts` direto, unificar `date-fns`/`dayjs`) | Baixo |
| 6 | Alinhar query-keys server↔client (`"Name"` vs `"name"`, base-1/base-0) + guard de paridade | Baixo |
| 7 | `next/dynamic` nos modais/tabelas/gráficos pesados | Médio |

### Médio prazo (débito estrutural)

| # | Ação | Esforço |
|---|---|---|
| 8 | Extrair `imports-table` genérico (~1.500 linhas dupl.) e unificar `distribution`/`recharge` vs `benefit/pma/*` | Médio |
| 9 | Instalar test runner + testar o núcleo já testável (`createServerAction`, refresh singleflight, `evaluate-policy`) | Médio |
| 10 | Ligar `typescript/no-explicit-any` como `warn`; tipar fronteira auth (`JWT`/`Session`/usuário) | Médio |
| 11 | Deletar `client.ts` morto + logging comentado; decidir 1 caminho HTTP e planejar deprecação do `v1` | Médio |
| 12 | Adotar Suspense/streaming coordenado nas listas (reduzir os 303 loadings independentes) | Médio-Alto |
| 13 | Validação de env (schema Zod) + gate de type-check/lint/teste auditável no CI do repo | Baixo |
| 14 | Remover `pluginReactQuery` do SDK (extrair antes as key-factories) — apaga ~269 arquivos / ~31k linhas | Baixo-Médio |
| 15 | Trocar `build` por `tsc --noEmit` no `sdk:format`; consolidar scripts de patch; remover órfãos (`rename-operationid-v1`, `toPascalCase`) e `.backup` versionados | Baixo |
| 16 | Substituir XState de distribution por `use-steps` (já existe) e deduplicar `distribution`/`benefit/pma` | Médio |
| 17 | Deletar código morto: `TableGeneric/`, `PagePolicies/` + mocks, `list-old.tsx`, `http/old/`, `src/http/client.ts` | Baixo |
| 18 | Consolidar utilitários de moeda (3–4 variantes) e cadeia CNPJ (3 saltos) | Baixo |

---

## 7. SDK/codegen e over-engineering

### 7.1 SDK gerado (Kubb a partir de OpenAPI)

O SDK é gerado em `src/lib/sdk/generated` (923 arquivos: 477 types, 269 hooks, 176 requests) por um pipeline de ~8 scripts. Achados concretos:

- **268 hooks React Query gerados = dead code** — o `pluginReactQuery` (`kubb.config.ts:52`) gera 269 arquivos de hooks `useXxxAsync`, mas **0 são importados fora de `generated/`**. O time usa factories próprias (`createQueryHook`/`createMutationHook`) sobre services `withApiClient`. Só as `getXxxQueryKey`/`MutationKey` (que moram nesses arquivos) são aproveitadas — 178 query-keys e 145 mutation-keys usadas, contra 0 hooks e 5 `queryOptions`. Os arquivos de hooks somam ~31.345 linhas lintadas/type-checadas a cada regeneração sem consumidor do hook em si.
- **Merge "último vence" silencioso** — `merge-openapi.js` funde 3 specs (benefícios/core/despesas) sobrescrevendo chaves iguais. Medido: **21 schemas duplicados** entre os specs (`Product`, `Address`, `AccountHolderParty`, `AnnualRevenueRange`...) são sobrescritos com apenas `console.warn`. Se dois microserviços definem o mesmo schema com shapes diferentes, o tipo gerado fica errado para um dos contextos sem falhar o build.
- **Patch por regex sobre TS gerado** — `patch-org-types.js` reescreve o response 200 de `GetOrganizationById` para uma união PJ/PF via regex que depende de nome de alias exato e do shape `accountHolderType?: string | null`. Contorna uma limitação real do Kubb 4.x (não gera union de `oneOf`+`discriminator`), mas quebra silenciosamente (`console.warn`) em upgrade do Kubb ou mudança de formatação. Um arquivo gerado (`ProblemDetails.ts`) é mantido via `git restore` após cada geração.
- **Scripts com defeitos** — `convert-query-params-to-pascal.js` chama `toCamelCase` apesar do nome (a função `toPascalCase` é dead code no próprio script); `rename-operationid-v1.js` é um script órfão (existe como npm script mas não está em `sdk:local`/`sdk:online`); 3 `.openapi.json.backup` estão versionados; `check-operation-ids.js` valida colisão intra-arquivo mas não a cross-arquivo que o merge introduz.
- **Regeneração dispara build de produção** — `sdk:format` (passo final de todos os pipelines de SDK) roda `lint && format && build`. Regenerar tipos compila a app inteira (minutos); `tsc --noEmit` validaria a geração sem isso.

### 7.2 Camadas de indireção HTTP

Uma chamada de API atravessa 6 hops: componente → hook (factory) → service (`withApiClient`) → `createApiClient` → `client-wrapper` → `server-api-client` → `kubbFetch`/`ky-adapter` → `getApi` → ky. Alguns hops não agregam valor:

- `server-api-client.ts` (13 linhas) só repassa para `kubbFetch` — wrapper trivial.
- `client-wrapper.ts:3` recebe `context: "server" | "client"`, mas o único chamador (`with-api-client.ts:19`) sempre passa `"server"`. O branch `"client"` — e todo o `src/http/client.ts` (312 linhas) que ele importa, incluindo hierarquia `TenantProvider` e logging construído-e-comentado — é inalcançável em runtime.

### 7.3 Over-engineering no código de aplicação

- **XState para navegação de wizard** — as máquinas `distribution-form.machine.ts` (198 l) + hooks associados (~580 l no total) codificam apenas step1→2→3, sem invoke/actors. A informação "passo atual" existe triplicada (estado XState + `context.currentStep` + refs React), sincronizada à mão. O próprio repo já tem `src/hooks/use-steps.ts` (45 linhas, `useState`) que resolve o mesmo problema e é usado por `organizations` e `policies`. O `footer.tsx` nem usa a máquina como fonte de verdade (recorre a um util `generateStepStates`).
- **Código morto versionado** — `TableGeneric/` (170 l, 0 usos) coexiste com `DataTable` (6 usos); `PagePolicies/` + mocks (`employees.ts` 4.504 l, `policies.ts` 6.212 l, 0 consumidores) é um demo esquecido em `src/`; `list-old.tsx` (125 l) e `create-policies-schema-old.ts` órfãos; diretório `http/old/`.
- **Nomeação enganosa** — os 8 `shared/forms/*/form-context.tsx` não chamam `createContext` (são pass-throughs que leem `useFormContext` do RHF e repassam props); `TabNavigation` + `TabNavigationV2` coexistem (migração inacabada).
- **Utilitários duplicados** — 3–4 variantes de formatação/conversão de moeda BRL (`format-currency.ts`, `cents-to-brl.ts`, `currency-conversion.ts` + `Intl.NumberFormat` inline); cadeia de 3 saltos para validar CNPJ (`validators/cnpj.ts` → `utils/validate-cnpj.ts` → `utils/cnpj.ts`); `ExtractValueFromServerActionFunction` copiado nas 2 factories.
- **Más práticas pontuais** — 29 `key={index}` (aceitável em skeletons estáticos, latente em tabelas de dados reais como os 3 `imports-table.tsx`); estado derivado dentro de `useEffect` que deveria ser `useMemo`/render (`form-step-1.tsx:31`, `payment-method-fields.tsx:41`); ~95 linhas de código comentado.

### 7.4 O que foi avaliado e considerado justificado

- **Split v1/v2** (43+ branches `version === "v1"|"v2"`, hooks duplos) — **não** é generalização prematura: `config/tenant-features.ts` mostra tenants reais ainda em v1 em produção e outros em v2. É migração multi-tenant viva. Ressalva: é a maior fonte de dobra de manutenção contínua — vale um plano de remoção do v1 quando possível.
- `utils/cnpj.ts` com flag `CNPJ_ALPHANUMERIC_ENABLED` — single source of truth justificada.
- Factories `createQueryHook`/`createMutationHook`, `use-steps`, `use-modals` — abstrações com uso real e disseminado.

---

## 8. Viabilidade de modularização

Avaliação da capacidade de o código evoluir para módulos isolados (várias features, fronteiras explícitas). Métricas medidas do estado atual:

### Sinais favoráveis

- **Grafo de features acíclico** — há 162 imports cross-feature, mas **zero ciclos** entre features (medido: nenhum par `A↔B` mútuo). Ciclos são o bloqueador fatal da modularização; sua ausência permite ordenar os módulos em camadas e extraí-los incrementalmente.
- **Organização já por domínio** — `src/features/{domain}/` e `src/app/(private)/{domain}/` espelham features. A intenção modular já existe na estrutura de pastas.
- **Infra compartilhada separada** — acoplamento a `@/lib` (151 arquivos), `@/components` (170), `@/http` (25) é o tipo saudável (núcleo comum). Já é o embrião de um pacote `core`/`shared`.
- **`benefit` como ensaio de módulo** — o sub-namespace aninhado (`benefit/pma/{distribution,recharge}`) mostra tendência do time a agrupar por módulo.

### Obstáculos (o que precisa mudar antes)

- **Zero fronteiras públicas** — nenhuma feature tem barrel/`index.ts` público. **150 dos 162 imports cross-feature furam direto para caminhos internos** (`organizations/components/...`, `people/hooks/...`). Sem superfície pública, "módulo" é só uma pasta.
- **`organizations` é hub, não módulo** — importado por 62–73 arquivos externos, importa apenas 4. É base compartilhada de fato; parte dele (headers de produto, seletor de org, `table-body-loading`) pertence ao `core`, não a um módulo isolado.
- **Vazamento de UI entre features** — ex.: `organizations/components/table-body-loading` é importado por 7 outras features (`order`, `expenses`, `policies`, `people`, `manage-cards`, `reports`). É um componente compartilhado morando dentro de uma feature.
- **Single package, sem tooling de monorepo** — sem workspaces, Turbo ou Nx. Fronteiras só podem ser convenção até que o build possa impô-las.

### Caminho incremental (sem rewrite)

| Fase | Ação | Efeito |
|---|---|---|
| 1 | `index.ts` público por feature + regra de lint (`no-restricted-imports`) proibindo import de caminho interno de outra feature | Cria a fronteira e impede regressão |
| 2 | Extrair `core`/`shared` real (o que mora em `organizations` mas é usado por todas + `@/lib` + `@/components`) | Separa núcleo comum dos módulos |
| 3 | Migrar os 150 imports internos para a API pública, um módulo por vez (ordem acíclica permite) | Reduz acoplamento com app sempre funcional |
| 4 | *Se/quando* necessário: workspaces (Turbo/Nx) + pacotes versionáveis | Fronteira imposta pelo build |

As fases 1–3 entregam modularidade lógica sem monorepo. A fase 4 (pacotes físicos) só se justifica para build isolado, times independentes ou publicação — pode nunca ser necessária.

**Verificação de tooling**: `no-restricted-imports` com `patterns` foi testado no oxlint 1.72 do projeto e **funciona** (detectou imports internos cross-feature). A fase 1 é executável sem adicionar dependências.

**Dependências desta trajetória**: dois débitos das seções anteriores atrapalham diretamente — a **ausência de testes** (mover código entre fronteiras sem rede de segurança é arriscado) e a **duplicação copy-paste** (decidir onde código sem dono claro "mora" trava a extração). Convém endereçá-los em paralelo à fase 1.

---

## 9. Síntese

O repositório combina uma **base técnica consistente** (sessão, server-actions, data-fetching, roteamento, documentação — implementações corretas que resolvem problemas reais de Next.js) com um **débito concentrado e nomeável** (duplicação copy-paste, camada HTTP fragmentada, ausência de testes). Os problemas de performance medidos são de configuração e otimizações padrão não aplicadas, não de bug arquitetural.

O fator estrutural mais relevante é a **ausência de rede de segurança** — testes ≈ 0% somados a lint que desliga `no-explicit-any`/`exhaustive-deps`. É o que permitiu o débito (duplicação, `any` pervasivo, regras de negócio no cliente) acumular sem detecção. Qualquer trajetória de evolução do produto interage diretamente com esse fator.

Os dados das seções 2–6 e o plano de ação da seção 6 quantificam esforço e risco de cada item, servindo de insumo para a decisão de direção — que fica a cargo de quem lê.
