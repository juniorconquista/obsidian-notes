# Pedidos FACISC — Levantamento | 18/08/2026

Origem: planilha `[Internal] Pedidos FACISC - Pedidos`, aba "Pedidos". Base por
trás do marco **"Adição dos 65 itens de melhoria da FACISC — 30/11"** do
[[2026-08-18 — Roteiro — Comitê de Priorização com o Sol|roteiro do Sol]].

> A ordem de prioridade mudou um pouco em relação ao que estava sendo dito antes
> **porque nem toda solução foi aprofundada 100%** — os itens marcados
> `Aprofundar` na complexidade ainda não têm desenho fechado, então não dá para
> saber com certeza onde entram na fila.

## Números

- **68 itens no total.**
- **15 concluídos**, **3 em andamento**, **50 não iniciados** — ou seja,
  **53 pendentes**.
- **Divergência a resolver:** as notas da semana vêm citando **"65 itens da
  FACISC"** como o escopo do marco de novembro, mas a planilha hoje mostra
  **53 pendentes** (ou **49**, se contar só os que ainda não estão
  contemplados no desenho do WL 2.0). Vale confirmar de onde veio o número 65
  antes de repetir para o Sol ou para a diretoria — pode ser uma contagem
  antiga, de antes de alguns itens serem concluídos.
- **49 dos 53 pendentes não estão contemplados no desenho atual do WL 2.0**
  (`Contemplado no WL 2.0` = `False`). Só 4 já estão previstos: Marketplace,
  Duplicar CPF, Desativar aproximação de cartão, Taxas de pedido para cadastro
  PF.
- **6 itens têm complexidade "Aprofundar"** — sem solução desenhada ainda, são
  os que mais podem mexer na ordem quando forem analisados:
  - Mais campos na justificativa (ex: conta contábil)
  - Mudar categoria da despesa (mesmo com MCC automático)
  - Acesso do gestor para justificativa de despesa
  - "Excluir benefício"
  - Relatório de usuários com TIMES
  - Ativação de cartões em lote via Gestão de Cartões

## Pendentes por prioridade e complexidade

| Prioridade | Qtd. pendente |
|---|---|
| Alta | 13 |
| Média | 18 |
| Baixa | 22 |

| Complexidade | Qtd. pendente |
|---|---|
| 🔥🔥🔥 (alta) | 9 |
| 🔥🔥 (média) | 12 |
| 🔥 (baixa) | 22 |
| Aprofundar | 6 |
| N/A | 3 |

## Lista completa

| Produto | Status | Solicitação | Prioridade | Complexidade | Contemplado WL 2.0 |
|---|---|---|---|---|---|
| Despesas | Concluído 🎉 | Download em lote dos comprovantes em PDF | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Autonomia portal Admin | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Relatório de usuários para envio de cartão | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Opção de pagamento por boleto | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Extrato em PDF | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Download em lote dos comprovantes (zip) | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Correção na importação de pessoas | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Upload de documentos nas políticas | Baixa | N/A | N/A |
| Despesas | Concluído 🎉 | Aumento do upload de comprovantes (10→50MB) | Alta | N/A | N/A |
| Despesas | Concluído 🎉 | Deslog automático e Face ID | Média | N/A | N/A |
| Despesas | Concluído 🎉 | Emissão do boleto (documento) de pedidos | Baixa | N/A | N/A |
| Despesas | Concluído 🎉 | Push notification (transações negadas/aprovadas) | Baixa | N/A | N/A |
| Despesas | Concluído 🎉 | Visualização de transação negada e motivo | Baixa | N/A | N/A |
| Despesas | Concluído 🎉 | Limite de comprovantes despesas (app, 50MB) | Baixa | N/A | N/A |
| Despesas | Concluído 🎉 | Melhoria boas-vindas (e-mail só tinha link) | Média | N/A | N/A |
| Despesas | Em andamento | Automação da cobrança por usuário no portal (**Épico**) | Alta | 🔥🔥🔥 | False |
| Multiproduto | Não iniciado | Fluxo de segunda via de cartão | Alta | 🔥🔥🔥 | False |
| Despesas | Não iniciado | Centro de custos (prometido na v1) | Alta | 🔥🔥🔥 | False |
| Despesas | Em andamento | Emissão de fatura | Alta | 🔥 | False |
| Despesas | Não iniciado | Mais campos na justificativa (conta contábil) — indispensável p/ SICREDI | Alta | Aprofundar | False |
| Despesas | Não iniciado | Mudar categoria da despesa (mesmo com MCC automático) — indispensável p/ SICREDI | Alta | Aprofundar | False |
| Despesas | Não iniciado | Ajustes no extrato de despesas totais (CNPJ, categoria, política, PDF) | Alta | 🔥 | False |
| Despesas | Não iniciado | Relatórios Boss/console (hoje só existe para benefícios) | Alta | 🔥🔥🔥 | False |
| Despesas | Não iniciado | Relatório de saldo atual (todos os colaboradores, em lote) | Alta | 🔥 | False |
| Despesas | Não iniciado | Integração com ERPs — já perdeu negociação comercial por falta disso | Média | 🔥🔥🔥 | False |
| Despesas | Não iniciado | Acesso do gestor para justificativa de despesa (hoje só pelo app) | Média | Aprofundar | False |
| Despesas | Não iniciado | TED/boleto/PIX dentro do Despesas — já perdeu negociação comercial | Média | 🔥🔥🔥 | False |
| Despesas | Não iniciado | Ajustes no extrato por pessoa (PDF/Excel: saldo anterior, categoria, justificativa) | Média | 🔥🔥 | False |
| Despesas | Não iniciado | Relatório de distribuição | Média | 🔥 | False |
| — | Não iniciado | Cópia de cadastro de benefícios (ticket #186908) | Média | — | False |
| Despesas | Não iniciado | Incluir dados no relatório de Situação de organizações | Média | 🔥 | False |
| Despesas | Não iniciado | ID por despesa | Média | 🔥 | False |
| Multiproduto | Não iniciado | Reprovação KYC — melhorar visualização do motivo (pop up) | Média | 🔥🔥 | False |
| Despesas | Não iniciado | Conclusão do dashboard operacional | Média | 🔥🔥 | False |
| Despesas | Não iniciado | Cadastro de empresa PF (precisa análise de compliance) | Média | 🔥🔥 | False |
| Despesas | Não iniciado | Integração com plataforma de atendimento (chat JA) | Média | 🔥🔥🔥 | False |
| Despesas | Em andamento | CNPJ no menu de acesso (filiais com mesmo nome) | Média | 🔥 | False |
| Benefícios | Não iniciado | Adiantamento salarial (pedido novo, mapa mental da FACISC) | Média | 🔥🔥🔥 | False |
| Despesas | Não iniciado | Melhoria IA assistente | Baixa | 🔥🔥 | False |
| Despesas | Não iniciado | Fluxo reembolso dentro do portal | Baixa | 🔥🔥🔥 | False |
| Multiproduto | Não iniciado | Excluir pedidos (melhorar visualização) | Baixa | 🔥 | False |
| Despesas | Não iniciado | Justificativa na tela (mostrar direto, sem clicar) | Baixa | 🔥🔥 | False |
| Despesas | Não iniciado | Cidade do estabelecimento no extrato (dado do merchant está incorreto) | Baixa | N/A | False |
| Despesas | Não iniciado | Edição de justificativa pelo usuário | Baixa | 🔥 | False |
| Despesas | Não iniciado | Rotacionar documento (notas de cabeça para baixo) | Baixa | 🔥 | False |
| Despesas | Não iniciado | Anexar mais de uma nota na justificativa | Baixa | 🔥 | False |
| Despesas | Não iniciado | Relatório de pessoas cadastradas | Baixa | 🔥 | False |
| Multiproduto | Não iniciado | Treinamentos (link para treinamento) | Baixa | 🔥 | False |
| Despesas | Não iniciado | Chave Pix com valor (hoje é estática) | Baixa | 🔥🔥 | False |
| Benefícios | Não iniciado | Marketplace no app (iFood, Uber, Spotify etc.) | Baixa | N/A | **True** |
| Despesas | Não iniciado | Alteração de e-mail da Organização | Baixa | 🔥 | False |
| Despesas | Não iniciado | Recortar foto da nota (hoje é quadrado fixo) | Baixa | 🔥 | False |
| Despesas | Não iniciado | Visualizar nota na tela (sem baixar) | Baixa | 🔥 | False |
| Benefícios | Não iniciado | Fatura do Bee Crédito (download e melhorar formato) | Alta | 🔥 | False |
| Benefícios | Não iniciado | Acesso aos pedidos do Bee Crédito no admin | Alta | 🔥🔥 | False |
| Multiproduto | Não iniciado | Duplicar CPF (mesmo usuário em empresas diferentes) | Alta | N/A | **True** |
| Benefícios | Não iniciado | Desativar aproximação dos cartões | Média | 🔥🔥 | **True** |
| Benefícios | Não iniciado | Relatório de clicks nos banners do app | Alta | 🔥 | False |
| Benefícios | Não iniciado | Retornar opção "Excluir benefício" | Baixa | Aprofundar | False |
| Benefícios | Não iniciado | App: usuário inativo consultar saldo | Baixa | 🔥🔥 | False |
| Benefícios | Não iniciado | Mensagens na tela de pagamento (horário e valor limite) | Média | 🔥 | False |
| Multiproduto | Não iniciado | Recusa de transação — detalhar motivo no app | Média | 🔥 | False |
| Multiproduto | Não iniciado | Data de cadastro do usuário na tela | Baixa | 🔥 | False |
| Multiproduto | Não iniciado | Código de verificação de carteiras também por e-mail | Baixa | 🔥🔥 | False |
| Benefícios | Não iniciado | Taxas de pedido para cadastro PF | Média | 🔥🔥 | **True** |
| Benefícios | Não iniciado | Relatório de usuários com TIMES vinculado | Baixa | Aprofundar | False |
| Benefícios | Não iniciado | Comprovantes de TED (gerar e enviar por e-mail) | Baixa | 🔥 | False |
| Benefícios | Não iniciado | Ativação de cartões em lote via Gestão de Cartões (~800 cartões, hoje manual) | Baixa | Aprofundar | False |

## Próximos passos

- [ ] Confirmar a origem do número "65 itens" citado nas notas da semana — a
  planilha hoje mostra 53 pendentes
- [ ] Aprofundar os 6 itens marcados `Aprofundar` antes de fechar a ordem final
  para o marco de 30/11
- [ ] Decidir se os 49 itens `Contemplado no WL 2.0 = False` entram no escopo
  do marco ou ficam para depois — hoje só 4 estão previstos no desenho atual
