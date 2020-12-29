---
title: Módulo iframe
description: Este tópico abrange o módulo iframe e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 4afd8f60938c99d1981be1625ef28f91d9e4bb4c
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665387"
---
# <a name="iframe-module"></a><span data-ttu-id="b3a2c-103">Módulo iframe</span><span class="sxs-lookup"><span data-stu-id="b3a2c-103">Iframe module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b3a2c-104">Este tópico abrange o módulo iframe e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-104">This topic covers the iframe module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="b3a2c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="b3a2c-105">Overview</span></span>

<span data-ttu-id="b3a2c-106">Um módulo iframe fornece um iframe (quadro embutido) que hospeda o conteúdo externo em um site.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-106">An iframe module provides an iframe (inline frame) that hosts external content on a site.</span></span> <span data-ttu-id="b3a2c-107">Por exemplo, ele pode ser usado para hospedar um vídeo do YouTube ou visualizador de arquivos de vídeo de PDF em qualquer página do site.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-107">For example, it can be used to host a YouTube video or a PDF file viewer on any site page.</span></span> 

<span data-ttu-id="b3a2c-108">Um módulo iframe requer uma URL de destino.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-108">An iframe module requires a target URL.</span></span> <span data-ttu-id="b3a2c-109">Em seguida, ele hospeda o conteúdo da página de destino dentro de um elemento do **iframe** de HTML.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-109">It then hosts the content of the target page inside an HTML **iframe** element.</span></span> <span data-ttu-id="b3a2c-110">As URLs externas devem estar na lista de permissões pelas diretivas do CSP (política de segurança de conteúdo) do site.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-110">External URLs must be on the allow list per the site's content security policy (CSP) directives.</span></span> <span data-ttu-id="b3a2c-111">Para conteúdo iframe, as URLs devem ser permitidas usando a diretiva **ancestral do quadro**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-111">For iframe content, URLs should be allowed by using the **frame-ancestor** directive.</span></span> <span data-ttu-id="b3a2c-112">Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="b3a2c-112">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b3a2c-113">O módulo iframe está disponível na versão 10.0.13 do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-113">The iframe module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="b3a2c-114">A imagem a seguir mostra exemplos de módulos iframe que demonstram vídeos externos nas páginas do site.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-114">The following image shows examples of iframe modules that showcase external videos on site pages.</span></span>

![Exemplo de módulos iframe que demonstram vídeos externos](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a><span data-ttu-id="b3a2c-116">Propriedades do módulo iframe</span><span class="sxs-lookup"><span data-stu-id="b3a2c-116">Iframe module properties</span></span>

| <span data-ttu-id="b3a2c-117">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="b3a2c-117">Property name</span></span>             | <span data-ttu-id="b3a2c-118">Alíquota</span><span class="sxs-lookup"><span data-stu-id="b3a2c-118">Value</span></span>                 | <span data-ttu-id="b3a2c-119">descrição</span><span class="sxs-lookup"><span data-stu-id="b3a2c-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="b3a2c-120">Título</span><span class="sxs-lookup"><span data-stu-id="b3a2c-120">Heading</span></span> | <span data-ttu-id="b3a2c-121">Texto</span><span class="sxs-lookup"><span data-stu-id="b3a2c-121">Text</span></span> | <span data-ttu-id="b3a2c-122">O título do módulo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-122">The heading for the module.</span></span> |
| <span data-ttu-id="b3a2c-123">URL de Destino</span><span class="sxs-lookup"><span data-stu-id="b3a2c-123">Target URL</span></span> | <span data-ttu-id="b3a2c-124">URL</span><span class="sxs-lookup"><span data-stu-id="b3a2c-124">URL</span></span> | <span data-ttu-id="b3a2c-125">A URL que está hospedada no módulo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-125">The URL that is hosted in the module.</span></span> |
| <span data-ttu-id="b3a2c-126">Altura</span><span class="sxs-lookup"><span data-stu-id="b3a2c-126">Height</span></span> | <span data-ttu-id="b3a2c-127">Número ou porcentagem</span><span class="sxs-lookup"><span data-stu-id="b3a2c-127">Number or percentage</span></span> | <span data-ttu-id="b3a2c-128">A altura do módulo, em pixels ou como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-128">The height of the module, in pixels or as a percentage.</span></span> <span data-ttu-id="b3a2c-129">Por exemplo, o valor **100** será tratado como um número de pixels e o valor **100%** será tratado como uma porcentagem.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-129">For example, the value **100** will be treated as a number of pixels, and the value **100%** will be treated as a percentage.</span></span> |
| <span data-ttu-id="b3a2c-130">Etiqueta aria</span><span class="sxs-lookup"><span data-stu-id="b3a2c-130">Aria label</span></span> | <span data-ttu-id="b3a2c-131">Texto</span><span class="sxs-lookup"><span data-stu-id="b3a2c-131">Text</span></span> | <span data-ttu-id="b3a2c-132">Uma etiqueta acessível por Rich Internet Applications (ARIA) pode ser definida para fins de acessibilidade.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-132">An Accessible Rich Internet Applications (ARIA) label can be defined for accessibility purposes.</span></span> |

## <a name="add-an-iframe-module-to-a-page"></a><span data-ttu-id="b3a2c-133">Adicionar um módulo iframe a uma página</span><span class="sxs-lookup"><span data-stu-id="b3a2c-133">Add an iframe module to a page</span></span>

<span data-ttu-id="b3a2c-134">Para adicionar um módulo iframe a uma página para mostrar um vídeo externo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-134">To add an iframe module to a page to show an external video, follow these steps.</span></span>

1. <span data-ttu-id="b3a2c-135">Vá para **Modelos** e selecione **Novo** para criar um novo modelo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-135">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b3a2c-136">Na caixa de diálogo **Novo Modelo**, em **Nome do modelo**, insira **Modelo de marketing** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-136">In the **New Template** dialog box, under **Template name**, enter **Marketing template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b3a2c-137">Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-137">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b3a2c-138">Vá para **Páginas** e selecione **Novo** para criar uma nova página.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-138">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="b3a2c-139">Na caixa de diálogo **Escolher um modelo**, selecione o modelo **Modelo de marketing**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-139">In the **Choose a template** dialog box, select the **Marketing template** template.</span></span> <span data-ttu-id="b3a2c-140">Em **Nome da página**, informe **página de Marketing** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-140">Under **Page name**, enter **Marketing page**, and then select **OK**.</span></span>
1. <span data-ttu-id="b3a2c-141">No slot **Principal** da nova página, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-141">In the **Main** slot of the new page, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b3a2c-142">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-142">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b3a2c-143">No painel de propriedades do módulo, defina o valor de **Largura** como **Preencher Contêiner**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-143">In the module's properties pane, set the **Width** value to **Fill Container**.</span></span>
1. <span data-ttu-id="b3a2c-144">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-144">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b3a2c-145">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **iframe** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-145">In the **Add Module** dialog box, select the **iframe** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b3a2c-146">No painel propriedades do módulo, defina o valor **URL de Destino** como uma URL externa para um vídeo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-146">In the module's properties pane, set the **Target URL** value to an external URL for a video.</span></span>
1. <span data-ttu-id="b3a2c-147">Defina outras propriedades, como **Título** e **Altura**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-147">Set other properties, such as **Heading** and **Height**, as you require.</span></span>
1. <span data-ttu-id="b3a2c-148">Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-148">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b3a2c-149">Acesse a página de marketing do site.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-149">Go to the marketing page on your site.</span></span> <span data-ttu-id="b3a2c-150">Você verá que o vídeo é processado no módulo iframe.</span><span class="sxs-lookup"><span data-stu-id="b3a2c-150">You should see that the video is rendered in the iframe module.</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="b3a2c-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b3a2c-151">Additional resources</span></span>

[<span data-ttu-id="b3a2c-152">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="b3a2c-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="b3a2c-153">Gerenciar a Política de Segurança de Conteúdo (CSP)</span><span class="sxs-lookup"><span data-stu-id="b3a2c-153">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
