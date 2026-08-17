# Processo Seletivo — Felipe Vasconcelos | 15/07/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que tope generalizar para back
**Status:** Shortlist final (4 candidatos) — a definir após entrevistas

---

## Perfil

- **LinkedIn:** linkedin.com/in/felipe-vasconcelos-324905179
- **Experiência:** 6+ anos — Jmak Tecnologia (atual), Framework Digital, Koode (Tech Lead .NET), 4MK Solutions
- **Stack:** .NET Core/.NET Framework + React.js/Next.js — as duas pontas, todos os dias, em várias empresas seguidas

## Por que está na shortlist

- **Único dos 4 finalistas que já vive nas duas stacks obrigatórias da vaga (.NET + React) simultaneamente e no dia a dia** — nas últimas 3 empresas ele descreve explicitamente "Backend: .NET Core | Frontend: React.js" como o próprio título do cargo.
- Domínio real de arquitetura: DDD, TDD, CQRS, arquitetura hexagonal, SOLID — bate diretamente com "Arquitetura & Padrões" da vaga.
- Já foi Tech Lead .NET (Koode), com experiência liderando time.
- Experiência com Azure Functions, Service Bus, mensageria — adjacente ao requisito de mensageria/eventos assíncronos (SQS/SNS/RabbitMQ, embora ele use Azure em vez de AWS).

## Gaps a validar

- **Nenhuma experiência de domínio fintech explícita** — projetos são mais genéricos (CRM, RPA, sistemas web diversos), diferente do Jean/João que têm pagamentos/bancos no currículo.
- Sem menção a liderança de front-end (design system, mentoria, acessibilidade) — parece mais "consegue fazer as duas pontas" do que "especialista em uma, forte na outra".
- Empresas menores e menos conhecidas — mais difícil calibrar o nível real de exigência técnica que ele enfrentou.
- Não menciona Next.js App Router, React Query, testes E2E explicitamente.
- Trajetória com trocas de emprego frequentes (quase todo ano) — vale entender o motivo.

---

## Roteiro de Entrevista Técnica

### 1. Abertura
- Você é um dos poucos perfis que já trabalha em .NET e React ao mesmo tempo há anos — como é o seu dia a dia real? Você troca de contexto entre back e front na mesma sprint, ou são períodos separados?
- Na Koode você foi Tech Lead — como era a dinâmica de decisão técnica ali?

### 2. Backend (.NET) — já é ponto forte, aprofundar
- Me fala de uma decisão de arquitetura hexagonal ou CQRS que você tomou — qual problema ela resolveu?
- Como você lida com mensageria assíncrona (Service Bus/RabbitMQ)? Já teve que lidar com falha de entrega ou reprocessamento?
- Experiência com AWS especificamente (a vaga usa AWS, você tem mais experiência em Azure) — você se sente confortável migrando de nuvem?

### 3. Front-end — validar profundidade e liderança
- Você lidera decisões de arquitetura de frontend, ou majoritariamente executa specs já definidas?
- Já liderou ou participou da criação de um design system ou biblioteca de componentes compartilhada?
- Next.js App Router / Server Components — já usou? Testes E2E fazem parte do seu fluxo?

### 4. Domínio de negócio (gap principal)
- Nenhum dos seus projetos anteriores parece ser fintech especificamente — como você se sente entrando num domínio de pagamentos corporativos, benefícios e carteiras digitais, com exigências de compliance (LGPD, BACEN)?
- Já teve que lidar com dados sensíveis ou regulação de algum tipo em outro domínio (mesmo que não financeiro)?

### 5. Arquitetura multi-tenant e escala
- Algum dos sistemas que você construiu era multi-tenant (múltiplos clientes com configuração própria)? Como isso era resolvido?
- Kubernetes/Helm — teve contato?

### 6. Trajetória e motivação
- Percebo trocas de empresa relativamente frequentes — o que te fez sair de cada uma? O que você busca agora que ainda não encontrou?
- Como você reagiria a um time que hoje tem mais front do que back rodando, precisando de alguém para equilibrar as duas pontas?

### 7. Fechamento
- Pretensão salarial e disponibilidade.

## Sinais de alerta a observar
- 🚩 Dificuldade em detalhar decisões técnicas próprias (pode indicar execução de spec, não autoria de arquitetura)
- 🚩 Desconforto ao ser questionado sobre as trocas frequentes de emprego, sem explicação clara
- ✅ Facilidade real em transitar de contexto entre back e front na mesma conversa — reforça o principal diferencial dele


---

## Gabarito — O que esperar em cada resposta

### 1. Abertura (dia a dia real entre .NET e React)

- ✅ Forte: descreve com naturalidade como alterna contexto entre back e front na mesma sprint/dia, com exemplo técnico específico de cada lado.
- 🚩 Fraca: resposta genérica, ou fica claro que uma das pontas é claramente secundária/mais fraca na prática (ex: "no front eu só ajusto CSS quando precisa").

**"Dinâmica de decisão técnica na Koode (Tech Lead)"**
- ✅ Forte: descreve processo real de decisão (discussão com o time, critérios usados, como ele arbitrava desacordos).
- 🚩 Fraca: "eu decidia tudo sozinho" sem menção a colaboração — pode indicar dificuldade de trabalhar em time maior ou mais maduro.

### 2. Backend .NET (ponto forte — aprofundar de verdade)

- ✅ Forte: explica com propriedade uma decisão de CQRS/hexagonal, incluindo o problema que ela resolvia e o trade-off (ex: mais complexidade em troca de testabilidade/desacoplamento).
- 🚩 Fraca: cita os termos mas não consegue explicar o "porquê" além do que está no currículo — sinal de que o currículo pode estar mais polido que o conhecimento real.
- ✅ Forte (mensageria): menciona reprocessamento, idempotência, dead-letter queue ou conceito equivalente.
- Sobre AWS vs Azure: resposta ideal é conforto genuíno em aprender o equivalente AWS (ex: "Service Bus é parecido com SQS, já vi a documentação").

### 3. Front-end — o ponto mais importante de validar

- ✅ Forte: cita decisão de arquitetura de frontend tomada por iniciativa própria (ex: escolha de padrão de state management, estrutura de pastas, ou API design de componente).
- 🚩 Fraca: front aparece só como "implementei o que o design/PM pediu" — reforça a suspeita de que ele é mais back do que front na prática.
- Sobre design system: se ele nunca liderou um, não é desqualificador — mas pergunte se ele já *usou* um construído por outros e o que faria diferente, pra avaliar critério técnico mesmo sem ter liderado.

### 4. Domínio fintech (gap real, sem histórico no currículo)

- ✅ Forte: mesmo sem experiência direta, demonstra que já pensou sobre implicações de lidar com dados sensíveis/dinheiro (ex: idempotência em transação, auditoria, cuidado extra em testes).
- 🚩 Fraca: trata o domínio como "só mais um CRUD", sem reconhecer que fintech tem exigências diferentes (compliance, auditoria, criticidade de bug).

### 5. Arquitetura multi-tenant e escala

- ✅ Forte: mesmo sem ter feito multi-tenant, entende o conceito e propõe uma abordagem razoável quando perguntado.
- 🚩 Fraca: nunca ouviu falar do conceito.

### 6. Trajetória e motivação (ponto sensível — trocas frequentes)

- ✅ Forte: explica com transparência os motivos de cada troca (ex: empresa pequena que não tinha crescimento, contrato por projeto que terminou) — motivos concretos e verificáveis.
- 🚩 Fraca: respostas evasivas, ou padrão de "a empresa não me valorizava" repetido em todas as saídas — pode indicar dificuldade de adaptação ou de permanência.

## Nota importante
Este é o candidato com o menor "colchão" de reputação (empresas pouco conhecidas, sem grandes marcas no currículo) — o peso da entrevista aqui é maior que nos outros 3, porque há menos sinal externo (nome de empresa, escala do produto) pra validar o que ele diz. Preste atenção redobrada em profundidade técnica real vs. resposta decorada.
