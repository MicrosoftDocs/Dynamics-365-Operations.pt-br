---
title: "Incluir valor físico"
description: "Você usa a caixa de seleção Incluir valor físico na Guia Rápida Modelo de estoque da página Grupos de modelos de item para especificar se as transações atualizadas fisicamente serão consideradas quando o preço de custo médio for calculado para um item."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79033
ms.assetid: 1928c145-bf82-436d-87ca-e7a173e31923
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 2d45e7a56851f3f4ac7a7d2d8c4ca9f23b6535fc
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="include-physical-value"></a>Incluir valor físico

[!include[banner](../includes/banner.md)]


Você usa a caixa de seleção Incluir valor físico na Guia Rápida Modelo de estoque da página Grupos de modelos de item para especificar se as transações atualizadas fisicamente serão consideradas quando o preço de custo médio for calculado para um item.

A caixa de seleção **Incluir valor físico** tem os valores a seguir.

| Valor    | Resultado                                                                                                                          |
|----------|---------------------------------------------------------------------------------------------------------------------------------|
| Selecionados | As transações atualizadas fisicamente como as atualizadas financeiramente são usadas para calcular o preço de custo médio corrente. |
| Desmarcado  | Somente as transações atualizadas financeiramente serão usadas para calcular o preço de custo médio corrente.                                     |

A caixa de seleção tem efeitos ligeiramente diferentes, dependendo do modelo de estoque usado.

-   Se você marcar a caixa de seleção **Incluir valor físico** ao usar o modelo de estoque FIFO, LIFO ou Data LIFO, o fechamento de estoque também ajustará as transações atualizadas fisicamente.
-   Se você não marcar a caixa de seleção **Incluir valor físico** ao usar esses modelos de estoque, o fechamento de estoque liquidará somente para transações atualizadas financeiramente.
-   Ao usar a média ponderada ou o modelo de estoque de data da média ponderada, o fechamento de estoque liquidará somente transações atualizadas financeiramente, independentemente de você marcar a caixa de seleção **Incluir valor físico**.

**Exemplo 1** Você marcou a caixa de seleção**Incluir valor físico** e recebe as seguintes ordens de compra:

-   Uma ordem de compra para uma quantidade 2 e um preço de custo de BRL 10,00 que foi atualizado na guia de remessa
-   Uma ordem de compra para uma quantidade 3 e um preço de custo de BRL 12,00 que foi atualizado na fatura

Nesse caso, o preço de custo médio corrente será BRL 11,20 porque tanto as transações atualizadas fisicamente como as atualizadas financeiramente são usadas para calcular o preço de custo. **Exemplo 2** Você não marcou a caixa de seleção **Incluir valor físico** e o preço de custo na configuração do item é BRL 10,00. Você recebe uma ordem de compra para uma quantidade 20 e um preço de custo de BRL 12,00 que foi atualizado na guia de remessa. Quando uma ordem de venda é lançada, o valor de custo lançado é de BRL 10,00, pois o preço de custo médio corrente não incluirá as transações lançadas fisicamente. **Observação:** para comparação, se você marcar a caixa de seleção **Incluir valor físico** para esse item, quando uma ordem de venda for lançada, o valor de custo lançado será BRL 12,00.




