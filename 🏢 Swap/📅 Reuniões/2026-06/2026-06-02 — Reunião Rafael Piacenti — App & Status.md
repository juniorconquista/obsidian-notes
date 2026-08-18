# Reunião Rafael Piacenti — Planilha & Status App — 02/06/2026

**Participantes:** Junior, Rafael Piacenti
**Objetivo:** Mapear atividades do time de mobile, bloqueios e ouvir como Rafael está

---

## Status das Atividades

| Task | Status | % | Bloqueio | Previsão |
|------|--------|---|---------|---------|
| Ajustes R6 / publicação na loja | Em andamento | 90% | Nenhum — só fazer o build | Amanhã 03/06 |
| Implementar customização cores RTF | Concluído | 100% | — | — |
| Implementar onboarding RTF | Concluído | 100% | Aguardando RTF em produção | — |
| Controle disponibilidade de serviço (app) | Concluído | 100% | Não impacta back | — |
| Fluxo boleto RTF | Bloqueado | 80% | Aguardando endpoints back | ~1 dia após desbloqueio |
| Transferência entre carteiras RTF | Bloqueado | 80% | Aguardando endpoints back | ~1 dia após desbloqueio |
| Homologação benefícios RTF | Bloqueado | 80% | Aguardando endpoints back | ~1 dia após desbloqueio |
| Marketplace (recarga, gift cards, clube) | Bloqueado | 50% | Sem PM + sem API definida | Indefinido |
| KYC Biometria (app) | Em andamento | 85-90% | API desbloqueada pelo Lucas | Segunda 08/06 |
| Wallets / emissão Visa (Samsung/Apple/Google) | Em andamento | — | Projeto em homologação | Samsung: fim de junho |
| CD benefícios legados | Em andamento | 75% | Depende de account managers responderem | Indefinido |

---

## Bloqueio Principal — RTF / Ledger

A maior parte do backlog do Rafael está bloqueada pelo mesmo problema do Felipe: falta de endpoints do backend relacionados ao RTF e ao Ledger.

Rafael foi muito claro:
- Não espera que tudo destrave de uma vez — o back vai liberando gradualmente
- Adiantou muito trabalho de front, mas chegou no limite do que dá para fazer sem a API
- Preocupação real: quando o back desbloquear tudo junto, ele pode virar o gargalo

---

## Marketplace

- PM saiu — produto está em redefinição
- Previsto no roadmap para esse mês
- Front já desenvolvido (~50%), mas integração com API vai ser complexa — contratos novos, fluxo inédito
- Rafael não acredita que será cancelado — usuários finais já usam fora do app (recargas, gift cards)

---

## Wallets / Emissão Visa

- Samsung: em homologação, previsão fim de junho
- Apple e Google: cronograma original era novembro, PM pediu adiantar para agosto — ainda incerto
- Trabalho atual é majoritariamente reuniões, não desenvolvimento

---

## Como o Rafael está

Honesto e maduro na conversa. Pontos que ele trouxe:

**Frustração legítima:**
- Trabalhou várias sprints no RTF e não conseguiu entregar para o cliente
- A maior parte do que fez está bloqueada — sensação de trabalhar sem ver resultado
- Impacto das saídas (Conrado, Igor) foi muito sentido — conhecimento que sumiu do time

**Ponto importante que ele levantou:**
As entregas de Helper não são contabilizadas como entrega de valor na review da SUAP — só os épicos planejados aparecem. Ele discorda fortemente disso e tem razão: corrigir um bug que impede o cliente de pagar boleto é altamente valioso. A gente precisa mudar como isso é apresentado.

**Postura:**
Engajado, não está conformado com a situação. Quer ver o time ser bem visto. Usa Shortcut integrado com MCP no fluxo de desenvolvimento — muito mais produtivo assim do que com planilha.

---

## Próximos Passos

- [ ] Junior — Resolver bloqueio do Ledger/RTF para destravar Rafael e Felipe
- [ ] Junior — Repensar como as entregas de Helper são apresentadas na review da SUAP
- [ ] Junior — Marcar 1:1 individual com Rafael nas próximas semanas
- [ ] Rafael — Finalizar publicação R6 amanhã (03/06)
- [ ] Rafael — Finalizar KYC app até segunda (08/06)
- [ ] Junior + Paulo — Acompanhar PM do marketplace para retomada do produto
