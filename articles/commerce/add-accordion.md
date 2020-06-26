---
title: Módulo de acordeão
description: Este tópico abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e06a0e0289e8c0c718aff4beab2c7a6ceb0a8cb1
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417245"
---
# <a name="accordion-module"></a><span data-ttu-id="f7534-103">Módulo de acordeão</span><span class="sxs-lookup"><span data-stu-id="f7534-103">Accordion module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="f7534-104">Este tópico abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f7534-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f7534-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="f7534-105">Overview</span></span>

<span data-ttu-id="f7534-106">Os módulos de acordeão são como contêineres usados para organizar as informações ou os módulos em uma página, com capacidade semelhante a uma gaveta recolhível.</span><span class="sxs-lookup"><span data-stu-id="f7534-106">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="f7534-107">Um módulo de acordeão pode ser usado em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="f7534-107">An accordion module can be used on any page.</span></span>

<span data-ttu-id="f7534-108">Dentro de cada módulo de acordeão, um ou mais módulos de item acordeão podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="f7534-108">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="f7534-109">Cada módulo de item de acordeão representa uma gaveta recolhível.</span><span class="sxs-lookup"><span data-stu-id="f7534-109">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="f7534-110">Dentro de cada módulo de item de acordeão, um ou mais módulos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="f7534-110">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="f7534-111">Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de acordeão.</span><span class="sxs-lookup"><span data-stu-id="f7534-111">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="f7534-112">A imagem a seguir mostra um exemplo de um módulo de acordeão usado para organizar informações na página perguntas frequentes de uma loja.</span><span class="sxs-lookup"><span data-stu-id="f7534-112">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Exemplo de um módulo de acordeão](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="f7534-114">Propriedades do módulo de acordeão</span><span class="sxs-lookup"><span data-stu-id="f7534-114">Accordion module properties</span></span>

| <span data-ttu-id="f7534-115">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="f7534-115">Property name</span></span> | <span data-ttu-id="f7534-116">Valores</span><span class="sxs-lookup"><span data-stu-id="f7534-116">Values</span></span> | <span data-ttu-id="f7534-117">descrição</span><span class="sxs-lookup"><span data-stu-id="f7534-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="f7534-118">Título</span><span class="sxs-lookup"><span data-stu-id="f7534-118">Heading</span></span> | <span data-ttu-id="f7534-119">Texto</span><span class="sxs-lookup"><span data-stu-id="f7534-119">Text</span></span> | <span data-ttu-id="f7534-120">Esta propriedade especifica um cabeçalho de texto opcional para o módulo de acordeão.</span><span class="sxs-lookup"><span data-stu-id="f7534-120">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="f7534-121">Expandir Tudo</span><span class="sxs-lookup"><span data-stu-id="f7534-121">Expand All</span></span> | <span data-ttu-id="f7534-122">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f7534-122">**True** or **False**</span></span> | <span data-ttu-id="f7534-123">Se o valor estiver definido como **verdadeiro**, a funcionalidade expandir/recolher será ativada para que todos os itens no módulo de acordeão possam ser expandidos e recolhidos.</span><span class="sxs-lookup"><span data-stu-id="f7534-123">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="f7534-124">Estilo de interação</span><span class="sxs-lookup"><span data-stu-id="f7534-124">Interaction Style</span></span> | <span data-ttu-id="f7534-125">**Independente** ou **Expandir somente um item**</span><span class="sxs-lookup"><span data-stu-id="f7534-125">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="f7534-126">Esta propriedade define o estilo de interação para itens do acordeão.</span><span class="sxs-lookup"><span data-stu-id="f7534-126">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="f7534-127">Se o valor estiver definido como **Independente**, cada item de acordeão poderá ser expandido ou recolhido de forma independente.</span><span class="sxs-lookup"><span data-stu-id="f7534-127">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="f7534-128">Se o valor estiver definido como **Expandir somente um item**, apenas um item poderá ser expandido por vez.</span><span class="sxs-lookup"><span data-stu-id="f7534-128">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="f7534-129">Conforme os itens são expandidos, os itens expandidos anteriormente são recolhidos.</span><span class="sxs-lookup"><span data-stu-id="f7534-129">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="f7534-130">Propriedades do módulo item do acordeão</span><span class="sxs-lookup"><span data-stu-id="f7534-130">Accordion item module properties</span></span>

| <span data-ttu-id="f7534-131">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="f7534-131">Property name</span></span> | <span data-ttu-id="f7534-132">Valores</span><span class="sxs-lookup"><span data-stu-id="f7534-132">Values</span></span> | <span data-ttu-id="f7534-133">descrição</span><span class="sxs-lookup"><span data-stu-id="f7534-133">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="f7534-134">Cargo</span><span class="sxs-lookup"><span data-stu-id="f7534-134">Title</span></span> | <span data-ttu-id="f7534-135">Texto</span><span class="sxs-lookup"><span data-stu-id="f7534-135">Text</span></span> | <span data-ttu-id="f7534-136">Esta propriedade especifica o texto do título para o módulo item do acordeão.</span><span class="sxs-lookup"><span data-stu-id="f7534-136">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="f7534-137">Ao selecionar a região do título, os usuários podem expandir ou recolher a seção.</span><span class="sxs-lookup"><span data-stu-id="f7534-137">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="f7534-138">Expandir por padrão</span><span class="sxs-lookup"><span data-stu-id="f7534-138">Expand by default</span></span> | <span data-ttu-id="f7534-139">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="f7534-139">**True** or **False**</span></span> | <span data-ttu-id="f7534-140">Se o valor for definido como **verdadeiro**, o item do acordeão será expandido por padrão quando a página for carregada.</span><span class="sxs-lookup"><span data-stu-id="f7534-140">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="f7534-141">Adicionar um módulo do acordeão a uma página perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="f7534-141">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="f7534-142">Para adicionar um módulo de acordeão a uma página perguntas frequentes e definir suas propriedades no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="f7534-142">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="f7534-143">Vá para **Páginas** e use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Perguntas frequentes de loja**.</span><span class="sxs-lookup"><span data-stu-id="f7534-143">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="f7534-144">No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7534-144">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7534-145">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7534-145">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7534-146">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7534-146">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7534-147">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Acordeão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7534-147">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7534-148">No painel de propriedades do módulo de acordeão, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="f7534-148">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="f7534-149">Na caixa de diálogo **Título**, em **Texto do título**, digite **Perguntas frequentes**.</span><span class="sxs-lookup"><span data-stu-id="f7534-149">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="f7534-150">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7534-150">Then select **OK**.</span></span>
1. <span data-ttu-id="f7534-151">No painel de propriedades do módulo de acordeão, marque a caixa de seleção **Mostrar expandir tudo** e, no campo **Estilo de interação**, selecione **Independente**.</span><span class="sxs-lookup"><span data-stu-id="f7534-151">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="f7534-152">No slot **Acordeão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7534-152">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7534-153">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item do acordeão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7534-153">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7534-154">No painel de propriedades do módulo de item do acordeão, em **Título**, digite o texto do título (por exemplo, **Como os retornos funcionam?**).</span><span class="sxs-lookup"><span data-stu-id="f7534-154">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="f7534-155">No slot **Item do acordeão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="f7534-155">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f7534-156">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7534-156">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f7534-157">No painel de propriedades do módulo bloco de texto, insira um parágrafo de texto (por exemplo, **As devoluções devem ser processadas via call center. Contate 1-800-FABRIKAM para devoluções. Os produtos têm uma política de devolução de 30 dias. As devoluções devem ser iniciadas neste intervalo de tempo.**).</span><span class="sxs-lookup"><span data-stu-id="f7534-157">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="f7534-158">No slot **Acordeão**, adicione mais alguns módulos de item do acordeão.</span><span class="sxs-lookup"><span data-stu-id="f7534-158">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="f7534-159">Em cada módulo de item do acordeão, adicione um módulo de bloco de texto que tenha conteúdo.</span><span class="sxs-lookup"><span data-stu-id="f7534-159">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="f7534-160">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="f7534-160">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="f7534-161">A página mostrará um módulo de acordeão que tem o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="f7534-161">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="f7534-162">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="f7534-162">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f7534-163">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f7534-163">Additional resources</span></span>

[<span data-ttu-id="f7534-164">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="f7534-164">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f7534-165">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="f7534-165">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="f7534-166">Módulo de guia</span><span class="sxs-lookup"><span data-stu-id="f7534-166">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="f7534-167">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="f7534-167">Text block module</span></span>](add-content-rich-block.md)