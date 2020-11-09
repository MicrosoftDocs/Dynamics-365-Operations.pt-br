---
title: Trabalhar com fragmentos
description: Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f1525610fb16edd5ff9ccefe0194f6f27b797b62
ms.sourcegitcommit: b063bf3a52f19baa11ddba31ef9313d58a0f610e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4019555"
---
# <a name="work-with-fragments"></a><span data-ttu-id="2894a-103">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="2894a-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="2894a-104">Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2894a-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2894a-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="2894a-105">Overview</span></span>

<span data-ttu-id="2894a-106">Os fragmentos permitem uma experiência de criação centralizada para configurações de módulos que devem ser reutilizadas em todo o site.</span><span class="sxs-lookup"><span data-stu-id="2894a-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="2894a-107">Por exemplo, cabeçalhos, rodapés e banners geralmente são configurados como fragmentos, porque são compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="2894a-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="2894a-108">Você pode pensar em fragmentos como páginas da Web em miniatura que podem ser inseridas em outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="2894a-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="2894a-109">Os fragmentos têm seu próprio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="2894a-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="2894a-110">Em outras palavras, eles são criados, referenciados, atualizados e excluídos como entidades independentes nas ferramentas de criação.</span><span class="sxs-lookup"><span data-stu-id="2894a-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="2894a-111">Após a configuração dos fragmentos, eles podem ser usados sempre que os módulos puderem ser usados na estrutura do site.</span><span class="sxs-lookup"><span data-stu-id="2894a-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="2894a-112">Os fragmentos podem ser referenciados em páginas, layouts, modelos e em outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="2894a-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="2894a-113">Os fragmentos podem ser aninhados até sete níveis dentro de outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="2894a-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="2894a-114">Por exemplo, se quiser promover um evento sazonal em muitas páginas do site, você pode usar um fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="2894a-115">A primeira etapa no processo de criação de um novo fragmento é selecionar o tipo de módulo que você deseja iniciar.</span><span class="sxs-lookup"><span data-stu-id="2894a-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="2894a-116">Neste exemplo, você pode construir o fragmento a partir de um módulo herói.</span><span class="sxs-lookup"><span data-stu-id="2894a-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="2894a-117">Os fragmentos podem ser criados em qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="2894a-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="2894a-118">É possível configurar o fragmento de herói com seu conteúdo promocional específico.</span><span class="sxs-lookup"><span data-stu-id="2894a-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="2894a-119">Você também pode localizá-lo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2894a-119">You can also localize it as you require.</span></span> <span data-ttu-id="2894a-120">O novo fragmento de herói independente pode ser consumido como um módulo pré-configurado em todo o site.</span><span class="sxs-lookup"><span data-stu-id="2894a-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="2894a-121">Você pode adicioná-lo facilmente a modelos, páginas específicas ou outros fragmentos que podem conter módulos de heróis.</span><span class="sxs-lookup"><span data-stu-id="2894a-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="2894a-122">Todos os locais onde o fragmento é adicionado são referências ao fragmento de herói central que você criou.</span><span class="sxs-lookup"><span data-stu-id="2894a-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="2894a-123">Se você publicar alterações no fragmento, essas alterações serão refletidas imediatamente em todos os locais em que o fragmento é referenciado no site.</span><span class="sxs-lookup"><span data-stu-id="2894a-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="2894a-124">Portanto, os fragmentos fornecem uma maneira poderosa e eficiente de reutilizar e gerenciar centralmente as configurações dos módulos em um site.</span><span class="sxs-lookup"><span data-stu-id="2894a-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="2894a-125">Ao usá-los efetivamente, você pode aumentar significativamente a agilidade e ajudar a reduzir o custo associado ao gerenciamento do conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="2894a-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="2894a-126">A ilustração a seguir mostra como os fragmentos podem ser usados para centralizar a criação das configurações de módulo compartilhadas através de um site de Comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2894a-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Uma ilustração que mostra como os fragmentos podem ser usados para centralizar a criação de configurações de módulos compartilhados em um site de Comércio eletrônico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="2894a-128">Criar um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-128">Create a fragment</span></span>

<span data-ttu-id="2894a-129">Você pode criar um novo fragmento ou salvar uma configuração de módulo existente como um fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="2894a-130">Salvar uma configuração de módulo existente como um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="2894a-131">Para converter um módulo configurado anteriormente a um fragmento reutilizável no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2894a-131">To convert a previously configured module to a reusable fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2894a-132">Abra uma página ou modelo que contém o módulo que você deseja converter em um fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="2894a-133">No painel de estrutura de tópicos à esquerda ou diretamente no construtor de página visual, selecione o módulo configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2894a-133">In the outline pane on the left or directly in visual page builder, select the previously configured module.</span></span>
1. <span data-ttu-id="2894a-134">Selecione as reticências ( **...** ) ao lado do nome do módulo no painel de estrutura de tópicos ou na barra de ferramentas do módulo selecionado no construtor de página visual.</span><span class="sxs-lookup"><span data-stu-id="2894a-134">Select the ellipsis ( **...** ) next to the name of the module in either the outline pane or the selected module's toolbar in visual page builder.</span></span> 
1. <span data-ttu-id="2894a-135">Selecione **Compartilhar como fragmento**.</span><span class="sxs-lookup"><span data-stu-id="2894a-135">Select **Share as fragment**.</span></span> 
1. <span data-ttu-id="2894a-136">Na caixa de diálogo **Salvar como fragmento** , insira um nome para o fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-136">In the **Save as fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="2894a-137">Selecione **OK** para salvar a configuração do módulo como um fragmento que possa ser adicionado a outras páginas.</span><span class="sxs-lookup"><span data-stu-id="2894a-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>
<!-- The following image shows how to save a module configuration as a fragment.-->
<!--![A screen capture of how to save a module configuration as a fragment](./media/save-as-fragment.png)-->

### <a name="create-a-new-fragment"></a><span data-ttu-id="2894a-138">Criar um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-138">Create a new fragment</span></span>

<span data-ttu-id="2894a-139">Para criar um novo fragmento no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2894a-139">To create a new fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2894a-140">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="2894a-140">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="2894a-141">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2894a-141">Select **New**.</span></span> <span data-ttu-id="2894a-142">Uma caixa de diálogo **Novo fragmento** aparece e mostra todos os tipos de módulo disponíveis.</span><span class="sxs-lookup"><span data-stu-id="2894a-142">A **New fragment** dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="2894a-143">Como mencionado anteriormente, os fragmentos podem ser criados de qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="2894a-143">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="2894a-144">Selecione um tipo de módulo para o fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-144">Select a module type for your fragment.</span></span>

<!-- The following image shows where to create a new fragment.-->
<!-- ![A screen capture of where to create a new fragment](./media/fragment-nav-menu.png)-->
> [!TIP]
> <span data-ttu-id="2894a-145">Ao selecionar um tipo de módulo de contêiner genérico, você obtém maior flexibilidade quando precisar atualizar e configurar seu fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2894a-145">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="2894a-146">Adicionar, remover ou editar fragmentos em uma página</span><span class="sxs-lookup"><span data-stu-id="2894a-146">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="2894a-147">Os procedimentos a seguir descrevem como adicionar, remover e edite fragmentos.</span><span class="sxs-lookup"><span data-stu-id="2894a-147">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="2894a-148">Adicionar um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-148">Add a fragment</span></span>

<span data-ttu-id="2894a-149">Para adicionar um fragmento a uma página no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2894a-149">To add a fragment to a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2894a-150">No painel de estrutura de tópicos à esquerda ou diretamente no construtor de página visual, selecione um contêiner ou slot ao qual os módulos filho possam ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="2894a-150">In the outline pane on the left or directly in visual page builder, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="2894a-151">Selecione as reticências ( **...** ) ao lado do nome do contêiner ou slot.</span><span class="sxs-lookup"><span data-stu-id="2894a-151">Select the ellipsis ( **...** ) next to the name of the container or slot.</span></span>  <span data-ttu-id="2894a-152">Como alternativa, se usar o construtor de página visual, selecione o símbolo de adição ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="2894a-152">Alternately, if using visual page builder, select the plus symbol ( **+** ).</span></span>  
1. <span data-ttu-id="2894a-153">Selecione **Adicionar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="2894a-153">Select **Add fragment**.</span></span>
    <!-- ![A screen capture of how to add an existing fragment to a slot or container](./media/add-fragment.png)-->
 
    > [!NOTE]
    > <span data-ttu-id="2894a-154">Se o contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar fragmento** não ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="2894a-154">If the container or slot doesn't support new child modules, the **Add fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="2894a-155">Na caixa de diálogo **Selecionar fragmento** , procure e selecione um fragmento a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="2894a-155">In the **Select fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="2894a-156">Se nenhum fragmento disponível estiver listado, você poderá primeiro criar um fragmento a partir de um tipo de módulo suportado pelo contêiner ou slot selecionado.</span><span class="sxs-lookup"><span data-stu-id="2894a-156">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="2894a-157">Selecione o fragmento desejado para adicionar ao contêiner ou ao slot na sua página.</span><span class="sxs-lookup"><span data-stu-id="2894a-157">Select your desired fragment to add it to the container or slot on your page.</span></span>
<!--    ![A screen capture of the fragment picker modal window](./media/fragment-picker.png)-->

> [!NOTE]
> <span data-ttu-id="2894a-158">Os módulos permitidos em um contêiner ou slot são definidos pelo modelo da página ou pelas próprias definições dos módulos.</span><span class="sxs-lookup"><span data-stu-id="2894a-158">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="2894a-159">Remova um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-159">Remove a fragment</span></span>

<span data-ttu-id="2894a-160">Para remover um fragmento de um slot ou contêiner em uma página no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2894a-160">To remove a fragment from a slot or container on a page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2894a-161">No painel de estrutura de tópicos à esquerda, selecione as reticências ( **...** ) ao lado do nome do fragmento a ser removido e, depois, selecione o símbolo de lixeira.</span><span class="sxs-lookup"><span data-stu-id="2894a-161">In the outline pane on the left, select the ellipsis ( **...** ) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="2894a-162">Como alternativa, você pode selecionar o fragmento no construtor de página visual e selecionar o símbolo de lixeira na barra de ferramentas do fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-162">Alternately, you can select the fragment in visual page builder and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="2894a-163">Quando for solicitado para confirmar se você deseja remover o fragmento, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2894a-163">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="2894a-164">Ao remover um fragmento de uma página, você apenas remove a referência a ele dessa página.</span><span class="sxs-lookup"><span data-stu-id="2894a-164">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="2894a-165">Você **não** exclui o fragmento de seu site.</span><span class="sxs-lookup"><span data-stu-id="2894a-165">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="2894a-166">Para excluir fragmentos de seu site, você deve usar a interface de usuário (UI) do inspetor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-166">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="2894a-167">Você pode excluir fragmentos do site apenas se não forem referidos atualmente por quaisquer páginas, modelos, ou por outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="2894a-167">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="2894a-168">Editar um fragmento</span><span class="sxs-lookup"><span data-stu-id="2894a-168">Edit a fragment</span></span>

<span data-ttu-id="2894a-169">Para editar fragmentos, você deve usar a interface de usuário do editor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="2894a-169">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="2894a-170">Esta restrição é por design.</span><span class="sxs-lookup"><span data-stu-id="2894a-170">This restriction is by design.</span></span> <span data-ttu-id="2894a-171">Isso ajuda a garantir que os autores não confundam o processo de edição dos módulos de uma página específica com o processo de edição de fragmentos que podem ser compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="2894a-171">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="2894a-172">Para editar um novo fragmento no construtor de sites do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2894a-172">To edit a fragment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2894a-173">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="2894a-173">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="2894a-174">Em **Fragmentos** , selecione o fragmento para editar.</span><span class="sxs-lookup"><span data-stu-id="2894a-174">Under **Fragments** , select the fragment to edit.</span></span>
1. <span data-ttu-id="2894a-175">Edite as propriedades e a estrutura do módulo do fragmento, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="2894a-175">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="2894a-176">O processo se assemelha ao processo de edição dos módulos que são editados na visualização do editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="2894a-176">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="2894a-177">Você também pode editar um fragmento selecionando-o em uma página, em um modelo ou em um fragmento pai e, em seguida, selecionando **Editar Fragmento** no painel propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="2894a-177">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2894a-178">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2894a-178">Additional resources</span></span>

[<span data-ttu-id="2894a-179">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="2894a-179">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="2894a-180">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="2894a-180">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="2894a-181">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="2894a-181">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="2894a-182">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="2894a-182">Work with publish groups</span></span>](publish-groups.md)
