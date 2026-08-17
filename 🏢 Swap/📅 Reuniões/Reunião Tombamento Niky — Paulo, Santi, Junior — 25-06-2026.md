# Reunião Tombamento Niky — Paulo, Santi, Junior | 25/06/2026

**Participantes:** Paulo Pereira, Gabriel Santi, Junior Oliveira
**Duração:** ~1h

---

## Contexto

A Niky está se tornando potencialmente o maior cliente da Swap. Há duas frentes em paralelo sendo trabalhadas pelo Paulo:

---

## Frente 1 — Integração de Dados (ANIC)

A ANIC (empresa parceira da Niky) precisa receber dados da Swap para:
- Emitir notas fiscais quando entra dinheiro na plataforma (carga/boleto/Pix/TED)
- Cancelar notas fiscais quando boleto vence sem pagamento
- Receber dumps diários/semanais de dados estruturados via CSV/FTP/S3

**O que eles precisam receber:**
- Base analítica de contratos/empresas
- Base analítica de beneficiários/pessoas
- Base analítica de cartões
- Base analítica de transações financeiras (empresa e beneficiário)
- Autorizações do beneficiário (compras aprovadas, negadas, estornos — D-1)

**Solução identificada pelo Santi:**
- Dados de empresa, pessoas, pedidos, contas → consegue extrair direto da base de benefícios, sem precisar do time de dados
- Eventos de entrada de dinheiro → usar webhook de funding já existente na Swap para disparar para a ANIC
- Extrato → podem usar a própria API da Swap

**Reunião com a ANIC marcada para hoje à tarde** — Paulo quer que Santi ouça e ajude a dimensionar o prazo real (Paulo estimou 6 semanas, ANIC achou muito e pediu revisão)

---

## Frente 2 — Tombamento e Multiorg

Paulo está desenvolvendo a importação das empresas da Niky para o portal de benefícios, incluindo suporte a multiorganização (mesma pessoa em duas empresas diferentes).

**O que já foi feito:**
- PR de importação de empresas e pessoas avançado
- Estrutura de multiorg funcionando localmente — mesmo CPF cadastrado em duas organizações
- Migrations criadas
- Deploy feito em stage da Niky via ArgoCD com ajuda do Santi

**Pendências técnicas:**
- Validar IP fixo do ambiente de STG/Prod do portal benefícios — necessário para bater na API da ANIC
- Resolver bug na query de multiorg (pessoa aparecendo duplicada)
- Testar o multiorg em stage antes de subir para produção
- O Regis está trabalhando numa migração de usuários que pode ser impactada pelo multiorg

---

## Dever de Casa — Junior

- [ ] Verificar com Alício ou Luício Provenzano se o ambiente de STG e Prod do Portal Benefícios tem IP fixo 🔴
- [ ] Se tiver IP fixo, solicitar o IP para que o Paulo possa fornecer à ANIC

---

## Próximos Passos

- Paulo e Santi participam da reunião com a ANIC hoje à tarde
- Paulo vai propor prazo menor com base no que o Santi validou
- Santi vai ajudar a revisar o PR do tombamento e orientar o deploy
