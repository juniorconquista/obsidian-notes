# Entrevista — Jean Ribeiro | 21/07/2026

**Vaga:** Frontend Sênior — Interfaces Swap
**Indicação:** Túlio Cruz
**Entrevistador:** Junior Oliveira

---

## Perfil Geral

Desenvolvedor frontend com ~8 anos de experiência. Background forte em React, TypeScript e Next.js. Trabalhou em projetos de grande escala. Comunicativo, articulado e demonstrou boa capacidade de raciocínio técnico durante a entrevista.

---

## Pontos Fortes

- Sólido em React + TypeScript — respondeu com segurança sobre hooks, performance e padrões de componentização
- Experiência com Next.js App Router — conhece Server Components e Server Actions
- Boa visão de arquitetura frontend — falou sobre separação de responsabilidades e organização por features
- Comunicação clara — explicou conceitos complexos de forma acessível
- Demonstrou interesse genuíno no produto e no contexto da Swap

## Pontos de Atenção

- Nunca trabalhou em fintech — contexto de compliance, regulação e dados sensíveis é novo para ele
- Pouca experiência com testes E2E (Playwright) — usou mais testes unitários no passado
- Não conhece Mantine — principal UI kit do projeto

---

## Leitura de perfil do Santi — não houve entrevista técnica

> [!warning] Corrigido em 05/08/2026
> Esta seção se chamava "Avaliação Técnica (Santi)" e dizia "aprovado
> tecnicamente", e o título da nota era "Entrevista Técnica". **Nada disso
> aconteceu.** O [[Gabriel Santi]] viu o perfil e gostou — nada além disso. A
> conversa de 21/07 foi só você e o Jean, como a lista de participantes da
> transcrição mostra.

O que o Santi disse, e é só isso: achou o perfil sólido para o nível sênior,
com curva de aprendizado esperada nas especificidades do projeto e sem
impedimento. É leitura de currículo.

**A etapa técnica está pendente, e está pendente para todo mundo.** Nem o Jean
nem o [[Processo Seletivo — Manolo Pina]] foram avaliados por alguém além de
você. Enquanto isso não mudar, comparar os dois é comparar duas leituras suas
de conversa — e nos dois casos a migração de legado prometida pelo currículo
caiu na entrevista, que é justamente o que uma técnica com o Santi mediria.

---

## Decisão

- [ ] Avançar para próxima etapa
- [ ] Reprovar
- [ ] Aguardar outros candidatos para comparar

---

## Próximos Passos

- [ ] Junior alinha com Célia sobre próximos passos do processo
- [ ] Dar retorno ao Jeean


---

## Resultado da Entrevista Técnica — 21/07/2026

**Participantes:** Junior Oliveira, Jean Ribeiro (transcrição completa via Gemini/Google Meet)
**Avaliação geral: Sólido e aprovável, não excepcional.** Confirmou os pontos fortes do currículo em quase tudo, mas a "liderança técnica" que o currículo sugeria (migrações, mentoria, autonomia) se mostrou mais modesta na prática do que no papel.

### Onde ele foi realmente forte (sem ressalva)

- **Pergunta-chave (.NET):** zero contato prévio, mas raciocínio correto (baseado em OOP, similar a outras linguagens). Reação: *"minha reação é a mesma de hoje... qualquer problema cabeludo que aparece em produção, seja front, tech, infra, eu tô ali disponível pra resolver... hoje a gente tem o auxílio da IA pra ajudar com contexto e documentação"*. Melhor resposta possível — genuína, não ensaiada.
- **Uso de IA:** o ponto mais maduro da entrevista. Usa Cloud Code + GPT-5.6 pesadamente (chega a paralelizar 4 terminais), mas foi enfático: *"a IA não vai tomar decisão por você... arquitetura ainda, quem toma a decisão é você"*. Validação crítica, não uso passivo.
- **Testes E2E:** está atualmente implementando o primeiro teste automatizado (Playwright) nos fluxos críticos (login, swap) na empresa atual — dono da prática, não delega pro QA.
- **Design system:** resposta rica em detalhe técnico real (biblioteca headless, design tokens, distribuição via GitHub Packages) — bateu com o currículo, não pareceu inflado.
- **Incidente de produção:** história concreta e completa (API de terceiro caiu sem aviso → fallback → deploy em produção → monitoramento → refactor depois). Processo claro, autonomia real.
- **Cross-chain (Bloom):** detalhe técnico consistente (trocou provedor de liquidez, reduziu de 10min para 10s).
- **Motivação:** pareceu genuína (interesse real em fintech/regulação, quer aprender em escala real em vez de projetos pessoais).

### Onde travou / ficou raso — pontos de atenção

- **Mentoria — resposta mais fraca da entrevista:** *"o time é pequeno, todo mundo é bem independente... não tô mentorando diretamente, mas tento compartilhar via revisão de PR"*. Currículo sugeria mais liderança nesse quesito do que ele demonstrou ao vivo.
- **Ponte front/back:** resposta genérica (*"eu ia conversar com as duas equipes pra entender a cultura de cada uma"*) — correta, mas sem nenhum exemplo real de já ter feito isso (o time dele hoje é pequeno e full-stack, nunca precisou ser literalmente essa ponte).
- **Idempotência em webhooks:** quando perguntado diretamente, desviou pra descrever o fluxo geral do webhook, sem endereçar retry/idempotência especificamente.
- **Next.js App Router:** confirmado como gap esperado — "não foi tão a fundo ainda", usa mais SvelteKit, mas mostrou entendimento conceitual de SSR e abertura pra aprender. Não é bandeira vermelha.
- Pequenos momentos de hesitação/esquecimento (nome de biblioteca Figma, confundiu nome do framework Svelte) — isolado não significa nada, mas reforça a sensação de "bom, sem brilho extra".

### Ponto crítico para decisão — pretensão salarial

**R$25k PJ** — acima da mediana L4 (18k) e acima até do que o Felipe (também L4) recebia (24k). Empurra diretamente pra decisão de nível (L4 alto vs L5) antes da conversa de RH com a Célia.
**Disponibilidade:** 2 semanas. **Modelo:** confortável com híbrido esporádico, não topa presencial full-time.
**Próxima etapa:** conversa de RH com Célia já agendada para quinta-feira (23/07).

### Recomendação

Dado o nível de entrega na entrevista (sólido, mas sem excepcionalidade em liderança/mentoria) frente ao salário pedido (acima até do Felipe), eu pagaria por um perfil "bom, confiável, com potencial" — o que justifica avançar, mas não necessariamente sustenta o L5 tão facilmente quanto pareceria antes da conversa. Vale alinhar esse ponto com a Célia antes de quinta.

## Próximos passos (atualizado)
- [ ] **Descobrir o que aconteceu com ele depois do RH de 23/07** — não apareceu no retorno da Célia de 05/08, duas semanas de silêncio. Antes de qualquer comparação, saber se ainda existe candidato
- [ ] Fazer a entrevista técnica com o [[Gabriel Santi]] — nunca aconteceu, e é a etapa que decide
- [ ] Decidir nível (L4 alto vs L5) com a Célia antes da conversa de RH de quinta-feira
- [ ] Levar a pretensão de 25k pra essa conversa de alinhamento
- [ ] Aguardar retorno da etapa de RH (Célia, 23/07)
