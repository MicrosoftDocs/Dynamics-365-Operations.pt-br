---
title: Trabalhar com módulos
description: Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/31/2020
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
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 769d6754fa944830b989d657e0dad9cc42212932
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025870"
---
# <a name="work-with-modules"></a><span data-ttu-id="33f92-103">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="33f92-103">Work with modules</span></span>

<span data-ttu-id="33f92-104">Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="33f92-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>


[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="33f92-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="33f92-105">Overview</span></span>

<span data-ttu-id="33f92-106">Módulos são blocos de construção lógicos que compõem a estrutura da sua página e têm vários objetivos e escopos.</span><span class="sxs-lookup"><span data-stu-id="33f92-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="33f92-107">Alguns módulos são contêineres de alto nível e seu único objetivo é manter e organizar outros módulos (módulos filhos).</span><span class="sxs-lookup"><span data-stu-id="33f92-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="33f92-108">Outros módulos, como um módulo simples de posicionamento de imagem, têm uma finalidade muito específica.</span><span class="sxs-lookup"><span data-stu-id="33f92-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="33f92-109">Outros módulos, como um módulo de carrossel, estão em algum lugar entre essas duas categorias.</span><span class="sxs-lookup"><span data-stu-id="33f92-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="33f92-110">Por padrão, seu site do Dynamics 365 Commerce contém uma biblioteca de módulos do kit de início que permite alcançar os cenários mais básicos de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="33f92-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="33f92-111">Você poderá criar um site de comércio eletrônico completo apenas usando esses módulos.</span><span class="sxs-lookup"><span data-stu-id="33f92-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="33f92-112">No entanto, você também pode querer personalizar esses módulos ou criar novos módulos personalizados para necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="33f92-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="33f92-113">Se quiser construir módulos personalizados, um SDK (Kit de Desenvolvimento de Software para criação de módulo) está disponível para ajudá-lo a criar uma biblioteca de módulos personalizados.</span><span class="sxs-lookup"><span data-stu-id="33f92-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="33f92-114">Módulos e slots de contêiner</span><span class="sxs-lookup"><span data-stu-id="33f92-114">Container modules and slots</span></span>

<span data-ttu-id="33f92-115">Como mencionado anteriormente, alguns módulos são projetados para conter módulos filhos.</span><span class="sxs-lookup"><span data-stu-id="33f92-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="33f92-116">Esse módulos são conhecidos como *contêineres*, e permitem hierarquias de módulos aninhadas.</span><span class="sxs-lookup"><span data-stu-id="33f92-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="33f92-117">Os módulos do contêiner contém *slots*.</span><span class="sxs-lookup"><span data-stu-id="33f92-117">Container modules include *slots*.</span></span> <span data-ttu-id="33f92-118">Os slots são usados para manipular o layout e a finalidade dos módulos filhos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="33f92-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="33f92-119">Um exemplo é um módulo básico de contêiner de página (um módulo de nível superior para qualquer página) que define vários slots importantes:</span><span class="sxs-lookup"><span data-stu-id="33f92-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="33f92-120">Um slot de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="33f92-120">A header slot</span></span>
- <span data-ttu-id="33f92-121">Um slot de corpo</span><span class="sxs-lookup"><span data-stu-id="33f92-121">A body slot</span></span>
- <span data-ttu-id="33f92-122">Um slot de rodapé</span><span class="sxs-lookup"><span data-stu-id="33f92-122">A footer slot</span></span>

<span data-ttu-id="33f92-123">O desenvolvedor do módulo define esses slots e determina quais módulos filhos e quantos módulos filhos podem ser colocados diretamente dentro dele.</span><span class="sxs-lookup"><span data-stu-id="33f92-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="33f92-124">Por exemplo, o slot do cabeçalho pode suportar apenas um módulo do tipo **Módulo do Cabeçalho**, enquanto o slot do corpo pode suportar um número ilimitado de módulos de qualquer tipo (exceto outros módulos de contêiner de página).</span><span class="sxs-lookup"><span data-stu-id="33f92-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="33f92-125">Nas ferramentas de criação, os autores de página não precisam saber com antecedência quais módulos podem e não podem ser colocados em cada slot.</span><span class="sxs-lookup"><span data-stu-id="33f92-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="33f92-126">Quando os autores da página selecionam um slot e, em seguida, tentam selecionar um módulo para adicioná-lo, eles veem uma exibição filtrada dos tipos de módulos suportados por esse slot.</span><span class="sxs-lookup"><span data-stu-id="33f92-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="33f92-127">Módulos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="33f92-127">Content modules</span></span>

<span data-ttu-id="33f92-128">Os módulos de conteúdo contêm elementos de conteúdo e mídia, como texto (por exemplo, títulos, parágrafos e links) ou referências de ativos (por exemplo, imagens, vídeo e PDFs).</span><span class="sxs-lookup"><span data-stu-id="33f92-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="33f92-129">Exemplos de tipos típicos de módulos de conteúdo são **Herói**, **Recurso** e **Banner**.</span><span class="sxs-lookup"><span data-stu-id="33f92-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="33f92-130">Os módulos desses três tipos podem conter texto ou mídia e não exigem módulos filhos para tornar algo visível em uma página.</span><span class="sxs-lookup"><span data-stu-id="33f92-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="33f92-131">A maioria das atividades típicas diárias de criação de página e conteúdo envolve módulos de conteúdo, principalmente porque esses módulos definem o conteúdo real que é renderizado em seus módulos de contêiner pai</span><span class="sxs-lookup"><span data-stu-id="33f92-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="33f92-132">Muitos módulos de conteúdo estão disponíveis, e esses módulos geralmente são as últimas partes que você adicionará à hierarquia de módulos aninhados de uma página.</span><span class="sxs-lookup"><span data-stu-id="33f92-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="33f92-133">A ilustração a seguir mostra como os módulos são aninhados nos slots de módulo de contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="33f92-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Aninhando módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="33f92-135">Adicionar ou remover módulos</span><span class="sxs-lookup"><span data-stu-id="33f92-135">Add or remove modules</span></span>

<span data-ttu-id="33f92-136">Os procedimentos a seguir descrevem como adicionar e remover módulos.</span><span class="sxs-lookup"><span data-stu-id="33f92-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="33f92-137">Adicionar um módulo</span><span class="sxs-lookup"><span data-stu-id="33f92-137">Add a module</span></span>

<span data-ttu-id="33f92-138">Para adicionar um módulo a um slot ou contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="33f92-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="33f92-139">No painel de estrutura de tópicos à esquerda, selecione um contêiner ou slot ao qual um módulo filho possa ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="33f92-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33f92-140">O designer do módulo define a lista de tipos de módulos que podem ser adicionados a um slot de módulo específico.</span><span class="sxs-lookup"><span data-stu-id="33f92-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="33f92-141">Os autores de modelos podem refinar as opções permitidas do módulo para ajudar a garantir otimização consistente do mecanismo de pesquisa (SEO) e eficiência de autoria para todas as páginas das páginas criadas a partir de um modelo específico.</span><span class="sxs-lookup"><span data-stu-id="33f92-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="33f92-142">Selecione o botão de reticências (**...**) para o módulo e selecione **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="33f92-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="33f92-143">A caixa de diálogo **Adicionar Módulo** será exibida.</span><span class="sxs-lookup"><span data-stu-id="33f92-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="33f92-144">Essa caixa de diálogo é filtrada automaticamente para mostrar apenas os módulos suportados no contêiner ou no slot selecionado.</span><span class="sxs-lookup"><span data-stu-id="33f92-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="33f92-145">A lista de módulos é determinada pelo modelo da página ou pela definição do módulo do contêiner.</span><span class="sxs-lookup"><span data-stu-id="33f92-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33f92-146">Se um contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Módulo** não ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="33f92-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="33f92-147">Na caixa de diálogo, procure e selecione um módulo para adicionar à sua página.</span><span class="sxs-lookup"><span data-stu-id="33f92-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="33f92-148">**Recurso** e **Herói** são bons tipos de módulo para os iniciantes trabalharem.</span><span class="sxs-lookup"><span data-stu-id="33f92-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="33f92-149">Selecione **OK** para adicionar o módulo selecionado ao contêiner ou slot selecionado em sua página.</span><span class="sxs-lookup"><span data-stu-id="33f92-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="33f92-150">Remover um módulo</span><span class="sxs-lookup"><span data-stu-id="33f92-150">Remove a module</span></span>

<span data-ttu-id="33f92-151">Para remover um módulo de um slot ou contêiner de uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="33f92-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="33f92-152">No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do módulo a ser removido e, em seguida, selecione o botão da lixeira.</span><span class="sxs-lookup"><span data-stu-id="33f92-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="33f92-153">Quando for solicitado para confirmar se você deseja remover o módulo, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="33f92-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="33f92-154">Configurar módulos</span><span class="sxs-lookup"><span data-stu-id="33f92-154">Configure modules</span></span>

<span data-ttu-id="33f92-155">Os procedimentos a seguir descrevem como configurar os módulos de conteúdo e contêiner.</span><span class="sxs-lookup"><span data-stu-id="33f92-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="33f92-156">Configurar um módulo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="33f92-156">Configure a content module</span></span>

<span data-ttu-id="33f92-157">Para configurar um módulo de conteúdo em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="33f92-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="33f92-158">No painel da estrutura de tópicos à esquerda, expanda a árvore e selecione qualquer módulo de conteúdo (por exemplo, **Recurso**, **Herói** ou **Banner**).</span><span class="sxs-lookup"><span data-stu-id="33f92-158">In the outline pane on the left, expand the tree and select any content module (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="33f92-159">No painel de propriedades à direita, localize os controles de conteúdo e configurações do módulo.</span><span class="sxs-lookup"><span data-stu-id="33f92-159">In the properties pane on the right, find the module's content and settings controls.</span></span>
1. <span data-ttu-id="33f92-160">Insira propriedades para qualquer controle de módulo desejado.</span><span class="sxs-lookup"><span data-stu-id="33f92-160">Enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="33f92-161">Selecione **Salvar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="33f92-161">Select **Save** in the command bar.</span></span> <span data-ttu-id="33f92-162">Isso também atualizará a tela de exibição.</span><span class="sxs-lookup"><span data-stu-id="33f92-162">This will also refresh the preview canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="33f92-163">Configurar um módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="33f92-163">Configure a container module</span></span>

<span data-ttu-id="33f92-164">Para configurar um módulo de contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="33f92-164">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="33f92-165">Selecione um módulo de contêiner em sua página (por exemplo, um carrossel ou um módulo fluido do contêiner).</span><span class="sxs-lookup"><span data-stu-id="33f92-165">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="33f92-166">No painel de propriedades à direita, expanda os controles aninhados selecionando os cabeçalhos e defina quaisquer valores de controle necessários.</span><span class="sxs-lookup"><span data-stu-id="33f92-166">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="33f92-167">No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do contêiner ou de quaisquer slots dentro do contêiner e, em seguida, selecione **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="33f92-167">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="33f92-168">Em seguida, adicione os módulos filho ao contêiner selecionado.</span><span class="sxs-lookup"><span data-stu-id="33f92-168">Then, add child modules to the selected container.</span></span> <span data-ttu-id="33f92-169">Para obter mais informações, consulte a seção [Trabalhar com módulos](#add-a-module) anterior nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="33f92-169">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="33f92-170">Se vários módulos filho existirem como irmãos um contêiner pai, poderá alterar a ordem de exibição no contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="33f92-170">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="33f92-171">Selecione o botão de reticências para um módulo, e use os botões de seta para cima e a seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="33f92-171">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="33f92-172">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="33f92-172">Additional resources</span></span>

[<span data-ttu-id="33f92-173">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="33f92-173">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="33f92-174">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="33f92-174">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="33f92-175">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="33f92-175">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="33f92-176">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="33f92-176">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="33f92-177">Adicionar um módulo de contêiner a uma página</span><span class="sxs-lookup"><span data-stu-id="33f92-177">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="33f92-178">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="33f92-178">Work with publish groups</span></span>](publish-groups.md)

