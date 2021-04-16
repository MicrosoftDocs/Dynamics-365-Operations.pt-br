---
title: Adicionar um logotipo
description: Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: d9e1cba6bd07e0c3d9ed7d741d87e10837d8021c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797590"
---
# <a name="add-a-logo"></a><span data-ttu-id="5a7ce-103">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="5a7ce-103">Add a logo</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5a7ce-104">Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="5a7ce-105">Quando você cria seu site, uma das primeiras coisas que você provavelmente fará é adicionar o logotipo da empresa ou da marca ao cabeçalho do site.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-105">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="5a7ce-106">A biblioteca de módulos online do Dynamics 365 Commerce fornece um módulo que facilita essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-106">The Dynamics 365 Commerce online module library provides a module that makes this task easy.</span></span>

<span data-ttu-id="5a7ce-107">Você pode adicionar um logotipo diretamente a um modelo, layout ou página.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-107">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="5a7ce-108">Dessa forma, você pode alterar facilmente o logotipo que aparece em páginas ou grupos de páginas específicos.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-108">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="5a7ce-109">No entanto, este tópico cobre o cenário mais frequente, no qual você adiciona seu logotipo a um fragmento de cabeçalho que pode ser reutilizado em todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-109">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5a7ce-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5a7ce-110">Prerequisites</span></span>

<span data-ttu-id="5a7ce-111">Para poder adicionar um logotipo a todas as páginas do site, você deve executar estas tarefas.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-111">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="5a7ce-112">Carregue o logotipo na Biblioteca de Mídia.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-112">Upload your logo to the Media Library.</span></span>
1. <span data-ttu-id="5a7ce-113">Criar um fragmento de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-113">Create a header fragment.</span></span> <span data-ttu-id="5a7ce-114">Para obter mais informações sobre como criar e usar fragmentos, consulte [Trabalhar com fragmentos](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="5a7ce-114">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="5a7ce-115">Inclua o fragmento de cabeçalho no modelo usado pelas páginas do site para as opções de módulo e layout.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-115">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="5a7ce-116">Para obter mais informações sobre como modelos, consulte [Trabalhar com modelos](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5a7ce-116">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="5a7ce-117">Adicionar um logotipo a um fragmento de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="5a7ce-117">Add a logo to a header fragment</span></span>

<span data-ttu-id="5a7ce-118">Para adicionar um logotipo ao fragmento do cabeçalho ao site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-118">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="5a7ce-119">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-119">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="5a7ce-120">Selecione o fragmento de cabeçalho que você criou antes e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-120">Select the header fragment that you created, and then select **Edit**.</span></span>
1. <span data-ttu-id="5a7ce-121">Expanda o módulo de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-121">Expand the header module.</span></span>
1. <span data-ttu-id="5a7ce-122">No painel de propriedades do módulo de cabeçalho, forneça uma imagem e um link para o logotipo.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-122">In the property pane for the header module, provide an image and link for the logo.</span></span> 
1. <span data-ttu-id="5a7ce-123">Salve o fragmento de cabeçalho, termine de editá-lo e publique-o.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-123">Save the header fragment, finish editing it, and publish it.</span></span>

<span data-ttu-id="5a7ce-124">Depois de publicar o fragmento de cabeçalho atualizado, todas as páginas do site que usam o modelo que contém o fragmento do cabeçalho mostrarão seu logotipo.</span><span class="sxs-lookup"><span data-stu-id="5a7ce-124">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5a7ce-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5a7ce-125">Additional resources</span></span>

[<span data-ttu-id="5a7ce-126">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="5a7ce-126">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="5a7ce-127">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="5a7ce-127">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="5a7ce-128">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="5a7ce-128">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="5a7ce-129">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="5a7ce-129">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="5a7ce-130">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="5a7ce-130">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="5a7ce-131">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="5a7ce-131">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="5a7ce-132">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="5a7ce-132">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
