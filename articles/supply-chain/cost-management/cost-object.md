---
title: Objetos de custo
description: Este artigo fornece informações sobre os objetos de custos, e explica como os custos e quantidades serão acumulados. Um objeto de custo é uma entidade para os quais os custos e as quantidades são acumulados. Uma entidade de custo prevista do objeto pode ser um produto ou variantes de produto, como grades para o estilo e cor.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6829f24b8efa29b39f5ed742d8ca99e09bcef01
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910344"
---
# <a name="cost-objects"></a>Objetos de custo

[!include [banner](../includes/banner.md)]

Este artigo fornece informações sobre os objetos de custos, e explica como os custos e quantidades serão acumulados. Um objeto de custo é uma entidade para os quais os custos e as quantidades são acumulados. Uma entidade de custo prevista do objeto pode ser um produto ou variantes de produto, como grades para o estilo e cor.  

## <a name="cost-objects"></a>Objetos de custo

A página **Objetos de custo** lista todos os objetos de custo que foram registrados em um produto. Os objetos de custo são definidos pelos dados das seguintes origens:

-   Produto
-   Grupo de dimensões do produto
-   Grupo de dimensões de armazenamento
-   Grupo de dimensões de rastreamento

**Observação:** Um objeto de custo representa um elemento de custo apenas do tipo **Material direto**. Um objeto de custo e um objeto de estoque são diferentes na forma como um objeto de custo é definido pelas dimensões de estoque e selecionados para o estoque financeiro. Por exemplo, um item tem a seguinte configuração:

-   **Local:** Estoque físico = Sim, Estoque financeiro = Sim
-   **Depósito:** Estoque físico = Sim, Estoque financeiro = Não
-   **Nº do lote:** Estoque físico = Sim, Estoque financeiro = Não

A tabela a seguir mostra o que é um objeto de custo e o que é um objeto de estoque.

| Tipo de Objeto      | Nº do item | Local | Depósito | Nº do lote |
|------------------|-------------|------|-----------|-----------|
| Objeto de custo      | x           | x    |           |           |
| Objeto de estoque | x           | x    |  x        | x         |

## <a name="accumulation-of-costs-and-quantities"></a>Acúmulo de custos e quantidades
-   O valor no campo **Valor** é uma soma dos seguintes valores:
    -   Valor de custo físico
    -   Valor de custo financeiro
    -   Ajustes
-   O valor no campo **Quantidade** é uma soma dos seguintes valores:
    -   Recebido
    -   Deduzido
    -   Quantidade lançada
-   O campo **Custo unitário médio** é um campo calculado. O valor é calculado dividindo o valor **Valor** pelo valor **Quantidade**.

**Observação:** O parâmetro **Incluir valor físico** não tem efeito nos cálculos precedentes.

<a name="additional-resources"></a>Recursos adicionais
--------

[Grupo de dimensões do produto](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[Grupo de dimensões de armazenamento](/dynamicsax-2012//storage-dimension-groups-form)

[Grupo de dimensões de rastreamento](/dynamicsax-2012//tracking-dimension-groups-form)

[Novidades ou alterações](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[Entradas de custo](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]