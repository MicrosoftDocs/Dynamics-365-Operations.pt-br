---
title: PEPS com marcação e valor físico
description: Primeiro a entrar, Primeiro a sair (PEPS) é um modelo de estoque em que os primeiros recebimentos obtidos são emitidos primeiro. As saídas atualizadas financeiramente do estoque são liquidadas contra os primeiros recebimentos atualizados financeiramente no estoque, com base na data financeira da transação de estoque.
author: AndersGirke
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b9be0881a1f37d1478ea6302576aa5c348d94714
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574032"
---
# <a name="fifo-with-physical-value-and-marking"></a>PEPS com marcação e valor físico

[!include [banner](../includes/banner.md)]

Primeiro a entrar, Primeiro a sair (PEPS) é um modelo de estoque em que os primeiros recebimentos obtidos são emitidos primeiro. As saídas atualizadas financeiramente do estoque são liquidadas contra os primeiros recebimentos atualizados financeiramente no estoque, com base na data financeira da transação de estoque. 

Quando você usar PEPS, não precisará usar a regra de PEPS. Em vez disso, você poderá marcar transações de estoque de tal forma que o recebimento de um item específico seja liquidado em relação a uma saída específica. Recomendamos um fechamento de estoque periódico quando o modelo de estoque PEPS for usado. Os exemplos a seguir mostram o efeito de usar o PEPS nas três configurações:

-   PEPS sem a opção **Incluir valor físico**
-   PEPS com a opção **Incluir valor físico**
-   PEPS com marcação

## <a name="fifo-without-the-include-physical-value-option"></a>PEPS sem a opção Incluir valor físico
Neste exemplo, o grupo de modelo de item não está marcado para incluir o valor físico. A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 2 ao custo de BRL 10,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 2 ao custo de BRL 10,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 20,00 cada (média ponderada de transações atualizadas financeiramente).
-   5b. Saída financeira de estoque para uma quantidade de 1 a um preço de custo de BRL 15,00 cada (média ponderada de transações atualizadas financeiramente).
-   6. O fechamento de estoque é executado. Com base no método PEPS, a primeira saída atualizada financeiramente será liquidada no primeiro recebimento atualizado financeiramente. Um ajuste de BRL –5,00 será feito na transação de saída.

O novo preço de custo médio reflete a média de transações atualizadas financeiramente. As ilustrações a seguir mostram os efeitos do modelo de estoque PEPS nesta série de transações quando a opção **Incluir valor físico** não é usada. 

![FIFO sem Incluir Valor Físico.](./media/fifowithoutincludephysicalvalue.gif) 

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

## <a name="fifo-with-the-include-physical-value-option"></a>PEPS com a opção Incluir valor físico
Se a caixa de seleção **Incluir valor físico** for marcada para um item na página **Grupo de modelos do item**, o sistema usará as transações de recebimento físico e financeiro para calcular o preço de custo médio em execução. Quando aplicável, o sistema também fará ajustes para a transação de saída atualizada fisicamente. Quando a caixa de seleção **Incluir valor físico** estiver desmarcada, o fechamento de estoque com o modelo de estoque PEPS liquidará somente as transações atualizadas financeiramente. A ilustração a seguir mostra essas transações:

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
-   7. O fechamento de estoque é executado. Com base no método de PEPS, a primeira transação de saída financeira será ajustada ou liquidada no primeiro recebimento atualizado, seja este financeiro ou físico.

A transação 5b será liquidada na transação de recebimento 1b. Haverá um ajuste de BRL –11,25 para essa transação de saída. O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente, em BRL 27,50. A ilustração a seguir mostra os efeitos do modelo de estoque PEPS nesta série de transações quando a opção **Incluir valor físico** é usada. 

![FIFO com Incluir Valor Físico.](./media/fifowithincludephysicalvalue.gif) 

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

## <a name="fifo-with-marking"></a>PEPS com marcação
A marcação é um processo que permite vincular ou marcar uma transação de saída para uma transação de recebimento. A marcação pode ocorrer antes ou depois que a transação for lançada. É possível usar a marcação quando você desejar verificar o custo exato do estoque quando a transação é lançada ou quando o fechamento de estoque é executado. Por exemplo, o departamento de Atendimento ao Cliente aceitou uma ordem urgente de um cliente importante. Como esta é uma ordem urgente, você deverá pagar mais por esse item para atender às solicitações do cliente. É necessário garantir que o custo desse item de estoque seja refletido na margem ou no custo dos produtos vendidos (COGS) para essa fatura de ordem de venda. Quando a ordem de compra é lançada, o estoque é recebido ao custo de BRL 120,00. Se esse documento de ordem de vendas for marcado para a ordem de compra antes da guia de remessa ou a fatura ser lançada, o COGS será BRL 120,00, não o custo médio atual para o item. Se a guia de remessa de ordem de vendas ou a fatura for lançada antes que a marcação ocorra, os COGS serão lançados no preço de custo médio. Antes que fechamento de estoque seja executado, essas duas transações ainda podem ser marcadas uma para a outra. Quando uma transação de recebimento corresponde a uma transação de saída, o método de avaliação definido no grupo de modelos de estoque do item é desconsiderado e o sistema liquida essas transações entre si. É possível marcar uma transação de saída para um recebimento antes que a transação seja lançada. Você pode fazer isso em uma linha da ordem de venda na página **Detalhes da ordem de venda**. Você pode exibir as transações de recebimento abertas na página **Marcação**. É possível marcar uma transação de saída para um recebimento depois que a transação for lançada. Você pode corresponder ou marcar uma transação de saída para uma transação de recebimento aberta para um item inventariado de um diário de ajuste de estoque lançado. A ilustração a seguir mostra essas transações:

-   1a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   1b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 10,00 cada.
-   2a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   2b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 20,00 cada.
-   3a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 25,00 cada.
-   4a. Recebimento físico de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   4b. Recebimento financeiro de estoque para uma quantidade de 1 ao custo de BRL 30,00 cada.
-   5a. Saída física de estoque para uma quantidade de 1 a um preço de custo de BRL 21,25 cada (média de transações atualizadas financeiramente e fisicamente).
-   5b. A saída financeira do estoque para uma quantidade de 1 é marcada para o recebimento de estoque 2b antes da transação ser lançada. Essa transação é lançada a um preço de custo de BRL 20,00 cada.
-   6a. Saída física de estoque para uma quantidade de 1 ao preço de custo de BRL 21,25 cada.
-   7. O fechamento de estoque é executado. Como as transações PEPS atualizadas financeiramente são marcadas para um recebimento existente, essas transações são liquidadas uma para a outra e nenhum ajuste é feito.

O novo preço de custo médio reflete a média das transações atualizadas financeira e fisicamente, em BRL 27,50. A ilustração a seguir mostra os efeitos do modelo de estoque PEPS nesta série de transações quando a marcação entre saídas e recebimentos é usada. 

![FIFO com marcação.](./media/fifowithmarking.gif) 

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






[!INCLUDE[footer-include](../../includes/footer-banner.md)]