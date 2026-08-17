# Iniciativa — Mega Refactor Portal Benefícios | William & Lucas — 05/06/2026

**Responsável:** William Magno Roque Sodre
**Origem da ideia:** Lucas (sugeriu o levantamento de custo quando William apresentou o refactor)
**Status:** Em andamento — aguardando métricas de custo para subir a branch

---

## Contexto

William identificou um problema crítico de arquitetura no Portal Benefícios: o sistema busca a collection completa do MongoDB para depois filtrar em memória. Isso gera custos altos de infraestrutura e risco real de inconsistência de dados.

A ideia de levantar os custos antes de subir o refactor partiu do Lucas — para ter um antes/depois e medir o ganho real.

---

## Problema Identificado

**Erro de arquitetura crítico:**
O sistema busca a collection inteira do MongoDB e filtra em memória ao invés de filtrar diretamente na base. Isso causa:
- Custo elevado de infraestrutura AWS
- Erros de out of memory (conhecidos e relevados pelo time)
- Risco de inconsistência de dados em caso de transação cortada no meio

**Próximos pontos que William vai atacar após o refactor:**
- Redis
- Mensageria
- Integridade geral do sistema

---

## Levantamento de Custos — Maio/2026

| Conta | Custo mensal |
|-------|-------------|
| portal-beneficios-production | USD 2.908,35 |
| portal-beneficios-qa | USD 1.417,72 |
| portal-beneficios-staging | USD 1.691,72 |
| **Total** | **USD 6.017,79/mês** |

⚠️ Staging + QA somados chegam quase ao valor de produção — sinal claro de ineficiência.

**Principais ofensores:** Compute, EC2, VPC, CloudWatch, ELB, NAT Gateway, DataTransfer.

**Outros pontos identificados:**
- Volumes EBS sem attach em produção (PVCs legados do MongoDB)
- Divergência entre storage declarado no manifesto do Mongo e storage observado no cluster (staging)
- Uso de LLM para mensagens de exceção nos 3 ambientes (QA, staging e produção) — William vai desligar em QA e staging

---

## Próximos Passos

- [ ] William — Subir branch do mega refactor após coleta das métricas
- [ ] William — Usar Claude para conferência geral do código antes de subir
- [ ] William — Desligar uso de LLM em QA e staging (variável de ambiente já preparada)
- [ ] William — Atacar Redis, mensageria e integridade após refactor principal
- [ ] Junior — Acompanhar evolução e cobrir bloqueios com outras áreas
- [ ] Junior — Quando fechar, sentar William com Dante para apresentar como case 🏆

---

## Por que isso é importante

Além do ganho técnico e financeiro direto para a Swap, essa iniciativa é um **case perfeito para vender o peixe do time**. William e Lucas trabalharam juntos, identificaram um problema crítico e estão resolvendo com método — levantamento de métricas, refactor estruturado, medição de resultado.

Quando fechar, levar para o Dante e mostrar como o time está contribuindo além das entregas de produto.

---

## 🎯 Estratégia de Impacto com a Liderança

Esse refactor tem potencial de ser o case mais concreto que o time já gerou. A lógica é simples: **números antes vs números depois.**

**O que já temos:**
- Custo atual: USD 6.017,79/mês nas 3 contas
- Problema identificado: sistema busca collection completa do MongoDB e filtra em memória
- Iniciativa do próprio time — não foi demanda externa

**O que capturar após o refactor:**
- Novo custo mensal nas 3 contas
- Redução percentual de custo
- Eliminação ou redução dos erros de out of memory
- Redução do DataTransfer e NAT Gateway em QA e staging

**Projeção de economia anual:**
- Se reduzir 30% do custo total → ~USD 21k/ano
- Se reduzir 50% → ~USD 36k/ano

**Como apresentar:**
Problema identificado → custo antes → ação tomada → custo depois → economia mensal e anual. Curto, visual, com números. Levar o William para sentar com o Dante e apresentar pessoalmente — ele merece o reconhecimento.

**Timing:** assim que o refactor subir e os primeiros números aparecerem — agir na hora, não esperar semanas.
