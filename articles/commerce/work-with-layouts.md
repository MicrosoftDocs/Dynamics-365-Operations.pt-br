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
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a2539880e76ffb1861e0d18227a935a2ef35c120
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210866"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="d5992-103">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="d5992-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d5992-104">Este tópico descreve como trabalhar com layouts predefinidos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d5992-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d5992-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="d5992-105">Overview</span></span>

<span data-ttu-id="d5992-106">Antes de concluir os procedimentos neste tópico, não deixe de ler [Layouts predefinidos e personalizados](templates-layouts-overview.md#preset-and-custom-layouts).</span><span class="sxs-lookup"><span data-stu-id="d5992-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="d5992-107">Para obter uma visão geral, consulte [Visão geral de modelos e layouts](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5992-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="d5992-108">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="d5992-108">Create a new preset layout</span></span>

<span data-ttu-id="d5992-109">Há dois métodos para criar um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="d5992-110">Você pode salvar um layout personalizado existente como um novo layout predefinido, ou criar um layout predefinido a partir do zero.</span><span class="sxs-lookup"><span data-stu-id="d5992-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="d5992-111">Crie um layout predefinido de um layout personalizado existente</span><span class="sxs-lookup"><span data-stu-id="d5992-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="d5992-112">Para criar um layout predefinido de um layout personalizado existente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d5992-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="d5992-113">Abra uma página existente que atualmente não use um layout predefinido e que tenha uma estrutura de módulo que você deseja reutilizar para outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="d5992-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="d5992-114">Selecione **Editar** para verificar a página.</span><span class="sxs-lookup"><span data-stu-id="d5992-114">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="d5992-115">Selecione **Salvar como novo layout**.</span><span class="sxs-lookup"><span data-stu-id="d5992-115">Select **Save as new layout**.</span></span> <span data-ttu-id="d5992-116">A caixa de diálogo **Salvar como novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="d5992-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="d5992-117">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="d5992-118">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="d5992-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="d5992-119">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="d5992-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="d5992-120">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5992-120">Select **OK**.</span></span>

<span data-ttu-id="d5992-121">O layout predefinido agora estará disponível quando você criar novas páginas ou selecionar um layout diferente para uma página na mesma hierarquia de modelo.</span><span class="sxs-lookup"><span data-stu-id="d5992-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="d5992-122">Para ver rapidamente se uma página específica está atualmente vinculada a um layout predefinido, selecione a página na exibição de lista de páginas e inspecione os metadados do layout no painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="d5992-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="d5992-123">Criar um novo layout predefinido</span><span class="sxs-lookup"><span data-stu-id="d5992-123">Create a new preset layout</span></span>

<span data-ttu-id="d5992-124">Para criar um layout predefinido do zero, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d5992-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="d5992-125">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="d5992-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="d5992-126">Selecione **Novo Layout**.</span><span class="sxs-lookup"><span data-stu-id="d5992-126">Select **New Layout**.</span></span> <span data-ttu-id="d5992-127">A caixa de diálogo **Novo layout** será exibida.</span><span class="sxs-lookup"><span data-stu-id="d5992-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="d5992-128">Selecione o modelo a ser usado para o layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="d5992-129">Digite um nome e uma descrição para seu layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="d5992-130">Os valores que você inserir serão mostrados a outros autores quando eles criarem novas páginas do seu layout ou mudarem para ele.</span><span class="sxs-lookup"><span data-stu-id="d5992-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="d5992-131">Portanto, insira valores que serão úteis para os criadores de página.</span><span class="sxs-lookup"><span data-stu-id="d5992-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="d5992-132">Selecione **OK** para criar o novo layout predefinido e abrir o editor de layout.</span><span class="sxs-lookup"><span data-stu-id="d5992-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="d5992-133">No editor de layout, adicione e configure módulos usando a árvore de estrutura de tópicos à esquerda e o painel de propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="d5992-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="d5992-134">(O processo se assemelha ao processo de adição e configuração de módulos para um modelo no editor de modelos.) A organização dos módulos e quaisquer configurações padrão bloqueadas tornam-se a configuração centralizada do módulo para todas as páginas que usam esse layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="d5992-135">Modifique um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="d5992-135">Modify a preset layout</span></span>

<span data-ttu-id="d5992-136">Para modificar um layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d5992-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="d5992-137">No painel de navegação à esquerda, selecione **Layouts**.</span><span class="sxs-lookup"><span data-stu-id="d5992-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="d5992-138">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo para alterar.</span><span class="sxs-lookup"><span data-stu-id="d5992-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="d5992-139">Em seguida, siga quaisquer uma dessas etapas:</span><span class="sxs-lookup"><span data-stu-id="d5992-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="d5992-140">Para mover um módulo para cima ou para baixo dentro de seu pai, selecione o botão de reticências (**...**) do módulo e selecione **Mover para cima** ou **Mover para baixo**.</span><span class="sxs-lookup"><span data-stu-id="d5992-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="d5992-141">Para alterar as configurações padrão de um módulo, use o painel de propriedades para inserir valores padrão e para bloquear-los opcionalmente para todas as páginas downstream.</span><span class="sxs-lookup"><span data-stu-id="d5992-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="d5992-142">Para adicionar novos módulos ou fragmentos aos módulos de contêiner, selecione o botão de reticências e selecione **Adicionar módulo** ou **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="d5992-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="d5992-143">Para remover um módulo do layout, selecione o botão de reticências e depois **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="d5992-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="d5992-144">Alterar um tema predefinido de layout</span><span class="sxs-lookup"><span data-stu-id="d5992-144">Change a preset layout theme</span></span>

<span data-ttu-id="d5992-145">Uma prática comum é definir um tema padrão para todas as páginas com um layout predefinido.</span><span class="sxs-lookup"><span data-stu-id="d5992-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="d5992-146">Para definir ou alterar um tema para todas as páginas filho com o layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d5992-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="d5992-147">No editor do layout, na árvore de estrutura de tópicos à esquerda, selecione o módulo de contêiner.</span><span class="sxs-lookup"><span data-stu-id="d5992-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="d5992-148">(Normalmente, este módulo é o segundo nó e é chamado **Página padrão**.)</span><span class="sxs-lookup"><span data-stu-id="d5992-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="d5992-149">No painel de propriedade à direita, no campo **Tema** , selecione um tema.</span><span class="sxs-lookup"><span data-stu-id="d5992-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="d5992-150">Salvar, fazer check-in, visualizar e publicar um layout predefinido</span><span class="sxs-lookup"><span data-stu-id="d5992-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="d5992-151">Para salvar e fazer check-in do layout predefinido, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d5992-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="d5992-152">Selecione **Salvar** na parte superior do editor do layout.</span><span class="sxs-lookup"><span data-stu-id="d5992-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="d5992-153">As alterações salvas não afetam as páginas downstream até o check-in.</span><span class="sxs-lookup"><span data-stu-id="d5992-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="d5992-154">Selecione **Concluir edição**.</span><span class="sxs-lookup"><span data-stu-id="d5992-154">Select **Finish editing**.</span></span> <span data-ttu-id="d5992-155">Suas alterações agora são detectáveis para fluxos de trabalho downstream.</span><span class="sxs-lookup"><span data-stu-id="d5992-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="d5992-156">Para visualizar as alterações, abra uma página existente que usa o layout predefinido ou crie uma nova página do layout.</span><span class="sxs-lookup"><span data-stu-id="d5992-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="d5992-157">Depois que você visualizou alterações no layout predefinido, siga uma dessas etapas para publicar o layout em seu site ativo:</span><span class="sxs-lookup"><span data-stu-id="d5992-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="d5992-158">Vá para **Layouts**, selecione o layout depois **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d5992-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="d5992-159">Selecione o nome do layout para abrir o editor de layout e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d5992-159">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="d5992-160">Publicar uma página que faça referência ao layout não publicado.</span><span class="sxs-lookup"><span data-stu-id="d5992-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="d5992-161">O layout será publicado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d5992-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="d5992-162">Os layouts predefinidos podem ser referenciados a várias páginas.</span><span class="sxs-lookup"><span data-stu-id="d5992-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="d5992-163">Quando você publica um layout predefinido, saiba que pode afetar o layout de várias páginas.</span><span class="sxs-lookup"><span data-stu-id="d5992-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d5992-164">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d5992-164">Additional resources</span></span>

[<span data-ttu-id="d5992-165">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="d5992-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="d5992-166">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="d5992-166">Work with templates</span></span>](work-with-templates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]