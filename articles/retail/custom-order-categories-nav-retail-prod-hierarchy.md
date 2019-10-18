---
title: Alterar a ordem de classificação das entidades de venda
description: Este tópico explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising no Dynamics 365 Retail.
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
ms.openlocfilehash: c159ff869d6c504fdebbef1fa68115a410c81d85
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019407"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="b744d-103">Alterar a ordem de classificação das entidades de venda</span><span class="sxs-lookup"><span data-stu-id="b744d-103">Change the sort order for merchandising entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="b744d-104">Os varejistas consideram a descoberta de produto uma ferramenta primária para a interação do cliente em todos os canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="b744d-104">Retailers consider product discovery a primary tool for customer interaction across all retail channels.</span></span> <span data-ttu-id="b744d-105">Várias funcionalidades podem ajudar os clientes a descobrir facilmente os produtos.</span><span class="sxs-lookup"><span data-stu-id="b744d-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="b744d-106">Por exemplo, eles podem procurar categorias, pesquisar e filtrar.</span><span class="sxs-lookup"><span data-stu-id="b744d-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="b744d-107">Este tópico explica os conceitos relacionados ao controle da ordem de exibição de várias entidades relacionadas a merchandising.</span><span class="sxs-lookup"><span data-stu-id="b744d-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="b744d-108">Também explica como alterar a ordem de classificação.</span><span class="sxs-lookup"><span data-stu-id="b744d-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="b744d-109">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b744d-109">Overview</span></span>

<span data-ttu-id="b744d-110">O suporte para classificação de várias entidades relacionadas a merchandising foi melhorado.</span><span class="sxs-lookup"><span data-stu-id="b744d-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="b744d-111">Atualmente, esse suporte está melhor alinhado aos cenários de clientes existentes que antes requeriam extensões dos parceiros de implementação.</span><span class="sxs-lookup"><span data-stu-id="b744d-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="b744d-112">Nas versões do Retail anteriores à versão 10.0.5, a ordem de classificação das categorias na hierarquia de navegação era alfabética.</span><span class="sxs-lookup"><span data-stu-id="b744d-112">In versions of Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="b744d-113">A nova funcionalidade de ordem de classificação personalizada permite que os gerentes de merchandising configurem a ordem de classificação para várias entidades relacionadas a merchandising em todos os clientes usuários finais.</span><span class="sxs-lookup"><span data-stu-id="b744d-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="b744d-114">Esses clientes incluem matriz e call centers.</span><span class="sxs-lookup"><span data-stu-id="b744d-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-retail-product-hierarchy"></a><span data-ttu-id="b744d-115">Configurar a ordem de exibição para categorias na hierarquia de produtos de varejo</span><span class="sxs-lookup"><span data-stu-id="b744d-115">Configure the display order for categories in the retail product hierarchy</span></span>

<span data-ttu-id="b744d-116">Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b744d-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="b744d-117">Vá para **Varejo \> Produtos e categorias \> Hierarquia de produtos de varejo**.</span><span class="sxs-lookup"><span data-stu-id="b744d-117">Go to **Retail \> Products and categories \> Retail product hierarchy**.</span></span>
2. <span data-ttu-id="b744d-118">Clique em **Editar hierarquia de categoria**.</span><span class="sxs-lookup"><span data-stu-id="b744d-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="b744d-119">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b744d-119">Click **Edit**.</span></span>
4. <span data-ttu-id="b744d-120">Na árvore, expanda **ALL (TUDO) \> Action Sports (Esportes de ação)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="b744d-121">Na árvore, expanda **ALL (TUDO) \> Team Sports (Esportes de equipe)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="b744d-122">No campo **Ordem de exibição**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b744d-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="b744d-123">(O número pode ser negativo.)</span><span class="sxs-lookup"><span data-stu-id="b744d-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="b744d-124">Repita as etapas 4 a 6 para qualquer categoria adicional da qual você deseja alterar a ordem.</span><span class="sxs-lookup"><span data-stu-id="b744d-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="b744d-125">A ordem de exibição da hierarquia de navegação do canal será refletida na matriz da hierarquia de produtos de varejo e produtos liberados por categoria.</span><span class="sxs-lookup"><span data-stu-id="b744d-125">The display order for the channel navigation hierarchy will be reflected in HQ for the retail product hierarchy and released products by category.</span></span>

![Hierarquia de produtos de varejo personalizados classificados com valores negativos](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Produtos liberados por categoria personalizada classificados com base na hierarquia de produtos de varejo](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="b744d-128">Configurar a ordem de exibição das categorias na hierarquia de navegação do canal</span><span class="sxs-lookup"><span data-stu-id="b744d-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="b744d-129">Antes de concluir esse procedimento, os dados de demonstração devem estar instalados no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b744d-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="b744d-130">Vá para **Varejo \> Produtos e categorias \> Categorias de navegação de canal**.</span><span class="sxs-lookup"><span data-stu-id="b744d-130">Go to **Retail \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="b744d-131">Na lista, selecione a hierarquia **Navegação de moda**.</span><span class="sxs-lookup"><span data-stu-id="b744d-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="b744d-132">Clique em **Editar hierarquia de categoria**.</span><span class="sxs-lookup"><span data-stu-id="b744d-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="b744d-133">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b744d-133">Click **Edit**.</span></span>
5. <span data-ttu-id="b744d-134">Na árvore, selecione **Fashion (Moda) \> Womenswear (Roupa feminina) \> Womens Shoes (Sapatos femininos)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="b744d-135">No campo **Ordem de exibição**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b744d-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="b744d-136">Na árvore, selecione **Fashion (Moda) \> Womenswear (Roupa feminina) \> Tops (Tops)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="b744d-137">Da mesma forma, é possível definir a ordem de classificação das subcategorias.</span><span class="sxs-lookup"><span data-stu-id="b744d-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="b744d-138">Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Casual Shirts (Camisas casuais)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="b744d-139">No campo **Ordem de exibição**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b744d-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="b744d-140">Na árvore, selecione **Fashion (Moda) \> Menswear (Roupa masculina) \> Coats & Jackets (Casacos e jaquetas)**.</span><span class="sxs-lookup"><span data-stu-id="b744d-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="b744d-141">No campo **Ordem de exibição**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b744d-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="b744d-142">Repita isso para qualquer categoria adicional da qual você deseja alterar a ordem.</span><span class="sxs-lookup"><span data-stu-id="b744d-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="b744d-143">A ordem de exibição da hierarquia de navegação do canal é refletida nos canais de matriz, catálogo e varejo.</span><span class="sxs-lookup"><span data-stu-id="b744d-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and retail channels.</span></span>

![Hierarquia de navegação do canal personalizada classificada](./media/ChannelNavCustomSorted.png)

![Hierarquia de navegação do catálogo personalizada classificada com base na hierarquia de navegação do canal](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV com categorias ordenadas personalizadas](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="b744d-147">Por padrão, o recurso de ordem de classificação personalizada será desativado.</span><span class="sxs-lookup"><span data-stu-id="b744d-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="b744d-148">Para saber como ativar esse recurso e outros, consulte [Gerenciamento de recursos](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="b744d-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>
