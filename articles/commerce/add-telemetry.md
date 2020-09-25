---
title: Adicionar o código de script a páginas do site para oferecer suporte à telemetria
description: Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761240"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="7b8c4-103">Adicionar o código de script a páginas do site para oferecer suporte à telemetria</span><span class="sxs-lookup"><span data-stu-id="7b8c4-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7b8c4-104">Este tópico descreve como adicionar código de script do cliente às páginas do site para oferecer suporte à coleção de telemetria do cliente.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="7b8c4-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7b8c4-105">Overview</span></span>

<span data-ttu-id="7b8c4-106">A análise da Web é uma ferramenta essencial quando você deseja entender como seus clientes interagem com seu site e tomar decisões que ajudarão a otimizar a experiência para obter a conversão máxima.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="7b8c4-107">Muitos pacotes de análise da Web estão disponíveis para ajudar você a atingir esses objetivos, como Google Analytics, Clicky, Moz Analytics e KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="7b8c4-108">A maioria dos pacotes de análise da Web exige que você adicione o código de script do cliente no elemento **\<head\>** do HTML para todas as páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="7b8c4-109">As instruções neste tópico também se aplicam a outras funcionalidades personalizadas do cliente que o Microsoft Dynamics 365 Commerce não oferece nativamente.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="7b8c4-110">Criar um fragmento reutilizável para o seu código de script</span><span class="sxs-lookup"><span data-stu-id="7b8c4-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="7b8c4-111">Um fragmento permite reutilizar o código de script embutido ou externo em todas as páginas do site, independentemente do modelo usado.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="7b8c4-112">Criar um fragmento reutilizável para o seu código de script embutido</span><span class="sxs-lookup"><span data-stu-id="7b8c4-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="7b8c4-113">Para criar um fragmento reutilizável para o código de script embutido no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b8c4-114">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="7b8c4-115">Na caixa de diálogo **Novo fragmento**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="7b8c4-116">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="7b8c4-117">No fragmento criado, selecione o módulo **Script embutido padrão**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="7b8c4-118">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="7b8c4-119">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="7b8c4-120">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7b8c4-121">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="7b8c4-122">Criar um fragmento reutilizável para o seu código de script externo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="7b8c4-123">Para criar um fragmento reutilizável para o código de script externo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b8c4-124">Vá para **Fragmentos** e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="7b8c4-125">Na caixa de diálogo **Novo fragmento**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="7b8c4-126">Em **Nome do fragmento**, digite um nome para o fragmento e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="7b8c4-127">No fragmento criado, selecione o módulo **Script externo padrão**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="7b8c4-128">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="7b8c4-129">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="7b8c4-130">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7b8c4-131">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="7b8c4-132">Adicionar um fragmento que inclua código de script a um modelo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="7b8c4-133">Para adicionar um fragmento que inclua código de script a um modelo no construtor de sites, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b8c4-134">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="7b8c4-135">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="7b8c4-136">No slot **Head do HTML**, selecione o botão de reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="7b8c4-137">Selecione o fragmento que você criou para o seu código de script.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="7b8c4-138">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7b8c4-139">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="7b8c4-140">Adicionar um script externo ou script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="7b8c4-141">Se você deseja inserir um script embutido ou externo diretamente em um conjunto de páginas controlado por um único modelo, não é necessário criar um fragmento primeiro.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="7b8c4-142">Adicionar um script embutido diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="7b8c4-143">Para adicionar um script embutido diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b8c4-144">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="7b8c4-145">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="7b8c4-146">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7b8c4-147">Na caixa de diálogo **Adicionar módulo**, selecione **Script embutido**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="7b8c4-148">No painel de propriedades, no lado direito, em **Script embutido**, insira o script de cliente.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="7b8c4-149">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="7b8c4-150">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7b8c4-151">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="7b8c4-152">Adicionar um script externo diretamente a um modelo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-152">Add an external script directly to a template</span></span>

<span data-ttu-id="7b8c4-153">Para adicionar um script externo diretamente a um modelo no site Builder, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="7b8c4-154">Vá para **Modelos** e abra o modelo para as páginas às quais você deseja adicionar seu código de script.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="7b8c4-155">No painel esquerdo, expanda a hierarquia do modelo para mostrar o slot **Head do HTML**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="7b8c4-156">No slot **Head do HTML**, selecione o botão de reticências (**...**) e depois selecione **Adicionar módulo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="7b8c4-157">Na caixa de diálogo **Adicionar módulo**, selecione **Script externo**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="7b8c4-158">No painel de propriedades no lado direito, em **Origem do script**, adicione um URL externo ou relativo para a origem de script externa.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="7b8c4-159">Em seguida, configure outras opções conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="7b8c4-160">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="7b8c4-161">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="7b8c4-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b8c4-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7b8c4-162">Additional resources</span></span>

[<span data-ttu-id="7b8c4-163">Adicionar um logotipo</span><span class="sxs-lookup"><span data-stu-id="7b8c4-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="7b8c4-164">Selecionar um tema de site</span><span class="sxs-lookup"><span data-stu-id="7b8c4-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="7b8c4-165">Trabalhar com arquivos de substituição CSS</span><span class="sxs-lookup"><span data-stu-id="7b8c4-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="7b8c4-166">Adicionar um favicon</span><span class="sxs-lookup"><span data-stu-id="7b8c4-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="7b8c4-167">Adicionar uma mensagem de boas-vindas</span><span class="sxs-lookup"><span data-stu-id="7b8c4-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="7b8c4-168">Adicionar um aviso de direitos autorais</span><span class="sxs-lookup"><span data-stu-id="7b8c4-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="7b8c4-169">Adicionar idiomas ao seu site</span><span class="sxs-lookup"><span data-stu-id="7b8c4-169">Add languages to your site</span></span>](add-languages-to-site.md)
