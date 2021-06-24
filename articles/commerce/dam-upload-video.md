---
title: Carregar vídeos
description: Este tópico descreve como carregar vídeos no construtor de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e3579b54c58898b79c84406480a3b58f541c4621
ms.sourcegitcommit: 257437a57e146496a49782bc8aad179c92fbf6e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6224529"
---
# <a name="upload-videos"></a><span data-ttu-id="e499b-103">Carregar vídeos</span><span class="sxs-lookup"><span data-stu-id="e499b-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e499b-104">Este tópico descreve como carregar vídeos no construtor de sites do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e499b-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="e499b-105">A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar vídeos.</span><span class="sxs-lookup"><span data-stu-id="e499b-105">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="e499b-106">Você sempre deve carregar a versão de um vídeo com a taxa de bits e a resolução mais altas, porque o vídeo será convertido automaticamente para se adequar a diferentes portas de exibição e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e499b-106">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="e499b-107">Informações de vídeo especificadas durante o carregamento</span><span class="sxs-lookup"><span data-stu-id="e499b-107">Video information specified during upload</span></span>

<span data-ttu-id="e499b-108">Ao carregar um vídeo, as informações a seguir podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="e499b-108">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="e499b-109">**Título, descrição, palavras-chave**: metadados do vídeo.</span><span class="sxs-lookup"><span data-stu-id="e499b-109">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="e499b-110">**Gerar legenda oculta automaticamente**: especifica se a legenda oculta deve ser gerada automaticamente para o vídeo (somente o idioma inglês é compatível).</span><span class="sxs-lookup"><span data-stu-id="e499b-110">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video (only English language is supported).</span></span> 
- <span data-ttu-id="e499b-111">**Legenda Oculta**: especifica as legendas ocultas a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="e499b-111">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="e499b-112">**Áudio Regular**: especifica a trilha de áudio comum a ser usada.</span><span class="sxs-lookup"><span data-stu-id="e499b-112">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="e499b-113">**Miniatura**: especifica a miniatura do vídeo.</span><span class="sxs-lookup"><span data-stu-id="e499b-113">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="e499b-114">Se não especificada, será gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e499b-114">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="e499b-115">**Áudio Descritivo**: especifica a trilha de áudio descritiva a ser usada.</span><span class="sxs-lookup"><span data-stu-id="e499b-115">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="e499b-116">Carregar um vídeo</span><span class="sxs-lookup"><span data-stu-id="e499b-116">Upload a video</span></span>

<span data-ttu-id="e499b-117">Para carregar um vídeo no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e499b-117">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e499b-118">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="e499b-118">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="e499b-119">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="e499b-119">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="e499b-120">Na janela do explorador de arquivos, explore e selecione um ou mais arquivos de vídeo a serem carregados e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e499b-120">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="e499b-121">Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.</span><span class="sxs-lookup"><span data-stu-id="e499b-121">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="e499b-122">Digite uma descrição opcional e palavras-chave e selecione uma categoria, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e499b-122">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="e499b-123">Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**</span><span class="sxs-lookup"><span data-stu-id="e499b-123">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="e499b-124">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e499b-124">Select **OK**.</span></span>

<span data-ttu-id="e499b-125">Se você estiver carregando vários tipos de ativos simultaneamente (por exemplo, imagens e vídeos), na caixa de diálogo **Carregar Item de Mídia**, você poderá especificar apenas palavras-chave, se os arquivos devem ser publicados imediatamente após o carregamento e se legendas ocultas devem ser geradas automaticamente para arquivos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="e499b-125">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="e499b-126">Todos os ativos compartilharão as mesmas palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="e499b-126">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e499b-127">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e499b-127">Additional resources</span></span>

[<span data-ttu-id="e499b-128">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="e499b-128">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="e499b-129">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="e499b-129">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="e499b-130">Carregue arquivos</span><span class="sxs-lookup"><span data-stu-id="e499b-130">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="e499b-131">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="e499b-131">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="e499b-132">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="e499b-132">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="e499b-133">Carregar e atender arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="e499b-133">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
