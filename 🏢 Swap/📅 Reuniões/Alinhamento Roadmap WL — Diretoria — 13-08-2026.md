---
data: 2026-08-13
hora: "16:00"
reuniao: "Alinhamento Roadmap WL — Diretoria"
tags: [reuniao]
participantes: [Junior Oliveira, Rodrigo Sol, Ury Rappaport, Gabriel Santi, Paulo Coleta, Stive Tormes, Lucas Ferreira da Silva, Leonardo Herbert Gonçalves, Pietra Oliveira]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Alinhamento - Roadmap WL - 2026_08_13 16_00 GMT-03_00 - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1jsZFZUzTwRVJQT7wfUgMKlajNYc7gAjj2tzH7zo_7cU"
---

# Alinhamento Roadmap WL — Diretoria | 13/08/2026

## Contexto

**Quase duas horas.** Formato híbrido: você, o **Sol**, o **Ury**, o
[[Gabriel Santi]], o **Coleta**, o [[Stive Tormes]] e o **Lucas Ferreira** numa
sala em São Paulo; o **Léo** e a [[Pietra Oliveira]] remotos.

É a call que você preparou em [[Roteiro Roadmap WL — Ury — 13-08-2026]], depois
da manhã com o Léo e o Santi em
[[Estrutura de contas RTF e CCLG — Léo e Santi — 13-08-2026]] e do compromisso
que o Sol assumiu em [[Conversa com Wagner — Bee Benefícios — 12-08-2026]].

A pergunta que o Ury pôs na mesa e que organizou tudo: **qual é o caminho mais
rápido para matar a V1?**

> ⚠️ **Atribuição da transcrição — pior que a de sempre.** Sete pessoas na mesma
> sala, dois notebooks abertos. O áudio da sala entrou pelo **PC do Lucas
> Ferreira**, então o canal **"Luis Ferreira" (899 falas) não é o Lucas falando
> — é a sala inteira**: Ury, Sol, Coleta, Santi e Stive misturados. O seu canal
> (517 falas) pegou o resto, e **boa parte do que está nele não é sua** — o
> trecho de conta garantia e Treasury é do Coleta, o de banco de dados amarrado
> a despesas é do Santi ou do Stive. Só o **Léo** e a **Pietra**, que estavam
> remotos, têm fala confiável. Atribuí abaixo pelo conteúdo, não pelo rótulo.

## Decisões tomadas

**1. A ordem inverteu: CCLG primeiro, RTF por último.**

Esta é a decisão da reunião, e ela vira de cabeça para baixo o que o time está
construindo. O raciocínio do Ury:

> *"Para matar a V1 a gente tem que ligar o CCLG, porque todo mundo consome o
> CCLG hoje na V1. Se a gente entrega o CCLG no white label com as features
> mínimas que ele já tem hoje, a gente pelo menos mata a V1 e para de dar
> manutenção nessa bosta de software."*

E o corolário, dito por ele sem meias palavras: *"estar perto de entregar o RTF
não contribui com o propósito de matar."*

**Quem fechou a confusão foi você**, e em uma frase:
*"Para matar a V1 a gente tem que fazer a V2 com CCLG e não com RTF."*

**2. A data de 04/09 foi descartada.** Era a entrega do RTF. Ficou explícito na
sala que *"esse quatro aqui não dá para considerar mesmo"*. O RTF passa a ser o
**último** marco — você mesmo: *"o último milestone vai ser o RTF depois de
tudo"*, e o híbrido de RTF fica para **dezembro**.

**3. Os marcos, na ordem:**

| Ordem | Entrega | Data |
|---|---|---|
| 1 | **Morte da V1** — WL 2.0 em CCLG com as features mínimas do legado | setembro/outubro |
| 2 | **Os 65 itens da FACISC**, inclusive relatórios | outubro |
| 3 | **V2 nova** — consignado, marketplace, multiproduto (benefício + gasto corporativo) | outubro |
| 4 | **RTF / híbrido** | dezembro |

> ⚠️ **A data do marco 1 não fechou.** O Léo defendeu tombar a V1 como ela está
> hoje, **sem nenhum item FACISC**, para trazer a entrega para setembro, e fazer
> os 65 itens em outubro logo em seguida. A sala oscilou e o Léo teve que
> perguntar duas vezes *"como ficou as datas da V1, V1 nova e da V2?"*. A
> resposta que ficou gravada foi "outubro e dezembro", com você puxando a V2
> para outubro. **Confirme isso antes de levar ao comitê.**

**4. Novembro morreu, e você matou.** *"V2 em novembro era impossível depois de
tudo que a gente falou aqui."* A promessa anterior do comitê caiu na própria
reunião.

**5. Vai ter time separado, e não pode ser a mesma gente.** O Léo cravou a
condição:

> *"Se for para continuar do jeito que tá, mesmo time, mesmas pessoas tocando,
> não vai chegar. Se a gente não fizer nada de diferente do que faz hoje, é só
> mais uma data que a gente vai dar aqui."*

E foi específico: se as mesmas pessoas seguirem olhando ticket de FACISC e Niky,
não chega. Você respondeu que vai segregar.

**6. Não vai ter V3 do zero.** O Ury chegou dizendo que *"a decisão de fazer do
zero bem feito está tomada"*. Você discordou com argumento — *"não vejo
necessidade de uma V3 agora; pega o que a gente tem nesse code base e começa a
migrar por partes"* — e o Léo convergiu: *"fazer a V3 usando tudo da V2 que já
está pronto para modular; não precisa codar tudo do zero"*. **Fechou em
refatorar a V2 para modular, não em recomeçar.**

**7. O plano vai ao comitê na segunda.** Você segurou governança contra a
pressa: *"tem um processo para isso, que é o comitê extraordinário; não é
questão de precisar, é questão de não perder a governança"*. A Pietra formaliza,
você leva.

## Próximos passos

- [ ] Consolidar o plano com roadmap repriorizado e levar ao comitê de priorização — Pietra e Léo consolidam, Junior leva — segunda, 17/08
- [ ] Definir a composição dos times: quem sai para a frente nova, quem entra para o dia a dia — Junior — segunda
- [ ] Confirmar a data do marco 1: setembro sem itens FACISC (proposta do Léo) ou outubro com os 65 — Junior — antes do comitê
- [ ] Levantar os cronogramas dos clientes que vão usar o WL: quando cada um precisa entrar em operação e em qual versão — Ury pediu, **sem dono** — em aberto
- [ ] Destravar as deliberações de compliance do RTF — Pietra sinalizou, **sem dono** — em aberto
- [ ] Mapear o impacto da hipótese "tudo vira RTF" antes de fechar o desenho de arquitetura — Junior/Santi — sem data
- [ ] Fechar o escopo de relatórios da FACISC com o time de dados — Léo levantou — sem dono

## Como você foi

**A clarificação mais importante da call foi sua, e coube numa frase.** A sala
passou quarenta minutos redescobrindo a diferença entre CCLG e RTF. Quando a
discussão finalmente chegou no que fazer, foi você quem amarrou: *"para matar a
V1 a gente tem que fazer a V2 com CCLG e não com RTF"*. Isso é o que virou a
ordem de prioridade da reunião inteira.

**Você segurou governança contra o dono da pressa.** O Ury queria sair da sala
executando. Você insistiu no comitê extraordinário e explicou por quê: *"não
quero fazer um compromisso que não vai ser cumprido. Preciso saber quem são as
pessoas, quando começam e o que cada um vai fazer, antes de falar 'vou te
entregar' — e eu fiz o compromisso com o Wagner lá."* É uma posição impopular
numa sala com diretoria querendo velocidade, e você a sustentou com o motivo
certo.

**Você foi o único que separou entrega de migração.** *"Entrega é uma coisa, a
migração dos caras é outra. Migrar dá trabalho e tem que ser bem feito, senão a
sustentação da transição dá trabalho."* Todo mundo estava falando de data de
entrega. Essa distinção é justamente a que costuma explodir tombamento — e ela
só entrou porque você pôs.

**E você matou uma data ruim em público.** Dizer *"V2 em novembro era
impossível"* na frente do Sol e do Ury custa no momento e paga depois. É o
oposto da compressão de trimestre que você fez em 03/08.

### O que ficou para trás

**A pergunta mais importante do seu roteiro não foi feita.** Você tinha escrito
que a pergunta 3 — quais contratos estão em venda, para quando, em qual modelo —
era *"a mais importante da reunião"*. Ela nunca saiu. Ironicamente foi o **Ury**
quem puxou o assunto (*"tem os cronogramas dos clientes que vão usar o white
label? entra numa sala e pega os cronogramas"*) — mas como tarefa para alguém,
sem dono, e dissolveu. **Você saiu sem a informação comercial que deveria
ordenar o roadmap.**

**Você não abriu com o item de 03/08.** O roteiro começava devolvendo o pedido
do Ury sobre Febraban e CONARH. A call foi sequestrada pela discussão de ledger
nos primeiros quarenta minutos e você nunca retomou o enquadramento. O item
segue aberto desde 03/08.

**O argumento dos 10% não foi usado.** Você o preparou como peça central e tinha
a resposta pronta da manhã. A sala refez a derivação do zero, com o Coleta
explicando conta garantia e Treasury. A decisão que saiu é compatível com a sua,
mas foi alcançada pelo caminho longo — e o argumento comercial que você tinha (o
tombamento sem migração de estrutura) não chegou a ser dito.

**As datas fecharam frouxas.** O Léo teve que perguntar duas vezes, e a resposta
oscilou entre outubro e dezembro. Você era a pessoa natural para fechar isso, e
saiu da sala sem número firme para levar ao comitê em três dias.

## Pontos de atenção

- **O time ainda não sabe que a ordem virou.** Está construindo RTF com data de
  04/09 — data que foi descartada na sala. Na segunda o time descobre que a
  prioridade é CCLG. **Isso precisa ser comunicado por você, com o motivo, antes
  de virar boato.** O [[Stive Tormes]] alertou em 12/08 exatamente que o 2.0 em
  RTF não atenderia a FACISC; a decisão dá razão a ele e vale dizer isso.

- **Apareceu uma trava de compliance no RTF e ninguém pegou.** A Pietra:
  *"a gente tá com algumas deliberações do compliance para o RTF e isso tá um
  pouco travado — eu acho que o Ury sabe"*. Ninguém respondeu. Ficou sem dono
  numa sala que tinha o Ury dentro. Agora que o RTF foi para dezembro isso
  parece menor, mas é o tipo de item que reaparece em novembro.

- **A V2 não tem desenho de arquitetura documentado.** Saiu na sala, e é grave:
  *"não tem um desenho de arquitetura, de infraestrutura da aplicação. Não tem o
  mapa de como está montado. Geralmente a primeira coisa que a gente faz num
  sistema é desenhar a arquitetura dele — a gente não tem isso, não
  documentou."* O artefato que você montou hoje cobre a camada de modelo de
  conta; **o buraco é bem maior que isso.**

- **A hipótese "tudo é RTF" ficou aberta e mexe direto no seu desenho.** A
  provocação: se o CCLG é um RTF com a regra 100% cheia, bastaria uma
  configuração. A resposta da sala foi *"conceitualmente pode ser, mas não é do
  jeito que a gente implementou — foi feito quase como um `if`"*, e que dá para
  ter um backend onde tudo é RTF, mas exige **mapeamento de impacto**. Se isso
  for verdade, a sua camada de adapters encolhe muito. **Vale medir antes de
  cravar o desenho.**

- **O RTF não fala com banking.** *"A gente ainda não tem a funcionalidade de
  RTF para banking."* Não existe Pix nem TED em RTF hoje — a Treasury some
  nesse fluxo. Cliente em RTF que precise disso não é atendido. Não foi tratado
  como risco na sala; deveria estar no desenho de dezembro.

- **A FACISC pediu o básico antes das novidades.** O Léo trouxe: *"antes de
  olhar os 65 itens novos, o básico bem feito — o que tem hoje funcionar"*.
  Bate com o que o Wagner falou em 12/08. **Isso é argumento a favor da proposta
  do Léo** de tombar em setembro sem os 65 itens — e você não usou.

- **Você ganhou escopo estrutural nessa call.** O Ury defendeu que o time de
  interfaces seja o dono da interface com o cliente, não só da interface
  gráfica: *"a camada de comunicação com o cliente é via interface — é time de
  interface com cliente"*, com BFF reempacotando as APIs. Você discutiu isso com
  o Coleta e o Léo, e o Léo reforçou: *"quem toma porrada dos clientes é a
  interface"*. **Isso amplia o seu time e o seu mandato.** Ainda não está
  formalizado em lugar nenhum — vale registrar antes que evapore.

- **Ruído de transcrição:** "Luis Ferreira" é o canal da sala inteira, captado
  pelo PC do Lucas Ferreira — não é ele falando;
  "Rodrigo" e "Rodriguez" são o **Sol**; "Uri" é o **Ury**; "Juninho"/"Junin" é
  você; "FCIS"/"fascis"/"Francisco"/"faisk" é a **FACISC**; "Nick" é a **Niky**;
  "B1"/"B2"/"veu"/"verão" são **V1** e **V2**; "SLG"/"CSLG"/"CCG"/"7G" são
  **CCLG**; "RDF"/"ETF" é **RTF**; "STK" é **SDK**; "PMA"/"VMA"/"TMA" é a
  **PMA**; "coleta" é o **Paulo Coleta**; "Chif"/"Steve" é o
  [[Stive Tormes]]; "Sant" é o [[Gabriel Santi]]; "Pietro"/"Preta"/"P" é a
  [[Pietra Oliveira]]; "Doug" é o Doug.
