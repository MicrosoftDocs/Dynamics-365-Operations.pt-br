---
title: Carregar imagens
description: Este tópico descreve como carregar imagens no assistente para criação de sites do Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8571c52b98a87751400dab9482168ee370834bcc
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096971"
---
# <a name="upload-images"></a><span data-ttu-id="e1057-103">Carregar imagens</span><span class="sxs-lookup"><span data-stu-id="e1057-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e1057-104">Este tópico descreve como carregar imagens no assistente para criação de sites do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e1057-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="e1057-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="e1057-105">Overview</span></span>

<span data-ttu-id="e1057-106">A Biblioteca de Mídia do assistente para criação de sites do Commerce permite carregar imagens, individualmente ou em massa, usando pastas.</span><span class="sxs-lookup"><span data-stu-id="e1057-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="e1057-107">Você sempre deve carregar a versão da imagem com a resolução e a qualidade mais altas, porque o componente redimensionador de imagem otimizará automaticamente a imagem em diferentes portas de exibição e seus pontos de interrupção.</span><span class="sxs-lookup"><span data-stu-id="e1057-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="e1057-108">Informações de imagem especificadas durante o carregamento</span><span class="sxs-lookup"><span data-stu-id="e1057-108">Image information specified during upload</span></span>

<span data-ttu-id="e1057-109">Ao carregar uma imagem, as informações a seguir podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="e1057-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="e1057-110">**Título, texto alt, descrição, palavras-chave**: metadados da imagem ou imagens.</span><span class="sxs-lookup"><span data-stu-id="e1057-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="e1057-111">Título e texto alt são valores obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="e1057-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="e1057-112">**Selecionar categoria**:</span><span class="sxs-lookup"><span data-stu-id="e1057-112">**Select category**:</span></span>
    - <span data-ttu-id="e1057-113">**Nenhum(a)**: usado em imagem(ns) para contar histórias de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e1057-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="e1057-114">**Produto, categoria, cliente, funcionário, catálogo**: usados em imagem(ns) de omnicanal do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e1057-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="e1057-115">**Publicar ativos após upload**: quando esta caixa de seleção está marcada, a imagem ou as imagens são publicadas imediatamente após o carregamento.</span><span class="sxs-lookup"><span data-stu-id="e1057-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="e1057-116">Os ativos de imagem com uma categoria atribuída também são marcados automaticamente com a categoria como uma palavra-chave para ajudar na pesquisa de ativos de uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="e1057-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="e1057-117">Convenções de nomenclatura para imagens de omnicanal</span><span class="sxs-lookup"><span data-stu-id="e1057-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="e1057-118">Se você configurou a Biblioteca de Mídia como o back-end da imagem de omnicanal, poderá usar categorias de imagens para indicar a qual categoria a imagem carregada pertence.</span><span class="sxs-lookup"><span data-stu-id="e1057-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="e1057-119">Também existe uma convenção de nomenclatura que deve ser seguida para garantir que as imagens sejam recuperadas corretamente por outros canais, como ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="e1057-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="e1057-120">A convenção de nomenclatura padrão varia de acordo com a categoria:</span><span class="sxs-lookup"><span data-stu-id="e1057-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="e1057-121">As imagens do catálogo devem ser nomeadas como "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="e1057-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="e1057-122">As imagens da categoria devem ser nomeadas como "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="e1057-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="e1057-123">As imagens do cliente devem ser nomeadas como "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="e1057-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="e1057-124">As imagens dos funcionários devem ser nomeadas como "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="e1057-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="e1057-125">As imagens do produto devem ser nomeadas como "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="e1057-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="e1057-126">001 é a sequência da imagem e pode ser 001, 002, 003, 004 ou 005</span><span class="sxs-lookup"><span data-stu-id="e1057-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="e1057-127">As imagens da grade de produto devem ser nomeadas como "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="e1057-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="e1057-128">Carregar uma imagem</span><span class="sxs-lookup"><span data-stu-id="e1057-128">Upload an image</span></span>

<span data-ttu-id="e1057-129">Para carregar uma imagem no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1057-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e1057-130">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="e1057-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="e1057-131">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="e1057-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="e1057-132">Na janela do explorador de arquivos, explore e selecione um ou mais arquivos de imagem a serem carregados e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e1057-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="e1057-133">Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.</span><span class="sxs-lookup"><span data-stu-id="e1057-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="e1057-134">Digite uma descrição opcional e palavras-chave e selecione uma categoria, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e1057-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="e1057-135">Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.</span><span class="sxs-lookup"><span data-stu-id="e1057-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="e1057-136">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1057-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="e1057-137">Carregar uma pasta de imagens</span><span class="sxs-lookup"><span data-stu-id="e1057-137">Upload a folder of images</span></span>

<span data-ttu-id="e1057-138">Para carregar uma pasta de imagens em massa no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e1057-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e1057-139">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="e1057-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="e1057-140">Na barra de comandos, selecione **Carregar \> Carregar Pasta**.</span><span class="sxs-lookup"><span data-stu-id="e1057-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="e1057-141">Na janela do explorador de arquivos, explore e selecione uma pasta a ser carregada e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="e1057-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="e1057-142">Na caixa de diálogo **Carregar Itens de Mídia**, insira palavras-chave opcionais e selecione uma categoria, se desejar.</span><span class="sxs-lookup"><span data-stu-id="e1057-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="e1057-143">Se você deseja publicar as imagens na pasta imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.</span><span class="sxs-lookup"><span data-stu-id="e1057-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="e1057-144">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1057-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e1057-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e1057-145">Additional resources</span></span>

[<span data-ttu-id="e1057-146">Visão geral do gerenciamento de ativos digitais</span><span class="sxs-lookup"><span data-stu-id="e1057-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="e1057-147">Carregar vídeo</span><span class="sxs-lookup"><span data-stu-id="e1057-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="e1057-148">Carregue arquivos</span><span class="sxs-lookup"><span data-stu-id="e1057-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="e1057-149">Cortar imagens</span><span class="sxs-lookup"><span data-stu-id="e1057-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="e1057-150">Personalizar pontos focais da imagem</span><span class="sxs-lookup"><span data-stu-id="e1057-150">Customize image focal points</span></span>](dam-custom-focal-point.md)
