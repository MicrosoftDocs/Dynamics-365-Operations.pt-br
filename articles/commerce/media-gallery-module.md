---
title: Módulo de galeria de mídia
description: Este tópico abrange os módulos de galeria de mídia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 07/31/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 9df2b91b0a57c73e395242f840c423fa8c7f2c9f
ms.sourcegitcommit: 629988f1a704d62648d98649056931b8c33b9e08
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2020
ms.locfileid: "3811149"
---
# <a name="media-gallery-module"></a><span data-ttu-id="806b6-103">Módulo de galeria de mídia</span><span class="sxs-lookup"><span data-stu-id="806b6-103">Media gallery module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="806b6-104">Este tópico abrange os módulos de galeria de mídia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="806b6-104">This topic covers media gallery modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="806b6-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="806b6-105">Overview</span></span>

<span data-ttu-id="806b6-106">Os módulos de galeria de mídia mostram uma ou mais imagens em uma exibição da galeria.</span><span class="sxs-lookup"><span data-stu-id="806b6-106">Media gallery modules show one or more images in a gallery view.</span></span> <span data-ttu-id="806b6-107">Os módulos de galeria de mídia oferecem suporte a imagens em miniatura, que podem ser organizadas horizontalmente (como uma linha abaixo da imagem) ou verticalmente (como uma coluna ao lado da imagem).</span><span class="sxs-lookup"><span data-stu-id="806b6-107">Media gallery modules support thumbnail images, which can be arranged either horizontally (as a row below the image) or vertically (as a column next to the image).</span></span> <span data-ttu-id="806b6-108">Os módulos de galeria de mídia também fornecem recursos que permitem que as imagens sejam ampliadas (aumentadas) ou exibidas no modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="806b6-108">Media gallery modules also provide capabilities that enable images to be zoomed (magnified) or viewed in full-screen mode.</span></span> <span data-ttu-id="806b6-109">Para ser renderizada em um módulo de galeria de mídia, uma imagem deve estar disponível na Biblioteca de Mídia do construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="806b6-109">To be rendered in a media gallery module, an image must be available in the Commerce site builder Media Library.</span></span> <span data-ttu-id="806b6-110">No momento, os módulos de galeria de mídia oferecem suporte somente a imagens.</span><span class="sxs-lookup"><span data-stu-id="806b6-110">Currently, media gallery modules support only images.</span></span>

<span data-ttu-id="806b6-111">No modo padrão, um módulo de galeria de mídia usa a ID do produto disponível no contexto da página de uma página de detalhes do produto (PDP) para renderizar as imagens de produto correspondentes.</span><span class="sxs-lookup"><span data-stu-id="806b6-111">In the default mode, a media gallery module uses the product ID that is available from the page context of a product details page (PDP) to render the corresponding product images.</span></span> <span data-ttu-id="806b6-112">Um caminho de arquivo de mídia deve ser definido para todos os produtos na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="806b6-112">In Commerce headquarters, a media file path must be defined for all products.</span></span> <span data-ttu-id="806b6-113">Em seguida, as imagens devem ser carregadas na Biblioteca de Mídia do construtor de sites de acordo com o caminho do arquivo definido para os produtos na sede do Commerce.</span><span class="sxs-lookup"><span data-stu-id="806b6-113">Images should then be uploaded to the site builder Media Library according to the file path that was defined for the products in Commerce headquarters.</span></span> <span data-ttu-id="806b6-114">Essas imagens incluem imagens de produtos e de variantes de produto.</span><span class="sxs-lookup"><span data-stu-id="806b6-114">These images include images for products and any product variants.</span></span> <span data-ttu-id="806b6-115">Para obter mais informações sobre como carregar imagens na Biblioteca de Mídia do construtor de sites, consulte [Carregar imagens](dam-upload-images.md).</span><span class="sxs-lookup"><span data-stu-id="806b6-115">For more information about how to upload images to site builder Media Library, see [Upload images](dam-upload-images.md).</span></span>

<span data-ttu-id="806b6-116">Como alternativa, um módulo de galeria de mídia pode hospedar um conjunto de imagens totalmente organizado em uma página da galeria de imagens, em que não haja nenhuma dependência na ID do produto ou no contexto da página.</span><span class="sxs-lookup"><span data-stu-id="806b6-116">Alternatively, a media gallery module can host a fully curated set of images on an image gallery page, where there are no dependencies on the product ID or page context.</span></span> <span data-ttu-id="806b6-117">Nesse caso, as imagens devem ser carregadas na Biblioteca de Mídia do construtor de sites e especificadas no site construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="806b6-117">In this case, images must be uploaded to site builder Media Library and specified in site builder.</span></span>

<span data-ttu-id="806b6-118">Veja alguns exemplos de uso dos módulos de galeria de mídia:</span><span class="sxs-lookup"><span data-stu-id="806b6-118">Here are some usage examples for media gallery modules:</span></span>

- <span data-ttu-id="806b6-119">Renderização de imagens de produtos em uma PDP</span><span class="sxs-lookup"><span data-stu-id="806b6-119">Rendering product images on a PDP</span></span>
- <span data-ttu-id="806b6-120">Renderização de imagens do produto em uma página de marketing do produto</span><span class="sxs-lookup"><span data-stu-id="806b6-120">Rendering product images on a product marketing page</span></span>
- <span data-ttu-id="806b6-121">Apresentação de um conjunto de imagens organizado em uma página de marketing, como uma página da galeria</span><span class="sxs-lookup"><span data-stu-id="806b6-121">Showcasing a curated set of images on a marketing page, such as a gallery page</span></span>

<span data-ttu-id="806b6-122">No exemplo da ilustração a seguir, uma caixa de compra em uma PDP hospeda imagens de produto usando um módulo de galeria de mídia.</span><span class="sxs-lookup"><span data-stu-id="806b6-122">In the example in the following illustration, a buy box on a PDP hosts product images by using a media gallery module.</span></span>

![Exemplo de uma caixa de compra em uma página de detalhes do produto que hospeda imagens do produto usando um módulo de galeria de mídia](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a><span data-ttu-id="806b6-124">Propriedades da galeria de mídia</span><span class="sxs-lookup"><span data-stu-id="806b6-124">Media gallery properties</span></span>

| <span data-ttu-id="806b6-125">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="806b6-125">Property name</span></span> | <span data-ttu-id="806b6-126">Valores</span><span class="sxs-lookup"><span data-stu-id="806b6-126">Values</span></span> | <span data-ttu-id="806b6-127">descrição</span><span class="sxs-lookup"><span data-stu-id="806b6-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="806b6-128">Origem da imagem</span><span class="sxs-lookup"><span data-stu-id="806b6-128">Image source</span></span> | <span data-ttu-id="806b6-129">**Contexto da página** ou **ID do produto**</span><span class="sxs-lookup"><span data-stu-id="806b6-129">**Page context** or **Product ID**</span></span> | <span data-ttu-id="806b6-130">O valor padrão é **Contexto de página**.</span><span class="sxs-lookup"><span data-stu-id="806b6-130">The default value is **Page context**.</span></span> <span data-ttu-id="806b6-131">Se a propriedade **Contexto da página** estiver selecionada, o módulo esperará que a página forneça as informações de ID do produto.</span><span class="sxs-lookup"><span data-stu-id="806b6-131">If **Page context** is selected, the module expects the page to provide the product ID information.</span></span> <span data-ttu-id="806b6-132">Se **ID do produto** estiver selecionada, a ID do produto de uma imagem deverá ser fornecida como o valor da propriedade **ID do produto**.</span><span class="sxs-lookup"><span data-stu-id="806b6-132">If **Product ID** is selected, the product ID for an image must be provided as the value of the **Product ID** property.</span></span> <span data-ttu-id="806b6-133">Esse recurso está disponível no Commerce versão 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="806b6-133">This capability is available in Commerce version 10.0.12.</span></span> |
| <span data-ttu-id="806b6-134">ID do produto</span><span class="sxs-lookup"><span data-stu-id="806b6-134">Product ID</span></span> | <span data-ttu-id="806b6-135">Uma ID do produto</span><span class="sxs-lookup"><span data-stu-id="806b6-135">A product ID</span></span> | <span data-ttu-id="806b6-136">Essa propriedade é aplicável somente se o valor da propriedade **Origem da imagem** for **ID do produto**.</span><span class="sxs-lookup"><span data-stu-id="806b6-136">This property is applicable only if the value of the **Image source** property is **Product ID**.</span></span> |
| <span data-ttu-id="806b6-137">Zoom da imagem</span><span class="sxs-lookup"><span data-stu-id="806b6-137">Image zoom</span></span> | <span data-ttu-id="806b6-138">**Inline** ou **Contêiner**</span><span class="sxs-lookup"><span data-stu-id="806b6-138">**Inline** or **Container**</span></span> | <span data-ttu-id="806b6-139">Essa propriedade permite que o usuário aplique zoom às imagens no módulo de galeria de mídia.</span><span class="sxs-lookup"><span data-stu-id="806b6-139">This property lets the user zoom images in the media gallery module.</span></span> <span data-ttu-id="806b6-140">Uma imagem pode ser ampliada inline ou em um contêiner separado ao lado da imagem.</span><span class="sxs-lookup"><span data-stu-id="806b6-140">An image can be zoomed either inline or in a separate container next to the image.</span></span> <span data-ttu-id="806b6-141">Esse recurso está disponível na versão 10.0.12</span><span class="sxs-lookup"><span data-stu-id="806b6-141">This capability is available in 10.0.12</span></span> |
| <span data-ttu-id="806b6-142">Escala de zoom</span><span class="sxs-lookup"><span data-stu-id="806b6-142">Zoom scale</span></span> | <span data-ttu-id="806b6-143">Um número decimal</span><span class="sxs-lookup"><span data-stu-id="806b6-143">A decimal number</span></span> | <span data-ttu-id="806b6-144">Essa propriedade especifica o fator de escala para a ampliação de imagens.</span><span class="sxs-lookup"><span data-stu-id="806b6-144">This property specifies the scale factor for zooming images.</span></span> <span data-ttu-id="806b6-145">Por exemplo, se o valor for definido como **2,5**, as imagens serão ampliadas 2,5 vezes.</span><span class="sxs-lookup"><span data-stu-id="806b6-145">For example, if the value is set to **2.5**, images are magnified 2.5 times.</span></span>|
| <span data-ttu-id="806b6-146">Tela inteira</span><span class="sxs-lookup"><span data-stu-id="806b6-146">Full screen</span></span> | <span data-ttu-id="806b6-147">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="806b6-147">**True** or **False**</span></span> | <span data-ttu-id="806b6-148">Essa propriedade especifica se as imagens podem ser exibidas no modo de tela inteira.</span><span class="sxs-lookup"><span data-stu-id="806b6-148">This property specifies whether images can be viewed in full-screen mode.</span></span> <span data-ttu-id="806b6-149">No modo de tela inteira, as imagens também podem ser ampliadas ainda mais se a capacidade de zoom estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="806b6-149">In full-screen mode, images can be also be further magnified if the zoom capability is turned on.</span></span> <span data-ttu-id="806b6-150">Esse recurso está disponível no Commerce versão 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="806b6-150">This capability is available in Commerce version 10.0.13.</span></span> |
| <span data-ttu-id="806b6-151">Imagens</span><span class="sxs-lookup"><span data-stu-id="806b6-151">Images</span></span> | <span data-ttu-id="806b6-152">Imagens selecionadas na Biblioteca de Mídia do construtor de sites</span><span class="sxs-lookup"><span data-stu-id="806b6-152">Images that are selected from site builder Media Library</span></span> | <span data-ttu-id="806b6-153">Além de serem renderizadas de um produto, as imagens podem ser organizadas para um módulo de galeria de mídia.</span><span class="sxs-lookup"><span data-stu-id="806b6-153">In addition to being rendered from a product, images can be curated for a media gallery module.</span></span> <span data-ttu-id="806b6-154">Essas imagens serão anexadas a qualquer imagem de produto disponível.</span><span class="sxs-lookup"><span data-stu-id="806b6-154">These images will be appended to any product images that are available.</span></span> <span data-ttu-id="806b6-155">Esse recurso está disponível no Commerce versão 10.0.12.</span><span class="sxs-lookup"><span data-stu-id="806b6-155">This capability is available in Commerce version 10.0.12.</span></span> |
| <span data-ttu-id="806b6-156">Orientação de miniatura</span><span class="sxs-lookup"><span data-stu-id="806b6-156">Thumbnail orientation</span></span> | <span data-ttu-id="806b6-157">**Vertical** ou **Horizontal**</span><span class="sxs-lookup"><span data-stu-id="806b6-157">**Vertical** or **Horizontal**</span></span> | <span data-ttu-id="806b6-158">Essa propriedade especifica se as imagens em miniatura devem ser exibidas em uma faixa vertical ou em uma faixa horizontal.</span><span class="sxs-lookup"><span data-stu-id="806b6-158">This property specifies whether thumbnail images should be shown in a vertical strip or a horizontal strip.</span></span> |

<span data-ttu-id="806b6-159">A ilustração a seguir mostra um exemplo de um módulo de galeria de mídia no qual as opções de tela inteira e de zoom estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="806b6-159">The following illustration shows an example of a media gallery module where the full-screen and zoom options are available.</span></span>

![Exemplo de um módulo de galeria de mídia no qual as opções de tela inteira e de zoom estão disponíveis](./media/ecommerce-media-zoom.png)

<span data-ttu-id="806b6-161">A ilustração a seguir mostra um exemplo de um módulo de galeria de mídia com imagens organizadas (isto é, as imagens especificadas não dependem da ID do produto ou do contexto da página).</span><span class="sxs-lookup"><span data-stu-id="806b6-161">The following illustration shows an example of a media gallery module that has curated images (that is, the specified images aren't dependent on the product ID or page context).</span></span>

![Exemplo de um módulo de galeria de mídia com imagens organizadas](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="806b6-163">Interação do Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="806b6-163">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="806b6-164">Quando a origem da imagem é derivada do contexto da página, a ID do produto da PDP é usada para recuperar as imagens.</span><span class="sxs-lookup"><span data-stu-id="806b6-164">When the image source is derived from the page context, the product ID from the PDP is used to retrieve the images.</span></span> <span data-ttu-id="806b6-165">O módulo de galeria de mídia recupera o caminho do arquivo da imagem dos produtos usando as interfaces de programação de aplicativos (APIs) de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="806b6-165">The media gallery module retrieves the image file path for products by using Commerce Scale Unit application programming interfaces (APIs).</span></span> <span data-ttu-id="806b6-166">As imagens são então extraídas da Biblioteca de Mídia para que possam ser renderizadas no módulo.</span><span class="sxs-lookup"><span data-stu-id="806b6-166">The images are then pulled from the Media Library so that they can be rendered in the module.</span></span>

## <a name="add-a-media-gallery-module-to-a-page"></a><span data-ttu-id="806b6-167">Adicionar um módulo de galeria de mídia a uma página</span><span class="sxs-lookup"><span data-stu-id="806b6-167">Add a media gallery module to a page</span></span>

<span data-ttu-id="806b6-168">Para adicionar um módulo de galeria de mídia a uma página de marketing, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="806b6-168">To add a media gallery module to a marketing page, follow these steps.</span></span>

1. <span data-ttu-id="806b6-169">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="806b6-169">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="806b6-170">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-170">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-171">No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="806b6-171">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="806b6-172">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Página Padrão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-172">In the **Add Module** dialog box, select the **Default Page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-173">No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="806b6-173">In the **Main** slot of the default page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="806b6-174">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-174">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-175">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="806b6-175">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="806b6-176">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="806b6-176">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="806b6-177">Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de marketing**.</span><span class="sxs-lookup"><span data-stu-id="806b6-177">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="806b6-178">Em **Nome da página**, insira **Página de galeria de mídia** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-178">Under **Page name**, enter **Media gallery page**, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-179">No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="806b6-179">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="806b6-180">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-180">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-181">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="806b6-181">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="806b6-182">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Galeria de mídia** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="806b6-182">In the **Add Module** dialog box, select the **Media gallery** module, and then select **OK**.</span></span>
1. <span data-ttu-id="806b6-183">No painel de propriedades do módulo de galeria de mídia, em **Origem da imagem**, selecione **Productid**.</span><span class="sxs-lookup"><span data-stu-id="806b6-183">In the property pane for the media gallery module, under **Image source**, select **Productid**.</span></span> <span data-ttu-id="806b6-184">Em seguida, no campo **ID do produto**, insira uma ID do produto.</span><span class="sxs-lookup"><span data-stu-id="806b6-184">Then, in the **Product id** field, enter a product ID.</span></span>
1. <span data-ttu-id="806b6-185">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="806b6-185">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="806b6-186">Você poderá ver as imagens do produto em uma exibição de galeria.</span><span class="sxs-lookup"><span data-stu-id="806b6-186">You should be able to see the images for the product in a gallery view.</span></span>
1. <span data-ttu-id="806b6-187">Para usar somente imagens organizadas, no painel de propriedades, em **Origem da imagem**, selecione **Productid**.</span><span class="sxs-lookup"><span data-stu-id="806b6-187">To use only curated images, in the property pane, under **Image source**, select **Productid**.</span></span> <span data-ttu-id="806b6-188">Em seguida, em **Imagens**, selecione **Adicionar uma imagem** quantas vez for necessário para adicionar imagens da Biblioteca de Mídia.</span><span class="sxs-lookup"><span data-stu-id="806b6-188">Then, under **Images**, select **Add an image** as many times as required to add images from the Media Library.</span></span>
1. <span data-ttu-id="806b6-189">Defina as propriedades adicionais que você quiser definir, como **Zoom de imagem**, **Fator de zoom** e **Orientação de miniaturas**.</span><span class="sxs-lookup"><span data-stu-id="806b6-189">Set any additional properties that you want to set, such as **Image zoom**, **Zoom factor**, and **Thumbnails orientation**.</span></span>
1. <span data-ttu-id="806b6-190">Depois que terminar, selecione **Salvar** e **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-la.</span><span class="sxs-lookup"><span data-stu-id="806b6-190">When you've finished, select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="806b6-191">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="806b6-191">Additional resources</span></span>

[<span data-ttu-id="806b6-192">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="806b6-192">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="806b6-193">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="806b6-193">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="806b6-194">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="806b6-194">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="806b6-195">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="806b6-195">Upload images</span></span>](dam-upload-images.md)