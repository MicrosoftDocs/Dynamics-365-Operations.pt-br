---
title: Data UEPS com marcação e valor físico
description: Data UEPS (último a entrar, primeiro a sair) é um modelo de estoque baseado no princípio UEPS. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque. Ao usar a Data UEPS, se não houver um recebimento antes da saída, a saída será liquidada com relação a qualquer recebimento que ocorra após a data da saída. Várias saídas na mesma data serão liquidadas na ordem última saída, último recebimento.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Retail
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1fed3de8741b375cf4992578db3e57d6e5a35a93
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980619"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>Data UEPS com marcação e valor físico

[!include [banner](../includes/banner.md)]

Data UEPS (último a entrar, primeiro a sair) é um modelo de estoque baseado no princípio UEPS. As saídas do estoque são liquidadas em relação aos últimos recebimentos do estoque com base na data da transação de estoque. Ao usar a Data UEPS, se não houver um recebimento antes da saída, a saída será liquidada com relação a qualquer recebimento que ocorra após a data da saída. Várias saídas na mesma data serão liquidadas na ordem última saída, último recebimento. 

Quando você usa o modelo de estoque de Data UEPS (último a entrar, primeiro a sair), se não houver um recebimento antes da saída, a saída será liquidada com relação a qualquer recebimento que ocorra após a data da saída. Várias saídas na mesma data podem ser liquidadas na ordem de última saída, último recebimento. Ao usar a Data UEPS, você não precisará usar a regra da Data UEPS. Em vez disso, você poderá marcar transações de estoque de tal forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. 

Recomendamos um fechamento de estoque periódico quando o modelo de estoque Data UEPS for usado. 

Os exemplos a seguir mostram o efeito de usar a Data UEPS nas três configurações:

-   Data UEPS sem a opção **Incluir valor físico**
-   Data UEPS com a opção**Incluir valor físico**
-   Data UEPS com marcação

## <a name="lifo-date-without-the-include-physical-value-option"></a>Data UEPS sem a opção Incluir valor físico
Neste exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 15,00 (média ponderada de transações atualizadas financeiramente).
-   4a. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de BRL 15,00 (média ponderada de transações atualizadas financeiramente).
-   5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   6. O fechamento de estoque é executado. Com base no método da Data UEPS, a última saída atualizada financeiramente será liquidada com o último recebimento atualizado financeiramente por data. Um ajuste de BRL 5,00 será feito na transação de saída. Essas transações serão liquidadas entre si.

O novo preço de custo médio reflete a média de transações atualizadas financeiramente em BRL 15,00. 

A ilustração a seguir mostra os efeitos do modelo de estoque de Data UEPS quando a opção **Incluir valor físico** não for usada. ![Data UEPS com Incluir Valor Físico](./media/lifodatewithoutincludephysicalvalue.gif) 

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="lifo-date-with-the-include-physical-value-option"></a>Data UEPS com a opção Incluir valor físico
Você pode marcar a caixa de seleção **Incluir valor físico** de um item na página **Grupos de modelo do item**. Neste caso, o sistema usará as transações de recebimento físico e financeiro para calcular o preço de custo médio. Quando aplicável, o sistema também fará ajustes para a transação de saída atualizada fisicamente. Quando a caixa de seleção **Incluir valor físico** for desmarcada, o fechamento de estoque que usa o modelo de estoque de Data UEPS liquidará somente transações que são atualizadas financeiramente. 

Nesse exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. 

A ilustração a seguir mostra estas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 18,33 cada (média ponderada de transações atualizadas financeiramente).
-   4a. Saída financeira de estoque para uma quantidade de 1 ao preço de custo de BRL 18,33 cada (média ponderada de transações atualizadas financeiramente).
-   5a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   6. O fechamento de estoque é executado. Com base no método da Data UEPS, a última saída atualizada será ajustada ou liquidada no último recebimento atualizado por data. Essas transações não serão liquidadas entre si porque a transação de recebimento financeiro será ajustada para uma transação de atualização física. Em vez disso, apenas um ajuste de BRL 6,67 será feito na transação de saída.

O novo preço de custo médio reflete a média de transações atualizadas financeiramente em BRL 20,00. 

A ilustração a seguir mostra os efeitos do modelo de estoque UEPS quando a opção **Incluir valor físico** for usada. ![Data UEPS com Incluir Valor Físico](./media/lifodatewithincludephysicalvalue.gif) 

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.

## <a name="lifo-date-with-marking"></a>Data UEPS com marcação
A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. 

Por exemplo, o departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Como esta é uma ordem urgente, você terá de pagar mais por esse item para atender às solicitações do cliente. É necessário garantir que o custo desse item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. 

Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Se esse documento de ordem de vendas for marcado para a ordem de compra antes da guia de remessa ou a fatura ser lançada, o COGS será BRL 120,00, não o custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a fatura for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio. 

Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra. 

Por exemplo, uma transação de recebimento é marcada para uma transação de saída. Neste caso, o método de avaliação definido no grupo de modelo de item do item será desconsiderado e o sistema liquidará essas transações entre si. 

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
-   7. O fechamento de estoque é executado. Como a transação Primeiro a entrar, Primeiro a sair (PEPS) atualizada financeiramente é marcada como um recebimento existente, essas transações são liquidadas uma para a outra e nenhum ajuste é feito.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente em BRL 27,50. 

A ilustração a seguir mostra os efeitos do modelo de estoque de UEPS quando é usada uma marcação entre as saídas e os recebimentos. ![Data UEPS com Marcação](./media/lifodatewithmarking.gif) 

**Chave para o diagrama**

- As transações de estoque são representadas por setas verticais.
- Os recebimentos no estoque são representados por setas verticais sobre a linha do tempo.
- Saídas fora do estoque são representadas por setas verticais abaixo da linha do tempo.
- Acima (ou abaixo) de cada seta vertical, o valor da transação de estoque é especificado no formato de quantidade x preço unitário.
- Um valor de transação de estoque entre parênteses indica que a transação de estoque é lançada fisicamente no estoque.
- Um valor de transação de estoque que não estiver entre parênteses indica que a transação de estoque é lançada financeiramente no estoque.
- Cada nova transação de recebimento ou saída é designada por uma nova etiqueta.
- Cada seta vertical é rotulada com um identificador sequencial, como *1a*. Os identificadores indicam a ordem de lançamentos de transação de estoque na linha do tempo.
- Os fechamentos de estoque são representados por uma linha tracejada vertical vermelha e a etiqueta *Fechamento de Estoque*.
- As liquidações executadas pelo fechamento de estoque são representadas por linhas tracejadas diagonais de um recebimento para uma saída.




