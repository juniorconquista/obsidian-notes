# Gap Legado × V2 — Funcionalidades | 18/08/2026

Levantamento inicial, olhando o código do legado contra o que existe hoje na V2 —
base técnica por trás da meta de
[[2026-08-18 — Roteiro — Comitê de Priorização com o Sol|"V1 Migrada com todas as
funcionalidades existentes" em 19/10]]. Feito para embasar o pedido de reforço
estratégico de **Dados** e **SRE** dedicados.

## Números

- **34 itens mapeados.**
- **23 são gap total** — o legado tem, a V2 não tem nada.
- **3 são gap parcial** (🟡) — a V2 tem uma versão mais pobre.
- **4 estão em paridade ou melhor** na V2.
- **2 já estavam mortos no próprio legado** (não entram na conta).
- **2 são novidade só da V2**, sem equivalente no legado.

Ou seja: **26 dos 34 itens (76%)** precisam de trabalho antes de dizer que a V2 tem
"todas as funcionalidades existentes" do legado. Vale ter esse número na cabeça ao
defender o prazo de 19/10 — são ~2 meses para fechar 23 itens do zero mais 3
ajustes, com o time de Modernização ainda com três vagas em aberto (.NET,
arquiteto, QA).

## Visão rápida — o que tem e o que não tem

Leitura de negócio, sem termos técnicos. O detalhe (arquivo/módulo por trás de
cada linha) fica para levantamento seguinte.

| Funcionalidade | Legado | Novo (v2) |
|---|---|---|
| Recarga via Pix/Boleto do produto Benefícios | ✅ | ❌ (ainda depende do legado por baixo dos panos) |
| Transferência bancária (TED) para conta do beneficiário | ✅ | ❌ |
| Aprovação manual de um pedido antes do dinheiro ser enviado | ✅ | ❌ (hoje envia automático) |
| Ajuste manual de saldo pelo suporte (crédito ou débito, com motivo) | ✅ | ❌ |
| Estorno de valor entre contas | ✅ | ❌ |
| Recuperação de saldo esquecido/inativo | ✅ | ❌ |
| Boleto grátis (cota mensal), valor mínimo de boleto, alerta em pedido de valor alto | ✅ | ❌ |
| Pagar um pedido usando saldo que a empresa já tem, sem gerar boleto/pix novo | ✅ | ❌ |
| Cartão "combo" (crédito + voucher no mesmo plástico) | ✅ | ✅ (até melhor) |
| Bloquear cartão informando o motivo (perda, roubo, etc.) | ✅ | 🟡 (bloqueia, mas sem motivo) |
| Ajustar o limite de gasto de um cartão específico manualmente | ✅ | 🟡 (mudou para um modelo de política, não é mais ajuste pontual) |
| Resetar senha de vários cartões de uma vez (upload de planilha) | ✅ | ❌ |
| Colocar/retirar saldo de um cartão manualmente | ✅ | ❌ |
| Benefício liberado só para um time específico da empresa | ✅ | ❌ |
| Benefício liberado só para pessoas selecionadas (não todo mundo) | ✅ | ❌ |
| Limitar % do saldo que pode ir para transferência/boleto/TED | ✅ | ❌ |
| Termo de uso vinculado a um pedido, com assinatura do funcionário | ✅ | ❌ |
| Termo de uso configurável por categoria de benefício/empresa | ✅ | ❌ |
| Convênios (lojas parceiras com desconto para o funcionário) | ✅ | ❌ |
| Organizar funcionários em times dentro da empresa | ✅ | ❌ |
| Mudar um funcionário de empresa mantendo o saldo dele | ✅ | ❌ |
| Controle de abastecimento (litros, km, placa do veículo) | ✅ | ❌ |
| Loja de benefícios / campanhas / cupons de desconto | ❌ (já tinha sido desativado no próprio legado) | ❌ |
| Plano de saúde como benefício | ❌ (nunca chegou a funcionar de fato) | ❌ |
| Reembolso de benefício (funcionário pede reembolso via formulário) | ✅ | ❌ |
| "Lembrar este aparelho" para não pedir 2FA de novo | ✅ | ❌ |
| Enviar SMS (ativação de conta, avisos) | ✅ | ❌ |
| Central de notificações dentro do sistema | ✅ | ❌ |
| Histórico de quem fez o quê, legível para um administrador investigar | ✅ | 🟡 (só um log técnico, sem tela pra consultar) |
| Aprovação de cadastro (KYC/KYB) | ✅ | ✅ (melhor) |
| Relatórios e dashboard | ✅ | ✅ |
| Personalização visual por cliente (marca própria) | ✅ | ✅ |
| 2FA com app autenticador (Google Authenticator etc.) | ❌ | ✅ (novidade) |
| Políticas de limite de gasto (diário/semanal/mensal) | ❌ | ✅ (novidade) |

## Próximos passos

- [ ] Priorizar os 23 itens de gap total — quais entram até 19/10 e quais podem
  ficar para depois (nem tudo precisa estar pronto para "poder migrar", só o
  suficiente para não perder funcionalidade crítica)
- [ ] Levantar o esforço técnico por item (arquivo/módulo) — este documento é só
  a visão de negócio
- [ ] Usar este número (76% de gap) para justificar o pedido de reforço de Dados
  e SRE dedicados
