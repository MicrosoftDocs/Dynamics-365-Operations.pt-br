---
title: Modificar uma página de site existente
description: Este tópico descreve como modificar uma página do site existente no Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6afd19a01520813e54871f4849aeb18f4424173c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223038"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="4beee-103">Modificar uma página de site existente</span><span class="sxs-lookup"><span data-stu-id="4beee-103">Modify an existing site page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="4beee-104">Este tópico descreve como modificar uma página do site existente no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4beee-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4beee-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="4beee-105">Overview</span></span>

<span data-ttu-id="4beee-106">Quando tiver que modificar uma página, a primeira etapa é abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="4beee-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="4beee-107">Vá para o site que contém sua página e, em seguida, na lista de páginas, localize a página que você deseja.</span><span class="sxs-lookup"><span data-stu-id="4beee-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="4beee-108">Se você não conseguir encontrar a página, use a funcionalidade de pesquisa sofisticada da ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="4beee-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="4beee-109">Digite o nome exato da página, ou digite as primeiras letras dela e um asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="4beee-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="4beee-110">Uma lista filtrada de páginas é exibida.</span><span class="sxs-lookup"><span data-stu-id="4beee-110">A filtered list of pages appears.</span></span> <span data-ttu-id="4beee-111">Você pode usar essa lista para localizar a página que deseja.</span><span class="sxs-lookup"><span data-stu-id="4beee-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="4beee-112">Depois que você encontrar a página correta, selecione o nome da página para abrir a página no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="4beee-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="4beee-113">Se sua página estiver visível no inspetor de páginas, você pode selecionar **Editar** e verificar a página antes de abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="4beee-113">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="4beee-114">Dessa forma, você pode fazer check-out de várias páginas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4beee-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="4beee-115">Depois que a página for aberta no editor de páginas, você deve garantir que fez check-out da página.</span><span class="sxs-lookup"><span data-stu-id="4beee-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="4beee-116">A barra de comandos na ferramenta de criação é dinâmica, contextual e sensível ao estado.</span><span class="sxs-lookup"><span data-stu-id="4beee-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="4beee-117">Portanto, ela mostra somente as ações que você pode executar atualmente na página.</span><span class="sxs-lookup"><span data-stu-id="4beee-117">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="4beee-118">Por exemplo, se você não fez check-out da página, os botões **Salvar** e **Terminar edição** não aparecerão na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="4beee-118">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="4beee-119">O estado da página também é mostrado no lado direito da janela.</span><span class="sxs-lookup"><span data-stu-id="4beee-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="4beee-120">Se ainda não foi feito o check-out da página, selecione **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="4beee-120">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="4beee-121">A barra de comandos é alterada para refletir o novo estado da página.</span><span class="sxs-lookup"><span data-stu-id="4beee-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="4beee-122">Você também recebe uma notificação informando que a página foi submetida a check-out por você.</span><span class="sxs-lookup"><span data-stu-id="4beee-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="4beee-123">A próxima etapa é fazer suas alterações reais.</span><span class="sxs-lookup"><span data-stu-id="4beee-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="4beee-124">Geralmente, você usa a árvore em destaque da página à esquerda para localizar e selecionar o módulo que deseja alterar e, em seguida, fazer alterações no painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="4beee-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="4beee-125">Entretanto, sua alteração pode, às vezes, envolver a adição ou remoção de modelos ou fragmentos.</span><span class="sxs-lookup"><span data-stu-id="4beee-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="4beee-126">Para adicionar um fragmento ou módulo, use a árvore de destaque da página para localizar o slot no qual você deseja adicionar o módulo ou fragmento e, em seguida, selecione o botão de reticências (**...**) desse slot.</span><span class="sxs-lookup"><span data-stu-id="4beee-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="4beee-127">É exibido um menu que tem comandos para adicionar um módulo ou fragmento.</span><span class="sxs-lookup"><span data-stu-id="4beee-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="4beee-128">Para remover um módulo ou fragmento, localize e selecione-o na árvore de destaque da página, selecione o botão de reticências e o comando para excluir o módulo ou o fragmento.</span><span class="sxs-lookup"><span data-stu-id="4beee-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="4beee-129">Você também pode exibir e editar as propriedades de qualquer módulo que esteja visível na visualização do construtor de página visual, selecionando-o diretamente.</span><span class="sxs-lookup"><span data-stu-id="4beee-129">You can also view and edit the properties for any module that is visible in the visual page builder preview by selecting it directly.</span></span>

<span data-ttu-id="4beee-130">Depois que terminar de fazer as alterações e visualizar seu efeito, você deve fazer check-in da página, selecionando **Terminar edição** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="4beee-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="4beee-131">Para publicar suas alterações imediatamente, selecione **Publicar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="4beee-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="4beee-132">A versão da página mais recente submetida a check-in modificada é publicada e fica disponível para usuários externos que exibem seu site.</span><span class="sxs-lookup"><span data-stu-id="4beee-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="4beee-133">Exemplo: Alterar o vídeo na home page</span><span class="sxs-lookup"><span data-stu-id="4beee-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="4beee-134">O exemplo a seguir mostra como modificar a home page alterando o vídeo que aparece no módulo do player de vídeo.</span><span class="sxs-lookup"><span data-stu-id="4beee-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="4beee-135">Em **Sites**, selecione **Fabrikam** (ou o nome do seu site).</span><span class="sxs-lookup"><span data-stu-id="4beee-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="4beee-136">No painel de navegação à esquerda, selecione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="4beee-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="4beee-137">Localize e selecione a home page para abri-la no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="4beee-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="4beee-138">Na barra de comandos, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="4beee-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="4beee-139">No destaque da página, selecione o slot **Principal**.</span><span class="sxs-lookup"><span data-stu-id="4beee-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="4beee-140">No slot **Principal** , expanda os módulos de contêiner fluidos.</span><span class="sxs-lookup"><span data-stu-id="4beee-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="4beee-141">Localize e selecione o módulo de player do vídeo.</span><span class="sxs-lookup"><span data-stu-id="4beee-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="4beee-142">No painel de propriedade no lado direito, selecione a propriedade **vídeo**.</span><span class="sxs-lookup"><span data-stu-id="4beee-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="4beee-143">O seletor de ativos é exibido.</span><span class="sxs-lookup"><span data-stu-id="4beee-143">The asset picker appears.</span></span>
1. <span data-ttu-id="4beee-144">No seletor de ativos, selecione um ativo de vídeo disponível ou selecione **Carregar novo ativo** para carregar um novo ativo do vídeo.</span><span class="sxs-lookup"><span data-stu-id="4beee-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="4beee-145">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4beee-145">Select **OK**.</span></span>
1. <span data-ttu-id="4beee-146">Selecione **Salvar** e **Finalizar edição**.</span><span class="sxs-lookup"><span data-stu-id="4beee-146">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="4beee-147">No campo **Comentários**, insira **Alterou o vídeo** e depois selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4beee-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="4beee-148">Selecione **Visualizar** para visualizar a página atualizada.</span><span class="sxs-lookup"><span data-stu-id="4beee-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="4beee-149">Quando terminar, feche a guia de visualização para retornar à ferramenta de criação.</span><span class="sxs-lookup"><span data-stu-id="4beee-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="4beee-150">Selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="4beee-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4beee-151">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4beee-151">Additional resources</span></span>

[<span data-ttu-id="4beee-152">Adicionar uma nova página do site</span><span class="sxs-lookup"><span data-stu-id="4beee-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="4beee-153">Selecionar layouts de página</span><span class="sxs-lookup"><span data-stu-id="4beee-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="4beee-154">Gerenciar metadados de SEO</span><span class="sxs-lookup"><span data-stu-id="4beee-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="4beee-155">Salvar, visualizar, e publicar uma página</span><span class="sxs-lookup"><span data-stu-id="4beee-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="4beee-156">Enriquecer uma página de produto</span><span class="sxs-lookup"><span data-stu-id="4beee-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="4beee-157">Enriquecer uma página de aterrissagem da categoria</span><span class="sxs-lookup"><span data-stu-id="4beee-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="4beee-158">Verificar acessibilidade do conteúdo da página</span><span class="sxs-lookup"><span data-stu-id="4beee-158">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="4beee-159">Criar páginas dinâmicas de comércio eletrônico com base nos parâmetros da URL</span><span class="sxs-lookup"><span data-stu-id="4beee-159">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]