---
data: 2026-08-03
hora: "10:00"
reuniao: "Planning Sprint 15 — White Label"
tags: [reuniao]
participantes: [Junior Oliveira, Daniela Melo, Pietra Oliveira, Gabriel Santi, Bruno Conti, Stive Tormes, Lucas Gomes, Túlio Cruz Ferreira da Silva, Dheyson Silva, Dante Marchi, Andrey Cunha, Alana Barbosa, Joselito Rend, Taillon Neves]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Planning - White Label - 2026_08_03 10_00 GMT-03_00 - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1POWq6rT4Il6iXu_P67KLIGh26hLYjcWcMe_AI-xesLg"
---

# Planning Sprint 15 — White Label | 03/08/2026

## Contexto

Planning da Sprint 15, 1h13m54s, 14 pessoas. A [[Daniela Melo]] conduziu o
ritual e a votação de tamanhos (345 falas), a [[Pietra Oliveira]] apresentou as
histórias (331). [[Gabriel Santi]], [[Bruno Conti]] e [[Stive Tormes]] fizeram o
debate técnico.

**Você falou só nos últimos quatro minutos** — 24 falas, todas depois de
01:10:00, e todas de recado. A planning é delas, e você não a disputou.

## Decisões tomadas

- **A certificação das wallets entrou na sprint sem refinamento.** O
  [[Stive Tormes]] avisou na abertura: a certificação com as carteiras está "na
  cara do gol", mas exige dois endpoints no White Label que não existem, e são
  ~2 dias de trabalho do [[Gabriel Santi]]. Apareceu na sexta à tarde, quando o
  prazo final foi estipulado. A Samsung fecha **quinta desta semana** e a Google
  entra em ~10 dias a duas semanas. A Dani desbloqueou os cards de Samsung e
  Google e realocou na Sprint 15, com subtarefa de back-end a ser criada pelo
  Stive.
- **A FACISC não será tombada enquanto a distribuição de pedidos não for
  resolvida.** Decisão da Pietra, dita nesses termos: *"a gente nem vai tombar a
  facisc enquanto isso não for resolvido"*. Na sexta uma organização com mais de
  400 pessoas travou, e levou muitas horas para descobrir que **dois** usuários
  sem bag criada bloquearam a distribuição inteira.
- **A correção é não bloquear todos por causa de um.** O [[Lucas Gomes]]
  fechou o desenho: marcar o usuário problemático como "distribuição pendente"
  em vez de travar o pedido todo. O card vai ser refinado antes de desenvolver.
- **Modo suporte:** validar o fluxo em benefícios, corrigir o bug de cair em
  despesas ao acessar uma organização, e reescrever o modal com o que o usuário
  precisa saber (72h de acesso, e-mail enviado à organização). Votado P.
- **Emissão de cartões mudou de escopo.** A Pietra reescreveu a história: a
  emissão **individual** entra agora, a tela de lote fica para uma história
  seguinte.
- **Storno de boleto entra como causa raiz.** Card do Santi, com caso FACISC de
  22/07 e efeito no tombamento da Niky. O Bruno puxou para esta sprint.
- **O André entra no time amanhã, 04/08.** Vem do CSO para apoiar o
  [[Andrey Cunha]] na frente de Helper. Começa das 9h à 13h porque está
  terminando de treinar alguém do CSO, depois migra full time.
- **Checkpoint diário da Niky às 16:00**, marcado pela Luma. Por enquanto só
  Santi e Stive; mais pessoas conforme necessário.
- **Apoio de QA para os cenários da Niky:** o Stive pediu, você chamou, e
  [[Alana Barbosa]] e [[Túlio Cruz Ferreira da Silva]] se ofereceram na hora.
- **Viagem a São Paulo na semana que vem:** Dani (quarta e quinta), Stive
  (semana toda), Pietra, Bruno (desde domingo), Lucas, Alana e Santi.
- **A escala de estimativa segue em calibração.** O Bruno sentiu falta de um
  tamanho de ~2 dias, entre o P (até 1 dia) e o M (até 3). A Dani topou ajustar
  na próxima planning.

## Próximos passos

- [ ] Criar a subtarefa de back-end dos dois endpoints da certificação — Stive — nesta sprint
- [ ] Desenvolver os dois endpoints das wallets — Santi — ~2 dias, antes de quinta (Samsung)
- [ ] Destravar o risco de bloqueio da loja de apps — Stive — prazo 08 a 10/08
- [ ] Refinar o card de status de distribuição antes de desenvolver — time — antes de iniciar
- [ ] Resolver a distribuição de pedidos que trava com usuário inconsistente — Lucas e time — é pré-requisito para tombar a FACISC
- [ ] Confirmar com o Dante o prazo do dia 07 — Pietra — ele voltou de férias
- [ ] Apoiar o Stive nos cenários de teste da Niky — Alana e Túlio — antes da call das 16:00
- [ ] Responder ao Bruno o card da FACISC que pede para não enviar e-mail ao usuário — Pietra — Bruno vai encaminhar
- [ ] Ajustar a escala de estimativa para incluir um tamanho de ~2 dias — Dani — próxima planning

## Como você foi

**O silêncio de 70 minutos não é o problema.** A planning tem dona, o ritual
está funcionando e gestor que narra planning tira o ritual de quem o construiu.
A Dani conduzindo a votação e comentando bloqueio por métrica — *"a gente
conseguiu entender porque que a tarefa ficou paralisada"* — é exatamente o que
você queria que existisse. Ficar de fora ali é acerto, não omissão.

**Seus quatro minutos foram eficientes e certeiros no que importava.** Os três
recados eram coisas que só você podia dar: a entrada do André, o checkpoint das
16:00 com visibilidade para todo mundo (e não só para os dois envolvidos), e o
aviso de que vai virar recorrente.

E o melhor momento: quando o Stive pediu apoio de QA para gerar cenário de
teste, você não levou para "vou ver" — nomeou na mesma frase: *"Alana e Túlio,
algum de vocês dois consegue ajudar a gente com isso?"*. Os dois se ofereceram
imediatamente. Isso fechou, em dez segundos, exatamente o furo que a call do
tombamento tinha deixado aberto: correção em produção sem teste que a valide.

**O que daria para fazer melhor — dois momentos pediam você e você não estava.**

O primeiro: a certificação das wallets entrou na sprint **sem refinamento, com
prazo de quinta-feira, consumindo dois dias do Santi** — o mesmo Santi que é a
única pessoa mexendo no incidente da Niky e que também tem o card de storno de
boleto. Ninguém pesou essa conta em voz alta. Isso não é decisão de story point,
é decisão de capacidade, e é sua. A Dani perguntou o esforço e aceitou o número;
faltou alguém perguntar de onde sai o tempo.

O segundo é mais grave: a Pietra disse que **a FACISC não será tombada** até a
distribuição de pedidos ser resolvida, e a frase passou sem reação de ninguém.
Isso muda um compromisso de cliente e mexe direto na sua meta de sanar a
insatisfação da FACISC — a que você apresentou ao Doug uma hora antes, nesta
mesma manhã. Mesmo que a decisão esteja certa, ela merecia um "entendi, e isso
muda o quê no prazo?" da sua parte.

**O recado do André saiu curto demais.** O Bruno precisou emendar três perguntas
seguidas — *"André, de onde que é? Em que que ele é? Ele vai ser o quê?"* — para
chegar no básico. Numa sprint em que o time já tem um Andrey e um André, uma
linha de enquadramento no começo evitava a confusão.

**E o Dheyson ficou sem resposta.** Ele perguntou direto se a tarefa de
importação de recarga da Niky estava em algum board de vocês, e você respondeu
*"não deve tá no board dele"*. O "deve" é o problema: ele é a pessoa que disse,
mais cedo na mesma call, *"tem muita coisa que eu não entendo aí, eu tô ainda
entendendo o sistema"*. Ele respondeu "beleza" e a reunião acabou.

**Sobre divergência:** nenhuma dirigida a você. O único atrito real foi entre o
Stive e o Bruno sobre o modo suporte funcionar ou não no benefício legado, e se
resolveu sozinho.

## Pontos de atenção

- **A FACISC não vai ser tombada até a distribuição de pedidos ser resolvida.**
  Isso ataca sua meta 1C pelo lado que você não previu: não é o cliente estar
  insatisfeito com o roadmap, é a plataforma não estar pronta para recebê-lo. E
  a decisão foi tomada numa planning, não numa conversa de meta.
- **O Santi está em três frentes simultâneas** e nenhuma foi negociada contra as
  outras: causa raiz do primeiro acesso da Niky (ver
  [[Tombamento Niky — 03-08-2026]]), os dois endpoints da
  certificação com prazo de quinta, e o storno de boleto. A nota de
  [[Calibragem Santi — Paulo — Maio-2026]] já registrava esse padrão — ele
  assume frentes simultâneas e "tem dado o melhor".
- **Risco de bloqueio da loja de apps entre 08 e 10/08.** Se acontecer, todos os
  apps da Swap saem do ar na loja — Interfaces, Despesas, Benefícios — e a
  certificação não pode ser finalizada. Não afeta os apps dos clientes, que são
  deles. O encaminhamento está com um contato do Léo, da Raro, sem responsável
  formal na Swap.
- **O nome do André, resolvido em 03/08.** É **[[André Almeida Rabelo]]**, e é a
  mesma pessoa da nota de migração para Tech — confirmado por você. O "Cunha"
  que constava no vault era erro de transcrição da call de 01/07, e a nota foi
  renomeada. Segue valendo conferir o destinatário antes de repassar ação: ele e
  o [[Andrey Cunha]] têm primeiro nome quase idêntico e estão os dois na frente
  de Helper.
- **A chegada do André cumpre a promessa da devolutiva do Andrey.** A pendência
  "retomar as correções de código a partir da chegada do André, agosto" tinha
  ficado sem data. Agora tem: amanhã. Vale cobrar o desdobramento.
- **A Dani saiu antes do fim com assunto pendente.** O Lucas notou (*"a Dani
  tinha alguma coisa para falar? não falou"*) e o Stive disse que ela avisaria no
  canal.
- **Duas dúvidas que a fonte não resolve:** o "Pedro" que o Dheyson está
  apoiando na importação de recarga — o único Pedro do vault é o
  [[Pedro Costa]], que saiu — e a sigla "IC" que a Pietra usou junto de
  biometria, que provavelmente é KYC.
- **Ruído de transcrição:** "Nick" é Niky, "SUAP" é Swap, "FCIS"/"FACIS" é
  FACISC, "Steve" é [[Stive Tormes]], "Sant"/"S" é [[Gabriel Santi]], "P"/"PI" é
  [[Pietra Oliveira]], "Haros"/"Har" é Raro, "end point" é endpoint e
  "Kipais" é KPIs.
