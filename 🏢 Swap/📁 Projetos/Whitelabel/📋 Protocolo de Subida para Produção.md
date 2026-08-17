# 📋 Protocolo de Subida para Produção

**Criado em:** 01/07/2026
**Contexto:** Criado após call de publicação de 30/06 que durou 2h+ por falta de processo. Aplicar em todas as subidas a partir de 03/07 (Franchi e Tourhouse).

---

## ✅ Checklist Pré-Subida (fazer até 1 dia antes)

### Dev responsável

- [ ] Branch fechada — nenhum commit novo após esse ponto
- [ ] Listar exatamente o que vai nessa subida (correções, features, dependências)
- [ ] Validar pipeline de CI — build passando sem erros
- [ ] Deploy feito em stage e testado
- [ ] Comunicar no canal qualquer impedimento ou dependência técnica

### QA (Túlio / Alana)

- [ ] Cenários de teste mapeados para essa subida
- [ ] Testes executados em stage antes da call
- [ ] Webhooks validados em stage — cadastrar pessoa de teste e confirmar recebimento no Grafana
- [ ] Verificar no Grafana se webhooks em prod estão chegando normalmente

### Antes de subir em Prod

- [ ] Confirmar que pipeline de CI passou
- [ ] Confirmar webhooks cadastrados em prod (staging e prod)
- [ ] Verificar se há outra operação em progresso no pod (evitar travamento como aconteceu na Cardix)
- [ ] Confirmar que nada novo foi commitado após o fechamento da branch

---

## 🚨 Regras da call de subida

1. **Nenhum commit durante a call** — o que não está pronto não sobe
2. **Problemas descobertos na call = não sobe** — agenda nova subida
3. **Call máxima de 1h** — se passar, algo não foi validado antes
4. **Cada cliente = validação rápida** — não testar em stage durante a call de prod

---

## Checklist por Cliente

### Webhooks — validar antes de cada subida

| Cliente | Webhooks Stage | Webhooks Prod | Observação |
|---------|----------------|----------------|------------|
| Cardix | ✅ | ✅ | Recebendo normalmente |
| Pigz | ⚠️ | ✅ | Confirmar cadastro stage |
| Sankhya | ✅ | ✅ | Recebendo normalmente |
| Franchi | ❓ | ❓ | Verificar antes da subida |
| Tourhouse | ❓ | ❓ | Verificar antes da subida |

---

## Histórico de Subidas

### 30/06/2026 — Cardix, Pigz, Sankhya
- ✅ KYC subido com sucesso nos 3 clientes
- ⚠️ Fallback inteligente não validado antes — não funcionou em prod
- ⚠️ Pod da Cardix travado — precisou acionar SRE (Lucas Gimenez)
- ⚠️ Call durou 2h+ por falta de processo

### 03/07/2026 — Franchi e Tourhouse (previsto)
