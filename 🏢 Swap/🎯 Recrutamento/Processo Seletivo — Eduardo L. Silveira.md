# Processo Seletivo — Eduardo L. Silveira | 17/07/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que tope generalizar para back
**Origem:** Indicação do Santi (junto com Jean e Lucas Verdan)
**Status:** Shortlist expandida (6 candidatos) — a definir após entrevistas

---

## Perfil

- **LinkedIn:** linkedin.com/in/elsilveira
- **Portfólio:** eduardosilveira.dev
- **Experiência:** 10+ anos — Stamp (França, até abr/2026), Vengreso, BMW Group US, Layer (Irlanda, bank-as-a-service), Trio
- **Stack:** React, Next.js, Angular, TypeScript, Node.js, Python, GraphQL/REST — front-leaning fullstack

## Por que está na shortlist

- **Perfil mais "AI-native" dos 6 finalistas** — construiu camada própria de orquestração de IA (SemanticIR), fluxos com LLMs/RAG/LangChain e widgets MCP. Bate direto com o diferencial "vivência em times que adotam agentes de IA no fluxo de desenvolvimento" — provavelmente o mais forte dos 6 nesse quesito específico.
- **Domínio fintech real:** na Layer (Irlanda), construiu features core de uma plataforma bank-as-a-service atendendo múltiplos clientes enterprise — bate diretamente com "arquitetura modular/multi-tenant" e "plataformas whitelabel" da vaga.
- Já refatorou frontend legado para Next.js + TypeScript, reduzindo tempo de carregamento em ~30% — sinal de profundidade real em performance e arquitetura.
- Passagem por BMW Group (aplicações financeiras) e Stamp (marketplace de alto tráfego) — variedade de domínios de escala.
- Curiosamente, teve uma passagem breve (2018) com **React Native, Angular, C# e .NET** na EASYCOMTEC — não é nível sênior nessa stack, mas mostra que já teve contato, ainda que superficial e antigo.

## Gaps a validar

- Título mais recente é "Frontend-Leaning Fullstack" — ele mesmo se posiciona como front primeiro, back quando necessário. Vale confirmar o quanto ele realmente topa se aprofundar em back no dia a dia, vs. eventualmente.
- Contato com .NET é de 2018, breve (4 meses) — na prática, equivale a quase nenhuma experiência relevante hoje.
- Testes: menciona Jest e Cypress, mas não fica claro o nível de cobertura/rigor.
- Trajetória com bastante mobilidade internacional (França, Irlanda, EUA, Brasil) — vale entender preferência de fuso e estabilidade de longo prazo.
- Não menciona React Query nem Tailwind especificamente.

---

## Roteiro de Entrevista Técnica

### 1. Abertura
- Você se descreve como "frontend-leaning fullstack" — o que isso significa na prática pro seu dia a dia? Qual a proporção real de front vs. back nos últimos projetos?
- Na Stamp, você teve ownership completo (arquitetura, IA, produção) — como era um dia típico seu ali?

### 2. Transição para .NET (gap principal)
- Você teve uma passagem breve com C#/.NET em 2018 — o que lembra dessa experiência? Foi suficiente pra ter alguma base, ou foi superficial?
- Como você reagiria a assumir tickets de backend em .NET no dia a dia, de forma consistente e não eventual?

### 3. IA no fluxo de desenvolvimento (ponto forte único dele — aprofundar)
- Fala sobre o SemanticIR — que problema ele resolvia e como funcionava na prática?
- Como você usa IA (Copilot, Cursor, Claude) hoje no seu fluxo — é algo pontual ou parte estruturada do processo?
- Como isso mudaria (pra melhor ou pior) sua velocidade de aprender uma stack nova como .NET?

### 4. Domínio fintech / multi-tenant (ponto forte — validar profundidade)
- Na Layer, como funcionava a arquitetura pra atender múltiplos clientes enterprise (bank-as-a-service)? Como configuração por cliente era resolvida?
- Já lidou com autenticação/MFA, compliance ou dados sensíveis nesse contexto?

### 5. Front-end — validar profundidade adicional
- Next.js App Router / Server Components — já usou na prática (Next 13/14 sugere que sim)?
- Testes E2E (Cypress) fazem parte do fluxo normal de PR, ou são esporádicos?

### 6. Trajetória e estabilidade
- Percebo bastante mobilidade internacional nos últimos anos — o que você busca agora em termos de estabilidade e fuso horário?
- Motivo de ter saído da Stamp em abril/2026?

### 7. Fechamento
- Pretensão salarial e disponibilidade/fuso horário atual.

## Sinais de alerta a observar
- 🚩 Se ele deixar claro que "back é só quando não tem jeito", isso reforça o risco de ele continuar nichado em front, mesmo topando verbalmente generalizar.
- 🚩 Respostas vagas sobre SemanticIR ou sobre a arquitetura multi-tenant da Layer — indicaria currículo mais polido que a realidade.
- ✅ Entusiasmo genuíno em usar IA pra acelerar aprendizado de .NET — maior diferencial competitivo dele frente aos outros 5.


---

## Gabarito — O que esperar em cada resposta

### 1. Abertura (proporção real front/back + ownership na Stamp)

- ✅ Forte: consegue quantificar com honestidade a proporção real (ex: "80% front, 20% back quando precisa") e dá exemplo técnico de cada lado.
- 🚩 Fraca: resposta vaga tipo "eu faço os dois igual", sem conseguir dar exemplo concreto do lado back.

### 2. Transição para .NET (gap principal)

**"O que lembra da experiência com .NET em 2018?"**
- ✅ Forte: mesmo sendo pouco e antigo, consegue falar com alguma propriedade sobre o que fez, mostrando que reteve algo.
- Aceitável: reconhece que foi muito breve e superficial, sem tentar inflar a experiência.
- 🚩 Fraca: tenta vender essa experiência de 4 meses como mais relevante do que realmente foi — sinal de possível inflação de currículo em outras áreas também.

**"Reação a assumir back em .NET no dia a dia"**
- ✅ Forte: entusiasmo real, idealmente reforçado por já ter trocado de stack antes (ele já trabalhou com múltiplas linguagens/frameworks ao longo da carreira).
- 🚩 Fraca: deixa claro que prefere continuar "front primeiro, back só quando não tem jeito" — é exatamente o padrão dele hoje, então a pergunta é se ele têm real intenção de mudar isso.

### 3. IA no fluxo (maior diferencial dele — aprofundar bastante)

**"SemanticIR — que problema resolvia?"**
- ✅ Forte: explica com clareza técnica o problema (contexto de codebase para LLMs) e a solução, sem só repetir termos do currículo.
- 🚩 Fraca: não consegue detalhar além do que está escrito — sinal de projeto mais experimental/pessoal do que robusto em produção.

**"Como isso mudaria sua velocidade de aprender .NET"**
- ✅ Forte: resposta concreta de como ele usaria IA pra acelerar (ex: gerar boilerplate, entender padrões do time, revisar seu próprio código com mais rigor).
- 🚩 Fraca: resposta genérica ("a IA ajuda em tudo hoje em dia") sem conexão específica com o desafio de aprender uma stack nova.

### 4. Domínio fintech / multi-tenant

- ✅ Forte: explica com detalhe técnico real como a Layer resolvia configuração por cliente (feature flags, dados por tenant, etc.) — deve ser um ponto forte real do currículo dele.
- 🚩 Fraca: resposta rasa, sugerindo que o trabalho era mais de execução de feature do que de decisão arquitetural.

### 5. Front-end adicional

- ✅ Forte: confirma uso real de Next.js App Router (a menção a Next 13/14 no currículo sugere que sim).
- 🚩 Fraca: só usou Pages Router, currículo sugeriu mais do que a realidade.

### 6. Trajetória e estabilidade

- ✅ Forte: motivos claros e específicos para cada mudança (visto, oportunidade de crescimento, fim de contrato) — mobilidade internacional não é red flag se bem explicada.
- 🚩 Fraca: padrão de insatisfação repetida ou resposta evasiva sobre por que sai de cada lugar em menos de 2 anos.

## Nota importante
Ele é o candidato dos 6 com o diferencial mais único (IA aplicada ao desenvolvimento) — isso pode compensar bastante o gap de .NET, especialmente se ele mostrar que usaria essa mesma capacidade pra acelerar a própria curva de aprendizado. Vale validar isso com genuína curiosidade na entrevista, não só como checkbox técnico.
