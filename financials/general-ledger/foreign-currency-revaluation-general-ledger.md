---
title: "Reavaliação de moeda estrangeira da Contabilidade"
description: "Este tópico fornece uma visão geral de seguir o processo de reavaliação de moeda estrangeira contabilidade - de instalação, a execução do processo, cálculo do processo, além como reverter transações de reavaliação, se necessário."
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

Este tópico fornece uma visão geral de seguir o processo de reavaliação de moeda estrangeira contabilidade - de instalação, a execução do processo, cálculo do processo, além como reverter transações de reavaliação, se necessário. 

Como parte de um fechamento, às convenções de contabilidade exigem saldos de conta contábil em moedas estrangeiras ser reavaliado os usando tipos de taxa de câmbio diferente (atual, o histórico, médio, etc.). Por exemplo, uma convenção contábil de ativos e as responsabilidades sejam reavaliados a taxa de câmbio atual, em ativos fixos a taxa de câmbio histórica, e lucros e contas de perdas na média mensal. A reavaliação de moeda estrangeira contábil pode ser usado para reavaliar o balanço e as contas de lucros e perdas. 

> [!NOTE]
> A reavaliação de moeda estrangeira também está disponível (AR) em contas a receber e em contas a pagar (AP). Se estiver usando os módulos, as transações devem excelentes ser reavaliado reavaliação usando de moeda estrangeira nesses módulos. A reavaliação de moeda estrangeira de AR e AP criará uma escrituração na contabilidade para refletir o lucro não realizado ou perda, garantindo do razão e a contabilidade podem ser reconciliados. Como reavaliação de moeda estrangeira de AR e AP e cria escriturações na contabilidade, contas a receber e contas de contas a pagar devem ser excluídas de reavaliação de moeda estrangeira contabilidade. 

Quando você executa o processo de reavaliação, o saldo em cada conta principal lançada em uma moeda estrangeira será reavaliado. As transações de lucro não realizado ou transações perdidas criadas durante o processo de reavaliação são geradas pelo sistema. Duas transações podem ser criadas uma, para a moeda contábil e uma segunda para a moeda de relatório, se relevante. Cada escrituração lança lucro não realizado ou perdas e a conta principal que está sendo reavaliada.

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

** ** Datas da taxa pode ser usado para definir a data da taxa de câmbio deve usar como padrão. Por exemplo, você pode reavaliar saldos insira o intervalo de datas do 1º de janeiro ao 31 de janeiro, mas usar a taxa de câmbio definida para o 1º de fevereiro. 

Selecione as contas da reavaliação: Tudo ou, balanço, lucros e perdas. Somente as listas principais marcadas para reavaliação (na página de conta serão reavaliado principal). Se quiser restringir ainda mais o intervalo de contas, principais use registros ** para incluir ** guia para definir um intervalo de contas, ou das principais individuais. 

O processo de reavaliação pode ser executado para uma ou mais entidades legais. A pesquisa exibirá somente as entidades legais as quais você tem acesso. Selecione as entidades legais para o qual você deseja executar o processo de reavaliação. 

Reavaliação pode ser realizado para uma ou mais moedas estrangeiras. A pesquisa incluirá todas as moedas lançadas no intervalo de data relevante para o tipo de conta principal (balanço ou esses lucros entre e perdas), pois as entidades legais selecionadas para reavaliar. A moeda contábil será incluída na lista, mas nada será reavaliado se a moeda contábil estiver selecionada. 

Conjunto ** visualização antes de lançar ** ** Sim ** se deseja de revisar o resultado de reavaliação de contabilidade. A exibição na contabilidade for diferente da simulação na reavaliação de moeda estrangeira de CR e CP. A simulação em dias e é AP em um relatório, mas a contabilidade tiver uma visualização que possa ser lançado, sem precisar executar novamente o processo de reavaliação. Os resultados de exibição podem ser exportados para o Microsoft Excel para manter o histórico como os valores forem calculados. Você não pode usar o processamento em lotes se você deseja visualizar os resultados de reavaliação. Visualização, o usuário tem a opção de lançar os resultados de todas as entidades legais usando **Lançar** o botão. Se houver um problema com os resultados de uma entidade legal, o usuário também tem a opção de lançar um subconjunto entidades legais usando **Entidades legais no lançamento** o botão. 

Depois que o processo de reavaliação de moeda estrangeira é concluído, será criado um registro para controlar o histórico de cada execução.  Um registro separado será criado para cada entidade legal e nível de lançamento.

## <a name="calculate-unrealized-gainloss"></a>Calcule lucros/perdas não realizado
As transações de lucros/perdas não realizado são criadas de forma diferente entre reavaliação contábil e o processo de reavaliação de AR e AP. Em dias e o MESMO, reavaliação anterior estiver completa revertida (supondo a transação não será liquidada ainda) e uma nova transação é criada de reavaliação para lucros/perdas não realizado com base na nova taxa de câmbio. Isso porque é reavaliamos cada transação individual em dias e o MESMO. Na contabilidade, reavaliação anterior não for revertida. Em vez disso, uma transação será criada para delta insira o saldo de conta a incluir todas, reavaliação valor anterior, e o novo valor com base na taxa de câmbio da data da taxa. 

** Exemplo ** seguir existem os saldos para a conta 110110 principal.

|            |                    |                        |                       |
|------------|--------------------|------------------------|-----------------------|
| **Data**   | **Conta contábil** | **Valor da transação** | **Valor contábil** |
| Janeiro de 20 | 110110 (Dinheiro)      | 500 EUR (Débito)        | 1000 USD (Débito)      |

A conta é reavaliada principal o 31 de janeiro.  Lucros/perdas não realizado é calculado a seguir.

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

Uma nova transação é lançada para o mês de fevereiro.  A conta é reavaliada principal o 28 de fevereiro.

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

Você pode reverter os resultados da ordem com de reavaliação, mas talvez seja necessário inverter também uma reavaliação atuais para garantir que os saldos correto para cada conta reavaliada principal. As reversões podem ocorrer com a ordem porque não há como controlar quais contas principais são reavaliados e frequência quando são reavaliados. Por exemplo, uma empresa pode optar para reavaliar trimestralmente principais suas contas de caixa, mas todas contas principais restantes mensais.


