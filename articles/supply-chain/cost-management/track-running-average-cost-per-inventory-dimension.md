---
title: "Rastreando o custo médio por dimensão de estoque"
description: "Um grupo de dimensões de estoque é anexado a cada item de estoque. Portanto, o preço de custo médio de um item é calculado com base nas dimensões de estoque selecionadas que estão sendo rastreadas financeiramente."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a88ec380810a9a2d7048d5a8773ebb5960e4cf86
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="tracking-running-average-cost-per-inventory-dimension"></a>Rastreando o custo médio por dimensão de estoque

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Um grupo de dimensões de estoque é anexado a cada item de estoque. Portanto, o preço de custo médio de um item é calculado com base nas dimensões de estoque selecionadas que estão sendo rastreadas financeiramente.

Há três tipos de dimensões de estoque: produto, armazenamento e rastreamento. As dimensões de produto incluem a configuração, o tamanho e a cor. As dimensões de produto sempre são rastreadas financeiramente. As dimensões de armazenamento e de rastreamento incluem o site, o depósito, a localização, o status de estoque, a placa de licença, o número do lote e o número de série. Você pode decidir quais dimensões de armazenamento e de rastreamento são rastreadas financeiramente. 

**Exemplo 1** 

Se o grupo de dimensões de armazenamento que for anexado ao item, for rastreado financeiramente por depósito, o preço de custo médio será calculado por depósito. Estas ordens de compra foram faturadas:

-   Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 10,00 foi faturada para o depósito GW.
-   Um ordem de compra para uma quantidade de 3 ao preço de custo de BRL 12,00 foi faturada para o depósito GW.
-   Uma ordem de compra para uma quantidade de 5 ao preço de custo de BRL 15,00 foi faturada para o depósito MW.

O preço de custo médio para o depósito GW é BRL 11.20, e o preço de custo médio para o depósito MW é BRL 15.00. Uma fatura de ordem de venda é lançada para o depósito GW. O valor do estoque e o custo dos produtos vendidos (antes do fechamento do estoque é executado sem marcação) será BRL 11,20. Outra ordem de venda é lançada para o depósito MW. O valor do estoque e o custo dos produtos vendidos (antes do fechamento do estoque é executado sem marcação) será BRL 15,00. 

**Exemplo 2** Se o grupo de dimensões de armazenamento que está associado ao item for rastreado financeiramente pelo depósito, e o grupo de dimensões de rastreamento for rastreado financeiramente por número de lote, o preço de custo médio será calculado para cada lote. 

**Observação:** Recomenda-se que você sempre exiba o preço de custo de todas as dimensões financeiras que estão sendo rastreadas. Estas ordens de compra foram faturadas:

-   Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 10,00 foi faturada para o depósito GW e o lote AAA.
-   Uma ordem de compra para uma quantidade de 3 ao preço de custo de BRL 12,00 foi faturada para o depósito GW e o lote AAA.
-   Uma ordem de compra para uma quantidade de 2 ao preço de custo de BRL 15,00 foi faturada para o depósito GW e o lote BBB.

O preço de custo médio para o depósito GW e lote AAA é BRL 11,20, e o preço de custo médio para o depósito GW e lote BBB é BRL 15,00.




