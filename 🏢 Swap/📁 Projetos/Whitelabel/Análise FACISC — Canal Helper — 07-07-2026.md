# Canal Helper — Análise FACISC
**Data:** 07/07/2026
**Contexto:** [[🗂️ Iniciativas de Gestão]] — Action Item #4 (Alinhamento com o Time de Helper)
**Gatilho:** Rodrigo Sol trouxe atrito de cliente FACISC por demora de resposta em tickets, antes de reunião de diretoria
**Fonte:** Export Shortcut (219 tickets, todos os clientes)

---

## Resumo Executivo

- **FACISC responde melhor que a média do canal**: SLA de 1ª resposta de 1,9 dias (mediana) contra 2,0 dias do canal geral. *Nota de metodologia: usamos mediana porque é a mesma estatística que o time já reporta no PDF semanal — a média aritmética distorce muito por causa de outliers (ver Seção 1).*
- **FACISC concentra 46% dos tickets abertos**, mas isso é proporcional ao seu peso no canal — ela representa 39,7% do volume total de demandas.
- **O gargalo real está em To Refine e Developing** (não em Backlog nem no atendimento inicial) — tickets antigos de até 84 dias estão parados nessas duas fases, tanto para FACISC quanto para o canal como um todo.
- **A causa "falta de treinamento do CS" é menos concentrada na FACISC** do que nos demais clientes (19% dos tickets evitáveis contra 39,7% de participação no volume) — o treinamento que começa semana que vem beneficia o canal inteiro, não é um remendo pontual para este cliente.
- **Duas frentes ficam pendentes**: estimativa de esforço das correções estruturais e simulação de capacity para zerar a fila.

> Contexto de gestão: o gargalo de tickets chegando ao Helper que deveriam ser resolvidos pelo CS já estava mapeado desde 27/05, no Action Item #4 das [[🗂️ Iniciativas de Gestão]]. O que está acontecendo agora é a execução desse plano, não uma resposta reativa a uma crise nova.

## 1. Página atual — ajustes solicitados pelo Sol

### Header — SLA da FACISC

| Métrica | Global | FACISC |
|---|---|---|
| **SLA de 1ª resposta — mediana** (o que o time já reporta hoje) | **2,0 dias** | **1,9 dias** |
| SLA de 1ª resposta — média aritmética (referência complementar) | 5,9 dias | 5,1 dias |

> ⚠️ **Correção de metodologia:** o "SLA médio" que o time reporta no PDF semanal/Looker é, na prática, a **mediana**, não a média aritmética. A média fica bem mais alta (quase 3x) porque 16% dos tickets (22 de 141 com resposta registrada) levam mais de 10 dias — alguns até 70 dias — puxando o número para cima. Usamos mediana no header para manter consistência com o que a diretoria já está acostumada a ver.
>
> FACISC responde **melhor ou igual** ao canal em ambas as estatísticas.

### Lead time médio por etapa — Global x FACISC (dias, tickets em aberto)
| Etapa | Global (média/mediana) | FACISC (média/mediana) |
|---|---|---|
| Backlog | 11,6 / 7,0 | 12,8 / 12,0 |
| To Refine | 30,9 / 31,9 | 39,4 / 33,6 |
| Developing | 39,9 / 42,1 | 38,4 / 31,9 |
| Validating | 11,2 / 6,4 | 15,6 / 7,4 |

> FACISC é um pouco mais lenta em Backlog e To Refine; empata em Developing e Validating.

### Sugestões de melhoria — impacto das causas raiz técnicas
| Iniciativa | Demandas impactadas (total) | Das quais FACISC | Estimativa de esforço |
|---|---|---|---|
| Migração de saldo em lote | 36 | 17 (47%) | **Não disponível** — não estimado no board ainda |
| Atualização de status KYC (Despesas) | 4 | 0 | **Não disponível** — não estimado no board ainda |

> ⚠️ Pendência: pedir estimativa de esforço ao time técnico.
> Nota: estas são correções de produto/engenharia. A causa organizacional (falta de autonomia do CS) é tratada separadamente na Seção 3.

---

## 2. Página nova — recorte FACISC

### Tickets abertos por fase, com tempo médio de espera
| Fase | Qtd | Média dias aberto | Mediana | Máx |
|---|---|---|---|---|
| Backlog | 31 | 12,8 | 12,0 | 28,0 |
| To Refine | 6 | 39,4 | 33,6 | 83,8 |
| Developing | 8 | 38,4 | 31,9 | 67,8 |
| Validating | 8 | 15,6 | 7,4 | 39,7 |
| **Total aberto FACISC** | **53** | — | — | — |

### SLA FACISC — percentis
| | P95 | P99 |
|---|---|---|
| 1ª resposta (created → started) | 14,6 dias | 59,5 dias |
| Resolução completa (created → completed) | 29,2 dias | 57,3 dias |

---

## 3. Causa raiz organizacional — "tickets evitáveis com treinamento do CS"

> Proxy usado: campo "Tipo de Helper" com categorias de dúvida/falta de autonomia do CS (Dúvida/Consulta, Falta de entendimento sobre o produto, Sem necessidade de escalar, Problemas de acessos, Criação de user admin), últimos 60 dias.

| Categoria | Outros clientes | FACISC | Total |
|---|---|---|---|
| Criação de user admin | 4 | 0 | 4 |
| Dúvida/Consulta | 4 | 1 | 5 |
| Falta de entendimento sobre o produto | 3 | 0 | 3 |
| Problemas de acessos | 3 | 2 | 5 |
| Sem necessidade de escalar | 3 | 1 | 4 |
| **Total** | **17** | **4** | **21** |

> FACISC é **19%** desses 21 tickets, mas representa **39,7%** do volume total — proporcionalmente, a FACISC gera **menos** ticket evitável que o esperado pelo seu tamanho. O problema de treinamento do CS é mais distribuído entre os outros clientes.

**Ação já em curso:** o treinamento do time de CS para reduzir esse volume de tickets evitáveis começa na semana de 13/07. O objetivo é que o CS passe a resolver diretamente cards de dúvida/acesso/cadastro sem escalar ao Helper — o que libera capacidade do time para focar nos gargalos reais (To Refine e Developing). Como o problema é mais distribuído entre os outros clientes do que concentrado na FACISC, o ganho desse treinamento beneficia o canal inteiro, não é uma resposta pontual a este caso.

---

## 4. Lista analítica — 53 tickets abertos da FACISC (ordenados por tempo aberto)

| ID | Ticket | Fase | Data de entrada | Dias aberto |
|---|---|---|---|---|
| 257627 | Visualização de compra (#207870) | To Refine | 14/04/2026 14:17 | 83,8 |
| 260491 | Visualização de cartão — atualização tela Portal Despesas (#209724) | To Refine | 28/04/2026 06:48 | 70,1 |
| 261359 | Erro na migração de usuários em benefícios por CPF já cadastrado (#206327) | Developing | 30/04/2026 14:43 | 67,8 |
| 266619 | Falha na visualização da tela com diferentes níveis de acesso — Bee Despesas (#212014) | Developing | 07/05/2026 11:50 | 60,9 |
| 269153 | Atualização de banners e relatório de clicks — App Bee Benefícios (#212135) | Developing | 08/05/2026 12:00 | 59,9 |
| 282351 | Expiração de link de boas vindas portal — Benefícios e Despesas (#214736) | To Refine | 26/05/2026 07:23 | 42,1 |
| 285480 | Migração de usuário (#216186) | Validating | 28/05/2026 16:03 | 39,8 |
| 318242 | Chave PIX — Módulo de benefícios (#216804) | Developing | 01/06/2026 15:14 | 35,8 |
| 331320 | Erro na retirada de saldo de carteiras voucher (#217085) | Validating | 03/06/2026 14:18 | 33,8 |
| 338680 | Transferência de saldo do Voucher Alimentação/Refeição (#218081) | Developing | 09/06/2026 10:40 | 28,0 |
| 338668 | Pedidos transferidos parcialmente (#217777) | Backlog | 09/06/2026 10:22 | 28,0 |
| 339668 | Despesa sem opção de avaliação (#218789) | Backlog | 11/06/2026 16:23 | 25,7 |
| 339690 | Não consegue pagar boleto — status desconhecido (#218511) | Developing | 11/06/2026 16:56 | 25,7 |
| 339783 | Artes atualizadas — App Bee Benefícios (#217226) | To Refine | 12/06/2026 08:53 | 25,1 |
| 339812 | Falha no recebimento do OTP via SMS — Despesas (#218952) | Validating | 12/06/2026 11:03 | 25,0 |
| 340939 | Surgimento de modalidade sem a empresa solicitar (#219826) | Backlog | 18/06/2026 07:35 | 19,1 |
| 340950 | Aprovação de usuário (#220108) | Backlog | 18/06/2026 08:05 | 19,1 |
| 341508 | Pedido pago não creditado — 128238 (#218437) | Backlog | 19/06/2026 12:43 | 17,9 |
| 341501 | Problema de Boleto Registrado com valor X | Developing | 19/06/2026 12:34 | 17,9 |
| 341573 | Erro ao transferir usuário (#220497) | Backlog | 19/06/2026 15:55 | 17,8 |
| 341947 | Ativar trilha voucher de cartões combo Bee (#220798) | Backlog | 22/06/2026 13:59 | 14,8 |
| 342154 | Usuário já cadastrado em benefícios — módulo despesas (#220975) | Backlog | 23/06/2026 08:53 | 14,1 |
| 342133 | Recusa de fraude — Jales Abrão Junior (#220814) | Backlog | 23/06/2026 07:57 | 14,1 |
| 342378 | Retirar notificação de Modo Suporte (#221133) | Backlog | 24/06/2026 07:17 | 13,1 |
| 342382 | Primeiro acesso ao app (#221247) | Backlog | 24/06/2026 07:26 | 13,1 |
| 343355 | Erro geração de pedido — Portal Despesas (#221501) | Backlog | 24/06/2026 12:25 | 12,9 |
| 343484 | Sankhya Benefícios — Desbloqueio de cartão (#219882) | Backlog | 24/06/2026 14:43 | 12,8 |
| 343413 | Instabilidade no painel (#221549) | Backlog | 24/06/2026 14:04 | 12,8 |
| 343689 | Instabilidade na geração de pedidos via boleto — Benefícios (#221771) | Backlog | 25/06/2026 11:22 | 12,0 |
| 343662 | Pedido PIX pago e não liberado — 1272 despesas (#221786) | Backlog | 25/06/2026 10:07 | 12,0 |
| 343663 | Liberação de pedido (#221785) | Backlog | 25/06/2026 10:10 | 12,0 |
| 343654 | Pedido pago e não liberado — 120583 (#221678) | Backlog | 25/06/2026 09:28 | 12,0 |
| 343687 | Pedido com status aguardando pagamento — FC Pisos (#221709) | Backlog | 25/06/2026 11:11 | 12,0 |
| 343671 | Transferência não efetivada — Empresa Rodolenz, URGENTE (#221702) | Backlog | 25/06/2026 10:29 | 12,0 |
| 343666 | Pedido não liberado na TA (#221761) | Backlog | 25/06/2026 10:17 | 12,0 |
| 343705 | Artes atualizadas — App Bee Benefícios (#217226) | Backlog | 25/06/2026 12:04 | 11,9 |
| 343874 | Liberação de pedido (#221937) | Backlog | 26/06/2026 07:57 | 11,1 |
| 343876 | Opção de transferência manual de pedidos — benefícios (#221947) | To Refine | 26/06/2026 08:04 | 11,1 |
| 343947 | Erro no app — não conseguimos carregar suas informações (#222100) | Developing | 26/06/2026 11:53 | 10,9 |
| 344022 | Mais de um cartão vinculado ao mesmo CPF — despesas (#222217) | Backlog | 26/06/2026 16:41 | 10,7 |
| 344020 | Erro no cadastro — ACIB (#222215) | Backlog | 26/06/2026 16:34 | 10,7 |
| 344025 | Estorno de pagamento (#222220) | Validating | 26/06/2026 16:50 | 10,7 |
| 344198 | Push notifications — App de benefícios (#222532) | Backlog | 29/06/2026 11:26 | 8,0 |
| 344601 | Compra negada (#222662) | Backlog | 01/07/2026 08:53 | 6,1 |
| 344820 | Migração de saldo (#222996) | Backlog | 01/07/2026 12:52 | 5,9 |
| 345139 | Estornar valor — Leonardo Mangilli Pereira (#223144) | Backlog | 02/07/2026 11:59 | 4,9 |
| 345452 | Cancelamento do cartão Bee Despesas Corporativas (#223301) | Backlog | 03/07/2026 09:28 | 4,0 |
| 345476 | URGÊNCIA — Estornar valor — Raiane Taina Xavier Gomes (#222980) | Validating | 03/07/2026 09:40 | 4,0 |
| 345481 | Logins admin de benefícios (#223564) | Backlog | 03/07/2026 09:54 | 4,0 |
| 346034 | Liberação de transferência entre carteiras (#223605) | To Refine | 03/07/2026 12:23 | 3,9 |
| 345687 | Verificação urgente — pedido com falha na transferência (#223545) | Validating | 03/07/2026 11:35 | 3,9 |
| 346037 | Estorno de taxas — Willian Cardoso Machado (#223609) | Validating | 03/07/2026 12:28 | 3,9 |
| 346178 | Aumento de limite (#223596) | Validating | 03/07/2026 16:19 | 3,8 |

**Destaques da lista:**
- 5 tickets com mais de 40 dias abertos (todos em To Refine/Developing) — são o alvo prioritário de mitigação
- Concentração forte em Backlog criado entre 24–26/06 (correlaciona com o pico de incidentes daquela semana, já registrado no diário)

---

## 5. Cruzamento completo — cada pedido exato do Sol x resposta

### Pedidos da mensagem de 19:42–19:43 (06/07)

**"SLA médio x SLA fasisc"**
→ Global: **2,0 dias** (mediana) · FACISC: **1,9 dias** (mediana). Metodologia: created_at → started_at (primeira movimentação/resposta), usando mediana — mesma estatística que o "SLA médio" do PDF/Looker do time, que na prática já é mediana e não média aritmética (a média sobe para 5,9/5,1 dias por causa de outliers).

**"Número de tickets em aberto x número de tickets fasisc"**
→ Total aberto (todos os clientes): **115** · FACISC: **53** (46% do total aberto, acima da fatia de volume da FACISC no canal, que é 39,7%).

**"Lista dos tickets abertos da fasisc com data de entrada"**
→ Lista completa dos 53 tickets — ver Seção 4 acima (ID, nome, fase, data de entrada, dias aberto).

**"Número de tickets fechados médio por cliente x número de tickets fechados fasisc nos recortes de 7, 14 e 30 dias"**
→ 7 dias: média 2,0/cliente x **5** FACISC · 14 dias: média 3,0/cliente x **15** FACISC · 30 dias: média 6,4/cliente x **33** FACISC.

**"Para zerar a fila da fasisc quanto tempo e qual o impacto no time"**
→ ⚠️ **Pendente.** Precisa de capacity do time (headcount do Helper + throughput médio de tickets/pessoa/dia).

**"Seria possível adicionar dev. Para aumentar SLA?"**
→ ⚠️ **Pendente.** É decisão de alocação de time, depende do resultado do item anterior.

---

## Pendências
- [ ] Estimativa de esforço dos épicos "Migração de saldo em lote" e "Atualização KYC" — pedir ao time
- [ ] Simulação de "zerar fila FACISC" — precisa de capacity do time (headcount + throughput/dia)
- [ ] Avaliação de adicionar dev — depende do resultado do item acima

---

## Histórico
- **06-07/07/2026** — Sol trouxe o atrito da FACISC antes da reunião de diretoria. Análise levantada em conjunto com Junior a partir do export do Shortcut.
