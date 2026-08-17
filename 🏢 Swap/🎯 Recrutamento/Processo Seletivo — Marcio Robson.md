# Processo Seletivo — Marcio Robson | 15/07/2026

**Vaga:** Desenvolvedor(a) Full-Stack Sênior — Interfaces Swap (substituição de [[Felipe Leal]])
**Perfil buscado:** front-end especialista que tope generalizar para back
**Status:** Shortlist final (4 candidatos) — a definir após entrevistas

---

## Perfil

- **LinkedIn:** linkedin.com/in/robsonmrsp
- **GitHub:** github.com/robsonmrsp
- **Experiência:** 18 anos — Princess Cruises (atual), Ymbu Soluções, e passagem marcante pela **PagSeguro** (fintech, 33.9M clientes)
- **Stack:** Java/Spring Boot + Node.js (back) e React/Next.js/TypeScript (front) — full-stack genuíno, mas back é Java, não .NET

## Por que está na shortlist

- **Tecnicamente o mais forte e com a maior escala fintech real dos 4 finalistas** — construiu microsserviços de pagamento de alta disponibilidade para 33.9 milhões de clientes na PagSeguro.
- Full-stack de verdade, não "front que ajuda no back": arquitetura ponta a ponta em múltiplos projetos (Pizza Hut/Yum!, Princess Cruises), incluindo Kafka, event-driven, AWS.
- 18 anos de experiência, Oracle Certified Java Programmer, pós-graduação em Engenharia de Software.
- Atua bem em times distribuídos internacionais (EUA/Europa), fuso compatível com Brasil.

## Gaps a validar (é o perfil mais "arriscado" dos 4 por um motivo específico)

- **Backend é Java, não .NET** — mesmo gap do João e do Jean, mas aqui o risco é maior: ele é claramente mais back-heavy e mais sênior em back do que em front, o que é o **perfil invertido** do que vocês definiram (o time quer alguém especialista em front que tope back, não o contrário).
- Ele pode ser o melhor engenheiro dos 4 "no papel", mas se a entrevista confirmar que o front é reativo/coadjuvante pra ele, não resolve o problema estrutural que motivou a saída do Felipe Leal (nicho e dependência de back).
- Vale entender se ele topa entrar como "gente que reforça o front", já que o currículo sugere que ele prefere e domina mais o back.

---

## Roteiro de Entrevista Técnica

### 1. Abertura — calibrar o real equilíbrio front/back
- Nos seus últimos projetos (Princess Cruises, Pizza Hut), qual fração do seu tempo era front vs. back, na prática?
- Se você tivesse que escolher só uma ponta para trabalhar pelos próximos 2 anos, qual seria — e por quê?
- **(pergunta-chave)** A vaga aqui busca alguém que hoje já é forte em front e tope generalizar pro back — isso descreve você, ou seria mais justo dizer que é o contrário?

### 2. Transição para .NET (gap técnico)
- Você tem 18 anos majoritariamente em Java — já teve contato com C#/.NET?
- Como você reagiria a trabalhar em .NET no lugar de Java, sabendo que os conceitos (OOP, DI, camadas) se transferem, mas a sintaxe e o ecossistema mudam?

### 3. Front-end — aprofundar, é o ponto de maior risco
- Fala de uma decisão de arquitetura de frontend que você tomou sozinho, sem apoio de outro dev especializado em front.
- Next.js App Router, React Query, testes E2E (Playwright) — você usa isso no dia a dia ou majoritariamente entrega o que já está especificado?
- Como você se sente liderando decisões de design system ou componentização, e não só consumindo uma já pronta?

### 4. Domínio fintech (ponto forte real)
- Na PagSeguro, quais eram os desafios técnicos reais de processar pagamento em escala (33.9M clientes)? Fala de um incidente ou gargalo que você resolveu.
- Já lidou com regulação (BACEN, PCI-DSS) diretamente?

### 5. Arquitetura e padrões
- Kafka, event-driven — já é ponto forte dele, aprofundar com pergunta técnica específica: como ele lida com ordenação de eventos e idempotência?
- Multi-tenant — já trabalhou com isso?

### 6. Senioridade e fit cultural
- Como você reagiria a ser, na prática, "o back mais experiente do time" mas puxado principalmente para resolver front no dia a dia?
- Motivação para trocar de Princess Cruises (empresa internacional estabelecida) para uma fintech brasileira em estágio de crescimento?

### 7. Fechamento
- Pretensão salarial (referência dele é de mercado internacional — calibrar expectativa) e disponibilidade/fuso.

## Sinais de alerta a observar
- 🚩 **O mais importante dos 4 roteiros:** se ele responder a pergunta-chave da seção 1 admitindo que prefere claramente o back, isso não é desqualificador de competência, mas é desalinhamento direto com o que vocês definiram como necessidade. Vale decidir antes da entrevista se "o melhor engenheiro" pesa mais que "o encaixe de perfil".
- 🚩 Front tratado como "o que sobra fazer" nas respostas, não como área de interesse genuíno.
- ✅ Se ele demonstrar entusiasmo real em se aprofundar em front (não só capacidade), isso muda a leitura — ele teria o teto técnico mais alto dos 4.


---

## Gabarito — O que esperar em cada resposta

### 1. Abertura — a pergunta mais importante de toda a rodada de entrevistas

**"Qual fração do seu tempo era front vs. back, na prática?"**
- ✅ Resposta honesta com números concretos (ex: "70% back, 30% front" ou o inverso) — o valor em si importa menos que a honestidade e a clareza.
- 🚩 Resposta evasiva ou "50/50 sempre" repetido para todo projeto — parece resposta calibrada pra agradar, não realidade.

**"Se tivesse que escolher só uma ponta"**
- Esta é a pergunta mais reveladora do processo inteiro. Preste atenção não só na resposta, mas na hesitação.
- Se ele disser "back" com convicção → isso não desqualifica a competência dele, mas indica desalinhamento direto com o que vocês definiram como necessidade real do time.
- Se ele disser "front" ou "não teria dificuldade em focar no front" com exemplos que sustentem isso → maior sinal positivo possível pra esse candidato específico.

**Pergunta-chave direta ("isso descreve você, ou seria mais justo dizer que é o contrário?")**
- ✅ Forte: autoavaliação honesta, mesmo que a resposta seja "sou mais back, mas toparia focar mais em front porque X" — sinceridade aqui vale mais que a resposta "certa".
- 🚩 Fraca: nega qualquer preferência quando o currículo e a trajetória (18 anos, maioria back/Java) sugerem fortemente o contrário — resposta pouco crível gera mais dúvida que confiança.

### 2. Transição para .NET

- ✅ Forte: reconhece que a sintaxe muda mas os conceitos (DI, camadas, testes) se transferem — mostra maturidade de quem já trocou de linguagem antes (Java → Node, por exemplo, já está no currículo).
- 🚩 Fraca: resistência ou desconforto claro.

### 3. Front-end — seção de maior risco, validar com rigor

- ✅ Forte: cita pelo menos um exemplo de decisão de arquitetura de frontend tomada com autonomia real, não apenas execução.
- 🚩 Fraca: front aparece sempre como "eu também fiz o front quando precisava", nunca como área de domínio ou interesse — confirma o risco de nicho invertido.
- Pergunta sobre liderar design system: resposta sincera de "nunca fiz isso, meu foco sempre foi back" não é desqualificador, mas é dado real pra decisão final.

### 4. Domínio fintech (ponto mais forte dele — aprofundar bastante)

- ✅ Forte: detalhe técnico real sobre escala (33.9M clientes), menciona desafios concretos (throughput, consistência, particionamento) — deve ser a parte da entrevista onde ele brilha mais.
- 🚩 Fraca (improvável, mas atenção): respostas vagas aqui seriam bandeira vermelha grande, já que é o ponto mais forte do currículo.

### 5. Arquitetura e padrões (Kafka, event-driven)

- ✅ Forte: menciona ordenação de eventos, idempotência, ou particionamento com propriedade técnica real.
- 🚩 Fraca: cita os termos sem conseguir aprofundar.

### 6. Fit cultural e motivação

**"Reação a ser 'o back mais experiente' mas puxado pro front no dia a dia"**
- ✅ Forte: entusiasmo real, ou pelo menos abertura genuína, sem soar como concessão forçada.
- 🚩 Fraca: desconforto visível ou resposta que soa como "toparia, mas não é o que eu queria fazer" — sinal de possível frustração futura no cargo.

**Motivação para sair de empresa internacional estabelecida**
- ✅ Forte: motivo claro e específico (ex: quer voltar a atuar mais perto do produto, quer trabalhar em português, busca outro tipo de desafio técnico).
- 🚩 Fraca: motivo vago ou puramente financeiro sem mais contexto — não é desqualificador, mas didaticamente importante pra saber o que reter futuramente.

## Nota importante — decisão estratégica, não só técnica
Este candidato é o único dos 4 onde o gabarito não é "resposta certa vs errada" — é sobre **honestidade de autoavaliação**. Ele pode ser o melhor engenheiro dos quatro e ainda assim ser a escolha errada se a resposta da seção 1 confirmar que ele é fundamentalmente um especialista de back que tolera front, não o inverso. Decida antes da entrevista: se ele confirmar esse padrão, vocês toparão contratar "o melhor engenheiro" mesmo fora do perfil, ou vão priorizar o encaixe de perfil sobre o teto técnico?
