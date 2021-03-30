---
title: Adicionar um favicon
description: Este tópico explica como adicionar um favicon ao seu site.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 786ba02c312b7cdb3cf7f0689737084887d536bc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206334"
---
# <a name="add-a-favicon"></a><span data-ttu-id="f6f64-103">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="f6f64-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f6f64-104">Este tópico explica como adicionar um favicon ao seu site.</span><span class="sxs-lookup"><span data-stu-id="f6f64-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="f6f64-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f6f64-105">Overview</span></span>

<span data-ttu-id="f6f64-106">Um favicon é um pequeno arquivo gráfico que é mostrado em uma guia do navegador da Web, na barra de endereços, no histórico de navegação e em indicadores ou favoritos, entre outros lugares.</span><span class="sxs-lookup"><span data-stu-id="f6f64-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="f6f64-107">Recomendamos que você adicione um favicon ao seu site, porque ele representa e reforça sua marca e ajuda a distinguir seu site de outros sites visitados por seus clientes.</span><span class="sxs-lookup"><span data-stu-id="f6f64-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="f6f64-108">Embora você possa adicionar vários favoritos de vários tamanhos e tipos de arquivo ao seu site, este tópico mostra como adicionar um único favorito.</span><span class="sxs-lookup"><span data-stu-id="f6f64-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="f6f64-109">No entanto, o mesmo processo e local são usados para adicionar mais favicons.</span><span class="sxs-lookup"><span data-stu-id="f6f64-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="f6f64-110">Carregar um favicon na coleção de ativos do seu site</span><span class="sxs-lookup"><span data-stu-id="f6f64-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="f6f64-111">Para carregar um favicon na coleção de ativos do seu site, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f6f64-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="f6f64-112">No painel de navegação esquerdo, selecione **Biblioteca de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-112">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="f6f64-113">Na barra de comandos, selecione **Carregar \> Carregar Itens de Mídia**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-113">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="f6f64-114">Na janela do explorador de arquivos, navegue até o arquivo de imagem favicon que deseja carregar, selecione-o e, em seguida, selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-114">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="f6f64-115">Na caixa de diálogo **Carregar Item de Mídia**, digite o título e o texto alt necessários.</span><span class="sxs-lookup"><span data-stu-id="f6f64-115">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="f6f64-116">Se você deseja publicar as imagens imediatamente após o carregamento, marque a caixa de seleção **Publicar itens de mídia após upload**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-116">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6f64-117">Se você não marcar a caixa de diálogo **Publicar itens de mídia após upload**, será preciso retornar à página **Itens de mídia** e publicar manualmente o favicon depois.</span><span class="sxs-lookup"><span data-stu-id="f6f64-117">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="f6f64-118">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-118">Select **OK**.</span></span>
1. <span data-ttu-id="f6f64-119">No painel de propriedades à direita, copie a URL pública do favicon.</span><span class="sxs-lookup"><span data-stu-id="f6f64-119">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="f6f64-120">Você usará essa URL posteriormente.</span><span class="sxs-lookup"><span data-stu-id="f6f64-120">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="f6f64-121">Criar o HTML do favicon</span><span class="sxs-lookup"><span data-stu-id="f6f64-121">Create the HTML for your favicon</span></span>

<span data-ttu-id="f6f64-122">Para criar o HTML do favicon, use a seguinte cadeia de caracteres de código de HTML.</span><span class="sxs-lookup"><span data-stu-id="f6f64-122">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="f6f64-123">No atributo **href**, substitua **URL\_pública\_para\_seu\_favicon** pela URL pública que você copiou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f6f64-123">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="f6f64-124">Criar um fragmento que contenha uma marca meta para o seu favicon</span><span class="sxs-lookup"><span data-stu-id="f6f64-124">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="f6f64-125">Para criar um fragmento que contenha uma marca meta para o seu favicon, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f6f64-125">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="f6f64-126">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-126">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="f6f64-127">Na caixa de diálogo **Novo fragmento**, selecione **Marcas meta** como o módulo no qual o fragmento se baseia.</span><span class="sxs-lookup"><span data-stu-id="f6f64-127">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="f6f64-128">Informe um nome para o fragmento e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-128">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f6f64-129">Na árvore de hierarquia de fragmento, selecione o filho **Padrão de marcas meta**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-129">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="f6f64-130">No painel à direita, em **Marcas meta**, selecione **Adicionar** e, em seguida, insira a cadeia de caracteres HTML criada anteriormente para o favicon.</span><span class="sxs-lookup"><span data-stu-id="f6f64-130">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="f6f64-131">Selecione **Concluir edição** e, em seguida, selecione **Publicar** para publicar o fragmento.</span><span class="sxs-lookup"><span data-stu-id="f6f64-131">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="f6f64-132">Adicionar o fragmento da marca meta à seção head do HTML de suas páginas</span><span class="sxs-lookup"><span data-stu-id="f6f64-132">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="f6f64-133">Para adicionar o fragmento da marca meta à seção **head** do HTML de suas páginas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f6f64-133">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="f6f64-134">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu favicon e seleciona **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-134">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="f6f64-135">Na árvore de hierarquia de modelos, selecione o botão de reticências (**...**) à direita do contêiner **Head do HTML** e, em seguida, selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-135">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="f6f64-136">Na caixa de diálogo **Selecionar fragmento**, selecione o fragmento da marca meta criado anteriormente e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f6f64-136">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="f6f64-137">Selecione **Concluir edição** e depois selecione **Publicar** para publicar o modelo.</span><span class="sxs-lookup"><span data-stu-id="f6f64-137">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="f6f64-138">Se o site usar mais de um modelo, você deverá adicionar o fragmento de marcas meta a todos eles.</span><span class="sxs-lookup"><span data-stu-id="f6f64-138">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="f6f64-139">Ao visualizar páginas baseadas no modelo ao qual você adicionou o fragmento de marcas meta, você verá agora o favicon na guia do navegador.</span><span class="sxs-lookup"><span data-stu-id="f6f64-139">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f6f64-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f6f64-140">Additional resources</span></span>

[<span data-ttu-id="f6f64-141">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="f6f64-141">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="f6f64-142">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="f6f64-142">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="f6f64-143">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="f6f64-143">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="f6f64-144">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="f6f64-144">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="f6f64-145">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="f6f64-145">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="f6f64-146">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="f6f64-146">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="f6f64-147">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="f6f64-147">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]