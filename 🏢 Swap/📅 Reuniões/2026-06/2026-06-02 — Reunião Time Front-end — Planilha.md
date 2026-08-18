# Reunião Time Front-end — Planilha & Bloqueios — 02/06/2026

**Participantes:** Junior Oliveira, Felipe Leal, Pedro Costa, Julio Santos Bissoli, Paulo Pereira
**Objetivo:** Visibilidade de atividades, status da sprint e identificação de bloqueios

---

## Contexto

Junior entrou no final da reunião — parte inicial foi conversa informal entre o time antes da chegada dele. Paulo também estava presente.

---

## Status de cada pessoa

| Pessoa | Atividade | % | Bloqueio | Previsão |
|--------|-----------|---|---------|---------|
| Felipe Leal | Distribuição de limites | 44% | 🔴 Ledger — aguardando 2 endpoints do back | Indefinida |
| Felipe Leal | Atualização identidade visual Facisc (portal legado) | Em andamento | Acesso AWS pendente | — |
| Julio Santos Bissoli | KYC — novo modelo (BACEN) | ~90% | Ajustes back e front | Amanhã 03/06 (~6h) |
| Julio Santos Bissoli | Billing/taxas de faturamento | Parado | Falta endpoints back + refinamento design | — |
| Pedro Costa | Config. produto para despesas | Em andamento | Aguardando endpoints back | — |
| Pedro Costa | Seleção de produto na criação de usuário | Desenvolvido local | Aguardando publicação do back para validação | ~4h |
| Pedro Costa | Card Helper (consulta de cliente) | Diagnosticado | Aguardando decisão de produto/suporte | — |

---

## Bloqueio Crítico — Ledger

🔴 O principal bloqueio do time de front e mobile é o **Ledger**.

Funcionalidades impactadas:
- Distribuição de limites
- Transferências entre carteiras
- Extratos
- Retirada de limites na BG (passar o cartão)

Felipe está com a tarefa de distribuição de limites há **dois meses** — sem resolução do Ledger qualquer estimativa de prazo é especulação.

---

## Saída do Julio

- Último dia: **10/06/2026** (quarta-feira)
- Motivo: proposta com salário maior — construção em andamento, precisa da grana
- Tarefas menores que sobrarem vão ficar como inventário para o próximo
- ⚠️ Risco: perda de conhecimento técnico — Julio tem muito contexto do projeto
- Felipe sugeriu: alocar Julio para **documentar e concluir tarefas específicas** antes de sair

---

## Principais Discussões

### Felipe — frustração acumulada
Felipe expressou frustração desde janeiro com falta de progresso em entregas críticas e repetição dos mesmos problemas em reuniões. Sugeriu foco concentrado para resolver o Ledger de uma vez — reunir as pessoas certas e destravar.

### Backend — necessidade de senioridade
Felipe e Paulo alinhados: o problema central é o backend. Front está sob controle. Falta senioridade no back para tracionar resultados. Felipe criticou o processo de contratação — a substituição de Conrado pelo Lucas não atingiu as expectativas de senioridade e rampagem.

Felipe defendeu contratação de **freelancers especializados por demanda** — mais eficiente do que contratar e rampar alguém novo no contexto atual.

### Pedro Costa — ativo valioso
Felipe pediu a Paulo que garantisse **mentoria de qualidade para Pedro** — o vê como ativo estratégico do time que precisa ser bem orientado.

### Processo e Shortcut
Junior apresentou a nova dinâmica de visibilidade via Shortcut/planilha. Time aderiu — próximos passos registrados.

### Benefícios — arquitetura legada
Atualização visual (CSS/HTML) pode atender cliente no curto prazo, mas a arquitetura atual (hexagonal) precisaria de reestruturação para escalabilidade a longo prazo.

---

## Próximos Passos

- [ ] Junior — Resolver bloqueio do Ledger com Paulo para destravar front e mobile
- [ ] Junior — 1:1 com Felipe Leal amanhã às 9:15
- [ ] Felipe — Criar card Facisc no Shortcut
- [ ] Felipe, Pedro, Julio — Listar todas as funcionalidades bloqueadas pelo Ledger para Paulo comunicar impacto ao cliente
- [ ] Pedro, Julio — Mapear endpoints necessários e compartilhar lista para cobrar do back
- [ ] Pedro — Atualizar status do card de helper na planilha
- [ ] Paulo — Remarcar reunião de alinhamento com Junior após almoço
- [ ] Paulo — Garantir mentoria para Pedro Costa
- [ ] Time — Preencher planilha ao final de cada dia
- [ ] Junior — Avaliar contratação de freelancers para fortalecer backend
