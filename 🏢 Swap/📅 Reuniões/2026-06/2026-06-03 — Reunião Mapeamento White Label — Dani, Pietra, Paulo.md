# Reunião Mapeamento White Label — Dani, Pietra, Paulo — 03/06/2026

**Participantes:** Junior Oliveira, Pietra Oliveira, Paulo Pereira, Daniela Melo (PMO - Raro)
**Objetivo:** Apresentar o White Label para Dani e mapear dores para plano de ação

---

## Contexto

Daniela Melo entrou na Raro dia 21/05 e foi alocada pelo Sol para apoiar Junior, Pietra e Paulo na organização do time de White Label. Essa foi a primeira reunião de mapeamento.

---

## O que é o White Label — resumo da Pietra

- SUAP é uma infraestrutura de meios de pagamento (BaaS)
- Parceiros podem conectar às APIs e desenvolver o próprio front, ou contratar o White Label
- Dois casos de uso principais: **benefícios flexíveis** e **despesas corporativas**
- Três aplicações: portal legado de benefícios, portal de despesas (novo) e **White Label 2.0** (em construção)
- **16 clientes** ativos
- **Facisc** representa mais de **90% da receita** do White Label (~R$80k/mês)
- Time é cliente interno da SUAP — qualquer mudança de endpoint impacta o White Label

---

## Principais Dores Mapeadas

### 1. Helper — o maior buraco

- Dois analistas júniors (Renan e Andrey) dedicados ao helper, sem senioridade para resolver tudo
- Devs seniores são acionados diretamente — no privado, sem registro em lugar nenhum
- CS marca o time inteiro no Slack (@whitelabelteam) — quem grita mais alto leva
- Pietra mal olha para o board de helper no dia a dia
- Trabalho invisível que não entra na sprint, não é metrificado e não aparece na review
- 32 cards em backlog sem tratamento + 9 em refinamento
- SLA médio de resposta: **3,8 dias** (extraído via API do Shortcut + Claude por Pietra)
- Pietra já criou dashboard no Claude com dados do helper — quer aprimorar

### 2. Ritos e Planning — formato herdado e ruim

- Pietra cria os épicos, devs criam as histórias (tarefas)
- Não há votação de esforço, não há refinamento técnico antes da planning
- Prazos colocados pelos próprios devs sem validação
- Junior trouxe o exemplo: dev pediu 6 dias para task simples, reduziu para 30 minutos quando questionado

### 3. Métricas e Visibilidade

- Time entregou mais de 200 cards em maio — nada aparece na review da SUAP
- Capacity do time aparece em 40% enquanto outras tribos chegam a 100%+
- Dani vai conectar Pietra com Mel (time de dados) para construir painéis gerenciais — reunião marcada para sexta

---

## Plano de Ação Combinado

### Sexta-feira (05/06) — redesenhar a Planning da Sprint 10
Junior, Pietra e Dani se reúnem antes da Sprint 10 começar na segunda (08/06).

**Proposta da Dani:**
- Pietra cria as histórias (não só épicos) — quebrando em entregáveis de valor menores
- Time vota esforço na planning usando **P/M/G**
- Dev cria tarefas com acompanhamento do líder técnico
- Junior acompanha via Shortcut — sem planilha

### Próximas semanas — Helper
- Pietra como ponto único de entrada — CS não aciona dev diretamente
- SLA definido por tipo de urgência
- Todo card registrado no Shortcut obrigatoriamente

### BI e Métricas
- Dani conecta Pietra com Mel para construir painéis gerenciais oficiais

---

## Próximos Passos

- [ ] Dani — Marcar reunião sexta (05/06) com Junior e Pietra para redesenhar a planning
- [ ] Dani — Incluir Pietra na reunião com Mel (dados) na sexta
- [ ] Dani — Marcar reunião específica sobre o fluxo do helper
- [ ] Pietra — Compartilhar links do Notion e apresentações com Dani
- [ ] Junior + Paulo — Coletar horas de KYC e RTF para registro da Lei do Bem
