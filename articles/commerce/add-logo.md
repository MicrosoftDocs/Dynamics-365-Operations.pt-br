---
title: Adicionar um logotipo
description: Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23bac9aae6beb59912bbc9e1f2c6958c007550b0
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914607"
---
# <a name="add-a-logo"></a><span data-ttu-id="e6c6d-103">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="e6c6d-103">Add a logo</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e6c6d-104">Este tópico descreve como adicionar um logotipo ao seu site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-104">This topic describes how to add a logo to your site in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="e6c6d-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e6c6d-105">Overview</span></span>

<span data-ttu-id="e6c6d-106">Quando você cria seu site, uma das primeiras coisas que você provavelmente fará é adicionar o logotipo da empresa ou da marca ao cabeçalho do site.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-106">When you build your site, one of the first things that you will probably do is add your company or brand logo to the site's header.</span></span> <span data-ttu-id="e6c6d-107">O kit de início do Dynamics 365 Commerce online fornece um módulo que facilita essa tarefa.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-107">The Dynamics 365 Commerce online starter kit provides a module that makes this task easy.</span></span>

<span data-ttu-id="e6c6d-108">Você pode adicionar um logotipo diretamente a um modelo, layout ou página.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-108">You can add a logo directly to a template, layout, or page.</span></span> <span data-ttu-id="e6c6d-109">Dessa forma, você pode alterar facilmente o logotipo que aparece em páginas ou grupos de páginas específicos.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-109">In this way, you can easily change the logo that appears on specific pages or groups of pages.</span></span> <span data-ttu-id="e6c6d-110">No entanto, este tópico cobre o cenário mais frequente, no qual você adiciona seu logotipo a um fragmento de cabeçalho que pode ser reutilizado em todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-110">However, this topic covers the most frequent scenario, where you add your logo to a header fragment that can be reused across all the pages of your site.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6c6d-111">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e6c6d-111">Prerequisites</span></span>

<span data-ttu-id="e6c6d-112">Para poder adicionar um logotipo a todas as páginas do site, você deve executar estas tarefas.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-112">Before you can add a logo to all the pages of your site, you must complete these tasks.</span></span>

1. <span data-ttu-id="e6c6d-113">Carregue seu logotipo no Gerenciador de ativos digitais, que pode ser acessado na página **Ativos**.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-113">Upload your logo to the digital assets manager, which you can access from the **Assets** page.</span></span>
1. <span data-ttu-id="e6c6d-114">Criar um fragmento de cabeçalho.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-114">Create a header fragment.</span></span> <span data-ttu-id="e6c6d-115">Para obter mais informações sobre como criar e usar fragmentos, consulte [Trabalhar com fragmentos](work-with-fragments.md).</span><span class="sxs-lookup"><span data-stu-id="e6c6d-115">For more information about how to create and use fragments, see [Work with fragments](work-with-fragments.md).</span></span>
1. <span data-ttu-id="e6c6d-116">Inclua o fragmento de cabeçalho no modelo usado pelas páginas do site para as opções de módulo e layout.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-116">Include the header fragment in the template that the pages of your site use for their layout and module options.</span></span> <span data-ttu-id="e6c6d-117">Para obter mais informações sobre como modelos, consulte [Trabalhar com modelos](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e6c6d-117">For more information about templates, see [Work with templates](work-with-templates.md).</span></span>

## <a name="add-a-logo-to-a-header-fragment"></a><span data-ttu-id="e6c6d-118">Adicionar um logotipo a um fragmento de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="e6c6d-118">Add a logo to a header fragment</span></span>

<span data-ttu-id="e6c6d-119">Para adicionar um logotipo ao fragmento do cabeçalho ao site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-119">To add a logo to the header fragment for your site, follow these steps.</span></span>

1. <span data-ttu-id="e6c6d-120">No painel de navegação à esquerda, selecione **Fragmentos** e, em seguida, selecione o fragmento de cabeçalho criado.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-120">In the navigation pane on the left, select **Fragments**, and then select the header fragment that you created.</span></span>
2. <span data-ttu-id="e6c6d-121">Selecione **Fazer Check-Out**.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-121">Select **Check out**.</span></span>
3. <span data-ttu-id="e6c6d-122">Expanda o slot de **Cabeçalho** e o slot de **Logotipo**.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-122">Expand the **Header** slot and the **Logo** slot.</span></span>
4. <span data-ttu-id="e6c6d-123">Selecione o botão de reticências (**...**) para o slot **Logotipo** e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-123">Select the ellipsis button (**...**) for the **Logo** slot, and then select **Add module**.</span></span>
5. <span data-ttu-id="e6c6d-124">Selecione o módulo do logotipo.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-124">Select the logo module.</span></span>
6. <span data-ttu-id="e6c6d-125">No painel de propriedades à direita, configure o módulo do logotipo para que ele mostre seu logotipo.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-125">In the properties pane on the right, configure the logo module so that it shows your logo.</span></span>
7. <span data-ttu-id="e6c6d-126">Salve o fragmento do cabeçalho, insira-o e publique-o.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-126">Save the header fragment, check it in, and publish it.</span></span>

<span data-ttu-id="e6c6d-127">Depois de publicar o fragmento de cabeçalho atualizado, todas as páginas do site que usam o modelo que contém o fragmento do cabeçalho mostrarão seu logotipo.</span><span class="sxs-lookup"><span data-stu-id="e6c6d-127">After you publish the updated header fragment, all site pages that use the template that contains the header fragment will show your logo.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6c6d-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e6c6d-128">Additional resources</span></span>

[<span data-ttu-id="e6c6d-129">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="e6c6d-129">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e6c6d-130">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="e6c6d-130">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e6c6d-131">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="e6c6d-131">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e6c6d-132">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="e6c6d-132">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e6c6d-133">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="e6c6d-133">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e6c6d-134">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="e6c6d-134">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="e6c6d-135">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="e6c6d-135">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

