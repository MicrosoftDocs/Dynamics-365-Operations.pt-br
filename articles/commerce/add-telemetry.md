---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 03/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4f26ed5b6674566f579e801f4b7be63c2d0dc38d
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686805"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="e6d74-103">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="e6d74-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e6d74-104">Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.</span><span class="sxs-lookup"><span data-stu-id="e6d74-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="e6d74-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="e6d74-105">Overview</span></span>

<span data-ttu-id="e6d74-106">A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima.</span><span class="sxs-lookup"><span data-stu-id="e6d74-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="e6d74-107">Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="e6d74-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="e6d74-108">A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="e6d74-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="e6d74-109">As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.</span><span class="sxs-lookup"><span data-stu-id="e6d74-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-page-fragment-for-your-script-code"></a><span data-ttu-id="e6d74-110">Criar um fragmento de página reutilizável para o seu código de script</span><span class="sxs-lookup"><span data-stu-id="e6d74-110">Create a reusable page fragment for your script code</span></span>

<span data-ttu-id="e6d74-111">Um fragmento de página permite reutilizar o código de script interno ou externo em todas as páginas do site, independentemente do modelo usado.</span><span class="sxs-lookup"><span data-stu-id="e6d74-111">A page fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-inline-script-code"></a><span data-ttu-id="e6d74-112">Criar um fragmento de página reutilizável para o seu código de script embutido</span><span class="sxs-lookup"><span data-stu-id="e6d74-112">Create a reusable page fragment for your inline script code</span></span>

<span data-ttu-id="e6d74-113">Para criar um fragmento de página reutilizável para o código de script embutido no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6d74-113">To create a reusable page fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6d74-114">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e6d74-115">Na caixa de diálogo **Novo fragmento de página**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-115">In the **New page fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e6d74-116">Em **Nome do fragmento de página**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-116">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e6d74-117">No fragmento de página criado, selecione o módulo de **Script embutido padrão**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-117">Under the page fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="e6d74-118">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6d74-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e6d74-119">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e6d74-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e6d74-120">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e6d74-121">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-page-fragment-for-your-external-script-code"></a><span data-ttu-id="e6d74-122">Criar um fragmento de página reutilizável para o seu código de script externo</span><span class="sxs-lookup"><span data-stu-id="e6d74-122">Create a reusable page fragment for your external script code</span></span>

<span data-ttu-id="e6d74-123">Para criar um fragmento de página reutilizável para o código de script externo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6d74-123">To create a reusable page fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6d74-124">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="e6d74-125">Na caixa de diálogo **Novo fragmento de página**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-125">In the **New page fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e6d74-126">Em **Nome do fragmento de página**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-126">Under **Page fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="e6d74-127">No fragmento de página criado, selecione o módulo de **Script externo padrão**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-127">Under the page fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="e6d74-128">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="e6d74-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e6d74-129">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e6d74-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e6d74-130">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e6d74-131">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-131">Select **Publish**.</span></span>

## <a name="add-a-page-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="e6d74-132">Adicionar um fragmento de página que inclua código de script a um modelo</span><span class="sxs-lookup"><span data-stu-id="e6d74-132">Add a page fragment that includes script code to a template</span></span>

<span data-ttu-id="e6d74-133">Para adicionar um fragmento de página que inclua código de script a um modelo no site builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6d74-133">To add a page fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6d74-134">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="e6d74-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e6d74-135">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e6d74-136">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Page Fragment**.</span></span>
1. <span data-ttu-id="e6d74-137">Selecione o fragmento que você criou para o seu código de script.</span><span class="sxs-lookup"><span data-stu-id="e6d74-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="e6d74-138">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e6d74-139">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="e6d74-140">Adicionar um script externo ou script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="e6d74-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="e6d74-141">Se você deseja inserir um script embutido ou externo diretamente a um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento de página primeiro.</span><span class="sxs-lookup"><span data-stu-id="e6d74-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a page fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="e6d74-142">Adicionar um script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="e6d74-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="e6d74-143">Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6d74-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6d74-144">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="e6d74-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e6d74-145">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e6d74-146">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e6d74-147">Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="e6d74-148">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6d74-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="e6d74-149">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e6d74-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e6d74-150">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e6d74-151">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="e6d74-152">Adicionar um script externo diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="e6d74-152">Add an external script directly to a template</span></span>

<span data-ttu-id="e6d74-153">Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e6d74-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e6d74-154">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="e6d74-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="e6d74-155">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="e6d74-156">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e6d74-157">Na caixa de diálogo **Adicionar módulo**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="e6d74-158">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="e6d74-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="e6d74-159">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e6d74-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="e6d74-160">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="e6d74-161">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e6d74-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6d74-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e6d74-162">Additional resources</span></span>

[<span data-ttu-id="e6d74-163">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="e6d74-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="e6d74-164">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="e6d74-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="e6d74-165">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="e6d74-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="e6d74-166">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="e6d74-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="e6d74-167">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="e6d74-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="e6d74-168">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="e6d74-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="e6d74-169">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="e6d74-169">Add languages to your site</span></span>](add-languages-to-site.md)
