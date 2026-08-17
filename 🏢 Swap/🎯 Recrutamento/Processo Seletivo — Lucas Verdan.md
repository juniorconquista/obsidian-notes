# Processo Seletivo — Lucas Verdan | 17/07/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que tope generalizar para back
**Origem:** **Processo de seleção do RH** — veio da triagem, não é indicação
*(corrigido em 05/08/2026: a nota registrava "indicação do Santi", o que não
procede)*
**Status:** ✅ **Entrevistado em 06/08/2026** (15:00, 1h24m38s). Resultado no fim da
nota. **É o nome mais forte do funil.** Aguarda conversa de perfil com a Célia.

---

> [!important] Recalibração antes da entrevista — 05/08/2026
> O roteiro abaixo foi escrito em 17/07. Quatro coisas mudaram desde então e
> alteram o peso das perguntas.
>
> **1. O .NET deixou de ser eliminatório.** Critério revisado por você em 05/08: com
> IA no fluxo, o que se mede é **disposição**, não domínio. A seção 2 do roteiro
> ainda trata backend como "o gap mais crítico dos 6" e o gabarito chama a reação
> ao .NET de "a bandeira mais importante de toda a rodada". **Não é mais.** Continua
> valendo perguntar — mas como curva a gerenciar, não como corte.
>
> **2. O foco da vaga é o WL 2.0 em Next, não o legado.** Definido por você em
> 05/08: *"meu foco aqui pra essa vaga não é no legado, é no Next.js, nossa V2 que
> está em construção — isso conta, mas não é o que decide."* É o mesmo que você
> disse ao [[Processo Seletivo — Jean Ribeiro]] e ao
> [[Processo Seletivo — Manolo Pina]] nas duas calls.
>
> **O que isso muda na leitura dos candidatos:** a pergunta deixa de ser "sabe
> migrar legado?" e passa a ser **"sabe construir bem um produto financeiro novo em
> Next, do zero, que vai durar anos?"**. Legado entra como convivência e contexto,
> não como mandato.
>
> **E cria um gap novo que não estava no comparativo de julho: profundidade real de
> App Router.** Os dois entrevistados falharam nele — o Jean *"não foi tão a fundo
> ainda"* e usa SvelteKit; o Manolo só tem App Router em projeto pessoal, o
> profissional dele foi Page Router há anos. Se o Lucas tiver App Router e Server
> Components em produção hoje, no checkout, **ele é o único**.
>
> **3. Teste virou requisito, não desejável.** A [[Priscila Campos]] entrou em 05/08
> e o acordo que você fixou é *"não se sobe mais nada sem teste"*. O roteiro trata
> testes como gap a validar. A régua agora é o Jean, que é dono da prática e está
> implementando Playwright em fluxo crítico. O Manolo não conhece Playwright.
>
> **4. Presencialidade é o que está matando o funil, e o modelo dele não está
> declarado.** Três candidatos caíram por isso. Pergunte cedo, como funcionou com o
> Manolo — e **ouça sem prometer**: você já disse ao Manolo que "não é uma exigência
> real ter presença" antes de fechar a regra com a Célia e o Vini.
>
> **Âncoras de preço que agora existem:** Jean pediu **R$ 25k PJ**, Manolo **R$
> 13-14k**. Você já achou o Jean caro para o que entregou.

---

## Perfil

- **LinkedIn:** linkedin.com/in/lucas-verdan
- **Experiência:** 8+ anos — Ambush/consultoria internacional (atual, para fintech Fortune 500), Banco Inter (liderou frontend de e-commerce), Avenue Code (5+ anos, consultoria enterprise)
- **Stack:** React, Next.js, TypeScript, Node.js — forte em arquitetura frontend e sistemas distribuídos

## Por que está na shortlist

- **Domínio fintech/pagamentos muito forte e recente:** atualmente trabalha em checkout para uma das maiores plataformas de pagamento digital do mundo (via consultoria); antes disso, liderou arquitetura de frontend no **Banco Inter** (um dos maiores bancos digitais da América Latina).
- Já **liderou tecnicamente** — no Banco Inter, dirigiu a migração para arquitetura de micro-frontend (Module Federation), permitindo múltiplos times desenvolverem/deployarem de forma independente. Isso é diretamente relevante para "arquitetura modular/multi-tenant" da vaga.
- Mentoria ativa de engenheiros front-end (Banco Inter) — maturidade sênior real, não só título.
- Experiência em ambientes distribuídos internacionais, parceria direta com backend engineers — sinal de que já colabora de perto com back, mesmo sem escrever o código back ele mesmo.
- Trajetória de crescimento consistente dentro da Avenue Code (de estagiário a sênior em 5 anos) — mostra capacidade de evolução e persistência.

## Gaps a validar *(todos derrubados na entrevista de 06/08)*

> [!warning] Esta seção estava errada e foi respondida
> O currículo não mostrava, mas a conversa mostrou. Fica registrada como estava,
> porque foi ela que quase desclassificou o candidato mais forte do funil.

- ~~**É o mais front-leaning dos 6 candidatos** — não há nenhuma menção a ele
  próprio escrevendo código de backend.~~ → **Falso.** Escreveu Java Micronaut no
  Banco Inter, Python e pandas na Avenue Code, além de Node.
- ~~Nenhuma menção a .NET/C# — nem contato superficial.~~ → **Falso.** Trabalhou com
  **.NET e Razor** no primeiro emprego, em software de qualidade para a linha de
  montagem da Fiat/FCA, pela Engineer do Brasil. É o único dos três entrevistados
  com contato real com a stack do nosso legado.
- ~~Não menciona testes E2E, Playwright, ou cobertura de testes.~~ → **Falso, e é o
  oposto.** Usa Jest, Storybook e **Playwright** no PayPal, com pre-commit hook e
  step de pipeline, e implantou o mesmo processo no Inter.

**A lição:** três gaps eliminatórios inferidos de ausência no currículo, e os três
eram falsos. Ausência no LinkedIn não é ausência na carreira.

---

## Roteiro — reescrito em 05/08/2026 para o cenário atual

> **Três decisões de desenho, e cada uma tem motivo:**
>
> 1. **O centro é construir a V2 em Next, não migrar o legado.** O bloco 4 mede
>    profundidade de Next moderno e arquitetura de produto novo. O legado virou o
>    bloco 5, curto, e serve para medir convivência e senioridade — não é o corte.
> 2. **O .NET desceu.** Com o critério revisado, o que se mede é disposição, não
>    domínio. Continua no roteiro, mas não é mais corte.
> 3. **Modelo de trabalho entra nos primeiros dez minutos**, porque foi o que
>    derrubou três candidatos, e o dele não está declarado.
>
> **Tempo:** os blocos 4, 6 e 7 são os que não podem ser cortados. Se apertar,
> sacrifique o 10 e encurte o 5. *Referência: o Jean rendeu 45min, o Manolo 1h21 e
> passou do previsto porque você falou demais no começo.*

### 1. Abertura (5 min)

> ⚠️ Ele **não veio por indicação** — chegou pela triagem do RH. Não pergunte "quem
> te indicou". Ele provavelmente sabe pouco da Swap, então o bloco 2 pesa mais aqui
> do que pesou com o Manolo, que já vinha com contexto do Samir.

- O que você já sabe da Swap e da vaga? *(descubra o que a Célia contou antes de
  enquadrar)*
- Conta o que você faz hoje na Ambush: é alocação em cliente? Qual produto, e qual
  o seu escopo no checkout?
- No Banco Inter você liderou a arquitetura de front — qual era o tamanho do time e
  o que exatamente estava sob a sua decisão?

### 2. O momento, dito sem maquiar (5 min)

*Conte o real. Funcionou com a [[Priscila Campos]] e com o
[[Processo Seletivo — Manolo Pina]]. **Não repita o que você contou ao
[[Processo Seletivo — Jean Ribeiro]]** — "a máquina tá redondinha" — porque não era
verdade nem em julho.*

Tombamento de 80 mil contas no sábado com prazo forçado por multa da Mastercard,
dois dias de war room, portal legado em Razor dentro do .NET com tela que carrega 26
mil registros e trava, um WL 2.0 em Next que precisa substituir o legado sem parar
nada, e uma especialista de qualidade entrando agora porque não há teste unitário
nem teste de carga.

- **Isso te atrai ou te assusta? Responde sincero.**

### 3. Modelo de trabalho — cedo de propósito (3 min)
- Como você trabalha hoje e como prefere: presencial, híbrido, remoto?
- A Swap é remota de fato, mas tem eventos algumas vezes por ano, com custo pago —
  vir ao escritório eventualmente é confortável?
- Uma vez por ano tem offsite de dois dias fora. Problema?

> ⚠️ **Ouvir, não prometer.** A exigência real ainda não está fechada com a Célia e o
> Vini, e você já prometeu ao Manolo que "não é uma exigência real ter presença".
> Não amplie o problema.

### 4. Construir a V2 em Next — **o bloco que decide** (18 min)

*Este é o trabalho da vaga: um produto financeiro novo, em Next, que vai substituir
o legado e durar anos. Ele constrói checkout em Next hoje, para uma das maiores
plataformas de pagamento do mundo — se a profundidade for real, aparece aqui.*

**App Router de verdade — o gap que os dois entrevistados têm**
- Seu uso hoje é App Router ou Pages Router? Em produção ou em estudo?
- Server Components e Server Actions: usa em produção? Onde entra e onde você
  decidiu **não** usar?
- Como você decide o que renderiza no servidor e o que vai para o cliente?
- Cache do Next já te mordeu? Conta.

**Arquitetura de dados e estado**
- Como você separa estado de cliente de estado de servidor? Usa React Query, SWR,
  ou resolve com o que o Next dá?
- Num produto com formulário longo, filtro que persiste e tabela pesada — onde mora
  cada estado?
- Como você tipa resposta de API que pode vir em formatos diferentes? Valida em
  runtime?

**Design system do zero — vale mais aqui do que em qualquer outro candidato**
- Se você entrasse hoje num produto novo, como montaria a base de componentes:
  headless, biblioteca pronta, ou construir?
- Como você distribui e versiona isso entre projetos?
- Design token: usa? Como evita que o time saia do padrão?
- Nosso UI kit é o **Mantine** — conhece?

**Performance como decisão de projeto, não como conserto**
- Qual foi o pior problema de performance que você resolveu? Métrica ruim, causa
  raiz, o que fez, e o número depois.
- Lista com volume grande: como você decide entre virtualizar, paginar ou empurrar
  para o backend?
- Como você impede que um produto novo vire lento em dois anos?

**A pergunta de projeto**

> Você entra num produto em Next que está em construção, que vai substituir um
> portal legado e atender clientes com dezenas de milhares de usuários cada.
> Ele ainda não tem teste. **Quais são as três primeiras coisas que você faria?**

### 5. O legado — convivência, não mandato (6 min)

*Conta, mas não decide. Serve para medir senioridade e realismo, e porque ele é o
único do funil que fez Module Federation em produção.*

- Module Federation no Banco Inter: qual era o problema antes, o que você liderou
  de fato, e **o que deu errado no caminho**?
- O que dói nisso na prática — versionamento de dependência compartilhada, contrato
  entre times, custo de build?
- Nosso contexto: portal legado em Razor dentro do .NET, e a V2 em Next que vai
  substituí-lo ao longo de mais de um ano. Hoje a gente migra pedaço a pedaço para
  React quando uma tela dói muito. **Isso é estratégia ou remendo, na sua leitura?**
- Micro-frontend faria sentido aqui, ou seria bala de prata errada?

### 6. Fintech e checkout — o ponto forte dele (8 min)
- No checkout que você constrói hoje, quais os maiores desafios de front no fluxo de
  pagamento — estados de erro, retry, idempotência, feedback em tempo real?
- Como você lida com uma operação que pode ter sido processada mas cuja resposta
  não chegou? *(O Jean desviou dessa. É pergunta boa.)*
- Já lidou com compliance ou segurança no front — tokenização, PCI, dado sensível?
- Você mexe com dinheiro de verdade hoje? O que acontece se o teu código erra?

### 7. Escala, criticidade e incidente (7 min)

*Bloco que ficou de fora na conversa com o Manolo e que é o maior diferenciador
entre candidatos. Não pule.*

- Qual o sistema mais crítico em que você mexeu — quantos usuários, o que acontecia
  se caísse?
- **Conta um incidente de produção que você resolveu.** O que quebrou, como você
  descobriu, o que fez, e o que mudou depois para não repetir.
- Já teve que subir correção direto em produção? Como decidiu que era seguro?

### 8. Testes — virou requisito (5 min)

*Com a entrada da [[Priscila Campos]] e o acordo de que nada sobe sem teste, isso
deixou de ser desejável. A régua é o Jean, que é dono da prática.*

- Teste faz parte do seu PR normal ou fica com QA?
- Já usou **Playwright**? É o nosso.
- Quem escreve o E2E dos fluxos críticos no seu time hoje?
- Como você garante que a cobertura não regride depois de três sprints? *(O Manolo
  respondeu "no olho mesmo".)*
- Já fez teste de carga? Em quê?

### 9. Disposição para o back e IA no fluxo (8 min)

*O .NET não é mais corte — mas o **como** ele valida o que não domina virou a
pergunta boa, e é a que ficou sem resposta com o Manolo.*

- Você já escreveu código de backend em algum momento, mesmo pequeno?
- Nosso backend é .NET. Você não precisa saber .NET para entrar, mas vai pegar
  ticket lá quando a fila pedir. Como isso soa?
- Já entrou em stack que não era a sua e teve que produzir rápido? Quanto tempo até
  o primeiro PR útil?
- Como você usa IA no fluxo hoje? Quero exemplo concreto: o que você delega, o que
  não delega, e um caso em que ela te levou para o buraco.
- **Numa linguagem que você não domina, como você sabe que o código que a IA gerou
  está certo? O que você checa antes de abrir o PR?**

### 10. Liderança e mentoria (5 min — cortável)

*Os dois entrevistados foram fracos aqui, e o time tem um gargalo real de
onboarding: o [[Gabriel Santi]]. Quem resolver isso ganha ponto que ninguém ganhou
ainda.*

- Como era sua mentoria no Banco Inter? Um exemplo com resultado concreto.
- Como você toma decisão técnica quando o time discorda?
- Se você entrasse aqui, como se colocaria em dia com um produto que quase ninguém
  documentou?

### 11. Trajetória — os 5 meses (3 min)
- Você está na posição atual desde março/2026. O que faria você considerar sair tão
  cedo?
- Avenue Code → Inter → Ambush em sequência: como você escolhe quando sair?

### 12. Fechamento (5 min)
- Pretensão salarial e disponibilidade.
- O que você precisa saber de nós para decidir?
- Próxima etapa: conversa de perfil com a Célia, e entrevista técnica com o Santi.

---

## Sinais de alerta a observar

- 🚩 **O mais importante agora:** App Router raso. Se o Next dele for conceitual ou
  de projeto pessoal, ele empata com o Jean e com o Manolo justamente no eixo da
  vaga — e aí não sobra motivo para preferi-lo.
- 🚩 Não distinguir estado de cliente de estado de servidor, ou guardar resposta de
  API em store global. O Manolo passou bem nisso e é a régua.
- 🚩 Design system respondido como "uso uma biblioteca pronta e crio uns
  componentes". A régua é o Jean: headless, design token, distribuição versionada.
- 🚩 Resistência real a pegar ticket de back — não a hesitação natural, que é
  esperada. Ou o oposto: minimizar a curva com "com IA hoje é tudo igual", que é
  precisamente a premissa que você está assumindo e precisa de alguém que a
  sustente com critério, não que a repita.
- 🚩 Nenhum exemplo de incidente de produção. Num time que rodou duas war rooms em
  dois dias, isso pesa.
- 🚩 Delegar teste 100% para QA.
- 🚩 Module Federation descrito no nível da definição. Não decide a vaga, mas se é o
  feito principal do currículo e não tem história dentro, contamina a leitura de
  tudo que ele contar.
- ✅ **O sinal que o coloca na frente:** App Router e Server Components rodando em
  produção hoje, num fluxo de pagamento, com decisão explícita de onde não usar. É
  literalmente o trabalho da vaga, e nenhum dos dois entrevistados tem isso.

---

## Gabarito — o que esperar, com a régua dos dois já entrevistados

### App Router e Next moderno (a pergunta que decide)

- ✅ **Forte:** App Router e Server Components em **produção**, no checkout, com
  decisão explícita de onde **não** usar RSC e por quê. Sabe contar uma vez em que o
  cache do Next o mordeu. Se vier assim, ele é o único dos três — Jean e Manolo
  falharam os dois aqui.
- Aceitável: usa App Router mas sem Server Actions, e explica bem os conceitos de
  servidor. Foi mais ou menos o nível do Jean e não foi bandeira vermelha.
- 🚩 **Fraca:** App Router só em projeto pessoal (Manolo) ou "não fui tão a fundo"
  (Jean). Nesse caso ele **empata com os dois no eixo da vaga**, e o que sobra para
  decidir é preço e fintech.

### Estado, dados e arquitetura do produto novo

- ✅ **Forte:** distingue estado de cliente de estado de servidor na primeira frase,
  usa ferramenta própria para cache de servidor, e sabe dizer onde cada estado mora
  num produto com formulário longo e tabela pesada. Valida resposta de API em
  runtime.
- 🚩 **Fraca:** guarda resposta de API em store global. **O Manolo passou bem nisso
  e é a régua** — se o Lucas ficar abaixo, é um problema sério para quem vai
  construir a V2.

### Design system do zero — vale mais nesta vaga que em qualquer outra

- ✅ **Forte:** a régua é o Jean — headless, design tokens, Storybook, distribuição
  versionada por pacote privado. Detalhe técnico real, não inflado.
- 🚩 **Fraca:** "uso uma biblioteca pronta e crio uns componentes". Ficou abaixo do
  Jean no caso do Manolo, e aqui custa mais, porque a V2 está sendo construída
  agora e essa base se decide uma vez só.
- Mantine: não conhecer é gap esperado. Nenhum dos dois conhecia.

### O legado e o Module Federation (conta, não decide)

- ✅ **Forte:** liderou de fato, sabe o que doeu — versionamento de dependência
  compartilhada, contrato entre times, custo de build — e no cenário do Razor
  pergunta antes de responder, admitindo que micro-frontend pode não valer a pena
  aqui.
- 🚩 **Fraca:** *"nem fui eu que configurou"* (foi a resposta do Manolo), ou solução
  pronta em trinta segundos com Module Federation como reflexo. Não desqualifica —
  mas se o feito principal do currículo não tem história dentro, isso contamina a
  leitura de tudo que ele contar depois.

### Performance

- ✅ **Forte:** métrica, causa raiz, ação e número depois. E na pergunta dos 26 mil,
  diz que vai atrás do back — e sabe como conduzir essa conversa.
- 🚩 **Fraca:** cita ferramenta sem resultado (Manolo), ou aceita resolver tudo no
  front e "deixa quieto" quando o back não colabora (também Manolo).

### Fintech e checkout

- ✅ **Forte:** fluente e específico — é o trabalho dele hoje. Deve ser o bloco mais
  fácil. Se ele responder idempotência com clareza, passa o Jean, que desviou.
- 🚩 **Fraca (improvável e grave):** genérico. Seria bandeira grande.

### Incidente de produção

- ✅ **Forte:** a régua é o Jean — fornecedor de API faliu sem aviso, ele trocou,
  usou fallback, subiu direto em produção, testou, monitorou e depois refatorou.
  História completa com processo e autonomia real.
- 🚩 **Fraca:** nunca teve, ou não sabe contar um.

### Testes

- ✅ **Forte:** a régua é o Jean — dono da prática, implementando o primeiro
  Playwright nos fluxos críticos, não delega.
- Aceitável: faz unitário e integração, não conhece Playwright. Foi o caso do
  Manolo e não o desqualificou, mas com a Priscila dentro isso agora custa.

### Disposição para o back e uso de IA

- ✅ **Forte:** aceita sem hesitar, cita caso real de stack nova com prazo curto, e
  descreve uso crítico de IA — o que revisa, o que não delega, e um caso em que ela
  o levou para o buraco. Sabe dizer como valida o que não domina: teste, leitura de
  contrato, par com quem domina.
- **Calibração dos dois extremos já vistos:** o Jean disse *"escrevo quase nada de
  código"* e paraleliza quatro terminais, mas fixou que *"a IA não vai tomar decisão
  por você"*. O Manolo está trocando de emprego por ter virado *"leitor de
  documentação"*. Os dois extremos têm risco. O que você quer ouvir é critério, não
  entusiasmo nem rejeição.

### Mentoria e onboarding

- ✅ **Forte:** exemplo real com resultado concreto, e um método para se colocar em
  dia sozinho num produto sem documentação.
- 🚩 Fraca: genérico. **Foi assim com os dois** — se ele também for, o item deixa de
  ser diferenciador e some da decisão.

### Trajetória

- ✅ Forte: motivo claro para sair aos 5 meses — contrato de consultoria com prazo,
  não instabilidade.
- 🚩 Fraca: pula de oportunidade sem critério.

---

## Nota de decisão — o que essa entrevista realmente resolve

O comparativo de julho colocava o gap de backend como o problema dele. **Não é mais
o problema** — com o critério revisado em 05/08, mede-se disposição, não domínio.

E o foco da vaga é o **WL 2.0 em Next**, não o legado. Isso reposiciona tudo: o
Module Federation do Banco Inter deixa de ser o trunfo e vira contexto. O que
importa é outra coisa — ele constrói **checkout em Next hoje, para uma das maiores
plataformas de pagamento do mundo**. Produto financeiro novo, em Next, com dinheiro
passando. É a coisa mais parecida com o trabalho da vaga que existe no funil.

Então a entrevista tem uma pergunta só, e todas as outras são apoio:

> **O Next dele é de produção ou de currículo?**

Porque esse é o gap que **Jean e Manolo têm em comum**, e é o único eixo em que
ninguém pontuou ainda. O Jean *"não foi tão a fundo"* e usa SvelteKit. O Manolo tem
App Router só em projeto pessoal — o profissional dele foi Page Router há anos.

- **Se o Next dele for de produção, com App Router e Server Components rodando num
  fluxo de pagamento:** ele é o nome mais forte do funil, com folga, e a decisão
  passa a ser de preço e presencialidade.
- **Se for raso:** ele empata com os outros dois no eixo que decide — e aí o Manolo
  entrega o mesmo por R$ 13-14k, e o Jean entrega mais coisa por R$ 25k.

> [!success] Respondido em 06/08 — **é de produção**
> App Router e Server Components rodando no checkout do PayPal, e ele trabalha
> especificamente do lado servidor. A decisão passou a ser de preço e
> presencialidade, como previsto — e nos dois ele passa limpo.

---

# Resultado da Entrevista — 06/08/2026

**Duração:** 1h24m38s, só vocês dois, sala "Oportunidade Swap".
**Fonte:** transcrição completa com falas.
**Proporção:** ele falou 978 vezes, você 643. Proporção certa para entrevista.
**Veredito:** **o nome mais forte do funil, com folga, e o mais barato dos dois
viáveis.**

## O que decidiu a favor

**App Router em produção — o eixo da vaga, e ele é o único.** Trabalha no checkout
do PayPal, especificamente no **server side**: intercepta requests, enriquece com
dados e envia ao framework de observabilidade. Construiu a integração com Datadog e
um dashboard automatizado a partir de eventos emitidos pela aplicação Next. Critério
de separação claro — gerenciamento de dado e integração externa no server component,
renderização no client.

O [[Processo Seletivo — Jean Ribeiro]] disse *"não foi tão a fundo ainda"* e usa
SvelteKit. O [[Processo Seletivo — Manolo Pina]] só tem App Router em projeto
pessoal.

**Razor e .NET, que ninguém esperava.** Primeiro emprego, software de qualidade para
a linha de montagem da Fiat/FCA. É o único dos três com contato real com a stack do
nosso legado.

**A melhor resposta das três entrevistas foi sobre não deixar o produto apodrecer:**

> *"O React é um framework muito pouco engessado. (…) A estrutura inicial ela não
> pode mudar, porque é isso que vai fazer o produto ser escalado daqui a 10 anos."*

Defende estabelecer arquitetura inicial, documentar e seguir. Usa container/
presentation. O Manolo, na mesma pergunta, respondeu *"no olho mesmo"*. É diretamente
aplicável à V2, que está sendo construída agora.

**Testes — ele implantou o processo, não só pratica.** Jest, Storybook e Playwright
no PayPal, com pre-commit hook e step de pipeline validando. Escreve o E2E ele
mesmo. E levou o mesmo processo para o Banco Inter. *"Por isso é difícil chegar bug
crítico em produção."* É o que a [[Priscila Campos]] veio construir aqui.

**Liderança — o único dos três que já fez e quer fazer.** Contratado no Inter como
líder técnico, liderou cinco pessoas por seis a sete meses, puxava planning, daily,
grooming e review. Mentorou uma estagiária na Braskem até ela entregar sozinha. **Já
fez entrevista técnica de front.** Resolve o gargalo de onboarding, que hoje é o
[[Gabriel Santi]].

**Module Federation no Inter, com detalhe que prova execução.** Monolito de front com
três times de cinco pessoas no mesmo repositório, conflito de entrega e gargalo de
dependência. Usou shared scope para compartilhar bibliotecas e reduzir bundle, e
criou um layer de cache com React Query para compartilhar dado entre microfronts.

**IA — a posição mais madura dos três.** No Inter puxou projetos de IA e implantou
**memory bank** para reduzir consumo de token, com arquivo MD por projeto. Hoje usa
Claude Code. Trata IA como ferramenta com custo a gerenciar — nem o entusiasmo do
Jean (*"escrevo quase nada de código"*) nem a rejeição do Manolo.

## Onde ficou abaixo

- **Design system é o ponto mais fraco, e é o que mais pesa agora.** Resposta
  genérica: depende do projeto, MUI é pesada, Tailwind dá mais trabalho mas reduz
  bundle. **Não citou design token, nem distribuição versionada, nem Storybook como
  base de design system.** Fica atrás do Jean, que deu headless + tokens + GitHub
  Packages. E a base da V2 se decide uma vez só.
- **O checkout dele é observabilidade, não fluxo de pagamento.** Foi honesto: *"eu
  nunca mexi nessa parte específica de integração com pagamento"*. Domina evento,
  tracking de jornada, dado de conversão e deduplicação de evento. É fintech em
  escala real, mas não é o que o currículo sugeria.
- **Incidente de produção é o item mais fraco.** O exemplo é antigo (loop de
  `useEffect` disparando e-mail repetido na Braskem) e ele mesmo disse *"não lembro
  ao certo o que eu fiz"*. Foi honesto ao dizer que no Inter e no PayPal quase não há
  incidente crítico, porque há muitos steps de validação. Corta dos dois lados: menos
  cicatriz, mas vem de ambiente onde isso não acontece e sabe por quê.
- **Performance sem número.** Deu causa raiz e ação — paginação, renderizar só o
  visível, bundle, tree shaking — mas nenhuma métrica antes e depois.
- **Não conhece Mantine.** Igual aos outros dois.

## Números

- **PJ: R$ 18.000.** CLT: R$ 14,5-15k. Prefere PJ, já tem a empresa estruturada.
- Disse estar **disposto a conversar** sobre o budget: *"achei a vaga bem
  interessante"*.
- **Custa 28% menos que o Jean (R$ 25k) e entrega mais.**
- **Presencialidade resolvida:** remoto por preferência, vai a São Paulo sem
  problema, offsite tranquilo. Mora em Conselheiro Lafaiete, perto de BH.
- ✅ **Disponibilidade: uma semana** — respondido por mensagem em 06/08, depois da
  call. É o mais rápido dos três (Jean pede duas semanas).

## Por que ele está saindo

O **PayPal está em reestruturação e as consultorias alocadas estão ameaçadas**. Ele
sabe que não fica muito mais tempo e começou a olhar o mercado por isso. É motivo
externo com data, não instabilidade — resolve a dúvida dos cinco meses no cargo
atual.

## Como você foi

**Você aplicou o aviso do roteiro e contou o cenário cru.** Tombamento de 80 mil
contas, terceiro dia de war room, Razor, os 26 mil registros, a especialista de
qualidade entrando. E foi além do previsto: contou as **oito saídas**, que parte
delas foi por não entregar, e que o Helper é o ofensor de hoje. Nada do *"máquina
redondinha"* que o Jean ouviu em julho.

**Cobriu quase o roteiro inteiro** e deixou o candidato falar mais que você.

**Quatro coisas escaparam, e três são as mesmas da entrevista do Manolo:**

- **Não devolveu o cenário do Razor como pergunta.** Contou o problema e não
  perguntou *"por onde você começaria?"*. Era o item que separava.
- **Não aprofundou design system** — justamente o ponto fraco dele.
- **Não pediu número na performance.**
- **Não fechou a disponibilidade.**

**E um detalhe de negociação:** você disse *"tecnicamente falando, para mim é o que
eu tô precisando aqui"* **antes** de saber a pretensão. Deu certo porque ele pediu
R$ 18k — mas se tivesse pedido 25k, o interesse já estava entregue.

## Ponto a alinhar

Você contou a ele: *"nós estamos parando o time aqui, vamos ficar um período sem
entrega, para cuidar da qualidade do produto"*. É exatamente a ideia que a
[[Priscila Campos]] recusou em 04/08 — *"não é sobre parar, é sobre construir
acordos daqui em diante"* — e que você tinha abandonado na hora, em favor do
mecanismo dela. Vale alinhar qual das duas vale, antes que a versão errada circule.

## Próximos passos

- [x] ~~Perguntar a disponibilidade de início~~ — **respondido em 06/08: uma semana**
- [ ] **Falar com a Célia hoje para agendar a conversa de perfil, com pedido de agilidade** — ele está no PayPal em reestruturação e olhando o mercado; é o candidato com maior risco de ser levado por outro processo
- [ ] Aprofundar design system: design token, distribuição, versionamento — é o gap real dele e vai definir a base da V2
- [ ] Devolver o cenário do portal Razor: *"por onde você começaria?"*
- [ ] Definir o modelo de contratação, já que ele prefere PJ e a pretensão CLT é bem menor
- [ ] Decidir entre ele e o Jean antes de o Jean reaparecer (ou não) do RH
