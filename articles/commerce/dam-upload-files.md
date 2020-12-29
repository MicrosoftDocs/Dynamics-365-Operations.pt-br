---
title: Carregar arquivos que não sejam imagens e vídeos
description: Este tópico descreve como carregar arquivos binários que não sejam imagens e vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 4acd3bec32cdfe627f6eb33dd5dc652f7cff74a8
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594203"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="bb0ca-103">Carregar arquivos que não sejam imagens e vídeos</span><span class="sxs-lookup"><span data-stu-id="bb0ca-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="bb0ca-104">Este tópico descreve como carregar arquivos que não sejam imagens e vídeos no assistente para criação de sites do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="bb0ca-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="bb0ca-105">Overview</span></span>

<span data-ttu-id="bb0ca-106">A Biblioteca de Mídia do assistente para criação de sites do Commerce permite o carregamento de ativos binários que não sejam imagens ou vídeos.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="bb0ca-107">Por exemplo, talvez você queira carregar arquivos do Microsoft Excel, Microsoft Word, Microsoft PowerPoint ou PDF.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="bb0ca-108">Há suporte para os seguintes tipos de documentos:</span><span class="sxs-lookup"><span data-stu-id="bb0ca-108">The following document types are supported:</span></span>
- <span data-ttu-id="bb0ca-109">7Z</span><span class="sxs-lookup"><span data-stu-id="bb0ca-109">7Z</span></span>
- <span data-ttu-id="bb0ca-110">AVI</span><span class="sxs-lookup"><span data-stu-id="bb0ca-110">AVI</span></span>
- <span data-ttu-id="bb0ca-111">CS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-111">CS</span></span>
- <span data-ttu-id="bb0ca-112">CSS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-112">CSS</span></span>
- <span data-ttu-id="bb0ca-113">DOC</span><span class="sxs-lookup"><span data-stu-id="bb0ca-113">DOC</span></span>
- <span data-ttu-id="bb0ca-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="bb0ca-114">DOCX</span></span>
- <span data-ttu-id="bb0ca-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="bb0ca-115">EPUB</span></span>
- <span data-ttu-id="bb0ca-116">GIF</span><span class="sxs-lookup"><span data-stu-id="bb0ca-116">GIF</span></span>
- <span data-ttu-id="bb0ca-117">INDD</span><span class="sxs-lookup"><span data-stu-id="bb0ca-117">INDD</span></span>
- <span data-ttu-id="bb0ca-118">JAR</span><span class="sxs-lookup"><span data-stu-id="bb0ca-118">JAR</span></span>
- <span data-ttu-id="bb0ca-119">JPG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-119">JPG</span></span>
- <span data-ttu-id="bb0ca-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-120">JPEG</span></span>
- <span data-ttu-id="bb0ca-121">JS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-121">JS</span></span>
- <span data-ttu-id="bb0ca-122">MP3</span><span class="sxs-lookup"><span data-stu-id="bb0ca-122">MP3</span></span>
- <span data-ttu-id="bb0ca-123">MP4</span><span class="sxs-lookup"><span data-stu-id="bb0ca-123">MP4</span></span>
- <span data-ttu-id="bb0ca-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-124">MPEG</span></span>
- <span data-ttu-id="bb0ca-125">MPG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-125">MPG</span></span>
- <span data-ttu-id="bb0ca-126">ODP</span><span class="sxs-lookup"><span data-stu-id="bb0ca-126">ODP</span></span>
- <span data-ttu-id="bb0ca-127">ODS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-127">ODS</span></span>
- <span data-ttu-id="bb0ca-128">ODT</span><span class="sxs-lookup"><span data-stu-id="bb0ca-128">ODT</span></span>
- <span data-ttu-id="bb0ca-129">PDF</span><span class="sxs-lookup"><span data-stu-id="bb0ca-129">PDF</span></span>
- <span data-ttu-id="bb0ca-130">PNG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-130">PNG</span></span>
- <span data-ttu-id="bb0ca-131">PPT</span><span class="sxs-lookup"><span data-stu-id="bb0ca-131">PPT</span></span>
- <span data-ttu-id="bb0ca-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="bb0ca-132">PPTX</span></span>
- <span data-ttu-id="bb0ca-133">PS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-133">PS</span></span>
- <span data-ttu-id="bb0ca-134">QXP</span><span class="sxs-lookup"><span data-stu-id="bb0ca-134">QXP</span></span>
- <span data-ttu-id="bb0ca-135">RAR</span><span class="sxs-lookup"><span data-stu-id="bb0ca-135">RAR</span></span>
- <span data-ttu-id="bb0ca-136">RTF</span><span class="sxs-lookup"><span data-stu-id="bb0ca-136">RTF</span></span>
- <span data-ttu-id="bb0ca-137">SVG</span><span class="sxs-lookup"><span data-stu-id="bb0ca-137">SVG</span></span>
- <span data-ttu-id="bb0ca-138">TAR</span><span class="sxs-lookup"><span data-stu-id="bb0ca-138">TAR</span></span>
- <span data-ttu-id="bb0ca-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="bb0ca-139">TGZ</span></span>
- <span data-ttu-id="bb0ca-140">TXT</span><span class="sxs-lookup"><span data-stu-id="bb0ca-140">TXT</span></span>
- <span data-ttu-id="bb0ca-141">WMV</span><span class="sxs-lookup"><span data-stu-id="bb0ca-141">WMV</span></span>
- <span data-ttu-id="bb0ca-142">XLS</span><span class="sxs-lookup"><span data-stu-id="bb0ca-142">XLS</span></span>
- <span data-ttu-id="bb0ca-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="bb0ca-143">XLSX</span></span>
- <span data-ttu-id="bb0ca-144">XML</span><span class="sxs-lookup"><span data-stu-id="bb0ca-144">XML</span></span>
- <span data-ttu-id="bb0ca-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="bb0ca-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="bb0ca-146">Carregar um arquivo</span><span class="sxs-lookup"><span data-stu-id="bb0ca-146">Upload a file</span></span>

<span data-ttu-id="bb0ca-147">Para carregar um arquivo no assistente para criação de sites do Commerce, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="bb0ca-148">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="bb0ca-149">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="bb0ca-150">No explorador de arquivos, selecione um ou mais arquivos e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="bb0ca-151">Na caixa de diálogo **Carregar Item de Mídia**, insira os metadados do título, descrição e palavra-chave, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="bb0ca-152">Para publicar o(s) arquivo(s) imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="bb0ca-153">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="bb0ca-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bb0ca-154">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="bb0ca-154">Additional resources</span></span>

[<span data-ttu-id="bb0ca-155">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="bb0ca-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="bb0ca-156">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="bb0ca-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="bb0ca-157">Carregar vídeos</span><span class="sxs-lookup"><span data-stu-id="bb0ca-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="bb0ca-158">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="bb0ca-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="bb0ca-159">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="bb0ca-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="bb0ca-160">Carregar e atender arquivos estáticos</span><span class="sxs-lookup"><span data-stu-id="bb0ca-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
