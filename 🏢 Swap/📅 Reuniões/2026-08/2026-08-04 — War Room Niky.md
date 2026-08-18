---
data: 2026-08-04
hora: "10:44"
reuniao: "War Room Niky"
tags: [reuniao]
participantes: [Junior Oliveira, Túlio Cruz Ferreira da Silva, Stive Tormes, Luma Gomes Leonardo, Gabriel Santi, Thales Machado, Lucas Gomes, Andrey Cunha, Luiz Lauxen, Joselito Rend, Kelly Almeida, Bruno Conti, Alana Barbosa, Taillon Neves, Dheyson Silva]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Niky - 2026_08_04 09_44 GMT-04_00 - Anotações do Gemini.docx"
tipo_fonte: anotacoes-gemini
doc_id: "1JXEj6J1xDfY_WMxdvslcmrJLXrSbxxX5rOfHpLlxB7g"
---

# War Room Niky | 04/08/2026

## Contexto

A sala aberta o dia inteiro, segundo dia de contenção depois do tombamento:
**7h29m57s de call**, das ~10:44 às ~18:15. Continuação de
[[2026-08-03 — Tombamento Niky|Tombamento Niky — 03-08-2026]].

Quem falou, por volume: [[Túlio Cruz Ferreira da Silva]] (969),
[[Stive Tormes]] (696), Luma Gomes Leonardo (682), [[Gabriel Santi]] (532),
Thales Machado (277), **você (269)**, [[Lucas Gomes]] (82),
[[Andrey Cunha]] (42) e Luiz Lauxen (37).

Convidados que não falaram: Joselito Rend, Kelly Almeida, [[Bruno Conti]],
[[Alana Barbosa]], Taillon Neves e Dheyson Silva. Luma, Thales, Andrey e o
Lauxen falaram sem constar no convite — a lista segue não representando a sala.

No meio dela você fez outras duas coisas: a conversa com a Priscila às 11:20 e o
[[2026-08-04 — Checkpoint Niky — Operação|Checkpoint Niky — Operação — 04-08-2026]] às 16:00, além de um alinhamento com
o Léo no fim do dia. Isso aparece na transcrição: você entra e sai, avisa que
acabou de chegar, atende telefone e repete uma pergunta que já tinha sido
respondida.

**Sobre a fonte:** é `Anotações do Gemini`, com a transcrição completa embutida
depois das observações — 4.691 linhas. Por isso a análise de condução é possível.

**A sala teve uma sessão anterior vazia**, às 10:33, com 28min20s de você sozinho
esperando o pessoal — nenhuma fala capturada. Baixada e verificada em 05/08, não
gerou nota.

## Decisões tomadas

**Lentidão do portal — resolvida e devolvida**

- A causa que você já tinha nomeado ontem: o select carrega **26 mil pessoas de
  uma vez** numa empresa grande da Niky e a tela travava.
- A correção foi a que você desenhou: **campo de busca dentro do select, limite
  de ~50 itens em tela** e o resto por filtro. *"Não faz sentido algum a gente
  trazer 26.000 usuários e querer que o usuário role até o final para ele
  encontrar a pessoa que tem o nome com a letra Z"*.
- **Você pediu um checkbox de "selecionar todos"** resolvido no backend, pensando
  em quem opera: senão a pessoa que quer mandar para todos vai ter que clicar um
  por um. O Santi implementou e validou com 500 usuários local.
- O Santi subiu, a **Luma validou** e confirmou que busca e seleção normalizaram.
- Ressalva registrada: volume muito alto ainda dá **timeout**. A orientação ao
  cliente é fracionar em lotes menores, e a Luma já alinhou com eles que lentidão
  em 10 mil usuários selecionados não é erro de portal.
- **Contorno enquanto não subia:** o Santi ensinou o caminho de importar planilha
  de valores e criar o pedido direto, sem carregar a lista na interface.

**Primeiro acesso — o problema que não fecha**

- Três hipóteses foram testadas e nenhuma reproduziu o erro.
- **Decisão sua, e é uma virada de posição:** parar de devolver para o cliente
  retestar e passar a simular internamente. *"Não vai dar para nós ficar pedindo
  para eles retestarem, testarem, testarem lá, não. Tem que pensar numa coisa aqui
  juntos pra gente tentar validar de cá"*.
- **O caminho que você propôs:** clonar para o staging da Swap o mesmo setup que
  foi feito para a Niky, com multiorg, para reproduzir com os mesmos dados. Ficou
  com você falar com o Paulo sobre viabilidade e tempo.
- O Stive separou dois problemas que estavam sendo tratados como um:
  **primeiro acesso** (cadastro inicial) e **login** (biometria/token). O "loop
  infinito de autenticação" era da base já corrigida, não do primeiro acesso.
- Ao investigar um ticket específico, o time provou que **não era falha de
  sistema**: o usuário já tinha refresh token processado e cartão virtual ativo, e
  cartão virtual só existe depois de login.
- A conclusão da investigação do fim do dia: boa parte da percepção de erro vem
  de **cache inconsistente e versão defasada** do app.

**App — força a atualização**

- Nova versão com performance, autenticação reescrita, multiorg, correção do botão
  de cadastro e tema claro/escuro. O Stive **reescreveu os serviços de
  autenticação do legado** e ganhou tempo de inicialização e de login.
- **Decidido aplicar force update** na versão mínima que resolve os impedimentos.
  A razão é operacional: com o volume de tickets é inviável responder um por um, e
  o Stive lembrou que cada deploy é caro porque passa por revisão de loja.
- O `expedite` da Apple funcionou: **revisão em 15 minutos**.
- O botão "Cadastrar" que não habilitava era falha de validação dos campos de
  senha — interagir com o olhinho forçava a validação. Corrigido, aguardando loja.

**Bags duplicadas**

- O Bruno adaptou o script que já existia em benefícios e **rodou na FACISC com
  sucesso**.
- **Você autorizou rodar para os demais clientes**, com o OK do Santi. Na Niky são
  **5 account holders** — os mesmos casos vistos na migração.

**Desbloqueio de cartão**

- Cinco tickets do mesmo tema. A causa foi cercada durante o dia: o **BFF não
  recupera corretamente o status de vínculo do cartão físico da API de Cartões**,
  então o sistema entende que já está vinculado e barra o desbloqueio.
- O Santi resolveu de forma indireta o erro 500 nas exceptions ao mexer na tela de
  regras de saldo.
- **Mitigação imediata:** orientar o usuário a criar cartão virtual.
- **Fim do dia:** o Lucas já tinha hotfix desenvolvido e testado, dependendo de
  merge com a branch do Santi. Você ofereceu passar o WhatsApp do Santi para
  destravar, com subida prevista para a manhã seguinte.

**Transferências e saldos**

- O Andrey resolveu os pedidos com **saldo transferido parcialmente**, com um
  script que percorre os pedidos e identifica pendência em voucher, concluindo os
  que estavam travados.
- Sobre o caso Qualicorp: o estorno caiu em **Saldo Livre (ID 16)** e não em
  Premiação, e a hipótese levantada é confusão entre a nomenclatura da categoria e
  os IDs da processadora. A ideia de habilitar transferência entre carteiras para
  o usuário se resolver **foi contestada aqui** pela Luma e pelo Túlio, pelo caos
  de fazer isso em massa sem relatório dos afetados. *(A decisão final veio depois,
  no checkpoint das 16:00: habilitar a carteira na organização.)*
- **Você pediu bloqueio de 15 minutos após o clique** para evitar transação
  duplicada por "dedo nervoso", e o time discutiu idempotência como alternativa.

**Métricas**

- **Você cobrou a etiqueta de cliente nos cards do Shortcut**, porque estava
  puxando os cards da Niky e não aparecia nada: *"senão a gente vai ficar sem
  métrica de nada aqui"*. A Dani faz o retroativo, e o time passa a etiquetar tudo
  que é novo.
- A Luma vai **categorizar os tickets de acesso em três cenários** para permitir
  resolução em massa em vez de resposta individual.

**FACISC**

- O problema de criação de bags foi resolvido. O que resta é alinhar com o cliente
  as **regras do PAT** — os novos clientes tentavam configurar bags misturando
  regras de benefício, o que não é permitido.
- **Você pediu ao Andrey para avisar a Ju** do avanço, já que ela havia perguntado
  no privado.

## Próximos passos

- [ ] Falar com o Paulo sobre clonar produção em staging para simular o primeiro acesso — Junior — sem prazo
- [ ] Incluir o Paulo no convite da reunião com o cliente — Junior — feito na call
- [ ] Avisar a Luma que a correção do desbloqueio de cartão está finalizada — Junior — sem prazo
- [ ] Enviar a planilha de status da Niky para o Stive validar — Junior — sem prazo
- [ ] Coordenar com o Santi o merge do hotfix de desbloqueio de cartão e publicar — Lucas Gomes — manhã de 05/08
- [ ] Subir a correção do botão de cadastro e do fluxo de primeiro acesso — Stive Tormes — aguardando loja
- [ ] Atualizar os ambientes de staging da Swap e da Niky — Stive Tormes — sem prazo
- [ ] Organizar os cenários de erro de acesso por versão corrigida, para a próxima reunião — Stive Tormes — sem prazo
- [ ] Testar multiorg no Android e criar conta em duas organizações no STG da Niky — Túlio — sem prazo
- [ ] Implementar o checkbox de selecionar todos — Gabriel Santi — commitado, a subir
- [ ] Investigar a transação 3558 e o estorno na carteira errada — Gabriel Santi — sem prazo
- [ ] Analisar os 5 tickets de desbloqueio de cartão pendentes — Gabriel Santi — sem prazo
- [ ] Investigar o erro 400 do Benefit Card com mais dados — Gabriel Santi — postergado
- [ ] Analisar os logs de unlock card enviados pelo Stive — Thales Machado — sem prazo
- [ ] Categorizar os tickets de acesso por cenário e reportar depois das 16h — Luma Gomes Leonardo — feito
- [ ] Levantar 3 exemplos de erro de primeiro acesso para achar padrão — Luma Gomes Leonardo — sem prazo
- [ ] Ajustar retroativamente as etiquetas de cliente nos cards do Shortcut — Dani — sem prazo
- [ ] Etiquetar o cliente em todo card novo — o time — a partir de agora
- [ ] Avisar a Ju sobre o avanço da FACISC — Andrey Cunha — na call
- [ ] Validar a lógica do script de processamento dos 3.500 cartões — thread técnica — sem prazo

## Como você foi

**Este é o oposto do seu comportamento nos checkpoints com o cliente.** Nas duas
calls com a Niky você falou duas vezes em 1h03 e zero vezes em 55 minutos. Aqui
você falou 269 vezes em 7h29 e conduziu de fato.

**E você mudou de posição sobre a coisa mais importante do dia.** Ontem, para
cortar custo de investigação, você disse: *"Se for dar muito trabalho, a gente tá
seguro. Vamos devolver, pedir para eles retestarem e boa"*. Hoje, sobre o mesmo
problema:

> *"Não vai dar para nós ficar pedindo para eles retestarem, testarem, testarem
> lá, não. Tem que pensar numa coisa aqui juntos pra gente tentar validar de cá."*

É a correção exata do que o vault registrou como falha ontem, feita em 24 horas e
sem ninguém ter apontado. E você não parou na frase: propôs o caminho concreto,
clonar o setup da Niky no staging da Swap com multiorg, e assumiu falar com o
Paulo.

**Você geriu recurso em tempo real, e isso é o que faltava.** Quando o Stive
precisou de ajuda na análise do cartão, você não mandou esperar: mapeou que o
Bruno estava nas bags duplicadas e o Santi estava preso, e realocou o Lucas na
hora. Três pessoas ocupadas e uma frente parada é o tipo de nó que só quem vê o
todo desata.

**E você fechou o loop que ontem ficou aberto.** Ontem a nota registrou que
"a gente tá seguro" foi dito antes de estar verificado. Hoje você perguntou à
Luma, duas vezes, se a correção da lentidão já tinha sido devolvida ao cliente e
se **funcionou** — não se subiu, se funcionou. Verificação virou pergunta sua.

**Três intervenções de dono do produto, não de gestor de fila.** O checkbox de
selecionar todos, pensado a partir do trabalho de quem opera. O bloqueio de 15
minutos contra transação duplicada por dedo nervoso. E a cobrança das etiquetas
no Shortcut — que é você resolvendo na origem o problema que te morde na hora de
reportar à diretoria, em vez de reclamar da falta de número depois.

**O que daria para fazer melhor.** Você perguntou duas vezes a mesma coisa sobre
a lentidão devolvida, com quase 100 linhas de distância, porque saiu, atendeu
telefone e perdeu a resposta. Numa call de 7h29 isso é humano, mas é o custo de
estar em três lugares ao mesmo tempo: war room, conversa com a Priscila e
checkpoint com o cliente. O contorno não é aguentar mais, é delegar a presença
contínua na sala a alguém e entrar nos momentos que precisam de você.

**E o repasse do Paulo continua sem data.** Você pediu a ele para participar,
conseguiu até 16:30 e assumiu incluí-lo no convite — tudo pontual e útil. A
sessão de repasse do que ele mudou na migração, que você mesmo chamou ontem de
pendência mais crítica do dia, segue como intenção. Hoje ela ficou embutida em
"vou falar com o Paulo para ver se ele tem alguma ideia de como simular".

## Pontos de atenção

- **A causa raiz do primeiro acesso segue desconhecida no fim do dia.** Três
  hipóteses caíram, a investigação apontou cache e versão defasada, e um ticket
  provou que o usuário já tinha acessado. Nada disso é a mesma coisa que ter
  encontrado a causa. Se o volume voltar depois do force update, a resposta atual
  não cobre.
- **O force update é aposta forte.** Ele limpa o ruído de versão antiga e, se
  sobrar erro, o que sobrar é real. Bom para diagnóstico, arriscado se a versão
  nova trouxer problema, porque não há para onde voltar.
- **O BFF que não lê o vínculo do cartão físico é dívida estrutural**, não bug
  isolado, e é o que gerou os cinco tickets de desbloqueio. O hotfix do Lucas
  resolve o sintoma.
- **O Santi expôs o custo do legado** e defendeu a migração para a 2.0 como
  solução definitiva. Isso conecta com a V0 já adiada para 04/09 — quanto mais
  tempo em contenção no legado, mais longe a 2.0.
- **Túlio pediu freezing nas melhorias de benefícios** para o RTF andar. É pedido
  de priorização vindo de baixo, e ainda não tem resposta sua.
- **A leitura dos erros no Grafana está sob suspeita** — Santi e Túlio acharam
  discrepância entre as rotas de login e de cartões e duvidaram do próprio número.
  Painel em que não se confia é pior que painel nenhum durante incidente.
- **O bloqueio de recarga por usuário não validado** já tinha spike na sprint
  anterior e está planejado para esta. É problema que afeta vários clientes, não
  só a Niky.
- **Dúvida de identidade não resolvida:** esta transcrição registra **Luma
  Gomes** e a do checkpoint registra **Luma Gomes Leonardo**. Pode ser a mesma pessoa
  com nomes de exibição diferentes ou duas pessoas distintas. Nenhuma das duas tem
  nota em `👥 Time/`, então o vault não desempata.
- **Ruído de transcrição:** "Steve"/"S"/"Sant"/"San" alternam entre
  [[Stive Tormes]] e [[Gabriel Santi]] e é preciso ler o contexto para saber qual,
  "Luna" é a Luma, "Otúlio"/"Tú" é o [[Túlio Cruz Ferreira da Silva]], "Andrei" é
  [[Andrey Cunha]], "Tales" é o Thales, "NIC"/"Nick" é Niky, "SUAP" é Swap,
  "FCIS"/"facisca" é FACISC, "daap"/"DMAP" aparece como sigla sem contexto,
  "Lauxen" é o Luiz Lauxen, "bags" são as bags de saldo e "BO" é back office.
