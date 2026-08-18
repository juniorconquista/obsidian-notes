---
data: 2026-08-13
hora: "10:31"
reuniao: "Estrutura de contas RTF e CCLG — Léo e Santi"
tags: [reuniao]
participantes: [Junior Oliveira, Leonardo Herbert Gonçalves, Gabriel Santi]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "qds-agdu-drd (2026-08-13 10_31 GMT-3) - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1XnRcheHtISllWg1Psx7b6XGLK3t-R2DuLFNIMxIy5uo"
---

# Estrutura de contas RTF e CCLG — Léo e Santi | 13/08/2026

## Contexto

**18min44s.** Conversa de preparação para a call de roadmap com o **Ury**, no fim do
dia. A pergunta que o Léo queria resolver antes: **se for para refundar o White
Label do zero, a gente escolhe RTF ou CCLG?**

Nasce de duas coisas da véspera: o compromisso do Sol com o Wagner de entregar a
versão nova até dezembro, em
[[2026-08-12 — Conversa com Wagner — Bee Benefícios|Conversa com Wagner — Bee Benefícios — 12-08-2026]], e o alerta do
[[Stive Tormes]] de que o WL 2.0 é concebido em RTF enquanto a FACISC opera em
CCLG.

> ⚠️ **Atribuição da transcrição.** Você e o [[Gabriel Santi]] estavam na mesma sala
> em São Paulo, no mesmo microfone — você abre a call avisando *"o Santi tá meio
> longe, você não vai ver todo mundo não"*. **A transcrição atribui a você toda a
> fala do Santi.** Boa parte do detalhe técnico abaixo é dele, não sua.

## Decisões tomadas

**Não escolher. Construir suportando as duas estruturas.**

O Léo colocou a pergunta em cima da mesa — *"se o cara chegar e falar 'a gente vai
fazer CCLG ou RTF?', a gente devia falar que não importa"* — e a resposta da sala
foi **"fazemos dois"**.

**O que sustenta:** a diferença é de cerca de **10% do sistema**. O Léo começou
estimando 80% agnóstico e refinou: *"nem a última camada — é uma camada específica;
para mim é 10% do que afeta a diferença"*.

**Por que é pouco.** O usuário final não percebe diferença: portal administrativo,
portal RH e app consomem saldo do mesmo jeito, e o saldo aparece igual na tela.
Operação de cartão — bloqueio, desbloqueio, troca de senha — é idêntica nos dois.

**O que de fato muda:**

| | CCLG | RTF |
|---|---|---|
| Natureza do saldo | dinheiro real na bag | limite, uma promessa de dinheiro na PMA |
| Onde consultar | ledger de banking | **ledger de limites** — a terceira, construída pelo time |
| Extrato | — | há `transaction type` de RTF que não deve aparecer em CCLG |
| Transação de cartão | dinheiro já está na bag | cai da PMA para a bag no momento do swipe |
| Distribuição | empresa faz funding com dinheiro | cliente distribui limite, com mínimo mas sem teto |

A autorização compartilhada também muda no RTF, mas **o White Label não controla
isso**.

**O argumento que decidiu, e é comercial, não técnico.** A objeção era que o RTF é
mais flexível e comportaria o CCLG dentro — então bastaria terminar o RTF e adaptar
depois. O Léo desmontou:

> *"Se a gente criar do zero e ele suporta as duas estruturas, não importa. **Eu
> posso tombar o cara e continuar na estrutura CCLG para ele, só por causa do
> tombamento.** Eu chego nele e falo: tenho uma solução para você tombar no White
> Label, você não precisa mudar nada pro seu cliente. Seu cliente vai nem sentir."*

**Suportar os dois elimina a barreira de migração.** Escolher um obriga todo cliente
do outro modelo a trocar de estrutura de conta antes de tombar.

E você fechou com o argumento que não tem contorno: **"tem cliente que não pode usar
RTF"**, por questão legal. Escolher RTF exclui esses clientes de forma permanente.

## Próximos passos

- [ ] Levar a posição de "suportar os dois" para a call de roadmap com o Ury — Junior — hoje, fim do dia
- [ ] Confirmar com banking e cartões se estão maduros nas duas estruturas — sem dono definido
- [ ] Validar a transação de cartão no RTF: o swipe precisa debitar do balance correto — Gabriel Santi, com banking — em teste
- [ ] Levar a decisão para o desenho arquitetural do WL 2.0, com a [[Priscila Campos]] desde a primeira agenda — Junior

## Como você foi

A atribuição misturada limita a análise, mas o que é claramente seu:

**Você montou a call certa antes da conversa que importa.** Levar o Santi e provocar
a discussão de estrutura de contas **antes** da call com o Ury é preparação, não
reação. O Léo inclusive disse o motivo: *"vamos preparar para escutar o que o cara
vai trazer"*.

**E você mudou de posição quando o argumento era melhor.** Sua proposta inicial era
terminar o RTF e adaptar o CCLG depois. Quando o Léo mostrou que isso empurra a
migração para o cliente, você reconheceu na hora — *"ah, tá, entendi"* — e a posição
final ficou melhor que a inicial. É o mesmo movimento da conversa com a
[[Priscila Campos]] em 04/08, quando você abandonou a ideia de parar o time.

**O melhor aporte foi o do cliente que não pode usar RTF.** É o único argumento da
conversa que não tem contorno técnico, e é seu.

## Pontos de atenção

- **Isto é o que torna o compromisso de dezembro cumprível.** O [[Stive Tormes]]
  alertou em 12/08 que o 2.0 não atenderia o Wagner por ser RTF. Suportar as duas
  estruturas resolve — e sem isso a promessa que o Sol fez ao cliente não fecha.
  **Vale dizer isso com essas palavras na call com o Ury:** não é preferência
  arquitetural, é a condição para tombar o maior cliente do White Label.

- **A pergunta certa não é do White Label.** A frase do Léo, pronta para usar:
  *"a pergunta é pro time de banking e cartões, se estão 100% confortáveis com RTF e
  CCLG"*. Do lado do WL as duas cabem; quem precisa confirmar maturidade é quem
  fornece a estrutura de contas. **E esse follow-up ficou sem dono.**

- **Um item técnico segue aberto no RTF.** Distribuição de limite funciona, criar e
  remover balance funciona, estrutura de conta está OK. Falta validar que a
  **transação de cartão debita do balance correto**. É o único item pendente e vale
  apresentar como tal, não como risco de fundação.

- **A ledger de limites é construção do time.** Havia a ledger da processadora e a de
  banking; o time subiu uma terceira, duplicando a de banking e retirando o que não
  usaria, para aproveitar a autorização compartilhada. É ativo próprio e vale
  registrar como tal na refundação — o Léo já apontou: *"se a gente fosse construir
  do zero, a gente devia reutilizar"*.

- **Ruído de transcrição:** "SSLG", "SLG", "CSLG" e "CSRG" são todos **CCLG**; "BGS"
  e "BG" são as **bags**; "led"/"leder"/"LED" é **ledger**; "PML" é **PMA**;
  "funzin"/"fundin" é **funding**; "Juninho"/"Jurinho" é você; "Sant" é o
  [[Gabriel Santi]]; "Steve"/"Chive" é o [[Stive Tormes]].
