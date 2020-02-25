---
title: Módulo de reprodutor de vídeo
description: Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025634"
---
# <a name="video-player-module"></a><span data-ttu-id="bbb80-103">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="bbb80-103">Video player module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="bbb80-104">Este tópico abrange os módulos de exibição e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bbb80-104">This topic covers video player modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bbb80-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="bbb80-105">Overview</span></span>

<span data-ttu-id="bbb80-106">O módulo de player de vídeo é usado para dar suporte à reprodução de vídeo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-106">The video player module is used to support video playback.</span></span> <span data-ttu-id="bbb80-107">Ele pode ser adicionado a qualquer página, desde que o conteúdo de vídeo seja carregado e disponibilizado no sistema de gerenciamento de conteúdo (CMS).</span><span class="sxs-lookup"><span data-stu-id="bbb80-107">It can be added to any page, provided that video content is uploaded to and available in the content management system (CMS).</span></span> <span data-ttu-id="bbb80-108">O módulo de player de vídeo oferece suporte para o tipo de mídia. mp4.</span><span class="sxs-lookup"><span data-stu-id="bbb80-108">The video player module supports the .mp4 media type.</span></span>

## <a name="video-player-module"></a><span data-ttu-id="bbb80-109">Módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="bbb80-109">Video player module</span></span>

<span data-ttu-id="bbb80-110">O módulo de reprodução de vídeo pode ser usado para exibir vídeos em um site comercial online.</span><span class="sxs-lookup"><span data-stu-id="bbb80-110">The video player module can be used to showcase videos on an e-Commerce site.</span></span> <span data-ttu-id="bbb80-111">Ele é compatível com todas as funcionalidades de reprodução, como reproduzir, pausar, modo tela cheia, descrições de áudio e legendas.</span><span class="sxs-lookup"><span data-stu-id="bbb80-111">It supports all playback capabilities, such as play, pause, full-size mode, audio descriptions, and closed captions.</span></span> <span data-ttu-id="bbb80-112">O módulo de exibição de vídeo também oferece suporte à personalização de legendas atender aos padrões de acessibilidade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbb80-112">The video player module also supports customization of closed captions to meet Microsoft accessibility standards.</span></span> <span data-ttu-id="bbb80-113">Por exemplo, você pode personalizar o tamanho da fonte e a cor de plano de fundo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-113">For example, you can customize the font size and background color.</span></span>

<span data-ttu-id="bbb80-114">O módulo player de vídeo também oferece suporte a faixas de áudio secundárias.</span><span class="sxs-lookup"><span data-stu-id="bbb80-114">The video player module also supports secondary audio tracks.</span></span> <span data-ttu-id="bbb80-115">Quando um vídeo é carregado no CMS, uma trilha de áudio secundária também pode ser carregada.</span><span class="sxs-lookup"><span data-stu-id="bbb80-115">When a video is uploaded to the CMS, a secondary audio track can also be uploaded.</span></span> <span data-ttu-id="bbb80-116">O módulo de reprodutor de vídeo pode reproduzir a trilha de áudio secundária se um usuário selecioná-la.</span><span class="sxs-lookup"><span data-stu-id="bbb80-116">The video player module can then play the secondary audio track if a user selects it.</span></span>

### <a name="examples-of-video-player-modules-in-e-commerce"></a><span data-ttu-id="bbb80-117">Exemplos de módulos de reprodutor de vídeo no comércio online</span><span class="sxs-lookup"><span data-stu-id="bbb80-117">Examples of video player modules in e-Commerce</span></span>

- <span data-ttu-id="bbb80-118">Vídeos instrutivas sobre a página de detalhes de produto ou páginas de marketing</span><span class="sxs-lookup"><span data-stu-id="bbb80-118">Instructional videos on product details pages or marketing pages</span></span>
- <span data-ttu-id="bbb80-119">Vídeos promocionais ou vídeos sobre políticas em qualquer página de marketing</span><span class="sxs-lookup"><span data-stu-id="bbb80-119">Promotional videos or videos about policies on any marketing page</span></span>
- <span data-ttu-id="bbb80-120">Vídeos de marketing que destacam recursos de produto em páginas de detalhes de produto ou páginas de marketing</span><span class="sxs-lookup"><span data-stu-id="bbb80-120">Marketing videos that highlight product features on product details pages or marketing pages</span></span>

### <a name="video-player-module-properties"></a><span data-ttu-id="bbb80-121">Propriedades de módulo de reprodutor de vídeo</span><span class="sxs-lookup"><span data-stu-id="bbb80-121">Video player module properties</span></span>

| <span data-ttu-id="bbb80-122">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="bbb80-122">Property name</span></span>         | <span data-ttu-id="bbb80-123">Alíquota</span><span class="sxs-lookup"><span data-stu-id="bbb80-123">Value</span></span>                               | <span data-ttu-id="bbb80-124">Descrição</span><span class="sxs-lookup"><span data-stu-id="bbb80-124">Description</span></span> |
|-----------------------|-------------------------------------|-------------|
| <span data-ttu-id="bbb80-125">Reprodução automática</span><span class="sxs-lookup"><span data-stu-id="bbb80-125">Auto play</span></span>             | <span data-ttu-id="bbb80-126">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-126">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-127">Quando o valor é definido como **Verdadeiro**, o vídeo é executado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="bbb80-127">When the value is set to **True**, the video is automatically played.</span></span> |
| <span data-ttu-id="bbb80-128">Ativar Mudo</span><span class="sxs-lookup"><span data-stu-id="bbb80-128">Mute</span></span>                  | <span data-ttu-id="bbb80-129">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-129">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-130">Quando o valor é definido como **Verdadeiro**, o áudio fica no mudo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-130">When the value is set to **True**, the audio is muted.</span></span> <span data-ttu-id="bbb80-131">Para esse reprodutor, o valor padrão é **Falso**.</span><span class="sxs-lookup"><span data-stu-id="bbb80-131">For this player, the default value is **False**.</span></span> <span data-ttu-id="bbb80-132">No navegador do Chrome, vídeos reproduzidos automaticamente são mudos por padrão e o áudio é reproduzido apenas se o usuário reproduzir manualmente o vídeo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-132">In the Chrome browser, autoplay videos are muted by default, and the audio is played only if the user manually plays the video.</span></span> |
| <span data-ttu-id="bbb80-133">Loop</span><span class="sxs-lookup"><span data-stu-id="bbb80-133">Loop</span></span>                  | <span data-ttu-id="bbb80-134">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-134">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-135">Quando o valor é definido como **Verdadeiro**, o vídeo é repetido em um loop.</span><span class="sxs-lookup"><span data-stu-id="bbb80-135">When the value is set to **True**, the video is repeated in a loop.</span></span> |
| <span data-ttu-id="bbb80-136">Mídia</span><span class="sxs-lookup"><span data-stu-id="bbb80-136">Media</span></span>                 | <span data-ttu-id="bbb80-137">Caminho e nome do arquivo de vídeo</span><span class="sxs-lookup"><span data-stu-id="bbb80-137">Video file path and name</span></span> | <span data-ttu-id="bbb80-138">O arquivo de vídeo é reproduzido pelo reprodutor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-138">The video file that is played in the video player.</span></span> |
| <span data-ttu-id="bbb80-139">Reproduzir em tela cheia</span><span class="sxs-lookup"><span data-stu-id="bbb80-139">Play fullscreen</span></span>       | <span data-ttu-id="bbb80-140">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-140">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-141">Quando o valor é definido como **Verdadeiro**, o vídeo é exibido no modo tela cheia.</span><span class="sxs-lookup"><span data-stu-id="bbb80-141">When the value is set to **True**, the video is played in full-screen mode.</span></span> |
| <span data-ttu-id="bbb80-142">Disparador da pausa de reprodução</span><span class="sxs-lookup"><span data-stu-id="bbb80-142">Play pause trigger</span></span>    | <span data-ttu-id="bbb80-143">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-143">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-144">Quando o valor é definido como **Verdadeiro**, o botão reproduzir/pausa será mostrado no vídeo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-144">When the value is set to **True**, a play/pause button is shown on the video.</span></span> |
| <span data-ttu-id="bbb80-145">Controles do player de vídeo</span><span class="sxs-lookup"><span data-stu-id="bbb80-145">Video player controls</span></span> | <span data-ttu-id="bbb80-146">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-146">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-147">Quando o valor é definido como **Verdadeiro**, todos os controles do player de vídeo são exibidos.</span><span class="sxs-lookup"><span data-stu-id="bbb80-147">When the value is set to **True**, all video player controls are shown.</span></span> <span data-ttu-id="bbb80-148">Esses controles incluem botões de reprodução e pausa, um indicador de progresso e opções de legenda.</span><span class="sxs-lookup"><span data-stu-id="bbb80-148">These controls include play and pause buttons, a progress indicator, and closed caption options.</span></span> |
| <span data-ttu-id="bbb80-149">Ocultar imagem do pôster</span><span class="sxs-lookup"><span data-stu-id="bbb80-149">Hide poster image</span></span>     | <span data-ttu-id="bbb80-150">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="bbb80-150">**True** or **False**</span></span>               | <span data-ttu-id="bbb80-151">Uma vídeo pode ter uma borda.</span><span class="sxs-lookup"><span data-stu-id="bbb80-151">A video can have a poster frame.</span></span> <span data-ttu-id="bbb80-152">Quando o valor desta propriedade é definido como **Verdadeiro**, a borda fica oculta.</span><span class="sxs-lookup"><span data-stu-id="bbb80-152">When the value of this property is set to **True**, the poster frame is hidden.</span></span> |
| <span data-ttu-id="bbb80-153">Nível de máscara</span><span class="sxs-lookup"><span data-stu-id="bbb80-153">Mask level</span></span>            | <span data-ttu-id="bbb80-154">Um número de **0** a **100**</span><span class="sxs-lookup"><span data-stu-id="bbb80-154">A number from **0** through **100**</span></span> | <span data-ttu-id="bbb80-155">A máscara aplicada ao vídeo para estilo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-155">The mask that is applied to the video for styling.</span></span> |

## <a name="add-a-video-player-module-to-a-page"></a><span data-ttu-id="bbb80-156">Adicionar um módulo de reprodutor de vídeo à página</span><span class="sxs-lookup"><span data-stu-id="bbb80-156">Add a video player module to a page</span></span>

> [!NOTE] 
> <span data-ttu-id="bbb80-157">Antes de criar um módulo de player de vídeo, primeiro você deve carregar um vídeo na Biblioteca de Mídia.</span><span class="sxs-lookup"><span data-stu-id="bbb80-157">Before you create a video player module, you must first upload a video to the Media Library.</span></span>

<span data-ttu-id="bbb80-158">Para adicionar um módulo de reprodução de vídeo a uma nova página e definir as propriedades necessárias, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="bbb80-158">To add a video player module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="bbb80-159">Criar um modelo da página chamado **modelo de reprodutor de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="bbb80-159">Create a page template that is named **video player template**.</span></span>
1. <span data-ttu-id="bbb80-160">No slot **Principal** da página padrão, adicione um módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="bbb80-160">In the **Main** slot of the default page, add a container module.</span></span>
1. <span data-ttu-id="bbb80-161">No módulo de contêiner, adicione os módulos de reprodutor de vídeo e reprodutor de vídeo ambiente.</span><span class="sxs-lookup"><span data-stu-id="bbb80-161">In the container module, add video player and ambient video player modules.</span></span>
1. <span data-ttu-id="bbb80-162">Termine de editar o modelo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="bbb80-162">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="bbb80-163">Use o modelo de player de vídeo que você criou para criar uma página chamada **página do player de vídeo**.</span><span class="sxs-lookup"><span data-stu-id="bbb80-163">Use the video player template that you created to create a page that is named **video player page**.</span></span>
1. <span data-ttu-id="bbb80-164">No slot **Principal** da nova página, adicione um módulo de reprodução de vídeo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-164">In the **Main** slot of the new page, add a video player module.</span></span>
1. <span data-ttu-id="bbb80-165">No painel de propriedades do módulo de player de vídeo, selecione **Adicionar um vídeo**.</span><span class="sxs-lookup"><span data-stu-id="bbb80-165">In the property pane for the video player module, select **Add a video**.</span></span>
1. <span data-ttu-id="bbb80-166">Na caixa de diálogo **Seletor de Mídia**, selecione um vídeo e clique em **Carregar novo item de mídia**.</span><span class="sxs-lookup"><span data-stu-id="bbb80-166">In the **Media Picker** dialog box, select a video, and then select **Upload new media item**.</span></span>
1. <span data-ttu-id="bbb80-167">Salve e exiba a página.</span><span class="sxs-lookup"><span data-stu-id="bbb80-167">Save and preview the page.</span></span> <span data-ttu-id="bbb80-168">Você deve ver o módulo de vídeo na página.</span><span class="sxs-lookup"><span data-stu-id="bbb80-168">You should see the video module on the page.</span></span> <span data-ttu-id="bbb80-169">Você pode alterar outras configurações para personalizar o comportamento do módulo.</span><span class="sxs-lookup"><span data-stu-id="bbb80-169">You can change additional settings to customize the behavior of the module.</span></span>
1. <span data-ttu-id="bbb80-170">Termine de editar a página e publique-a.</span><span class="sxs-lookup"><span data-stu-id="bbb80-170">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bbb80-171">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bbb80-171">Additional resources</span></span>

[<span data-ttu-id="bbb80-172">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="bbb80-172">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="bbb80-173">Módulo de faixa promocional</span><span class="sxs-lookup"><span data-stu-id="bbb80-173">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="bbb80-174">Módulo do carrossel</span><span class="sxs-lookup"><span data-stu-id="bbb80-174">Carousel module</span></span>](add-carousel.md)

[<span data-ttu-id="bbb80-175">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="bbb80-175">Text block module</span></span>](add-content-rich-block.md)

[<span data-ttu-id="bbb80-176">Módulo de bloco de conteúdo</span><span class="sxs-lookup"><span data-stu-id="bbb80-176">Content block module</span></span>](add-hero-module.md)
