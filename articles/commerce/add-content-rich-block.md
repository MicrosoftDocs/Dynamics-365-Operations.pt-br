---
title: Módulo de bloco de texto
description: Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3926f23e4e762a49ef94ef0c8f3291e7e9a4a6a2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206382"
---
# <a name="text-block-module"></a><span data-ttu-id="dec20-103">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="dec20-103">Text block module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dec20-104">Este tópico abrange os módulos de bloco de texto e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dec20-104">This topic covers text block modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="dec20-105">Um módulo de bloco de texto é um módulo usado para adicionar conteúdo textual.</span><span class="sxs-lookup"><span data-stu-id="dec20-105">A text block module is a module that is used to add textual content.</span></span> <span data-ttu-id="dec20-106">Esse conteúdo pode ser informativo ou promocional.</span><span class="sxs-lookup"><span data-stu-id="dec20-106">This content can be informational or promotional.</span></span>

<span data-ttu-id="dec20-107">Os módulos de bloco de texto são direcionados por dados do sistema de gerenciamento de conteúdo (CMS) e podem ser colocados em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="dec20-107">Text block modules are driven by data from the content management system (CMS) and can be put on any page.</span></span> <span data-ttu-id="dec20-108">São módulos autônomos que não dependem do contexto da página ou de outros módulos.</span><span class="sxs-lookup"><span data-stu-id="dec20-108">They are stand-alone modules that don't depend on page context or any other modules.</span></span>

## <a name="examples-of-text-block-modules-in-e-commerce"></a><span data-ttu-id="dec20-109">Exemplos de módulos de bloco de texto no comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="dec20-109">Examples of text block modules in e-Commerce</span></span>

<span data-ttu-id="dec20-110">Os módulos de bloco de texto podem ser usados das seguintes formas:</span><span class="sxs-lookup"><span data-stu-id="dec20-110">Text block modules can be used in the following ways:</span></span>

* <span data-ttu-id="dec20-111">Para exibir os recursos do produto em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="dec20-111">To showcase product features on a product details page.</span></span>
* <span data-ttu-id="dec20-112">Para fins informativos em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="dec20-112">For informational purposes on any page.</span></span> <span data-ttu-id="dec20-113">Por exemplo, eles podem explicar os benefícios dos programas de fidelidade, descrever as políticas de remessa e devolução, responder a perguntas frequentes ou fornecer conteúdo "sobre nós".</span><span class="sxs-lookup"><span data-stu-id="dec20-113">For example, they can explain the benefits of loyalty programs, describe shipping and return policies, answer frequently asked questions, or provide "about us" content.</span></span>
* <span data-ttu-id="dec20-114">Para adicionar mensagens personalizadas em uma página de detalhes do produto.</span><span class="sxs-lookup"><span data-stu-id="dec20-114">To add custom messages on a product details page.</span></span> <span data-ttu-id="dec20-115">(por exemplo, "Frete grátis para pedidos acima de US$ 50").</span><span class="sxs-lookup"><span data-stu-id="dec20-115">(for example, "Free shipping for orders over $50").</span></span>
* <span data-ttu-id="dec20-116">Para avisos de isenção de responsabilidade e detalhes de contato nas páginas de detalhes do produto, páginas de carrinho, páginas de finalização de compra e outras páginas (por exemplo, "Remessas e devoluções estão sujeitas às políticas da loja").</span><span class="sxs-lookup"><span data-stu-id="dec20-116">For disclaimers and contact details on product details pages, cart pages, checkout pages, and other pages (for example, "Shipping and returns are subject to store policies").</span></span>

<span data-ttu-id="dec20-117">A imagem a seguir mostra um exemplo de um módulo de bloco de texto que é usado em uma home page.</span><span class="sxs-lookup"><span data-stu-id="dec20-117">The following image shows an example of a text block module that is used on a home page.</span></span>

![Exemplo de um módulo de bloco de texto](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a><span data-ttu-id="dec20-119">Propriedades do módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="dec20-119">Text block module properties</span></span>

| <span data-ttu-id="dec20-120">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="dec20-120">Property name</span></span>     | <span data-ttu-id="dec20-121">Alíquota</span><span class="sxs-lookup"><span data-stu-id="dec20-121">Value</span></span>                                            | <span data-ttu-id="dec20-122">descrição</span><span class="sxs-lookup"><span data-stu-id="dec20-122">Description</span></span> |
|-------------------|--------------------------------------------------|-------------|
| <span data-ttu-id="dec20-123">Rich text</span><span class="sxs-lookup"><span data-stu-id="dec20-123">Rich text</span></span>         | <span data-ttu-id="dec20-124">Rich text</span><span class="sxs-lookup"><span data-stu-id="dec20-124">Rich text</span></span>                                        | <span data-ttu-id="dec20-125">Texto do parágrafo.</span><span class="sxs-lookup"><span data-stu-id="dec20-125">Paragraph text.</span></span> <span data-ttu-id="dec20-126">Há suporte para alguns recursos básicos de rich text, como negrito, sublinhado e itálico.</span><span class="sxs-lookup"><span data-stu-id="dec20-126">Some basic rich text capabilities are supported, such as bold, underlined, and italic text.</span></span> |
| <span data-ttu-id="dec20-127">Nome da classe personalizada</span><span class="sxs-lookup"><span data-stu-id="dec20-127">Custom class name</span></span> | <span data-ttu-id="dec20-128">Um nome de classe de folhas de estilo em cascata (CSS)</span><span class="sxs-lookup"><span data-stu-id="dec20-128">A Cascading Style Sheets (CSS) class name</span></span>        | <span data-ttu-id="dec20-129">O nome de uma classe CSS personalizada que um desenvolvedor fornece para formatar esse módulo.</span><span class="sxs-lookup"><span data-stu-id="dec20-129">The name of a custom CSS class that a developer provides to format this module.</span></span> <span data-ttu-id="dec20-130">O nome da classe deve ser definido no pacote de tema.</span><span class="sxs-lookup"><span data-stu-id="dec20-130">The class name should be defined in the theme pack.</span></span> |
| <span data-ttu-id="dec20-131">Tamanho da fonte</span><span class="sxs-lookup"><span data-stu-id="dec20-131">Font size</span></span>         | <span data-ttu-id="dec20-132">**Pequeno**, **Médio**, **Grande** ou **Extra-grande**</span><span class="sxs-lookup"><span data-stu-id="dec20-132">**Small**, **Medium**, **Large**, or **X-Large**</span></span> | <span data-ttu-id="dec20-133">O tamanho da fonte do conteúdo.</span><span class="sxs-lookup"><span data-stu-id="dec20-133">The font size of the content.</span></span> |

## <a name="add-a-text-block-module-to-a-page"></a><span data-ttu-id="dec20-134">Adicionar um módulo de bloco de texto a uma página</span><span class="sxs-lookup"><span data-stu-id="dec20-134">Add a text block module to a page</span></span>

<span data-ttu-id="dec20-135">Para adicionar um módulo de bloco de texto a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="dec20-135">To add a text block module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="dec20-136">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="dec20-136">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="dec20-137">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira um **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="dec20-137">In the **New Template** dialog box, under **Template name**, enter **Content template**.</span></span>
1. <span data-ttu-id="dec20-138">No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="dec20-138">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dec20-139">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="dec20-139">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="dec20-140">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="dec20-140">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="dec20-141">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="dec20-141">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="dec20-142">Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="dec20-142">In the **Choose a template** dialog box, select **Content template**.</span></span> <span data-ttu-id="dec20-143">Em **Nome da página**, insira **Página de conteúdo** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="dec20-143">Under **Page name**, enter **Content page**, and then select **OK**.</span></span>
1. <span data-ttu-id="dec20-144">No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="dec20-144">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dec20-145">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="dec20-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="dec20-146">No painel de propriedades do módulo de contêiner, defina a propriedade **Largura** como **Preencher contêiner**.</span><span class="sxs-lookup"><span data-stu-id="dec20-146">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="dec20-147">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="dec20-147">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="dec20-148">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="dec20-148">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span> 
1. <span data-ttu-id="dec20-149">No painel de propriedades do módulo de bloco de texto, adicione um texto ao campo **Texto rico**.</span><span class="sxs-lookup"><span data-stu-id="dec20-149">In the property pane of the text block module, add text to the **Rich text** field.</span></span>
1. <span data-ttu-id="dec20-150">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="dec20-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="dec20-151">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="dec20-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dec20-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dec20-152">Additional resources</span></span>

[<span data-ttu-id="dec20-153">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="dec20-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="dec20-154">Módulo de banner de promoção</span><span class="sxs-lookup"><span data-stu-id="dec20-154">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="dec20-155">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="dec20-155">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="dec20-156">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="dec20-156">Content block module</span></span>](add-hero-module.md)

[<span data-ttu-id="dec20-157">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="dec20-157">Video player module</span></span>](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]