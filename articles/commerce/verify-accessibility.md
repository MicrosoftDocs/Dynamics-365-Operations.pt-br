---
title: Verificar acessibilidade do conteúdo da página
description: Este tópico descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 885696c13b0e5353e6dbd9dc21cf075d5e301786
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791622"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="a2413-103">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="a2413-103">Verify page content accessibility</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a2413-104">Este tópico descreve como verificar a acessibilidade do conteúdo da página no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a2413-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a2413-105">Quando tiver terminado de alterar uma página, verifique se o conteúdo está acessível a todos na Web.</span><span class="sxs-lookup"><span data-stu-id="a2413-105">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="a2413-106">Nas ferramentas de criação do Commerce, você pode facilmente verificar a acessibilidade do conteúdo da página usando o serviço integrado [Insights de Acessibilidade da Microsoft](https://accessibilityinsights.io/).</span><span class="sxs-lookup"><span data-stu-id="a2413-106">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="a2413-107">Este serviço verifica o conteúdo da página em relação às diretrizes de [Acessibilidade da World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility) mais recentes.</span><span class="sxs-lookup"><span data-stu-id="a2413-107">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="a2413-108">A integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) deve ser ativada no nível de site ou locatário antes de você usá-la.</span><span class="sxs-lookup"><span data-stu-id="a2413-108">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="a2413-109">Ative o Microsoft Accessibility Insights para todos os sites de seu locatário.</span><span class="sxs-lookup"><span data-stu-id="a2413-109">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="a2413-110">Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para todos os sites do Commerce em seu locatário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a2413-110">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="a2413-111">Para acessar as configurações de locatários, você deve fazer logon no Commerce como um administrador de sistema.</span><span class="sxs-lookup"><span data-stu-id="a2413-111">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="a2413-112">Faça logon no Commerce como um administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="a2413-112">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="a2413-113">No painel de navegação esquerdo, selecione **Configurações do Locatário** (próximo ao símbolo de engrenagem) para expandi-las.</span><span class="sxs-lookup"><span data-stu-id="a2413-113">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="a2413-114">Em **Configurações do Locatário**, selecione **Recursos**.</span><span class="sxs-lookup"><span data-stu-id="a2413-114">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="a2413-115">Defina a opção de **Verificação de Acessibilidade** como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a2413-115">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="a2413-116">Ative o Microsoft Accessibility Insights para um único site</span><span class="sxs-lookup"><span data-stu-id="a2413-116">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="a2413-117">Para ativar a integração do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para um site único do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a2413-117">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="a2413-118">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="a2413-118">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a2413-119">No painel de navegação esquerdo, selecione **Configurações de Site** para expandi-lo.</span><span class="sxs-lookup"><span data-stu-id="a2413-119">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="a2413-120">Em **Configurações de Site**, selecione **Recursos**.</span><span class="sxs-lookup"><span data-stu-id="a2413-120">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="a2413-121">Defina a opção de **Verificação de Acessibilidade** como **Ativada**.</span><span class="sxs-lookup"><span data-stu-id="a2413-121">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="a2413-122">Verifique a acessibilidade do conteúdo na home page</span><span class="sxs-lookup"><span data-stu-id="a2413-122">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="a2413-123">Para usar o serviço integrado do [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para digitalizar e verificar o conteúdo de sua home page no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a2413-123">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="a2413-124">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="a2413-124">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="a2413-125">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="a2413-125">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="a2413-126">Localize e selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="a2413-126">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="a2413-127">Na barra de comandos, selecione **Verificar acessibilidade**.</span><span class="sxs-lookup"><span data-stu-id="a2413-127">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="a2413-128">A página **Verificar Acessibilidade** é exibida.</span><span class="sxs-lookup"><span data-stu-id="a2413-128">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="a2413-129">Depois que a digitalização for concluída, revise o conteúdo do relatório.</span><span class="sxs-lookup"><span data-stu-id="a2413-129">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="a2413-130">Se houver falha nas verificações, selecione cada item de verificação com falha para expandi-lo, de forma que você possa exibir mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a2413-130">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="a2413-131">Para fechar o relatório depois de concluir a revisão, role até a parte inferior da página **Verificar acessibilidade** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a2413-131">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2413-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a2413-132">Additional resources</span></span>

[<span data-ttu-id="a2413-133">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="a2413-133">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="a2413-134">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="a2413-134">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="a2413-135">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="a2413-135">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="a2413-136">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="a2413-136">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="a2413-137">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="a2413-137">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="a2413-138">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="a2413-138">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="a2413-139">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="a2413-139">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="a2413-140">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="a2413-140">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
