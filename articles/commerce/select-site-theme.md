---
title: Selecionar um tema de site
description: Este tópico descreve como configurar ou alterar um tema do site no Microsoft Dynamics 365 Commerce.
author: bicyclingfool
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: e3f7f38a0b4b1e0be85d619a1c133d1555706d93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254712"
---
# <a name="select-a-site-theme"></a><span data-ttu-id="49921-103">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="49921-103">Select a site theme</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="49921-104">Este tópico descreve como configurar ou alterar um tema do site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49921-104">This topic describes how to set or change your site's theme in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="49921-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="49921-105">Overview</span></span>

<span data-ttu-id="49921-106">O layout e o estilo de um site (por exemplo, fontes, tamanhos e cores) são definidos pelo tema que você seleciona e aplica ao site.</span><span class="sxs-lookup"><span data-stu-id="49921-106">A site's layout and style (for example, fonts, sizes, and colors) are defined by the theme that you select and apply to the site.</span></span> <span data-ttu-id="49921-107">Um tema é criado e implantado por um desenvolvedor em sua empresa.</span><span class="sxs-lookup"><span data-stu-id="49921-107">A theme is created and deployed by a developer at your company.</span></span> <span data-ttu-id="49921-108">Para obter uma visão geral dos temas, consulte [Visão geral de Temas](e-commerce-extensibility/theming.md).</span><span class="sxs-lookup"><span data-stu-id="49921-108">For an overview of themes, see [Theming overview](e-commerce-extensibility/theming.md).</span></span> <span data-ttu-id="49921-109">Para obter mais informações sobre como criar e implantar os temas, consulte [Criar um novo tema](e-commerce-extensibility/create-theme.md).</span><span class="sxs-lookup"><span data-stu-id="49921-109">For more information about how to create and deploy themes, see [Create a new theme](e-commerce-extensibility/create-theme.md).</span></span>

<span data-ttu-id="49921-110">Por padrão, quando você cria um site pela primeira vez, ele usa um tema chamado **Fabrikam**.</span><span class="sxs-lookup"><span data-stu-id="49921-110">By default, when you first create a site, it uses a theme that is named **Fabrikam**.</span></span> <span data-ttu-id="49921-111">Este tema padrão é fornecido como parte da biblioteca de módulos do Comércio.</span><span class="sxs-lookup"><span data-stu-id="49921-111">This default theme is provided as part of the Commerce module library.</span></span> <span data-ttu-id="49921-112">Depois que tiver implantado temas adicionais para seu site, você pode configurar o site de forma que use um deles.</span><span class="sxs-lookup"><span data-stu-id="49921-112">After you've deployed additional themes for your site, you can configure the site so that it uses one of them instead.</span></span>

## <a name="select-the-site-theme"></a><span data-ttu-id="49921-113">Selecione o tema do site</span><span class="sxs-lookup"><span data-stu-id="49921-113">Select the site theme</span></span>

<span data-ttu-id="49921-114">Para selecionar o tema que é aplicado ao seu site, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="49921-114">To select the theme that is applied to your site, follow these steps.</span></span>

1. <span data-ttu-id="49921-115">No ambiente de criação do site, vá para seu site.</span><span class="sxs-lookup"><span data-stu-id="49921-115">In the site authoring environment, go to your site.</span></span>
1. <span data-ttu-id="49921-116">Vá para **Gerenciamento de Sites** \> **Extensibilidade**.</span><span class="sxs-lookup"><span data-stu-id="49921-116">Go to **Site Management** \> **Extensibility**.</span></span>
1. <span data-ttu-id="49921-117">Em **Tema**, selecione um tema no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="49921-117">Under **Theme**, select a theme on the drop-down menu.</span></span>
1. <span data-ttu-id="49921-118">Para aplicar o tema selecionado ao site, selecione **Salve e publicar**.</span><span class="sxs-lookup"><span data-stu-id="49921-118">To apply the selected theme to your site, select **Save and publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="49921-119">O tema selecionado é publicado em seu site assim que você seleciona **Salvar e publicar** na página **Extensibilidade**.</span><span class="sxs-lookup"><span data-stu-id="49921-119">The theme that you select is published to your site as soon as you select **Save and publish** on the **Extensibility** page.</span></span> <span data-ttu-id="49921-120">Para visualizar um tema em seu site antes de aplicá-lo, você pode usar seu desenvolvimento ou ambiente da sandbox.</span><span class="sxs-lookup"><span data-stu-id="49921-120">To preview a theme on your site before you apply it, you can use your development or sandbox environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49921-121">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="49921-121">Additional resources</span></span>

[<span data-ttu-id="49921-122">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="49921-122">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="49921-123">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="49921-123">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="49921-124">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="49921-124">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="49921-125">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="49921-125">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="49921-126">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="49921-126">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="49921-127">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="49921-127">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="49921-128">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="49921-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="49921-129">Visão geral de temas</span><span class="sxs-lookup"><span data-stu-id="49921-129">Theming overview</span></span>](e-commerce-extensibility/theming.md)

[<span data-ttu-id="49921-130">Criar um tema</span><span class="sxs-lookup"><span data-stu-id="49921-130">Create a new theme</span></span>](e-commerce-extensibility/create-theme.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]