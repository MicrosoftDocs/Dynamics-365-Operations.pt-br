---
title: Trabalhar com módulos
description: Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801352"
---
# <a name="work-with-modules"></a><span data-ttu-id="f02c7-103">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="f02c7-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f02c7-104">Este tópico descreve como e quando usar os módulos no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f02c7-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f02c7-105">Módulos são blocos de construção lógicos que compõem a estrutura da sua página e têm vários objetivos e escopos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-105">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="f02c7-106">Alguns módulos são contêineres de alto nível e seu único objetivo é manter e organizar outros módulos (módulos filhos).</span><span class="sxs-lookup"><span data-stu-id="f02c7-106">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="f02c7-107">Outros módulos, como um módulo simples de posicionamento de imagem, têm uma finalidade muito específica.</span><span class="sxs-lookup"><span data-stu-id="f02c7-107">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="f02c7-108">Outros módulos, como um módulo de carrossel, estão em algum lugar entre essas duas categorias.</span><span class="sxs-lookup"><span data-stu-id="f02c7-108">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="f02c7-109">Por padrão, seu site do Dynamics 365 Commerce contém uma biblioteca de módulos que permite alcançar os cenários mais básicos de comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f02c7-109">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="f02c7-110">Você poderá criar um site de comércio eletrônico completo apenas usando esses módulos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-110">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="f02c7-111">No entanto, você também pode querer personalizar esses módulos ou criar novos módulos personalizados para necessidades específicas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-111">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="f02c7-112">Se quiser construir módulos personalizados, um SDK (Kit de Desenvolvimento de Software para criação de módulo) está disponível para ajudá-lo a criar uma biblioteca de módulos personalizados.</span><span class="sxs-lookup"><span data-stu-id="f02c7-112">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="f02c7-113">Módulos e slots de contêiner</span><span class="sxs-lookup"><span data-stu-id="f02c7-113">Container modules and slots</span></span>

<span data-ttu-id="f02c7-114">Como mencionado anteriormente, alguns módulos são projetados para conter módulos filhos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-114">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="f02c7-115">Esse módulos são conhecidos como *contêineres*, e permitem hierarquias de módulos aninhadas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-115">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="f02c7-116">Os módulos do contêiner contém *slots*.</span><span class="sxs-lookup"><span data-stu-id="f02c7-116">Container modules include *slots*.</span></span> <span data-ttu-id="f02c7-117">Os slots são usados para manipular o layout e a finalidade dos módulos filhos no contêiner.</span><span class="sxs-lookup"><span data-stu-id="f02c7-117">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="f02c7-118">Um exemplo é um módulo básico de contêiner de página (um módulo de nível superior para qualquer página) que define vários slots importantes:</span><span class="sxs-lookup"><span data-stu-id="f02c7-118">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="f02c7-119">Um slot de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="f02c7-119">A header slot</span></span>
- <span data-ttu-id="f02c7-120">Um slot de subcabeçalho</span><span class="sxs-lookup"><span data-stu-id="f02c7-120">A sub-header slot</span></span>
- <span data-ttu-id="f02c7-121">Um slot principal</span><span class="sxs-lookup"><span data-stu-id="f02c7-121">A main slot</span></span>
- <span data-ttu-id="f02c7-122">Um slot de rodapé</span><span class="sxs-lookup"><span data-stu-id="f02c7-122">A footer slot</span></span>
- <span data-ttu-id="f02c7-123">Um slot de sub-rodapé</span><span class="sxs-lookup"><span data-stu-id="f02c7-123">A sub-footer slot</span></span>

<span data-ttu-id="f02c7-124">O desenvolvedor do módulo define esses slots e determina quais módulos filhos e quantos módulos filhos podem ser colocados diretamente dentro dele.</span><span class="sxs-lookup"><span data-stu-id="f02c7-124">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="f02c7-125">Por exemplo, o slot do cabeçalho pode suportar apenas um módulo do tipo **Módulo do Cabeçalho**, enquanto o slot do corpo pode suportar um número ilimitado de módulos de qualquer tipo (exceto outros módulos de contêiner de página).</span><span class="sxs-lookup"><span data-stu-id="f02c7-125">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="f02c7-126">Nas ferramentas de criação, os autores de página não precisam saber com antecedência quais módulos podem e não podem ser colocados em cada slot.</span><span class="sxs-lookup"><span data-stu-id="f02c7-126">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="f02c7-127">Quando os autores da página selecionam um slot e, em seguida, tentam selecionar um módulo para adicioná-lo, eles veem uma exibição filtrada dos tipos de módulos suportados por esse slot.</span><span class="sxs-lookup"><span data-stu-id="f02c7-127">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="f02c7-128">Módulos de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f02c7-128">Content modules</span></span>

<span data-ttu-id="f02c7-129">Os módulos de conteúdo contêm elementos de conteúdo e mídia, como texto (por exemplo, títulos, parágrafos e links) ou referências de ativos (por exemplo, imagens, vídeo e PDFs).</span><span class="sxs-lookup"><span data-stu-id="f02c7-129">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="f02c7-130">Os tipos de módulos de conteúdo típicos incluem módulos de bloco de conteúdo, bloco de texto e faixa promocional.</span><span class="sxs-lookup"><span data-stu-id="f02c7-130">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="f02c7-131">Os módulos desses três tipos podem conter texto ou mídia e não exigem módulos filhos para tornar algo visível em uma página.</span><span class="sxs-lookup"><span data-stu-id="f02c7-131">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="f02c7-132">A maioria das atividades típicas diárias de criação de página e conteúdo envolve módulos de conteúdo, principalmente porque esses módulos definem o conteúdo real que é renderizado em seus módulos de contêiner pai</span><span class="sxs-lookup"><span data-stu-id="f02c7-132">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="f02c7-133">Muitos módulos de conteúdo estão disponíveis, e esses módulos geralmente são as últimas partes que você adicionará à hierarquia de módulos aninhados de uma página.</span><span class="sxs-lookup"><span data-stu-id="f02c7-133">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="f02c7-134">A ilustração a seguir mostra como os módulos são aninhados nos slots de módulo de contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="f02c7-134">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Aninhando módulos](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="f02c7-136">Adicionar ou remover módulos</span><span class="sxs-lookup"><span data-stu-id="f02c7-136">Add or remove modules</span></span>

<span data-ttu-id="f02c7-137">Os procedimentos a seguir descrevem como adicionar e remover módulos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-137">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="f02c7-138">Adicionar um módulo</span><span class="sxs-lookup"><span data-stu-id="f02c7-138">Add a module</span></span>

<span data-ttu-id="f02c7-139">Para adicionar um módulo a um slot ou contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-139">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-140">No painel de estrutura de tópicos à esquerda ou diretamente na tela principal, selecione um contêiner ou slot ao qual um módulo filho possa ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-140">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f02c7-141">O designer do módulo define a lista de tipos de módulos que podem ser adicionados a um slot de módulo específico.</span><span class="sxs-lookup"><span data-stu-id="f02c7-141">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="f02c7-142">Os autores de modelos podem refinar as opções de módulo permitidas para ajudar a garantir otimização consistente do mecanismo de pesquisa (SEO) e eficiência de autoria para todas as páginas criadas com base em um modelo específico.</span><span class="sxs-lookup"><span data-stu-id="f02c7-142">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="f02c7-143">Ao adicionar um módulo a um slot, a caixa de diálogo **Adicionar Módulo** é filtrada automaticamente para mostrar apenas os módulos com suporte no contêiner ou slot selecionado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-143">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="f02c7-144">Esta lista de módulos permitidos é determinada pelo modelo da página ou pela definição do módulo do contêiner.</span><span class="sxs-lookup"><span data-stu-id="f02c7-144">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="f02c7-145">Se estiver usando o painel de estrutura de tópicos, selecione as reticências (**...**) ao lado do nome do módulo e selecione **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-145">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="f02c7-146">Se estiver usando os controles diretamente na tela, selecione o símbolo de adição (**+**) em um slot vazio ou adjacente ao módulo selecionado no momento e selecione **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-146">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f02c7-147">Se um contêiner ou slot não suportar novos módulos filhos, a opção **Adicionar Módulo** não ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="f02c7-147">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="f02c7-148">Na caixa de diálogo **Adicionar Módulo**, selecione um módulo para adicionar à página.</span><span class="sxs-lookup"><span data-stu-id="f02c7-148">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="f02c7-149">O **bloco de conteúdo** é um bom tipo de módulo para iniciantes.</span><span class="sxs-lookup"><span data-stu-id="f02c7-149">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="f02c7-150">Selecione **OK** para adicionar o módulo selecionado ao contêiner ou slot selecionado em sua página.</span><span class="sxs-lookup"><span data-stu-id="f02c7-150">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="f02c7-151">Remover um módulo</span><span class="sxs-lookup"><span data-stu-id="f02c7-151">Remove a module</span></span>

<span data-ttu-id="f02c7-152">Para remover um módulo de um slot ou contêiner de uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-152">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-153">No painel de estrutura de tópicos à esquerda, selecione as reticências (**...**) ao lado do nome do módulo a ser removido e, depois, selecione o símbolo de lixeira.</span><span class="sxs-lookup"><span data-stu-id="f02c7-153">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="f02c7-154">Como alternativa, na tela principal, você pode selecionar o símbolo da lixeira na barra de ferramentas de um módulo selecionado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-154">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="f02c7-155">Quando for solicitado a confirmar que você deseja remover o módulo, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-155">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="f02c7-156">Mover um módulo para uma nova posição</span><span class="sxs-lookup"><span data-stu-id="f02c7-156">Move a module to a new position</span></span>

<span data-ttu-id="f02c7-157">Para mover um módulo para uma nova posição na página, use um dos métodos a seguir.</span><span class="sxs-lookup"><span data-stu-id="f02c7-157">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="f02c7-158">Mover um módulo usando o painel de estrutura de tópicos</span><span class="sxs-lookup"><span data-stu-id="f02c7-158">Move a module using the outline pane</span></span>

<span data-ttu-id="f02c7-159">Para mover um módulo usando o painel de estrutura de tópicos, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-159">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-160">Selecione e mantenha pressionado o módulo que deseja mover no painel de estrutura de tópicos e, em seguida, arraste o módulo para uma nova posição na estrutura de tópicos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-160">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="f02c7-161">A linha azul na estrutura de tópicos e na tela indica onde o módulo pode ser colocado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-161">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="f02c7-162">Libere o módulo para soltá-lo na nova posição.</span><span class="sxs-lookup"><span data-stu-id="f02c7-162">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="f02c7-163">Mover um módulo diretamente na tela</span><span class="sxs-lookup"><span data-stu-id="f02c7-163">Move a module directly within the canvas</span></span>

<span data-ttu-id="f02c7-164">Para mover um módulo diretamente na tela, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-164">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-165">Selecione o módulo a ser movido na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-165">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="f02c7-166">Selecione um símbolo de seta apontando para cima ou para baixo na barra de ferramentas do módulo e arraste a seta para uma nova posição na página.</span><span class="sxs-lookup"><span data-stu-id="f02c7-166">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="f02c7-167">A linha azul na tela e na estrutura de tópicos indica onde o módulo pode ser colocado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-167">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="f02c7-168">Se um módulo não puder ser movido para cima ou para baixo, esse símbolo de seta ficará esmaecido.</span><span class="sxs-lookup"><span data-stu-id="f02c7-168">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="f02c7-169">Libere o módulo para soltá-lo na nova posição.</span><span class="sxs-lookup"><span data-stu-id="f02c7-169">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="f02c7-170">Mover um módulo usando o menu de reticências</span><span class="sxs-lookup"><span data-stu-id="f02c7-170">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="f02c7-171">Para mover um módulo usando o menu de reticências, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-171">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-172">Selecione um módulo na estrutura de tópicos ou na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-172">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="f02c7-173">Selecione as reticências (**...**) ao lado do nome do módulo no painel de estrutura de tópicos ou na barra de ferramentas do módulo selecionado na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-173">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="f02c7-174">Se o módulo puder ser movido para cima ou para baixo no contêiner ou slot, você verá as opções para **Mover para cima** ou **Mover para baixo**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-174">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="f02c7-175">Selecione a opção de movimentação desejada para mover o módulo para cima ou para baixo em relação aos irmãos.</span><span class="sxs-lookup"><span data-stu-id="f02c7-175">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="f02c7-176">Configurar módulos</span><span class="sxs-lookup"><span data-stu-id="f02c7-176">Configure modules</span></span>

<span data-ttu-id="f02c7-177">Os procedimentos a seguir descrevem como configurar os módulos de conteúdo e contêiner.</span><span class="sxs-lookup"><span data-stu-id="f02c7-177">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="f02c7-178">Configurar um módulo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="f02c7-178">Configure a content module</span></span>

<span data-ttu-id="f02c7-179">Para configurar um módulo de conteúdo em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-179">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-180">No painel da estrutura de tópicos à esquerda, expanda a árvore e selecione qualquer módulo de conteúdo (por exemplo, **Bloco de conteúdo**).</span><span class="sxs-lookup"><span data-stu-id="f02c7-180">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="f02c7-181">Como alternativa, você pode selecionar o módulo na tela principal.</span><span class="sxs-lookup"><span data-stu-id="f02c7-181">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="f02c7-182">No painel de propriedades do módulo, à direita, insira propriedades para os controles de módulo desejados.</span><span class="sxs-lookup"><span data-stu-id="f02c7-182">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="f02c7-183">Na barra de comandos, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-183">On the command bar, select **Save**.</span></span> <span data-ttu-id="f02c7-184">Isso também atualizará a tela de exibição.</span><span class="sxs-lookup"><span data-stu-id="f02c7-184">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="f02c7-185">Editar propriedades de texto do módulo</span><span class="sxs-lookup"><span data-stu-id="f02c7-185">Edit module text properties</span></span>

<span data-ttu-id="f02c7-186">As propriedades de texto do módulo que não são somente leitura podem ser editadas diretamente na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-186">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="f02c7-187">Para editar as propriedades de texto do módulo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-187">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-188">Selecione o controle de texto na tela e coloque o cursor no local onde deseja editar o texto.</span><span class="sxs-lookup"><span data-stu-id="f02c7-188">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="f02c7-189">Insira o conteúdo do seu texto.</span><span class="sxs-lookup"><span data-stu-id="f02c7-189">Enter your text content.</span></span>
1. <span data-ttu-id="f02c7-190">Selecione qualquer local fora do conteúdo do texto para continuar editando outro conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f02c7-190">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="f02c7-191">Seleção de imagem embutida</span><span class="sxs-lookup"><span data-stu-id="f02c7-191">Inline image selection</span></span>

<span data-ttu-id="f02c7-192">As imagens do módulo que não são somente leitura podem ser alteradas diretamente na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-192">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="f02c7-193">Para escolher uma nova imagem para um módulo de conteúdo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-193">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-194">Na tela, clique duas vezes na imagem.</span><span class="sxs-lookup"><span data-stu-id="f02c7-194">In the canvas, double-click the image.</span></span> <span data-ttu-id="f02c7-195">Isso exibirá a janela do seletor de mídia.</span><span class="sxs-lookup"><span data-stu-id="f02c7-195">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="f02c7-196">Localize e selecione uma nova imagem a ser usada e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-196">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="f02c7-197">A nova imagem agora é renderizada na tela.</span><span class="sxs-lookup"><span data-stu-id="f02c7-197">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="f02c7-198">Configurar um módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="f02c7-198">Configure a container module</span></span>

<span data-ttu-id="f02c7-199">Para configurar um módulo de contêiner em uma página, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f02c7-199">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="f02c7-200">Selecione um módulo de contêiner em sua página (por exemplo, um carrossel ou um módulo fluido do contêiner).</span><span class="sxs-lookup"><span data-stu-id="f02c7-200">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="f02c7-201">No painel de propriedades à direita, expanda os controles aninhados selecionando os cabeçalhos e defina quaisquer valores de controle necessários.</span><span class="sxs-lookup"><span data-stu-id="f02c7-201">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="f02c7-202">No painel de estrutura de tópicos à esquerda, selecione o botão de reticências ao lado do nome do contêiner ou de quaisquer slots dentro do contêiner e, em seguida, selecione **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f02c7-202">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="f02c7-203">Em seguida, adicione os módulos filho ao contêiner selecionado.</span><span class="sxs-lookup"><span data-stu-id="f02c7-203">Then, add child modules to the selected container.</span></span> <span data-ttu-id="f02c7-204">Para obter mais informações, consulte a seção [Trabalhar com módulos](#add-a-module) anterior nesse tópico.</span><span class="sxs-lookup"><span data-stu-id="f02c7-204">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="f02c7-205">Se vários módulos filho existirem como irmãos um contêiner pai, poderá alterar a ordem de exibição no contêiner pai.</span><span class="sxs-lookup"><span data-stu-id="f02c7-205">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="f02c7-206">Selecione o botão de reticências para um módulo, e use os botões de seta para cima e a seta para baixo.</span><span class="sxs-lookup"><span data-stu-id="f02c7-206">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f02c7-207">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f02c7-207">Additional resources</span></span>

[<span data-ttu-id="f02c7-208">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="f02c7-208">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="f02c7-209">Trabalhar com modelos</span><span class="sxs-lookup"><span data-stu-id="f02c7-209">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="f02c7-210">Trabalhar com layouts predefinidos</span><span class="sxs-lookup"><span data-stu-id="f02c7-210">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="f02c7-211">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="f02c7-211">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="f02c7-212">Adicionar um módulo de contêiner a uma página</span><span class="sxs-lookup"><span data-stu-id="f02c7-212">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="f02c7-213">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="f02c7-213">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
