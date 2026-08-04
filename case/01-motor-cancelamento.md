# Requisito de Negócio: Motor de Cancelamento e Estorno SaaS (Caso 01)

---

## 📌 Descrição do Problema de Negócio
O sistema deve permitir que um assinante solicite o cancelamento de sua assinatura SaaS a qualquer momento pela plataforma de forma autônoma.

Quando a solicitação for recebida, o sistema precisa processar o reembolso proporcional dos dias não utilizados do mês vigente do cancelamento.

## ⚖️ Regras de Negócio e Restrições
1. **Regra de Precedência / Legal (CDC - Direito de Arrependimento):** Caso o cancelamento ocorra dentro dos primeiros 7 dias a partir da data de assinatura inicial, o reembolso deve ser integral (100%), cancelando a assinatura sem a incidência de multas ou qualquer verificação de limite de uso de dados ou infrações.
2. **Regra de Limites e Cotas Operacionais:** Fora do período de arrependimento (após 7 dias), se o usuário tiver consumido mais de 50GB de tráfego de dados no mês corrente ou tiver qualquer pendência de infração nos termos de uso, o reembolso automático deve ser negado e o valor mantido zerado (R$ 0,00).
3. **Regra de Cálculo Temporal:** O cálculo do reembolso proporcional mensal deve considerar estritamente os dias corridos exatos do mês vigente em que a solicitação foi efetuada.
4. **Regra de Multa ou Penalidade Contratual (Plano Anual):** Para assinantes do Plano Anual, o cancelamento implica na cobrança de uma multa rescisória de 10% sobre o valor total do saldo bruto restante do contrato (soma dos meses futuros inteiros + fração pró-rata do mês atual).

## 🎯 Resultados Esperados
O sistema deve atualizar a assinatura para o status correspondente (`CANCELLED`, `CANCELLED_WITH_REFUND` ou `CANCELLED_WITHOUT_REFUND`), calculando e retornando o valor aprovado do reembolso líquido e o valor de eventuais multas aplicadas. O valor aprovado pode ser creditado como Saldo na Plataforma ou estornado via PIX.