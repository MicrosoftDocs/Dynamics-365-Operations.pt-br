---
title: "Reavaliação de moeda estrangeira da Contabilidade"
description: "Este tópico fornece uma visão geral dos seguintes procedimentos para o processo de reavaliação de moeda estrangeira da contabilidade: instalação, execução do processo, cálculo do processo e como reverter transações de reavaliação, se necessário."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CurrencyLedgerGainLossAccount
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 62153
ms.assetid: 842e8561-560f-4cc6-8668-70cca60b1ba3
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: 5d6d13fe44eef7766b4dcaf274c3522bce3da816
ms.lasthandoff: 03/31/2017


---

# <a name="foreign-currency-revaluation-for-general-ledger"></a>Reavaliação de moeda estrangeira da Contabilidade

[!include[banner](../includes/banner.md)]


Este tópico fornece uma visão geral dos seguintes procedimentos para o processo de reavaliação de moeda estrangeira da contabilidade: instalação, execução do processo, cálculo do processo e como reverter transações de reavaliação, se necessário. 

Como parte de um fechamento, às convenções de contabilidade exigem saldos de conta contábil em moedas estrangeiras ser reavaliado os usando tipos de taxa de câmbio diferente (atual, o histórico, médio, etc.). Por exemplo, uma convenção contábil de ativos e as responsabilidades sejam reavaliados a taxa de câmbio atual, em ativos fixos a taxa de câmbio histórica, e lucros e contas de perdas na média mensal. A reavaliação de moeda estrangeira contábil pode ser usado para reavaliar o balanço e as contas de lucros e perdas. 

> [!NOTE]
> A reavaliação de moeda estrangeira também está disponível em para Contas a receber (AR) e Contas a pagar (AP). Se estiver usando estes módulos, as transações pendentes devem ser reavaliadas usando a reavaliação de moeda estrangeira nestes módulos. A reavaliação de moeda estrangeira de AR e AP criará uma escrituração na contabilidade para refletir o lucro não realizado ou perda, garantindo do razão e a contabilidade podem ser reconciliados. Como reavaliação de moeda estrangeira de AR e AP e cria escriturações na contabilidade, contas a receber e contas de contas a pagar devem ser excluídas de reavaliação de moeda estrangeira contabilidade. 

Quando você executa o processo de reavaliação, o saldo em cada conta principal lançada em uma moeda estrangeira será reavaliado. As transações de lucro não realizado ou transações perdidas criadas durante o processo de reavaliação são geradas pelo sistema. Duas transações podem ser criadas uma, para a moeda contábil e uma segunda para a moeda de relatório, se relevante. Cada escrituração lançará lucro ou perda não realizado e a conta principal que está sendo reavaliada.

## <a name="prepare-to-run-foreign-currency-revaluation"></a>Preparação para executar a reavaliação de moeda estrangeira
Para executar o processo de reavaliação, é necessária uma configuração adicional.

-   Na página **Conta principal**:
-   Se a conta principal tiver de ser reavaliada na Contabilidade, selecione **Reavaliação de moeda estrangeira**. Se a conta for principal reavaliada (como a de AR e se o MESMO reavaliado em razão), desmarque esta opção.
-   Se a conta principal estiver marcado para reavaliação, entre em **Tipo de taxa de câmbio**. Este tipo de taxa de câmbio será usado reavaliando a conta principal. Um campo, **Tipo de taxa de câmbio de relatório financeiro** separado, disponíveis para relatórios financeiros. Os dois campos não são mantidos na sincronização, permitindo tipos de taxa de câmbio diferente ser usado para a reavaliação e o relatório financeiro.

-   Na página **Razão**:
-   Especifique **Tipo de taxa de câmbio**. Se o tipo de taxa de câmbio não for definido na conta principal, este tipo de taxa de câmbio será usado na reavaliação de moeda estrangeira.
-   Especifique o lucro realizado, a perda realizada, o lucro não realizado e a perda não realizada para a reavaliação de moeda. As contas de lucros realizados e perdas realizadas são usadas em transações liquidadas AR e AP, e as contas de lucro não realizado e de perda não realizada são usadas em transações abertas e contas principais de contabilidade.

-   Na página **Contas de reavaliação de moeda**:
-   A reavaliação de moeda diferente selecionar para cada moeda e empresa. Se nenhuma conta for definida, as contas da página **Razão** serão usadas.

## <a name="process-foreign-currency-revaluation"></a>Processar uma reavaliação de moeda estrangeira
Ao concluir a configuração, use a página **Reavaliação de moeda estrangeira** para reavaliar as transações e os saldos das contas principais. Você pode executar o processo em tempo real ou agendá-lo para execução usando um lote. 

A página **Reavaliação de moeda estrangeira** exibe o histórico por processo de reavaliação, incluindo quando o processo foi executado, que foram definidos critérios, um link para comprovantes criada para reavaliação, e um registro anterior se a reavaliação tiver sido revertida. Para executar o processo de reavaliação, clique no botão **Reavaliação de moeda estrangeira**. 

**A data** Valores e **Até** defina o intervalo de datas para calcular o saldo em moeda estrangeira a ser reavaliado. Quando você reavalia as contas de lucros e perdas, todas as transações que ocorrem no intervalo de datas são reavaliadas. Quando você reavalia as contas de balanço, data é ignorado. Em vez disso, o saldo a ser reavaliado é determinado pela o início do ano fiscal até a data até. 

A **Data da taxa** pode ser usada para definir a data na qual a taxa de câmbio deve ser padronizada. Por exemplo, você pode reavaliar saldos entre o intervalo de datas de 1º de janeiro ao 31 de janeiro, mas usar a taxa de câmbio definida para 1º de fevereiro. 

Selecione as contas da reavaliação: Tudo ou, balanço, lucros e perdas. Somente as contas principais marcadas para reavaliação (na página Conta principal) serão reavaliadas. Se quiser restringir ainda mais o intervalo de contas principais, use a guia Registros **para incluir** um intervalo de contas principais ou contas principais individuais. 

O processo de reavaliação pode ser executado para uma ou mais entidades legais. A pesquisa exibirá somente as entidades legais às quais você tem acesso. Selecione as entidades legais para as quais você deseja executar o processo de reavaliação. 

Reavaliação pode ser realizado para uma ou mais moedas estrangeiras. A pesquisa incluirá todas as moedas lançadas no intervalo de data relevante para o tipo de conta principal (balanço ou lucros e perdas), para as entidades legais selecionadas para reavaliação. A moeda contábil será incluída na lista, mas nada será reavaliado, se a moeda contábil estiver selecionada. 

Defina **Visualizar antes do lançamento** como **Sim** se quiser revisar o resultado da reavaliação da Contabilidade. A exibição na contabilidade é diferente da simulação na reavaliação de moeda estrangeira de AR e AP. A simulação em AR e AP é um relatório, mas a contabilidade tem uma visualização que pode ser lançada, sem precisar executar novamente o processo de reavaliação. Os resultados de exibição podem ser exportados para o Microsoft Excel para manter o histórico como os valores forem calculados. Você não pode usar o processamento em lotes se você deseja visualizar os resultados de reavaliação. Visualização, o usuário tem a opção de lançar os resultados de todas as entidades legais usando **Lançar** o botão. Se houver um problema com os resultados de uma entidade legal, o usuário também tem a opção de lançar um subconjunto entidades legais usando **Entidades legais no lançamento** o botão. 

Depois que o processo de reavaliação de moeda estrangeira for concluído, será criado um registro para controlar o histórico de cada execução.  Um registro separado será criado para cada entidade legal e nível de lançamento.

## <a name="calculate-unrealized-gainloss"></a>Calcule lucros/perdas não realizado
As transações de lucros/perdas não realizado são criadas de forma diferente entre reavaliação contábil e o processo de reavaliação de AR e AP. Em dias e o MESMO, reavaliação anterior estiver completa revertida (supondo a transação não será liquidada ainda) e uma nova transação é criada de reavaliação para lucros/perdas não realizado com base na nova taxa de câmbio. Isso porque é reavaliamos cada transação individual em dias e o MESMO. Na contabilidade, a reavaliação anterior não é revertida. Em vez disso, uma transação será criada para o delta entre o saldo da conta principal, incluindo todos os valores de reavaliação anterior, e o novo valor com base na taxa de câmbio da data da taxa. 

**Exemplo** Existem os seguintes saldos para a conta principal 110110.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Data**   | **Conta contábil** | **Valor da transação** | **Valor contábil** |
| Janeiro de 20 | 110110 (Dinheiro)      | 500 EUR (Débito)        | 1000 USD (Débito)      |

A conta principal é reavaliada em 31 de janeiro.  O lucro/perda não realizado é calculado como segue.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo atual na moeda da transação** | **Saldo atual na moeda contábil** | **Taxa de câmbio na reavaliação** | **Novo valor de moeda de contabilidade** | **Lucro/perda não realizado**    |
| 500 EUR                                     | 1000 USD                                   | 166.6667                         | 833,33 EUR (500 x 1,666667)        | 166,67 perda (833,33 – 1000) |

A entrada de contabilidade a seguir será criada.

|            |                          |           |            |
|------------|--------------------------|-----------|------------|
| **Data**   | **Conta contábil**       | **Débito** | **Crédito** |
| 31 de janeiro | 110110 (Dinheiro)            |           | 166.67     |
| 31 de janeiro | 801400 (perda não realizada) | 166.67    |            |

Nenhuma transação nova será lançada para o mês de fevereiro.  A conta principal será reavaliada em 28 de fevereiro.

|                                             |                                            |                                  |                                    |                             |
|---------------------------------------------|--------------------------------------------|----------------------------------|------------------------------------|-----------------------------|
| **Saldo atual na moeda da transação** | **Saldo atual na moeda contábil** | **Taxa de câmbio na reavaliação** | **Novo valor de moeda de contabilidade** | **Lucro/perda não realizado**    |
| 500 EUR                                     | 833,33 USD (1000 - 166,67)                 | 250.0000                         | 1250 USD (500 x 2,5)               | 416,67 ganho (1250 – 833,33) |

A entrada de contabilidade a seguir será criada.

|             |                          |           |            |
|-------------|--------------------------|-----------|------------|
| **Data**    | **Conta contábil**       | **Débito** | **Crédito** |
| 28 de fevereiro | 110110 (Dinheiro)            | 416.67    |            |
| 28 de fevereiro | 801600 (lucro não realizado) |           | 416.67     |

## <a name="reverse-foreign-currency-revaluation"></a>Reavaliação de moeda estrangeira reversa
Se você precisa reverter a transação de reavaliação, selecione o botão **Transação revertida** na página **Reavaliação de moeda estrangeira**. Histórico de um registro novo reavaliação de moeda estrangeira será criado para manter o histórico trilha de auditoria de reavaliação quando ocorreu ou foi revertida. 

Você pode reverter os resultados da ordem de reavaliação desatualizada, mas também pode ser necessário reverter uma reavaliação mais atual para garantir os saldos corretos para cada conta principal reavaliada. As reversões podem ocorrer com a ordem desatualizada porque não há como controlar quais contas principais são reavaliadas e frequência na qual são reavaliadas. Por exemplo, uma empresa pode optar para reavaliar trimestralmente sua principais contas de caixa, e mensalmente todas as contas principais restantes.




