---
data: 2026-08-03
hora: "11:54"
reuniao: "Tombamento Niky"
tags: [reuniao]
participantes: [Junior Oliveira, Gabriel Santi, Stive Tormes, Túlio Cruz Ferreira da Silva, Alana Barbosa, Lucas Gomes, Thales Machado, Paulo Pereira, Marcio Filho, Weslley Silva, Kelly Almeida, Luma Gomes Leonardo, Dheyson Silva, Taillon Neves, Andrey Cunha, Bruno Leonardo Conti, Joselito Rend]
projeto: "Whitelabel"
status_acoes: pendente
fonte: "Tombamento Niky - 2026_08_03 17_04 GMT-03_00 - Transcript.docx"
tipo_fonte: transcricao
doc_id: "1KHKAS1sb32X2Ml__vlKGgis6DxpmCFnmv_7Vry5EgAs"
---

# Tombamento Niky | 03/08/2026

## Contexto

A sala de guerra do tombamento, aberta e reaberta ao longo do dia inteiro. Quatro
transcrições, **5h20 de call**, do meio-dia às 20h18:

| Sessão | Duração | Quem | O que foi |
|---|---|---|---|
| **11:54** | 48min | 9 pessoas | Investigação da falha de primeiro acesso; causa raiz encontrada |
| **13:38** | 10 segundos | só o Andrey | sala aberta por acidente, sem conteúdo |
| **14:02** | 2h03 | 13, com Kelly e Luma | Validação, triagem da planilha de casos, descoberta do Firebase |
| **17:04** | **3h14** | 15, com Paulo Pereira, Marcio Filho e Weslley Silva | Pós-checkpoint com o cliente: escalada de infra e retomada de contexto |

No meio delas, às 16:01, aconteceu o checkpoint com o cliente — call separada,
com quatro pessoas da Niky na sala. É a reunião que muda o tom da sessão de
17:04.

O `doc_id` do frontmatter é o da sessão de 11:54, a única cujo mapeamento está
confirmado. As outras três estão nos Docs
`1hYmVpk0JR5uBlTPfhQY1F8d_l_AO_mxiPWn16xWWfYY`,
`1Qxa1Z2ftwf1x-EBNhSJp_GHTR-Rh6cNRgEee7Wi974g` e
`1yxm4pnT1sqs-6rJD35_dcu-kLmjCUsawgCA-PXDZAsA`.

## Decisões tomadas

**Manhã — a causa raiz do primeiro acesso**

- **O [[Gabriel Santi]] achou a causa ao vivo:** usuários importados da Niky
  ficaram sem vínculo de `user ID`. Uma notificação que ele havia adicionado
  gerava exceção no primeiro acesso (`null reference`), e a pessoa travava mesmo
  com o usuário já criado.
- **O fix da causa já estava em produção desde sexta, 31/07** — mas quem tentou
  antes dele não foi corrigido retroativamente. **Os 242 usuários travados foram
  corrigidos por update direto na base**, durante a call.
- **Todos os migrados precisam fazer o primeiro acesso normal no app.** Dúvida do
  Stive, confirmada pelo Santi: *"Primeiro acesso. Todo mundo geral"*. Valida a
  orientação que o CSO já havia enviado.
- **Reproduzir o bug em staging foi descartado por você:** *"Se for dar muito
  trabalho, a gente tá seguro. Vamos devolver, pedir para eles retestarem e
  boa"*.
- **Dois bugs de app mapeados pelo Stive, nenhum impeditivo do primeiro acesso:**
  o "lembrar minha senha" reusando o campo de senha antiga — paliativo foi
  desligar a flag, e a versão com a correção está pronta e não publicada; e a
  inicialização do app rodando em paralelo ao pedido de permissão de internet,
  o que faz o app subir com feature flags e tema default na primeira abertura.
  Duas saídas possíveis para o segundo: tela inicial de OK ou retries.
- **Você autorizou trazer o pessoal da outra squad para perto:** *"Se vocês
  quiserem puxar o pessoal aqui, pode me mandar bala"*. Sem nome nem data. E
  matou o reflexo de "não é problema nosso" quando o Túlio perguntou se não havia
  outro time cuidando: *"essas squads elas nascem e morrem. Então, independente
  se eles estão fazendo algo lá, no final das contas vai virar nosso aqui"*.
- Números: ~79 a 80 mil contas viraram no sábado 01/08, ~2 mil já instalaram o
  app, 67 mil aparecem sem `user ID` — mistura de quem ainda não acessou com
  quem estava quebrado. Só **242** foram confirmados quebrados.

**Tarde — validação e o que não era nosso**

- **A Kelly Almeida validou o primeiro acesso em produção**, a pedido da
  [[Alana Barbosa]] — era a ação que faltava para transformar "corrigimos" em
  "verificamos". A Alana criou o usuário dela em produção.
- **Descoberta importante: parte das reclamações não é do app da Swap.** O
  [[Stive Tormes]] identificou que existe o **Nick Benefícios**, app antigo do
  próprio cliente, com muitos usuários na loja e mesmo nome. O print que o
  cliente mandou mostra uma tela que não é de vocês. Ficou decidido tirar print e
  vídeo do fluxo correto para usar como evidência na call das 16:00.
- **O OTP respeita o telefone do portal, não o do primeiro acesso.** Túlio
  testou: o número preenchido no onboarding do app é ignorado, e o SMS vai para
  o cadastrado no portal. Explica o relato do "final nove".
- **O contactless corta os centavos** — configurar R$ 200 salva R$ 2. O
  [[Lucas Gomes]] assumiu o card, e o problema provavelmente afeta outros
  clientes, não só a Niky.
- **O Firebase do app da Niky estava travado no plano grátis.** O Stive
  descobriu que o projeto `Nick App Prod` estava sem billing account, estourou a
  cota diária e os apps em produção pararam de ler as feature flags: *"eu não
  consigo nem dizer o tanto de problema que isso pode causar. É n problemas"*.
- **Três casos de "autenticando infinito" foram consolidados** como um só tema,
  por decisão da Luma e do Thales — com retorno individual antes de unificar.

**Noite — a war room**

- **O Firebase foi resolvido na call.** Você chamou o Márcio; veio primeiro o
  Weslley Silva, de SRE, que descobriu não ter permissão de billing, **conseguiu
  se dar a permissão** e vinculou a conta `apps White Label`. O
  Marcio Filho entrou depois e confirmou o encaminhamento: vincular billing
  em todos os projetos e definir um limite de orçamento alto.
- **Outros projetos de produção estão sem billing.** O Weslley confirmou na tela.
  Ficou como backlog — a Niky só foi a primeira a bater a cota porque é grande.
- **A lentidão do portal da Qualicorp foi diagnosticada:** uma tela carrega um
  select com **26 mil pessoas** de uma vez. Não é infra, é front sem
  virtualização. O Santi está convertendo a tela para React e vai aplicar
  `virtualized list` / lazy loading. O Stive: *"é coisa que nunca foi feito um
  teste de carga nesse sistema"*.
- **A recarga manual da Qualicorp foi executada na call** — R$ 202.543 em
  pedidos criados e enviados, com o Thales acompanhando.
- **O merge da correção do [[Regis Graf]] para a branch da Niky foi feito** pelo
  Santi, com ressalva explícita: *"não me sinto confortável, mas dá para fazer"*
  — porque não se sabe o que o Paulo alterou por cima.
- **O Paulo Pereira entrou na sala** depois de você mandar a transcrição do
  checkpoint. Confirmou que não acompanhou todos os casos, pediu para ser
  incluído na planilha e se ofereceu para ajudar nas questões de migração, onde
  esteve mais envolvido.
- **Nada foi decidido sobre o repasse formal de contexto do Paulo** — você
  levantou a necessidade duas vezes, e ficou como intenção.

## Próximos passos

- [ ] Sentar com o Paulo Pereira para repasse do que foi alterado na migração — Junior e Paulo — sem prazo, e é a pendência mais crítica do dia
- [ ] Incluir o Paulo na planilha de casos do GT Tickets Nick — Junior — ele pediu na call
- [ ] Converter a tela de regras de saldo para React com lista virtualizada — Santi — em andamento
- [ ] Vincular billing account nos demais projetos de produção do Firebase — Marcio Filho / Rafael — backlog, sem prazo
- [ ] Definir limite de orçamento no billing do `Nick App Prod` — Weslley e Marcio — combinado na call
- [ ] Corrigir o contactless que corta os centavos e replicar para todos os clientes — Lucas Gomes — vai publicar em stage e validar
- [ ] Corrigir o bug de "autenticando infinito" no multiorg — Stive — já estava trabalhando na correção
- [ ] Atualizar a API do Android exigida pela Google — Stive — **até dia 30**
- [ ] Pedir print da tela inteira ao cliente nas próximas evidências — Túlio pediu ao CSO na call
- [ ] Retomar amanhã de manhã, incluindo o merge que o Lucas deixou para não subir de madrugada — time — 04/08

## Como você foi

**Você conduziu a escalada, e é isso que se esperava de você.** A call de 17:04
abre com o time processando uma surra do cliente — *"Meu Deus, mano, que amass
foi esse?"* — e em quinze minutos você já estava ligando para o Márcio, trazendo
o Weslley e pedindo ao Thales para cobrar em paralelo. O problema do Firebase era
o único bloqueio que nenhuma pessoa do seu time podia resolver sozinha, e você
tratou como tal. Foi resolvido dentro da própria call.

**E você fez a leitura estrutural certa, em voz alta.** Duas vezes:

> *"tem muita coisa que o Paulo mexeu com a gente. Falei com ele que a gente
> precisa sentar e ficar mais próximo nesses primeiros dias, porque senão a
> gente vai ficar apanhando aqui."*

> *"a gente tá sem visão nenhuma. E aí é f\*\*\*. Tipo, a gente não consegue
> responder porque a gente não tem contexto direito. O que que ele fez?"*

Esse é o diagnóstico do dia. O time não apanhou por incompetência técnica —
apanhou por não ter o contexto das mudanças que outra pessoa fez no produto que
eles precisam defender na frente do cliente. E você nomeou também o erro de
sequenciamento, sem se poupar: *"precisava de ter quebrado mesmo o time, mas
tinha que ter tido um tempo de ter um repasse com o Paulo, de entender tudo que
foi feito, quais foram as mudanças"*. O Stive havia acabado de questionar a
quebra em dois times, e você concordou em vez de defender a decisão.

**Você também não terceirizou a culpa para o cliente.** Quando o time estava
irritado com as cobranças, você equilibrou: *"super compreensível também entender
o lado das meninas lá. Os caras falaram que tão 400 chamada na fila. Imagina que
loucura. Tem a razão delas estarem com a paciência mais esgotada"*. Manter isso
num dia em que sua equipe levou pancada é difícil, e é o que impede o time de se
fechar contra o cliente.

**Duas outras coisas boas, pequenas e específicas.** Você perguntou pelos itens
que estavam sendo tocados por quem **não** estava na call apanhando — pergunta
que ninguém mais faria, porque quem estava na call só via o próprio fogo. E fez a
ponte de informação com o Paulo em tempo real, repassando ao time o que ele ia
concluindo.

**O que daria para fazer melhor.** O repasse com o Paulo, que você mesmo
identificou como a causa raiz do dia, **saiu da call sem data**. Foi dito duas
vezes, o Paulo estava na sala e concordou, e ninguém marcou. É o mesmo padrão que
o vault já registra nas devolutivas de 31/07 e na call do André de 01/07:
diagnóstico certo, combinado sem dono e sem data. Aqui o custo é mensurável — a
próxima call com o cliente é hoje.

**"A gente tá seguro" continuou sendo dito antes de estar verificado.** Na sessão
da manhã você usou isso para cortar a reprodução em staging. A validação só veio
horas depois, com a Kelly, e por iniciativa da Alana — não sua. O corte de custo
estava certo; a afirmação de segurança veio antes da evidência.

**E a call de 3h14 terminou em papo de LOL e CS.** Os últimos vinte minutos são
descompressão de gente que trabalhou até as 20h18 e é humano, mas houve espaço
ali para fechar o dia com os cinco próximos passos ditos em voz alta. Você fechou
com *"amanhã nós voltamos"*, e o Lucas ficou mexendo em código à noite dizendo
*"me empolguei"* — sem ninguém dizer que podia parar.

**Sobre divergência:** houve uma real, e não com você. O Túlio insistiu que a
correção da planilha não tinha subido e o Santi rebateu que sim, com firmeza
(*"Subi, mano. Não tem como não funcionar isso aí"*). Acabou sendo questão de
flag em staging. Você não entrou, e não precisava.

## Pontos de atenção

- **A falta de repasse do Paulo é o risco número um.** Ele mexeu em migração e em
  partes do portal, o time não sabe o quê, e é o time que senta na frente do
  cliente todo dia às 16:00. Enquanto isso não for feito, cada checkpoint tem
  chance de repetir a call de ontem.
- **A quebra do time em dois aconteceu sem handover** — reconhecido por você e
  pelo Stive na call. Vale registrar como aprendizado de processo, não só como
  incidente.
- **O cliente nunca usou o ambiente de staging.** O Stive: *"o nosso onboarding
  tem uma validação onde o cliente teria que fazer todos esses testes no ambiente
  de STG. E pelo que eu vi da Nick, os caras nem acessaram. Eles foram direto
  para Prod"*. E o Santi: *"parece que ninguém explicou para eles como é que
  funciona o portal"*. Parte do que chegou como bug é falta de treinamento e de
  validação em homologação — o que conecta direto com a meta de OnboardAI.
- **O `Nick Benefícios` é uma fonte permanente de falso positivo.** App antigo do
  cliente, mesmo nome, ainda na loja. Enquanto existir, usuários vão instalar o
  errado e abrir ticket para vocês.
- **Nenhum teste de carga foi feito no sistema.** A tela de 26 mil pessoas é o
  primeiro sintoma; com o volume da Niky dentro, não será o último.
- **Outros projetos de produção estão sem billing no Firebase.** Só a Niky bateu a
  cota porque é grande. Os demais vão bater conforme crescerem.
- **A Google exige atualização da API do Android até dia 30**, e isso ainda não
  tem dono formal além do Stive.
- **O Stive perdeu os acessos ao Firebase** que antes permitiam a ele resolver
  esse tipo de problema sozinho: *"tirava todos meus acessos no Firebase, eu
  resolvia tudo isso na hora"*. A segregação é correta em segurança e caríssima
  em tempo de incidente — vale desenhar um caminho de acesso emergencial.
- **O KYC entrou sem prazo e virou bloqueio.** O Stive: *"o IC também chegou do
  nada pra gente, sem prazo nenhum. Não tem como a gente dar desculpa pros
  caras"*.
- **Só uma das quatro transcrições vai ser reconhecida pelo `limpar.py`.** O
  campo `fonte` aceita um arquivo, e esta nota cobre quatro. Os `.docx` das
  sessões de 11:54, 13:38 e 14:02 vão aparecer como "sem nota no vault" no
  relatório de limpeza, mesmo estando resumidos aqui.
- **Ruído de transcrição:** "Nick" é Niky, "SUAP" é Swap, "Steve" é
  [[Stive Tormes]], "Sant"/"S" é [[Gabriel Santi]], "Ris"/"Réges" é
  [[Regis Graf]], "o IC"/"o K"/"QC" é KYC, "Márcia" é Marcio Filho,
  "Otávio" e "Tales" são o Thales Machado, "bet" é o BaaS, "Calicó"/"Qualicor" é
  Qualicorp, "biling" é billing e "carry"/"K" é query.
