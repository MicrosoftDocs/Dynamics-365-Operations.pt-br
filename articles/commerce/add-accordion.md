---
title: Módulo de acordeão
description: Este tópico abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: a08441f5dffa9c2c65b304d0265dd107a838a685
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206598"
---
# <a name="accordion-module"></a><span data-ttu-id="e0f4a-103">Módulo de Accordion</span><span class="sxs-lookup"><span data-stu-id="e0f4a-103">Accordion module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e0f4a-104">Este tópico abrange os módulos de acordeão e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-104">This topic covers accordion modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e0f4a-105">Os módulos de acordeão são como contêineres usados para organizar as informações ou os módulos em uma página, com capacidade semelhante a uma gaveta recolhível.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-105">Accordion modules are container-like modules that are used to organize the information or modules on a page by providing a collapsible drawer-like capability.</span></span> <span data-ttu-id="e0f4a-106">Um módulo de acordeão pode ser usado em qualquer página.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-106">An accordion module can be used on any page.</span></span>

<span data-ttu-id="e0f4a-107">Dentro de cada módulo de acordeão, um ou mais módulos de item acordeão podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-107">Inside every accordion module, one or more accordion item modules can be added.</span></span> <span data-ttu-id="e0f4a-108">Cada módulo de item de acordeão representa uma gaveta recolhível.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-108">Each accordion item module represents a collapsible drawer.</span></span> <span data-ttu-id="e0f4a-109">Dentro de cada módulo de item de acordeão, um ou mais módulos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-109">Inside every accordion item module, one or more modules can be added.</span></span> <span data-ttu-id="e0f4a-110">Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de acordeão.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-110">There are no restrictions on the types of modules that can be added to an accordion item module.</span></span>

<span data-ttu-id="e0f4a-111">A imagem a seguir mostra um exemplo de um módulo de acordeão usado para organizar informações na página perguntas frequentes de uma loja.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-111">The following image shows an example of an accordion module that is used to organize information on a store's frequently asked questions (FAQ) page.</span></span>

![Exemplo de um módulo de acordeão](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a><span data-ttu-id="e0f4a-113">Propriedades do módulo de acordeão</span><span class="sxs-lookup"><span data-stu-id="e0f4a-113">Accordion module properties</span></span>

| <span data-ttu-id="e0f4a-114">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="e0f4a-114">Property name</span></span> | <span data-ttu-id="e0f4a-115">Valores</span><span class="sxs-lookup"><span data-stu-id="e0f4a-115">Values</span></span> | <span data-ttu-id="e0f4a-116">descrição</span><span class="sxs-lookup"><span data-stu-id="e0f4a-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="e0f4a-117">Título</span><span class="sxs-lookup"><span data-stu-id="e0f4a-117">Heading</span></span> | <span data-ttu-id="e0f4a-118">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f4a-118">Text</span></span> | <span data-ttu-id="e0f4a-119">Esta propriedade especifica um cabeçalho de texto opcional para o módulo de acordeão.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-119">This property specifies an optional text heading for the accordion module.</span></span> |
| <span data-ttu-id="e0f4a-120">Expandir Tudo</span><span class="sxs-lookup"><span data-stu-id="e0f4a-120">Expand All</span></span> | <span data-ttu-id="e0f4a-121">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="e0f4a-121">**True** or **False**</span></span> | <span data-ttu-id="e0f4a-122">Se o valor estiver definido como **verdadeiro**, a funcionalidade expandir/recolher será ativada para que todos os itens no módulo de acordeão possam ser expandidos e recolhidos.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-122">If the value is set to **True**, expand/collapse functionality is turned on, so that all items in the accordion module can be expanded and collapsed.</span></span> |
| <span data-ttu-id="e0f4a-123">Estilo de interação</span><span class="sxs-lookup"><span data-stu-id="e0f4a-123">Interaction Style</span></span> | <span data-ttu-id="e0f4a-124">**Independente** ou **Expandir somente um item**</span><span class="sxs-lookup"><span data-stu-id="e0f4a-124">**Independent** or **Expand one item only**</span></span> | <span data-ttu-id="e0f4a-125">Esta propriedade define o estilo de interação para itens do acordeão.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-125">This property defines the style of interaction for accordion items.</span></span> <span data-ttu-id="e0f4a-126">Se o valor estiver definido como **Independente**, cada item de acordeão poderá ser expandido ou recolhido de forma independente.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-126">If the value is set to **Independent**, each accordion item can be expanded or collapsed independently.</span></span> <span data-ttu-id="e0f4a-127">Se o valor estiver definido como **Expandir somente um item**, apenas um item poderá ser expandido por vez.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-127">If the value is set to **Expand one item only**, only one item can be expanded at a time.</span></span> <span data-ttu-id="e0f4a-128">Conforme os itens são expandidos, os itens expandidos anteriormente são recolhidos.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-128">As items are expanded, previously expanded items are collapsed.</span></span> |

## <a name="accordion-item-module-properties"></a><span data-ttu-id="e0f4a-129">Propriedades do módulo item do acordeão</span><span class="sxs-lookup"><span data-stu-id="e0f4a-129">Accordion item module properties</span></span>

| <span data-ttu-id="e0f4a-130">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="e0f4a-130">Property name</span></span> | <span data-ttu-id="e0f4a-131">Valores</span><span class="sxs-lookup"><span data-stu-id="e0f4a-131">Values</span></span> | <span data-ttu-id="e0f4a-132">descrição</span><span class="sxs-lookup"><span data-stu-id="e0f4a-132">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="e0f4a-133">Cargo</span><span class="sxs-lookup"><span data-stu-id="e0f4a-133">Title</span></span> | <span data-ttu-id="e0f4a-134">Texto</span><span class="sxs-lookup"><span data-stu-id="e0f4a-134">Text</span></span> | <span data-ttu-id="e0f4a-135">Esta propriedade especifica o texto do título para o módulo item do acordeão.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-135">This property specifies the title text for the accordion item module.</span></span> <span data-ttu-id="e0f4a-136">Ao selecionar a região do título, os usuários podem expandir ou recolher a seção.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-136">By selecting the title region, users can expand or collapse the section.</span></span> |
| <span data-ttu-id="e0f4a-137">Expandir por padrão</span><span class="sxs-lookup"><span data-stu-id="e0f4a-137">Expand by default</span></span> | <span data-ttu-id="e0f4a-138">**Verdadeiro** ou **Falso**</span><span class="sxs-lookup"><span data-stu-id="e0f4a-138">**True** or **False**</span></span> | <span data-ttu-id="e0f4a-139">Se o valor for definido como **verdadeiro**, o item do acordeão será expandido por padrão quando a página for carregada.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-139">If the value is set to **True**, the accordion item is expanded by default when the page is loaded.</span></span> |

## <a name="add-an-accordion-module-to-a-faq-page"></a><span data-ttu-id="e0f4a-140">Adicionar um módulo do acordeão a uma página perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="e0f4a-140">Add an accordion module to a FAQ page</span></span>

<span data-ttu-id="e0f4a-141">Para adicionar um módulo de acordeão a uma página perguntas frequentes e definir suas propriedades no assistente para criação de sites, siga as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-141">To add an accordion module to a FAQ page and set its properties in site builder, follow these steps.</span></span>

1. <span data-ttu-id="e0f4a-142">Vá para **Páginas** e use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Perguntas frequentes de loja**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-142">Go to **Pages**, and use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store FAQ**.</span></span>
1. <span data-ttu-id="e0f4a-143">No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-143">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e0f4a-144">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-144">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="e0f4a-145">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-145">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e0f4a-146">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Acordeão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-146">In the **Add Module** dialog box, select the **Accordion** module, and then select **OK**.</span></span>
1. <span data-ttu-id="e0f4a-147">No painel de propriedades do módulo de acordeão, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-147">In the property pane of the accordion module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="e0f4a-148">Na caixa de diálogo **Título**, em **Texto do título**, digite **Perguntas frequentes**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-148">In the **Heading** dialog box, under **Heading Text**, enter **Frequently asked questions**.</span></span> <span data-ttu-id="e0f4a-149">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-149">Then select **OK**.</span></span>
1. <span data-ttu-id="e0f4a-150">No painel de propriedades do módulo de acordeão, marque a caixa de seleção **Mostrar expandir tudo** e, no campo **Estilo de interação**, selecione **Independente**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-150">In the property pane of the accordion module, select the **Show expand all** check box, and then, in the **Interaction style** field, select **Independent**.</span></span>
1. <span data-ttu-id="e0f4a-151">No slot **Acordeão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-151">In the **Accordion** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e0f4a-152">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item do acordeão** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-152">In the **Add Module** dialog box, select the **Accordion item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="e0f4a-153">No painel de propriedades do módulo de item do acordeão, em **Título**, digite o texto do título (por exemplo, **Como os retornos funcionam?**).</span><span class="sxs-lookup"><span data-stu-id="e0f4a-153">In the property pane of the accordion item module, under **Title**, enter title text (for example, **How do returns work?**).</span></span>
1. <span data-ttu-id="e0f4a-154">No slot **Item do acordeão**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-154">In the **Accordion item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="e0f4a-155">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-155">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="e0f4a-156">No painel de propriedades do módulo bloco de texto, insira um parágrafo de texto (por exemplo, **As devoluções devem ser processadas via call center. Contate 1-800-FABRIKAM para devoluções. Os produtos têm uma política de devolução de 30 dias. As devoluções devem ser iniciadas neste intervalo de tempo.**).</span><span class="sxs-lookup"><span data-stu-id="e0f4a-156">In the property pane of the text block module, enter a paragraph of text (for example, **Returns must be processed via the call center. Contact 1-800-FABRIKAM for returns. Products have a 30-day return policy. Returns must be initiated within this time frame.**).</span></span>
1. <span data-ttu-id="e0f4a-157">No slot **Acordeão**, adicione mais alguns módulos de item do acordeão.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-157">In the **Accordion** slot, add a few more accordion item modules.</span></span> <span data-ttu-id="e0f4a-158">Em cada módulo de item do acordeão, adicione um módulo de bloco de texto que tenha conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-158">In each accordion item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="e0f4a-159">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-159">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="e0f4a-160">A página mostrará um módulo de acordeão que tem o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-160">The page will show an accordion module that has the content that you added.</span></span>
1. <span data-ttu-id="e0f4a-161">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="e0f4a-161">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0f4a-162">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e0f4a-162">Additional resources</span></span>

[<span data-ttu-id="e0f4a-163">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="e0f4a-163">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="e0f4a-164">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="e0f4a-164">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="e0f4a-165">Módulo de guia</span><span class="sxs-lookup"><span data-stu-id="e0f4a-165">Tab module</span></span>](add-tab.md)

[<span data-ttu-id="e0f4a-166">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="e0f4a-166">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]