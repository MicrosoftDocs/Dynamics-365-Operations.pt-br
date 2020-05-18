---
title: Carregar vídeos
description: Este tópico descreve como carregar vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98cb4f9049509dd700cf38a5d176447f86e9c824
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096973"
---
# <a name="upload-videos"></a><span data-ttu-id="1d519-103">Carregar vídeos</span><span class="sxs-lookup"><span data-stu-id="1d519-103">Upload videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1d519-104">Este tópico descreve como carregar vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="1d519-104">This topic describes how to upload videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="1d519-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="1d519-105">Overview</span></span>

<span data-ttu-id="1d519-106">A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar vídeos.</span><span class="sxs-lookup"><span data-stu-id="1d519-106">The Commerce site builder Media Library allows you to upload videos.</span></span> <span data-ttu-id="1d519-107">Você sempre deve carregar a versão de um vídeo com a taxa de bits e a resolução mais altas, porque o vídeo será convertido automaticamente para se adequar a diferentes portas de exibição e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="1d519-107">You should always upload the version of a video with the highest bitrate and resolution, because the video will be automatically converted to be suitable for different viewports and their breakpoints.</span></span>

### <a name="video-information-specified-during-upload"></a><span data-ttu-id="1d519-108">Informações de vídeo especificadas durante o carregamento</span><span class="sxs-lookup"><span data-stu-id="1d519-108">Video information specified during upload</span></span>

<span data-ttu-id="1d519-109">Ao carregar um vídeo, as informações a seguir podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="1d519-109">When uploading a video, the following information can be specified.</span></span>

- <span data-ttu-id="1d519-110">**Título, descrição, palavras-chave**: metadados do vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d519-110">**Title, Description, Keywords**: Metadata of the video.</span></span>
- <span data-ttu-id="1d519-111">**Gerar automaticamente legendas ocultas**: especifica se as legendas ocultas devem ser geradas automaticamente para o vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d519-111">**Automatically generate closed captions**: Specifies whether closed captions should be automatically generated for the video.</span></span>
- <span data-ttu-id="1d519-112">**Legenda Oculta**: especifica as legendas ocultas a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="1d519-112">**Closed Caption**: Specifies the closed captions to be used.</span></span>
- <span data-ttu-id="1d519-113">**Áudio Regular**: especifica a trilha de áudio comum a ser usada.</span><span class="sxs-lookup"><span data-stu-id="1d519-113">**Regular Audio**: Specifies the regular audio track to be used.</span></span>
- <span data-ttu-id="1d519-114">**Miniatura**: especifica a miniatura do vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d519-114">**Thumbnail**: Specifies the thumbnail for the video.</span></span> <span data-ttu-id="1d519-115">Se não especificada, será gerada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="1d519-115">If not specified, it will be generated automatically.</span></span>
- <span data-ttu-id="1d519-116">**Áudio Descritivo**: especifica a trilha de áudio descritiva a ser usada.</span><span class="sxs-lookup"><span data-stu-id="1d519-116">**Descriptive Audio**: Specifies the descriptive audio track to be used.</span></span>

## <a name="upload-a-video"></a><span data-ttu-id="1d519-117">Carregar um vídeo</span><span class="sxs-lookup"><span data-stu-id="1d519-117">Upload a video</span></span>

<span data-ttu-id="1d519-118">Para carregar um vídeo no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="1d519-118">To upload a video in site builder, follow these steps.</span></span>

1. <span data-ttu-id="1d519-119">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="1d519-119">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="1d519-120">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="1d519-120">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="1d519-121">Na janela do explorador de arquivos, explore e selecione um ou mais arquivos de vídeo a serem carregados e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="1d519-121">In the File Explorer window, navigate to and select one or more video files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="1d519-122">Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.</span><span class="sxs-lookup"><span data-stu-id="1d519-122">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="1d519-123">Digite uma descrição opcional e palavras-chave e selecione uma categoria, se desejar.</span><span class="sxs-lookup"><span data-stu-id="1d519-123">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="1d519-124">Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**</span><span class="sxs-lookup"><span data-stu-id="1d519-124">If you want to publish the image(s) after immediately upload, select the **Publish media items after upload** check box</span></span>
1. <span data-ttu-id="1d519-125">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1d519-125">Select **OK**.</span></span>

<span data-ttu-id="1d519-126">Se você estiver carregando vários tipos de ativos simultaneamente (por exemplo, imagens e vídeos), na caixa de diálogo **Carregar Item de Mídia**, você poderá especificar apenas palavras-chave, se os arquivos devem ser publicados imediatamente após o carregamento e se legendas ocultas devem ser geradas automaticamente para arquivos de vídeo.</span><span class="sxs-lookup"><span data-stu-id="1d519-126">If you are uploading multiple types of assets simultaneously (for example, images and videos), in the **Upload Media Item** dialog box you will only be able to specify keywords, whether the files should be published immediately after upload, and whether closed captions should be automatically generated for video files.</span></span> <span data-ttu-id="1d519-127">Todos os ativos compartilharão as mesmas palavras-chave.</span><span class="sxs-lookup"><span data-stu-id="1d519-127">All the assets will share the same keywords.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1d519-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="1d519-128">Additional resources</span></span>

[<span data-ttu-id="1d519-129">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="1d519-129">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="1d519-130">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="1d519-130">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="1d519-131">Carregue arquivos</span><span class="sxs-lookup"><span data-stu-id="1d519-131">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="1d519-132">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="1d519-132">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="1d519-133">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="1d519-133">Customize image focal points</span></span>](dam-custom-focal-point.md)