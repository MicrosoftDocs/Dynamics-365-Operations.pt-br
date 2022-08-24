---
title: Alterar a ordem de classificação das entidades de venda
description: Este artigo explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising no Dynamics 365 Commerce.
author: josaw1
ms.date: 08/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: brshoo
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 80586597f4f60476b341e4cf1cfd90f3681e15c0
ms.sourcegitcommit: 52e31b1ef2b3ed8675de931d06090cd57e057fc2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9265827"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a>Alterar a ordem de classificação das entidades de venda


[!Include [banner](includes/banner.md)]

Os varejistas consideram a descoberta de produtos a principal ferramenta para a interação com os clientes em todos os canais. Há vários recursos que podem ajudar os clientes a descobrir produtos com facilidade. Por exemplo, os clientes podem procurar categorias, pesquisar e filtrar.

Este artigo explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising. Também explica como alterar a ordem de classificação.

## <a name="overview"></a>Visão geral

No Commerce, a classificação de várias entidades relacionadas ao merchadising é alinhada com os cenários de clientes existentes e não requer mais extensões de parceiros de implementação.

No Commerce versão 10.0.5 e anterior, a ordem de classificação de categorias na hierarquia de navegação era alfabética. A funcionalidade de ordem de classificação personalizada atual permite que os gerentes de merchandising configurem a ordem de classificação para várias entidades relacionadas a merchandising em todos os clientes usuários finais. Esses clientes incluem o headquarters (HQ) e os call centers.

## <a name="configure-the-display-order-for-categories-in-the-product-hierarchy"></a>Configurar a ordem de exibição para categorias na hierarquia de produtos

Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.

1. Acesse **Varejo e Comércio \> Produtos e categorias \> Hierarquia de produtos de comércio**.
2. Clique em **Editar hierarquia de categoria**.
3. Clique em **Editar**.
4. Na árvore, expanda **ALL (TUDO) \> Action Sports (Esportes de ação)**.
5. Na árvore, expanda **ALL (TUDO) \> Team Sports (Esportes de equipe)**.
6. No campo **Ordem de exibição**, insira um número. (O número pode ser negativo.)
7. Repita as etapas 4 a 6 para qualquer categoria adicional da qual você deseja alterar a ordem.

A ordem de exibição da hierarquia de navegação do canal será refletida no HQ para a hierarquia de produtos de comércio e produtos liberados por categoria.

![Hierarquia de produtos de classificação personalizada com valores negativos.](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produtos liberados por categoria de classificação personalizada com base na hierarquia de produtos.](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a>Configurar a ordem de exibição das categorias na hierarquia de navegação do canal

Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.

1. Acesse **Varejo e Comércio \> Produtos e categorias \> Categorias de navegação de canal**.
2. Na lista, selecione a hierarquia **Navegação de moda**.
3. Clique em **Editar hierarquia de categoria**.
4. Clique em **Editar**.
5. Na árvore, selecione **Moda \> Roupa feminina \> Sapatos femininos**.
6. No campo **Ordem de exibição**, insira um número.
7. Na árvore, selecione **Fashion (Moda) \> Womenswear (Roupa feminina) \> Tops (Tops)**.

Da mesma forma, é possível definir a ordem de classificação das subcategorias.

8. Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Casual Shirts (Camisas casuais)**.
9. No campo **Ordem de exibição**, insira um número.
10. Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Coats & Jackets (Casacos e jaquetas)**.
11. No campo **Ordem de exibição**, insira um número.
12. Repita isso para qualquer categoria adicional da qual você deseja alterar a ordem.

A ordem de exibição da hierarquia de navegação de canal é refletida no HQ, no catálogo e nos canais.

![Hierarquia de navegação do canal personalizada classificada.](./media/ChannelNavCustomSorted.png)

![Hierarquia de navegação do catálogo personalizada classificada com base na hierarquia de navegação do canal.](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV com categorias ordenadas personalizadas.](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> Por padrão, o recurso **Habilitar ordem de exibição para entidades de merchandising** está desativado. Use o [Gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativá-lo. Após ativar o recurso, execute o trabalho CDX **Configuração global -1110** da agenda de distribuição.
> Se as categorias solicitadas no PDV não forem atualizadas, reative o dispositivo. As informações sobre a categoria são buscadas quando ocorre a ativação do dispositivo, de forma que o dispositivo talvez precise buscar novamente as informações de categoria com ordens de exibição atualizadas. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
