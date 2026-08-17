# Roteiro — Roadmap do White Label com o Ury | 13/08/2026

**Formato:** presencial, sem slide. O roteiro é a apresentação.
**Objetivo da call:** sair com a direção de arquitetura confirmada e com o item de
03/08 fechado.

> **Leitura do interlocutor.** O Ury é CRO — ele pensa em contrato, tombamento e
> time-to-value, não em ledger. **Toda vez que a conversa for para o técnico, traga
> de volta para "isso permite ou impede fechar contrato".** E lembre que na segunda
> rodada de metas, em 03/08, ele foi o **único** que te questionou: pediu para
> alinhar o prazo do WL 2.0 com os contratos em venda e com os anúncios da Febraban e
> do CONARH. Ficou como próximo passo, sem data — e nunca aconteceu.

---

## 1. Abertura — puxe o que ficou dele

*Comece devolvendo o pedido dele. Ganha crédito e enquadra a conversa.*

> "Ury, na segunda rodada de metas você pediu para alinhar o prazo do WL 2.0 com os
> contratos que estão sendo vendidos e com o que a gente ia anunciar na Febraban e no
> CONARH. Ficou em aberto e eu vim fechar isso hoje. E aconteceu uma coisa desde
> então que muda a conversa."

---

## 2. O que mudou — em três frases

> "O Sol se comprometeu ontem com a FACISC de entregar a versão nova rodando até
> dezembro. A gente vai refundar o White Label, com time dedicado, e a diretoria está
> apoiando."
>
> "A data não está em discussão. **O que a gente decide agora é escopo.**"
>
> "E tem uma decisão de fundação que precisa sair hoje, porque ela define o que dá
> para vender no ano que vem."

---

## 3. A decisão: RTF e CCLG, os dois

*Se ele pedir para escolher um — e é provável que peça, para acelerar — esta é a
resposta.*

> "A pergunta natural é escolher um modelo para ir mais rápido. Eu sentei com o Santi
> e com o Léo hoje de manhã para medir isso, e a resposta é que **não compensa
> escolher**."
>
> "**Cerca de 10% do sistema muda entre um modelo e outro.** Portal administrativo,
> portal de RH e aplicativo consomem saldo do mesmo jeito. Bloqueio de cartão, troca
> de senha, extrato na tela — tudo igual. O usuário final não percebe diferença
> nenhuma. O que muda é uma camada específica, que decide de qual ledger ler o saldo."

**E aqui está o argumento que interessa a ele:**

> "Suportando os dois, **eu tombo um cliente sem obrigar ele a mudar de estrutura**.
> Eu chego e falo: traz sua operação para o White Label novo, você não muda nada para
> o seu cliente final, ele não vai sentir. Trocar de modelo vira decisão dele, quando
> ele quiser."
>
> "Se a gente escolher um só, **toda a base do outro modelo precisa migrar de
> estrutura de conta antes de tombar** — e aí a barreira comercial volta."
>
> "E tem um detalhe que não tem contorno: **tem cliente que, por questão legal, não
> pode operar em RTF.** Escolher RTF exclui esses clientes de forma permanente."

**O fecho, ligando ao compromisso:**

> "Na prática, suportar os dois é o que torna o compromisso de dezembro com a FACISC
> cumprível. Ela opera em CCLG. Se a gente entregar só RTF, não tem como tombar ela —
> e é o nosso maior cliente de White Label."

---

## 4. O que está aberto — diga antes que ele pergunte

> "Tem um item técnico que ainda não fechou: no RTF, a transação de cartão precisa
> debitar do balance correto no momento do swipe. Distribuição de limite, criação e
> remoção de saldo e estrutura de conta já estão funcionando e testados. Falta esse, e
> está em teste com o banking."

> "E tem uma pergunta que não é minha para responder: **banking e cartões estão 100%
> confortáveis em suportar os dois modelos?** Do lado do White Label os dois cabem. A
> maturidade da estrutura de contas é deles. Isso precisa de dono."

---

## 5. O que eu preciso de você

1. **Confirmar a direção** — os dois modelos entram no desenho da refundação.
2. **Um dono para a validação de banking e cartões.**
3. **A informação comercial que só você tem:** quais contratos estão em venda, para
   quando, e em qual modelo eles operam. *Isso muda a ordem do que a gente constrói
   primeiro.*

*A pergunta 3 é a mais importante da reunião. Ela transforma a conversa de "me deixa
fazer os dois" em "me ajuda a priorizar dentro dos dois".*

---

## PERGUNTAS QUE PODEM VIR

**"Por que não escolhe um e entrega mais rápido?"**
> Porque a economia é pequena e o custo é grande. São 10% do sistema — uma camada. E
> escolher um significa que metade da base não tomba sem migrar de estrutura antes.
> Ganho alguns dias e perco o tombamento da FACISC.

**"Dezembro é real?"**
> A data está comprometida com o cliente pelo Sol e eu trabalho com ela. O que a gente
> ajusta é escopo, não prazo. Por isso a conversa de hoje: definir o que entra é o que
> torna dezembro possível.
> *(Cuidado: o cronograma de comitê registra V0 em 04/09, V1 com CCLG em novembro e as
> funcionalidades completas do legado em janeiro/2027. Se ele cravar "tudo em
> dezembro", diga que o que estará rodando em dezembro é o produto novo com a
> operação, e que a cauda de funcionalidades do legado segue em janeiro. Não repita a
> compressão de trimestre que saiu na sua fala de 03/08.)*

**"E os anúncios da Febraban e do CONARH?"**
> É exatamente o que eu vim fechar. Preciso saber o que foi anunciado e para quando,
> para eu não construir uma coisa e o comercial ter vendido outra.

**"Quanto custa fazer os dois?"**
> Uma camada de configuração por empresa, que chaveia a origem do saldo. Não é
> desenvolver duas vezes. O resto do sistema é agnóstico.

**"O que garante que dessa vez não atrasa?"**
> Três coisas diferentes de antes: time dedicado só para isso; a Priscila entrando no
> desenho de qualidade desde a primeira agenda, não no fim; e o compromisso do Sol de
> blindar essa frente no comitê de priorização, para o roadmap não mudar no meio.

**"Quem vai fazer?"**
> Time dedicado com apoio da Raro, e as três pessoas-chave nossas dentro: Santi,
> Stive e o Lucas Verdan, que fechou ontem e é especialista de front com Next em
> produção.

**"E o legado, quem segura?"**
> É o ponto que ainda precisa de decisão. Se o Santi e o Stive vão para a refundação,
> a sustentação fica sem quem conhece o legado. Estou trabalhando nisso essa semana.
> *(Não improvise aqui — se ele pressionar, é honesto dizer que ainda não está
> resolvido.)*

---

## O que NÃO levar para essa conversa

- **Detalhe de ledger.** Ele não precisa saber que existem três ledgers. Se perguntar,
  uma frase: "a diferença é de onde a gente lê o saldo".
- **Reclamação de capacity.** A conversa é sobre direção, não sobre falta de gente.
- **A discussão de quem segura o legado**, a menos que ele puxe. É problema seu, não
  dele.
