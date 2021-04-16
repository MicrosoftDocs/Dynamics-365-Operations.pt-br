---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797422"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="8c8ea-103">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="8c8ea-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8c8ea-104">Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="8c8ea-105">A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="8c8ea-106">Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="8c8ea-107">A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="8c8ea-108">As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="8c8ea-109">Criar um fragmento reutilizável para o seu código de script</span><span class="sxs-lookup"><span data-stu-id="8c8ea-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="8c8ea-110">Um fragmento permite reutilizar o código de script embutido ou externo em todas as páginas do site, independentemente do modelo usado.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="8c8ea-111">Criar um fragmento reutilizável para o seu código de script embutido</span><span class="sxs-lookup"><span data-stu-id="8c8ea-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="8c8ea-112">Para criar um fragmento reutilizável para o código de script embutido no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8c8ea-113">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8c8ea-114">Na caixa de diálogo **Novo fragmento**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8c8ea-115">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8c8ea-116">No fragmento criado, selecione o módulo **Script embutido padrão**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="8c8ea-117">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8c8ea-118">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8c8ea-119">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8c8ea-120">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="8c8ea-121">Criar um fragmento reutilizável para o seu código de script externo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="8c8ea-122">Para criar um fragmento reutilizável para o código de script externo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8c8ea-123">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8c8ea-124">Na caixa de diálogo **Novo fragmento**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8c8ea-125">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8c8ea-126">No fragmento criado, selecione o módulo **Script externo padrão**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="8c8ea-127">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8c8ea-128">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8c8ea-129">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8c8ea-130">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="8c8ea-131">Se a política de segurança de conteúdo (CSP) estiver habilitada para seu site, verifique se todas as URLs externas são adicionadas à diretiva **script-src** da CSP no construtor de sites do Commerce.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="8c8ea-132">Para obter mais informações, consulte [Gerenciar a Política de Segurança de Conteúdo (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8c8ea-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="8c8ea-133">Adicionar um fragmento que inclua código de script a um modelo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="8c8ea-134">Para adicionar um fragmento que inclua código de script a um modelo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8c8ea-135">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8c8ea-136">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8c8ea-137">No slot **Head do HTML**, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="8c8ea-138">Selecione o fragmento que você criou para o seu código de script.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="8c8ea-139">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8c8ea-140">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="8c8ea-141">Adicionar um script externo ou script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="8c8ea-142">Se você deseja inserir um script embutido ou externo diretamente em um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento primeiro.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="8c8ea-143">Adicionar um script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="8c8ea-144">Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8c8ea-145">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8c8ea-146">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8c8ea-147">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8c8ea-148">Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8c8ea-149">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8c8ea-150">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8c8ea-151">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8c8ea-152">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="8c8ea-153">Adicionar um script externo diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-153">Add an external script directly to a template</span></span>

<span data-ttu-id="8c8ea-154">Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8c8ea-155">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8c8ea-156">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8c8ea-157">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8c8ea-158">Na caixa de diálogo **Adicionar módulo**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8c8ea-159">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8c8ea-160">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8c8ea-161">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8c8ea-162">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="8c8ea-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c8ea-163">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8c8ea-163">Additional resources</span></span>

[<span data-ttu-id="8c8ea-164">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="8c8ea-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="8c8ea-165">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="8c8ea-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="8c8ea-166">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="8c8ea-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="8c8ea-167">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="8c8ea-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="8c8ea-168">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="8c8ea-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="8c8ea-169">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="8c8ea-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="8c8ea-170">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="8c8ea-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
