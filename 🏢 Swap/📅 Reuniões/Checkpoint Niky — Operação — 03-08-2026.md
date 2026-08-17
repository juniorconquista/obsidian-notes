---
data: 2026-08-03
hora: "16:01"
reuniao: "Checkpoint Niky — Operação"
tags: [reuniao]
participantes: [Junior Oliveira, Thales Machado, Gabriel Santi, Túlio Cruz Ferreira da Silva, Luma Gomes Leonardo, Ricardo Etchenique, Renata Correia, Alyne Ribeiro, Vanessa Preite, Milka Braga Souza do Nascimento, Renan Dias]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "[Niky] Checkpoint diário operação  - 2026_08_03 16_01 GMT-03_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1gvZ6cRf6wlAmo_jH_wMUgeBe0NEMQF4cmXmFAme5_70"
---

# Checkpoint Niky — Operação | 03/08/2026

## Contexto

O primeiro checkpoint diário com o cliente depois do tombamento — 1h02m54s,
criado pela Luma Gomes Leonardo por causa do volume de tickets. Do lado da Swap:
Luma, Thales Machado, [[Gabriel Santi]], [[Túlio Cruz Ferreira da Silva]] e
você. Do lado da Niky: Ricardo Etchenique, Renata Correia e Alyne Ribeiro
(confirmados pelos e-mails `@niky.com.vc`), mais Vanessa Preite, Milka Braga e
Renan Dias, que entraram sem constar nos convidados e falam como operação do
cliente.

A Luma abriu explicando o desenho: *"as maiores volumes de tickets estão
vinculados ao portal white label"* — e por isso a sala é com o seu time. **Há
~400 tickets na fila.**

É esta a call que produz o tom da sessão de 17:04 do
[[Tombamento Niky — 03-08-2026]], onde o time sai dizendo *"que amass foi
esse?"*.

**Existe uma segunda sessão do mesmo checkpoint, às 18:53**, ainda não baixada.
Esta nota cobre só a de 16:01.

**Sobre a fonte:** é `Anotações do Gemini`, mas o export traz as observações
**e** a transcrição completa, então as falas abaixo são literais.

## Decisões tomadas

- **A recarga manual da Qualicorp foi autorizada na hora.** O Ricardo colocou o
  problema sem rodeio: precisa de uma recarga de "cento e poucos mil" hoje e
  outra de R$ 1,05 milhão em seguida, *"já escalou CFO, já escalou não sei
  quem"*, *"tá um negócio lá realmente insustentável"* e **"esse é o meu maior
  cliente hoje"**. O Thales perguntou se dava para fazer pelo portal
  administrativo, e você e o Santi confirmaram. Executada depois, na war room —
  R$ 202.543 em pedidos.
- **A lentidão da Qualicorp foi confirmada como real, não percepção do cliente.**
  A Luma já havia feito teste assistido antes da call. A Alyne: *"eles não
  conseguem fazer nenhuma movimentação, nem nós pelo portal administrativo. Só de
  entrar na conta da Qualicorp já trava o portal todo"*.
- **Teste acompanhado ficou combinado** — o cliente compartilha tela e faz o
  fluxo enquanto o time observa, para extrair o insight técnico do travamento.
- **A melhoria do lote de recarga está em desenvolvimento.** Hoje uma planilha de
  recarga falha inteira se um usuário não completou o onboarding ou o KYC. O
  Ricardo apontou que isso é inviável para cliente com alta rotatividade que
  recarrega todo dia. O Santi informou que já está sendo desenvolvido retermos
  apenas o crédito do usuário pendente, sem invalidar o lote.
- **A transferência de saldo entre alimentação e refeição não vai acontecer.**
  Limitação de regras de MCC, explicada pelo Thales à Alyne. Ficou de avaliar
  formas de unificar o uso.
- **A migração de saldo das contas antigas (NIC) para as novas (Swap) foi
  desenhada:** a Renata envia planilha com CNPJ e valores exatos, o procedimento
  precisa ser validado pelo Gison para controle contábil, e o Pix tem que ter
  valor exato — sem diferença de centavos.
- **Aprovação de cadastro de menores entra com prioridade**, com a exigência de
  nome completo da mãe e do vínculo, por diretriz do Banco Central.
- **Logística de cartões:** manuseio só em dia útil. Pedido feito depois das 8h
  de sexta só começa a processar na segunda. Ficou combinado centralizar os
  códigos de remessa no Thales para ele pedir prioridade — há **500 solicitações
  pendentes**.
- **A lista oficial de profissões vai virar planilha.** O Thales tentou
  compartilhar o link e nenhuma das quatro pessoas do cliente conseguiu acessar,
  mesmo com e-mail corporativo. Ele assumiu extrair e enviar em planilha para não
  travar o trabalho do dia.
- **Uma planilha unificada de status será criada** pelo Thales, com todos os
  casos e clientes, para servir de referência comum ao atendimento.
- **A configuração de TED foi resolvida ao vivo** — o Túlio demonstrou o caminho
  no portal de RH e o Santi esclareceu que a recorrência (mensal, semanal,
  esporádica) afeta só a geração de pedidos, não a autorização da transferência.
  Ficou registrado que o sistema tem **falhas de espelhamento** entre o portal
  administrativo e o acesso da empresa.

## Próximos passos

- [ ] Executar a recarga manual da Qualicorp — Junior e Santi — feito na noite do mesmo dia
- [ ] Enviar os dados da recarga da Qualicorp — Alyne Ribeiro — na call
- [ ] Enviar lista com 3 CNPJs para recarga via e-mail — Alyne Ribeiro
- [ ] Enviar planilha com CNPJ e valores exatos para migração de saldo — Renata Correia — validar com o Gison antes
- [ ] Investigar a falha de upload da planilha da Lojas Escala e validar os campos obrigatórios — Thales Machado
- [ ] Criar a planilha consolidada de status de cadastros e biometrias — Thales Machado
- [ ] Enviar a lista oficial de profissões em planilha — Thales Machado — hoje, para não travar o cliente
- [ ] Enviar CPF e data do cadastro manual que falhou, para análise de log — Milka Braga
- [ ] Enviar códigos de remessa das 500 entregas pendentes e pedir priorização — Renata Correia e Thales
- [ ] Verificar o status de entrega dos cartões da Bionexo — Thales Machado
- [ ] Avaliar a possibilidade técnica de unificar uso dos saldos de alimentação e refeição — Thales Machado
- [ ] Elaborar dossiê de tickets e padrões de erro recorrentes — Luma Gomes Leonardo — até o fim do dia
- [ ] Enviar a ata do checkpoint — Luma Gomes Leonardo
- [ ] Priorizar as demandas de Pix — Luma Gomes Leonardo — pedido explícito da Renata

## Como você foi

**Você falou duas vezes em uma hora e três minutos.** As duas falas inteiras:
*"S tá aqui"* e *"acho que a gente consegue sim"*. O Thales falou 251 vezes, a
Renata 161, o Ricardo 99, o Santi 46, o Túlio 7.

Não é um número que se interpreta sozinho, então vale separar o que ele
significa e o que não significa.

**O que não significa:** a call não era sua. Foi criada pela Luma, do CSO, para
triagem de tickets, e o Thales tem a relação com o cliente e a visão transversal
entre banking, riscos e logística — a maior parte da pauta não era de interface.
Ficar calado enquanto o especialista certo responde é acerto, não covardia. E
quando a pergunta foi sua, você respondeu na hora e resolveu: o Thales perguntou
se dava para fazer a recarga pelo portal e você confirmou sem hesitar,
autorizando um desbloqueio de R$ 1 milhão para o maior cliente da Niky.

**O que significa.** Na sala em que o cliente disse *"já escalou CFO"*,
*"insustentável"* e *"esse é o meu maior cliente"*, sobre um produto que é seu, o
gestor da área disse duas frases. Quem respondeu pelo White Label foi alguém de
fora do seu time. E a sua própria leitura, uma hora depois, entrega o que você
achou disso:

> *"Ainda bem que o T estava lá para dar uma apanhada por nós."*

E depois, brincando: *"na próxima nós vamos revesar, nós vai sortear quem que
vai"*. O Túlio no mesmo trecho: *"eu fiquei até com medo de falar. Falei: 'St
fala você, pelo amor de Deus, eu não vou falar não'"*. O time inteiro se
silenciou, e você tratou isso como sorte, não como problema.

**O que faltou não era discurso técnico, era enquadramento.** Ninguém disse ao
cliente, naquela sala, três coisas que o seu time já sabia às 12h42:

1. que a causa raiz da falha de primeiro acesso **tinha sido encontrada e
   corrigida**, com 242 usuários já destravados;
2. que parte dos prints que eles mandam é de **outro aplicativo** — o `Nick
   Benefícios`, antigo, deles mesmos, ainda na loja;
3. que a lentidão da Qualicorp tem causa identificada e não é infra.

Essas três frases mudam a temperatura de uma sala com 400 tickets na fila. Quem
tinha as três era você e o Santi. A primeira nem apareceu na call.

**Sobre divergência:** não houve nenhuma dirigida a você — não havia como haver,
com duas falas. O atrito real foi o Ricardo pressionando por prazo e o Thales
absorvendo.

## Pontos de atenção

- **O cliente escalou ao CFO dele.** Isso muda o patamar: não é mais atrito de
  operação, é assunto de diretoria do outro lado. E o Ury já havia cobrado
  satisfação de cliente na review de 31/07 — a mesma pressão está vindo pelos
  dois lados agora.
- **400 tickets na fila e a Renata dizendo que o time não consegue mapear todos**
  com a tempestividade necessária, porque exige tratativa caso a caso.
- **O fluxo de recarga em lote é incompatível com o negócio do cliente.** Falhar
  o lote inteiro por causa de um KYC pendente é inviável para quem tem alta
  rotatividade e recarrega diariamente. A correção está em desenvolvimento, sem
  prazo dito na call.
- **Falha de espelhamento entre o portal administrativo e o acesso da empresa** —
  reconhecida na call como algo que "precisa ser contornado". Contornar não é
  corrigir.
- **Campos obrigatórios que o negócio não precisa.** A Milka relatou que
  `capacidade financeira` e `profissão` travam o cadastro em massa das Lojas
  Escala e Plural e não são necessários para a operação deles. É o mesmo tema que
  o [[Regis Graf]] corrigiu na semana anterior e que só chegou à branch da Niky
  na war room da noite.
- **A lista de profissões não é acessível ao cliente.** Quatro pessoas tentaram e
  nenhuma conseguiu abrir o link, com e-mail corporativo. Sinal de permissão mal
  desenhada, não de erro pontual.
- **Existe uma segunda sessão deste checkpoint às 18:53** que ainda não foi
  baixada. Como este é o rito diário que passa a governar a relação com o
  cliente, vale ter a série completa.
- **Ruído de transcrição:** "Policorpio"/"Calicó" é Qualicorp, "SUAP" é Swap,
  "NIC"/"Nick" é Niky, "insite" é insight, "Aline" é Alyne, "Sant"/"S" é
  [[Gabriel Santi]], e "1.Hão50" é R$ 1,05 milhão.
