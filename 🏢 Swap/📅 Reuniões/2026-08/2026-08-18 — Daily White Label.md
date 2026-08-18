---
data: 2026-08-18
hora: "09:59"
reuniao: "Daily White Label"
tags: [reuniao]
participantes: [Alana Barbosa, André Almeida Rabelo, Andrey Cunha, Bruno Conti, Daniela Melo, Dante Marchi, Dheyson Silva, Gabriel Santi, Joselito Rend, Junior Oliveira, Lucas Gomes, Pedro Costa, Pietra Oliveira, Priscila Campos, Regis Graf, Stive Tormes, Taillon Neves, Túlio Cruz Ferreira da Silva, William Sodre]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Daily - White Label - (Oficial) - 2026_08_18 09_59 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1GJgnWsxfS9DJ7h-DzoyXppd9CB9i-4--NBa3t44Wfbs"
---

# Daily White Label | 18/08/2026

## Contexto

**41min21s.** Sem a [[Daniela Melo]], que avisou estar em compromisso externo
até 14h — diferente da daily de 07/08, que ela conduziu do início ao fim.
Falaram de fato: [[Alana Barbosa]], [[André Almeida Rabelo]],
[[Andrey Cunha]], [[Bruno Conti]], [[Dheyson Silva]], [[Gabriel Santi]],
Joselito Rend, você, [[Lucas Gomes]], [[Stive Tormes]] e
[[Túlio Cruz Ferreira da Silva]]. [[Pietra Oliveira]], Regis Graf, Dante
Marchi, Priscila Campos, Pedro Costa e William Sodre estavam convidados mas
não aparecem falando na transcrição.

> **Sobre a fonte:** é `Anotações do Gemini`, mas o export veio com a
> transcrição inteira embutida — por isso a análise de condução foi possível.

## Decisões tomadas

**Itens técnicos do dia:**
- Erro 404 (originado por ação não intencional do [[Bruno Conti]]) já corrigido.
- Bloqueio na fila de distribuição por nova validação de biometria (1 rosto por
  CPF): [[Andrey Cunha]] corrigiu e está subindo para staging ainda hoje. Se
  não normalizar até o início da tarde, o CSO será avisado de atraso de 1–2 dias.
- Notificações push com falha: o Firebase Cloud Messaging só entrega para o
  primeiro dispositivo logado na conta — [[Stive Tormes]] e [[Alana Barbosa]]
  vão investigar pelos logs, não pela visualização no app.
- Falha no envio de 2FA por e-mail no despesas: causa identificada é uma API
  do SendGrid desatualizada, que afeta todos os produtos com a mesma chave.
- MR de Billing **congelado por enquanto** — dev concluído, falta só revisar e
  testar antes de prosseguir.
- Padronização de ambientes vai focar em **multi-org** por ora, deixando
  "multiproduto" para depois (sugestão do [[Gabriel Santi]]).
- Cards parados no fluxo passam a usar a label "bloqueado" com comentário
  justificando o motivo.

**A revelação estratégica (00:29–00:38):** o Stive abriu o tema sem querer,
comentando que "tem bastante coisa sendo feita... melhorias no portal legado" e
questionando se valia a pena continuar investindo nisso. Você reconheceu na
hora — *"eu acho que o Steve acabou de dar um spoiler para vocês aqui"* —,
**mudou de sala** para não expor mais gente e foi além do que o Steve tinha
dito:

- A diretoria (você citou uma conversa de corredor com **"Wood"** — provável
  ruído de transcrição para o **Sol**, dado que bate com o mesmo relato de
  escalada registrado em
  [[2026-08-14 — Desdobramento do Roadmap com o Time|Desdobramento do Roadmap com o Time — 14-08-2026]]) autorizou **matar o
  portal legado até o final do ano**.
- Em vez de reescrever do zero, o time vai **evoluir a base do despesas** para
  incorporar benefícios.
- **CSLG é a prioridade**, não o RTF — o RTF fica para o final do ano.
- Meta provisória: **meados de outubro** para o portal novo ter todas as
  features do legado, pronto para quem quiser migrar (não que todo mundo
  migre até lá).
- **Novo dev de frontend confirmado** — Lucas, com experiência em Itaú e
  PayPal, entra no dia 1º para reforçar o time de front, hoje só com o
  [[Taillon Neves|Taillon]] sozinho.
- Você fechou avisando: **nada oficial ainda**, aguardando aprovações formais.

## Próximos passos

- [ ] Alana — marcar o card da fila de distribuição como bloqueado, com
  comentário sobre o impedimento de biometria
- [ ] Alana, Stive — investigar a falha de notificações push pelos logs do
  Firebase Cloud Messaging
- [ ] Túlio — validar se o envio de 2FA por e-mail está funcionando no
  despesas
- [ ] Gabriel — conversar com o Paulo sobre os impactos de multiorg/
  multiproduto nas interfaces dos clientes
- [ ] Grupo — alinhar ambientes de desenvolvimento entre SUAP e as demais
  instâncias, garantindo coexistência do WL 2.0
- [ ] Dheyson — reunião à tarde com a Dani sobre alinhamento com o time da
  Niky (Raro)
- [ ] Junior — avisar o CSO se o bloqueio de biometria não normalizar até o
  início da tarde de hoje
- [ ] Junior — comunicar oficialmente ao time assim que sair a aprovação —
  *"assim que eu tiver novidades aqui, que bateu o martelo, eu aviso para
  vocês o mais rápido possível"*

## Como você foi

**Você tratou bem os itens técnicos** — direto, delegando com prazo (Andrey
no staging "ainda hoje", CSO avisado só se não normalizar até a tarde),
sem travar em nenhum ponto.

**Mas a revelação estratégica foi reativa, não decidida.** Minutos antes desta
call, você tinha me explicado por que não podia abrir isso ao time ainda —
"até estar 100% certo". O Steve deu uma brecha pequena, e você escolheu ir
fundo: mudou de sala, contou o histórico completo (conversa de corredor,
escalada até a diretoria, CSLG sobre RTF, contratação nova) e só depois
nomeou o próprio atraso: *"não tem problema já ter contado para vocês, já
tinha que ter feito isso. Eu sei que eu tô devendo aí um pouquinho."*
Reconhecer a dívida na hora é honesto. Mas o critério que você tinha acabado
de me dar — só abrir com certeza técnica fechada — não foi o que decidiu o
momento; foi a oportunidade da sala vazia.

**O cuidado de mudar de sala mostra que você sabia o risco.** Isso é
consistente com o padrão de 08/08 (Força Tarefa Defense Team): boa intenção,
execução improvisada. Lá você saiu da sala sem voltar; aqui você trocou de
sala para conter a informação, mas a decisão de falar em si não foi
premeditada.

## Pontos de atenção

- **Informação assimétrica menor do que parecia à primeira vista.** A
  [[Daniela Melo]] e a [[Pietra Oliveira]] já sabiam da virada antes desta
  call — confirmado depois pelo Junior. Quem ficou de fora mesmo foi o
  restante do time que não estava na sala (e o Regis Graf, ainda de férias,
  volta só amanhã, 19/08). O grupo sem informação é menor do que a nota
  registrou originalmente, mas o princípio segue de pé: quanto mais gente
  souber informalmente, maior a chance de alguém saber por boato em vez de
  por você.
- **A data "meados de outubro" apareceu aqui pela primeira vez com esse
  nível de precisão**, mas ainda não é o número que ficou pendente de
  confirmar antes do comitê de segunda (marco 1: setembro sem FACISC vs.
  outubro com os 65 itens). Vale reconciliar antes de repetir a data para
  mais gente.
- **Contratação de dev de frontend (Lucas, ex-Itaú/PayPal, entrada dia 1º)
  não estava registrada nas notas da semana passada.** Reforça time de front
  hoje reduzido a uma pessoa (Taillon) — vale cruzar com a composição de
  times que você fechou na segunda-feira.
- **MR de Billing ficou congelado sem dono nem prazo para retomar.** Bom para
  não gerar retrabalho agora, mas sem dono declarado tende a ficar esquecido.
- **O desalinhamento com o time da Niky (Raro) segue sem solução** — mesmo
  ponto que apareceu na Planning de ontem (board separado no Trello). A
  reunião desta tarde entre Dheyson e Dani é o primeiro passo concreto.
- **Ruído de transcrição:** "Wood" é provavelmente o **Sol**, mas fica sem
  confirmação — vale checar se é isso mesmo antes de repetir o nome; "Steve"
  é o [[Stive Tormes]]; "Dan"/"Dani" é a [[Daniela Melo]]; "Nick"/"a Nick" é a
  Niky; "Fisc"/"MAP" são ambientes de cliente citados sem contexto completo;
  "UR"/"Uri" é o Ury Rappaport.
