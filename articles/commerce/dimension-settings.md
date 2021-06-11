---
title: Aplicar configurações de exibição para dimensões do produto
description: Este tópico abrange as configurações de exibição para dimensões do produto e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117209"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="8c188-103">Aplicar configurações de exibição para dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="8c188-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="8c188-104">Este tópico abrange as configurações de exibição para dimensões do produto e descreve como aplicá-las no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8c188-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="8c188-105">O Dynamics 365 Commerce oferece suporte a dimensões de tamanho, estilo e cor para distinguir grades de produtos.</span><span class="sxs-lookup"><span data-stu-id="8c188-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="8c188-106">Normalmente, as dimensões são mostradas como valores de texto, como "Pequeno", "Médio" e "Grande" para tamanhos e "Preto" e "Marrom" para cores.</span><span class="sxs-lookup"><span data-stu-id="8c188-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="8c188-107">No entanto, se um produto oferecer suporte a várias variações, pode ser difícil procurar grades de produtos, pois várias seleções são necessárias para exibir a imagem de cada grade.</span><span class="sxs-lookup"><span data-stu-id="8c188-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="8c188-108">Para facilitar a navegação por grades de produtos, a versão 10.0.20 do Commerce pode usar imagens e códigos hexadecimais (hex) para mostrar as dimensões como amostras.</span><span class="sxs-lookup"><span data-stu-id="8c188-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="8c188-109">No construtor de sites do Commerce, as configurações de dimensão são definidas em **Configurações do Site \> Extensões \> Configurações da Dimensão**.</span><span class="sxs-lookup"><span data-stu-id="8c188-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="8c188-110">A ilustração a seguir mostra um exemplo das configurações de dimensão no construtor de sites.</span><span class="sxs-lookup"><span data-stu-id="8c188-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Exemplo de configurações de site no construtor de sites do Commerce](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="8c188-112">Duas configurações de dimensão estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="8c188-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="8c188-113">**Dimensões a serem exibidas como imagem** – especifique quais dimensões devem aparecer como amostras nas páginas de site de comércio eletrônico, como PDPs (páginas de detalhes do produto) e páginas de lista de resultados de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8c188-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="8c188-114">Qualquer combinação de dimensões de estilo, tamanho e cor pode ser mostrada como uma amostra.</span><span class="sxs-lookup"><span data-stu-id="8c188-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="8c188-115">Se uma dimensão for selecionada para exibição como uma amostra, a renderização do módulo comercial procurará uma configuração disponível de uma amostra de código hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="8c188-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="8c188-116">Se nenhum código hexadecimal for configurado, a lógica do sistema procurará uma configuração de uma amostra de URL da imagem.</span><span class="sxs-lookup"><span data-stu-id="8c188-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="8c188-117">Se nem um código hexadecimal nem uma URL de imagem estiverem configurados, o texto será mostrado.</span><span class="sxs-lookup"><span data-stu-id="8c188-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="8c188-118">A ilustração a seguir mostra um exemplo em que um PDP em um site de comércio eletrônico inclui amostras de cor e tamanho.</span><span class="sxs-lookup"><span data-stu-id="8c188-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="8c188-119">Neste exemplo, um código hexadecimal é configurado para a dimensão de cor.</span><span class="sxs-lookup"><span data-stu-id="8c188-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="8c188-120">Portanto, as amostras são mostradas como cores.</span><span class="sxs-lookup"><span data-stu-id="8c188-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="8c188-121">No entanto, nem um código hexadecimal nem uma URL de imagem estão configurados para a dimensão de tamanho.</span><span class="sxs-lookup"><span data-stu-id="8c188-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="8c188-122">Portanto, o texto é exibido.</span><span class="sxs-lookup"><span data-stu-id="8c188-122">Therefore, text is shown.</span></span>

    ![Exemplo da dimensão de cor mostrada como amostras em uma página de detalhes de produtos de comércio eletrônico](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="8c188-124">**Dimensões a serem exibidas no cartão de produto** – especifique quais dimensões devem aparecer em cartões de produtos que são mostrados nas listas e nas páginas de listagem.</span><span class="sxs-lookup"><span data-stu-id="8c188-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="8c188-125">Antes que uma dimensão possa aparecer em um cartão de produto, essa configuração deve ser habilitada para essa dimensão.</span><span class="sxs-lookup"><span data-stu-id="8c188-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="8c188-126">A configuração **Dimensões a serem exibidas como imagem** também deve ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="8c188-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="8c188-127">O comportamento de seleção de amostras em cartões de produto é otimizado para a dimensão de cor.</span><span class="sxs-lookup"><span data-stu-id="8c188-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="8c188-128">Para outras dimensões, uma extensão de exibição pode ser necessária para personalizar o comportamento de seleção de amostra.</span><span class="sxs-lookup"><span data-stu-id="8c188-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="8c188-129">A ilustração a seguir mostra um exemplo onde uma página de listagem em um site de comércio eletrônico contém cartões de produto que incluem amostras de cores.</span><span class="sxs-lookup"><span data-stu-id="8c188-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Exemplo da dimensão de cor mostrada como amostras em uma página de lista de comércio eletrônico](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="8c188-131">Para obter informações sobre como configurar dimensões de produto para que sejam mostradas como amostras nas páginas do site, consulte [Configurar valores de dimensão do produto para serem exibidos como amostras](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="8c188-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c188-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8c188-132">Additional resources</span></span>

[<span data-ttu-id="8c188-133">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="8c188-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="8c188-134">Módulo de resultados de pesquisa</span><span class="sxs-lookup"><span data-stu-id="8c188-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="8c188-135">Módulo de caixa de compra</span><span class="sxs-lookup"><span data-stu-id="8c188-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="8c188-136">Configurar valores de dimensão de produto para serem exibidos como amostras</span><span class="sxs-lookup"><span data-stu-id="8c188-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
