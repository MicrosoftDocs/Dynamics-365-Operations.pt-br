---
title: Criar um novo produto no Commerce
description: Este tópico descreve como criar um novo produto no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: cb0137468d690649abb18b9d19673ff740d52e5d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207910"
---
# <a name="create-a-new-product-in-commerce"></a><span data-ttu-id="d2a84-103">Criar um novo produto no Commerce</span><span class="sxs-lookup"><span data-stu-id="d2a84-103">Create a new product in Commerce</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d2a84-104">Este tópico descreve como criar um novo produto no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d2a84-104">This topic describes how to create a new product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d2a84-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d2a84-105">Overview</span></span>

<span data-ttu-id="d2a84-106">Um produto é definido principalmente por um número de produto, nome e descrição.</span><span class="sxs-lookup"><span data-stu-id="d2a84-106">A product is primarily defined by a product number, name, and description.</span></span> <span data-ttu-id="d2a84-107">No entanto, outros dados também são necessários para descrever um produto ou serviço:</span><span class="sxs-lookup"><span data-stu-id="d2a84-107">However, other data is also required in order to describe a product or service:</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="d2a84-108">Criar um novo produto</span><span class="sxs-lookup"><span data-stu-id="d2a84-108">Create a new product</span></span>

1. <span data-ttu-id="d2a84-109">No painel de navegação, vá para **Módulos \> Varejo e comércio \> Produtos e categorias \> Produtos por categoria**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-109">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Products by category**.</span></span>
1. <span data-ttu-id="d2a84-110">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d2a84-111">Na lista suspensa **Tipo de produto**, selecione **Item** ou **Serviço**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-111">In the **Product type** drop-down list, select either **Item** or **Service**.</span></span>
1. <span data-ttu-id="d2a84-112">Na lista suspensa **Subtipo de produto**, selecione **Produto** (se o produto não tiver grades) ou **Produto mestre** (se o produto tiver grades).</span><span class="sxs-lookup"><span data-stu-id="d2a84-112">In the **Product subtype** drop-down list, select either **Product** (if the product will have no variants) or **Product master** (if the product will have variants).</span></span>
1. <span data-ttu-id="d2a84-113">Na caixa **Número do produto**, insira um número de produto se já não houver um preenchido previamente.</span><span class="sxs-lookup"><span data-stu-id="d2a84-113">In the **Product number** box, enter a product number if one is not already prepopulated.</span></span>
1. <span data-ttu-id="d2a84-114">Na caixa **Nome do produto**, insira um nome de produto.</span><span class="sxs-lookup"><span data-stu-id="d2a84-114">In the **Product name** box, enter a product name.</span></span>
1. <span data-ttu-id="d2a84-115">Na caixa **Nome da pesquisa**, insira um nome de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2a84-115">In the **Search name** box, enter a search name.</span></span>
1. <span data-ttu-id="d2a84-116">Na lista suspensa **Categoria de varejo**, selecione uma categoria apropriada.</span><span class="sxs-lookup"><span data-stu-id="d2a84-116">In the **Retail category** drop-down list, select an appropriate category.</span></span>
1. <span data-ttu-id="d2a84-117">Se o produto for um kit, selecione **Sim** para **Kit de produtos**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-117">If the product is a kit, select **Yes** for **Product kit**.</span></span>
1. <span data-ttu-id="d2a84-118">Se o subtipo de produto for produto mestre, defina o **Grupo de dimensões do produto** para incluir as grades com suporte.</span><span class="sxs-lookup"><span data-stu-id="d2a84-118">If the product subtype is product master, set the **Product dimension group** to include the supported variants.</span></span> <span data-ttu-id="d2a84-119">As opções incluem **Cor**, **Tamanho**, **Estilo** e **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-119">Options include **Color**, **Size**, **Style**, and **Configuration**.</span></span> <span data-ttu-id="d2a84-120">Pode ser necessário criar mais grupos de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="d2a84-120">You may need to create additional product dimension groups if needed.</span></span>
1. <span data-ttu-id="d2a84-121">Na lista suspensa **Tecnologia de configuração**, selecione uma opção apropriada.</span><span class="sxs-lookup"><span data-stu-id="d2a84-121">In the **Configuration technology** drop-down list, select an appropriate option.</span></span>
1. <span data-ttu-id="d2a84-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-122">Select **OK**.</span></span>

<span data-ttu-id="d2a84-123">A imagem a seguir mostra um exemplo de produto sendo adicionado.</span><span class="sxs-lookup"><span data-stu-id="d2a84-123">The following image shows an example product being added.</span></span>

![Criar um produto](media/create-new-product.png)

<span data-ttu-id="d2a84-125">Depois que um produto é adicionado, é possível definir outros dados para ele, como **Descrição do produto**, **Grupos de grades**, **Grupos de dimensões**, **Atributos de produto** e **Produtos relacionados**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-125">Once a product is added, additional data can be set for it, such as **Product description**, **Variant groups**, **Dimension groups**, **Product attributes**, and **Related products**.</span></span>

<span data-ttu-id="d2a84-126">A imagem a seguir mostra mais detalhes de um produto.</span><span class="sxs-lookup"><span data-stu-id="d2a84-126">The following image shows a product's additional details.</span></span>

![Detalhes do produto](media/create-new-product-2.png)

### <a name="create-product-variants"></a><span data-ttu-id="d2a84-128">Criar grades de produtos</span><span class="sxs-lookup"><span data-stu-id="d2a84-128">Create product variants</span></span>

<span data-ttu-id="d2a84-129">Se o subtipo de produto for **Produto mestre**, será necessário criar grades específicas.</span><span class="sxs-lookup"><span data-stu-id="d2a84-129">If the product subtype is **Product master**, specific variants will need to be created.</span></span> 

<span data-ttu-id="d2a84-130">Para criar grades de produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d2a84-130">To create product variants, follow these steps.</span></span>

1. <span data-ttu-id="d2a84-131">No painel de ação, selecione **Grades de produto**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-131">On the action pane, select **Product variants**.</span></span>
1. <span data-ttu-id="d2a84-132">Se grupos de grades tiverem sido selecionados no painel de ação, selecione \**Sugestões de grade*.</span><span class="sxs-lookup"><span data-stu-id="d2a84-132">If variant groups have been selected on the action pane, select \**Variant suggestions*.</span></span>
1. <span data-ttu-id="d2a84-133">Selecione as grades do produto às quais você gostaria de oferecer suporte.</span><span class="sxs-lookup"><span data-stu-id="d2a84-133">Select the variants you would like to support for the product.</span></span>
1. <span data-ttu-id="d2a84-134">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-134">Select **Create**.</span></span>

## <a name="release-a-product"></a><span data-ttu-id="d2a84-135">liberar produtos</span><span class="sxs-lookup"><span data-stu-id="d2a84-135">Release a product</span></span>

<span data-ttu-id="d2a84-136">Para vender um produto, primeiro ele deve ser liberado para uma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="d2a84-136">To sell a product it must first be released to a legal entity.</span></span>

1. <span data-ttu-id="d2a84-137">Na página do produto, selecione **Liberar produtos**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-137">From the product page, select **Release products**.</span></span>

    ![Liberar produto](media/create-new-product-3.png)

1. <span data-ttu-id="d2a84-139">Selecione o produto a ser liberado e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-139">Select the product to release, and then select **Next**.</span></span>

    ![Escolher o produto a ser liberado](media/create-new-product-4.png)

1. <span data-ttu-id="d2a84-141">Selecione o conjunto de grades de produto para liberação e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-141">Select the set of product variants to release, and then select **Next**.</span></span>

    ![Escolher as grades a serem liberadas](media/create-new-product-5.png)

1. <span data-ttu-id="d2a84-143">Selecione a entidade legal e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-143">Select the legal entity, and then select **Next**.</span></span>

    ![Escolher entidade legal](media/create-new-product-6.png)

1. <span data-ttu-id="d2a84-145">Selecione **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-145">Select **Finish**.</span></span>

    ![Concluir liberação de produto](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a><span data-ttu-id="d2a84-147">Configurar um produto liberado</span><span class="sxs-lookup"><span data-stu-id="d2a84-147">Configure a released product</span></span>

<span data-ttu-id="d2a84-148">Depois que um produto é liberado, ele precisa de mais configurações, entre elas adicionar um preço ao produto.</span><span class="sxs-lookup"><span data-stu-id="d2a84-148">Once a product is released, it will then require further configuration that includes adding a price to the product.</span></span>

1. <span data-ttu-id="d2a84-149">No painel de navegação, vá para **Módulos \> Varejo e Comércio \> Produtos e categorias \> Produtos lançados por categoria**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-149">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Released products by category**.</span></span>
1. <span data-ttu-id="d2a84-150">Selecione o nó de categoria de produto do produto que foi liberado e, depois, escolha o produto na lista de produtos.</span><span class="sxs-lookup"><span data-stu-id="d2a84-150">Select the product category node for the product that was released, and then select the product from the product list.</span></span>
1. <span data-ttu-id="d2a84-151">No painel de ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-151">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="d2a84-152">Na seção **Compra**, configure todas as propriedades necessárias, inclusive **Unidade**, **Preço** e **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-152">In the **Purchase** section, configure any required properties including **Unit**, **Price**,  and **Quantity**.</span></span>
1. <span data-ttu-id="d2a84-153">No painel de ação, selecione **Validar** para garantir que não haja erros de campos ausentes.</span><span class="sxs-lookup"><span data-stu-id="d2a84-153">On the action pane, select **Validate** to ensure that no errors are reported for missing fields.</span></span>
1. <span data-ttu-id="d2a84-154">No painel de ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d2a84-154">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d2a84-155">A imagem a seguir mostra um exemplo de configuração de produto liberado.</span><span class="sxs-lookup"><span data-stu-id="d2a84-155">The following image shows an example configuration for a released product.</span></span>

![Configurar produto liberado](media/create-new-product-8.png)

## <a name="additional-resources"></a><span data-ttu-id="d2a84-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d2a84-157">Additional resources</span></span>

[<span data-ttu-id="d2a84-158">Criar entidades legais</span><span class="sxs-lookup"><span data-stu-id="d2a84-158">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="d2a84-159">Criar um grupo de grades</span><span class="sxs-lookup"><span data-stu-id="d2a84-159">Create a variant group</span></span>](create-variant-group.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]