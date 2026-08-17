---
data: 2026-08-04
hora: "11:20"
reuniao: "Alinhamento Qualidade e Testes — Priscila Campos"
tags: [reuniao]
participantes: [Junior Oliveira, Priscila Campos]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "gie-oqnz-qhw (2026-08-04 11_20 GMT-3) - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1DKnN9hkLyIv9u_zPDyjn09GRcc1Com1SJEa7C6buXWk"
---

# Alinhamento Qualidade e Testes — Priscila Campos | 04/08/2026

## Contexto

Conversa de **29min57s**, só vocês dois, em que você convidou a Priscila Campos
para estruturar qualidade e testes no White Label. É a execução, no mesmo dia, da
decisão tomada de manhã em [[Alinhamento — Comunicação — 04-08-2026]].

Aconteceu às 11:20, **no meio da [[War Room Niky — 04-08-2026]]** — você avisa na
segunda linha: *"pera aí só um minuto, tô fazendo um monte de coisa ao mesmo
tempo"*, e mais tarde diz que está se mudando para outra sala.

O contexto da negociação você mesmo registrou na abertura: o Andrade pedia ajuda
da [[Daniela Melo]], e você condicionou — *"eu te empresto ela, mas vai ter que me
arrumar a Priscila"*.

**Sobre a fonte:** na transcrição ela aparece como **"Risk Dev"**, nome de
exibição da conta. Você a chama de "Pri"; ela te chama de "Julinho".

## Decisões tomadas

**Você apresentou o cenário sem maquiar**

- A parte de organização está resolvida: ritos, board, dados do helper, com a
  ajuda da Dani. O problema agora é outro: *"os códigos eles não têm teste
  unitário, a gente não tem teste de carga"*.
- A imagem que você usou para o momento: *"a gente tá trocando a roda do caminhão
  com o carro andando"* e *"é loucura misturada com doideira"*.
- As causas raiz já estão mapeadas — falta braço. Daí a ideia do **dev temporário
  da Raro** só para causa raiz, com o exemplo do card de erro de recarga que
  aparece 15 vezes.
- Quem ela vai capacitar: a [[Alana Barbosa]], com gás para evoluir tecnicamente, e
  o [[Túlio Cruz Ferreira da Silva]], que domina o negócio mas *"é parado no tempo,
  é só teste manual"*, o que faz a fila de testes crescer.
- E o agravante estrutural: **dois sistemas convivendo**, o legado e o WL 2.0, com
  a dor maior no legado.

**A contraproposta dela, que é o que redefiniu o escopo**

- **A parte mão na massa é a fácil.** Ela pede a relação de repositórios, começa
  **pela API** por ser onde o custo cai mais, sobe o setup e treina a Alana e o
  Túlio para dar manutenção.
- **A parte difícil é comportamento:** *"é insanidade a gente esperar um bom
  resultado sem mudança de comportamento. Ou as pessoas arrumam o tempo ou elas
  continuam trabalhando no caos"*. E isso é cultura, que não nasce da noite para o
  dia — resultado aparece em 2 a 3 meses.
- **Ela recusou a sua ideia de parar o time uma semana:** *"não é sobre parar, é
  sobre construir acordos daqui em diante"*. Nunca viu time que parasse, a não ser
  produto em sustentação.
- **E recusou o reflexo de contratar mais QA:** *"o problema não é falta de teste,
  o problema é falta de um processo de desenvolvimento que trabalhe com
  segurança"*, *"se colocar 10 não vai resolver porque é um problema de
  engenharia"*.
- **Sobre ela como barreira humana:** se ficar na ponta testando, melhora a
  percepção do usuário e não escala. *"Se essa semana eu achei 10 bugs, semana que
  vem achei 15, na verdade a qualidade do time piorou. O ponto é que eu fiquei ali
  com o ser humano fazendo serviço de máquina."*
- **A analogia que fecha o argumento:** o hospital com 300 mil queimados chegando
  de uma vez, e a equipe decidindo não passar álcool em gel porque não há tempo —
  e três anos depois tratando infecção. *"Nunca vai se melhorar a qualidade
  enquanto não começar a fazer escolhas agora."*
- **O mecanismo que ela propõe é acordo, não força-tarefa:** coverage travado,
  subindo gradual, com piso que não abaixa. *"O meu combinado é deixar melhor do
  que eu encontrei."*
- **Métrica mensal de 30 minutos** — coverage, code smell, duplicação, cobertura
  de automação, volume de bug — com um objetivo explícito: gerar desconforto
  consciente. *"Quando você mostra o número ali que é muito negativo, as pessoas
  começam a se incomodar com isso."*
- **Assessment por formulário antes de agir**, porque consultoria que chega e
  resolve sozinha não deixa a pessoa sentir o valor: *"quando você faz um
  assessment, as pessoas falam 'essa dor, você sente também?'... ela conseguiu
  construir a história junto com você"*.

**O combinado**

- **Ela entra na daily de 05/08** para ser apresentada ao time e dar um overview
  do que vai fazer. Proposta sua, com a razão dita: *"só para não acontecer do tipo
  assim, do nada, ah, tem alguém me chamando aqui, eu não sei nem o que que é"*.
- Depois da daily ela manda o **formulário de qualidade** para o time responder.
- A **Dani inclui ela nos ritos**, e ela filtra o que não faz sentido acompanhar
  agora.
- Você vai indicando com quem ela fala, por time e por assunto técnico.
- **O acordo que você fixou:** *"tudo que a gente for fazer agora tem que ter
  teste. Não se sobe mais nada sem teste."*

**O feedback sobre a Raro, que você não pediu**

- Duas pessoas disseram a ela que, quando a Raro chegou, *"a gente não sabia se as
  pessoas iriam ficar uma semana ou um mês ou iriam apoiar, porque as pessoas só
  entraram"*. A leitura dela: gerou incômodo, mas também **afastamento**.
- A frase mais dura da call: *"a gente também foi detrator do processo"* — então
  hoje é menos sobre implantar e mais sobre **recuperar**.
- Ela contrapôs o conselho do Léo que você tinha levado ao pé da letra, de que *"as
  pessoas têm que estar incomodadas com você"*. O modelo dela é o inverso na
  ordem: criar laço, treinar, e **só depois** cobrar. *"Eu fiquei 4 anos com bug
  zero em produção e só consegui isso buildando o time na paz."*

**Sua resposta, e ela foi honesta**

- Você trocou **oito pessoas** do time desde que chegou e disse não ter dó de
  trocar: quem compra os objetivos caminha junto, quem não compra sai.
- Reconheceu o erro sem rodeio: a Raro trouxe gente para posição de tech lead
  quando o [[Gabriel Santi]] e o [[Stive Tormes]] podiam ocupar a cadeira, e isso
  gerou revolta. **Um desses tech leads da Raro você já tirou** por não entregar.
- E fixou o princípio: *"não existe lado, tá todo mundo no mesmo barco. Se é da
  Raro não tá indo bem, vai ser cobrado do mesmo jeito que a gente cobra o pessoal
  da Swap."*
- Sobre a Niky, reconheceu a raiz: a migração tinha data forçada por **multa da
  Mastercard** se não ocorresse antes de 31/07, e *"o pessoal não sabe nem como usa
  a plataforma"*.

## Próximos passos

- [ ] Apresentar a Priscila na daily e abrir espaço para o overview dela — Junior — 05/08
- [ ] Pedir à Dani para incluir a Priscila nos ritos do time — Junior — 05/08
- [ ] Enviar a relação de repositórios e a documentação das APIs — Junior — sem prazo
- [ ] Indicar quais pessoas e times ela deve procurar para a parte técnica — Junior — sem prazo
- [ ] Enviar o formulário de assessment de qualidade ao time — Priscila — depois da daily
- [ ] Subir o setup de teste de API e treinar a Alana e o Túlio na manutenção — Priscila — sem prazo
- [ ] Definir o acordo de coverage mínimo travado, com piso subindo — Junior e Priscila — sem prazo
- [ ] Extrair métricas de qualidade e apresentar em 30 min por mês — Priscila — mensal

## Como você foi

**Você vendeu o problema, não uma versão bonita dele.** Abriu com *"tenho uma
missão para você, mas vamos ver se você vai topar"* e em seguida entregou o
cenário real: sem teste unitário, sem teste de carga, dois sistemas convivendo,
time sem tempo. É o que permitiu a ela calibrar a resposta em vez de aceitar um
escopo irreal.

**E você perguntou de um jeito que permite discordância.** Duas vezes: *"queria
muito tentar entender como que você consegue me ajudar nesse cenário"* e *"então
você acha que não faz sentido?"*. Ela usou o espaço nas duas — e é dela que saiu
a melhor ideia da call.

**Você abandonou o seu plano quando o argumento era melhor.** A ideia de parar o
time uma semana morreu ali, e você migrou na hora para o mecanismo dela: acordo de
teste obrigatório para tudo que subir. Não defendeu a proposta por ser sua.

**O melhor movimento foi o da apresentação na daily.** Você insistiu que ela seja
apresentada ao time antes de acionar ninguém, justamente para ninguém ser chamado
por alguém desconhecido. Repare que isso é **exatamente a falha que ela acabou de
descrever sobre a chegada da Raro** — pessoas que entraram, colocaram a mão nas
coisas e não conversaram. Você aplicou o feedback antes de ela terminar de dar.

**E recebeu a crítica sem se defender.** Quando ela trouxe o afastamento que a
Raro causou, você não relativizou: reconheceu o erro dos tech leads, citou que já
tirou um deles e fechou com "não existe lado". Foi o momento em que a conversa
virou de negociação para acordo.

**O que daria para fazer melhor.** A call decide como a qualidade vai ser
construída no time, e você a fez em 30 minutos encaixados no meio de uma war room
de 7h29, mudando de sala e avisando que está fazendo várias coisas. Foi suficiente
para alinhar; não é suficiente para desenhar. A conversa de escopo ainda precisa
acontecer com você inteiro na sala.

**E quase nada saiu com data.** Só a daily. O envio dos repositórios, o acordo de
coverage, o piso, a indicação das pessoas — tudo ficou em "vamos nos falando". É o
mesmo padrão que o vault registra há dias, e aqui o custo é específico: ela é de
outro time e vai priorizar pelo que tiver prazo.

**Uma pendência de posicionamento que ficou aberta.** Você citou o conselho do Léo
sobre incomodar as pessoas como algo que levou ao pé da letra, e ela discordou
frontalmente, propondo laço antes de cobrança. Você não defendeu nem descartou. Ela
vai agir pelo modelo dela — vale você decidir qual dos dois vale no time, antes
que a diferença apareça na frente de alguém.

## Pontos de atenção

- **O escopo dela é maior do que "montar teste automatizado".** Ela condicionou
  resultado a mudança de comportamento, vai medir e vai expor número ao time. O
  desconforto é parte do método, não efeito colateral — e você é quem vai sustentar
  isso quando alguém reclamar.
- **Vocês estão em prazos diferentes, e isso não foi reconciliado.** Você disse na
  call que precisa *"começar a ter dados para dar resposta pra diretoria"*. Ela
  disse que mudança de comportamento aparece em 2 a 3 meses. As duas coisas são
  verdade e ninguém combinou o que se diz à diretoria nesse intervalo.
- **O legado pode ficar de fora.** A dor maior está nele, e a estratégia dela
  começa pela API por questão de custo. Vale confirmar se a cobertura de API
  alcança o legado ou se o pior pedaço segue sem teste.
- **Ela é do time do Andrade e a vinda foi negociada como troca pela Dani.** Se o
  Andrade puxar de volta, você perde a frente de qualidade — e a Dani já está
  repartida em três frentes, conforme
  [[Feedback 50 dias e Continuidade do Time — Dani — 31-07-2026]].
- **Ela não tem nota em `👥 Time/`**, então o histórico dela começa aqui.
- **Ruído de transcrição:** "Risk Dev" é a Priscila Campos, "Pri"/"PR" é ela,
  "Julinho" é você, "Qway"/"Q" é QA, "IPI"/"EPI" é API, "Cai" é CI,
  "corativo"/"quarto quarto" aparecem no lugar de coverage, "Bu Zero" é bug zero,
  "Harro"/"rara" é Raro, "sol" é o Rodrigo Sol, "Sant" é o [[Gabriel Santi]],
  "Steve" é o [[Stive Tormes]], "NIC"/"Nick" é Niky e "Robson" é onde vocês
  trabalharam juntos antes — a transcrição não deixa claro se é empresa ou pessoa.
