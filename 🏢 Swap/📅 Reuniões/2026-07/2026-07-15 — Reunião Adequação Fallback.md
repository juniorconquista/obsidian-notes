# Reunião Adequação Fallback — 15/07/2026

**Participantes:** Junior Oliveira, Pietra Oliveira, Bruno Conti, Stive Tormes, Jonas Barros, Jefferson Lacerda
**Duração:** ~37 min
**Contexto:** Adequação do Fallback de benefícios para atender regulamentação Mastercard/decreto PAT

---

## Contexto do Problema

A Mastercard exige que benefícios alimentícios (VA/VR) transacionem pelo trilho voucher. O Fallback foi criado para ajudar o usuário quando o estabelecimento não aceita voucher — mas na prática todo mundo passou a usar o crédito e ninguém usa o voucher.

**Números do mês:** 70 milhões de fundin na conta pré-paga, mas apenas 9 milhões saíram no trilho voucher. Meta seria ~120 milhões.

A Mastercard enviou uma intimação com prazo até 30/06 para regularizar — prazo não foi cumprido.

Dois clientes (Sankhya e Green Card) fizeram rollback do bloqueio após problemas: usuário bloqueado no crédito, estabelecimento não aceitou voucher, usuário ficou sem conseguir pagar.

---

## Estágios do Fallback

- **Estágio 0** — Sem bloqueio (situação atual da maioria dos clientes)
- **Estágio 1** *(novo)* — Bloqueio apenas em estabelecimentos qualificados (com histórico de transações aprovadas no voucher)
- **Estágio 2** — Bloqueio amplo (o que causou os problemas com Sankhya/Green Card)
- **Estágio 3** — Fallback desligado (benefício só no voucher, saldo livre só no crédito)

---

## Decisões

### Frente 1 — Push Notifications ✅ Entra na próxima sprint
- Quando usuário tentar usar crédito num estabelecimento que aceita voucher → recebe push educativo orientando usar voucher
- Mesmo mecanismo do response code 301 já existente — Bruno confirmou esforço pequeno
- App do Stive já está preparado para receber pushes sem nova versão
- Jefferson (processadora) entrega payload na semana que vem
- **Não precisa ir ao comitê** — Pietra decidiu colocar direto na sprint

### Banner no app ✅ Imediato — sem desenvolvimento
- Funcionalidade de banner já existe no app
- Ao clicar, redireciona usuário para vídeo educativo sobre voucher (sendo produzido, previsão fim do mês)
- Stive confirmou: não precisa de nova versão, pode ser ativado agora

### Frente 2 — Ordem de prioridade das bags 🔄 Para comitê futuro
- Dar ao usuário opção de escolher se gasta saldo livre ou benefício primeiro
- Requer discovery, design e mais desenvolvimento
- Pietra não vai levar no comitê de amanhã — precisa mais maturidade

---

## Próximos Passos

- [ ] Jefferson entrega payload do response code na semana que vem
- [ ] Bruno implementa push notifications na próxima sprint
- [ ] Jonas envia vídeo para equipe quando ficar pronto (previsão fim do mês)
- [ ] Pietra alinha banner com design
- [ ] Frente 2 (ordem de bags) vai para comitê futuro após discovery

---

## Observação para o Junior

Call técnica de produto — papel do gestor foi garantir pessoas certas na sala e registro. Pietra conduziu bem, tomando decisões claras sobre o que vai e o que não vai ao comitê. Bruno e Stive contribuíram tecnicamente de forma sólida.
