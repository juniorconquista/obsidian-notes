# Processo Seletivo — João Firmino | 15/07/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que tope generalizar para back
**Status:** Shortlist final (4 candidatos) — a definir após entrevistas

---

## Perfil

- **LinkedIn:** linkedin.com/in/firminoweb
- **Portfólio:** github.com/firminoweb | firmino.dev
- **Experiência:** 16+ anos — Itaú Unibanco (atual), O Boticário, TOTVS, UOL, Walmart, Santander, Vivo
- **Stack:** Angular (9+ anos), React/Next.js (6+ anos), Node.js, React Native, TypeScript

## Por que está na shortlist

- **Único candidato que já se descreve literalmente como o perfil pedido:** ele mesmo caracteriza seu trabalho no Itaú como "60% Front-end / 40% Back-end" — não é disposição declarada, é o que ele já faz.
- Maior escala e maturidade dos 4 finalistas — 16 anos, passagem por bancos e enterprises de grande porte.
- Já mentora devs seniores, lidera revisão de código e padrões.
- Usa IA aplicada ao fluxo de desenvolvimento (Claude, Cursor) — bate com o diferencial da vaga.
- Acessibilidade (WCAG 2.1 AA) — bate com diferencial de a11y.

## Gaps a validar

- Sem menção a .NET/C# — backend dele é Node.js.
- Domínio é mais "enterprise geral" (bancos, varejo) do que "fintech de pagamentos/carteiras" especificamente — vale confirmar profundidade real em meios de pagamento.
- Não confirma Next.js App Router, React Query, testes E2E (Playwright) explicitamente.
- CQRS/DDD/Clean Architecture não mencionados — ele vem mais do lado Angular/React enterprise que de arquitetura backend estruturada.

---

## Roteiro de Entrevista Técnica

### 1. Abertura
- No Itaú você descreve seu trabalho como 60% front / 40% back — me conta um exemplo real de feature onde você transitou entre as duas pontas na mesma entrega.
- De todos os lugares por onde você passou (Itaú, Boticário, TOTVS, Santander, Vivo), qual foi o ambiente mais parecido com "sem nicho, todo mundo faz tudo"? Como foi?

### 2. Transição para .NET/C# (gap principal)
- Você tem 9+ anos de Angular e uso pesado de TypeScript — já teve contato com C#/.NET em algum momento da carreira?
- Como você reagiria a assumir tickets de backend em .NET no dia a dia, não só quando sobra tempo?
- Como você usa IA (Claude, Cursor) no fluxo hoje — isso te ajudaria a acelerar essa transição de stack?

### 3. Profundidade de front-end
- Fala sobre a migração de páginas legadas pra arquitetura moderna que você liderou — quais foram as decisões mais difíceis?
- Você tem experiência com Next.js App Router e Server Components, ou seu uso de Next.js é mais com Pages Router?
- Testes E2E (Playwright) fazem parte do seu fluxo, ou você usa só Jest/Testing Library?

### 4. Domínio fintech/pagamentos (validar profundidade real)
- No Itaú e no Santander, você chegou a mexer diretamente com fluxos de pagamento, cartões, PIX, ou seu trabalho era mais em sistemas internos/administrativos?
- Já teve contato com regulação (BACEN, LGPD) no dia a dia de algum projeto?

### 5. Arquitetura e padrões
- Você já ouviu falar ou trabalhou com CQRS, DDD, Clean Architecture? Mesmo informalmente, seu código já seguia alguma separação parecida?
- Como era a arquitetura multi-tenant (se houve) nos projetos internos do Itaú?

### 6. Senioridade e autonomia
- Me conta de um incidente de produção que você resolveu com autonomia total.
- Como funciona sua mentoria hoje — que tipo de dev você já ajudou a evoluir?
- Reação a entrar num time que hoje é nichado (só front ou só back) e virar a ponte entre as duas pontas?

### 7. Fechamento
- Pretensão salarial e disponibilidade.
- Motivo de estar buscando nova oportunidade saindo do Itaú.

## Sinais de alerta a observar
- 🚩 Resistência a .NET no dia a dia (mesma bandeira do roteiro do Jean)
- 🚩 Respostas genéricas sobre "60/40 front/back" sem exemplo técnico concreto — pode indicar que o front domina muito mais que o back na prática
- ✅ Exemplos reais de mentoria e revisão de padrões — reforça maturidade sênior acima da média dos outros candidatos


---

## Gabarito — O que esperar em cada resposta

### 1. Abertura (60% front / 40% back)

**"Exemplo real de transição entre front e back na mesma entrega"**
- ✅ Forte: exemplo específico, com decisão técnica em cada ponta, não só "eu fazia os dois".
- 🚩 Fraca: fala em termos vagos, ou quando pressionado revela que uma das pontas era só manutenção simples enquanto a outra era o trabalho "de verdade".

**"Ambiente mais parecido com 'sem nicho'"**
- ✅ Forte: cita exemplo concreto de time pequeno/ágil onde ele genuinamente circulava entre as pontas.
- 🚩 Fraca: não consegue identificar nenhum ambiente assim — sinal de que ele sempre trabalhou em estruturas mais nichadas, mesmo tendo as duas skills.

### 2. Transição para .NET/C#

- ✅ Forte: mesmo sem experiência prévia, mostra abertura genuína e cita paralelos entre Angular/TS (tipagem forte, OOP) e o que ele sabe de C#.
- Aceitável: nunca usou, mas pergunta como o time apoiaria essa curva (mostra planejamento, não so concordância vazia).
- 🚩 Fraca: minimiza a dificuldade ("é tudo igual") ou demonstra relutância clara.
- ✅ Forte (uso de IA): já usa Claude/Cursor de forma crítica, não só como autocomplete — isso é diferencial real dele frente aos outros 3, vale explorar a fundo.

### 3. Profundidade de front-end

**"Migração de páginas legadas — decisões mais difíceis"**
- ✅ Forte: menciona trade-offs reais (performance vs. compatibidade, escopo de rollback, comunicação com stakeholders durante a migração).
- 🚩 Fraca: descreve só "a gente migrou" sem entrar em decisão técnica nenhuma.

**"Next.js App Router / Server Components"**
- Aceitável: não ter usado ainda — é o gap mais fácil de fechar, igual no caso do Jean.
- 🚩 Fraca: confundir com outra tecnologia ou nunca ter ouvido falar mesmo depois de uma explicação rápida.

**"Testes E2E no fluxo"**
- ✅ Forte: testes fazem parte do PR normal, ele mesmo escreve.
- 🚩 Fraca: delega isso 100% pra QA ou outro time.

### 4. Domínio fintech/pagamentos

- ✅ Forte: cita exemplo concreto de trabalho com PIX, cartões, ou fluxo financeiro real no Itaú/Santander, com detalhe técnico.
- 🚩 Fraca: admite que o trabalho era mais em sistemas administrativos internos, sem contato direto com fluxo de pagamento — não é desqualificador, mas reduz a vantagem de "domínio fintech" que o currículo sugeria.

### 5. Arquitetura e padrões

- ✅ Forte: reconhece os conceitos de CQRS/DDD quando explicados e relaciona com algo que já fez, mesmo informalmente.
- 🚩 Fraca: nunca ouviu falar e não consegue relacionar com nada da própria experiência.

### 6. Senioridade e autonomia

**"Incidente de produção resolvido com autonomia"**
- ✅ Forte: exemplo real com processo claro (diagnóstico → ação → prevenção).
- 🚩 Fraca: sempre escalava para outra pessoa ou não tem exemplo.

**"Reação a virar a ponte entre front e back"**
- ✅ Forte: resposta natural, reforçada por já ter feito isso na prática em algum momento dos 16 anos — não é sobre concordar, é sobre já ter vivido essa dinâmica.
- 🚩 Fraca: concorda "no papel" sem nenhum exemplo real de ter feito isso.

## Nota importante
Este gabarito é guia de calibração, não checklist rígido. Dado que o João tem a trajetória mais longa dos 4 candidatos, dê atenção especial a saber se a profundidade técnica acompanhou os 16 anos ou se ficou mais rasa/gerencial com o tempo.
