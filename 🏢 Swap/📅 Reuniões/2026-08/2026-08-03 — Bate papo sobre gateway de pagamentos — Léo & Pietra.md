---
data: 2026-08-03
hora: "17:30"
reuniao: "Bate papo sobre gateway de pagamentos — Léo & Pietra"
tags: [reuniao]
participantes: [Junior Oliveira, Pietra Oliveira, Leonardo Herbert Gonçalves]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Bate papo sobre gateway de pagamentos - 2026_08_03 17_30 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1sLLRbAGXjoPvLHxiNh-a_ugZwpxcFQ0ByG8hy4qJNH8"
---

# Bate papo sobre gateway de pagamentos — Léo & Pietra | 03/08/2026

## Contexto

Consultoria técnica de 20min22s que **você marcou e da qual saiu nos primeiros
dois minutos.** A [[Pietra Oliveira]] estava travada numa dúvida sobre gateway
de pagamentos no marketplace e você mobilizou o Leonardo Herbert Gonçalves, da
Raro (`leonardo@rarolabs.com.br`), que já implementou exatamente esse fluxo no
banco BMG.

Suas 14 falas estão todas na abertura. Você apresentou os dois, enquadrou o
assunto e entregou: *"eu não vou conseguir acompanhar vocês que eu tô resolvendo
uns problemas da Nick aqui com os meninos, mas aí a Pietra tá com boas mãos,
depois eu pego o resumo aqui"*. Saiu para a war room do
[[2026-08-03 — Tombamento Niky|Tombamento Niky — 03-08-2026]].

**Esta call responde a pergunta que ficou aberta sobre o Comitê de Produtos de
ontem:** o tema do gateway foi levado por ela ao comitê no mesmo dia, e o comitê
também ficou em dúvida. É por isso que ela buscou o Léo.

**Sobre a fonte:** é `Anotações do Gemini`, mas o export traz a transcrição
completa, então as falas são literais.

## Decisões tomadas

- **Não é preciso contratar gateway de pagamentos.** É a conclusão da call, e ela
  fecha a dúvida. Os fornecedores de gift card — Blackhawk, Incon e EPI —
  pediram um gateway porque aplicaram o modelo padrão de e-commerce, em que o
  usuário digita cartão no checkout. No fluxo da Swap o débito acontece
  **internamente**, no saldo do colaborador. O Léo, direto: *"no final das
  contas, o gate de pagamento vai ser a própria SUAP"*.
- **A Pietra vai voltar aos fornecedores para explicar o modelo.** A recomendação
  do Léo é explicitar que a Swap é instituição financeira, que debita
  internamente e devolve ao fornecedor uma confirmação de sucesso da transação —
  o que dispensa o gateway. Ele avisou o que esperar: *"talvez um ou outro fale
  'a gente não trabalha assim', beleza, vai descartar. Mas vários deles com
  certeza vai trabalhar"*.
- **A tela do marketplace fica na Swap**, não no fornecedor. Confirmado pela
  Pietra e é o que torna o desenho acima possível.
- **A Lomadi entra como alternativa de fornecedor a avaliar.** O Léo usou essa
  plataforma no BMG para a loja virtual dentro do app, com o mesmo fluxo de
  débito interno (lá era fatura de cartão, com webhook de ida e volta).
- **O critério de escolha ficou definido pela Pietra:** ponderar a rentabilidade
  oferecida — o rebate, o percentual de cada fornecedor — contra o grau de
  esforço técnico de integração.
- **A EPI é a mais promissora das três**, na leitura do Léo, porque as parcerias
  dela já são com instituições bancárias.
- O Léo se colocou à disposição para participar das conversas com os fornecedores
  se for útil.

## Próximos passos

- [ ] Voltar aos fornecedores de gift card explicando que a Swap é o próprio gateway e o débito é no saldo do colaborador — Pietra — sem prazo
- [ ] Avaliar a Lomadi como alternativa de fornecedor — Pietra
- [ ] Consultar o diretor Irinandi sobre o histórico da parceria com a Lomadi na época dele no BMG — Pietra
- [ ] Consolidar a análise de rentabilidade × esforço técnico de integração por fornecedor — Pietra

## Como você foi

**Você não estava nesta call para resolver o problema, e agiu como tal.** Dois
minutos: cumprimentou, contextualizou a dúvida, apresentou as duas pessoas,
disse que a Pietra estava em boas mãos e saiu para o incidente. É delegação
limpa — e é o oposto do que a maioria faria numa dúvida técnica sobre o próprio
produto, que é ficar e assistir.

**E o valor que você entregou aqui foi anterior à call.** A Pietra estava
travada num tema que ela mesma admitiu não dominar — *"eu não entendo muito
dessa parte de gateway de pagamentos, nunca trabalhei com isso e eu fiquei de
certa forma vendida que levei no comitê"* — e o comitê também não resolveu. Você
achou, na sua rede na Raro, alguém que já tinha implementado exatamente esse
fluxo num banco, e marcou a agenda. Vinte minutos depois a dúvida estava
encerrada. Conectar a pessoa certa é uma forma de trabalho que não aparece em
nenhum board.

**O que vale observar, e não é crítica à condução:** você abriu a call desabafando
sobre o dia — *"nós nunca apanhamos tanto na vida"*, *"o Paulo tocou muita coisa
e a gente ficou meio que apartado, então a gente ficou meio vendido e algumas
perguntas a gente não sabia responder, foi bem ruim, mas ainda bem que o Thales
estava lá e deu uma boa blindada na gente"*. É o mesmo diagnóstico que você
faria meia hora depois na war room, dito aqui primeiro, para a sua PM. Não há
nada de errado nisso — ela é par, o desabafo foi curto e ela respondeu no mesmo
tom. Registro porque mostra que a leitura do problema estava formada **antes**
da war room, e ainda assim o repasse com o Paulo saiu do dia sem data.

**Sobre divergência:** não houve, e não havia como haver — você saiu antes do
conteúdo começar.

## Pontos de atenção

- **O comitê de produtos não resolveu a dúvida que era dele para resolver.** A
  Pietra levou o tema ao comitê no mesmo dia e a resposta veio de um contato
  externo, de graça, em vinte minutos. Vale entender se foi falta de repertório na
  sala ou falta de preparo da pauta — porque o marketplace é uma frente aprovada
  em comitê e vai voltar lá.
- **O marketplace saiu das metas mas continua consumindo a Pietra.** Ele foi
  trocado pelo WL 2.0 na proposta ao Doug, e segue no roadmap dela — como já
  estava registrado em [[2026-07-27 — Feedback semestral — Pietra|Feedback semestral — Pietra — 27-07-2026]], somando à
  carga do segundo semestre dela.
- **A Pietra assumiu duas vezes na call que ficou "vendida"** por não dominar o
  tema. Ela tratou com naturalidade e resolveu buscando ajuda, o que é o
  comportamento certo. Mas é a segunda frente em que ela está sozinha num assunto
  novo — vale lembrar do que a devolutiva dela de 27/07 já apontava sobre carga.
- **O Thales já estava desgastado antes de ontem.** A Pietra: *"ele já tava meio
  estressado já na semana passada, viu? Que viu umas mensagens que eles trocaram
  ali com o Danilo também"*. E foi ele que segurou a call com o cliente às 16:00.
  Vale olhar — é a segunda pessoa fora do seu time carregando peso do seu
  produto.
- **Nomes a confirmar:** "Blackhk" é provavelmente a Blackhawk, e "Nash" na fala
  do Léo é provavelmente o Nubank. O diretor citado é o Irinandi, e o Freire era
  o diretor de TI do BMG que levou a Lomadi.
