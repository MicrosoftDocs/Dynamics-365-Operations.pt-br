---
title: Trabalhar com layouts predefinidos
description: Este tópico descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ce54be1032777ffcaac474773cdeeef3b9028110
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5793912"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="e0662-103">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="e0662-103">Work with preset layouts</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0662-104">Este tópico descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e0662-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e0662-105">Antes de concluir os procedimentos neste tópico, não deixe de ler [Layouts predefinidos e personalizados](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="e0662-105">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="e0662-106">Para obter uma visão geral, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e0662-106">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="e0662-107">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="e0662-107">Create a new preset layout</span></span>

<span data-ttu-id="e0662-108">Há dois métodos para criar um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-108">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="e0662-109">Você pode salvar um layout personalizado existente como um novo layout predefinido, ou criar um layout predefinido a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="e0662-109">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="e0662-110">Crie um layout predefinido de um layout personalizado existente</span><span class="sxs-lookup"><span data-stu-id="e0662-110">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="e0662-111">Para criar um layout predefinido de um layout personalizado existente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e0662-111">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="e0662-112">Abra uma página existente que atualmente não use um layout predefinido e que tenha uma estrutura de módulo que você deseja reutilizar para outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="e0662-112">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="e0662-113">Selecione **Editar** para verificar a página.</span><span class="sxs-lookup"><span data-stu-id="e0662-113">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="e0662-114">Selecione **Salvar como novo layout**.</span><span class="sxs-lookup"><span data-stu-id="e0662-114">Select **Save as new layout**.</span></span> <span data-ttu-id="e0662-115">A caixa de diálogo **Salvar como novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="e0662-115">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="e0662-116">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-116">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="e0662-117">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="e0662-117">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="e0662-118">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="e0662-118">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="e0662-119">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0662-119">Select **OK**.</span></span>

<span data-ttu-id="e0662-120">O layout predefinido agora estará disponível quando você criar novas páginas ou selecionar um layout diferente para uma página na mesma hierarquia de modelo.</span><span class="sxs-lookup"><span data-stu-id="e0662-120">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="e0662-121">Para ver rapidamente se uma página específica está atualmente vinculada a um layout predefinido, selecione a página na exibição de lista de páginas e inspecione os metadados do layout no painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="e0662-121">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="e0662-122">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="e0662-122">Create a new preset layout</span></span>

<span data-ttu-id="e0662-123">Para criar um layout predefinido do zero, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e0662-123">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="e0662-124">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="e0662-124">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="e0662-125">Selecione **Novo Layout**.</span><span class="sxs-lookup"><span data-stu-id="e0662-125">Select **New Layout**.</span></span> <span data-ttu-id="e0662-126">A caixa de diálogo **Novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="e0662-126">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="e0662-127">Selecione o modelo a ser usado para o layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-127">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="e0662-128">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-128">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="e0662-129">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="e0662-129">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="e0662-130">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="e0662-130">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="e0662-131">Selecione **OK** para criar o novo layout predefinido e abrir o editor de layout.</span><span class="sxs-lookup"><span data-stu-id="e0662-131">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="e0662-132">No editor de layout, adicione e configure módulos usando a árvore de estrutura de tópicos à esquerda e o painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="e0662-132">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="e0662-133">(O processo se assemelha ao processo de adição e configuração de módulos para um modelo no editor de modelos.) A organização dos módulos e quaisquer configurações padrão bloqueadas tornam-se a configuração centralizada do módulo para todas as páginas que usam esse layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-133">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="e0662-134">Modifique um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="e0662-134">Modify a preset layout</span></span>

<span data-ttu-id="e0662-135">Para modificar um layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e0662-135">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="e0662-136">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="e0662-136">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="e0662-137">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo para alterar.</span><span class="sxs-lookup"><span data-stu-id="e0662-137">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="e0662-138">Em seguida, siga quaisquer uma dessas etapas:</span><span class="sxs-lookup"><span data-stu-id="e0662-138">Then follow any of these steps:</span></span>

    - <span data-ttu-id="e0662-139">Para mover um módulo para cima ou para baixo dentro de seu pai, selecione o botão de reticências (**...**) do módulo e selecione **Mover para cima** ou **Mover para baixo**.</span><span class="sxs-lookup"><span data-stu-id="e0662-139">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="e0662-140">Para alterar as configurações padrão de um módulo, use o painel de propriedades para inserir valores padrão e para bloquear-los opcionalmente para todas as páginas downstream.</span><span class="sxs-lookup"><span data-stu-id="e0662-140">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="e0662-141">Para adicionar novos módulos ou fragmentos aos módulos de contêiner, selecione o botão de reticências e selecione **Adicionar módulo** ou **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="e0662-141">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="e0662-142">Para remover um módulo do layout, selecione o botão de reticências e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="e0662-142">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="e0662-143">Alterar um tema predefinido de layout</span><span class="sxs-lookup"><span data-stu-id="e0662-143">Change a preset layout theme</span></span>

<span data-ttu-id="e0662-144">Uma prática comum é definir um tema padrão para todas as páginas com um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="e0662-144">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="e0662-145">Para definir ou alterar um tema para todas as páginas filho com o layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e0662-145">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="e0662-146">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="e0662-146">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="e0662-147">(Normalmente, este módulo é o segundo nó e é chamado **Página padrão**.)</span><span class="sxs-lookup"><span data-stu-id="e0662-147">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="e0662-148">No painel de propriedade à direita, no campo **Tema** , selecione um tema.</span><span class="sxs-lookup"><span data-stu-id="e0662-148">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="e0662-149">Salvar, fazer check-in, visualizar e publicar um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="e0662-149">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="e0662-150">Para salvar e fazer check-in do layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e0662-150">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="e0662-151">Selecione **Salvar** na parte superior do editor do layout.</span><span class="sxs-lookup"><span data-stu-id="e0662-151">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="e0662-152">As alterações salvas não afetam as páginas downstream até o check-in.</span><span class="sxs-lookup"><span data-stu-id="e0662-152">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="e0662-153">Selecione **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="e0662-153">Select **Finish editing**.</span></span> <span data-ttu-id="e0662-154">Suas alterações agora são detectáveis para fluxos de trabalho downstream.</span><span class="sxs-lookup"><span data-stu-id="e0662-154">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="e0662-155">Para visualizar as alterações, abra uma página existente que usa o layout predefinido ou crie uma nova página do layout.</span><span class="sxs-lookup"><span data-stu-id="e0662-155">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="e0662-156">Depois que você visualizou alterações no layout predefinido, siga uma dessas etapas para publicar o layout em seu site ativo:</span><span class="sxs-lookup"><span data-stu-id="e0662-156">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="e0662-157">Vá para **Layouts**, selecione o layout depois **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e0662-157">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="e0662-158">Selecione o nome do layout para abrir o editor de layout e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="e0662-158">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="e0662-159">Publicar uma página que faça referência ao layout não publicado.</span><span class="sxs-lookup"><span data-stu-id="e0662-159">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="e0662-160">O layout será publicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e0662-160">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="e0662-161">Os layouts predefinidos podem ser referenciados a várias páginas.</span><span class="sxs-lookup"><span data-stu-id="e0662-161">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="e0662-162">Quando você publica um layout predefinido, saiba que pode afetar o layout de várias páginas.</span><span class="sxs-lookup"><span data-stu-id="e0662-162">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0662-163">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e0662-163">Additional resources</span></span>

[<span data-ttu-id="e0662-164">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="e0662-164">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e0662-165">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="e0662-165">Work with templates</span></span>](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
