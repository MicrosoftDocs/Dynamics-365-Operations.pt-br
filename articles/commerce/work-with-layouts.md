---
title: Trabalhar com layouts predefinidos
description: Este tópico descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f31dfa1fdbb3732610748abe4a9de851033f2b89
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269880"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="c82e9-103">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="c82e9-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c82e9-104">Este tópico descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c82e9-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c82e9-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="c82e9-105">Overview</span></span>

<span data-ttu-id="c82e9-106">Antes de concluir os procedimentos neste tópico, não deixe de ler [Layouts predefinidos e personalizados](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="c82e9-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="c82e9-107">Para obter uma visão geral, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="c82e9-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="c82e9-108">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="c82e9-108">Create a new preset layout</span></span>

<span data-ttu-id="c82e9-109">Há dois métodos para criar um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="c82e9-110">Você pode salvar um layout personalizado existente como um novo layout predefinido, ou criar um layout predefinido a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="c82e9-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="c82e9-111">Crie um layout predefinido de um layout personalizado existente</span><span class="sxs-lookup"><span data-stu-id="c82e9-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="c82e9-112">Para criar um layout predefinido de um layout personalizado existente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="c82e9-113">Abra uma página existente que atualmente não use um layout predefinido e que tenha uma estrutura de módulo que você deseja reutilizar para outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="c82e9-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="c82e9-114">Selecione **Editar** para verificar a página.</span><span class="sxs-lookup"><span data-stu-id="c82e9-114">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="c82e9-115">Selecione **Salvar como novo layout**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-115">Select **Save as new layout**.</span></span> <span data-ttu-id="c82e9-116">A caixa de diálogo **Salvar como novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c82e9-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="c82e9-117">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="c82e9-118">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="c82e9-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="c82e9-119">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="c82e9-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="c82e9-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-120">Select **OK**.</span></span>

<span data-ttu-id="c82e9-121">O layout predefinido agora estará disponível quando você criar novas páginas ou selecionar um layout diferente para uma página na mesma hierarquia de modelo.</span><span class="sxs-lookup"><span data-stu-id="c82e9-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="c82e9-122">Para ver rapidamente se uma página específica está atualmente vinculada a um layout predefinido, selecione a página na exibição de lista de páginas e inspecione os metadados do layout no painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="c82e9-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="c82e9-123">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="c82e9-123">Create a new preset layout</span></span>

<span data-ttu-id="c82e9-124">Para criar um layout predefinido do zero, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="c82e9-125">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="c82e9-126">Selecione **Novo Layout**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-126">Select **New Layout**.</span></span> <span data-ttu-id="c82e9-127">A caixa de diálogo **Novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="c82e9-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="c82e9-128">Selecione o modelo a ser usado para o layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="c82e9-129">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="c82e9-130">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="c82e9-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="c82e9-131">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="c82e9-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="c82e9-132">Selecione **OK** para criar o novo layout predefinido e abrir o editor de layout.</span><span class="sxs-lookup"><span data-stu-id="c82e9-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="c82e9-133">No editor de layout, adicione e configure módulos usando a árvore de estrutura de tópicos à esquerda e o painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="c82e9-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="c82e9-134">(O processo se assemelha ao processo de adição e configuração de módulos para um modelo no editor de modelos.) A organização dos módulos e quaisquer configurações padrão bloqueadas tornam-se a configuração centralizada do módulo para todas as páginas que usam esse layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="c82e9-135">Modifique um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="c82e9-135">Modify a preset layout</span></span>

<span data-ttu-id="c82e9-136">Para modificar um layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="c82e9-137">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="c82e9-138">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo para alterar.</span><span class="sxs-lookup"><span data-stu-id="c82e9-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="c82e9-139">Em seguida, siga quaisquer uma dessas etapas:</span><span class="sxs-lookup"><span data-stu-id="c82e9-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="c82e9-140">Para mover um módulo para cima ou para baixo dentro de seu pai, selecione o botão de reticências (**...**) do módulo e selecione **Mover para cima** ou **Mover para baixo**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="c82e9-141">Para alterar as configurações padrão de um módulo, use o painel de propriedades para inserir valores padrão e para bloquear-los opcionalmente para todas as páginas downstream.</span><span class="sxs-lookup"><span data-stu-id="c82e9-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="c82e9-142">Para adicionar novos módulos ou fragmentos aos módulos de contêiner, selecione o botão de reticências e selecione **Adicionar módulo** ou **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="c82e9-143">Para remover um módulo do layout, selecione o botão de reticências e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="c82e9-144">Alterar um tema predefinido de layout</span><span class="sxs-lookup"><span data-stu-id="c82e9-144">Change a preset layout theme</span></span>

<span data-ttu-id="c82e9-145">Uma prática comum é definir um tema padrão para todas as páginas com um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="c82e9-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="c82e9-146">Para definir ou alterar um tema para todas as páginas filho com o layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="c82e9-147">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="c82e9-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="c82e9-148">(Normalmente, este módulo é o segundo nó e é chamado **Página padrão**.)</span><span class="sxs-lookup"><span data-stu-id="c82e9-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="c82e9-149">No painel de propriedade à direita, no campo **Tema** , selecione um tema.</span><span class="sxs-lookup"><span data-stu-id="c82e9-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="c82e9-150">Salvar, fazer check-in, visualizar e publicar um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="c82e9-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="c82e9-151">Para salvar e fazer check-in do layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="c82e9-152">Selecione **Salvar** na parte superior do editor do layout.</span><span class="sxs-lookup"><span data-stu-id="c82e9-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="c82e9-153">As alterações salvas não afetam as páginas downstream até o check-in.</span><span class="sxs-lookup"><span data-stu-id="c82e9-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="c82e9-154">Selecione **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-154">Select **Finish editing**.</span></span> <span data-ttu-id="c82e9-155">Suas alterações agora são detectáveis para fluxos de trabalho downstream.</span><span class="sxs-lookup"><span data-stu-id="c82e9-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="c82e9-156">Para visualizar as alterações, abra uma página existente que usa o layout predefinido ou crie uma nova página do layout.</span><span class="sxs-lookup"><span data-stu-id="c82e9-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="c82e9-157">Depois que você visualizou alterações no layout predefinido, siga uma dessas etapas para publicar o layout em seu site ativo:</span><span class="sxs-lookup"><span data-stu-id="c82e9-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="c82e9-158">Vá para **Layouts**, selecione o layout depois **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="c82e9-159">Selecione o nome do layout para abrir o editor de layout e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="c82e9-159">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="c82e9-160">Publicar uma página que faça referência ao layout não publicado.</span><span class="sxs-lookup"><span data-stu-id="c82e9-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="c82e9-161">O layout será publicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c82e9-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="c82e9-162">Os layouts predefinidos podem ser referenciados a várias páginas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="c82e9-163">Quando você publica um layout predefinido, saiba que pode afetar o layout de várias páginas.</span><span class="sxs-lookup"><span data-stu-id="c82e9-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c82e9-164">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c82e9-164">Additional resources</span></span>

[<span data-ttu-id="c82e9-165">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="c82e9-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="c82e9-166">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="c82e9-166">Work with templates</span></span>](work-with-templates.md)
