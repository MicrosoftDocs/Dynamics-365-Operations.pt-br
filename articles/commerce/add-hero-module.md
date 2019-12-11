---
title: Módulo de hero
description: Este tópico abrange os módulos de hero e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785372"
---
# <a name="hero-module"></a><span data-ttu-id="a14b0-103">Módulo de hero</span><span class="sxs-lookup"><span data-stu-id="a14b0-103">Hero module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a14b0-104">Este tópico abrange os módulos de hero e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a14b0-104">This topic covers hero modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a14b0-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="a14b0-105">Overview</span></span>

<span data-ttu-id="a14b0-106">Um módulo de hero é usado para comercializar produtos ou promoções por meio de uma combinação de imagens e texto.</span><span class="sxs-lookup"><span data-stu-id="a14b0-106">A hero module is used to market products or promotions through a combination of images and text.</span></span> <span data-ttu-id="a14b0-107">Por exemplo, um varejista pode adicionar um módulo de hero à home page de um site de comércio eletrônico para promover um novo produto e atrair a atenção dos clientes.</span><span class="sxs-lookup"><span data-stu-id="a14b0-107">For example, a retailer can add a hero module to the home page of an e-Commerce site to promote a new product and attract the attention of customers.</span></span>

<span data-ttu-id="a14b0-108">Um módulo de hero é direcionado por dados do sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="a14b0-108">A hero module is driven by data from the content management system (CMS).</span></span> <span data-ttu-id="a14b0-109">É um módulo autônomo que não depende de nenhum outro módulo na página.</span><span class="sxs-lookup"><span data-stu-id="a14b0-109">It's a stand-alone module that doesn't depend on any other modules on the page.</span></span> <span data-ttu-id="a14b0-110">Um módulo de hero pode ser colocado em qualquer página do site em que um varejista queira comercializar ou promover algo (por exemplo, produtos, vendas ou recursos).</span><span class="sxs-lookup"><span data-stu-id="a14b0-110">A hero module can be put on any site page where a retailer wants to market or promote something (for example, products, sales, or features).</span></span>

## <a name="examples-of-hero-module-in-e-commerce"></a><span data-ttu-id="a14b0-111">Exemplos de módulo de hero no comércio online</span><span class="sxs-lookup"><span data-stu-id="a14b0-111">Examples of hero module in e-Commerce</span></span>

- <span data-ttu-id="a14b0-112">Um módulo de hero pode ser usado na home page de um site de comércio eletrônico para destacar promoções e novos produtos.</span><span class="sxs-lookup"><span data-stu-id="a14b0-112">A hero module can be used on the home page of an e-Commerce site to highlight promotions and new products.</span></span>
- <span data-ttu-id="a14b0-113">Um módulo de hero pode ser usado em uma página de detalhes do produto para mostrar informações do produto.</span><span class="sxs-lookup"><span data-stu-id="a14b0-113">A hero module can be used on a product details page to showcase product information.</span></span>
- <span data-ttu-id="a14b0-114">Vários módulos de hero podem ser colocados dentro de um módulo de carrossel para destacar vários produtos ou promoções.</span><span class="sxs-lookup"><span data-stu-id="a14b0-114">Multiple hero modules can be put inside a carousel module to highlight multiple products or promotions.</span></span>

## <a name="hero-module-properties"></a><span data-ttu-id="a14b0-115">Propriedades de módulo de hero</span><span class="sxs-lookup"><span data-stu-id="a14b0-115">Hero module properties</span></span>

| <span data-ttu-id="a14b0-116">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="a14b0-116">Property name</span></span>  | <span data-ttu-id="a14b0-117">Valores</span><span class="sxs-lookup"><span data-stu-id="a14b0-117">Values</span></span> | <span data-ttu-id="a14b0-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="a14b0-118">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="a14b0-119">Imagem</span><span class="sxs-lookup"><span data-stu-id="a14b0-119">Image</span></span>          | <span data-ttu-id="a14b0-120">Arquivo de imagem</span><span class="sxs-lookup"><span data-stu-id="a14b0-120">Image file</span></span> | <span data-ttu-id="a14b0-121">Uma imagem pode ser usada para mostrar um produto ou uma promoção.</span><span class="sxs-lookup"><span data-stu-id="a14b0-121">An image can be used to showcase a product or a promotion.</span></span> <span data-ttu-id="a14b0-122">Uma imagem pode ser carregada na galeria de imagens ou uma imagem existente pode ser usada.</span><span class="sxs-lookup"><span data-stu-id="a14b0-122">An image can be uploaded to the image gallery, or an existing image can be used.</span></span> |
| <span data-ttu-id="a14b0-123">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="a14b0-123">Heading</span></span>        | <span data-ttu-id="a14b0-124">Texto do cabeçalho e tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**)</span><span class="sxs-lookup"><span data-stu-id="a14b0-124">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="a14b0-125">Todo módulo de hero pode ter um cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a14b0-125">Every hero module can have a heading.</span></span> <span data-ttu-id="a14b0-126">Por padrão, a tag de cabeçalho **H2** é usada para o cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="a14b0-126">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="a14b0-127">No entanto, a tag pode ser alterada para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="a14b0-127">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="a14b0-128">Parágrafo</span><span class="sxs-lookup"><span data-stu-id="a14b0-128">Paragraph</span></span>      | <span data-ttu-id="a14b0-129">Texto de parágrafo</span><span class="sxs-lookup"><span data-stu-id="a14b0-129">Paragraph text</span></span> | <span data-ttu-id="a14b0-130">Os módulos de hero é compatível com texto de parágrafo em formato rich text.</span><span class="sxs-lookup"><span data-stu-id="a14b0-130">Hero modules support paragraph text in rich text format.</span></span> <span data-ttu-id="a14b0-131">Alguns recursos básicos de rich text são compatíveis, como negrito, sublinhado, itálico e hiperlinks.</span><span class="sxs-lookup"><span data-stu-id="a14b0-131">Some basic rich text capabilities are supported, such as bold, underlined, and italic text, and hyperlinks.</span></span> <span data-ttu-id="a14b0-132">Alguns desses recursos podem ser substituídos pelo tema da página aplicado ao módulo.</span><span class="sxs-lookup"><span data-stu-id="a14b0-132">Some of these capabilities can be overridden by the page theme that is applied to the module.</span></span> |
| <span data-ttu-id="a14b0-133">Vincular</span><span class="sxs-lookup"><span data-stu-id="a14b0-133">Link</span></span>           | <span data-ttu-id="a14b0-134">Texto do link, URL do link, etiqueta ARIA (Accessible Rich Internet Applications) e **Abrir link em uma nova guia**</span><span class="sxs-lookup"><span data-stu-id="a14b0-134">Link text, link URL, Accessible Rich Internet Applications (ARIA) label, and **Open link in new tab**</span></span> | <span data-ttu-id="a14b0-135">Os módulos de hero oferecem suporte a um ou mais links de "chamada à ação".</span><span class="sxs-lookup"><span data-stu-id="a14b0-135">Hero modules support one or more "call to action" links.</span></span> <span data-ttu-id="a14b0-136">Se um link for adicionado, será necessário o texto do link, um URL e uma etiqueta ARIA.</span><span class="sxs-lookup"><span data-stu-id="a14b0-136">If a link is added, link text, a URL, and an ARIA label are required.</span></span> <span data-ttu-id="a14b0-137">As etiquetas ARIA devem ser descritivas para atender aos requisitos de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="a14b0-137">ARIA labels should be descriptive to meet accessibility requirements.</span></span> <span data-ttu-id="a14b0-138">Os links podem ser configurados para serem abertos em uma nova guia.</span><span class="sxs-lookup"><span data-stu-id="a14b0-138">Links can be configured so that they are opened on a new tab.</span></span> |
| <span data-ttu-id="a14b0-139">Posicionamento do texto</span><span class="sxs-lookup"><span data-stu-id="a14b0-139">Text placement</span></span> | <span data-ttu-id="a14b0-140">**Esquerdo superior**, **Direito superior**, **Superior central**, **Esquerdo inferior**, **Direito inferior**, **Centro inferior**, **Centro esquerdo**, **Centro direito** ou **Centro central**</span><span class="sxs-lookup"><span data-stu-id="a14b0-140">**Top Left**, **Top Right**, **Top Center**, **Bottom Left**, **Bottom Right**, **Bottom Center**, **Center Left**, **Center Right**, or **Center Center**</span></span> | <span data-ttu-id="a14b0-141">Esta propriedade define a posição da imagem em relação ao texto.</span><span class="sxs-lookup"><span data-stu-id="a14b0-141">This property defines the position of the image relative to the text.</span></span> <span data-ttu-id="a14b0-142">Por exemplo, se **Direito** estiver selecionado, a imagem aparecerá à direita do texto.</span><span class="sxs-lookup"><span data-stu-id="a14b0-142">For example, if **Right** is selected, the image appears to the right of the text.</span></span> |
| <span data-ttu-id="a14b0-143">Tema de texto</span><span class="sxs-lookup"><span data-stu-id="a14b0-143">Text theme</span></span>     | <span data-ttu-id="a14b0-144">**Claro** ou **Escuro**</span><span class="sxs-lookup"><span data-stu-id="a14b0-144">**Light** or **Dark**</span></span> | <span data-ttu-id="a14b0-145">Um esquema de cores pode ser definido para o texto, com base na imagem de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="a14b0-145">A color scheme can be defined for the text, based on the background image.</span></span> <span data-ttu-id="a14b0-146">Por exemplo, se a imagem tiver um fundo escuro, um tema claro poderá ser aplicado para tornar o texto mais visível e atender às taxas de contraste de cores para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="a14b0-146">For example, if the image has a dark background, a light theme can be applied to make the text more visible and to meet color contrast ratios for accessibility purposes.</span></span> |
| <span data-ttu-id="a14b0-147">Gradiente</span><span class="sxs-lookup"><span data-stu-id="a14b0-147">Gradient</span></span>       | <span data-ttu-id="a14b0-148">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="a14b0-148">**True** or **False**</span></span> | <span data-ttu-id="a14b0-149">Um gradiente pode ser aplicado à imagem para atender às taxas de contraste de cores para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="a14b0-149">A gradient can be applied to the image to meet color contrast ratios for accessibility purposes.</span></span> |

## <a name="add-a-hero-module-to-a-new-page"></a><span data-ttu-id="a14b0-150">Adicionar um módulo de hero a uma nova página</span><span class="sxs-lookup"><span data-stu-id="a14b0-150">Add a hero module to a new page</span></span>

<span data-ttu-id="a14b0-151">Para adicionar um módulo de hero a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a14b0-151">To add a hero module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="a14b0-152">Vá para **Modelos** e crie um modelo de página chamado **modelo de hero**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-152">Go to **Templates**, and create a page template that is named **hero template**.</span></span>
1. <span data-ttu-id="a14b0-153">No slot **Principal** da página padrão, adicione um módulo de hero.</span><span class="sxs-lookup"><span data-stu-id="a14b0-153">In the **Main** slot of the default page, add a hero module.</span></span>
1. <span data-ttu-id="a14b0-154">Faça check-in do modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="a14b0-154">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="a14b0-155">Use o modelo de hero que criou para criar uma página nomeada **página de hero**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-155">Use the hero template that you just created to create a page that is named **hero page**.</span></span>
1. <span data-ttu-id="a14b0-156">No slot **Principal** da página padrão, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-156">In the **Main** slot of the default page, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="a14b0-157">Na caixa de diálogo **Adicionar módulo**, em **Selecionar módulos**, selecione um módulo de hero e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-157">In the **Add Module** dialog box, under **Select Modules**, select the hero module, and then select **OK**.</span></span>
1. <span data-ttu-id="a14b0-158">Na árvore de estrutura de tópicos à esquerda, selecione o módulo de hero.</span><span class="sxs-lookup"><span data-stu-id="a14b0-158">In the outline tree on the left, select the hero module.</span></span>
1. <span data-ttu-id="a14b0-159">No painel de propriedades à direita, selecione **Adicionar uma imagem**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-159">In the properties pane on the right, select **Add an image**.</span></span> <span data-ttu-id="a14b0-160">Em seguida, selecione uma imagem existente ou carregue uma nova imagem.</span><span class="sxs-lookup"><span data-stu-id="a14b0-160">Then either select an existing image or upload a new image.</span></span>
1. <span data-ttu-id="a14b0-161">Selecione **Título**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-161">Select **Heading**.</span></span>
1. <span data-ttu-id="a14b0-162">Na caixa de diálogo **Título**, adicione o texto do cabeçalho, selecione o nível do cabeçalho e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-162">In the **Heading** dialog box, add the heading text, select the heading level, and then select **OK**.</span></span>
1. <span data-ttu-id="a14b0-163">Em **Rich Text**, adicione o texto como necessário.</span><span class="sxs-lookup"><span data-stu-id="a14b0-163">Under **Rich Text**, add text as you require.</span></span>
1. <span data-ttu-id="a14b0-164">Selecione **Adicionar link de ação**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-164">Select **Add Action Link**.</span></span>
1. <span data-ttu-id="a14b0-165">Na caixa de diálogo **Action Link**, adicione o texto do link, uma URL do link e uma etiqueta ARIA para o link e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a14b0-165">In the **Action Link** dialog box, add link text, a link URL, and an ARIA label for the link, and then select **OK**.</span></span>
1. <span data-ttu-id="a14b0-166">Salve a página e visualize suas alterações.</span><span class="sxs-lookup"><span data-stu-id="a14b0-166">Save the page, and preview your changes.</span></span>
1. <span data-ttu-id="a14b0-167">Insira a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="a14b0-167">Check in the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a14b0-168">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a14b0-168">Additional resources</span></span>

[<span data-ttu-id="a14b0-169">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="a14b0-169">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a14b0-170">Módulo de alerta</span><span class="sxs-lookup"><span data-stu-id="a14b0-170">Alert module</span></span>](add-alert.md)

[<span data-ttu-id="a14b0-171">Módulo de carrossel</span><span class="sxs-lookup"><span data-stu-id="a14b0-171">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="a14b0-172">Módulo de bloco de conteúdo sofisticado</span><span class="sxs-lookup"><span data-stu-id="a14b0-172">Content rich block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="a14b0-173">Módulo de posicionamento de conteúdo</span><span class="sxs-lookup"><span data-stu-id="a14b0-173">Content placement module</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="a14b0-174">Módulo de recurso</span><span class="sxs-lookup"><span data-stu-id="a14b0-174">Feature module</span></span>](add-feature-module.md)

[<span data-ttu-id="a14b0-175">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="a14b0-175">Video player module</span></span>](add-video-player.md)
