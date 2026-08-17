---
data: 2026-08-05
hora: "10:52"
reuniao: "War Room Niky"
tags: [reuniao]
participantes: [Junior Oliveira, Gabriel Santi, Stive Tormes, Thales Machado, Túlio Cruz Ferreira da Silva, Lucas Gomes, Bruno Conti, Luma Gomes Leonardo, Dheyson Silva, Guilherme Andrade, Alana Barbosa, Anna Albuquerque, Kelly Almeida]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Niky - 2026_08_05 09_52 GMT-04_00 - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1rDQ2GvKgGLxifu5ScICbSx7wmHC_C81-Qah2OeMlJgg"
---

# War Room Niky | 05/08/2026

## Contexto

**7h55m30s**, terceiro dia consecutivo de sala aberta e o mais longo dos três —
ontem foram 7h29, anteontem 5h20 divididos em quatro sessões.

Quem falou, por volume: [[Gabriel Santi]] (1.297), [[Stive Tormes]] (1.090),
Thales Machado (783), **você (613)**, [[Lucas Gomes]] (576), [[Bruno Conti]] (317),
Luma Gomes Leonardo (161), Dheyson Silva (128), Guilherme Andrade (110),
[[Alana Barbosa]] (91), Anna Albuquerque (49) e Kelly Almeida (43). O
[[Túlio Cruz Ferreira da Silva]] aparece em volume alto de fala espalhado pelo dia
inteiro e foi quem sustentou a sala nos períodos em que você saiu.

**Você falou 613 vezes contra 269 ontem.** É a maior presença sua registrada numa
sala de guerra, e ela aparece no conteúdo: hoje você distribuiu caso, chamou
reforço e cobrou fechamento, em vez de acompanhar.

No meio dela você fez a retrospectiva às 15h e a entrevista do
[[Processo Seletivo — Manolo Pina]] às 16h — e chegou a cogitar desmarcar o
candidato para ir ao checkpoint com a Niky. O Túlio foi no seu lugar.

O tom virou dentro do próprio dia. Começou com o time caçando causa em cinco frentes
e terminou com o Túlio voltando do checkpoint dizendo *"agora já tá uma conversa mais
amigável"* e *"consegui me livrar de dois cards que não era problema nosso"*.

## Decisões tomadas

**Desbloqueio de cartão — causa raiz encontrada, e quem achou foi a Luma**

Ela puxou os cinco tickets abertos do tema, cruzou os CPFs e viu que **quatro tinham
a mesma pendência de verificação de identidade**. A conclusão foi dela:

> *"Os caras estão conseguindo logar e dar o erro no desbloqueio porque tá com essa
> pendência na validação biométrica, ou seja, não deveria deixar logar."*

O [[Stive Tormes]] explicou o mecanismo: **o app nunca teve guard rail de KYC** —
validava só biometria, porque antes o usuário só chegava ao app com o KYC já
aprovado. Com o fluxo novo, em duas etapas, passou a existir a combinação
`identity verification approved` + `KYC rejected`, e o app deixava entrar. O usuário
logava, caía numa home quebrada e tomava erro em qualquer ação — inclusive
desbloquear cartão.

A origem é a importação: gente migrada com **nome, CPF ou data de nascimento
errados**, que reprovou no KYC mas passou no Ident. Um caso concreto encontrado ao
vivo: uma pessoa aprovada em uma organização e reprovada em outra, com o nome
grafado errado, logando e quebrando na troca de empresa.

**O que o Santi subiu:** bloqueio de login sem KYC aprovado, e o vínculo de cartão
virou **idempotente** — se o cartão já estava vinculado mas não salvou na base, agora
salva e segue, em vez de recusar.

**Estorno de TED caindo na carteira errada — diagnosticado pelo Thales e pelo Túlio**

Uma organização que só tem a carteira "premiação" fez um TED acima do limite. O
sistema simula a saída e estorna em seguida — e o estorno **caiu no saldo livre, que
nem estava habilitado para aquela organização**.

A causa que os dois montaram: existiam duas categorias "premiação" no portal, uma
ativa (ID 14) e uma inativa (ID 16). O ID 16 é o mesmo do saldo livre. Na devolução,
**o sistema valida pelo nome da categoria, não pelo ID Swap** — bateu no nome,
pegou o ID do inativo e jogou o dinheiro no saldo livre.

Paliativo aplicado na hora: renomearam as inativas e trocaram o balance para 100.
Fica pendente revisar o código para confirmar se a devolução de TED valida nome ou
balance ID.

**Caso Ecom — devolvido ao cliente, não era nosso**

O cliente alegava saldo transferido e não disponível no app. O Túlio verificou que
**não existe nenhum pedido criado** para aquela organização no portal de gestão. A
leitura do Thales: *"parece que eles efetuaram a recarga no sistema antigo deles, da
DOC"*. Combinado devolver com a explicação de que sem pedido gerado no sistema da
Swap o saldo não cai.

**Melhorias da Niky vão ser levadas para os demais clientes**

Você e o Túlio fecharam que tudo que foi corrigido aqui serve para toda a base. Sua
posição: subir primeiro as correções, depois as melhorias, e usar a Niky como prova
de fogo — *"se tiver redondinho com a Niky, a gente não vai ter problema trazer isso
pros outros clientes"*. O Túlio: *"se isso aqui diminuir os nossos helper, vai ser a
coisa mais linda"*.

**App novo em revisão nas lojas** com tema escuro, correções de acesso e melhorias de
performance. O Stive reescreveu vários serviços do app no processo.

## Próximos passos

- [ ] Revisar o código de devolução de TED para confirmar se valida nome ou balance ID — Gabriel Santi / Bruno Conti — sem prazo
- [ ] Puxar a relação de categorias inativas com balance ID duplicado nos demais clientes — Thales Machado — sem prazo
- [ ] Investigar o estorno sem rastro (ver Pontos de atenção) — Bruno Conti — travado
- [ ] Destravar a emissão de cartão físico em staging, que não vincula o combo card — Gabriel Santi — bloqueia os testes do Túlio e do Lucas
- [ ] Descobrir por que o webhook de KYC não replica o status no portal em staging — Bruno Conti — sem prazo
- [ ] Confirmar com o Stive se o bloqueio de login por KYC cobre todos os cenários do app — Gabriel Santi / Stive Tormes — sem prazo
- [ ] Levar as correções da Niky para os demais clientes, correções antes de melhorias — o time — depois de estabilizar
- [ ] Responder individualmente os tickets de acesso, porque a resposta não é a mesma para todos — Luma Gomes Leonardo — hoje
- [ ] Devolver o caso Ecom ao cliente com a explicação do pedido — Luma Gomes Leonardo / Túlio — na call
- [ ] Reunião sobre jornada de cadastro e fonte única de clientes — marcada pelo Rafa, de Dados
- [ ] Alinhar com a Anna Albuquerque o escopo de segmentação de push notification — Junior e Stive — precisa de conversa própria

## Como você foi

**Você conduziu, e a diferença com ontem é grande.** 613 falas contra 269. E não é
volume vazio: você distribuiu caso por caso da planilha, chamou o Bruno para reforçar
quando viu o Santi afunilando, pediu ao Lucas para pegar a rota de ocupações,
direcionou dois casos para o Andrei e fez a ponte com o Andrade, de Riscos, mais de
uma vez.

**A melhor pergunta do dia foi sua, e é de gestor:** *"a gente já fez alguma ação de
correção ou a gente tá só simulando o problema?"*. Numa sala em que sete pessoas
estavam investigando em paralelo havia horas, foi a pergunta que separou diagnóstico
de entrega.

**E você fechou o loop com o cliente sem esperar ser cobrado.** Perguntou à Luma se
tinha entrado caso novo além dos dois do dia, e mandou marcar como resolvido o que já
estava tratado. Verificação antes da afirmação — que é a crítica que o vault registra
desde 03/08 — apareceu de novo hoje.

**O que daria para fazer melhor.** O Thales pediu, com todas as letras, que você ou o
Túlio estivessem no checkpoint das 16h: *"só para ter alguém ali de White Label,
porque às vezes tem algum contexto que a Luma não vai saber explicar, às vezes nem eu
sei também"*. Você tinha a entrevista do Manolo marcada para o mesmo horário, cogitou
desmarcar o candidato e no fim mandou o Túlio. Deu certo — mas é o terceiro dia
seguido em que a cadeira do White Label na frente do cliente é ocupada por outra
pessoa, e desta vez ela foi pedida nominalmente.

**A entrevista no meio da war room repete o padrão de anteontem.** A conversa com a
[[Priscila Campos]] foi encaixada no meio da sala de ontem, e a nota registrou que
serviu para alinhar mas não para desenhar. Hoje foi uma entrevista de 1h21 no mesmo
formato. O custo não apareceu na war room; apareceu na entrevista, que passou do
tempo e deixou quatro perguntas de fora.

## Pontos de atenção

- **Dinheiro se moveu sem deixar rastro, e ninguém sabe como.** No caso do estorno, o
  Bruno procurou em tabela de transferência bancária, em tabela de auditoria e nos
  logs, e **não achou registro de nada** — nem do endpoint sendo chamado. A conclusão
  dele: *"ou foi uma operação manual ou foi algum script que foi executado"*. Ficou
  sem dono e sem prazo. Numa operação que passou por migração com script manual, isso
  é o achado mais grave do dia e o único que não avançou.

- **Staging está travado e isso bloqueia teste.** Usuários ficam presos em análise, o
  webhook de KYC não replica o status no portal, e a emissão de cartão físico não
  vincula o combo card. O Túlio e o Lucas passaram o dia sem conseguir validar o que
  precisavam. O Túlio chegou a perguntar se valia subir direto em produção para
  testar lá.

- **O Thales foi até 2h30 da manhã.** Emitiu os cartões e executou as transferências
  que o cliente pediu até meia-noite, precisou escrever a parte de fundos porque o
  script existente só mandava para bag, e depois ainda foi atrás dos outros clientes
  que ficaram parados o dia todo. A [[Pietra Oliveira]] já tinha registrado em 03/08
  que ele estava desgastado antes disso começar. Ele não é do seu time — quem pode
  ajustar a carga dele é outra pessoa, e vale a conversa.

- **A cadência cai na semana que vem.** O Thales avisou que estarão todos presenciais
  e que não dá para garantir checkpoint diário — *"vai ter uma no máximo"*. A
  estrutura que segurou o cliente nesses três dias se desmonta sem substituto
  definido.

- **A segmentação de push notification que a Anna trouxe é projeto, não ajuste.** O
  Stive foi direto: não existe base para isso hoje — só há segmentação por
  organização. Fazer o que foi pedido exige público no Analytics, criação de tópicos,
  inscrição de usuário e disparo no backend. Entrou como demanda e precisa de
  dimensionamento antes de virar compromisso.

- **O app legado está sem dono arquitetural, e o Stive nomeou isso.** Descreveu a
  arquitetura como *"meio Frankenstein"*, projeto de quatro anos que foi comprado e
  passou por vários times, e disse que não se preocupa mais com fidelidade
  arquitetural nele porque a ideia é migrar tudo para o WL 2.0. É decisão consciente,
  mas significa que o legado vai piorar até a migração acontecer.

- **Ruído de transcrição:** "Sant"/"S" é o [[Gabriel Santi]], "Steve" é o
  [[Stive Tormes]], "Tales"/"Thalis"/"Thal" é o Thales Machado, "Luna" é a Luma,
  "Tú"/"T" é o [[Túlio Cruz Ferreira da Silva]], "QIC"/"QYC"/"que o IC" é KYC,
  "Nick"/"NIT"/"NX" é Niky, "punk"/"pan" é o PAN do cartão, "doc" é o sistema antigo
  da Niky e "bag" é bag mesmo.

- **"Andrei" é ambíguo por construção, e vai continuar sendo.** O nome aparece cinco
  vezes e **o [[Andrey Cunha]] e o [[André Almeida Rabelo]] estão os dois na war
  room**, os dois na mesma frente de Helper. A transcrição colapsa os dois num
  "Andrei" só e o contexto de triagem de ticket serve para qualquer um deles.
  **Consequência prática:** toda ação atribuída a "Andrei" nas notas de war room é
  não confiável — na dúvida, confirme com quem estava na sala antes de cobrar. Se
  isso incomodar, o conserto é na origem: nomes de exibição distintos no Meet.
