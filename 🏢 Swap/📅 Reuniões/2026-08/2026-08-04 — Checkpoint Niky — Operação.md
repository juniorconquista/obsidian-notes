---
data: 2026-08-04
hora: "15:59"
reuniao: "Checkpoint Niky — Operação"
tags: [reuniao]
participantes: [Junior Oliveira, Luma Gomes Leonardo, Thales Machado, Gabriel Santi, Stive Tormes, Túlio Cruz Ferreira da Silva, Paulo Pereira, Luiz Lauxen, Ricardo Etchenique, Renata Correia, Alyne Ribeiro, Vanessa Preite, Milka Braga Souza do Nascimento]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "[Niky] Checkpoint diário operação  - 2026_08_04 15_59 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1N8wSrI-yHK-2BzeNnNNLouWhBo520eG7buzBqtyVVhY"
---

# Checkpoint Niky — Operação | 04/08/2026

## Contexto

O segundo checkpoint diário com o cliente, 55min35s. Continuação de
[[2026-08-03 — Checkpoint Niky — Operação|Checkpoint Niky — Operação — 03-08-2026]], e o dia é o mesmo em que você
enviou o primeiro report formal à diretoria.

Do lado da Swap: Luma Gomes Leonardo conduzindo, com [[Gabriel Santi]],
[[Stive Tormes]], [[Túlio Cruz Ferreira da Silva]], Thales Machado e Paulo
Pereira. Do lado da Niky: Ricardo Etchenique, Renata Correia, Alyne Ribeiro,
Vanessa Preite e Milka Braga.

**Você e o Luiz Lauxen estavam convidados e não falaram nenhuma vez.** Paulo
Pereira, Vanessa, Milka e o próprio Ricardo não constavam na lista de
convidados e falaram — mesmo padrão de ontem, a lista não representa a sala.

O tom é completamente diferente do de ontem. Ontem era escalada; hoje é
operação: Luma abriu explicando que o time está atrás de **padrão** nos tickets
em vez de tratar caso isolado, e a call rodou tema por tema com decisão em
quase todos.

**Sobre a fonte:** é `Anotações do Gemini`, mas o export traz a transcrição
completa depois das observações, então as falas abaixo são literais.

## Decisões tomadas

**App e acesso — as correções entraram**

- **A versão corrigida foi aprovada pelas lojas e o force update está ligado.**
  O Stive explicou o ciclo: deploy de app passa por revisão da Apple e da Google,
  então existe uma flag para forçar atualização e garantir que ninguém fique numa
  versão com problema limitante.
- **As flags de biometria de login foram desligadas como paliativo** — Face ID e
  digital — porque era ali que o usuário travava em tela parada. O Stive religa
  conforme a base for atualizando.
- **Separação importante que o Stive fez, provocado pela Alyne:** essa biometria
  é a de conveniência do login, **não** a do KYC com coleta de documento. Status
  "em análise" não é afetado. A pergunta dela era boa e evitou confusão que ia
  virar ticket.
- **A correção do botão de cadastrar ainda não subiu** — está em revisão nas
  lojas. Até então a orientação ao usuário é clicar no olhinho e conferir a
  senha; o fluxo não é impeditivo.
- **Antes de abrir ticket, o CS da Niky valida se o usuário está na versão
  nova.** A Luma foi direta: se o erro persiste na versão nova, é problema; se é
  versão antiga, é o mesmo caso já resolvido. O Stive gera um PDF com os fluxos e
  erros corrigidos para orientar o atendimento.
- Modo escuro entrou no mesmo pacote, como feature, não correção.

**Qualicorp e a carteira saldo livre — a decisão principal do dia**

- **O diagnóstico:** na migração, o saldo nasceu em premiação e terminou numa
  carteira "saldo livre" que **não está habilitada na organização Qualicorp**. O
  usuário vê o saldo no app e não consegue movimentar, porque a categoria não
  existe para a org. Vem do depara de carteiras — a nomenclatura da Niky era
  "saldo livre" e na Swap é "premiação".
- **Decidido habilitar temporariamente a carteira saldo livre na org, via script
  do Paulo Pereira**, em vez de transferir os saldos. O argumento do Paulo é o
  que fechou a decisão: *"eu acho que é a operação mais perigosa, a gente tentar
  fazer a transferência e também a gente pode inclusive consumir limites das
  pessoas como efeito colateral e gerar um outro problema por cima"*.
- É habilitação na organização, ação única, não precisa mexer usuário por
  usuário.
- **O bug que devolve estorno em saldo livre em vez de premiação seria corrigido
  hoje.** Depois que o saldo remanescente zerar, a categoria pode ser
  desabilitada.
- **O caso da Clarissa não é falha de migração.** O Túlio leu o cenário: o
  dinheiro caiu dia 01 e se moveu dia 03, e *"o dinheiro não se movimenta
  sozinho"* — provável tentativa de TED acima do limite que gerou estorno na
  carteira errada. A Luma confirmou que o saldo nasceu no lugar certo.

**Limite de saque**

- Hoje está em R$ 1.000 por transação. O Ricardo pediu voltar à regra que a Niky
  tinha: **até 10 saques diários de até R$ 1.000 cada**, geral, não por pessoa.
  Motivo dele, sem rodeio: *"esses caras que sacam geralmente são os caras que
  recebem saldo livre, então é pentelhação"*.
- A Luma pediu formalização por WhatsApp para efetivar, e disse que sai no mesmo
  dia.
- **O Thales fixou uma regra de rastro:** alteração geral pode ir pelo pedido,
  mas exceção por cliente exige ticket — *"daqui a um ano vão falar: por que que
  o Steve pode sacar R$ 20.000? Quem que autorizou isso?"*.

**Cartões e remessas**

- **Conrio:** 3.500 cartões porta a porta. Cerca de 24 casos estão sem o bairro
  e **ficam fora da remessa atual** para não travar o envio do resto. A Renata
  completa os dados depois.
- **Os 80 endereços com erro** que o Jorge passou ficam com a Alyne, que vai
  puxar o endereço certo no Google.
- **O Thales decidiu fazer remessa e Pix em sequência, não em paralelo:** *"são
  duas coisas muito sensíveis para fazer na mão e chance de errar é grande"*.

**Ritos**

- **A semanal de amanhã foi cancelada** — as dailies estão suprindo o
  alinhamento. O Thales pediu ao João para desmarcar.
- A Luma manda o reporte dos tickets do dia no fim do dia, com a tratativa de
  cada um, como fez ontem.

**Souza Lima**

- Os 15 usuários pendentes não são só KYC. As recusas são por erro de digitação e
  CPF inválido, **incluindo um caso de CPF de pessoa falecida**. A Niky checa no
  console, caso a caso.
- Número que a Luma trouxe: **9.800 documentos enviados, 9.700 aprovados, 99% de
  aprovação**. A recusa é percentual pequeno e pontual.

**Aceitação de cartão**

- **Voucher recusado em autoatendimento: orientar o usuário a passar no débito.**
  Exceção é mobilidade, que segue em investigação.
- O Thales explicou a causa: depende do estabelecimento atualizar para o trilho
  correto e das adquirentes ficarem compliant. A Swap leva report à Mastercard
  três vezes por semana. Ele deu o precedente do iFood, que não aceitava nenhum
  BIN da Swap e foi resolvido.
- **A Luma vai compartilhar mensalmente os materiais de aceitação de mercado**, e
  o estudo interno em que a Swap distribuiu cartão para os colaboradores e testou
  transação em vários cenários para reportar à Master.
- **O Stive vai publicar banners e vídeo explicativo** no app e no portal, com
  instrução sobre o fallback para crédito, mais notificação própria quando a
  transação é recusada.

**O que ficou sem decisão**

- **TED e boleto em massa:** o Thales precisa validar com o time de processadora.
  Habilitar TED e saque sai por script, mas taxas variáveis por cliente podem
  impedir script único. Fica manual por enquanto.
- **Escala, consolidação de alimentação e refeição:** o Thales recusou mexer
  agora — *"a gente já tá mexendo em muito saldo e ficar mexendo agora seria um
  pouco crítico"*. Pediu à Alyne mapear quem está com saldo errado enquanto isso.
- **Documentos de menores:** threads abertas no suporte, sem retorno. O Thales
  vai cobrar.
- **Delay de ~2h na notificação de recusa** que a Renata reportou: possível delay
  de webhook, a revisar depois das correções.

## Próximos passos

- [ ] Formalizar por WhatsApp a regra de saque de 10x R$ 1.000 por dia — Ricardo Etchenique — hoje
- [ ] Habilitar a carteira saldo livre na organização Qualicorp via script — Paulo Pereira — na sequência da call
- [ ] Corrigir o bug que devolve estorno em saldo livre em vez de premiação — time — hoje, conforme dito na call
- [ ] Gerar o PDF com fluxos e erros corrigidos na última versão do app — Stive Tormes — em seguida
- [ ] Enviar o reporte dos tickets do dia com a tratativa de cada um — Luma Gomes Leonardo — fim do dia
- [ ] Desmarcar a semanal de amanhã — João, pedido do Thales
- [ ] Completar os endereços sem bairro da Conrio — Renata Correia — sem prazo
- [ ] Corrigir os 80 endereços que deram erro — Alyne Ribeiro — sem prazo
- [ ] Validar com a processadora a habilitação em massa de TED e boleto — Thales Machado — depois das remessas
- [ ] Cobrar o retorno das threads dos documentos de menores — Thales Machado — sem prazo
- [ ] Mapear os colaboradores da Escala com saldo errado — Alyne Ribeiro — sem prazo
- [ ] Abrir chamado de mobilidade e enviar print do extrato de recusa da wallet — Vanessa Preite — sem prazo
- [ ] Compartilhar os materiais de aceitação de mercado e o estudo interno — Luma Gomes Leonardo — mensal
- [ ] Publicar banners e vídeo explicativo no app e no portal — Stive Tormes — sem prazo
- [ ] Religar as flags de biometria de login conforme a base atualizar — Stive Tormes — acompanhando

## Como você foi

**Você não falou uma única vez em 55 minutos.** Zero falas. Ontem foram duas em
1h03. Você confirmou que estava na call, como ouvinte — então é silêncio, não
ausência. São dois dias seguidos calado na sala em que o cliente discute o
produto que é seu, e agora é padrão, não episódio.

A diferença é que hoje **o silêncio custou menos**, e vale entender por quê. As
três frases que faltaram ontem — causa raiz do primeiro acesso encontrada, parte
dos prints é do app antigo do cliente, a lentidão tem causa e não é infra — hoje
apareceram na call. Só que foram o Stive e a Luma que as disseram, não você. O
enquadramento aconteceu; a sua ausência nele é que se repetiu.

**E teve um ganho concreto seu no meio disso, mesmo sem você abrir a boca.** O
Paulo Pereira estava na sala e resolveu a decisão principal do dia. Ontem você
nomeou duas vezes que a falta de repasse dele era a causa raiz do estrago e a
pendência mais crítica; hoje ele está operando junto com o time na frente do
cliente. A aproximação que você pediu aconteceu, mesmo sem a reunião de repasse
ter data.

**O que daria para fazer melhor.** Numa call de 55 minutos com onze pessoas, uma
frase sua bastaria para fazer o que ninguém fez: fechar o dia. Ninguém disse ao
cliente o que estava resolvido, o que ficou aberto e o que vem amanhã — a call
terminou em "vou mandar o reporte no fim do dia" e tchau. Você tinha essa visão
inteira, porque acabou de escrevê-la num email para a diretoria. Era só dizer em
voz alta.

**E vale registrar a assimetria:** você passou o dia escrevendo o report que
explica esta operação para o Alê, o Doug e o Ury, e não disse uma palavra na sala
em que a operação estava acontecendo. As duas coisas são trabalho seu, mas só uma
delas o cliente vê.

## Pontos de atenção

- **O report que você enviou hoje diz que a Niky "demonstrou satisfação".** Esta
  call sustenta isso em parte: o Ricardo agradeceu o Thales de forma efusiva na
  questão dos cartões — *"obrigado. Irado. Valeu"* e *"isso já ajuda demais"*. Mas
  também teve atrito real e não resolvido sobre aceitação de cartão: *"é f***
  justificar pro cara isso"* e *"é um discurso ruim"*. A frase do email é
  defensável, não é completa.
- **Recusa em Carrefour, Açaí e iFood é o ponto onde o argumento técnico não
  passa.** O Ricardo já rejeitou explicitamente a explicação de adquirente não
  atualizada nesses casos: *"os caras tão 100% compliance já"*. Orientar o usuário
  a passar no débito resolve a transação e não resolve a conversa dele com o
  cliente final.
- **Mexer em saldo virou gargalo com três frentes críticas simultâneas** —
  remessa Conrio, Pix e carteira Qualicorp — e o Thales explicitou que não faz em
  paralelo pelo risco de erro manual. Enquanto isso a Escala espera.
- **A operação está dependendo de script manual do Thales e do Paulo.** É ponto
  único de falha em duas pessoas, num momento em que tudo é urgente.
- **A Renata avisou que o problema vai mudar de natureza:** *"daqui 15 dias, lá
  pro finalzinho do mês, as recargas vão começar a cair e os nossos motivos e
  problemas vão ser outros"* — de cadastro e acesso para uso de cartão. Vale
  preparar o time e o report para essa virada.
- **O repasse formal do Paulo continua sem data**, mesmo com ele já atuando junto.
  A proximidade aconteceu por circunstância, não por combinado.
- **Ruído de transcrição:** "Steve"/"Chir"/"Estive" é [[Stive Tormes]],
  "QYIC"/"QIC"/"o IC"/"o AC" é KYC, "com Rio"/"CONR"/"Conri" é Conrio,
  "Aquaricorp"/"Qualic" é Qualicorp, "Nick" é Niky, "SUAP" é Swap, "Bali" é o
  Marcelo Balija, "Andrei" é [[Andrey Cunha]], "GISUM" é o Gison,
  "fall"/"fallendo"/"falleir" é fallback, "vcher" é voucher, "carrefura" é
  Carrefour, "Rê"/"Rei" é a Renata Correia, "Aline" é a Alyne Ribeiro, "Milca" é
  a Milka, "retentar transferência" é o termo correto do portal e
  "bag"/"bags" é bag de saldo.
