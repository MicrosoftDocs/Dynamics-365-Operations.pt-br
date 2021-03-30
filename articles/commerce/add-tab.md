---
title: Módulo de guia
description: Este tópico abrange os módulos de guia e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 8375c33bd6ffd3004cfc9d7b686d9a0edc77cdef
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209218"
---
# <a name="tab-module"></a><span data-ttu-id="61208-103">Módulo de guia</span><span class="sxs-lookup"><span data-stu-id="61208-103">Tab module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61208-104">Este tópico abrange os módulos de guia e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="61208-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="61208-105">Os módulos de guia são módulos semelhantes aos usados para organizar as informações em uma página de site em guias.</span><span class="sxs-lookup"><span data-stu-id="61208-105">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="61208-106">Eles podem ser usados em qualquer página em que as informações devem ser apresentadas nas guias.</span><span class="sxs-lookup"><span data-stu-id="61208-106">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="61208-107">Em cada módulo de guia, um ou mais módulos de item de guia podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="61208-107">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="61208-108">Cada módulo de item da guia representa uma única guia. Em cada módulo de item de guia, um ou mais módulos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="61208-108">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="61208-109">Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de guia.</span><span class="sxs-lookup"><span data-stu-id="61208-109">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="61208-110">A imagem a seguir mostra um exemplo de um módulo de guia em uma página de site.</span><span class="sxs-lookup"><span data-stu-id="61208-110">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="61208-111">Neste exemplo, a guia **Remessa** foi selecionada.</span><span class="sxs-lookup"><span data-stu-id="61208-111">In this example, the **Shipping** tab selected.</span></span>

![Exemplo de um módulo de guia](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="61208-113">Propriedades do módulo de guia</span><span class="sxs-lookup"><span data-stu-id="61208-113">Tab module properties</span></span>

| <span data-ttu-id="61208-114">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="61208-114">Property name</span></span> | <span data-ttu-id="61208-115">Valores</span><span class="sxs-lookup"><span data-stu-id="61208-115">Values</span></span> | <span data-ttu-id="61208-116">descrição</span><span class="sxs-lookup"><span data-stu-id="61208-116">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="61208-117">Título</span><span class="sxs-lookup"><span data-stu-id="61208-117">Heading</span></span> | <span data-ttu-id="61208-118">Texto</span><span class="sxs-lookup"><span data-stu-id="61208-118">Text</span></span> | <span data-ttu-id="61208-119">Esta propriedade especifica um cabeçalho de texto opcional para o módulo de guia.</span><span class="sxs-lookup"><span data-stu-id="61208-119">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="61208-120">Índice da Guia Ativo</span><span class="sxs-lookup"><span data-stu-id="61208-120">Active Tab Index</span></span> | <span data-ttu-id="61208-121">Número</span><span class="sxs-lookup"><span data-stu-id="61208-121">Number</span></span> | <span data-ttu-id="61208-122">Esta propriedade especifica a guia que deve estar ativa por padrão quando uma página é carregada.</span><span class="sxs-lookup"><span data-stu-id="61208-122">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="61208-123">Se nenhum valor for fornecido, o primeiro item da guia ficará ativo por padrão.</span><span class="sxs-lookup"><span data-stu-id="61208-123">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="61208-124">Propriedades do módulo de item de guia</span><span class="sxs-lookup"><span data-stu-id="61208-124">Tab item module properties</span></span>

| <span data-ttu-id="61208-125">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="61208-125">Property name</span></span> | <span data-ttu-id="61208-126">Valores</span><span class="sxs-lookup"><span data-stu-id="61208-126">Values</span></span> | <span data-ttu-id="61208-127">descrição</span><span class="sxs-lookup"><span data-stu-id="61208-127">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="61208-128">Cargo</span><span class="sxs-lookup"><span data-stu-id="61208-128">Title</span></span> | <span data-ttu-id="61208-129">Texto</span><span class="sxs-lookup"><span data-stu-id="61208-129">Text</span></span> | <span data-ttu-id="61208-130">Esta propriedade especifica o texto do título para o módulo de item de guia.</span><span class="sxs-lookup"><span data-stu-id="61208-130">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="61208-131">Adicionar um módulo de guia a uma página</span><span class="sxs-lookup"><span data-stu-id="61208-131">Add a tab module to a page</span></span>

<span data-ttu-id="61208-132">Para adicionar um módulo de guia a uma página e definir as propriedades, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="61208-132">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="61208-133">Use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Página Armazenar políticas**.</span><span class="sxs-lookup"><span data-stu-id="61208-133">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="61208-134">No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61208-134">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61208-135">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61208-135">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61208-136">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61208-136">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61208-137">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Guia** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61208-137">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61208-138">No painel de propriedades do módulo de guia, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="61208-138">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="61208-139">Na caixa de diálogo **Título**, em **Texto do Título**, insira o texto do título (por exemplo, **Políticas**).</span><span class="sxs-lookup"><span data-stu-id="61208-139">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="61208-140">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="61208-140">Then select **OK**.</span></span>
1. <span data-ttu-id="61208-141">No slot **Guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61208-141">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61208-142">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item da guia** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61208-142">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61208-143">No painel de propriedades do módulo de item de guia, em **Título**, digite o texto do título (por exemplo, **Entrega**).</span><span class="sxs-lookup"><span data-stu-id="61208-143">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="61208-144">No slot **Item de guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61208-144">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61208-145">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61208-145">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61208-146">No painel de propriedades do módulo de bloco de texto, em **Texto rico**, insira um parágrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="61208-146">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="61208-147">No slot **Guia**, adicione mais alguns módulos de itens de guia com títulos.</span><span class="sxs-lookup"><span data-stu-id="61208-147">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="61208-148">Em cada módulo de item de guia, adicione um módulo de bloco de texto que tenha conteúdo.</span><span class="sxs-lookup"><span data-stu-id="61208-148">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="61208-149">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="61208-149">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="61208-150">A página mostrará um módulo de guia que contém módulos de itens de guia com o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="61208-150">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="61208-151">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="61208-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61208-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="61208-152">Additional resources</span></span>

[<span data-ttu-id="61208-153">Visão geral da biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="61208-153">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="61208-154">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="61208-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="61208-155">Módulo de Accordion</span><span class="sxs-lookup"><span data-stu-id="61208-155">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="61208-156">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="61208-156">Text block module</span></span>](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]