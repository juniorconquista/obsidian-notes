---
data: 2026-07-30
hora: "noite"
reuniao: "Migração de Valores — Bags Duplicadas"
tags: [reuniao]
participantes: [Junior Oliveira, Paulo Coleta, Gabriel Santi]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "WhatsApp — conversa com Paulo Coleta e grupo Bags Duplicadas"
tipo_fonte: whatsapp
doc_id: ""
---

# Migração de Valores — Bags Duplicadas | 30/07/2026

> [!warning] Esta call não tem transcrição
> Sala avulsa `meet.google.com/ykf-uped-cay`, na quinta à noite, **até
> meia-noite**. Não existe transcrição no Drive nem em disco — provavelmente
> não foi ativada, ou ficou no Drive de quem ativou. Esta nota foi montada em
> 04/08 a partir das conversas de WhatsApp com o Paulo Coleta e do grupo "Bags
> Duplicadas". É o único registro que existe da call, e o único elo entre a
> migração desenhada em 15/07 e as correções de 03 e 04/08.

## Contexto

Call noturna de emergência sobre a **migração de valores que rodou antes do
tombamento da Niky**. A migração deu erro e o time encontrou **bags
duplicadas** — o mesmo tema desenhado em
[[2026-07-15 — Reunião Tombamento Niky — Migração Saldo|Reunião Tombamento Niky — Migração Saldo — 15-07-2026]], onde ficou
registrado que os saldos *"precisam sair da DOC, passar por conta da Niky e
entrar na Swap distribuídos nas bags corretas"*.

Você acompanhou **da estrada**, com a conexão caindo o tempo todo. O
[[Gabriel Santi]] passou o caminho de query correto. O Paulo Coleta estava do
outro lado, gerando a base.

O tombamento aconteceu no sábado seguinte, 01/08.

## Decisões tomadas

- **A duplicidade veio do caminho errado de extração.** O Coleta confirmou na
  manhã seguinte que o caminho de query do Santi retornou os dados no formato
  necessário, e admitiu o custo: *"comemos mosca quando geramos a primeira base,
  que fizemos por um outro caminho e caímos na duplicidade. Se tivéssemos pedido
  ao Santi no momento zero teria dado certo em horário comercial"*.
- **A causa provável do lado de vocês é webhook duplicado.** Sua leitura na
  manhã seguinte: *"parece que está chegando webhook duplicado aqui, estamos
  tratando isso e vamos ver uma forma de evitar"*. **Essa causa segue aberta.**
- **Foram identificados 5 account holders da Niky com bag duplicada** nessa
  call. São exatamente os 5 que o Bruno reencontrou hoje.

**Desdobramento em 04/08 — a correção**

- O [[Bruno Conti]] **ajustou um script que já existia em benefícios** para
  tratar bags duplicadas, criou o grupo "Bags Duplicadas" e rodou em alguns AH
  da FACISC como teste.
- **Dimensão do problema, medida por ele:** ~**60 account holders na FACISC**
  com mais de uma bag ativa por trilha, e **5 na Niky**.
- **Você autorizou rodar para todos.** O Bruno começou pela Niky, por serem
  poucos, para validar antes de aplicar na FACISC.
- Você incluiu o Coleta no grupo para dar contexto, já que ele estava ciente do
  problema desde a call.

## Próximos passos

- [ ] Rodar o script de bags duplicadas na Niky (5 AH) para validar — Bruno — 04/08, em andamento
- [ ] Rodar na FACISC (~60 AH) depois da validação — Bruno — 04/08
- [ ] **Tratar o webhook duplicado na origem** — time — sem prazo, e é a causa, não o sintoma
- [ ] Levar "bags duplicadas / webhook duplicado" como item nº 1 do dev temporário de causa raiz — Junior — sem prazo
- [ ] Incluir esta call na lição aprendida do tombamento — Junior — você disse na call com a Priscila que queria mapear isso

## Como você foi

**A fonte não permite avaliar a condução da call** — não há transcrição, só as
mensagens do dia seguinte. O que dá para registrar, a partir do que sobrou:

**Você acompanhou uma call crítica de dentro de um carro, caindo o tempo todo.**
Sua própria frase: *"eu tentei acompanhar o possível na estrada, mas tava caindo
toda hora"*. A call foi até meia-noite e resolveu uma migração de valores na
véspera de um tombamento de 80 mil contas. Não havia como você não estar, mas
também não havia como você contribuir daquele lugar — e não há registro de
alguém ter assumido a condução formalmente na sua ausência efetiva.

**Você não pegou a saída fácil quando o Coleta se culpou.** Ele disse "comemos
mosca" e apontou o próprio erro de ter gerado a base por outro caminho. Você não
concordou nem absolveu — respondeu *"bom, mas bom que deu certo!"* e agradeceu a
ajuda. Considerando que o erro dele custou uma call até meia-noite, não cobrar no
dia seguinte é escolha, não descuido. Vale notar que na devolutiva do
[[Andrey Cunha]] em 31/07 o padrão apontado foi o inverso — absolver rápido demais
e tirar o peso da mão da pessoa. Aqui, com um par de outra área, o silêncio
funciona diferente.

**A autorização foi rápida e com o teste na ordem certa.** O Bruno pediu
confirmação às 11h39, você liberou às 12h02, e ele começou pela Niky com 5 casos
antes de tocar nos 60 da FACISC. Validar no menor volume primeiro é o
encaminhamento certo, e foi ele que propôs — você não atrapalhou.

## Pontos de atenção

- **A correção é limpeza de dados, não correção de causa.** É a **terceira
  limpeza da mesma classe de problema em cinco dias**: na quinta à noite nesta
  call, na war room de segunda (o Santi rodou query e removeu benefícios
  duplicados, ver [[2026-08-03 — Tombamento Niky|Tombamento Niky — 03-08-2026]]) e hoje com o script do
  Bruno. O webhook duplicado que você identificou como causa não foi tocado.
- **A FACISC tem doze vezes mais casos que a Niky** — 60 contra 5. E a FACISC é
  o cliente da sua meta 1C, que já não pode ser tombada até a distribuição de
  pedidos ser resolvida, conforme
  [[2026-08-03 — Planning Sprint 15 — White Label|Planning Sprint 15 — White Label — 03-08-2026]].
- **Bag é o ponto de falha que atravessa os dois maiores clientes, com dois
  sintomas opostos:** aqui, bag duplicada; na planning de 03/08, dois usuários
  **sem** bag criada travando a distribuição de 400 pessoas. Mesmo domínio,
  falhas espelhadas.
- **É o exemplo concreto do que o Santi chamou de causa raiz histórica.** Na call
  de hoje ele disse: *"o maior problema que a gente tem hoje é de pedido de
  benefício. A gente mexe lá, arruma, mas continua dando problema"*. Este é o
  caso, com número: 65 account holders afetados.
- **E é o caso que sustenta o argumento da Priscila.** Ela disse hoje que *"o
  problema não é falta de teste, o problema é falta de um processo de
  desenvolvimento que trabalhe com segurança"*. Três limpezas em cinco dias sem
  tocar a origem é exatamente isso.
- **A lição do Coleta é barata e vale institucionalizar:** pedir o caminho de
  extração a quem conhece a base antes de gerar, não depois. Custou uma call até
  meia-noite na véspera do tombamento.
- **Esta call não tem transcrição e por pouco não teve registro nenhum.** Vale
  conferir se as salas avulsas noturnas estão com transcrição ativada por
  padrão — foi só porque você trouxe o WhatsApp que isso entrou no vault.
