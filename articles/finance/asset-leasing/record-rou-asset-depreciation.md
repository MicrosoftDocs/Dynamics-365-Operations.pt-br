---
title: Registrar depreciação de ativo de direito de uso (versão preliminar)
description: Este tópico explica como criar a entrada de diário para a amortização necessária para arrendamentos reconhecidos no balanço de uma organização.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0dd8308acb875affc96ca6d9ed856d74d4b2eb37
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440543"
---
# <a name="record-right-of-use-asset-depreciation-preview"></a>Registrar depreciação de ativo de direito de uso (versão preliminar)

[!include [banner](../includes/banner.md)]

Para arrendamentos reconhecidos no balanço de uma organização, o ativo de direito de uso (DDU) é amortizado mensalmente. Este tópico explica como criar a entrada de diário para a amortização. A amortização debita da conta contábil de despesas e credita na conta contábil de depreciação acumulada, com base na configuração do seu perfil de lançamento e do tipo de arrendamento. Essas entradas podem ser criadas para cada arrendamento ou podem ser criadas para vários arrendamentos usando a funcionalidade de diário de lote.

## <a name="asset-depreciation-schedule"></a>Agenda de depreciação de ativos

1. Na página **Resumo do arrendamento** , selecione um arrendamento. Em seguida, selecione **Registros \> Agenda de depreciação de ativos** para abrir a página **Agenda de depreciação de ativos**.

    A entrada do diário de despesas da depreciação de ativos DDU baseia-se no valor da coluna **Despesa de Depreciação**. Para obter um exemplo de diretrizes para conformidade com o padrão contábil, consulte a seção [Cálculo de despesa de amortização de ativos DDU para arrendamentos mercantis](#calculation-of-rou-asset-amortization-expense-for-finance-leases) posteriormente neste tópico.

2. Selecione o período de depreciação e, em seguida, selecione **Criar diário**. Você recebe uma mensagem que indica que o diário que será usado para registrar a depreciação foi criado.
3. Selecione **Diários \> Diários de arrendamento de ativos** para abrir a página **Diário de arrendamento de ativos**, onde você pode exibir a entrada de diário de despesas de depreciação que foi criada.
4. Selecione a entrada de diário e, em seguida, selecione **Lançar** para registrar a entrada de depreciação na Contabilidade.

## <a name="calculation-of-rou-asset-amortization-expense-for-operating-leases"></a>Cálculo de despesas de amortização de ativos DDU para arrendamentos operacionais

A despesa de depreciação de um arrendamento operacional é calculada como a diferença entre as despesas de arrendamento linear e a despesa de juros mensais na responsabilidade com arrendamento, de acordo com o Tópico 842 da Codificação de Padrões Contábeis (ASC 842), que é o padrão nos Princípios Contábeis Geralmente Aceitos nos Estados Unidos (US GAAP). A despesa de arrendamento linear é calculada como a soma de todos os pagamentos de arrendamento dividida pelo prazo do arrendamento em meses. (A soma de pagamentos de arrendamentos inclui pagamentos antecipados, custos diretos iniciais, custos de desmontagem e incentivos de arrendamento). A tabela a seguir mostra um exemplo da despesa de amortização para um arrendamento operacional.

### <a name="example-of-rou-asset-amortization-expense-for-operating-leases"></a>Exemplo de despesas de amortização de ativos DDU para arrendamentos operacionais

| Campo                                          | Alíquota       |
|------------------------------------------------|-------------|
| Valor do pagamento                                 | 1.000       |
| Frequência de pagamento                              | Mensalmente     |
| Prazo de arrendamento (meses)                            | 24          |
| Total de pagamentos do arrendamento                           | 24,000      |
| Taxa incremental de empréstimo                     | 5%          |
| Tipo de anuidade                                   | Anuidade devida |
| Intervalo de composição                           | Mensalmente     |
| Valor presente de pagamentos do arrendamento mínimos futuros | 22,888.87   |

Como mencionado anteriormente, a despesa de arrendamento linear é calculada como a soma de todos os pagamentos dividida pelo prazo do arrendamento. O sistema calcula automaticamente as despesas de juros mensais na agenda de amortização de passivo. As despesas de juros são calculadas usando o método de taxa de juros efetiva. O sistema usará o custo de arrendamento linear para subtrair as despesas de juros para cada mês. O valor é usado para reduzir o ativo DDU.

| Mês | Custo de arrendamento linear | Despesa de Juros                        | Cálculo de despesas de amortização de ativos DDU |
|-------|--------------------------|-----------------------------------------|-----------------------------------------------|
| 1     | (24.000 ÷ 24) = 1.000,00 | (22.888,87 – 1.000) × (5% ÷ 12) = 91,20 | 1.000 – 91,20 = 908,80                        |
| 2     | (24.000 ÷ 24) = 1.000,00 | (21.980,08 – 1.000) × (5% ÷ 12) = 87,42 | 1.000 – 87,42 = 912,58                        |
| 3     | (24.000 ÷ 24) = 1.000,00 | (21.067,49 – 1.000) × (5% ÷ 12) = 83,62 | 1.000 – 83,62 = 916,39                        |

> [!NOTE]
> De acordo com o ASC 842, a depreciação do ativo DDU de um arrendamento operacional é classificada como uma despesa de arrendamento no demonstrativo de renda. Para obter visibilidade, o Arrendamento de ativos descreve a entrada como a depreciação do ativo DDU. No entanto, a entrada de débito deve ser atribuída a uma conta de despesas de arrendamento operacional, e a entrada de crédito deve ser atribuída diretamente ao ativo DDU para o arrendamento operacional. No entanto, nos parâmetros do arrendamento, você pode especificar que as entradas de crédito devem ser feitas em uma conta de depreciação acumulada para ativos DDU operacionais.

## <a name="calculation-of-rou-asset-amortization-expense-for-finance-leases"></a>Cálculo de despesas de amortização de ativos DDU para arrendamentos mercantis

Para arrendamentos com uma classificação mercantil, o sistema calcula a amortização de ativos DDU linear. Portanto, a despesa de depreciação será a mesma para cada mês.

De acordo com o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16) e o ASC 842, o ativo será amortizado sobre o prazo de arrendamento ou a vida útil do ativo, o que for menor. Além disso, se o parâmetro **Transferência de propriedade** estiver ativado para o arrendamento, o arrendamento será automaticamente depreciado na vida útil do ativo.

### <a name="example-of-rou-asset-amortization-expense-for-finance-leases"></a>Exemplo de despesa de amortização de ativos DDU para arrendamentos mercantis

| Campo                                | Alíquota                                   |
|--------------------------------------|-----------------------------------------|
| Como iniciar o balanço do ativo de direito de uso | 22,889.87                               |
| Prazo de arrendamento (meses)                  | 24                                      |
| Vida útil do ativo (meses)           | 36                                      |
| Mês                                | Despesa de amortização de ativo de direito de uso |
| 1                                    | 22.889,87 ÷ 24 = 953,74                 |
| 2                                    | 22.889,87 ÷ 24 = 953,74                 |
| 3                                    | 22.889,87 ÷ 24 = 953,74                 |
