# Processo Seletivo — Manolo Pina | 05/08/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que **se disponha** a tocar back quando
precisar — **não precisa ser full-stack de fato** (critério revisado por você em
05/08: com IA no fluxo, atuar em duas frentes deixou de ser barreira)
**Indicação:** **Samir** → [[Stive Tormes]] → você. O Samir é quem indicou; o Stive
só passou o nome adiante (ver correção abaixo).
**Status:** ✅ Entrevistado em 05/08/2026. Aguarda decisão e etapa técnica.
**Fonte:** export de perfil do LinkedIn (`Profile.pdf`, 05/08/2026) + transcrição
da entrevista de 05/08 (`Oportunidade Swap - 2026_08_05 15_58 - Transcript.docx`)

---

## Perfil

- **LinkedIn:** linkedin.com/in/manolopina
- **Localização:** Guarulhos, São Paulo
- **Headline:** Software Developer: React.js, React Native & Node.js | TypeScript | Full-Stack, Mobile & Web
- **Experiência:** 10+ anos declarados (trajetória desde 2011)
- **Stack:** React, Next.js, TypeScript, Node.js/Express, MongoDB; Angular e AngularJS no histórico; PHP/Laravel/MySQL no início de carreira
- **Top skills que ele mesmo destaca:** **desenvolvimento orientado por especificações**, **Module Federation**, **Zustand**
- **Idiomas:** português nativo, inglês profissional completo, espanhol básico
- **Formação:** FIAP — Gestão de Sistemas de Informação (2014–2018); FMU — Tecnologia em Sistemas para Internet (2013–2014)
- **Certificações:** MongoDB, Angular (duas), Programação Reativa, SEO

**Trajetória**

| Empresa | Papel | Período |
|---|---|---|
| Source2IT | Software Developer | set/2025 – atual |
| Copastur Viagens e Turismo | Frontend Developer | jan/2024 – fev/2025 |
| IS Entrega | Frontend Developer | abr/2020 – jan/2024 (3a10m) |
| Evolution Virtual | Front-end Developer | ago/2019 – fev/2020 |
| Brate | Front-end Developer | mar/2018 – jul/2019 |
| Mooven Consulting | Front-end Developer | jan – mar/2018 |
| Gauge | Front-end Developer | jun/2017 – fev/2018 |
| Editora Positivo | Full Stack Developer | ago/2015 – jan/2017 |
| Agência Carnaval | Back-end Developer | mai – jul/2015 |
| 18digital | Full Stack Developer | dez/2013 – out/2014 |
| Mirago | Front-end Developer | abr – mai/2012 |
| VENONE | Web Designer | dez/2011 – mar/2012 |

## Por que interessa

**Ele é o único candidato cujo currículo bate com o problema que o time tem hoje,
não com o perfil abstrato da vaga.** Três coisas, na ordem de importância:

1. **Migração de código legado e redução de dívida técnica** aparecem como
   especialidade declarada. Isso é exatamente o que o [[Gabriel Santi]] está
   fazendo à mão no portal — convertendo tela de Razor para React — e o que ele
   defendeu na [[War Room Niky — 04-08-2026]] como única solução definitiva para o
   legado.
2. **Otimização de performance** (Core Web Vitals, Lighthouse) e **design system**
   (Storybook, Shadcn). A tela que travou com 26 mil registros na Qualicorp é
   sintoma dessa classe de problema, e o Stive já disse que nunca houve teste de
   carga no sistema.
3. **Module Federation** como top skill. Nenhum dos outros quatro menciona
   micro-frontend, e isso é diretamente relevante para o WL 2.0 conviver com o
   legado em vez de esperar o big bang — o cenário que você descreveu à Priscila
   como "dois sistemas que não precisam conviver, mas convivem".

Somando: **"desenvolvimento orientado por especificações"** como skill em
destaque sugere fluxo spec-first, provavelmente assistido por IA. O uso de IA no
fluxo é critério do comparativo e diferencial da vaga, e hoje só o João Firmino
pontua nele.

### A indicação é do Samir, não do Stive — e isso vale mais, não menos

> [!warning] Corrigido em 05/08/2026, pela entrevista
> Esta seção dizia que o [[Stive Tormes]] indicou o Manolo e que isso lhe daria um
> padrinho natural para a integração. **Errado.** Na entrevista você perguntou
> *"você conhece o Steve?"* e ele respondeu **"não"**. O Stive foi só o carteiro.

**Quem indicou foi o Samir — que ocupou a sua cadeira antes de você.** Ele foi head
do White Label na Swap. E não conhece o Manolo de corredor: foi o Samir quem
**entrevistou e contratou** o Manolo para a consultoria onde os dois trabalharam,
e depois sentou na mesma squad como back do front dele, na refatoração do sistema
da **MRV**.

Isso torna a indicação a mais qualificada do funil — e o funil tem poucas. O Jean
veio por indicação do [[Túlio Cruz Ferreira da Silva]]; o
[[Processo Seletivo — Lucas Verdan]] veio da triagem do RH, sem indicação nenhuma.
A do Samir é de outra natureza: casa **um profissional que ele avaliou pessoalmente
com uma cadeira que ele mesmo ocupou**.

**O caveat:** o Samir indicou para a vaga como ele a conheceu. Ele não viu o
tombamento da Niky, não sabe da tela que trava com 26 mil registros, não sabe que a
[[Priscila Campos]] entrou nem que "nada sobe sem teste" virou acordo. A leitura
dele é do perfil de julho.

**A ligação que vale mais que qualquer PDF ou entrevista técnica.** Perguntar ao
Samir três coisas, e a primeira é a mais importante:

1. **O Manolo segura a linha ou recua?** Ele contou na entrevista que o back passou
   a devolver 40 mil registros num autocomplete depois que o Samir saiu, que ele
   levantou o problema e depois *"deixou quieto"*. O Samir estava lá antes disso e
   sabe se isso é padrão ou foi uma organização ruim.
2. **O que foi a migração da MRV de fato**, já que na entrevista ela virou troca de
   biblioteca.
3. **Conhecendo esta cadeira e conhecendo o Manolo — ele é o cara para o cenário de
   agosto?** Legado grande, performance péssima, migração para a 2.0 sem parar o
   produto.

## Gaps a validar

- **Zero .NET/C#.** O backend dele é Node/Express, com PHP/Laravel no começo da
  carreira. **Deixou de ser bandeira vermelha** com o critério revisado em 05/08: o
  que se valida agora é disposição de pegar o ticket, não domínio prévio. Ainda
  assim é curva real, e vale medir a disposição com pergunta concreta, não
  declaração genérica.
- **🚩 Nenhum domínio de fintech ou meios de pagamento.** A trajetória é turismo,
  logística de entrega, educação, agências. É o candidato com menos aderência de
  negócio dos cinco — pior que o Felipe Vasconcelos nesse quesito, porque o dele
  ao menos era enterprise.
- **🚩 Lacuna de 7 meses** entre a saída da Copastur (fev/2025) e a entrada na
  Source2IT (set/2025), sem explicação no perfil.
- **React Native está na headline e não aparece em nenhuma descrição de cargo.**
  Todas as experiências descritas são web. Vale confirmar se o mobile é real ou
  aspiracional.
- **Empresas pouco conhecidas e sem escala declarada.** Nenhum número de usuário,
  volume ou criticidade aparece no perfil. O "colchão de reputação" é baixo, como
  no caso do Felipe Vasconcelos.
- **Source2IT é consultoria.** Vale entender o que ele faz de fato lá e para qual
  cliente — um ano em body shop pode significar projeto sério ou alocação rasa.
- **Início de carreira muito picado** (2 a 4 meses em várias casas até 2018). A
  partir de 2018 a permanência melhora, e a IS Entrega mostra 3 anos e 10 meses —
  o que importa é a tendência, e ela é boa.
- **Testes:** Jest e Cypress aparecem em "key skills", nenhuma descrição de cargo
  menciona teste. Dada a entrada da Priscila Campos e o acordo de que nada sobe
  sem teste, isso deixou de ser desejável e passou a ser requisito.
- **CQRS, DDD, Clean Architecture** não aparecem.

---

## Roteiro do bate-papo

> Formato: bate-papo de ~55 min. A entrevista técnica com o [[Gabriel Santi]] vem
> depois — e vale saber que ela **nunca aconteceu com nenhum candidato**, nem com
> o [[Processo Seletivo — Jean Ribeiro]]. **Duas decisões de desenho:** o modelo de trabalho
> entra nos primeiros dez minutos, porque foi o que derrubou três candidatos; e o
> momento do time é contado sem maquiar, que é o que funcionou na conversa com a
> [[Priscila Campos]].

### 1. Abertura
- Como você conhece o Stive? Trabalharam juntos onde, em quê?
- O que ele já te contou sobre o time e sobre a vaga?
- Conta o que você faz hoje na Source2IT: é alocação em cliente? Qual produto, e
  qual o seu escopo?
- Você se descreve como full-stack, e as descrições de cargo são quase todas de
  front. Me conta uma entrega recente em que você fez as duas pontas — o que era
  back de verdade ali?

*Se ele já sabe muito pelo Stive, descubra o que foi prometido antes de enquadrar.*

### 2. O momento, dito sem maquiar

Conte o real: tombamento de 80 mil contas no sábado, dois dias de war room, portal
legado com tela que carrega 26 mil registros e trava, um produto novo em construção
que precisa substituir o legado sem parar nada, e uma especialista de qualidade
entrando agora porque não há teste unitário nem teste de carga.

- Isso te atrai ou te assusta? Responde sincero.

*Quem se anima com "legado grande e dívida acumulada" é o perfil. Quem hesita aqui
vai hesitar em produção.*

### 3. Modelo de trabalho — cedo de propósito
- Como você trabalha hoje, e como prefere: presencial, híbrido, remoto?
- Você mora em Guarulhos — vir ao escritório com que frequência é confortável?
- Uma vez por ano tem offsite de dois dias fora. Isso é problema?

*Ouvir, não prometer: a exigência real de presencialidade ainda não foi fechada com
a Célia e o Vini.*

### 4. Migração de legado — o motivo real do interesse
- Você cita migração de código legado como especialidade. Me conta a maior que
  você fez: o que era o legado, qual a estratégia, e o que deu errado no caminho.
- Você migrou incrementalmente ou fez big bang? Como decidiu?
- **Cenário real nosso:** temos um portal legado em Razor, com telas que carregam
  26 mil registros de uma vez e travam, e um produto novo em construção que deve
  substituí-lo. Não podemos parar nenhum dos dois. Por onde você começaria?
- Onde entra o Module Federation nessa conversa? Você já colocou micro-frontend em
  produção, ou é conhecimento de estudo?

### 5. Front-end na nossa stack

*Mesmos pontos que foram aferidos no [[Processo Seletivo — Jean Ribeiro]], de
propósito: dá para comparar os dois lado a lado depois.*

**Estado e dados**
- Zustand é uma das suas três principais skills. Onde você usa e onde você não usa?
- Como você separa estado de cliente de estado de servidor? Usa React Query, SWR,
  ou resolve no Zustand também?

**Next.js**
- Seu uso é mais Pages Router ou App Router?
- Já trabalhou com Server Components e Server Actions em produção, ou o
  entendimento é conceitual?

**UI kit — o gap provável**
- Já usou **Mantine**? É o nosso principal UI kit.
- Você cita Shadcn e Storybook. Me conta o design system que você construiu ou
  manteve: era headless? Tinha design token? Como distribuía para os projetos?

**Performance, com número**
- Você cita Core Web Vitals e Lighthouse. Qual métrica estava ruim, qual era a
  causa, o que você fez e qual o número depois?
- Já fez lista virtualizada ou paginação com volume grande? Como decide entre
  virtualizar, paginar ou resolver no backend?

**Componentização e organização**
- Como você organiza um projeto React grande — por tipo de arquivo ou por feature?
- Como você decide que um componente ficou grande demais?
- Já pegou projeto com componente de 800 linhas e prop drilling em cinco níveis? O
  que você fez?

**Testes**
- Teste faz parte do seu PR normal ou fica com QA?
- Você usa Cypress. Já usou **Playwright**? É o nosso.
- Quem escreve o E2E dos fluxos críticos no seu time hoje?

**TypeScript**
- Como você tipa resposta de API que pode vir em formatos diferentes?

### 6. Disposição de atravessar para o back, com IA no fluxo
*(critério revisado: não se busca domínio de .NET, se busca disposição real)*
- Nosso backend é .NET. Você não precisa saber .NET para entrar, mas vai pegar
  ticket lá quando a fila pedir. Como isso soa?
- Já entrou em stack que não era a sua e teve que produzir rápido? Conta como foi e
  quanto tempo levou para o primeiro PR útil.
- Como você usa IA no fluxo hoje? Quero exemplo concreto: o que você delega, o que
  você não delega, e onde já te levou para o buraco.
- Numa linguagem que você não domina, como você sabe que o código que a IA gerou
  está certo? O que você checa antes de abrir o PR?

### 7. Desenvolvimento orientado por especificações
- Você destaca isso como uma das suas três principais skills. O que significa na
  prática, no seu dia?
- Como isso muda a forma de trabalhar com quem escreve a especificação?
- E quando a especificação está errada ou incompleta — o que você faz?

### 8. Qualidade que não regride
- Como você garante que a otimização não volta a degradar depois de três sprints?
- Já fez teste de carga? Em quê?
- O que você considera cobertura mínima aceitável, e por quê?

### 9. Escala, criticidade e o intervalo de 2025
- Qual o sistema mais crítico em que você mexeu — quantos usuários, o que
  acontecia se caísse?
- Já lidou com dinheiro ou dado financeiro em produção? Regulação, auditoria,
  conciliação?
- Já entrou em incidente de produção? Conta um.
- Entre fevereiro e setembro de 2025 tem um intervalo no seu perfil. Me conta o que
  aconteceu nesse período.

*A pergunta do intervalo é direta e sem julgamento — o problema não é ter tido, é
não conseguir falar dele com naturalidade.*

### 10. Senioridade e time
- Você menciona mentoria e liderança técnica na Evolution Virtual. Que tipo de dev
  você ajudou a evoluir, e como?
- Nosso time hoje não tem nicho: quem entra circula entre front e back e senta na
  frente do cliente quando precisa. Como isso soa para você?
- Você chegou por indicação. O que já te contaram sobre o nosso contexto?

### 11. Fechamento
- Pretensão salarial e disponibilidade.
- Por que sair de onde está.
- O que você precisa saber de nós para decidir?

## Sinais de alerta a observar

- 🚩 Migração de legado descrita sem trade-off nem erro — quem migrou de verdade
  tem cicatriz e conta.
- 🚩 Module Federation e desenvolvimento orientado por especificações citados como
  buzzword, sem caso concreto. Se são as top skills dele, tem que haver história.
- 🚩 Relutância com .NET, ou o oposto: minimizar a curva dizendo "é tudo igual".
- 🚩 Nenhum exemplo de sistema crítico ou de escala. É o maior risco do perfil.
- 🚩 Resposta evasiva sobre a lacuna de 2025.
- ✅ Se ele responder o cenário do portal legado com estratégia incremental,
  priorização por risco e menção a medir antes e depois, isso o coloca à frente de
  todos os outros quatro no problema que o time tem hoje.

---

## Gabarito — o que esperar em cada resposta

### Migração de legado (a pergunta que decide)

- ✅ **Forte:** descreve estratégia incremental, com critério de o que migra
  primeiro (risco, tráfego, dívida), convivência das duas versões, e uma decisão
  difícil que ele tomou e não gostou. Cita como mediu se melhorou.
- Aceitável: já fez, conta bem, mas nunca com dois sistemas em produção ao mesmo
  tempo.
- 🚩 **Fraca:** "reescrevemos em React e ficou melhor", sem número, sem trade-off,
  sem plano de rollback.

### Module Federation

- ✅ **Forte:** rodou em produção, sabe dizer o que dói — versionamento de
  dependência compartilhada, contrato entre times, custo de build.
- Aceitável: fez em projeto próprio ou POC, e reconhece que não levou a produção.
- 🚩 **Fraca:** repete a definição sem aplicação, ou não distingue de monorepo.

### Disposição para o back e uso de IA

- ✅ **Forte:** aceita sem hesitar, cita caso real de stack nova com prazo curto, e
  descreve uso crítico de IA — o que revisa, o que não delega, e um caso em que a
  IA o levou para o buraco. Sabe dizer como valida código em linguagem que não
  domina: teste, leitura de contrato, par com quem domina.
- Aceitável: aceita e não tem caso de stack nova, mas mostra método de validação.
- 🚩 **Fraca:** duas formas opostas, e as duas contam contra. Relutância explícita,
  ou o oposto — minimizar a curva com "com IA hoje é tudo igual". A segunda é a mais
  perigosa, porque é exatamente a premissa que você está assumindo, e você precisa
  de alguém que a sustente com critério, não que a repita.

### Desenvolvimento orientado por especificações

- ✅ **Forte:** descreve fluxo concreto — spec antes de código, critério de aceite
  explícito, uso de IA para gerar a partir da spec — e sabe dizer onde isso falha.
  Isso conecta direto com o problema de o time não ter documentação de jornada de
  produto, apontado pela [[Daniela Melo]] em
  [[Alinhamento — Comunicação — 04-08-2026]].
- 🚩 **Fraca:** vira sinônimo de "eu leio a task antes de começar".

### Performance

- ✅ **Forte:** número antes e depois, ferramenta de medição, e causa raiz
  identificada — não só "coloquei lazy loading".
- 🚩 **Fraca:** só cita ferramenta sem resultado.

### Front-end na nossa stack

*A barra aqui foi definida pelo [[Processo Seletivo — Jean Ribeiro]] em 21/07 —
use como referência de comparação, não como nota de corte.*

**Estado de cliente vs. de servidor**
- ✅ Distingue os dois na primeira frase e usa ferramenta própria para cache de
  servidor (React Query, SWR).
- 🚩 Coloca resposta de API dentro do Zustand. Sinal de que nunca teve cache de
  servidor doendo.

**Next.js App Router**
- Aceitável não ter ido a fundo — foi o caso do Jean e não foi bandeira vermelha, é
  o gap mais fácil de fechar.
- 🚩 Confundir com outra coisa depois de uma explicação rápida.

**Design system — onde o Jean levantou a barra**
- ✅ **Forte:** o Jean deu biblioteca headless, design tokens e distribuição via
  GitHub Packages. Detalhe técnico real, não inflado. Essa é a referência.
- 🚩 **Fraca:** "usei o Shadcn e criei uns componentes" fica abaixo do Jean.
- Mantine: não conhecer é gap esperado — o Jean também não conhecia e isso não o
  desqualificou.

**Testes E2E — virou requisito, não diferencial**
- ✅ **Forte:** o Jean é dono da prática, está implementando o primeiro Playwright
  nos fluxos críticos e não delega para QA. Com a entrada da
  [[Priscila Campos]] e o acordo de que nada sobe sem teste, essa é a régua.
- 🚩 **Fraca:** delega 100% para QA.

**Componente de 800 linhas com prop drilling**
- ✅ **Forte:** estratégia de refatoração incremental, com critério de por onde
  começar.
- 🚩 **Fraca:** "eu reescrevo". É a mesma resposta que o vault já registra como
  padrão que não se sustenta no legado do portal.

**TypeScript**
- ✅ **Forte:** union discriminada, validação em runtime com `zod` ou equivalente.
- 🚩 **Fraca:** `any` com comentário, ou "eu tipo depois".

**Onde o Jean *não* alcançou, e o Manolo pode passar**
- Mentoria e ponte front/back: o Jean respondeu genérico, sem exemplo real. Se o
  Manolo trouxer caso concreto da liderança técnica na Evolution Virtual, é ponto em
  que ele supera o Jean — vale explorar em vez de aceitar a primeira resposta.

### Escala e criticidade

- ✅ **Forte:** um sistema com consequência real de queda, mesmo que não seja
  fintech.
- 🚩 **Fraca:** nunca teve sistema crítico. Não desqualifica, mas define o nível de
  acompanhamento que ele vai precisar nos primeiros meses — e hoje o time não tem
  quem acompanhe: o Santi é o gargalo declarado do onboarding.

## Nota de calibração

Com o critério revisado em 05/08, o quadro dele muda bastante. O gap de .NET era o
que o empatava com o Jean e o João e o colocava atrás do Felipe Vasconcelos. Se o
requisito passa a ser **disposição** em vez de domínio, sobra o que ele tem de
próprio — e o que ele tem é o mais alinhado ao problema que o White Label vive
agora: legado grande, performance ruim, dívida acumulada e uma migração para a 2.0
que precisa acontecer sem parar o produto.

Os riscos que **continuam** de pé e não são afetados pela revisão:

- **Nenhum domínio de fintech.** Nesse quesito ele é o mais fraco dos cinco.
- **Nenhuma escala comprovada.** Nenhum número de usuário ou criticidade aparece no
  perfil, e o time não tem quem faça onboarding — o Santi é o gargalo declarado.
- **A lacuna de 7 meses em 2025.**

A pergunta de decisão deixou de ser "ele cobre a stack?" e passou a ser: **a vaga é
para preencher o perfil desenhado em julho, ou para atacar o gargalo que apareceu
em agosto?** Se for a segunda, ele é o nome mais forte da lista.

**Um cuidado com a premissa da IA.** Ela é razoável e é sua, mas ainda não foi
testada aqui: a [[Priscila Campos]] acabou de dizer, em
[[Alinhamento Qualidade e Testes — Priscila Campos — 04-08-2026]], que o problema
do time é falta de processo de desenvolvimento com segurança, e que o time não tem
cultura de teste. Alguém produzindo em stack que não domina, com IA, num código sem
teste unitário e sem teste de carga, é a combinação exata que gerou os incidentes da
Niky. A premissa se sustenta **depois** que o acordo de "nada sobe sem teste"
estiver de pé — não antes. Vale entrar na entrevista sabendo disso e perguntar como
ele valida o que não domina.

---

# Resultado da Entrevista — 05/08/2026

**Duração:** 1h21m32s, só vocês dois, na sala "Oportunidade Swap" (a mesma do Jean).
**Fonte:** transcrição completa com falas.
**Veredito:** bom front-end sênior de React, honesto e barato — **mas os três
motivos que o colocaram à frente na lista não sobreviveram à entrevista.**

## O que caiu

**Migração de legado, que era o motivo do interesse.** O que ele apresentou como
migração foi troca de biblioteca dentro de um React que já existia: Material →
Shadcn, Redux → Context → Zustand, styled-components → Tailwind. Não apareceu nada
do que o gabarito pedia — convivência de duas versões, critério de o que migra
primeiro, rollback, medição antes e depois. **E o cenário do portal Razor você
contou, mas não devolveu como pergunta.**

**Module Federation — ele usa, não implantou.** Quando você perguntou como
compartilham estado entre as aplicações, ele foi honesto: *"não vou saber ser claro
com você, porque nem fui eu que configurou"*, e *"comecei a ter mais contato e
aprendizado com microfrontend agora nessa atuação mais recente"*.

**Performance — 🚩.** Core Web Vitals e Lighthouse estão no LinkedIn como skill.
Na call: *"vou ser bem sincero, não saberia dizer com precisão"* e *"não lembro
exatamente quais os parâmetros"*. O único número que deu foi build de dev de 3-5s
para 700ms com Hot Module Replacement — isso é tempo de compilação, não performance
de runtime. Não é o que trava com 26 mil registros.

## O que ficou forte

**Estado de cliente vs. de servidor — o melhor momento dele, e passa a régua do
Jean.** Zustand só para o que atravessa componentes sem relação vertical, React
Query para tudo que vem de serviço. Exemplo concreto: a sidebar de filtros que
precisa sobreviver à transição de tela. O gabarito marcava como bandeira vermelha
guardar resposta de API no Zustand — ele fez o contrário e justificou.

**Organização de código.** Feature-based, pasta de primitivos, e **query factories**
do React Query para não criar dezenas de arquivos de três linhas. Detalhe de quem
escreve código.

**Autocrítica calibrada.** *"Eu sou um front sênior, e como back estaria para um
pleno."* Admitiu ter escrito componente de 800 linhas com prop drilling ele mesmo.

**A lacuna de 2025 está resolvida.** Layoff na Copastur, depois um app React Native
com um ex-gestor que ia durar seis meses e durou um ano — não pôs no currículo para
não ter que explicar experiência curta. Contou com naturalidade, que era o critério.
Isso também confirma que o React Native da headline existe.

## O que ficou fraco

- **Anti-regressão:** *"não diria que tenho uma estratégia consolidada"*, *"meu
  pessoalmente assim é no olho mesmo"*. É o oposto do mecanismo da
  [[Priscila Campos]] — coverage travado com piso que não abaixa.
- **Playwright: não conhece.** Faz unitário e integração, já teve exigência de 80%
  de cobertura. Fica abaixo do Jean, que é dono da prática.
- **Next.js:** o uso profissional foi há anos e nem era App Router. Server
  Components e Server Actions são projeto pessoal — *"nenhum especialista"*. E o
  portal novo, onde você disse que ele vai atuar, é exatamente onde ele tem menos
  rodagem.
- **Escala e criticidade — o maior gap, confirmado.** *"Não sei se essas questões
  esbarravam tanto em mim, como front end."* Não sabe dizer usuários do sistema mais
  crítico. Nunca lidou com dinheiro em produção.
- **Lista com volume grande — a resposta certa com a atitude errada.** Já recebeu 40
  mil registros num autocomplete e disse o correto (*"o front não deveria estar
  fazendo isso"*), mas completou: *"eu até cheguei a levantar esses pontos, mas no
  final eu falei: ah, deixa quieto"*. O problema dos 26 mil só se resolve com alguém
  que não deixa quieto.
- **Negócio e comunicação:** autodeclarou gap e timidez inicial. Você discordou na
  hora. Importa porque o time senta na frente do cliente.

## O motivo de saída — risco de retenção, e inverte a leitura do LinkedIn

Ele está saindo porque **o spec-driven development virou obrigatório** onde está:

> *"Cair para algo onde eu seja mais um leitor de documentação."*
> *"Ganha muito em produtividade, absurdamente, mas perde em qualidade."*
> *"Uma coisa é a IA trabalhar para você, outra é você trabalhar para a IA."*

E **a dúvida principal dele na call foi**: *"existe também essa cultura de as coisas
virarem spec driven development? Porque hoje onde eu tô atuando, isso é
obrigatório."*

Isso inverte a leitura desta nota antes da entrevista, que contava "desenvolvimento
orientado por especificações" como sinal de fluxo spec-first assistido por IA e como
ponto a favor. **Ele listou porque é o que faz hoje — e é do que está fugindo.**

A crítica dele é madura e específica (implantaram sem projeto base, sem
reestruturação, sem ajustar devops) e você concordou na hora. Mas é risco direto
contra a premissa com que você revisou o critério da vaga em 05/08.

## Números

- **R$ 81,50/hora PJ ≈ R$ 13-14 mil/mês.** Disse estar dentro. Último CLT: R$ 10 mil.
- **Disponibilidade:** 1 a 1,5 semana.
- **Presencialidade: resolvida.** Remoto por preferência, mas topa ir eventualmente
  e o offsite de dois dias não é problema. É o único do funil que passa limpo nesse
  filtro. ⚠️ Você disse a ele *"não é uma exigência real ter presença"* — a regra
  ainda não estava fechada com a Célia e o Vini, e agora está prometida.

## Como você foi

**O roteiro funcionou e você o seguiu.** O momento contado sem maquiar —
tombamento, 80 mil contas, multa da Mastercard, dois dias de war room, a tela dos 26
mil — é a mesma jogada que deu certo com a [[Priscila Campos]]. O modelo de trabalho
entrou cedo, como planejado. A pergunta de curiosidade sobre estado compartilhado no
Module Federation foi a melhor da call: foi ela que expôs que ele não configurou
nada.

**Mas você fechou três respostas fracas com "boa".** Migração de legado, performance
e anti-regressão — o gabarito tinha critério para as três, ele ficou abaixo nas três,
e nenhuma foi confrontada.

**E entregou o enquadramento antes da resposta, várias vezes.** *"Acho que isso aí é
menor problema"* no Mantine, antes de ele responder. Completou a frase dele quando
travou na performance (*"V laser mesmo, né? Fazer o split da tela"*). No .NET,
tranquilizou (*"você não vai ficar desamparado"*) antes de medir a disposição.

**Quatro perguntas do roteiro ficaram de fora — e são as do maior risco dele:**

- Já lidou com dinheiro ou dado financeiro em produção?
- Conta um incidente de produção.
- Já entrou em stack que não era a sua? Quanto tempo até o primeiro PR útil?
- **Como você sabe que o código que a IA gerou em linguagem que você não domina está
  certo?** — o gabarito chamava essa de decisiva, e ela vale mais ainda depois de ele
  dizer que IA "perde em qualidade".

**A call durou 1h21 contra os ~55 min planejados**, e boa parte foi você explicando
Swap, momento, legado e cultura de IA. Comeu o tempo do bloco de escala e
criticidade, que é justamente onde ele é mais fraco.

## Comparação com o [[Processo Seletivo — Jean Ribeiro]]

Os dois são os candidatos reais em mão. Comparação completa na nota
[[Comparativo — Vaga Interfaces (Substituição Felipe Leal)]]. O resumo:

- **Jean é mais forte** em dinheiro em produção (diário), incidente resolvido
  sozinho de ponta a ponta, Playwright em fluxo crítico agora, design system com
  token e distribuição, e a melhor resposta de .NET possível.
- **Manolo é melhor** no código do dia a dia — estado, organização, factories — e
  custa **45% do preço** (13-14k contra 25k).
- **Empatam para baixo** em migração de legado, mentoria, App Router e Mantine.
- **Estão nos extremos opostos do eixo da IA:** o Jean *"escreve quase nada de
  código"* e paraleliza quatro terminais; o Manolo está pedindo demissão por ter
  virado leitor de documentação. A tua aposta de 05/08 depende do modelo do Jean —
  mas a Priscila acabou de dizer que produzir com IA numa base sem teste é o que
  gerou os incidentes da Niky. Não existe escolha neutra aqui.

## Próximos passos

- [ ] **Ligar para o Samir** — as três perguntas estão na seção da indicação, acima. Vale mais que a entrevista técnica
- [ ] Fazer as quatro perguntas que ficaram de fora — cabem em 20 minutos, não precisa de call inteira
- [ ] Entrevista técnica com o [[Gabriel Santi]] — nunca aconteceu com nenhum candidato
- [ ] Devolver o cenário do portal Razor como pergunta: *"por onde você começaria?"*
- [ ] Resolver a pergunta de retenção sobre IA, que é mútua: é o motivo de saída dele e a premissa da tua vaga
- [ ] Fechar com a Célia e o Vini a exigência real de presencialidade — você já prometeu a ele que não existe
- [ ] Célia vai chamá-lo para a conversa de perfil; você ficou de pedir agilidade
