---
title: Alterar a ordem de classificação das entidades de venda
description: Este tópico explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising no Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: b983cb5c63db171c76d34375a93a2b9086185d3a
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3021570"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Alterar a ordem de classificação das entidades de venda


[!include [banner](includes/banner.md)]

Os varejistas consideram a descoberta de produtos a principal ferramenta para a interação com os clientes em todos os canais. Várias funcionalidades podem ajudar os clientes a descobrir facilmente os produtos. Por exemplo, eles podem procurar categorias, pesquisar e filtrar.

Este tópico explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising. Também explica como alterar a ordem de classificação.

## <a name="overview"></a>Visão Geral

O suporte para classificação de várias entidades relacionadas a merchandising foi melhorado. Atualmente, esse suporte está melhor alinhado aos cenários de clientes existentes que antes requeriam extensões dos parceiros de implementação.

Nas versões do Retail anteriores à versão 10.0.5, a ordem de classificação das categorias na hierarquia de navegação era alfabética. A nova funcionalidade de ordem de classificação personalizada permite que os gerentes de merchandising configurem a ordem de classificação para várias entidades relacionadas a merchandising em todos os clientes usuários finais. Esses clientes incluem matriz e call centers.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Configurar a ordem de exibição para categorias na hierarquia de produtos

Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.

1. Vá para **Varejo e Comércio \> Produtos e categorias \> Hierarquia de produtos de comércio**.
2. Clique em **Editar hierarquia de categoria**.
3. Clique em **Editar**.
4. Na árvore, expanda **ALL (TUDO) \> Action Sports (Esportes de ação)**.
5. Na árvore, expanda **ALL (TUDO) \> Team Sports (Esportes de equipe)**.
6. No campo **Ordem de exibição**, insira um número. (O número pode ser negativo.)
7. Repita as etapas 4 a 6 para qualquer categoria adicional da qual você deseja alterar a ordem.

A ordem de exibição da hierarquia de navegação do canal será refletida no HQ para a hierarquia de produtos de comércio e produtos liberados por categoria.

![Hierarquia de produtos de classificação personalizada com valores negativos](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produtos liberados por categoria de classificação personalizada com base na hierarquia de produtos](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configurar a ordem de exibição das categorias na hierarquia de navegação do canal

Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.

1. Vá para **Varejo e Comércio \> Produtos e categorias \> Categorias de navegação de canal**.
2. Na lista, selecione a hierarquia **Navegação de moda**.
3. Clique em **Editar hierarquia de categoria**.
4. Clique em **Editar**.
5. Na árvore, selecione **Fashion (Moda) \> Womenswear (Roupa feminina) \> Womens Shoes (Sapatos femininos)**.
6. No campo **Ordem de exibição**, insira um número.
7. Na árvore, selecione **Fashion (Moda) \> Womenswear (Roupa feminina) \> Tops (Tops)**.

    Da mesma forma, é possível definir a ordem de classificação das subcategorias.

8. Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Casual Shirts (Camisas casuais)**.
9. No campo **Ordem de exibição**, insira um número.
10. Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Coats & Jackets (Casacos e jaquetas)**.
11. No campo **Ordem de exibição**, insira um número.
12. Repita isso para qualquer categoria adicional da qual você deseja alterar a ordem.

A ordem de exibição da hierarquia de navegação de canal é refletida no HQ, no catálogo e nos canais.

![Hierarquia de navegação do canal personalizada classificada](./media/ChannelNavCustomSorted.png)

![Hierarquia de navegação do catálogo personalizada classificada com base na hierarquia de navegação do canal](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV com categorias ordenadas personalizadas](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Por padrão, o recurso de ordem de classificação personalizada será desativado. Para saber como ativar esse recurso e outros, consulte [Gerenciamento de recursos](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).
