---
title: Carregar arquivos que não sejam imagens e vídeos
description: Este tópico descreve como carregar arquivos binários que não sejam imagens e vídeos no construtor de sites do Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
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
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799244"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="64ff1-103">Carregar arquivos diferentes de imagens e vídeos</span><span class="sxs-lookup"><span data-stu-id="64ff1-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="64ff1-104">Este tópico descreve como carregar arquivos binários que não sejam imagens e vídeos no construtor de sites do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="64ff1-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="64ff1-105">A Biblioteca de Mídia do assistente para criação de sites do Commerce permite o carregamento de ativos binários que não sejam imagens ou vídeos.</span><span class="sxs-lookup"><span data-stu-id="64ff1-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="64ff1-106">Por exemplo, talvez você queira carregar arquivos do Microsoft Excel, Microsoft Word, Microsoft PowerPoint ou PDF.</span><span class="sxs-lookup"><span data-stu-id="64ff1-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="64ff1-107">Há suporte para os seguintes tipos de documentos:</span><span class="sxs-lookup"><span data-stu-id="64ff1-107">The following document types are supported:</span></span>
- <span data-ttu-id="64ff1-108">7Z</span><span class="sxs-lookup"><span data-stu-id="64ff1-108">7Z</span></span>
- <span data-ttu-id="64ff1-109">AVI</span><span class="sxs-lookup"><span data-stu-id="64ff1-109">AVI</span></span>
- <span data-ttu-id="64ff1-110">CS</span><span class="sxs-lookup"><span data-stu-id="64ff1-110">CS</span></span>
- <span data-ttu-id="64ff1-111">CSS</span><span class="sxs-lookup"><span data-stu-id="64ff1-111">CSS</span></span>
- <span data-ttu-id="64ff1-112">DOC</span><span class="sxs-lookup"><span data-stu-id="64ff1-112">DOC</span></span>
- <span data-ttu-id="64ff1-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="64ff1-113">DOCX</span></span>
- <span data-ttu-id="64ff1-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="64ff1-114">EPUB</span></span>
- <span data-ttu-id="64ff1-115">GIF</span><span class="sxs-lookup"><span data-stu-id="64ff1-115">GIF</span></span>
- <span data-ttu-id="64ff1-116">INDD</span><span class="sxs-lookup"><span data-stu-id="64ff1-116">INDD</span></span>
- <span data-ttu-id="64ff1-117">JAR</span><span class="sxs-lookup"><span data-stu-id="64ff1-117">JAR</span></span>
- <span data-ttu-id="64ff1-118">JPG</span><span class="sxs-lookup"><span data-stu-id="64ff1-118">JPG</span></span>
- <span data-ttu-id="64ff1-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="64ff1-119">JPEG</span></span>
- <span data-ttu-id="64ff1-120">JS</span><span class="sxs-lookup"><span data-stu-id="64ff1-120">JS</span></span>
- <span data-ttu-id="64ff1-121">MP3</span><span class="sxs-lookup"><span data-stu-id="64ff1-121">MP3</span></span>
- <span data-ttu-id="64ff1-122">MP4</span><span class="sxs-lookup"><span data-stu-id="64ff1-122">MP4</span></span>
- <span data-ttu-id="64ff1-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="64ff1-123">MPEG</span></span>
- <span data-ttu-id="64ff1-124">MPG</span><span class="sxs-lookup"><span data-stu-id="64ff1-124">MPG</span></span>
- <span data-ttu-id="64ff1-125">ODP</span><span class="sxs-lookup"><span data-stu-id="64ff1-125">ODP</span></span>
- <span data-ttu-id="64ff1-126">ODS</span><span class="sxs-lookup"><span data-stu-id="64ff1-126">ODS</span></span>
- <span data-ttu-id="64ff1-127">ODT</span><span class="sxs-lookup"><span data-stu-id="64ff1-127">ODT</span></span>
- <span data-ttu-id="64ff1-128">PDF</span><span class="sxs-lookup"><span data-stu-id="64ff1-128">PDF</span></span>
- <span data-ttu-id="64ff1-129">PNG</span><span class="sxs-lookup"><span data-stu-id="64ff1-129">PNG</span></span>
- <span data-ttu-id="64ff1-130">PPT</span><span class="sxs-lookup"><span data-stu-id="64ff1-130">PPT</span></span>
- <span data-ttu-id="64ff1-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="64ff1-131">PPTX</span></span>
- <span data-ttu-id="64ff1-132">PS</span><span class="sxs-lookup"><span data-stu-id="64ff1-132">PS</span></span>
- <span data-ttu-id="64ff1-133">QXP</span><span class="sxs-lookup"><span data-stu-id="64ff1-133">QXP</span></span>
- <span data-ttu-id="64ff1-134">RAR</span><span class="sxs-lookup"><span data-stu-id="64ff1-134">RAR</span></span>
- <span data-ttu-id="64ff1-135">RTF</span><span class="sxs-lookup"><span data-stu-id="64ff1-135">RTF</span></span>
- <span data-ttu-id="64ff1-136">SVG</span><span class="sxs-lookup"><span data-stu-id="64ff1-136">SVG</span></span>
- <span data-ttu-id="64ff1-137">TAR</span><span class="sxs-lookup"><span data-stu-id="64ff1-137">TAR</span></span>
- <span data-ttu-id="64ff1-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="64ff1-138">TGZ</span></span>
- <span data-ttu-id="64ff1-139">TXT</span><span class="sxs-lookup"><span data-stu-id="64ff1-139">TXT</span></span>
- <span data-ttu-id="64ff1-140">WMV</span><span class="sxs-lookup"><span data-stu-id="64ff1-140">WMV</span></span>
- <span data-ttu-id="64ff1-141">XLS</span><span class="sxs-lookup"><span data-stu-id="64ff1-141">XLS</span></span>
- <span data-ttu-id="64ff1-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="64ff1-142">XLSX</span></span>
- <span data-ttu-id="64ff1-143">XML</span><span class="sxs-lookup"><span data-stu-id="64ff1-143">XML</span></span>
- <span data-ttu-id="64ff1-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="64ff1-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="64ff1-145">Carregar um arquivo</span><span class="sxs-lookup"><span data-stu-id="64ff1-145">Upload a file</span></span>

<span data-ttu-id="64ff1-146">Para carregar um arquivo no assistente para criação de sites do Commerce, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="64ff1-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="64ff1-147">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="64ff1-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="64ff1-148">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="64ff1-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="64ff1-149">No explorador de arquivos, selecione um ou mais arquivos e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="64ff1-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="64ff1-150">Na caixa de diálogo **Carregar Item de Mídia**, insira os metadados do título, descrição e palavra-chave, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="64ff1-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="64ff1-151">Para publicar o(s) arquivo(s) imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.</span><span class="sxs-lookup"><span data-stu-id="64ff1-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="64ff1-152">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="64ff1-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64ff1-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="64ff1-153">Additional resources</span></span>

[<span data-ttu-id="64ff1-154">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="64ff1-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="64ff1-155">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="64ff1-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="64ff1-156">Carregar vídeos</span><span class="sxs-lookup"><span data-stu-id="64ff1-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="64ff1-157">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="64ff1-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="64ff1-158">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="64ff1-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="64ff1-159">Carregar e atender arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="64ff1-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
