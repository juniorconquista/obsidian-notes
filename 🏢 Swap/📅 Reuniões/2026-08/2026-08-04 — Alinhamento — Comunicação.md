---
data: 2026-08-04
hora: "09:26"
reuniao: "Alinhamento — Comunicação"
tags: [reuniao]
participantes: [Junior Oliveira, Daniela Melo, Pietra Oliveira, Gabriel Santi]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Alinhamento - 2026_08_04 09_26 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1RBV-Lnx5arle2o5Uq9lsxfxiU3aqeLy45zyIhH_i_XI"
---

# Alinhamento — Comunicação | 04/08/2026

## Contexto

Call de 32min16s que **você convocou de manhã**, depois de acordar com mensagens
do Rodrigo Sol e do Léo — sócio da Raro. Com a [[Daniela Melo]], a
[[Pietra Oliveira]] e o [[Gabriel Santi]].

Você falou 149 vezes das 379 falas da call. Foi você que pautou, conduziu e
fechou com ações.

Abriu com uma crise: um ticket urgente da Juliana informando que **colaboradores
estão ameaçando não trabalhar por não terem recebido o benefício**, possivelmente
ligado a vouchers, sinalizado pelo [[Andrey Cunha]]. Ficou encaminhado para a
daily, com o Lucas já tendo identificado algo no vínculo de balance account
(DMAP).

**Sobre a fonte:** é `Anotações do Gemini`, mas o export traz a transcrição
completa.

## Decisões tomadas

**Comunicação com a diretoria — a decisão principal do dia**

- **O time vai assumir o controle da narrativa.** O push é do Sol, e a frase
  dele é o eixo da call: *"vocês têm que assumir o controle da comunicação porque
  as pessoas vão usar essas informações de acordo com o interesse próprio delas"*.
- **Report formal por e-mail para o Alê, o Doug e o Ury**, começando hoje. A
  cadência: uma agora, outra no fim da semana, depois quinzenal — alinhada ao
  ciclo da sprint.
- **O formato ficou desenhado pela Dani:** retrato do dia, plano de ação para os
  gargalos, o que foi feito nos últimos 15 dias, volume de cards no backlog por
  cliente, SLA e pontos de atenção. Você pediu para incluir **detalhe técnico** e
  status de entregas — foi por isso que trouxe o Santi para a call.
- **Estrutura do e-mail:** resumo consolidado no corpo, documento detalhado em
  anexo, cobrindo julho e agosto. Entregas a destacar: tombamento da Niky,
  migrações de KYC, CNPJ alfanumérico e o WL 2.0.
- **O Sol revisa antes do envio.**
- Você conectou isso à review em que os números do White Label criaram clima
  ruim: conversou com a [[Carol — Líder CS]], que disse que a cobrança veio *"meio
  top down"* e que ficou chateada de ter que levar aquela informação. Sua leitura:
  *"tem muito a ver com a forma como a gente não entrega comunicação"*.

**Reforço do time**

- **Autorizado trazer um dev temporário da Raro por alguns meses.** A sugestão é
  do Léo, motivada pela preocupação do Alê com a FACISC diante da entrada da
  **IPO** — cliente de API hoje, que pretende migrar para White Label. O
  pré-requisito que você fixou: profissional muito experiente, que aprenda o
  negócio de forma autônoma e ocupe o mínimo possível do time. **Se não
  funcionar, a pessoa volta para a Raro** — e é isso que torna o risco menor que
  uma contratação.
- **O foco dele será causa raiz**, não fila de suporte. O Santi nomeou o alvo:
  **pedido de benefício**, problema histórico e recorrente que exigiria um dia
  inteiro de investigação focada que nunca acontece.
- **Trazer a Priscila Campos para desenhar qualidade e testes.** Especialista da
  área, ex-Raro, anos em teste end-to-end e de fumaça, hoje no time do Andrade.
  O objetivo é montar a arquitetura de testes e **capacitar o Túlio e a Alana**,
  reduzindo a dependência de teste manual. O Santi apoiou lembrando que o time já
  usou Playwright anos atrás e que a saída dos QAs coincidiu com o aumento de
  problemas em produção.
- **Você vai conversar com a Priscila** para alinhar expectativa antes de
  qualquer coisa, e convidou o Santi a participar.

**O número que justifica o reforço**

A Pietra trouxe: o TPV do White Label era de **45 milhões**, a Niky adiciona
**25 milhões** — **mais de 50% de crescimento** em volume transacional,
atendimento e usuários, **sem nenhuma pessoa nova no time**. E o diagnóstico
dela: *"a gente tá enxugando o gelo, porque a gente coloca na sprint resolver
causa raiz, mas chega tanto ticket que a gente não consegue"*.

**Técnico e produto**

- **A tela de 26 mil registros:** você propôs limitar o carregamento, colocar
  campo de busca com debounce e um "selecionar todos" que resolve no backend em
  vez de materializar a lista. O Santi concordou e concluiu que dá para fazer no
  próprio Razor, sem converter para React. O Dante pode ajudar na usabilidade —
  com a sua ressalva: *"tem que dar uma segurada no Dante, tem hora que ele quer
  fazer um trem muito complexo, tem que ser simples"*.
- **Não existe documentação das jornadas de produto.** A Dani apontou que isso
  prejudica tanto o dev quanto o CSO, e vai conversar com o Dante esta semana
  para construir essa visão, fidedigna ao que está em produção.
- **A variável de PMA pedida pela Jéssica** fica com o Santi até o fim da semana.
  A Pietra sugeriu passar para o Joselito; o Santi explicou por que não: cada
  coisa que eles pegam exige ele parar para explicar, então ele está passando
  cards de melhoria, que são mais fáceis de entender.
- **O André começa hoje escrevendo um manual de triagem para o CS** — sugestão da
  Pietra, adotada por você na hora. A ideia é registrar o que o CS precisa
  investigar e trazer no card antes de escalar, aproveitando que ele vem de lá e
  que não vai depender de ninguém para fazer isso.

**Divisão da Dani**

Ela vai começar a ajudar o time do Andrade além do Coleta, e vai se organizar
para participar dos ritos dos dois. A Pietra ofereceu uma saída explícita:
*"se você achar que fica pesado participar aqui, a gente já tá conseguindo rodar
tranquilo também"*. Você complementou o alerta sobre o Coleta: *"não é assim, vai
te pedir ajuda só no help, depois ele vai te puxando mais"*.

## Próximos passos

- [ ] Montar o modelo de report de comunicação para revisão do Sol — Junior e Dani — hoje
- [ ] Enviar o primeiro report formal ao Alê, Doug e Ury — Junior — hoje
- [ ] Conversar com a Priscila Campos para alinhar expectativa e escopo de atuação — Junior — ela está numa daily; conversar hoje
- [ ] Confirmar ao Léo o OK para o dev temporário, com o pré-requisito de autonomia — Junior — sem prazo
- [ ] Otimizar a tela de listagem com busca, limite e seleção no backend — Santi — sem prazo
- [ ] Ajustar a variável de PMA pedida pela Jéssica — Santi — até o fim da semana
- [ ] Conversar com o Dante para estruturar a documentação das jornadas de produto — Dani — esta semana
- [ ] Escrever o manual de triagem e investigação para o time de CS — André — primeiras semanas
- [ ] Tratar o problema de vínculo de balance account (DMAP) — Lucas e Santi — na daily

## Como você foi

**Esta é a call mais bem conduzida sua que existe no vault.** Vale registrar o
que a fez funcionar, porque é replicável.

**Você convocou por um motivo claro e disse o motivo.** Não foi "vamos alinhar" —
foi "acordei com mensagem do Sol e do Léo, são dois assuntos, vamos por partes".
E trouxe exatamente as quatro pessoas necessárias: a Dani pela estrutura de
comunicação, a Pietra pelos números, o Santi pelo detalhe técnico que você queria
no report.

**Você pediu opinião de um jeito que permite discordância real.** Ao Santi:
*"em relação à Priscila, o que que você acha? Você acha que faz sentido? Não faz
sentido. Tô viajando?"*. Oferecer a própria ideia como possivelmente errada é o
que abre espaço de verdade — e funcionou: o Santi trouxe o contraponto mais
importante da call, que era o medo de trazer mais uma pessoa sem ter quem a
sustente. *"eu não consigo parar um tempinho para explicar para eles"*.

**E você respondeu o contraponto sem desmontá-lo.** Não disse que o medo era
infundado. Reenquadrou o risco: tem que ser alguém "safo", e se não der, devolve
para a Raro — o que é mais barato que uma contratação que não dá para desfazer.
O Santi saiu concordando de verdade, não por hierarquia.

**Você nomeou a própria transitoriedade em voz alta:** *"eu também não sei quanto
tempo que eu vou ficar aqui não, mas o time precisa conseguir rodar depois sem as
pessoas que a gente tá trazendo aqui"*. É a segunda vez que isso aparece — a
primeira foi com a Dani em 31/07 — e é o que transforma a vinda da Priscila de
"contratar um QA" em "instalar capacidade no Túlio e na Alana".

**Duas coisas pequenas e boas:** você adotou a sugestão da Pietra sobre o André
na hora, sem reformular para parecer sua. E deu um aviso operacional útil sobre o
Dante, que evita que uma tarefa simples volte complexa.

**O que daria para fazer melhor.** O Santi propôs uma alternativa que você elogiou
e deixou cair: parar dois ou três dias e atacar só causa raiz, com o time que já
existe. Sua frase foi *"pode ser uma boa estratégia, porque a gente faz o
arrumando quando o circo tá pegando fogo"* — e em seguida *"mas eu não queria
dispensar a ajuda do Léo"*. Os dois caminhos não são excludentes. O do Santi é o
mais barato, o mais rápido e o único que não depende da agenda de outra pessoa, e
saiu da call sem dono e sem data enquanto o caminho externo saiu encaminhado.

**Você afrouxou a cadência que o Sol sugeriu, no primeiro dia.** Ele propôs um
report agora e outro em 12 horas. Você converteu em "um hoje e outro no fim da
semana, e se eles sentirem falta é só dar um push". A adaptação é defensável, mas
o plano inteiro nasceu da premissa de que **esperar o outro pedir é o que criou o
problema**. Afrouxar exatamente isso na largada enfraquece o mecanismo.

**E os prazos:** só a variável da Jéssica e a conversa da Dani com o Dante saíram
com data. O dev temporário, a conversa com a Priscila e a otimização da tela
ficaram sem. É o mesmo padrão dos últimos quatro dias, e aqui é mais visível
porque a call foi boa em todo o resto.

## Pontos de atenção

- **O crescimento de 50% no TPV sem headcount é o argumento mais forte que você
  tem**, e ele apareceu pela Pietra, não por você. Vale ser o número de abertura
  do report ao Alê, Doug e Ury — é o que transforma "estamos lentos" em "estamos
  absorvendo metade mais de volume com o mesmo time".
- **A entrada da IPO no White Label é um risco novo.** Cliente de API grande
  querendo migrar, com o Alê preocupado com o impacto na FACISC. E a FACISC já
  não pode ser tombada até a distribuição de pedidos ser resolvida, conforme
  [[2026-08-03 — Planning Sprint 15 — White Label|Planning Sprint 15 — White Label — 03-08-2026]].
- **O Santi é o gargalo declarado do onboarding.** Ele disse que não consegue
  orientar os novos porque não sai de incidente, e que precisa parar para
  explicar cada coisa que eles pegam. Trazer mais uma pessoa sem resolver isso
  repete o problema — o pré-requisito de autonomia é a mitigação, não a solução.
- **A causa raiz nomeada é "pedido de benefício"**, e é histórica: *"toda vez a
  gente tem problema, a gente mexe lá, arruma, mas continua dando problema"*. É
  também o que está por trás da crise da manhã, com colaboradores ameaçando não
  trabalhar.
- **Não existe documentação de jornada de produto.** Isso conecta direto com a
  meta de OnboardAI e com o diagnóstico da devolutiva da Dani em 31/07, que
  apontava a lacuna de visão de produto — o mesmo assunto, agora com dono e
  semana.
- **A Dani está sendo repartida em três frentes** — White Label, Coleta e
  Andrade. A Pietra já ofereceu a saída, e a nota de
  [[2026-07-31 — Feedback 50 dias e Continuidade do Time — Dani|Feedback 50 dias e Continuidade do Time — Dani — 31-07-2026]] já registrava
  esse risco. Seu próprio alerta sobre o Coleta indica que você sabe que a
  demanda vai crescer.
- **Ruído de transcrição:** "NIC"/"Nick" é Niky, "FCISC"/"FCIS" é FACISC, "URI" é
  Ury, "Play White" é Playwright, "teste antiwend"/"testendí" é teste end-to-end,
  "Sand"/"Sant"/"S" é [[Gabriel Santi]], "Pri" é a Priscila Campos, "PMA" é a
  variável citada pela Jéssica e "DMAP" aparece como sigla sem contexto.
