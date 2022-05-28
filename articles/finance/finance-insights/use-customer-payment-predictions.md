---
title: Usar Previsões de pagamento do cliente
description: Este tópico percorre os pré-requisitos e as amplas etapas necessárias para usar uma versão de avaliação do Finance Insights.
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-11-16
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: ecc864485dfc106df22b48e92a85f2c73d58e0e8
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740614"
---
# <a name="use-customer-payment-predictions"></a>Usar Previsões de pagamento do cliente

[!include [banner](../includes/banner.md)]

Este tópico explica como usar as Previsões de pagamento do cliente. Antes de usar esse recurso, conclua as etapas de configuração para ele. Para obter mais informações, consulte [Habilitar previsões de pagamento do cliente](enable-cust-paymnt-prediction.md).

Você pode exibir as previsões de pagamento do cliente no espaço de trabalho **Gerenciar crédito e cobranças do cliente** e em duas novas páginas de lista: **Previsões de pagamento de transação** e **Previsões de pagamento do cliente**.

### <a name="manage-customer-credit-and-collections-workspace"></a>Espaço de trabalho Gerenciar crédito e cobranças do cliente

O espaço de trabalho **Gerenciar crédito e cobranças do cliente** inclui dois novos blocos: **Previsões de pagamento de transação** e **Previsões de pagamento do cliente**.

### <a name="transaction-payment-predictions-list-page"></a>Página da lista de Previsão de pagamento de transação

Na página da lista de **Previsões de pagamento de transação**, você pode exibir a probabilidade de pagamento para transações abertas nos buckets **No prazo**, **Atrasado** e **Muito atrasado**. Para cada transação na grade, a coluna **Probabilidade no prazo** mostra a probabilidade de que a fatura seja paga na data de conclusão ou antes. Se a probabilidade de um pagamento no prazo for inferior a 50%, um círculo vermelho aparecerá ao lado da porcentagem na coluna **Probabilidade no prazo** para indicar o risco de pagamento atrasado.

[![Página Previsão de pagamento por transação.](./media/payment-predictions-per-transaction.png)](./media/payment-predictions-per-transaction.png)

O painel **Informações relacionadas**, no lado direito da página, mostra mais detalhes sobre as previsões:

- Para a transação selecionada na grade, a Guia Rápida **Previsão de pagamento** mostra os detalhes das previsões de pagamento nos buckets **No prazo**, **Atrasado** e **Muito atrasado**. A seção **Principais fatores** mostra os principais fatores que influenciaram as previsões. Os principais fatores são atributos da transação selecionada e/ou do cliente para aquela transação.
- A Guia Rápida **Insights do cliente** mostra as estatísticas atuais de fatura, pagamento e cobranças do cliente para a transação selecionada.
- A Guia Rápida **Histórico do cliente** mostra o histórico de pagamento do cliente nos buckets **No prazo**, **Atrasado** e **Muito atrasado**.

Os dados na seção **Principais fatores** e nas Guias Rápidas **Insights do cliente** e **Histórico do cliente**, ajudam a explicar as previsões de pagamento. Eles podem ajudar a aumentar sua confiança na eficácia das previsões.

[![Indicadores gráficos para previsões de pagamento no painel Informações relacionadas.](./media/payment-prediction-gauges.png)](./media/payment-prediction-gauges.png)

### <a name="customer-payment-predictions-list-page"></a>Página da lista de Previsões de pagamento do cliente

A página da lista de **Previsão de pagamento do cliente** mostra o saldo total em aberto e o valor previsto a ser pago nos buckets **No prazo**, **Atrasado** e **Muito atrasado**.

[![Página Previsões de pagamento por cliente.](./media/payment-predictions-per-transaction-02.png)](./media/payment-predictions-per-transaction-02.png)

O valor do pagamento em cada bucket é calculado como a soma da média ponderada do saldo da transação. Esse valor é calculado com base nas probabilidades de pagamento em cada bucket.

Por exemplo, um cliente tem três transações abertas com as seguintes probabilidades de pagamento em cada bucket.

| Lançamento | Valor | Probabilidade de pagamento no prazo | Probabilidade de pagamento atrasado | Probabilidade de pagamento muito atrasado |
|-------------|--------|-----------------------------|--------------------------|-------------------------------|
| T1          | 100    | 10%                  | 50%               | 40%                    |
| T2          | 1.000  | 50%                  | 30%               | 20%                    |
| T3          | 10,000 | 1%                   | 4%                | 95%                    |

Nesse caso, os pagamentos são projetados para cada bucket da seguinte maneira.

| Buckets   | Transação T1      | Transação T2         | Transação T3            | Total |
|-----------|---------------------|------------------------|---------------------------|-------|
| No prazo   | 100 × 10 ÷ 100 = 10 | 1.000 × 50 ÷ 100 = 500 | 10.000 × 1 ÷ 100 = 100    | 610   |
| Atrasado      | 100 × 50 ÷ 100 = 50 | 1.000 × 30 ÷ 100 = 300 | 10.000 × 4 ÷ 100 = 400    | 750   |
| Muito atrasado | 100 × 40 ÷ 100 = 40 | 1.000 × 20 ÷ 100 = 200 | 10.000 × 95 ÷ 100 = 9.500 | 9,740 |

A seção **Informações relacionadas**, no lado direito da página, mostra mais detalhes sobre as previsões:

- Para a transação selecionada na grade, a Guia Rápida **Previsões de pagamento** mostra os detalhes das previsões de pagamento nos buckets **No prazo**, **Atrasado** e **Muito Atrasado**.
- A Guia Rápida **Insights do cliente** mostra as estatísticas atuais de fatura, pagamento e cobranças do cliente para a transação selecionada.
- A Guia Rápida **Histórico do cliente** mostra o histórico de pagamento do cliente nos buckets **No prazo**, **Atrasado** e **Muito atrasado**.

Os dados nas Guia Rápidas **Insights do cliente** e **Histórico do cliente** ajudam a explicar as previsões de pagamento. Eles podem ajudar a aumentar sua confiança na eficácia das previsões.

## <a name="improving-the-accuracy-of-payment-predictions"></a>Como aumentar a precisão de previsões de pagamento

Você pode exibir a precisão das previsões de pagamento em **Crédito e cobranças \> Configuração \> Finance Insights \> Parâmetros do Finance Insights**. Na guia **Insights de pagamento de cliente**, a seção **Modelo de previsão** mostra a precisão do modelo de previsão como uma porcentagem.

Se você não estiver satisfeito com a precisão, selecione o link **Aumentar precisão do modelo** para abrir a experiência de extensão do AI Builder. Na experiência de extensão do AI Builder, você pode selecionar ou cancelar a seleção de campos até que tenha selecionado os campos que acredita ser mais importantes para prever probabilidades de pagamento com precisão. Quando terminar, você poderá treinar facilmente o modelo de previsão e publicar as alterações. O modelo de previsão recentemente treinado será automaticamente escolhido para previsões no Dynamics 365 Finance.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
