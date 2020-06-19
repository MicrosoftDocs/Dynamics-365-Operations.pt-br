---
title: Módulo de bloco de texto
description: Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 93ad09a05d188a30b099b9a44c35e15839be80a7
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411126"
---
# <a name="text-block-module"></a><span data-ttu-id="0e9e8-103">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="0e9e8-103">Text block module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0e9e8-104">Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0e9e8-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="0e9e8-105">Overview</span></span>

<span data-ttu-id="0e9e8-106">Um módulo de bloco de texto é um módulo usado para adicionar conteúdo textual.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-106">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="0e9e8-107">Esse conteúdo pode ser informativo ou promocional.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-107">This content can be informational or promotional.</span></span>

<span data-ttu-id="0e9e8-108">Os módulos de bloco de texto são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-108">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="0e9e8-109">São módulos autônomos que não dependem do contexto da página ou de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-109">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="0e9e8-110">Exemplos de módulos de bloco de texto no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="0e9e8-110">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="0e9e8-111">Os módulos de bloco de texto podem ser usados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="0e9e8-111">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="0e9e8-112">Para exibir os recursos do produto em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-112">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="0e9e8-113">Para fins informativos em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-113">For informational purposes on any page.</span></span> <span data-ttu-id="0e9e8-114">Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".</span><span class="sxs-lookup"><span data-stu-id="0e9e8-114">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="0e9e8-115">Para adicionar mensagens personalizadas em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-115">To add custom messages on a product details page.</span></span> <span data-ttu-id="0e9e8-116">(por exemplo, "Frete grátis para pedidos acima de US$ 50").</span><span class="sxs-lookup"><span data-stu-id="0e9e8-116">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="0e9e8-117">Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").</span><span class="sxs-lookup"><span data-stu-id="0e9e8-117">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="0e9e8-118">A imagem a seguir mostra um exemplo de um módulo de bloco de texto que é usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-118">The following image shows an example of a text block module that is used on a home page.</span></span>

![Exemplo de um módulo de bloco de texto](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="0e9e8-120">Propriedades do módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="0e9e8-120">Text block module properties</span></span>

| <span data-ttu-id="0e9e8-121">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="0e9e8-121">Property name</span></span>     | <span data-ttu-id="0e9e8-122">Alíquota</span><span class="sxs-lookup"><span data-stu-id="0e9e8-122">Value</span></span>                                            | <span data-ttu-id="0e9e8-123">descrição</span><span class="sxs-lookup"><span data-stu-id="0e9e8-123">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="0e9e8-124">Rich text</span><span class="sxs-lookup"><span data-stu-id="0e9e8-124">Rich text</span></span>         | <span data-ttu-id="0e9e8-125">Rich text</span><span class="sxs-lookup"><span data-stu-id="0e9e8-125">Rich text</span></span>                                        | <span data-ttu-id="0e9e8-126">Texto do parágrafo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-126">Paragraph text.</span></span> <span data-ttu-id="0e9e8-127">Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-127">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="0e9e8-128">Nome da classe personalizada</span><span class="sxs-lookup"><span data-stu-id="0e9e8-128">Custom class name</span></span> | <span data-ttu-id="0e9e8-129">Um nome de classe de folhas de estilo em cascata (CSS)</span><span class="sxs-lookup"><span data-stu-id="0e9e8-129">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="0e9e8-130">O nome de uma classe CSS personalizada que um desenvolvedor fornece para formatar esse módulo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-130">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="0e9e8-131">O nome da classe deve ser definido no pacote de tema.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-131">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="0e9e8-132">Tamanho da fonte</span><span class="sxs-lookup"><span data-stu-id="0e9e8-132">Font size</span></span>         | <span data-ttu-id="0e9e8-133">**Pequeno**, **Médio**, **Grande** ou **Extra-grande**</span><span class="sxs-lookup"><span data-stu-id="0e9e8-133">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="0e9e8-134">O tamanho da fonte do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-134">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="0e9e8-135">Adicionar um módulo de bloco de texto a uma página</span><span class="sxs-lookup"><span data-stu-id="0e9e8-135">Add a text block module to a page</span></span>

<span data-ttu-id="0e9e8-136">Para adicionar um módulo de bloco de texto a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-136">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="0e9e8-137">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-137">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="0e9e8-138">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira um **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-138">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="0e9e8-139">No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-139">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0e9e8-140">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-140">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="0e9e8-141">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-141">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="0e9e8-142">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-142">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="0e9e8-143">Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-143">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="0e9e8-144">Em **Nome da página**, insira **Página de conteúdo** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-144">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="0e9e8-145">No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-145">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0e9e8-146">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-146">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="0e9e8-147">No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-147">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="0e9e8-148">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-148">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0e9e8-149">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-149">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="0e9e8-150">No painel de propriedades do módulo de bloco de texto, adicione um texto ao campo **Texto rico**.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-150">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="0e9e8-151">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-151">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="0e9e8-152">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="0e9e8-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e9e8-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0e9e8-153">Additional resources</span></span>

[<span data-ttu-id="0e9e8-154">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="0e9e8-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0e9e8-155">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="0e9e8-155">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="0e9e8-156">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="0e9e8-156">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="0e9e8-157">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="0e9e8-157">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="0e9e8-158">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="0e9e8-158">Video player module</span></span>](add-video-player.md)

