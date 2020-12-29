---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
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
ms.openlocfilehash: e15ba6a0d624bd97c25936aa6d3bfafb844b66c0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410132"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="3e5bc-103">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="3e5bc-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e5bc-104">Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="3e5bc-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="3e5bc-105">Overview</span></span>

<span data-ttu-id="3e5bc-106">A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="3e5bc-107">Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="3e5bc-108">A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="3e5bc-109">As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="3e5bc-110">Criar um fragmento reutilizável para o seu código de script</span><span class="sxs-lookup"><span data-stu-id="3e5bc-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="3e5bc-111">Um fragmento permite reutilizar o código de script embutido ou externo em todas as páginas do site, independentemente do modelo usado.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="3e5bc-112">Criar um fragmento reutilizável para o seu código de script embutido</span><span class="sxs-lookup"><span data-stu-id="3e5bc-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="3e5bc-113">Para criar um fragmento reutilizável para o código de script embutido no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e5bc-114">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="3e5bc-115">Na caixa de diálogo **Novo fragmento**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="3e5bc-116">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5bc-117">No fragmento criado, selecione o módulo **Script embutido padrão**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="3e5bc-118">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="3e5bc-119">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e5bc-120">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e5bc-121">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="3e5bc-122">Criar um fragmento reutilizável para o seu código de script externo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="3e5bc-123">Para criar um fragmento reutilizável para o código de script externo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e5bc-124">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="3e5bc-125">Na caixa de diálogo **Novo fragmento**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="3e5bc-126">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="3e5bc-127">No fragmento criado, selecione o módulo **Script externo padrão**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="3e5bc-128">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="3e5bc-129">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e5bc-130">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e5bc-131">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="3e5bc-132">Se a política de segurança de conteúdo (CSP) estiver habilitada para seu site, verifique se todas as URLs externas são adicionadas à diretiva **script-src** da CSP no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="3e5bc-133">Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="3e5bc-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="3e5bc-134">Adicionar um fragmento que inclua código de script a um modelo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="3e5bc-135">Para adicionar um fragmento que inclua código de script a um modelo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e5bc-136">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e5bc-137">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e5bc-138">No slot **Head do HTML**, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="3e5bc-139">Selecione o fragmento que você criou para o seu código de script.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="3e5bc-140">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e5bc-141">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="3e5bc-142">Adicionar um script externo ou script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="3e5bc-143">Se você deseja inserir um script embutido ou externo diretamente em um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento primeiro.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="3e5bc-144">Adicionar um script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="3e5bc-145">Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e5bc-146">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e5bc-147">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e5bc-148">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e5bc-149">Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="3e5bc-150">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="3e5bc-151">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e5bc-152">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e5bc-153">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="3e5bc-154">Adicionar um script externo diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-154">Add an external script directly to a template</span></span>

<span data-ttu-id="3e5bc-155">Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="3e5bc-156">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="3e5bc-157">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="3e5bc-158">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="3e5bc-159">Na caixa de diálogo **Adicionar módulo**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="3e5bc-160">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="3e5bc-161">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="3e5bc-162">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="3e5bc-163">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="3e5bc-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3e5bc-164">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3e5bc-164">Additional resources</span></span>

[<span data-ttu-id="3e5bc-165">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="3e5bc-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="3e5bc-166">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="3e5bc-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="3e5bc-167">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="3e5bc-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="3e5bc-168">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="3e5bc-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="3e5bc-169">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="3e5bc-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="3e5bc-170">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="3e5bc-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="3e5bc-171">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="3e5bc-171">Add languages to your site</span></span>](add-languages-to-site.md)
