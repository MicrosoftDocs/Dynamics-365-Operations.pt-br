---
title: Criar uma hierarquia de navegação de canal
description: Este tópico descreve como criar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 2e1462c10dfe1c858429e9f4cc5d720ca43df609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221320"
---
# <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="f9e0f-103">Criar uma hierarquia de navegação de canal</span><span class="sxs-lookup"><span data-stu-id="f9e0f-103">Create a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f9e0f-104">Este tópico descreve como criar uma hierarquia de navegação de canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-104">This topic describes how to create a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f9e0f-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="f9e0f-105">Overview</span></span>

<span data-ttu-id="f9e0f-106">Uma hierarquia de navegação de canal é usada para agrupar e organizar os produtos em categorias, de modo que eles possam ser procurados online ou em pontos de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="f9e0f-106">A channel navigation hierarchy is used to group and organize products into categories so that the products can be browsed online or in point of sale (POS).</span></span>

## <a name="create-a-channel-navigation-hierarchy"></a><span data-ttu-id="f9e0f-107">Criar uma hierarquia de navegação de canal</span><span class="sxs-lookup"><span data-stu-id="f9e0f-107">Create a channel navigation hierarchy</span></span>

<span data-ttu-id="f9e0f-108">Para criar uma hierarquia de navegação de canal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-108">To create a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="f9e0f-109">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Categorias de navegação de canal**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Channel navigation categories**.</span></span>
1. <span data-ttu-id="f9e0f-110">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f9e0f-111">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-111">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="f9e0f-112">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-112">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="f9e0f-113">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-113">Select **Create**.</span></span>
1. <span data-ttu-id="f9e0f-114">No painel de ação, selecione **Novo nó de categoria** para criar um nó raiz.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-114">On the action pane, select **New category node** to create a root node.</span></span>
1. <span data-ttu-id="f9e0f-115">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-115">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="f9e0f-116">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-116">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="f9e0f-117">Na caixa **Nome amigável**, insira um nome amigável.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-117">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="f9e0f-118">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f9e0f-119">A imagem a seguir mostra um exemplo de nó raiz.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-119">The following image shows a example root node.</span></span>

![Nó raiz de exemplo](media/create-channel-hierarchy-1.png)

## <a name="create-navigation-category-nodes"></a><span data-ttu-id="f9e0f-121">Criar nós de categoria de navegação</span><span class="sxs-lookup"><span data-stu-id="f9e0f-121">Create navigation category nodes</span></span>

<span data-ttu-id="f9e0f-122">Para criar outros nós de categoria de navegação para representar as categorias de produto no canal, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-122">To create any additional navigation category nodes to represent the product categories on the channel, follow these steps.</span></span>

1. <span data-ttu-id="f9e0f-123">No painel de navegação, selecione o nó pai ao qual adicionar uma categoria.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-123">In the navigation pane, select the parent node to add a category to.</span></span>
1. <span data-ttu-id="f9e0f-124">No painel de ação, selecione **Novo nó de categoria**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-124">On the action pane, select **New category node**.</span></span>
1. <span data-ttu-id="f9e0f-125">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-125">In the **Name** box, enter a name.</span></span>
1. <span data-ttu-id="f9e0f-126">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-126">In the **Description** box, enter a description.</span></span>
1. <span data-ttu-id="f9e0f-127">Na caixa **Nome amigável**, insira um nome amigável.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-127">In the **Friendly name** box, enter a friendly name.</span></span>
1. <span data-ttu-id="f9e0f-128">Na caixa **Ordem de exibição**, insira uma ordem de exibição (opcional).</span><span class="sxs-lookup"><span data-stu-id="f9e0f-128">In the **Display order** box, enter a display order (optional).</span></span>
1. <span data-ttu-id="f9e0f-129">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-129">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f9e0f-130">A imagem a seguir mostra um exemplo de hierarquia de navegação de canal concluída.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-130">The following image shows an example of a completed channel navigation hierarchy.</span></span>

![Hierarquia de canal de exemplo](media/create-channel-hierarchy-2.png)

## <a name="add-products-to-category-nodes"></a><span data-ttu-id="f9e0f-132">Adicionar produtos a nós de categoria</span><span class="sxs-lookup"><span data-stu-id="f9e0f-132">Add products to category nodes</span></span>

<span data-ttu-id="f9e0f-133">Para adicionar produtos a nós de categoria, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-133">To add products to category nodes, follow these steps.</span></span>

1. <span data-ttu-id="f9e0f-134">Selecione um nó de categoria.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-134">Select a category node.</span></span>
1. <span data-ttu-id="f9e0f-135">Em **Produtos**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-135">Under **Products**, select **Add**.</span></span>
1. <span data-ttu-id="f9e0f-136">Localize o(s) novo(s) produto(s) que você quer adicionar usando o número ou o nome do produto e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-136">Find the new product(s) you want to add using product number or product name, and then select **OK**.</span></span>
1. <span data-ttu-id="f9e0f-137">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-137">On the action pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="f9e0f-138">Adicionar produtos a um nó dentro da hierarquia de navegação de canal não é suficiente para os produtos serem mostrados no canal selecionado; eles também devem ser classificados para um produto.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-138">Adding products to a node inside the channel navigation hierarchy is not sufficient for the products to show up on a selected channel, the products must also be assorted to a product.</span></span>

<span data-ttu-id="f9e0f-139">A imagem a seguir mostra um exemplo de nó com produtos adicionados.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-139">The following image shows an example node with products added.</span></span>

![Produtos adicionados a um nó de categoria](media/create-channel-hierarchy-3.png)

## <a name="add-product-attribute-groups-to-category-nodes"></a><span data-ttu-id="f9e0f-141">Adicionar grupos de atributo de produto a nós de categoria</span><span class="sxs-lookup"><span data-stu-id="f9e0f-141">Add product attribute groups to category nodes</span></span>

> [!NOTE]
> <span data-ttu-id="f9e0f-142">Grupos de atributo devem ser criados para que você possa adicioná-los a um nó dentro da hierarquia de navegação de canal.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-142">Attribute groups must be created before you can add them to a node inside the channel navigation hierarchy.</span></span>

<span data-ttu-id="f9e0f-143">Para adicionar um grupo de atributos de produto a um nó de categoria, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-143">To add product an attribute group to a category node, follow these steps.</span></span>

1. <span data-ttu-id="f9e0f-144">Selecione um nó de categoria.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-144">Select a category node.</span></span>
1. <span data-ttu-id="f9e0f-145">Em **Grupo de atributos de produto**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-145">Under **Product attribute group**, select **Add**.</span></span>
1. <span data-ttu-id="f9e0f-146">Localize o(s) grupo(s) de atributos que você gostaria de adicionar e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-146">Find the attribute group(s) you would like to add, and then select **OK**.</span></span>
1. <span data-ttu-id="f9e0f-147">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-147">On the action pane, select **Save**.</span></span>

<span data-ttu-id="f9e0f-148">A imagem a seguir mostra um nó de exemplo com grupos de atributo de produto adicionados.</span><span class="sxs-lookup"><span data-stu-id="f9e0f-148">The following image shows a sample node with product attribute groups added.</span></span>

![Grupos de atributo de produto em um nó](media/create-channel-hierarchy-4.png)

## <a name="additional-resources"></a><span data-ttu-id="f9e0f-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f9e0f-150">Additional resources</span></span>

[<span data-ttu-id="f9e0f-151">Configurar classificações</span><span class="sxs-lookup"><span data-stu-id="f9e0f-151">Set up assortments</span></span>](set-up-assortments.md)

[<span data-ttu-id="f9e0f-152">Gerenciar atributos e grupos de atributos</span><span class="sxs-lookup"><span data-stu-id="f9e0f-152">Manage attributes and attribute groups</span></span>](attribute-attributegroups-lifecycle.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]