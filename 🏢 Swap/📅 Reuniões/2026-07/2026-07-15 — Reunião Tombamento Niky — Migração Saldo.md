# Reunião Tombamento Niky — Migração de Saldo Massificada | 15/07/2026

**Participantes:** Paulo Pereira, Paulo Coleta (Banking), Gabriel Santi, Ana Carvalho (Risco/KYC), Luma Gomes Leonardo, Thales Machado, Mateus Escorcio, Guilherme Andrade
**Duração:** ~1h24min
**Contexto:** Definição de como fazer o tombamento de ~30.000 usuários da Niky (migrando da DOC para a Swap)

---

## Contexto Geral

A Niky tem aproximadamente 30.000 vidas (1.177 organizações, média de 30 pessoas por empresa) que precisam migrar da DOC para a Swap. O tombamento envolve dois grandes desafios:

1. **KYC/Biometria** — usuários não têm biometria na DOC, precisarão fazer pela primeira vez na Swap
2. **Migração de saldo** — os saldos precisam sair da DOC, passar por conta da Niky e entrar na Swap distribuídos nas bags corretas

---

## O Problema Central

- A Niky quer que o saldo apareça na conta do usuário **no dia da migração** — não no dia que ele acessar o app pela primeira vez
- Isso se deve a risco de processo de sindicato: se o saldo não estiver disponível na data acordada, o sindicato pode abrir processo contra o RH → Nick → Swap
- A Niky já foi traumatizada por esse tipo de situação antes
- Por isso, **o modelo Big Bang é necessário**: congelar tudo em um dia, migrar tudo de uma vez

---

## As Duas Propostas Discutidas

### Proposta 1 — Flag de controle de biometria (solução da Ana/Risco)
- Criar uma flag no sistema que indica se o account holder pode ou não ativar bag sem biometria
- Contas da Niky nascem com flag = true (podem ativar bag)
- Após 30 dias, flag vira false para quem não enviou biometria
- Vantagem: solução mais definitiva e reutilizável para outros clientes
- Desvantagem: requer desenvolvimento, pode não caber no prazo da Niky

### Proposta 2 — Beta V3 + migração escalonada de biometria ✅ ESCOLHIDA
- Criar todas as contas via beta V3 (sem exigir biometria na criação)
- Migrar saldo no modelo Big Bang normalmente
- Ao longo do tempo, fazer PUTs escalonados por organização convertendo para V1 (que exige biometria)
- Quando o usuário tentar acessar o app após o PUT, é forçado a fazer biometria
- Enviar push notifications proativamente convidando usuários a fazer biometria antes do prazo
- No fim dos 30 dias, fazer PUT em todos os remanescentes
- Vantagem: menor esforço de desenvolvimento, gestão fica do lado do time de interfaces
- Desvantagem: biometria vem depois, risco regulatório temporário

**Consenso:** Proposta 2 é o caminho. Ana vai documentar a Proposta 1 como estratégia de longo prazo para tombamento de base legada.

---

## Pontos Técnicos Importantes

- Script de migração atual bate na V1 — precisa ser adaptado para bater na beta V3
- No app: quando tem biometria pendente (após PUT para V1), usuário não consegue acessar o app — fica travado na tela de biometria
- Push notification via Firebase para induzir usuário a fazer biometria antecipadamente
- Possibilidade de banner na home do app como alternativa ao push
- Token de biometria expira a cada 72h — precisa de gestão de refresh
- Contas via beta V3 podem ativar bags e transacionar normalmente — só não podem criar NOVAS bags sem biometria

---

## Gestão do Projeto

- PM do White Label (Pietra/Dani) identificada como responsável natural pelo acompanhamento
- Thales saindo do time em breve — vai documentar tudo antes de sair
- Decisão de priorização vai para o comitê
- Paulo Pereira vai compartilhar proposta 2 no GT Tombamento Niky

---

## Próximos Passos

- [ ] Paulo Pereira compartilha proposta 2 no GT Tombamento Niky
- [ ] Ana documenta proposta 1 como estratégia de longo prazo
- [ ] Levar para o comitê de priorização
- [ ] Testar velocidade do script de migração (risco: 30.000 contas podem demorar dias)
- [ ] Adaptar script para bater na beta V3
- [ ] Definir cronograma de PUTs escalonados por organização
