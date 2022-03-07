---
title: Rastrear o custo médio por dimensão de estoque
description: Um grupo de dimensões de estoque é anexado a cada item de estoque. Portanto, o preço de custo médio de um item é calculado com base nas dimensões de estoque selecionadas que estão sendo rastreadas financeiramente.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9ed1ced17eb25bdc10994b1e9e74c90a1d4ec95227bb1ddb072bae88e9255c0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6781077"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a>Rastrear o custo médio por dimensão de estoque

[!include [banner](../includes/banner.md)]

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





[!INCLUDE[footer-include](../../includes/footer-banner.md)]