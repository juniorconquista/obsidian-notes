# War Room KYC — 16/07/2026

**Duração:** ~4 horas (14h às 18h30)
**Participantes:** Junior, Santi, Stive, Túlio, Regis, Lucas, Alana, Andrey, Thales (Risco), Kellen (Risco), Guilherme Andrade (Risco)

---

## O Problema

Vários tickets de KYC surgindo no Helper de múltiplos clientes (Próspera, Sankhya, Cardix, Pigz, etc). Usuários travados numa tela de "Aguarde sua análise" sem conseguir prosseguir.

---

## Investigação — o que descobriram

**Causa raiz:** O time de Risco lançou dois novos status no fluxo de biometria:
- `IN_PROCESS` — lançado em 23/06, já estava em produção para todos
- `CAPTURE_COMPLETED` — lançado em 15/07, estava em produção apenas para Valeshop (mas apareceu em outros clientes via GET)

O app de benefícios (legado) não mapeava esses status. Quando o usuário iniciava a biometria e o status ia para `IN_PROCESS` ou `CAPTURE_COMPLETED`, o app não reconhecia e caia num estado desconhecido — exibindo a tela de "em análise" sem conseguir avançar.

**Agravante:** o time WL não estava no canal `gt_novo_kyc_biometria` onde o comunicado foi enviado. Lucas e Regis estavam no canal mas não repassaram internamente.

**Bug adicional descoberto:** Quando o usuário minimizava o app durante o fluxo de biometria e clicava no "X" para fechar a tela, ao voltar o app batia no endpoint de identity e retornava o status novo não mapeado — travando o usuário.

**Bug extra:** String "Atualize seu aplicativo para prosseguir" vinda do backend — relacionada a um método antigo de validação de header MFA que ainda existia no código do app legado.

---

## Solução

**Paliativo (aplicado no dia):** Santi remapeou no backend os novos status para status que o app já conhecia:
- `IN_PROCESS` → `CREATED` (app consegue retomar o fluxo)
- `CAPTURE_COMPLETED` → `EM_ANALISE` (status final, usuário aguarda)

Deploy feito em interfaces (ambiente interno) e validado por Túlio. Resolveu os casos reportados.

**Solução definitiva (a fazer):** Criar camada de tradução de status no BFF para que mudanças futuras do lado do Risco não quebrem o app. Criar card para implementar.

---

## O que causou o problema estruturalmente

1. **Time não estava no canal de comunicação do Risco** — o comunicado foi enviado em 23/06 e 15/07 mas ninguém de WL estava lá para capturar
2. **App legado sem testes unitários suficientes** — tratamento de status por igualdade de string sem fallback
3. **Subida gradual de clientes** — o problema não apareceu antes porque poucos clientes usavam o fluxo novo

---

## Próximos Passos

- [ ] Stive criar card para solução definitiva — camada de tradução de status no BFF
- [ ] Adicionar pessoas do time WL no canal `gt_novo_kyc_biometria`
- [ ] Não repassar status diretamente — sempre traduzir para status conhecidos internamente
- [ ] Acompanhar clientes afetados via planilha de war room

---

## Aprendizado

> "Ao invés de repassar direto, vamos fazer um tratamento do nosso lado dos status conhecidos. Se rolar alguma mudança ou entrar coisa nova que não acompanhamos, não vamos quebrar do nosso lado."
> — Junior Oliveira, 16/07/2026
