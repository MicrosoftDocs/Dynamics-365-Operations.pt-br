---
title: Módulo de bloco de conteúdo sofisticado
description: Este tópico abrange os módulos de bloco de conteúdo sofisticado e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785412"
---
# <a name="content-rich-block-module"></a><span data-ttu-id="28565-103">Módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="28565-103">Content rich block module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="28565-104">Este tópico abrange os módulos de bloco de conteúdo sofisticado e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="28565-104">This topic covers content rich block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="28565-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="28565-105">Overview</span></span>

<span data-ttu-id="28565-106">Um módulo de bloco de conteúdo sofisticado é um contêiner especial dentro do qual um ou mais itens de bloco de conteúdo sofisticado podem ser colocados.</span><span class="sxs-lookup"><span data-stu-id="28565-106">A content rich block module is a special container that one or more content rich block items can be put inside.</span></span> <span data-ttu-id="28565-107">Os módulos de bloco de conteúdo sofisticado são usados para o conteúdo de texto em uma página.</span><span class="sxs-lookup"><span data-stu-id="28565-107">Content rich block modules are used for textual content on a page.</span></span> <span data-ttu-id="28565-108">Esse conteúdo pode ser informativo ou promocional.</span><span class="sxs-lookup"><span data-stu-id="28565-108">This content can be either informational or promotional.</span></span>

<span data-ttu-id="28565-109">Os módulos de bloco de conteúdo sofisticado são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="28565-109">Content rich block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="28565-110">São módulos autônomos que não dependem do contexto da página ou de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="28565-110">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a><span data-ttu-id="28565-111">Exemplos de módulos de bloco de conteúdo sofisticado no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="28565-111">Examples of content rich block modules in e-Commerce</span></span>

<span data-ttu-id="28565-112">Os módulos de bloco de conteúdo sofisticado podem ser usados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="28565-112">Content rich block modules can be used in the following ways:</span></span>

* <span data-ttu-id="28565-113">Para exibir os recursos do produto em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="28565-113">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="28565-114">Para fins informativos em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="28565-114">For informational purposes on any page.</span></span> <span data-ttu-id="28565-115">Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".</span><span class="sxs-lookup"><span data-stu-id="28565-115">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="28565-116">Para adicionar mensagens personalizadas em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="28565-116">To add custom messages on a product details page.</span></span> <span data-ttu-id="28565-117">(por exemplo, "Frete grátis para pedidos acima de US$ 50").</span><span class="sxs-lookup"><span data-stu-id="28565-117">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="28565-118">Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").</span><span class="sxs-lookup"><span data-stu-id="28565-118">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

## <a name="content-rich-block-module-properties"></a><span data-ttu-id="28565-119">Propriedades do módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="28565-119">Content rich block module properties</span></span>

| <span data-ttu-id="28565-120">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="28565-120">Property name</span></span>     | <span data-ttu-id="28565-121">Alíquota</span><span class="sxs-lookup"><span data-stu-id="28565-121">Value</span></span>                                 | <span data-ttu-id="28565-122">Propriedade</span><span class="sxs-lookup"><span data-stu-id="28565-122">Property</span></span> |
|-------------------|---------------------------------------|----------|
| <span data-ttu-id="28565-123">Número de colunas</span><span class="sxs-lookup"><span data-stu-id="28565-123">Number of columns</span></span> | <span data-ttu-id="28565-124">Um número de **1** a **4**</span><span class="sxs-lookup"><span data-stu-id="28565-124">A number from **1** through **4**</span></span>     | <span data-ttu-id="28565-125">O número de colunas no bloco de conteúdo sofisticado.</span><span class="sxs-lookup"><span data-stu-id="28565-125">The number of columns in the content rich block.</span></span> <span data-ttu-id="28565-126">Pode haver até quatro colunas.</span><span class="sxs-lookup"><span data-stu-id="28565-126">There can be up to four columns.</span></span> |
| <span data-ttu-id="28565-127">Largura</span><span class="sxs-lookup"><span data-stu-id="28565-127">Width</span></span>             | <span data-ttu-id="28565-128">**Preencher contêiner** ou **Preencher tela**</span><span class="sxs-lookup"><span data-stu-id="28565-128">**Fill container** or **Fill screen**</span></span> | <span data-ttu-id="28565-129">Se o valor estiver definido como **Preencher contêiner**, os itens dentro do contêiner serão restritos à largura do contêiner.</span><span class="sxs-lookup"><span data-stu-id="28565-129">If the value is set to **Fill container**, the items inside the container are restricted to the width of the container.</span></span> <span data-ttu-id="28565-130">Se o valor estiver definido como **Preencher tela**, os itens não serão restritos à largura do contêiner, mas poderão entrar no modo de tela cheia.</span><span class="sxs-lookup"><span data-stu-id="28565-130">If the value is set to **Fill screen**, the items aren't restricted to the container width but can go into full-screen mode.</span></span> <span data-ttu-id="28565-131">É possível alterar o valor para obter o layout desejado.</span><span class="sxs-lookup"><span data-stu-id="28565-131">You can change the value to achieve the desired layout.</span></span> |

## <a name="content-rich-block-item-module-properties"></a><span data-ttu-id="28565-132">Propriedades do módulo do item de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="28565-132">Content rich block item module properties</span></span>

| <span data-ttu-id="28565-133">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="28565-133">Property name</span></span> | <span data-ttu-id="28565-134">Alíquota</span><span class="sxs-lookup"><span data-stu-id="28565-134">Value</span></span>          | <span data-ttu-id="28565-135">Descrição</span><span class="sxs-lookup"><span data-stu-id="28565-135">Description</span></span> |
|---------------|----------------|-------------|
| <span data-ttu-id="28565-136">Parágrafo</span><span class="sxs-lookup"><span data-stu-id="28565-136">Paragraph</span></span>     | <span data-ttu-id="28565-137">Texto de parágrafo</span><span class="sxs-lookup"><span data-stu-id="28565-137">Paragraph text</span></span> | <span data-ttu-id="28565-138">O texto que acompanha cada item de bloco de conteúdo sofisticado.</span><span class="sxs-lookup"><span data-stu-id="28565-138">The text that accompanies each content rich block item.</span></span> <span data-ttu-id="28565-139">Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico.</span><span class="sxs-lookup"><span data-stu-id="28565-139">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |

## <a name="add-a-content-rich-block-module-to-a-page"></a><span data-ttu-id="28565-140">Adicionar um módulo de bloco de conteúdo sofisticado a uma página</span><span class="sxs-lookup"><span data-stu-id="28565-140">Add a content rich block module to a page</span></span>

<span data-ttu-id="28565-141">Para adicionar um módulo de bloco de conteúdo sofisticado a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="28565-141">To add a content rich block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="28565-142">Criar um modelo da página chamado **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="28565-142">Create a page template that is named **Content template**.</span></span>
1. <span data-ttu-id="28565-143">No slot **Principal** da página padrão, adicione um módulo de bloco de conteúdo sofisticado.</span><span class="sxs-lookup"><span data-stu-id="28565-143">In the **Main** slot of the default page, add a content rich block module.</span></span>
1. <span data-ttu-id="28565-144">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="28565-144">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="28565-145">Use o modelo de conteúdo que criou para criar uma página nomeada **Página do conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="28565-145">Use the content template that you just created to create a page that is named **Content page**.</span></span>
1. <span data-ttu-id="28565-146">No slot **Principal** da nova página, adicione um módulo de bloco de conteúdo sofisticado.</span><span class="sxs-lookup"><span data-stu-id="28565-146">In the **Main** slot of the new page, add a content rich block module.</span></span>
1. <span data-ttu-id="28565-147">Nas propriedades do módulo de bloco de conteúdo sofisticado, defina o número de colunas como **2**.</span><span class="sxs-lookup"><span data-stu-id="28565-147">In the properties of the content rich block module, set number of columns to **2**.</span></span>
1. <span data-ttu-id="28565-148">No módulo de bloco de conteúdo sofisticado, selecione **Adicionar um módulo** e adicione um item de bloco de conteúdo sofisticado (por exemplo, **item1**).</span><span class="sxs-lookup"><span data-stu-id="28565-148">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item1**).</span></span>
1. <span data-ttu-id="28565-149">No novo item de bloco de conteúdo sofisticado, adicione o texto do parágrafo.</span><span class="sxs-lookup"><span data-stu-id="28565-149">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="28565-150">No módulo de bloco de conteúdo sofisticado, selecione **Adicionar um módulo** e adicione um item de bloco de conteúdo sofisticado (por exemplo, **item2**).</span><span class="sxs-lookup"><span data-stu-id="28565-150">In the content rich block module, select **Add a module**, and add a content rich block item (for example, **item2**).</span></span>
1. <span data-ttu-id="28565-151">No novo item de bloco de conteúdo sofisticado, adicione o texto do parágrafo.</span><span class="sxs-lookup"><span data-stu-id="28565-151">In the new content rich block item, add paragraph text.</span></span>
1. <span data-ttu-id="28565-152">Salve a página e visualize as alterações.</span><span class="sxs-lookup"><span data-stu-id="28565-152">Save the page, and preview the changes.</span></span> <span data-ttu-id="28565-153">Você verá dois blocos de rich text em uma exibição de duas colunas.</span><span class="sxs-lookup"><span data-stu-id="28565-153">You should see two rich text blocks in a two-column view.</span></span>
1. <span data-ttu-id="28565-154">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="28565-154">Check in the page, and publish it.</span></span>

> [!NOTE]
> <span data-ttu-id="28565-155">Se você adicionar um terceiro item de bloco de conteúdo sofisticado, ele será empilhado abaixo dos dois itens que você adicionou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="28565-155">If you add a third content rich block item, it will be stacked below the two items that you previously added.</span></span> <span data-ttu-id="28565-156">Alterando o número de colunas e itens no contêiner, você poderá obter layouts diferentes para o conteúdo textual.</span><span class="sxs-lookup"><span data-stu-id="28565-156">By changing the number of columns and items in the container, you can achieve different layouts for textual content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28565-157">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="28565-157">Additional resources</span></span>

[<span data-ttu-id="28565-158">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="28565-158">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="28565-159">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="28565-159">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="28565-160">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="28565-160">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="28565-161">Módulo de posicionamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="28565-161">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="28565-162">Módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="28565-162">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="28565-163">Módulo de hero</span><span class="sxs-lookup"><span data-stu-id="28565-163">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="28565-164">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="28565-164">Video player module</span></span>](add-video-player.md)

