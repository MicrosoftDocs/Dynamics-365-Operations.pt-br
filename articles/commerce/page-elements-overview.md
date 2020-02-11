---
title: Glossário do modelo de página
description: Este tópico descreve os diversos elementos usados nas páginas de um site do Microsoft Dynamics 365 Commerce .
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: 0285af2f73a25db3199b3cb089bc0b253a3b3f00
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914855"
---
# <a name="page-model-glossary"></a><span data-ttu-id="e01b8-103">Glossário do modelo de página</span><span class="sxs-lookup"><span data-stu-id="e01b8-103">Page model glossary</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="e01b8-104">Este tópico descreve os diversos elementos usados nas páginas de um site do Microsoft Dynamics 365 Commerce .</span><span class="sxs-lookup"><span data-stu-id="e01b8-104">This topic describes the various elements that are used on the pages of a Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="page-element-definitions"></a><span data-ttu-id="e01b8-105">Definições de elementos de página</span><span class="sxs-lookup"><span data-stu-id="e01b8-105">Page element definitions</span></span>

<span data-ttu-id="e01b8-106">A tabela a seguir fornece um resumo dos termos com os quais você deve se familiarizar quando altera a aparência e o conteúdo do seu site.</span><span class="sxs-lookup"><span data-stu-id="e01b8-106">The following table provides a summary of terms that you should be familiar with when you change the look, feel, and content of your site.</span></span> <span data-ttu-id="e01b8-107">Para explicações e procedimentos mais detalhados, siga os links.</span><span class="sxs-lookup"><span data-stu-id="e01b8-107">For more thorough explanations and procedures, follow the links.</span></span>

| <span data-ttu-id="e01b8-108">Termo</span><span class="sxs-lookup"><span data-stu-id="e01b8-108">Term</span></span> | <span data-ttu-id="e01b8-109">Descrição e notas</span><span class="sxs-lookup"><span data-stu-id="e01b8-109">Description and notes</span></span> |
|------|-----------------------|
| [<span data-ttu-id="e01b8-110">Módulo</span><span class="sxs-lookup"><span data-stu-id="e01b8-110">Module</span></span>](work-with-modules.md) | <p><span data-ttu-id="e01b8-111">**Definição:** Módulos são blocos de construção que podem ser criados e compõem o esqueleto de uma página da web.</span><span class="sxs-lookup"><span data-stu-id="e01b8-111">**Definition:** Modules are building block that can be authored and make up the skeleton of a webpage.</span></span> <span data-ttu-id="e01b8-112">Os exemplos incluem os módulos de cabeçalho, herói e de carrossel.</span><span class="sxs-lookup"><span data-stu-id="e01b8-112">Examples include header, hero, and carousel modules.</span></span></p><p><span data-ttu-id="e01b8-113">**Onde estão selecionados:** Os módulos implantados podem ser selecionados e configurados em vários estágios do fluxo de trabalho de criação do site, como os estágios de criação de modelo, layout, página e fragmento.</span><span class="sxs-lookup"><span data-stu-id="e01b8-113">**Where it's selected:** Deployed modules can be selected and configured in various stages of the site authoring workflow, such as the template, layout, page, and fragment authoring stages.</span></span></p><p><span data-ttu-id="e01b8-114">**Onde são editados:** Os módulos personalizados são criados no código usando o kit de desenvolvimento de software (SDK).</span><span class="sxs-lookup"><span data-stu-id="e01b8-114">**Where it's edited:** Custom modules are created in code by using the software development kit (SDK).</span></span> <span data-ttu-id="e01b8-115">Eles são carregados no seu site, onde ficam disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="e01b8-115">They are then uploaded to your site, where they become available for selection.</span></span></p> |
| <span data-ttu-id="e01b8-116">Propriedade do módulo</span><span class="sxs-lookup"><span data-stu-id="e01b8-116">Module property</span></span> | <p><span data-ttu-id="e01b8-117">**Definição:** Propriedades do módulo são configurações específicas que são definidas pelo módulo.</span><span class="sxs-lookup"><span data-stu-id="e01b8-117">**Definition:** Module properties are specific settings that are defined by the module.</span></span> <span data-ttu-id="e01b8-118">Podem ser editadas nas ferramentas de criação de Comércio eletrônico.</span><span class="sxs-lookup"><span data-stu-id="e01b8-118">They can be edited in the e-Commerce authoring tools.</span></span> <span data-ttu-id="e01b8-119">Por exemplo, as propriedades do módulo são usadas para definir o título e a imagem de plano de fundo de um módulo da faixa.</span><span class="sxs-lookup"><span data-stu-id="e01b8-119">For example, module properties are used to set the heading and background image of a banner module.</span></span></p><p><span data-ttu-id="e01b8-120">**Onde são configuradas:** As propriedades do módulo são selecionadas e configuradas no painel de propriedades que aparece nos ambientes de criação (editores) para modelos, layouts, páginas, fragmentos e configurações de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e01b8-120">**Where it's configured:** Module properties are selected and configured in the property pane that appears in the authoring environments (editors) for templates, layouts, pages, fragments, and app settings.</span></span></p> |
| [<span data-ttu-id="e01b8-121">Modelo</span><span class="sxs-lookup"><span data-stu-id="e01b8-121">Template</span></span>](templates-layouts-overview.md) | <p><span data-ttu-id="e01b8-122">**Definição:** Os modelos definem as combinações e opções de módulos que devem ser usadas para uma categoria de páginas (por exemplo, páginas de marketing, páginas de categorias e páginas de produtos).</span><span class="sxs-lookup"><span data-stu-id="e01b8-122">**Definition:** Templates define the module combinations and options that should be used for a category of pages (for example, marketing pages, category pages, and product pages).</span></span></p><p><span data-ttu-id="e01b8-123">**Onde são selecionados:** Os modelos podem ser selecionados durante fluxos de trabalho de criação de página ou layout.</span><span class="sxs-lookup"><span data-stu-id="e01b8-123">**Where it's selected:** Templates can be selected during page or layout creation workflows.</span></span></p><p><span data-ttu-id="e01b8-124">**Onde são editados:** Os modelos são criados no editor do modelo.</span><span class="sxs-lookup"><span data-stu-id="e01b8-124">**Where it's edited:** Templates are authored in the template editor.</span></span> <span data-ttu-id="e01b8-125">Nenhum código é necessário para criá-los ou modificá-los.</span><span class="sxs-lookup"><span data-stu-id="e01b8-125">No code is required to create or modify them.</span></span></p> |
| [<span data-ttu-id="e01b8-126">Layout</span><span class="sxs-lookup"><span data-stu-id="e01b8-126">Layout</span></span>](templates-layouts-overview.md) | <p><span data-ttu-id="e01b8-127">**Definição:** Os layouts definem a seleção final e a organização dos módulos do conjunto de opções do modelo pai.</span><span class="sxs-lookup"><span data-stu-id="e01b8-127">**Definition:** Layouts define the final selection and arrangement of modules from the parent template's set of options.</span></span> <span data-ttu-id="e01b8-128">Um layout pode ser configurado para uma única página (*layout personalizado*) ou pode ser compartilhado por várias página (*layout predefinido*).</span><span class="sxs-lookup"><span data-stu-id="e01b8-128">A layout can be configured for a single page (*custom layout*), or it can be shared by multiple pages (*preset layout*).</span></span></p><p><span data-ttu-id="e01b8-129">**Onde são selecionados:** Os layouts podem ser selecionados durante a criação da nova página ou quando um layout diferente for necessário para uma página existente.</span><span class="sxs-lookup"><span data-stu-id="e01b8-129">**Where it's selected:** Layouts can be selected during new page creation or when a different layout is required for an existing page.</span></span></p><p><span data-ttu-id="e01b8-130">**Onde são editados:** Os layouts são criados no editor de layout.</span><span class="sxs-lookup"><span data-stu-id="e01b8-130">**Where it's edited:** Layouts are authored in the layout editor.</span></span> <span data-ttu-id="e01b8-131">Nenhum código é necessário para criá-los ou modificá-los.</span><span class="sxs-lookup"><span data-stu-id="e01b8-131">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="e01b8-132">Instância da página</span><span class="sxs-lookup"><span data-stu-id="e01b8-132">Page instance</span></span> | <p><span data-ttu-id="e01b8-133">**Definição:** As instâncias da página definem o conteúdo localizado final específico da página para uma única página.</span><span class="sxs-lookup"><span data-stu-id="e01b8-133">**Definition:** Page instances define the final, page-specific localized content for a single page.</span></span> <span data-ttu-id="e01b8-134">Este conteúdo é derivado dos valores das propriedades do módulo.</span><span class="sxs-lookup"><span data-stu-id="e01b8-134">This content is derived from the values of module properties.</span></span></p><p><span data-ttu-id="e01b8-135">**Onde são selecionadas:** As páginas são selecionadas quando as URLs são atribuídas.</span><span class="sxs-lookup"><span data-stu-id="e01b8-135">**Where it's selected:** Pages are selected when URLs are assigned.</span></span></p><p><span data-ttu-id="e01b8-136">**Onde são editadas:** As páginas são editadas no editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="e01b8-136">**Where it's edited:** Pages are edited in the page editor.</span></span> <span data-ttu-id="e01b8-137">Nenhum código é necessário para criá-los ou modificá-los.</span><span class="sxs-lookup"><span data-stu-id="e01b8-137">No code is required to create or modify them.</span></span></p> |
| [<span data-ttu-id="e01b8-138">Tema</span><span class="sxs-lookup"><span data-stu-id="e01b8-138">Theme</span></span>](select-site-theme.md) | <p><span data-ttu-id="e01b8-139">**Definição:** Os temas definem a Folha de Estilos em Cascata (CSS) e determinam a aparência dos módulos que são renderizados em uma página.</span><span class="sxs-lookup"><span data-stu-id="e01b8-139">**Definition:** Themes define the Cascading Style Sheet (CSS), and determine the look and feel of the modules that are rendered on a page.</span></span></p><p><span data-ttu-id="e01b8-140">**Onde é selecionado:** Depois que um tema é carregado para seu site usando o Microsoft Dynamics Lifecycle Services (LCS), ele pode ser selecionado como uma propriedade do módulo do contêiner da página.</span><span class="sxs-lookup"><span data-stu-id="e01b8-140">**Where it's selected:** After a theme is uploaded to your site by using Microsoft Dynamics Lifecycle Services (LCS), it can be selected as a property of the page container module.</span></span></p><p><span data-ttu-id="e01b8-141">**Onde são editados:** Os temas atualmente são criados e editados usando o SDK.</span><span class="sxs-lookup"><span data-stu-id="e01b8-141">**Where it's edited:** Themes are currently created and edited by using the SDK.</span></span> <span data-ttu-id="e01b8-142">Em seguida, são carregados para seu site usando a LCS.</span><span class="sxs-lookup"><span data-stu-id="e01b8-142">They are then uploaded to your site by using LCS.</span></span></p> |
| [<span data-ttu-id="e01b8-143">Fragmento</span><span class="sxs-lookup"><span data-stu-id="e01b8-143">Fragment</span></span>](work-with-fragments.md) | <p><span data-ttu-id="e01b8-144">**Definição:** Fragmentos são módulos totalmente configurados que possuem conteúdo localizado que pode ser reutilizado e atualizado centralmente em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="e01b8-144">**Definition:** Fragments are fully configured modules that have localized content that can be reused and centrally updated across multiple pages.</span></span> <span data-ttu-id="e01b8-145">Por exemplo, um fragmento criado a partir de um módulo de cabeçalho pode ser usado em todos os modelos e em todas as páginas do site e atualizado centralmente em um único local.</span><span class="sxs-lookup"><span data-stu-id="e01b8-145">For example, a fragment that is created from a header module can be used in all templates and on all pages across your site, and centrally updated in one place.</span></span></p><p><span data-ttu-id="e01b8-146">**Onde são selecionados:** Fragmentos podem ser selecionados onde quer que os módulos possam ser selecionados.</span><span class="sxs-lookup"><span data-stu-id="e01b8-146">**Where it's selected:** Fragments can be selected wherever modules can be selected.</span></span> <span data-ttu-id="e01b8-147">Eles podem ser substituídos por um módulo para ajudar a aumentar a eficiência por meio da criação reutilizável e centralizada.</span><span class="sxs-lookup"><span data-stu-id="e01b8-147">They can be substituted for a module to help increase efficiency through reusable and centralized authoring.</span></span></p><p><span data-ttu-id="e01b8-148">**Onde são editados:** Os fragmentos são editados no editor de fragmentos.</span><span class="sxs-lookup"><span data-stu-id="e01b8-148">**Where it's edited:** Fragments are edited in the fragment editor.</span></span> <span data-ttu-id="e01b8-149">Nenhum código é necessário para criá-los ou modificá-los.</span><span class="sxs-lookup"><span data-stu-id="e01b8-149">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="e01b8-150">URL</span><span class="sxs-lookup"><span data-stu-id="e01b8-150">URL</span></span> | <p><span data-ttu-id="e01b8-151">**Definição:** URLs (Uniform resource locators) são endereços que apontam para páginas da Web ou outras URLs.</span><span class="sxs-lookup"><span data-stu-id="e01b8-151">**Definition:** Uniform resource locators (URLs) are addresses that point to webpages or other URLs.</span></span></p><p><span data-ttu-id="e01b8-152">**Onde são selecionadas:** As URLs são selecionadas sempre os links entre as páginas são necessários.</span><span class="sxs-lookup"><span data-stu-id="e01b8-152">**Where it's selected:** URLs are selected wherever links between pages are required.</span></span></p><p><span data-ttu-id="e01b8-153">**Onde são editadas:** As URLs são editadas no editor de URL.</span><span class="sxs-lookup"><span data-stu-id="e01b8-153">**Where it's edited:** URLs are edited in the URL editor.</span></span> <span data-ttu-id="e01b8-154">Nenhum código é necessário para criá-los ou modificá-los.</span><span class="sxs-lookup"><span data-stu-id="e01b8-154">No code is required to create or modify them.</span></span></p> |
| <span data-ttu-id="e01b8-155">Ativo</span><span class="sxs-lookup"><span data-stu-id="e01b8-155">Asset</span></span> | <p><span data-ttu-id="e01b8-156">**Definição:** Ativos são binários de arquivos que têm uma extensão como .jpg, .docx, .pdf ou .mpg.</span><span class="sxs-lookup"><span data-stu-id="e01b8-156">**Definition:** Assets are file binaries that have an extension such as .jpg, .docx, .pdf, or .mpg.</span></span></p><p><span data-ttu-id="e01b8-157">**Onde são selecionados:** Os ativos são selecionados como propriedades do módulo para módulos que os exigem.</span><span class="sxs-lookup"><span data-stu-id="e01b8-157">**Where it's selected:** Assets are selected as module properties for modules that require them.</span></span></p><p><span data-ttu-id="e01b8-158">**Onde são editados:** Os ativos são carregados e os metadados associados são editados no gerenciador de ativos.</span><span class="sxs-lookup"><span data-stu-id="e01b8-158">**Where it's edited:** Assets are uploaded, and associated metadata is edited in the asset manager.</span></span></p> |

## <a name="additional-resources"></a><span data-ttu-id="e01b8-159">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e01b8-159">Additional resources</span></span>

[<span data-ttu-id="e01b8-160">Maneiras de adicionar conteúdo</span><span class="sxs-lookup"><span data-stu-id="e01b8-160">Ways to add content</span></span>](add-manage-content.md)

[<span data-ttu-id="e01b8-161">Estados de documento e de ciclo de vida</span><span class="sxs-lookup"><span data-stu-id="e01b8-161">Document states and lifecycle</span></span>](document-states-overview.md)

[<span data-ttu-id="e01b8-162">Trabalhar com grupos de publicações</span><span class="sxs-lookup"><span data-stu-id="e01b8-162">Work with publish groups</span></span>](publish-groups.md)

[<span data-ttu-id="e01b8-163">Trabalhar com módulos</span><span class="sxs-lookup"><span data-stu-id="e01b8-163">Work with modules</span></span>](work-with-modules.md)

[<span data-ttu-id="e01b8-164">Trabalhar com fragmentos</span><span class="sxs-lookup"><span data-stu-id="e01b8-164">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="e01b8-165">Visão geral de modelos e layouts</span><span class="sxs-lookup"><span data-stu-id="e01b8-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e01b8-166">Personalizar a navegação do site</span><span class="sxs-lookup"><span data-stu-id="e01b8-166">Customize site navigation</span></span>](customize-site-navigation.md)