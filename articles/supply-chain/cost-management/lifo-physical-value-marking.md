---
title: "UEPS com marcação e valor físico"
description: "Último a entrar, Primeiro a sair (UEPS) é um modelo de estoque no qual os últimos (mais recentes) recebimentos são emitidos primeiro. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 86bafb9346b7335bf0a5d6c156eee6d53f1998a9
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="lifo-with-physical-value-and-marking"></a>UEPS com marcação e valor físico

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Último a entrar, Primeiro a sair (UEPS) é um modelo de estoque no qual os últimos (mais recentes) recebimentos são emitidos primeiro. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque. 

No modelo UEPS (último a entrar, primeiro a sair), os últimos (mais novos) recebimentos saem primeiro. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque. Quando você usar UEPS, não precisará usar a regra de UEPS. Em vez disso, você poderá marcar transações de estoque de tal forma que a emissão de um item específico seja liquidado em relação a um recebimento específico. É recomendável um fechamento de estoque periódico quando você usa o modelo de estoque UEPS. 

Os exemplos a seguir mostram o efeito de usar o UEPS nas três configurações:

-   UEPS sem a opção **Incluir valor físico**
-   UEPS com a opção **Incluir valor físico**
-   UEPS com marcação

## <a name="lifo-without-the-include-physical-value-option"></a>UEPS sem a opção Incluir valor físico
Neste exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 20,00 cada (média ponderada de transações atualizadas financeiramente).
-   5b. Saída financeira de estoque para uma quantidade de 1 a um preço de custo de BRL 20,00 cada (média ponderada de transações atualizadas financeiramente).
-   6. O fechamento de estoque é executado. Com base no método UEPS, a última saída atualizada financeiramente será liquidada para o último recebimento atualizado financeiramente. Um ajuste de BRL 10,00 será feito na transação de saída.

O novo preço de custo médio reflete a média de transações atualizadas financeiramente em BRL 15,00. A ilustração a seguir mostra os efeitos do modelo de estoque LIFO nesta série de transações quando a opção **Incluir valor físico** não é usada. ![UEPS sem Incluir Valor Físico](./media/lifowithoutincludephysicalvalue.gif) 

**Chave para o diagrama**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato Quantity@Unit price.
-   Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
-   Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="lifo-with-the-include-physical-value-option"></a>UEPS com a opção Incluir valor físico
Se a caixa de seleção **Incluir valor físico** for marcada para um item na página **Grupos de modelos do item**, o sistema usará as transações de recebimento físico e financeiro para calcular o preço de custo médio em execução. Quando aplicável, o sistema também fará ajustes para a transação de saída atualizada fisicamente. Quando a caixa de seleção **Incluir valor físico** estiver desmarcada, o fechamento de estoque com o modelo de estoque UEPS liquidará somente as transações atualizadas financeiramente. 

A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 cada (média de transações atualizadas financeiramente e fisicamente).
-   5b. Saída financeira de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 cada (média de transações atualizadas financeiramente e fisicamente).
-   6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 21,25 cada.
-   7. O fechamento de estoque é executado. Com base no método UEPS, a última transação de saída será ajustada ou liquidada para o último recebimento atualizado.

A transação 6a será ajustada para a transação de recebimento 4b. O sistema não liquidará essas transações, já que o recebimento é atualizado fisicamente, mas não financeiramente. Em vez disso, só será lançado um ajuste de BRL 8,75 para a transação de saída física. A transação 5b será ajustada para a transação de recebimento física 3a. O sistema não liquidará essas transações porque elas não estão atualizadas financeiramente. Em vez disso, só será feito um ajuste de BRL –3,75 para essa transação de saída. O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente, em BRL 20,00. 

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS nesta série de transações quando a opção **Incluir valor físico** é usada. ![UEPS com Incluir Valor Físico](./media/lifowithincludephysicalvalue.gif) 

**Chave para o diagrama**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato Quantity@Unit price.
-   Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
-   Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="lifo-with-marking"></a>UEPS com marcação
A marcação é um processo do que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. Por exemplo, o departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Como esta é uma ordem urgente, você deverá pagar mais por esse item para atender às solicitações do cliente. 

É necessário garantir que o custo desse item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Se esse documento de ordem de vendas for marcado para a ordem de compra antes da guia de remessa ou a fatura ser lançada, o COGS será BRL 120,00, não o custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a fatura for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio. 

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra. 

É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer isso em uma linha da ordem de venda na página **Detalhes da ordem de venda**. Você pode exibir as transações de recebimento abertas na página **Marcação**. 

É possível marcar uma transação de saída para um recebimento depois que a transação for lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado. 

A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 cada (média de transações atualizadas financeiramente e fisicamente).
-   5b. A saída financeira do estoque para uma quantidade de 1 é marcada para o recebimento de estoque 2b antes da transação ser lançada. Essa transação é lançada com o preço de custo de BRL 20,00 cada.
-   6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 21,25 cada.
-   7. O fechamento de estoque é executado. Como as transações PEPS atualizadas financeiramente são marcadas para um recebimento existente, essas transações são liquidadas uma para a outra e nenhum ajuste é feito.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente, em BRL 27,50. 

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS nesta série de transações quando a marcação entre saídas e recebimentos é usada. ![UEPS com Marcação    ](./media/lifowithmarking.gif) 

**Chave para o diagrama**

-   As transações de estoque são representadas por setas verticais.
-   Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
-   Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
-   Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato Quantity@Unit price.
-   Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
-   Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
-   Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
-   Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
-   Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
-   As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.





