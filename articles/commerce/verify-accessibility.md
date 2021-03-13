---
title: Verificar acessibilidade do conteúdo da página
description: Este tópico descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7690f3bb17a56b9a16b6e818b675064b1979948e
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097356"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="3c5c7-103">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="3c5c7-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3c5c7-104">Este tópico descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3c5c7-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="3c5c7-105">Overview</span></span>

<span data-ttu-id="3c5c7-106">Quando tiver terminado de alterar uma página, verifique se o conteúdo está acessível a todos na Web.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="3c5c7-107">Nas ferramentas de criação do Commerce, você pode facilmente verificar a acessibilidade do conteúdo da página usando o serviço integrado [Insights de Acessibilidade da Microsoft](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="3c5c7-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="3c5c7-108">Este serviço verifica o conteúdo da página em relação às diretrizes de [Acessibilidade da World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility) mais recentes.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="3c5c7-109">A integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve ser ativada no nível de site ou locatário antes de você usá-la.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="3c5c7-110">Ative o Microsoft Accessibility Insights para todos os sites de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="3c5c7-111">Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para todos os sites do Commerce em seu locatário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="3c5c7-112">Para acessar as configurações de locatários, você deve fazer logon no Commerce como um administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="3c5c7-113">Faça logon no Commerce como um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="3c5c7-114">No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="3c5c7-115">Em **Configurações do Locatário**, selecione **Recursos**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="3c5c7-116">Defina a opção de **Verificação de Acessibilidade** como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="3c5c7-117">Ative o Microsoft Accessibility Insights para um único site</span><span class="sxs-lookup"><span data-stu-id="3c5c7-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="3c5c7-118">Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para um site único do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="3c5c7-119">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="3c5c7-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="3c5c7-120">No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="3c5c7-121">Em **Configurações de Site**, selecione **Recursos**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="3c5c7-122">Defina a opção de **Verificação de Acessibilidade** como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="3c5c7-123">Verifique a acessibilidade do conteúdo na home page</span><span class="sxs-lookup"><span data-stu-id="3c5c7-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="3c5c7-124">Para usar o serviço integrado do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para digitalizar e verificar o conteúdo de sua home page no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="3c5c7-125">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="3c5c7-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="3c5c7-126">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="3c5c7-127">Localize e selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="3c5c7-128">Na barra de comandos, selecione **Verificar acessibilidade**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="3c5c7-129">A página **Verificar Acessibilidade** é exibida.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="3c5c7-130">Depois que a digitalização for concluída, revise o conteúdo do relatório.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="3c5c7-131">Se houver falha nas verificações, selecione cada item de verificação com falha para expandi-lo, de forma que você possa exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="3c5c7-132">Para fechar o relatório depois de concluir a revisão, role até a parte inferior da página **Verificar acessibilidade** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c5c7-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3c5c7-133">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3c5c7-133">Additional resources</span></span>

[<span data-ttu-id="3c5c7-134">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="3c5c7-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="3c5c7-135">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="3c5c7-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="3c5c7-136">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="3c5c7-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="3c5c7-137">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="3c5c7-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="3c5c7-138">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="3c5c7-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="3c5c7-139">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="3c5c7-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="3c5c7-140">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="3c5c7-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="3c5c7-141">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="3c5c7-141">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)
