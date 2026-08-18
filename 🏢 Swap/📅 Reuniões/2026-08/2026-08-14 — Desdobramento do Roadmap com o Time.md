---
data: 2026-08-14
hora: "11:05"
reuniao: "Desdobramento do Roadmap com o Time"
tags: [reuniao]
participantes: [Junior Oliveira, Stive Tormes, Pietra Oliveira, Daniela Melo]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Reunião iniciada às 2026_08_14 11_05 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1QT_NobjL0ElUgpKBqb21xaWQY0bsTr_lnrEbQSeYvM0"
---

# Desdobramento do Roadmap com o Time | 14/08/2026

## Contexto

**1h13m.** Você, o [[Stive Tormes]], a [[Pietra Oliveira]] e a
[[Daniela Melo]] — quatro pessoas, não o time todo. É o desdobramento de
[[2026-08-13 — Alinhamento Roadmap WL — Diretoria|Alinhamento Roadmap WL — Diretoria — 13-08-2026]].

Você abriu dando o contexto político inteiro: como começou (sua conversa com o
Ury sobre o portal legado ser o maior ofensor), como escalou até o Sol, e que
*"a gente tem, entre aspas, carta branca com relação a recursos e capacidade"*.

*O export é de Anotações do Gemini, mas veio com a transcrição inteira embutida
— por isso há análise de condução.*

> A [[Pietra Oliveira]] abriu a call contando do acidente de carro dela na
> véspera. Está bem; o carro foi de guincho e está no seguro.

## Decisões tomadas

**1. Para o RTF, começa o módulo CCLG dentro do WL 2.0.** O Stive foi direto:
*"agora é a hora da gente parar o RTF e começar um módulo novo de benefício
CCLG, inclusive pedir pro Santi o que dá para reaproveitar"*. É a execução do
que foi decidido ontem.

**2. Não se começa do zero — evolui o code base do despesas.** Consenso da sala.
O Stive: *"não tem essa de começar do zero; o código tem muita coisa
reaproveitável"*, e a estrutura do despesas *"no geral tá boa"*. **Mas com
condição:** o Santi e o Stive fazem uma análise profunda da base antes, e se ela
não sustentar, vocês usam a carta branca.

**3. O Stive e o Santi saem da execução.** Sua colocação:

> *"Vocês dois tinham que ser menos mão na massa possível. Vocês têm que
> escrever documento técnico de como fazer, porque hoje a gente não tem. Vocês
> são responsáveis por fazer a engrenagem girar — a mão de obra, a galera que
> vai carregar piano, a gente vai ter."*

O Stive aceitou com ressalva realista: *"vai ser um pouco inevitável, mas a
gente vai ter que escalar isso"*.

**4. A divisão dos times:**

| Frente | Pessoas |
|---|---|
| **Reescrita / V2** | Gabriel Santi, Stive Tormes, Bruno Conti, Dheyson Silva, Lucas, alguém de dados, **Léo como arquiteto** |
| **Sustentação** | Andrey Cunha, Regis Graf (voltando), Ana, André, Joselito, Taillon |
| **Reforço da Raro** | ~3 pessoas — um backend, um front, talvez um fullstack |

O **Lucas Verdan** entra dia **01/09** — perto demais para contar com ele agora.
Você tratou a divisão como provisória de propósito: *"é uma organização inicial;
se a gente ver que quer trocar alguém de lugar, a gente vai manipulando"*.

**5. O quórum atual é suficiente.** O Stive travou a tentação de inchar:
*"a gente tá com um quórum já bem legal, Junior — cuidado de não inflar
demais"*. Não vai ter contratação nova além do que já estava.

**6. Entra uma pessoa de dados no time.** Proposta do Stive, endossada pela
Pietra com o argumento que fecha:

> *"O white label é muito cego em relação aos dados. A gente apartou isso e
> direcionou para a SUAP, mas deveria ser algo que o nosso produto entrega. É um
> dos pedidos da FACISC, e um dos pontos em que eles estão decepcionados."*

O Stive quer contínuo, não pontual: *"não quero um cara de dados para vir aqui
executar uma tarefa"*. Ele usou o [[André Almeida Rabelo|André]] como exemplo do
que muda quando alguém vem de fora e passa a enxergar o todo.

**7. Piloto do layout novo em homologação.** O Stive já montou o app de
benefícios com a cara do despesas apontando para o back antigo. Vai para **USIP**
(preferência) e possivelmente **PIGS**, em homologação, para colher feedback sem
tocar produção. A Daniela alinha com o CSO antes.

**8. A Pietra centraliza os 65 itens da FACISC**, com a Tati e o Dante
executando. Ela escreve as histórias antes da viagem da semana que vem.

**9. Reunião semanal estratégica**, e a agenda com a FACISC passa a ser **toda
terça, 11h** — desdobramento direto da conversa com o Wagner.

### As datas — o que ficou de fato

Isso resolve a ambiguidade que tinha ficado de ontem:

- O **Ury quer a V1 morta até meados de setembro**
- **Outubro é o prazo do conjunto** — *"a gente já sabe que o prazo não vai
  mudar, é até outubro"*
- **Nenhuma data foi cravada com o Ury ainda:** *"a gente não cravou uma data
  com ele ontem, porque a gente precisava conversar aqui e entender"*

Na leitura do Stive, a **V3 não é reescrita** — é *"a versão que tem tudo"*:
multiproduto, marketplace, consignado e as melhorias da FACISC. E o **consignado
já está pronto**, preso só a questão contratual com o fornecedor. O
**marketplace** vai como plugin/SDK; se a Raro constrói ainda é discussão aberta.

## Próximos passos

- [ ] Alinhar com o Sol para garantir que Doug e Alê saibam antes do comitê — Junior — antes de segunda, 17/08
- [ ] Dar uma data para a análise da base de código da V2 — Stive — sábado, 15/08
- [ ] Pedir ao Santi a avaliação do que dá para reaproveitar no módulo CCLG — Stive — sem data
- [ ] Enviar os repositórios ao Léo para uma análise crítica — Junior — sem data
- [ ] Reunião de decisão da base de código: Junior, Stive, Santi, Bruno e Léo — terça 18/08, fim do dia
- [ ] Analisar a performance e a estrutura do front — Junior — segunda
- [ ] Grupo de trabalho dos 65 itens da FACISC: escrever e detalhar as histórias — Pietra, com Tati e Dante — antes da viagem
- [ ] Organizar com o CSO o piloto do layout novo na USIP e na PIGS — Daniela — sem data
- [ ] Agendar com a Mel a revisão dos relatórios em andamento da FACISC — Daniela — sem data
- [ ] Enviar o resumo das funcionalidades do app — Stive, para Daniela — sem data
- [ ] Montar as análises de alto nível das melhorias de back e front para levar ao Sol — Stive — sem data
- [ ] Criar usuário de teste no portal novo para o Stive — Junior — hoje
- [ ] Alinhar o discurso e comunicar a mudança ao time inteiro — Junior, com o Léo — semana que vem

## Como você foi

**Você deu contexto político, não tarefa.** Abriu contando a origem — sua
conversa com o Ury sobre o portal legado consumir o trust do time — e como
aquilo escalou. Gente que entende por que a prioridade virou defende a decisão
sozinha depois; gente que só recebe a nova prioridade reclama dela no corredor.

**E pôs qualidade acima do prazo, em voz alta, assumindo o risco você.**

> *"Não adianta nada a gente entregar em outubro e não estar com a qualidade que
> a gente gostaria. Se a gente precisar dar um passo atrás, a gente vai dar. Eu
> tô mais preocupado em fazer um negócio muito bem feito, pra gente não ser
> cobrado no futuro, do que ter que cumprir o prazo que o Uri quer."*

Isso é absorver pressão em vez de repassar. E veio no momento certo: o Stive
tinha acabado de dizer *"se já é difícil entregar em outubro um negócio sem
qualidade, imagine com qualidade"* — que é ansiedade, não análise. Você
respondeu direto na ansiedade: *"se a gente assumir o prazo, a gente não tá
assumindo sozinho. Fique tranquilo quanto a isso."*

**Você perguntou em vez de mandar, e aceitou ser contrariado.** Na composição do
time você abriu com *"como que tá a visão de vocês?"* e, quando o Stive disse
para não inflar, você não insistiu. O resultado é um desenho que o time
sustenta, não um que ele recebeu.

**E você nomeou uma falha sua sem ninguém pedir:** *"é horrível ficar tendo
essas conversas de corredor e os meninos não ficam cientes; isso é uma ação
minha"*. Chefe que diagnostica o próprio ponto cego na frente da equipe compra
crédito que nenhum discurso compra.

### O que vigiar

**O time continua sem saber, e essa é a segunda vez que fica para depois.** Você
diagnosticou o problema com precisão e a ação que saiu foi esperar o comitê —
*"semana que vem a gente tenta tirar um dia para alinhar o discurso"*. É
defensável, mas o custo é real: nove pessoas seguem trabalhando em RTF com uma
data que não existe mais, enquanto a conversa corre entre quatro. **Se o comitê
de segunda escorregar, marque a comunicação assim mesmo.**

**Cuidado com "carta branca" na boca do time.** Você usou a expressão duas
vezes. O que existe hoje, na prática, é uma decisão, um prazo e gente ainda
abstrata — o próprio Léo não deu nome nem data para ninguém. Se o time ouvir
carta branca e o comitê não entregar pessoas, a conta chega em você, não no Léo.
Vale trocar por algo verificável: *"temos apoio da diretoria e vamos brigar por
recurso no comitê"*.

**A melhor leitura política da sala foi da Pietra, não sua.** Foi ela quem
perguntou se o **Doug e o Alê** já sabem, ou se o comitê de segunda vai ser
surpresa para eles — *"para não parecer que a gente é doida e chegou do nada"*.
O Stive reforçou: *"para não parecer que de novo foi algo tirado da gente"*.
Isso virou ação sua, e ainda bem — mas era o tipo de risco que você deveria ter
visto primeiro, porque é exatamente onde uma decisão boa morre.

**E ficou combinado filtrar informação técnica do Ury.** O Stive propôs no fim:
*"não preocupar ele com essa parte técnica; ele nunca vai saber quanto a gente
jogou fora e quanto ficou"*, e você fechou. **É defensável** — o Ury não é
técnico e a proporção realmente não muda nada para ele. Mas registre que foi uma
escolha consciente, não um detalhe: essa mesma lógica, repetida, é como um time
para de contar o que está difícil.

## Pontos de atenção

- **A decisão de base de código ainda não foi tomada, e o prazo já foi.** Você
  disse "vamos usar o despesas" para fora e, para dentro, pediu a análise que
  vai decidir isso. Se ela voltar ruim na terça, você já terá dito ao Sol e ao
  Ury que a base está mantida. **Evite cravar isso com a diretoria antes de
  terça.**

- **O Sol e a diretoria precisam estar alinhados antes de segunda.** Levantado
  pela Pietra e virou ação sua. É o item mais urgente da lista — vale mais que
  o roadmap em si, porque um comitê onde o Doug se surpreende derruba a decisão
  independentemente do mérito.

- **A USIP virou detratora no NPS ontem** — era promotora do White Label. O
  Stive quer levar o piloto justamente para lá, e a Pietra apoiou com um bom
  argumento: eles são atritados mas receptivos, foram os únicos a integrar o
  FGTS sabendo que era experimento. **O risco existe e a decisão é do CSO** —
  foi bem encaminhado assim.

- **A PIGS está em risco de churn há muito tempo**, citando layout e experiência
  como 80% da reclamação, e é o cliente mais focado em app. Se o piloto tiver
  que escolher um só pelo impacto, é ela.

- **O Stive está usando IA de um jeito que resolve o seu problema de kudos.** Ele
  montou prompts que geram o diff de produto entre versões — o que mudou da
  1.33 (FACISC em produção) para a 1.35 (Niky em produção), em linguagem de
  negócio, sem nada técnico. É material de reunião com cliente e diretoria,
  feito com IA. **Isso é exatamente a categoria que só tem 1 kudos entre os 34
  do time.** Vale reconhecer nessa categoria, e vale como entrega de IA dele no
  GUP.

- **O Stive está sobrecarregado agora.** Ele saiu da call para resolver a
  certificação Google/Samsung com o Danilo cobrando — *"tô com uma bomba aqui
  para resolver"*. Ele é peça central da reescrita e está preso num projeto de
  outra frente. Vale saber quando isso libera.

- **A Mel já está fazendo relatórios para a FACISC e você descobriu por
  acidente.** Trabalho do time de dados acontecendo para o seu cliente sem
  passar por você. É o mesmo sintoma que motivou o pedido de uma pessoa de dados
  dentro do time.

- **Ruído de transcrição:** "Steve"/"Ti" é o [[Stive Tormes]]; "Sant"/"Santes"/
  "San" é o [[Gabriel Santi]]; "Ris"/"Réges" é o [[Regis Graf]]; "Andrei" é o
  [[Andrey Cunha]]; "Deon"/"Deson"/"Don" é o Dheyson Silva; "Petra"/"Pi"/
  "Api" é a [[Pietra Oliveira]]; "Dânia"/"Dani" é a [[Daniela Melo]];
  "FCIS"/"Fascis"/"Fascista"/"Francisco" é a **FACISC**; "Nick" é a **Niky**;
  "USP"/"IP"/"usay" é a **USIP**; "QYC"/"QIC" é **KYC**; "Haro"/"Rara"/"Raros" é
  a **Raro**; "Leal" é o **Léo**; "trast" é *trust*.
