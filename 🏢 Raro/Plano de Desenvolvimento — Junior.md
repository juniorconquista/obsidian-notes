# 🚀 Plano de Desenvolvimento — Junior Oliveira

**Criado em:** 26/06/2026
**Contexto:** Junior está numa posição única na Swap — gestor técnico com background forte em frontend, exposto a todas as frentes de engenharia, produto e negócio fintech. Objetivo: aproveitar ao máximo essa janela para se desenvolver como engenheiro completo.

---

## Frentes de aprendizado identificadas

### 1. 🔧 Backend — Node.js / Elixir
**Por que é importante:** O gargalo do time hoje é backend. Entender o que está sendo feito te dá autoridade técnica real nas decisões e te tira da dependência de terceiros para entender o tamanho dos problemas.

**O que está disponível aqui:**
- Santi e William trabalhando no RTF diariamente — código aberto no GitLab
- Paulo construindo o multiorg da Niky — PR aberto para revisão
- William construindo a home do app — pode acompanhar de perto

**Como aproveitar:**
- [ ] Pedir ao Santi 30 min por semana para te explicar o que ele está construindo
- [ ] Ler os PRs abertos no GitLab — não precisa entender tudo, mas começar a reconhecer os padrões
- [ ] Quando surgir um bug simples no backend, tentar investigar antes de passar para o time

---

### 2. ☁️ Infraestrutura — AWS / ArgoCD / Kubernetes
**Por que é importante:** Você já está participando de decisões sobre deploy, IP fixo, ambientes. Entender a infra te dá visão do sistema completo.

**O que está disponível aqui:**
- ArgoCD — você tem acesso a DEV e STG
- AWS DEV e STG — acesso PowerUser
- HashiCorp Vault STG — secrets e credenciais
- Deploys acontecendo toda semana — oportunidade de acompanhar ao vivo

**Como aproveitar:**
- [ ] Na próxima subida importante, pedir para acompanhar o deploy no ArgoCD ao vivo com alguém do time
- [ ] Entender como funciona o pipeline GitLab → ArgoCD → Kubernetes no contexto da Swap
- [ ] Perguntar ao Santi ou William como funciona o processo de deploy quando algo dá errado (rollback)

---

### 3. 🔐 Segurança e Autenticação — Keycloak / Cognito / Cloudflare
**Por que é importante:** Você já entende Keycloak conceitualmente. A Swap usa autenticação em múltiplas camadas — aprofundar aqui te diferencia muito.

**O que está disponível aqui:**
- Keycloak DEV e STG — acesso direto
- Discussão ativa sobre federação de identidade (Kontik, Tourhouse)
- Cloudflare Access em uso

**Como aproveitar:**
- [ ] Explorar o Keycloak DEV — criar um realm de teste, entender como funciona a federação
- [ ] Acompanhar a evolução da demanda da Tourhouse/Kontik — ela é um case real de autenticação federada

---

### 4. 💳 Negócio Fintech — Ledger / Processadora / Cartões / KYC
**Por que é importante:** Você está gerindo um time que entrega produtos financeiros complexos. Entender o negócio te torna um gestor muito mais eficaz e abre portas para posições de liderança em fintechs.

**O que está disponível aqui:**
- Santi explicou o funcionamento da Ledger, priority vs name balance
- Paulo trabalhando com tombamento, multiorg, notas fiscais
- KYC, RTF, wallets — todos rodando no seu time

**Como aproveitar:**
- [ ] Toda vez que surgir um conceito novo (Ledger, PMA, RTF, combo card), registrar aqui uma explicação simples com suas palavras
- [ ] Pedir ao Paulo uma sessão de 1h para entender o fluxo completo do dinheiro na Swap — da recarga até o cartão
- [ ] Acompanhar a reunião com a ANIC sobre notas fiscais — é negócio puro

---

### 5. 📊 Dados e Métricas — Metabase / Analytics
**Por que é importante:** Você já está construindo reports do helper e faróis de entrega. Aprofundar em dados te dá argumentos concretos para qualquer conversa com liderança.

**O que está disponível aqui:**
- Metabase com acesso
- Time de dados parceiro (já ajudou no Shortcut)
- Iniciativa do canal Helper — dados reais para explorar

**Como aproveitar:**
- [ ] Explorar o Metabase — ver quais dashboards existem para o Portal Benefícios
- [ ] Na próxima análise do Helper, tentar construir pelo menos uma query simples você mesmo

---

### 6. 🏗️ Arquitetura de Sistemas
**Por que é importante:** Você já está tomando decisões que afetam arquitetura — multiorg, federação, webhook. Ter um modelo mental claro de como sistemas distribuídos funcionam te eleva muito.

**O que está disponível aqui:**
- Discussões reais acontecendo todo dia — webhook vs CSV, IP fixo, STG vs Prod
- Santi tem visão arquitetural profunda — é uma fonte de ouro

**Como aproveitar:**
- [ ] Toda decisão arquitetural que passar por você, anotar aqui o raciocínio — por que escolhemos A e não B
- [ ] Pedir ao Santi para te explicar a arquitetura completa do WL 2.0 em uma sessão

---

## Registro de aprendizados

*Aqui você vai registrando coisas que aprendeu ao longo do tempo — conceitos, decisões, insights técnicos.*

---

## Métricas de evolução

- **Mês 1 (junho):** Entrei sem conhecer o negócio. Aprendi: Keycloak, Ledger, ArgoCD, pipeline de deploy, fluxo de KYC, RTF
- **Mês 2 (julho):** _a preencher_
- **Mês 3 (agosto):** _a preencher_

---

# Reconhecimento recebido — kudos

Registro dos kudos recebidos no programa de reconhecimento entre pares da Swap.
Acumulam ao longo do ano; quem acumula mais aparece como destaque no fim.
**Isto é evidência, não elogio guardado** — o ciclo avaliativo do 2º semestre exige
uma entrega atrelada a cliente, e todos os seis abaixo estão na categoria
*impacto positivo nos clientes*.

## Ciclo de julho/2026 — seis kudos, de seis áreas diferentes

**Alexandre Winandy — Organizações (COO e fundador)**
> "Segurou a onda com o time de tombar volume da Niky e resolver o backlog da
> FACISC. Um alto volume de ações e complexidade, que teve uma grande mobilização
> do time para nada quebrar."

**Carolina de Lemos — Suporte**
> "Reconhecimento por toda a parceria ao longo desses últimos meses. Mesmo diante
> de um cenário desafiador, com alto volume de tickets e problemas, tem conduzido as
> demandas com muita excelência, transparência e visibilidade. Vem atuando de forma
> consistente na raiz dos problemas, estruturando planos de ação para melhorar o
> portal dos nossos clientes, trazendo feedbacks relevantes e estando sempre muito
> disposto a ajudar."

**Lucas Ferreira da Silva — Tecnologia**
> "O Junior tem diminuído a distância entre os clientes e o time WL e também entre o
> time WL e a gestão Swap. Firmando pontes e dando visibilidade a todo o trabalho."

**Alana de Bem Nogueira — Enterprise**
> "Junior tem se desdobrado com paciência e proatividade em coordenar o atendimento
> de tickets do WL, que vem enfrentando dificuldades pelo capacity."

**Luisa Martins Fanzeres — Growth Care**
> "Junior tem apoiado na resolução de problemas de clientes com Interfaces. Sempre
> disponível e disposto a ajudar!"

**[[Andrey Cunha]] — Interfaces** *(o único de dentro do time)*
> "Junior sempre liderando e direcionando muito bem o time de Interfaces. Mesmo em
> momentos delicados e com muitos atritos não deixa o clima do time perder a
> leveza."

## Ciclo de junho/2026

**Guilherme Andrade — Risco**
> "Junior, queria agradecer pela parceria nesse trabalho de evolução do SDK de
> biometria. Foi muito bom construir essas melhorias em conjunto, sempre discutindo
> soluções e buscando o melhor resultado. Acho muito legal a sua preocupação com os
> detalhes, seja em performance, usabilidade, experiência do usuário, tratamento de
> erros ou nos pequenos ajustes que fazem diferença no produto final. Esse cuidado
> elevou bastante a qualidade das entregas."

---

## O que os seis dizem juntos

**Cinco dos seis vieram de fora do time.** Quatro são de áreas de CSO — Suporte,
Enterprise, Growth Care — que eram justamente o outro lado do atrito. Quem
reconheceu foi quem sofria o problema, não quem trabalha ao seu lado.

**Três temas se repetem, e os três são meta sua:**

1. **Ponte e visibilidade** — dito pela Tecnologia e pelo Suporte. Vale notar que a
   referência é **julho**, ou seja, antes do [[Report à Diretoria — Niky e Operação WL]]
   e de tudo que foi montado na semana de 04 a 08/08. A percepção de ponte já
   existia; o que veio depois foi o mecanismo.
2. **Causa raiz** — *"atuando de forma consistente na raiz dos problemas,
   estruturando planos de ação"*. É a entrega **7A** dos direcionadores, dita por
   quem recebe o resultado.
3. **Clima sob pressão** — o único de dentro do time.

**O kudos do Winandy é o mais pesado, e por uma razão específica.** Fundador não
escreve *"para nada quebrar"* por educação: ele está reconhecendo que uma operação
de alta complexidade **aguentou**, que é a régua de quem olha risco.

E ele corrige um desequilíbrio: **na review da empresa de 07/08, o tombamento da
Niky foi narrado pelo CSO e os nomes que ficaram foram Paulo e Thales** — você não
foi citado. No mecanismo que existe para reconhecimento individual, quem te nomeou
por esse mesmo trabalho foi o COO.

---

# Kudos do time — 34 acumulados

Visão consolidada dos reconhecimentos recebidos pelos liderados diretos, em
08/08/2026.

| Categoria | Total |
|---|---|
| Impacto positivo nos clientes | **28** — 82% |
| Problema histórico da Swap | 5 |
| **Processo inteligente com IA** | **1** |

## O time é reconhecido por absorver dor, não por eliminá-la

Você disse à Luma em 05/08 que *"nosso time sofre muito com um histórico de cobrança
alta e não tanto reconhecimento"*. Os 34 kudos mostram que reconhecimento existe —
**mas está concentrado numa coisa só**.

O contraste com a avaliação do 1º semestre é grande: **as sete pessoas do time
tiveram entrega de IA registrada no GUP** — o [[Gabriel Santi]] usando IA para
escrever regras de negócio e montar cards, a [[Pietra Oliveira]] construindo o
dashboard analítico do Helper do zero, o [[Stive Tormes]] aplicando ao fluxo mobile,
o [[Bruno Conti]] em regras e automação, o [[Andrey Cunha]] criando o hub de suporte
do Helper, o [[Regis Graf]] medindo eficiência de IA contra método manual em cinco
cards, e o [[Túlio Cruz Ferreira da Silva]] usando NotebookLM e Gemini para virar
reunião em história de usuário.

**Sete entregas de IA no semestre, um kudos.** E cinco em "problema histórico",
quando a meta **7A** do time é justamente atacar causa raiz de problema recorrente.

## Por que isso vira problema no 2º semestre

O [[2026-08-03 — Segunda Rodada Metas 2S — Doug & Gestores|Doug]] fixou na review de
07/08 que cada pessoa contrata **uma entrega necessariamente atrelada a IA**. Se o
trabalho de IA do time é invisível no reconhecimento, tende a ficar invisível na
avaliação — a pessoa entrega, ninguém vê, e a nota não reflete.

**Duas ações:**

- [ ] No desdobramento das metas da super semana, garantir que a entrega de IA de cada pessoa nasça com forma de ser mostrada — algo nomeável, como o hub do Andrey e o dashboard da Pietra viraram
- [ ] Ao dar kudos ao time, usar as categorias de **IA** e **problema histórico**, não a de cliente. A de cliente já tem 28; as outras duas é que amarram nos direcionadores e estão vazias

## O benchmark da empresa — review de 14/08/2026

A Desiree apresentou os números do ciclo de julho na review: **452 kudos
enviados, 71% de adesão**. A distribuição da Swap inteira:

| Categoria | Empresa | Seu time |
|---|---|---|
| Impacto positivo nos clientes | 67% | **82%** |
| Problema histórico da SUAP | 25% | 15% |
| Processo inteligente com IA | 8% | **3%** |

Isso muda o enquadramento da leitura acima. **O gap de IA é real, mas a empresa
toda está baixa nessa categoria** — 8% não é um patamar de referência. E o time
está **quinze pontos acima da média** em impacto no cliente.

Ao levar isso para o time ou para cima, a frase honesta é *"somos referência em
cliente e ainda não contamos a história de IA"* — não *"estamos atrás"*. A
segunda versão é injusta com o time e falsa contra o dado.

# Reconhecimento externo ao time — Niky

## Review de 14/08/2026 — o depoimento do Thales

O **Thales Machado ficou em primeiro lugar no ranking de kudos de julho** da
empresa. O
Vinicius o chamou ao palco para o depoimento de reconhecido, e ele **usou o
tempo dele para falar do White Label**.

Sobre o tombamento da Niky:

> *"No tombamento da Niky que nós fizemos agora, eu tinha pouca interface com o
> pessoal de White Label. A gente conversava muito bem pontualmente e, cara,
> **agora eu levo muito eles para a vida**. Eles me ajudaram muito, a gente se
> ajudou também. A gente tinha fluxos ali que a gente não entendia por que
> fazia, e ao mesmo tempo conseguiu construir uma relação muito boa e ver a
> efetividade do processo."*

E o que o cliente disse, na visita presencial à Niky em **13/08**:

> *"Ontem a gente visitou a Niky e, apesar do primeiro dia de atendimento ter
> sido um pouco mais caótico, ontem eles trouxeram: **'a gente não podia ter
> escolhido um parceiro melhor do que vocês'**. Toda a disponibilidade, tanto do
> time, tanto do Luan quanto da **Luma**, que fizeram várias tarefas para
> conseguir não só ajudar a gente, mas também todos os outros clientes que
> estavam ali. Então é uma gratidão."*

**Por que isso vale registrar:**

- **O elogio é do cliente, não interno.** A Niky disse isso presencialmente,
  depois de um começo que o próprio Thales chamou de caótico. É a virada de
  percepção acontecendo na frente do cliente.
- **A Luma Gomes Leonardo foi citada pelo nome**, no palco, por alguém de
  fora do time — a mesma pessoa que achou a causa raiz do desbloqueio de cartão
  no [[2026-08-05 — War Room Niky|war room de 05/08]].
- **O reconhecimento veio de quem mais foi reconhecido na empresa.** O Thales
  tinha o palco e podia falar de qualquer coisa. Falou do seu time.

*Ruído da transcrição: as anotações do Gemini atribuem a fala ao Vinicius
Aranha, mas é o Thales — o Vinicius o chama e a fala emenda sem troca de rótulo.
"Nick"/"Nik" é a **Niky**; "White Lig" é **White Label**; "cudo" é **kudos**.*
