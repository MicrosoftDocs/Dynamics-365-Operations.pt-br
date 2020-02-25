---
title: Adicionar um favicon
description: Este tópico explica como adicionar um favicon ao seu site.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 287663817232e7ce86e8fdb1fb5c2fcfeed33d20
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001522"
---
# <a name="add-a-favicon"></a><span data-ttu-id="a4106-103">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="a4106-103">Add a favicon</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="a4106-104">Este tópico explica como adicionar um favicon ao seu site.</span><span class="sxs-lookup"><span data-stu-id="a4106-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="a4106-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="a4106-105">Overview</span></span>

<span data-ttu-id="a4106-106">Um favicon é um pequeno arquivo gráfico que é mostrado em uma guia do navegador da Web, na barra de endereços, no histórico de navegação e em indicadores ou favoritos, entre outros lugares.</span><span class="sxs-lookup"><span data-stu-id="a4106-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="a4106-107">Recomendamos que você adicione um favicon ao seu site, porque ele representa e reforça sua marca e ajuda a distinguir seu site de outros sites visitados por seus clientes.</span><span class="sxs-lookup"><span data-stu-id="a4106-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="a4106-108">Embora você possa adicionar vários favoritos de vários tamanhos e tipos de arquivo ao seu site, este tópico mostra como adicionar um único favorito.</span><span class="sxs-lookup"><span data-stu-id="a4106-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="a4106-109">No entanto, o mesmo processo e local são usados para adicionar mais favicons.</span><span class="sxs-lookup"><span data-stu-id="a4106-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="a4106-110">Carregar um favicon na coleção de ativos do seu site</span><span class="sxs-lookup"><span data-stu-id="a4106-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="a4106-111">Para carregar um favicon na coleção de ativos do seu site, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4106-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="a4106-112">Vá para **Ativos \> Carregar \> Carregar ativos**.</span><span class="sxs-lookup"><span data-stu-id="a4106-112">Go to **Assets \> Upload \> Upload assets**.</span></span>
1. <span data-ttu-id="a4106-113">Localize e selecione o favicon no seu sistema de arquivos local.</span><span class="sxs-lookup"><span data-stu-id="a4106-113">Find and select the favicon on your local file system.</span></span>
1. <span data-ttu-id="a4106-114">Insira um título e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4106-114">Enter a title, and then select **OK**.</span></span> 
1. <span data-ttu-id="a4106-115">No painel de propriedades à direita, copie a URL pública do favicon.</span><span class="sxs-lookup"><span data-stu-id="a4106-115">In the property pane on the right, copy the public URL of the favicon.</span></span>

> [!NOTE]
> <span data-ttu-id="a4106-116">Se você não selecionar a opção **Publicar ativos após upload**, será preciso retornar à página **Ativos** e publicar manualmente o favicon depois.</span><span class="sxs-lookup"><span data-stu-id="a4106-116">If you don't select the **Publish assets after upload** option, you must return to **Assets** page and manually publish the favicon later.</span></span>

## <a name="create-the-html-for-the-favicon"></a><span data-ttu-id="a4106-117">Criar o HTML do favicon</span><span class="sxs-lookup"><span data-stu-id="a4106-117">Create the HTML for the favicon</span></span>

<span data-ttu-id="a4106-118">Para criar o HTML do favicon, use o seguinte trecho de código de HTML.</span><span class="sxs-lookup"><span data-stu-id="a4106-118">To create the HTML for the favicon, use the following HTML snippet.</span></span> <span data-ttu-id="a4106-119">No atributo **href**, substitua **"URL\_pública\_para\_seu\_favicon"** pela URL pública que você copiou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4106-119">For the **href** attribute, replace **"Public\_URL\_for\_your\_favicon"** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="add-the-html-for-the-favicon-to-the-head-element-of-your-pages"></a><span data-ttu-id="a4106-120">Adicione o HTML do favicon ao elemento \<head\> das suas páginas</span><span class="sxs-lookup"><span data-stu-id="a4106-120">Add the HTML for the favicon to the \<head\> element of your pages</span></span>

<span data-ttu-id="a4106-121">Para adicionar um favicon ao seu site, use o mesmo procedimento usado para adicionar qualquer tipo de HTML ou script ao elemento **\<head\>** das páginas do site.</span><span class="sxs-lookup"><span data-stu-id="a4106-121">To add a favicon to your site, use the same procedure that is used to add any type of HTML or script to the **\<head\>** element of your site pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a4106-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a4106-122">Additional resources</span></span>

[<span data-ttu-id="a4106-123">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="a4106-123">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="a4106-124">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="a4106-124">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="a4106-125">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="a4106-125">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="a4106-126">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="a4106-126">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="a4106-127">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="a4106-127">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="a4106-128">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="a4106-128">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="a4106-129">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="a4106-129">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

