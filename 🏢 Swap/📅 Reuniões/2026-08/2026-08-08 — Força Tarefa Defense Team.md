---
data: 2026-08-08
hora: "09:03"
reuniao: "Força Tarefa Defense Team"
tags: [reuniao]
participantes: [Junior Oliveira, Stive Tormes, Gabriel Santi, Andre Rabelo, Túlio Cruz Ferreira da Silva, Andrey Cunha]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Força tarefa defense team - 2026_08_08 09_03 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1F1-Y2NDgewamHexFL5f3pRc3TeJFPHeJaHpGl90zELc"
---

# Força Tarefa Defense Team | 08/08/2026

## Contexto

**Sábado.** A primeira força-tarefa do time de Defesa, no dia seguinte ao anúncio
da divisão em [[2026-08-07 — Daily White Label|Daily White Label — 07-08-2026]]. A sala foi reservada das 9h às
14h — **cinco horas** — mas a transcrição tem **25min50s** e termina com o
[[Túlio Cruz Ferreira da Silva]] perguntando *"parar de gravar, né? Para que que
essa sala tá gravando?"*. As outras quatro horas e meia não têm registro.

Falaram o Túlio, o [[Andrey Cunha]], você e o [[Stive Tormes]]. **O
[[Gabriel Santi]] não entrou** — tinha dito que chegaria mais tarde — e o
Andre Rabelo, convidado, não aparece.

O sábado não estava planejado como força-tarefa de agenda: a manhã começou porque
a Luma mandou mensagem cedo dizendo que os usuários da Niky não estavam recebendo
código de verificação.

> **Sobre a fonte:** é `Anotações do Gemini`, mas o export traz a transcrição
> embutida, com as falas. Por isso a análise de condução foi possível.

## Decisões tomadas

**Nada foi resolvido dentro da call.** O que houve foi diagnóstico e encaminhamento.

**Falha no envio de OTP — o assunto que tomou a manhã**

Os usuários não recebem o código de verificação por e-mail. A suspeita ficou no
**SendGrid**, e o quadro que o Túlio levantou testando cliente por cliente:

- **Não chega:** SUAP, TNT SUAP, **Niky** e Próspera
- **Chega normalmente:** FACISC
- **Interfaces:** entra direto, porque o OTP **está desativado** ali

O problema **já existia na sexta** — *"ontem eu não tava recebendo nem pro ambiente
de stage"* — e o Stive confirmou: *"ontem era vários, lembra que a gente testou?"*.

Duas coisas ficaram sem resposta e são as que importam:

1. **Por que só alguns clientes?** O Túlio disse em voz alta o que não fecha:
   *"estranho, como que um... será que vai ter uma ou outra que não vai funcionar?
   Faz nem sentido."* Se fosse SendGrid caído, cairia para todos.
2. **Ninguém sabe onde desativar o OTP.** O Stive: *"tem como desativar isso? É um
   feature flag no portal também."* O Túlio: *"sei que dá para desativar, mas aí é
   com o Santi mesmo."* A saída de contingência dependia de alguém que não estava
   na sala.

**Encaminhamento:** você identificou que é caso de SRE e ficou de acionar o Márcio.

**Bloqueio de cartão está cancelando o cartão — bug novo e recorrente**

O usuário usa o **bloqueio temporário** no app — aquele de "perdi o cartão, bloqueio
até achar" — e o sistema **cancela em definitivo**. Depois ele não consegue mais
desbloquear.

- **Do lado da Swap o cartão consta apenas bloqueado**; no sistema de vocês, cancelado.
- **É o segundo caso** — uma mulher antes, e agora um usuário reportado pela Carol,
  do CS.
- A hipótese do Túlio é que seja específico da Niky, *"por conta do código da Niky
  estar diferente"*.
- **Não dá para reproduzir.** Não há cartão físico de teste em staging nem no
  ambiente da Niky. O Túlio pediu ao Santi, que não conseguiu criar; o Bruno também
  não. A frase dele: *"se os caras que sabem não conseguiram, não vou nem tentar"*.

**Tela de aprovação de despesas — possível retrabalho.** O Andrey trouxe um card do
Bruno sobre estorno aparecendo antes da transação de compra, e o Túlio reagiu:
*"isso aqui já tava mais do que arrumado"* — a lógica de tirar o valor da
justificativa no caso de estorno já existia. Vale conferir se é regressão ou card
duplicado.

## Próximos passos

- [ ] Acionar o Márcio, do SRE, sobre a instabilidade no disparo de e-mail — Junior — combinado na call
- [ ] Verificar se há mais clientes com falha de disparo além dos identificados — Túlio Cruz — sem prazo
- [ ] Descobrir onde fica o feature flag que desativa o OTP no portal — depende do [[Gabriel Santi]] — sem prazo
- [ ] Testar o fluxo de bloqueio de cartão para entender por que cancela — Túlio Cruz — bloqueado por falta de cartão de teste
- [ ] Criar cenário de cartão físico em staging para a Niky — [[Gabriel Santi]] — tentado e sem sucesso
- [ ] Conferir se o card da tela de aprovação de despesas é regressão ou duplicata — Túlio e Bruno — sem prazo
- [ ] Chamar o [[Lucas Gomes]] para apoiar, se puder — Andrey Cunha — feito na call, sem retorno

## Como você foi

**Você fez a única coisa que só você podia fazer, e fez rápido.** O Túlio e o Andrey
estavam travados — *"pior que alguém sabe ver isso daí?"*, *"pior que não"* — e em
menos de um minuto você enquadrou: *"isso aqui vai ser com alguém de SRE. Eu dou uma
mensagem no Márcio para dar uma olhada para nós."* É o mesmo movimento de 03/08, com
o Firebase: quando o bloqueio é acesso que ninguém do time tem, você vai buscar fora
em vez de deixar o time tentar.

**E delegou a verificação sem esperar.** *"Aí eu peço para você dar uma verificada
mesmo sem o Santi aqui."* Não travou a investigação na ausência dele.

**O que daria para fazer melhor, e são três coisas.**

**Você convocou força-tarefa de sábado e saiu.** *"Para que eu já volto aqui"* — e
não há registro de retorno. Pode ter voltado depois que a gravação parou; o que fica
registrado é a saída. Numa sessão de estreia do modelo novo, a presença de quem
propôs o modelo tem peso simbólico além do operacional.

**A sessão nasceu com dependência de quem não estava.** A contingência do OTP —
desativar o flag — exigia o Santi, que tinha avisado que entraria mais tarde. Vale
como regra: força-tarefa de sábado precisa confirmar antes quem tem a chave do que
provavelmente vai travar.

**E a lacuna do modelo apareceu no primeiro dia.** Ver abaixo.

## Pontos de atenção

- **A regra de troca entre as frentes faltou logo na estreia.** O [[Lucas Gomes]]
  estava online e o time precisou dele. O Túlio: *"o Lucas tá online hoje, ele ia
  entrar com a gente... mas a sala foi criada sem ele. Será que o Júnior combinou com
  ele?"* E o Andrey: **"eu não sei se você tá falando com o pessoal do time de ataque
  ou se ele vai querer entrar aqui."** Mandaram o link e ele não entrou. É exatamente
  o "a definir" do desenho da divisão — quem decide quando alguém atravessa — e
  custou uma manhã de apoio no primeiro sábado.

- **Quatro horas e meia sem registro, por decisão.** A gravação foi interrompida.
  Somando com a retrospectiva de 07/08 e a sessão do Team Sword, o vault não tem
  registro nenhum do que as duas frentes fizeram no primeiro fim de semana do modelo.

- **O bug de bloqueio virando cancelamento é o segundo caso e não tem como ser
  testado.** Três pessoas tentaram criar cartão de teste e nenhuma conseguiu. Isso
  vira dívida: sem cenário reproduzível, cada caso novo é tratado individualmente e a
  causa nunca sai. É a mesma classe de problema que o desbloqueio de cartão da semana
  passada, e vale checar se não é a mesma raiz.

- **O que foi reportado à diretoria como resolvido tem parente vivo.** O
  [[Report à Diretoria — Niky e Operação WL]] fechou o desbloqueio de cartão como
  resolvido em 05/08. Este é outro caminho do mesmo fluxo — bloquear em vez de
  desbloquear — e está aberto. Se voltar como recorrência, vale antecipar no próximo
  report em vez de deixar chegar pelo cliente.

- **O board do Helper estourou na sexta.** O Andrey: *"o board aqui do Helper estourou
  de caso da Niky ontem"*. É a mesma pessoa que na daily de sexta disse *"eu nem olho
  mais backlog"*.

- **Segundo sábado seguido de trabalho.** O tombamento foi em 02/08 e a força-tarefa
  em 08/08. Vale acompanhar, principalmente para o Túlio, que carregou esta manhã
  praticamente sozinho.

- **Uma pergunta de segurança que ficou implícita:** o OTP está **desativado** no
  Interfaces. Foi assim que o Túlio descobriu que aquele ambiente entrava direto. Se é
  configuração intencional, tudo bem; se sobrou de algum teste, é controle de
  autenticação desligado em produção.

- **Ruído de transcrição:** "Sand Grip", "C de gripe" e "sended" são o **SendGrid**;
  "ATP" e "TP" são **OTP**; "Nick" é Niky; "Fisk", "FCIS", "Francisc" e "fascista" são
  **FACISC**; "Sand"/"S" é o [[Gabriel Santi]]; "Lana" é a [[Alana Barbosa]];
  "Caroline"/"Co Caroline" é a [[Carol — Líder CS]].
