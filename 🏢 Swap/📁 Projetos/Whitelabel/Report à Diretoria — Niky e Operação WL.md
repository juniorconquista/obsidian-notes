---
tipo: iniciativa
projeto: "Whitelabel"
tags: [comunicacao, diretoria]
iniciado: 2026-08-04
cadencia: "1º agora, 2º no fim da semana, depois quinzenal"
destinatarios: [Alexandre Winandy, Douglas Storf, Ury Rappaport]
status: ativo
---

# Report à Diretoria — Niky e Operação WL

## Por que existe

Criado em 04/08/2026, decidido em [[2026-08-04 — Alinhamento — Comunicação|Alinhamento — Comunicação — 04-08-2026]]. O
push é do Rodrigo Sol, e a frase dele é a razão de ser:

> *"Vocês têm que assumir o controle da comunicação porque as pessoas vão usar
> essas informações de acordo com o interesse próprio delas."*

O gatilho foi o tombamento da Niky, mas a causa é anterior. Na review em que os
números do White Label criaram clima ruim, a cobrança chegou à
[[Carol — Líder CS]] *"meio top down"* e ela ficou chateada de ter que levar
aquela informação. Sua leitura na call: *"tem muito a ver com a forma como a gente
não entrega comunicação"*. A thread existe para que a diretoria receba o número
pela sua mão, e não pela de terceiros.

## Combinado

- **Para:** Alê, Doug e Ury. **cc:** time de CSO.
- **Cadência:** o primeiro imediatamente, o segundo no fim da semana, depois
  quinzenal, alinhada ao ciclo da sprint. *Nota: o Sol propôs o segundo em 12
  horas e você converteu em fim de semana — o plano nasceu da premissa de que
  esperar o outro pedir é o que criou o problema, então afrouxar a cadência
  enfraquece o mecanismo.*
- **Estrutura:** resumo consolidado **no corpo**, documento detalhado **em anexo**,
  cobrindo julho e agosto.
- **Conteúdo desenhado pela [[Daniela Melo]]:** retrato do dia, plano de ação para
  os gargalos, o que foi feito nos últimos 15 dias, volume de cards no backlog por
  cliente, SLA e pontos de atenção.
- **O Sol revisa antes do envio.**
- Entregas a destacar na série: tombamento da Niky, migrações de KYC, CNPJ
  alfanumérico e o WL 2.0.

## Regras de escrita — o que aprendemos na marra

O primeiro rascunho foi reprovado duas vezes pelo Sol. As três frases dele valem
mais que qualquer checklist:

> *"Tá tão bom que está ruim."*
> *"O cara vai parar de ler no segundo parágrafo."*
> *"Não é para contar um drama. É um relatório executivo."*

E a orientação de processo:

> *"Depois que você fizer manualmente pode usar a IA pra corrigir um
> texto/gramática. Para esse público alvo, eles sacam na hora se foi IA que
> escreveu e desengaja."*

O que sai disso, em regra:

1. **Fato seco embaixo de rótulo, não narrativa.** Contexto, Fatos, O que já
   fizemos, Próximos passos — o esqueleto que o Sol mandou.
2. **Um cliente por report.** *"Não mistura FACISC com Niky. Não vale a pena
   colocar no mesmo balaio."*
3. **Escrever à mão primeiro.** A IA entra na gramática, não na composição. Texto
   que se esforça para prender atenção é o que soa fabricado para esse público.
4. **Abrir pelo número que enquadra**, não pela cena. O crescimento de **mais de
   50% de TPV sem headcount** é o argumento mais forte que existe — ele transforma
   "estamos lentos" em "estamos absorvendo metade mais de volume com o mesmo time".
   Foi levantado pela [[Pietra Oliveira]].
5. **Separar a fila do cliente da nossa.** Sem isso, "400 tickets" é lido como
   fila da Swap.
6. **Evitar sinais de texto gerado:** títulos numerados em caixa alta, emoji,
   bullet com rótulo em negrito, três substantivos abstratos em fila, antítese
   repetida ("não é X, é Y"), e frases que anunciam o que vão fazer ("resumindo
   antes de detalhar").

## O que foi enviado em 04/08

Assunto: **Status Update: Tombamento Niky e Operação White Label**. Enviado à
noite, depois de três versões — a final escrita com o Léo.

**O enquadramento que a versão final trouxe e as anteriores não tinham:** o volume
de incidentes deste primeiro momento **já era esperado** pela forma como o processo
de migração foi estruturado, e a operação está sob controle.

**A distinção de fila, que era o ponto:**

- ~**400 tickets** estão represados no atendimento da própria Niky, com os
  usuários finais dela. Não são chamados abertos com a Swap.
- **35 chamados** foram escalados à Swap, sendo **12 do WL** e **6 em aberto** —
  5 deles do mesmo tema, desbloqueio de cartão.

**Painel de incidentes enviado:** recarga Qualicorp, falha de primeiro acesso,
Firebase do app, lentidão do portal e bags duplicadas como resolvidos; multiorg em
andamento; migração de saldo em lote priorizada na Sprint 15.

**Mecanismo, em vez de promessa:** o foco declarado é estabilizar a base, com war
room aberta com o CSO e checkpoint diário com o cliente. A reunião de lições
aprendidas **foi retirada** do report a pedido seu — o compromisso ficou só em
estabilizar.

**Percepção do cliente**, com o antes e depois: a primeira call foi dura, com o
cliente atritado e olhando para o volume da ponta; na agenda seguinte o tom mudou
e a Niky demonstrou satisfação com o empenho e a prontidão do time.

## Números usados, e o que conferir antes do próximo

- **R$ 1.684.738,35** de recarga manual da Qualicorp. O
  [[Gabriel Santi]] confirmou este valor. **Quatro notas do vault registram
  R$ 202.543** e estão erradas: [[2026-08-03 — Checkpoint Niky — Operação|Checkpoint Niky — Operação — 03-08-2026]],
  [[2026-08-03 — Tombamento Niky|Tombamento Niky — 03-08-2026]], [[2026-08-03]] e o rascunho antigo. Precisam
  ser corrigidas.
- **R$ 45 mi + R$ 25 mi de TPV.** Falta registrar **o período** — mensal,
  acumulado ou desde o início. Para diretoria isso muda a leitura.
- A Niky tem **R$ 70 milhões de TPV adicional** hoje no concorrente, dito pela
  Gabriela na review. É o argumento mais forte da série e ainda não foi usado:
  transforma o tombamento de "migração que deu trabalho" em "porta de entrada de
  mais R$ 70 mi".
- **Fonte da fila:** a planilha compartilhada com a Niky,
  `Cópia de Niky - Tickets agosto.xlsx`, abas `Escalados` e `Resolvidos Julho`. A
  aba de julho traz **43 chamados resolvidos**, número diferente dos 31 do painel
  antigo — usar a planilha, que é a que o cliente também vê.
- **Cartão é o tema recorrente:** 16 dos 43 resolvidos em julho eram de Cards, e
  5 dos 6 abertos hoje são desbloqueio de cartão. Não é problema novo do
  tombamento; a virada amplificou.

## Próximos passos

- [ ] Enviar o segundo report, com os indicadores atualizados — Junior — prometido para 05/08
- [ ] Corrigir o valor da recarga nas quatro notas do vault — Junior — sem prazo
- [ ] Confirmar o período do TPV de R$ 45 mi e R$ 25 mi — Junior — sem prazo
- [ ] Montar o documento detalhado do anexo, cobrindo julho e agosto — Junior e Dani — sem prazo
- [ ] Decidir o que dizer à diretoria no intervalo entre o report e o resultado de qualidade, que a Priscila estima em 2 a 3 meses — Junior — sem prazo
