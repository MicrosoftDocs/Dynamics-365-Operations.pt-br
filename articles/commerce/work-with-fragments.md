---
title: Trabalhar com fragmentos
description: Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 07/31/2020
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
ms.openlocfilehash: 671caf1feeb7ac9e7d5a166c5de12540ab9b9792
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818341"
---
# <a name="work-with-fragments"></a><span data-ttu-id="7ef72-103">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="7ef72-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]

<span data-ttu-id="7ef72-104">Este tópico descreve por que, quando e como usar fragmentos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7ef72-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7ef72-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="7ef72-105">Overview</span></span>

<span data-ttu-id="7ef72-106">Os fragmentos permitem uma experiência de criação centralizada para configurações de módulos que devem ser reutilizadas em todo o site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="7ef72-107">Por exemplo, cabeçalhos, rodapés e banners geralmente são configurados como fragmentos, porque são compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="7ef72-108">Você pode pensar em fragmentos como páginas da Web em miniatura que podem ser inseridas em outras páginas do seu site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="7ef72-109">Os fragmentos têm seu próprio ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7ef72-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="7ef72-110">Em outras palavras, eles são criados, referenciados, atualizados e excluídos como entidades independentes nas ferramentas de criação.</span><span class="sxs-lookup"><span data-stu-id="7ef72-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="7ef72-111">Após a configuração dos fragmentos, eles podem ser usados sempre que os módulos puderem ser usados na estrutura do site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="7ef72-112">Os fragmentos podem ser referenciados em páginas, layouts, modelos e em outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="7ef72-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef72-113">Os fragmentos podem ser aninhados até sete níveis dentro de outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="7ef72-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="7ef72-114">Por exemplo, se quiser promover um evento sazonal em muitas páginas do site, você pode usar um fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="7ef72-115">A primeira etapa no processo de criação de um novo fragmento é selecionar o tipo de módulo que você deseja iniciar.</span><span class="sxs-lookup"><span data-stu-id="7ef72-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="7ef72-116">Neste exemplo, você pode construir o fragmento a partir de um módulo herói.</span><span class="sxs-lookup"><span data-stu-id="7ef72-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef72-117">Os fragmentos podem ser criados em qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="7ef72-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="7ef72-118">É possível configurar o fragmento de herói com seu conteúdo promocional específico.</span><span class="sxs-lookup"><span data-stu-id="7ef72-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="7ef72-119">Você também pode localizá-lo, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ef72-119">You can also localize it as you require.</span></span> <span data-ttu-id="7ef72-120">O novo fragmento de herói independente pode ser consumido como um módulo pré-configurado em todo o site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="7ef72-121">Você pode adicioná-lo facilmente a modelos, páginas específicas ou outros fragmentos que podem conter módulos de heróis.</span><span class="sxs-lookup"><span data-stu-id="7ef72-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="7ef72-122">Todos os locais onde o fragmento é adicionado são referências ao fragmento de herói central que você criou.</span><span class="sxs-lookup"><span data-stu-id="7ef72-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="7ef72-123">Se você publicar alterações no fragmento, essas alterações serão refletidas imediatamente em todos os locais em que o fragmento é referenciado no site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="7ef72-124">Portanto, os fragmentos fornecem uma maneira poderosa e eficiente de reutilizar e gerenciar centralmente as configurações dos módulos em um site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="7ef72-125">Ao usá-los efetivamente, você pode aumentar significativamente a agilidade e ajudar a reduzir o custo associado ao gerenciamento do conteúdo do site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="7ef72-126">A ilustração a seguir mostra como os fragmentos podem ser usados para centralizar a criação das configurações de módulo compartilhadas através de um site de Comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7ef72-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![Uma ilustração que mostra como os fragmentos podem ser usados para centralizar a criação de configurações de módulos compartilhados em um site de Comércio eletrônico](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="7ef72-128">Criar um fragmento</span><span class="sxs-lookup"><span data-stu-id="7ef72-128">Create a fragment</span></span>

<span data-ttu-id="7ef72-129">Você pode criar um novo fragmento ou salvar uma configuração de módulo existente como um fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="7ef72-130">Salvar uma configuração de módulo existente como um fragmento</span><span class="sxs-lookup"><span data-stu-id="7ef72-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="7ef72-131">Para converter um módulo configurado anteriormente a um fragmento reutilizável, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-131">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="7ef72-132">Abra uma página ou modelo que contém o módulo que você deseja converter em um fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="7ef72-133">No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione o módulo configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ef72-133">In the outline pane on the left or directly in the main canvas, select the previously configured module.</span></span>
1. <span data-ttu-id="7ef72-134">Selecione as reticências (**...**) ao lado do nome do módulo no painel de estrutura de tópicos ou na barra de ferramentas do módulo selecionado na tela.</span><span class="sxs-lookup"><span data-stu-id="7ef72-134">Select the ellipsis (**...**) next to the name of the module in either the outline pane or the selected module's toolbar in the canvas.</span></span> 
1. <span data-ttu-id="7ef72-135">Selecione **Compartilhar como Fragmento de Página**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-135">Select **Share as Page Fragment**.</span></span> 
1. <span data-ttu-id="7ef72-136">Na caixa de diálogo **Salvar como Fragmento de Página**, insira um nome para o fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-136">In the **Save as Page Fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="7ef72-137">Selecione **OK** para salvar a configuração do módulo como um fragmento que possa ser adicionado a outras páginas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

<span data-ttu-id="7ef72-138">A imagem a seguir mostra como salvar uma configuração de módulo como fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-138">The following image shows how to save a module configuration as a fragment.</span></span>

![Uma captura de tela de como salvar uma configuração de módulo como fragmento](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a><span data-ttu-id="7ef72-140">Criar um novo documento</span><span class="sxs-lookup"><span data-stu-id="7ef72-140">Create a new fragment</span></span>

<span data-ttu-id="7ef72-141">Para criar um novo fragmento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-141">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="7ef72-142">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-142">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="7ef72-143">Selecione **Novo Fragmento da Página**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-143">Select **New Page Fragment**.</span></span> <span data-ttu-id="7ef72-144">É exibida uma caixa de diálogo que mostra todos os tipos de módulo disponíveis.</span><span class="sxs-lookup"><span data-stu-id="7ef72-144">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="7ef72-145">Como mencionado anteriormente, os fragmentos podem ser criados de qualquer tipo de módulo.</span><span class="sxs-lookup"><span data-stu-id="7ef72-145">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="7ef72-146">Selecione um tipo de módulo para o fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-146">Select a module type for your fragment.</span></span>

<span data-ttu-id="7ef72-147">A imagem a seguir mostra onde criar um novo fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-147">The following image shows where to create a new fragment.</span></span>

![Uma captura de tela de onde criar um novo fragmento](./media/fragment-nav-menu.png)

> [!TIP]
> <span data-ttu-id="7ef72-149">Ao selecionar um tipo de módulo de contêiner genérico, você obtém maior flexibilidade quando precisar atualizar e configurar seu fragmento posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7ef72-149">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="7ef72-150">Adicionar, remover ou editar fragmentos em uma página</span><span class="sxs-lookup"><span data-stu-id="7ef72-150">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="7ef72-151">Os procedimentos a seguir descrevem como adicionar, remover e edite fragmentos.</span><span class="sxs-lookup"><span data-stu-id="7ef72-151">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="7ef72-152">Adicionar um fragmento</span><span class="sxs-lookup"><span data-stu-id="7ef72-152">Add a fragment</span></span>

<span data-ttu-id="7ef72-153">Para adicionar um fragmento a uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-153">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="7ef72-154">No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione um contêiner ou slot ao qual os módulos filho possam ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="7ef72-154">In the outline pane on the left or directly in the main canvas, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="7ef72-155">No painel online, selecione as reticências (**...**) ao lado do nome do contêiner ou slot.</span><span class="sxs-lookup"><span data-stu-id="7ef72-155">In the online pane, select the ellipsis (**...**) next to the name of the container or slot.</span></span>  <span data-ttu-id="7ef72-156">Como alternativa, se usar a tela principal, selecione o símbolo de adição (**+**).</span><span class="sxs-lookup"><span data-stu-id="7ef72-156">Alternately, if using the main canvas, select the plus symbol (**+**).</span></span>  
1. <span data-ttu-id="7ef72-157">Selecione **Adicionar Fragmento**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-157">Select **Add Fragment**.</span></span>

    ![Uma captura de tela de como adicionar um fragmento existente a um slot ou contêiner](./media/add-fragment.png)
 
    > [!NOTE]
    > <span data-ttu-id="7ef72-159">Se o contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Fragmento** não ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="7ef72-159">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="7ef72-160">Na caixa de diálogo **Adicionar Fragmento**, procure e selecione um fragmento a ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="7ef72-160">In the **Add Fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="7ef72-161">Se nenhum fragmento disponível estiver listado, você poderá primeiro criar um fragmento a partir de um tipo de módulo suportado pelo contêiner ou slot selecionado.</span><span class="sxs-lookup"><span data-stu-id="7ef72-161">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="7ef72-162">Selecione o fragmento desejado para adicionar ao contêiner ou ao slot na sua página.</span><span class="sxs-lookup"><span data-stu-id="7ef72-162">Select your desired fragment to add it to the container or slot on your page.</span></span>

    ![Uma captura de tela da janela modal do seletor de fragmento](./media/fragment-picker.png)

> [!NOTE]
> <span data-ttu-id="7ef72-164">Os módulos permitidos em um contêiner ou slot são definidos pelo modelo da página ou pelas próprias definições dos módulos.</span><span class="sxs-lookup"><span data-stu-id="7ef72-164">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="7ef72-165">Remova um fragmento</span><span class="sxs-lookup"><span data-stu-id="7ef72-165">Remove a fragment</span></span>

<span data-ttu-id="7ef72-166">Para remover um fragmento de um slot ou contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-166">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="7ef72-167">No painel de estrutura de tópicos à esquerda, selecione as reticências (**...**) ao lado do nome do fragmento a ser removido e, depois, selecione o símbolo de lixeira.</span><span class="sxs-lookup"><span data-stu-id="7ef72-167">In the outline pane on the left, select the ellipsis (**...**) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="7ef72-168">Como alternativa, você pode selecionar o fragmento na tela e selecionar o símbolo de lixeira na barra de ferramentas do fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-168">Alternately, you can select the fragment in the canvas and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="7ef72-169">Quando for solicitado para confirmar se você deseja remover o fragmento, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-169">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="7ef72-170">Ao remover um fragmento de uma página, você apenas remove a referência a ele dessa página.</span><span class="sxs-lookup"><span data-stu-id="7ef72-170">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="7ef72-171">Você **não** exclui o fragmento de seu site.</span><span class="sxs-lookup"><span data-stu-id="7ef72-171">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="7ef72-172">Para excluir fragmentos de seu site, você deve usar a interface de usuário (UI) do inspetor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-172">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="7ef72-173">Você pode excluir fragmentos do site apenas se não forem referidos atualmente por quaisquer páginas, modelos, ou por outros fragmentos.</span><span class="sxs-lookup"><span data-stu-id="7ef72-173">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="7ef72-174">Editar um fragmento</span><span class="sxs-lookup"><span data-stu-id="7ef72-174">Edit a fragment</span></span>

<span data-ttu-id="7ef72-175">Para editar fragmentos, você deve usar a interface de usuário do editor de fragmento.</span><span class="sxs-lookup"><span data-stu-id="7ef72-175">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="7ef72-176">Esta restrição é por design.</span><span class="sxs-lookup"><span data-stu-id="7ef72-176">This restriction is by design.</span></span> <span data-ttu-id="7ef72-177">Isso ajuda a garantir que os autores não confundam o processo de edição dos módulos de uma página específica com o processo de edição de fragmentos que podem ser compartilhados em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-177">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="7ef72-178">Para editar um fragmento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-178">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="7ef72-179">No painel de navegação à esquerda, selecione **Fragmentos**.</span><span class="sxs-lookup"><span data-stu-id="7ef72-179">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="7ef72-180">Em **Fragmentos**, selecione o fragmento para editar.</span><span class="sxs-lookup"><span data-stu-id="7ef72-180">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="7ef72-181">Edite as propriedades e a estrutura do módulo do fragmento, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ef72-181">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="7ef72-182">O processo se assemelha ao processo de edição dos módulos que são editados na visualização do editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="7ef72-182">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="7ef72-183">Você também pode editar um fragmento selecionando-o em uma página, em um modelo ou em um fragmento pai e, em seguida, selecionando **Editar Fragmento** no painel propriedades à direita.</span><span class="sxs-lookup"><span data-stu-id="7ef72-183">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ef72-184">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7ef72-184">Additional resources</span></span>

[<span data-ttu-id="7ef72-185">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="7ef72-185">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="7ef72-186">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="7ef72-186">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="7ef72-187">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="7ef72-187">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="7ef72-188">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="7ef72-188">Work with publish groups</span></span>](publish-groups.md)
