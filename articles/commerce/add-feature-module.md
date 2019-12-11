---
title: Módulo de recurso
description: Este tópico abrange os módulos de recurso e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785274"
---
# <a name="feature-module"></a><span data-ttu-id="0a06f-103">Módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="0a06f-103">Feature module</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="0a06f-104">Este tópico abrange os módulos de recurso e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0a06f-104">This topic covers feature modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0a06f-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="0a06f-105">Overview</span></span>

<span data-ttu-id="0a06f-106">Um módulo de recurso é usado para comercializar produtos ou promoções por meio de uma combinação de imagens e texto.</span><span class="sxs-lookup"><span data-stu-id="0a06f-106">A feature module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="0a06f-107">Por exemplo, um revendedor pode adicionar um módulo de recurso a uma página de detalhes do produto para destacar os recursos do produto.</span><span class="sxs-lookup"><span data-stu-id="0a06f-107">For example, a retailer can add a feature module to a product details page to highlight the features of the product.</span></span>

<span data-ttu-id="0a06f-108">Um módulo de recurso é direcionado por dados do sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="0a06f-108">A feature module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="0a06f-109">É um módulo autônomo que não depende de nenhum outro módulo na página.</span><span class="sxs-lookup"><span data-stu-id="0a06f-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="0a06f-110">Um módulo de recurso pode ser colocado em qualquer página do site em que um varejista queira comercializar ou promover algo (por exemplo, produtos, vendas ou recursos).</span><span class="sxs-lookup"><span data-stu-id="0a06f-110">A feature module can be put on any site page where a retailer wants to market or promote something (for example products, sales, or features).</span></span>

## <a name="examples-of-feature-modules-in-e-commerce"></a><span data-ttu-id="0a06f-111">Exemplos de módulos de recurso no comércio online</span><span class="sxs-lookup"><span data-stu-id="0a06f-111">Examples of feature modules in e-Commerce</span></span>

<span data-ttu-id="0a06f-112">Um módulo de recurso pode ser usado nas seguintes páginas:</span><span class="sxs-lookup"><span data-stu-id="0a06f-112">A feature module can used on the following pages:</span></span>

- <span data-ttu-id="0a06f-113">Uma página de detalhes do produto, para mostrar os recursos do produto</span><span class="sxs-lookup"><span data-stu-id="0a06f-113">A product details page, to showcase product features</span></span>
- <span data-ttu-id="0a06f-114">A home page, para promover produtos</span><span class="sxs-lookup"><span data-stu-id="0a06f-114">The home page, to promote products</span></span>
- <span data-ttu-id="0a06f-115">Uma página de categoria, para destacar uma categoria de produtos</span><span class="sxs-lookup"><span data-stu-id="0a06f-115">A category page, to highlight a category of products</span></span>

## <a name="feature-module-properties"></a><span data-ttu-id="0a06f-116">Propriedades do módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="0a06f-116">Feature module properties</span></span>

| <span data-ttu-id="0a06f-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="0a06f-117">Property name</span></span>     | <span data-ttu-id="0a06f-118">Valores</span><span class="sxs-lookup"><span data-stu-id="0a06f-118">Values</span></span> | <span data-ttu-id="0a06f-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="0a06f-119">Description</span></span> |
|-------------------|--------|-------------|
| <span data-ttu-id="0a06f-120">Imagem</span><span class="sxs-lookup"><span data-stu-id="0a06f-120">Image</span></span>             | <span data-ttu-id="0a06f-121">Arquivo de imagem</span><span class="sxs-lookup"><span data-stu-id="0a06f-121">Image file</span></span> | <span data-ttu-id="0a06f-122">Uma imagem pode ser usada para comercializar o produto ou promoção.</span><span class="sxs-lookup"><span data-stu-id="0a06f-122">An image can be used to market the product or promotion.</span></span> <span data-ttu-id="0a06f-123">Uma imagem pode ser carregada na galeria de imagens ou uma imagem existente pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="0a06f-123">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="0a06f-124">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="0a06f-124">Heading</span></span>           | <span data-ttu-id="0a06f-125">Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="0a06f-125">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="0a06f-126">Todo módulo de recurso pode ter um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0a06f-126">Every feature module can have a heading.</span></span> <span data-ttu-id="0a06f-127">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="0a06f-127">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="0a06f-128">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="0a06f-128">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="0a06f-129">Parágrafo</span><span class="sxs-lookup"><span data-stu-id="0a06f-129">Paragraph</span></span>         | <span data-ttu-id="0a06f-130">Texto de parágrafo</span><span class="sxs-lookup"><span data-stu-id="0a06f-130">Paragraph text</span></span> | <span data-ttu-id="0a06f-131">Os módulos de recurso é compatível com texto de parágrafo em formato rich text.</span><span class="sxs-lookup"><span data-stu-id="0a06f-131">Feature modules support paragraph text in rich text format.</span></span> <span data-ttu-id="0a06f-132">Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="0a06f-132">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="0a06f-133">Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo.</span><span class="sxs-lookup"><span data-stu-id="0a06f-133">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="0a06f-134">Vincular</span><span class="sxs-lookup"><span data-stu-id="0a06f-134">Link</span></span>              | <span data-ttu-id="0a06f-135">Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia**</span><span class="sxs-lookup"><span data-stu-id="0a06f-135">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="0a06f-136">Os módulos de recurso oferecem suporte a um ou mais links de "chamada à ação".</span><span class="sxs-lookup"><span data-stu-id="0a06f-136">Feature modules support one or more "call to action" links.</span></span> <span data-ttu-id="0a06f-137">Se um link for adicionado, será necessário o texto do link, um URL e uma etiqueta ARIA.</span><span class="sxs-lookup"><span data-stu-id="0a06f-137">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="0a06f-138">As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="0a06f-138">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="0a06f-139">Os links podem ser configurados para serem abertos em uma nova guia.</span><span class="sxs-lookup"><span data-stu-id="0a06f-139">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="0a06f-140">Posicionamento de Imagem</span><span class="sxs-lookup"><span data-stu-id="0a06f-140">Image placement</span></span>   | <span data-ttu-id="0a06f-141">**Direito**, **Esquerdo**, **Superior** ou **Inferior**</span><span class="sxs-lookup"><span data-stu-id="0a06f-141">**Right**, **Left**, **Top**, or **Bottom**</span></span> | <span data-ttu-id="0a06f-142">Esta propriedade define a posição da imagem em relação ao texto.</span><span class="sxs-lookup"><span data-stu-id="0a06f-142">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="0a06f-143">Por exemplo, se **Direito** estiver selecionado, a imagem aparecerá à direita do texto.</span><span class="sxs-lookup"><span data-stu-id="0a06f-143">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="0a06f-144">Tamanho da coluna de imagem</span><span class="sxs-lookup"><span data-stu-id="0a06f-144">Image column size</span></span> | <span data-ttu-id="0a06f-145">Um valor de **1** a **12**</span><span class="sxs-lookup"><span data-stu-id="0a06f-145">A value from **1** through **12**</span></span> | <span data-ttu-id="0a06f-146">Esta propriedade define o tamanho da imagem em relação ao texto.</span><span class="sxs-lookup"><span data-stu-id="0a06f-146">This property defines the size of the image relative to the text.</span></span> <span data-ttu-id="0a06f-147">O tamanho é expresso como um número de colunas na página.</span><span class="sxs-lookup"><span data-stu-id="0a06f-147">Size is expressed as a number of columns on the page.</span></span> <span data-ttu-id="0a06f-148">Existem 12 colunas em uma página.</span><span class="sxs-lookup"><span data-stu-id="0a06f-148">There are 12 columns on a page.</span></span> <span data-ttu-id="0a06f-149">Por padrão, a imagem e o texto têm o mesmo tamanho (seis colunas cada).</span><span class="sxs-lookup"><span data-stu-id="0a06f-149">By default, the image and text have equal size (six columns each).</span></span> <span data-ttu-id="0a06f-150">Contudo, o tamanho pode ser ajustado conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="0a06f-150">However, the size can be adjusted as required.</span></span> |

## <a name="add-a-feature-module-to-a-new-page"></a><span data-ttu-id="0a06f-151">Adicionar um módulo de recurso a uma nova página</span><span class="sxs-lookup"><span data-stu-id="0a06f-151">Add a feature module to a new page</span></span> 

<span data-ttu-id="0a06f-152">Para adicionar um módulo de recurso a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="0a06f-152">To add a feature module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="0a06f-153">Vá para **Modelos** e crie um modelo de página chamado **modelo de recurso**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-153">Go to **Templates**, and create a page template that is named **feature template**.</span></span>
1. <span data-ttu-id="0a06f-154">No slot **Principal** da página padrão, adicione um módulo de recurso.</span><span class="sxs-lookup"><span data-stu-id="0a06f-154">In the **Main** slot of the default page, add a feature module.</span></span>
1. <span data-ttu-id="0a06f-155">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="0a06f-155">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="0a06f-156">Use o modelo de recurso que criou para criar uma página nomeada **página do recurso**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-156">Use the feature template that you just created to create a page that is named **feature page**.</span></span>
1. <span data-ttu-id="0a06f-157">No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-157">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="0a06f-158">Na caixa de diálogo **Adicionar módulo**, em **Selecionar módulos**, selecione um módulo de recurso e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-158">In the **Add Module** dialog box, under **Select Modules**, select a feature module, and then select **OK**.</span></span>
1. <span data-ttu-id="0a06f-159">Na árvore de estrutura de tópicos à esquerda, selecione o módulo de recurso.</span><span class="sxs-lookup"><span data-stu-id="0a06f-159">In the outline tree on the left, select the feature module.</span></span>
1. <span data-ttu-id="0a06f-160">No painel de propriedades à direita, selecione **Adicionar uma imagem**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-160">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="0a06f-161">Em seguida, selecione uma imagem existente ou carregue uma nova imagem.</span><span class="sxs-lookup"><span data-stu-id="0a06f-161">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="0a06f-162">Selecione **Título**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-162">Select **Heading**.</span></span>
1. <span data-ttu-id="0a06f-163">Na caixa de diálogo **Título**, adicione o texto do cabeçalho, selecione o nível do cabeçalho e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-163">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="0a06f-164">Em **Rich Text**, adicione o texto como necessário.</span><span class="sxs-lookup"><span data-stu-id="0a06f-164">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="0a06f-165">Selecione **Adicionar link de ação**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-165">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="0a06f-166">Na caixa de diálogo **Action Link**, adicione o texto do link, uma URL do link e uma etiqueta ARIA para o link e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="0a06f-166">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="0a06f-167">Salve a página e visualize suas alterações.</span><span class="sxs-lookup"><span data-stu-id="0a06f-167">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="0a06f-168">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="0a06f-168">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0a06f-169">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0a06f-169">Additional resources</span></span>

[<span data-ttu-id="0a06f-170">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="0a06f-170">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="0a06f-171">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="0a06f-171">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="0a06f-172">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="0a06f-172">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="0a06f-173">Módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="0a06f-173">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="0a06f-174">Módulo de posicionamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="0a06f-174">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="0a06f-175">Módulo de hero</span><span class="sxs-lookup"><span data-stu-id="0a06f-175">Hero module</span></span>](add-hero-module.md)

[<span data-ttu-id="0a06f-176">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="0a06f-176">Video player module</span></span>](add-video-player.md)
