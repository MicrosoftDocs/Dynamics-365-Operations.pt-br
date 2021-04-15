---
title: Criar uma nova hierarquia de produtos
description: Este tópico descreve como criar uma nova hierarquia de produtos no Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8aef33a501f43105730eaa21a9159eb1398a1b36
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799556"
---
# <a name="create-a-new-product-hierarchy"></a><span data-ttu-id="5f8b4-103">Criar uma nova hierarquia de produtos</span><span class="sxs-lookup"><span data-stu-id="5f8b4-103">Create a new product hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5f8b4-104">Este tópico descreve como criar uma nova hierarquia de produtos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-104">This topic describes how to create a new product hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5f8b4-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="5f8b4-105">Overview</span></span>

<span data-ttu-id="5f8b4-106">O Dynamics 365 Commerce oferece suporte a vários canais de varejo.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-106">Dynamics 365 Commerce supports multiple retail channels.</span></span> <span data-ttu-id="5f8b4-107">Esses canais de varejo incluem lojas online, call centers e lojas de varejo (também chamadas de lojas tradicionais).</span><span class="sxs-lookup"><span data-stu-id="5f8b4-107">These retail channels include online stores, call centers, and retail stores (also known as brick-and-mortar stores).</span></span> <span data-ttu-id="5f8b4-108">Cada canal de loja de varejo pode ter seus próprios métodos de pagamento, grupos de preços, terminais de pontos de venda (PDV), contas de receita e despesa e equipe.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-108">Each retail store channel can have its own payment methods, price groups, point of sale (POS) registers, income accounts and expense accounts, and staff.</span></span> <span data-ttu-id="5f8b4-109">Você deve configurar todos esses elementos para poder criar um canal de loja de varejo.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-109">You must set up all of these elements before you can create a retail store channel.</span></span> 

<span data-ttu-id="5f8b4-110">Uma hierarquia de produtos de Comércio é usada para definir a hierarquia de produtos geral da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-110">A Commerce product hierarchy is used to define the overall product hierarchy for your organization.</span></span> <span data-ttu-id="5f8b4-111">Você pode usar uma hierarquia de produtos de Comércio para comercialização, preços e promoções, relatórios e planejamento de classificação.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-111">You can use a Commerce product hierarchy for merchandising, pricing and promotions, reporting, and assortment planning.</span></span> <span data-ttu-id="5f8b4-112">Apenas uma hierarquia de produtos de Comércio pode ser atribuída por organização.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-112">Only one Commerce product hierarchy can be assigned per organization.</span></span>

## <a name="create-and-configure-a-product-hierarchy"></a><span data-ttu-id="5f8b4-113">Criar e configurar uma hierarquia de produtos</span><span class="sxs-lookup"><span data-stu-id="5f8b4-113">Create and configure a product hierarchy</span></span>

<span data-ttu-id="5f8b4-114">Para criar e configurar uma hierarquia de produtos de Comércio, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-114">To create and configure a Commerce product hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="5f8b4-115">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Hierarquia de produtos de comércio**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-115">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Commerce product hierarchy**.</span></span>
1. <span data-ttu-id="5f8b4-116">Se ainda não existir uma hierarquia, no **Painel de ação**, selecione **Novo** para criar a raiz da hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-116">If no hierachy exists yet, on the **Action pane**, select **New** to create the root of the hierarchy.</span></span>
1. <span data-ttu-id="5f8b4-117">Em **Geral**:</span><span class="sxs-lookup"><span data-stu-id="5f8b4-117">Under **General**:</span></span>
    1. <span data-ttu-id="5f8b4-118">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-118">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="5f8b4-119">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-119">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="5f8b4-120">Na caixa **Nome amigável**, insira um nome amigável.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-120">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="5f8b4-121">Defina **Ativo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-121">Set **Active** to **Yes**.</span></span>

## <a name="add-hierarchy-nodes"></a><span data-ttu-id="5f8b4-122">Adicionar nós de hierarquia</span><span class="sxs-lookup"><span data-stu-id="5f8b4-122">Add hierarchy nodes</span></span>

<span data-ttu-id="5f8b4-123">Para adicionar nós de hierarquia, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-123">To add hierarchy nodes, follow these steps.</span></span>

1. <span data-ttu-id="5f8b4-124">No painel de ação, selecione **Editar hierarquia de categoria**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-124">On the action pane, select **Edit category hierarchy**.</span></span>
1. <span data-ttu-id="5f8b4-125">Selecione o nó pai ao qual você deseja adicionar um novo nó e clique em **Novo nó de categoria**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-125">Select the parent node you want to add a new node to, and then select **New category node**.</span></span>
1. <span data-ttu-id="5f8b4-126">Na seção **Geral**, forneça **Nome**, **Descrição**, **Nome amigável** e **Palavras-chave**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-126">In the **General** section provide a **Name**, **Description**, **Friendly name** and **Keywords**.</span></span>
1. <span data-ttu-id="5f8b4-127">Em **Geral**:</span><span class="sxs-lookup"><span data-stu-id="5f8b4-127">Under **General**:</span></span>
    1. <span data-ttu-id="5f8b4-128">Na caixa **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-128">In the **Name** box, enter a name.</span></span>
    1. <span data-ttu-id="5f8b4-129">Na caixa **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-129">In the **Description** box, enter a description.</span></span>
    1. <span data-ttu-id="5f8b4-130">Na caixa **Nome amigável**, insira um nome amigável.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-130">In the **Friendly name** box, enter a friendly name.</span></span>
    1. <span data-ttu-id="5f8b4-131">Na caixa **Palavras-chave**, insira palavras-chave relevantes.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-131">In the **Keywords** box, enter relevant keywords.</span></span>
    1. <span data-ttu-id="5f8b4-132">Na caixa **Ordem de exibição**, insira um número para a ordem de exibição (opcional).</span><span class="sxs-lookup"><span data-stu-id="5f8b4-132">In the **Display order** box, enter a number for the display order (optional).</span></span>
1. <span data-ttu-id="5f8b4-133">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-133">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="5f8b4-134">Repita as etapas acima para adicionar mais nós.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-134">Repeat the steps above to add additional nodes.</span></span>

<span data-ttu-id="5f8b4-135">A imagem a seguir mostra a criação de um novo nó de hierarquia de produtos.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-135">The following image shows the creation of a new product hierarchy node.</span></span>

![Criar hierarquia de produtos](media/create-product-hierarchy.png)

## <a name="other-settings"></a><span data-ttu-id="5f8b4-137">Outras configurações</span><span class="sxs-lookup"><span data-stu-id="5f8b4-137">Other settings</span></span>

<span data-ttu-id="5f8b4-138">Grupos de atributos de categoria também podem ser atribuídos a cada grupo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="5f8b4-138">Category attribute groups can also be assigned to each group as required.</span></span>  

## <a name="additional-resources"></a><span data-ttu-id="5f8b4-139">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5f8b4-139">Additional resources</span></span>

[<span data-ttu-id="5f8b4-140">hierarquias do Commerce</span><span class="sxs-lookup"><span data-stu-id="5f8b4-140">commerce hierarchies</span></span>](retail-hierarchies.md)

[<span data-ttu-id="5f8b4-141">Gerenciar produtos e categorias de produtos </span><span class="sxs-lookup"><span data-stu-id="5f8b4-141">Manage product categories and products </span></span>](category-management-product-creation.md)

[<span data-ttu-id="5f8b4-142">Alterar a ordem de classificação das entidades de comercialização</span><span class="sxs-lookup"><span data-stu-id="5f8b4-142">Change the sort order for merchandizing entities</span></span>](custom-order-categories-nav-retail-prod-hierarchy.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]