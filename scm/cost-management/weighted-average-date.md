---
title: "Data de média ponderada"
description: 
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2a0d3fe9dcdb58e40d519b2792700dd6d40bb99d
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="weighted-average-date"></a>Data de média ponderada

[!include[banner](../includes/banner.md)]


A data de média ponderada é um modelo de estoque baseado no princípio de média ponderada. Para o princípio de média ponderada, as saídas do estoque são avaliadas pelo valor médio dos itens recebidos no estoque para cada dia no período de fechamento de estoque. Quando você executa um fechamento de estoque usando uma data de média ponderada, todos os recebimentos diários são liquidados em relação a uma saída virtual. Essa saída virtual contém a quantidade total recebida e o valor desse dia. A saída virtual possui um recebimento virtual correspondente do qual as saídas serão liquidadas. Portanto, todas as saídas recebem o mesmo custo médio. A saída e o recebimento virtuais podem ser considerados como uma transferência virtual, conhecida como *transferência de fechamento de estoque de média ponderada*. 

Se somente um recebimento tiver ocorrido até a data, não será necessário avaliar a média. Como todas as saídas são liquidadas a partir desse recebimento, a transferência virtual não será criada. Da mesma forma, se só houver saídas na data, não haverá recebimentos dos quais avaliar a média, e a transferência virtual também não será criada. Ao usar a data de média ponderada, você poderá marcar transações de estoque de tal forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. Nesse caso, você não usará a regra de data de média ponderada. Recomendamos um fechamento de estoque mensal quando o modelo de estoque de data de média ponderada for usado. 

A seguinte fórmula é usada para calcular o método de avaliação de custo de data de média ponderada: 

Média ponderada = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q*n* × P*n*\]) ÷ (Q1 + Q2 + Q*n*) 

Durante o fechamento do estoque, o cálculo é executado diariamente ao longo do período de fechamento como mostrado na ilustração a seguir. 

![Modelo de cálculo diário de data de média ponderada](./media/weightedaveragedatedailycalculationmodel.gif) 

As transações de estoque que deixam o estoque, como ordens de venda, diários de estoque e ordens de produção, ocorrem a um preço de custo estimado na data de lançamento. Esse preço de custo estimado também é conhecido como o preço de custo médio. Na data de fechamento de estoque, o sistema analisará as transações de estoque para períodos anteriores, para dias anteriores e para o dia atual. Essa análise é usada para determinar quais dos seguintes princípios de fechamento devem ser usados:

-   Liquidação direta
-   Liquidação resumida

As liquidações são lançamentos de fechamento de estoque que ajustam as saídas para a média ponderada correta a partir da data de fechamento. 

**Observação:** Para obter mais informações sobre liquidações, consulte o artigo sobre o encerramento do estoque. Os seguintes exemplos ilustram o efeito do uso da média ponderada com cinco configurações:

-   Liquidação direta de data de média ponderada quando a opção **Incluir valor físico** não é usada
-   Liquidação resumida de data de média ponderada quando a opção **Incluir valor físico** não é usada
-   Liquidação direta de data de média ponderada quando a opção **Incluir valor físico** é usada
-   Liquidação resumida de data de média ponderada quando a opção **Incluir valor físico** não é usada
-   Data de média ponderada quando a marcação é usada

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidação direta de data de média ponderada quando a opção Incluir valor físico não é usada
A versão atual usa o mesmo princípio de liquidação direta que era usada para média ponderada em versões anteriores. O sistema liquida diretamente entre recebimentos e saídas. O sistema usa esse princípio de liquidação direta em certas situações específicas:

-   Um recebimento e uma ou mais saídas foram lançados no período.
-   Somente saídas foram lançadas no período e o estoque contém itens disponíveis de um fechamento anterior.

No cenário a seguir, foram lançados um recebimento e uma saída atualizados financeiramente. Durante o fechamento de estoque, o sistema liquidará o recebimento diretamente contra a saída e não será necessário nenhum ajuste para o preço de custo na saída. 

A ilustração a seguir mostra estas transações:

-   1a. O recebimento físico de estoque é atualizado para uma quantidade 5 a um custo de BRL 10,00 cada.
-   1b. O recebimento financeiro de estoque é atualizado para uma quantidade 5 a um custo de BRL 10,00 cada.
-   2a. A saída física de estoque é atualizada para uma quantidade 2 a um custo de BRL 10,00 cada.
-   2b. A saída financeira de estoque é atualizada para uma quantidade 2 a um custo de BRL 10,00 cada.
-   3. O fechamento de estoque é executado usando o método de liquidação direta para liquidar o recebimento financeiro de estoque para a saída financeira de estoque.

![Liquidação direta de data de média ponderada sem a opção Incluir valor físico](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Chave para a ilustração:**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato *Quantidade*@*Preço unitário*.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada fisicamente no estoque.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas vermelhas pontilhadas na diagonal de um recebimento para uma saída.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidação resumida de data de média ponderada quando a opção Incluir valor físico não é usada
A média ponderada baseia-se no princípio de que todos os recebimentos em um período de fechamento são resumidos em uma nova transação de transferência de estoque. Essa transação é conhecida como *Fechamento de estoque de média ponderada*. Todos os recebimentos para a data serão liquidados contra a saída da recém-criada transação de transferência de estoque. Todas as saídas para a data são liquidadas em relação ao recebimento da nova transação de transferência de estoque. Se o estoque disponível for positivo depois do fechamento de estoque, o estoque disponível e o valor do estoque são resumidos no novo recebimento de transação de transferência de estoque. Se o estoque disponível for negativo depois do fechamento de estoque, o estoque disponível e o valor do estoque serão a soma de saídas individuais que não foram liquidadas completamente. 

No cenário a seguir vários recebimentos e saídas atualizados financeiramente foram lançados durante o período. Durante o fechamento de estoque, o sistema avaliará todos os dias para determinar como cada um deve ser tratado pelo fechamento. 

A ilustração a seguir mostra estas transações: 

**Dia 1:**

-   1a. O recebimento físico de estoque é atualizado para uma quantidade 3 a BRL 15,00 cada.
-   1b. O recebimento financeiro de estoque é atualizado para uma quantidade 3 a BRL 15,00 cada.
-   2a. Saída física de estoque para uma quantidade de 1 ao custo médio de BRL 15,00 cada.
-   2a. Saída financeira de estoque para uma quantidade de 1 ao custo médio de BRL 15,00 cada.

O sistema usará a abordagem de liquidação direta para o dia 1. 

**Dia 2:**

-   3a. Saída física de estoque para uma quantidade 1 a um custo médio de BRL 15,00 cada
-   3b. saída financeira de estoque para uma quantidade igual a 1 a um custo médio em execução de R$ 15,00

O sistema usará a abordagem de liquidação direta para o dia 2. 

**Dia 3:**

-   4a. Saída física de estoque para uma quantidade 1 a um custo médio de BRL 15,00 cada
-   4b. saída financeira de estoque para uma quantidade igual a 1 a um custo médio em execução de R$ 15,00
-   5a. Recebimento físico de estoque para uma quantidade 1 a BRL 17,00 cada
-   5b. Recebimento financeiro de estoque para uma quantidade 1 a BRL 17,00 cada

O fechamento de estoque é executado. Será preciso usar a liquidação direta porque há vários recebimentos ao longo de vários dias.

-   7a. Uma saída financeira de transação de fechamento de estoque de média ponderada é criada para uma quantidade 2 a BRL 32,00 para resumir as liquidações de todos os recebimentos financeiros de estoque até a data atual que não tenham sido fechados.
-   7b. Um recebimento financeiro de transação de fechamento de estoque de média ponderada é criado como compensação para 7a.

O sistema gera e lança a transação de transferência de estoque resumida. Além disso, o sistema liquida todos os recebimentos para o dia e o estoque disponível para dias anteriores em relação à transação de saída de transferência de estoque resumida. Todas as saídas do dia são liquidadas em relação à transação de recebimento de transferência de estoque resumida. O preço de custo médio ponderado é calculado como BRL 16,00. A saída terá um ajuste de BRL 1,00 para ajustar-se ao custo médio ponderado. O novo preço de custo médio é BRL 16,00. 

A ilustração a seguir mostra essa série de transações e os efeitos do uso do modelo de estoque de média ponderada e o princípio de liquidação resumida sem usar a opção **Incluir valor físico**. 

![Liquidação resumida de data de média ponderada sem a opção Incluir valor físico](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Chave para a ilustração**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato *Quantidade*@*Preço unitário*.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada fisicamente no estoque.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas vermelhas pontilhadas na diagonal de um recebimento para uma saída.
-   As setas diagonais vermelhas mostram as transações de recebimento liquidadas para a transação de saída criada pelo sistema.
-   A seta diagonal verde representa a transação de recebimento de compensação gerada pelo sistema para a qual a transação de saída lançada originalmente é liquidada

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Liquidação direta de data de média ponderada quando a opção Incluir valor físico é usada
A versão atual usa o mesmo princípio de liquidação direta para a data média ponderada que é usada em versões anteriores. O sistema liquida diretamente entre recebimentos e saídas. O sistema usa esse princípio de liquidação direta em certas situações específicas:

-   Um recebimento e uma ou mais saídas foram lançados no período.
-   Somente saídas foram lançadas no período e o estoque contém estoque disponível de um fechamento anterior.

Se você marcar a caixa de seleção **Incluir valor físico** para um item na página **Grupo de modelos de item**, o sistema usará recebimentos atualizados fisicamente quando calcular o preço de custo estimado ou de custo médio. As saídas são lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, somente os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidação resumida de data de média ponderada quando a opção Incluir valor físico não é usada
Se você marcar a caixa de seleção **Incluir valor físico** para um item na página **Grupo de modelos de item**, o sistema usará recebimentos atualizados fisicamente quando calcular o preço de custo estimado ou de custo médio. As saídas são lançadas com base nesse preço de custo estimado durante o período. Durante o fechamento de estoque, somente os recebimentos atualizados financeiramente serão considerados somente no cálculo de média ponderada. A liquidação da média ponderada se baseia no princípio de que todos os recebimentos em um período de fechamento são resumidos em uma nova transação de transferência de estoque, conhecida como *fechamento de estoque de média ponderada*. Todos os recebimentos para a data serão liquidados contra a saída da recém-criada transação de transferência de estoque. Todas as saídas para a data são liquidadas em relação ao recebimento da nova transação de transferência de estoque. Se o estoque disponível for positivo depois do fechamento de estoque, o estoque disponível e o valor do estoque são resumidos na nova transação de transferência de estoque (recebimento). Se o estoque disponível for negativo depois do fechamento de estoque, o estoque disponível e o valor do estoque serão a soma de saídas individuais que não foram liquidadas completamente.

## <a name="weighted-average-date-when-marking-is-used"></a>Data de média ponderada quando a marcação é usada
A marcação é um processo que permite vincular uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. 

Por exemplo, seu departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Porque esta é uma ordem urgente, você terá de pagar mais por esse item para atender às solicitações do cliente. É necessário garantir que o custo desse item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. O documento de ordem de venda é marcado para a ordem de compra antes do lançamento da guia de remessa ou da fatura. Então, o COGS será de R$ 120,00 em vez do custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a nota fiscal for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio. Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra. Quando uma transação de recebimento é marcada para uma transação de saída, o método de avaliação definido no grupo de modelos de de item é desconsiderado. Em vez disso, o sistema liquida essas transações uma para a outra. 

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer isso em uma linha da ordem de venda na página **Detalhes da ordem de venda**. Você pode exibir as transações de recebimento abertas na página **Marcação**. É possível marcar uma transação de saída para um recebimento depois que a transação é lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado. A ilustração a seguir mostra estas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao preço de custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao preço de custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao preço de custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao preço de custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao preço de custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao preço de custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao preço de custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 21,25 (média de transações atualizadas financeiramente e fisicamente).
-   5b. Saída financeira para uma quantidade de 1 é marcada para o recebimento de estoque 2b antes da transação ser lançada. Essa transação é lançada ao preço de custo de BRL 20,00.
-   6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 21,25.
-   7. O fechamento de estoque é executado. Como as transações atualizadas financeiramente são marcadas para um recebimento existente, essas transações são liquidadas uma para a outra e nenhum ajuste é feito.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente em BRL 27,50. A ilustração a seguir mostra essa série de transações e os efeitos de usar o modelo de estoque de data de média ponderada e a marcação.

![Data de média ponderada com a marcação](./media/weightedaveragedatewithmarking.gif) 

**Chave para a ilustração:**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato *Quantidade*@*Preço unitário*.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada fisicamente no estoque.
-   Se um valor de transação de estoque estiver entre parênteses, a transação de estoque será lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a seqüência de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas vermelhas pontilhadas na diagonal de um recebimento para uma saída.





