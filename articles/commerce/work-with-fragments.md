---
title: Trabalhar com fragmentos
description: Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698087"
---
# <a name="work-with-fragments"></a><span data-ttu-id="657d3-103">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="657d3-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="657d3-104">Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="657d3-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="657d3-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="657d3-105">Overview</span></span>

<span data-ttu-id="657d3-106">Os fragmentos permitem uma experiência de criação centralizada para configurações de módulos que devem ser reutilizadas em todo o site.</span><span class="sxs-lookup"><span data-stu-id="657d3-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="657d3-107">Por exemplo, cabeçalhos, rodapés e banners geralmente são configurados como fragmentos, porque são compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="657d3-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="657d3-108">Você pode pensar em fragmentos como páginas da Web em miniatura que podem ser inseridas em outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="657d3-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="657d3-109">Os fragmentos têm seu próprio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="657d3-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="657d3-110">Em outras palavras, eles são criados, referenciados, atualizados e excluídos como entidades independentes nas ferramentas de criação.</span><span class="sxs-lookup"><span data-stu-id="657d3-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="657d3-111">Após a configuração dos fragmentos, eles podem ser usados sempre que os módulos puderem ser usados na estrutura do site.</span><span class="sxs-lookup"><span data-stu-id="657d3-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="657d3-112">Os fragmentos podem ser referenciados em páginas, layouts, modelos e em outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="657d3-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="657d3-113">Os fragmentos podem ser aninhados até sete níveis dentro de outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="657d3-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="657d3-114">Por exemplo, se quiser promover um evento sazonal em muitas páginas do site, você pode usar um fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="657d3-115">A primeira etapa no processo de criação de um novo fragmento é selecionar o tipo de módulo que você deseja iniciar.</span><span class="sxs-lookup"><span data-stu-id="657d3-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="657d3-116">Neste exemplo, você pode construir o fragmento a partir de um módulo herói.</span><span class="sxs-lookup"><span data-stu-id="657d3-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="657d3-117">Os fragmentos podem ser criados em qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="657d3-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="657d3-118">É possível configurar o fragmento de herói com seu conteúdo promocional específico.</span><span class="sxs-lookup"><span data-stu-id="657d3-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="657d3-119">Você também pode localizá-lo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="657d3-119">You can also localize it as you require.</span></span> <span data-ttu-id="657d3-120">O novo fragmento de herói independente pode ser consumido como um módulo pré-configurado em todo o site.</span><span class="sxs-lookup"><span data-stu-id="657d3-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="657d3-121">Você pode adicioná-lo facilmente a modelos, páginas específicas ou outros fragmentos que podem conter módulos de heróis.</span><span class="sxs-lookup"><span data-stu-id="657d3-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="657d3-122">Todos os locais onde o fragmento é adicionado são referências ao fragmento de herói central que você criou.</span><span class="sxs-lookup"><span data-stu-id="657d3-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="657d3-123">Se você publicar alterações no fragmento, essas alterações serão refletidas imediatamente em todos os locais em que o fragmento é referenciado no site.</span><span class="sxs-lookup"><span data-stu-id="657d3-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="657d3-124">Portanto, os fragmentos fornecem uma maneira poderosa e eficiente de reutilizar e gerenciar centralmente as configurações dos módulos em um site.</span><span class="sxs-lookup"><span data-stu-id="657d3-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="657d3-125">Ao usá-los efetivamente, você pode aumentar significativamente a agilidade e ajudar a reduzir o custo associado ao gerenciamento do conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="657d3-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="657d3-126">A ilustração a seguir mostra como os fragmentos podem ser usados para centralizar a criação das configurações de módulo compartilhadas através de um site de Comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="657d3-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Uma ilustração que mostra como os fragmentos podem ser usados para centralizar a criação de configurações de módulos compartilhados em um site de Comércio eletrônico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="657d3-128">Criar um fragmento</span><span class="sxs-lookup"><span data-stu-id="657d3-128">Create a fragment</span></span>

<span data-ttu-id="657d3-129">Você pode criar um novo fragmento ou salvar uma configuração de módulo existente como um fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="657d3-130">Criar um novo documento</span><span class="sxs-lookup"><span data-stu-id="657d3-130">Create a new fragment</span></span>

<span data-ttu-id="657d3-131">Para criar um novo fragmento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="657d3-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="657d3-132">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="657d3-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="657d3-133">Selecione **Novo Fragmento da Página**.</span><span class="sxs-lookup"><span data-stu-id="657d3-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="657d3-134">É exibida uma caixa de diálogo que mostra todos os tipos de módulo disponíveis.</span><span class="sxs-lookup"><span data-stu-id="657d3-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="657d3-135">Como mencionado anteriormente, os fragmentos podem ser criados de qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="657d3-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="657d3-136">Selecione um tipo de módulo de seu fragmento e depois **OK**.</span><span class="sxs-lookup"><span data-stu-id="657d3-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="657d3-137">Ao selecionar um tipo de módulo de contêiner genérico, você obtém mais flexibilidade ao atualizar e configurar seu fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="657d3-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="657d3-138">Salvar uma configuração de módulo existente como um fragmento</span><span class="sxs-lookup"><span data-stu-id="657d3-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="657d3-139">Para converter um módulo configurado anteriormente a um fragmento reutilizável, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="657d3-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="657d3-140">Abra uma página ou modelo que contém o módulo que você deseja converter em um fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="657d3-141">No painel de estrutura de tópicos à esquerda, selecione o botão de reticências (**...**) ao lado do nome do módulo e, em seguida, selecione **Salvar como Fragmento**.</span><span class="sxs-lookup"><span data-stu-id="657d3-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="657d3-142">Uma caixa de diálogo será exibida.</span><span class="sxs-lookup"><span data-stu-id="657d3-142">A dialog box appears.</span></span>
1. <span data-ttu-id="657d3-143">Digite um nome e metadados para o fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="657d3-144">Selecione **OK** para salvar a configuração do módulo como um fragmento que possa ser adicionado a outras páginas.</span><span class="sxs-lookup"><span data-stu-id="657d3-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="657d3-145">Adicionar, remover ou editar fragmentos em uma página</span><span class="sxs-lookup"><span data-stu-id="657d3-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="657d3-146">Os procedimentos a seguir descrevem como adicionar, remover e edite fragmentos.</span><span class="sxs-lookup"><span data-stu-id="657d3-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="657d3-147">Adicionar um fragmento</span><span class="sxs-lookup"><span data-stu-id="657d3-147">Add a fragment</span></span>

<span data-ttu-id="657d3-148">Para adicionar um fragmento a uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="657d3-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="657d3-149">No painel de estrutura de tópicos à esquerda, selecione um contêiner ou slot aos quais os módulos filho podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="657d3-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="657d3-150">Selecione o botão de reticências ao lado do nome do contêiner ou do slot e selecione **Adicionar Fragmento**.</span><span class="sxs-lookup"><span data-stu-id="657d3-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="657d3-151">Uma caixa de diálogo será exibida.</span><span class="sxs-lookup"><span data-stu-id="657d3-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="657d3-152">Se o contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Fragmento** não ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="657d3-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="657d3-153">Na caixa de diálogo, procure e selecione um fragmento para adicionar.</span><span class="sxs-lookup"><span data-stu-id="657d3-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="657d3-154">Se nenhum fragmento disponível estiver listado, você poderá primeiro criar um fragmento a partir de um tipo de módulo suportado pelo contêiner ou slot selecionado.</span><span class="sxs-lookup"><span data-stu-id="657d3-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="657d3-155">Selecione **OK** para adicionar o fragmento selecionado ao contêiner ou ao slot selecionado na página.</span><span class="sxs-lookup"><span data-stu-id="657d3-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="657d3-156">Os módulos permitidos em um contêiner ou slot são definidos pelo modelo da página ou pelas próprias definições dos módulos.</span><span class="sxs-lookup"><span data-stu-id="657d3-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="657d3-157">Remova um fragmento</span><span class="sxs-lookup"><span data-stu-id="657d3-157">Remove a fragment</span></span>

<span data-ttu-id="657d3-158">Para remover um fragmento de um slot ou contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="657d3-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="657d3-159">No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do fragmento a ser removido e, em seguida, selecione o botão da lixeira.</span><span class="sxs-lookup"><span data-stu-id="657d3-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="657d3-160">Quando for solicitado para confirmar se você deseja remover o fragmento, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="657d3-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="657d3-161">Ao remover um fragmento de uma página, você apenas remove a referência a ele dessa página.</span><span class="sxs-lookup"><span data-stu-id="657d3-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="657d3-162">Você **não** exclui o fragmento de seu site.</span><span class="sxs-lookup"><span data-stu-id="657d3-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="657d3-163">Para excluir fragmentos de seu site, você deve usar a interface de usuário (UI) do inspetor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="657d3-164">Você pode excluir fragmentos do site apenas se não forem referidos atualmente por quaisquer páginas, modelos, ou por outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="657d3-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="657d3-165">Editar um fragmento</span><span class="sxs-lookup"><span data-stu-id="657d3-165">Edit a fragment</span></span>

<span data-ttu-id="657d3-166">Para editar fragmentos, você deve usar a interface de usuário do editor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="657d3-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="657d3-167">Esta restrição é por design.</span><span class="sxs-lookup"><span data-stu-id="657d3-167">This restriction is by design.</span></span> <span data-ttu-id="657d3-168">Isso ajuda a garantir que os autores não confundam o processo de edição dos módulos de uma página específica com o processo de edição de fragmentos que podem ser compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="657d3-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="657d3-169">Para editar um fragmento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="657d3-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="657d3-170">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="657d3-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="657d3-171">Em **Fragmentos**, selecione o fragmento para editar.</span><span class="sxs-lookup"><span data-stu-id="657d3-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="657d3-172">Edite as propriedades e a estrutura do módulo do fragmento, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="657d3-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="657d3-173">O processo se assemelha ao processo de edição dos módulos que são editados na visualização do editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="657d3-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="657d3-174">Você também pode editar um fragmento selecionando-o em uma página, em um modelo ou em um fragmento pai e, em seguida, selecionando **Editar Fragmento** no painel propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="657d3-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="657d3-175">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="657d3-175">Additional resources</span></span>

[<span data-ttu-id="657d3-176">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="657d3-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="657d3-177">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="657d3-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="657d3-178">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="657d3-178">Work with preset layouts</span></span>](work-with-layouts.md)
