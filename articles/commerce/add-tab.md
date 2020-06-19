---
title: Módulo de guia
description: Este tópico abrange os módulos de guia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 60af9b74f7e647e83229e352a03c09d63d0c7902
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417360"
---
# <a name="tab-module"></a><span data-ttu-id="61708-103">Módulo de guia</span><span class="sxs-lookup"><span data-stu-id="61708-103">Tab module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="61708-104">Este tópico abrange os módulos de guia e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="61708-104">This topic covers tab modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="61708-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="61708-105">Overview</span></span>

<span data-ttu-id="61708-106">Os módulos de guia são módulos semelhantes aos usados para organizar as informações em uma página de site em guias.</span><span class="sxs-lookup"><span data-stu-id="61708-106">Tab modules are container-like modules that are used to organize the information on a site page on tabs.</span></span> <span data-ttu-id="61708-107">Eles podem ser usados em qualquer página em que as informações devem ser apresentadas nas guias.</span><span class="sxs-lookup"><span data-stu-id="61708-107">They can be used on any page where information must be presented on tabs.</span></span>

<span data-ttu-id="61708-108">Em cada módulo de guia, um ou mais módulos de item de guia podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="61708-108">In every tab module, one or more tab item modules can be added.</span></span> <span data-ttu-id="61708-109">Cada módulo de item da guia representa uma única guia. Em cada módulo de item de guia, um ou mais módulos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="61708-109">Each tab item module represents a single tab. In each tab item module, one or more modules can be added.</span></span> <span data-ttu-id="61708-110">Não há restrições quanto aos tipos de módulos que podem ser adicionados a um módulo de item de guia.</span><span class="sxs-lookup"><span data-stu-id="61708-110">There are no restrictions on the types of modules that can be added to a tab item module.</span></span>

<span data-ttu-id="61708-111">A imagem a seguir mostra um exemplo de um módulo de guia em uma página de site.</span><span class="sxs-lookup"><span data-stu-id="61708-111">The following image shows an example of a tab module on a site page.</span></span> <span data-ttu-id="61708-112">Neste exemplo, a guia **Remessa** foi selecionada.</span><span class="sxs-lookup"><span data-stu-id="61708-112">In this example, the **Shipping** tab selected.</span></span>

![Exemplo de um módulo de guia](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a><span data-ttu-id="61708-114">Propriedades do módulo de guia</span><span class="sxs-lookup"><span data-stu-id="61708-114">Tab module properties</span></span>

| <span data-ttu-id="61708-115">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="61708-115">Property name</span></span> | <span data-ttu-id="61708-116">Valores</span><span class="sxs-lookup"><span data-stu-id="61708-116">Values</span></span> | <span data-ttu-id="61708-117">descrição</span><span class="sxs-lookup"><span data-stu-id="61708-117">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="61708-118">Título</span><span class="sxs-lookup"><span data-stu-id="61708-118">Heading</span></span> | <span data-ttu-id="61708-119">Texto</span><span class="sxs-lookup"><span data-stu-id="61708-119">Text</span></span> | <span data-ttu-id="61708-120">Esta propriedade especifica um cabeçalho de texto opcional para o módulo de guia.</span><span class="sxs-lookup"><span data-stu-id="61708-120">This property specifies an optional text heading for the tab module.</span></span> |
| <span data-ttu-id="61708-121">Índice da Guia Ativo</span><span class="sxs-lookup"><span data-stu-id="61708-121">Active Tab Index</span></span> | <span data-ttu-id="61708-122">Número</span><span class="sxs-lookup"><span data-stu-id="61708-122">Number</span></span> | <span data-ttu-id="61708-123">Esta propriedade especifica a guia que deve estar ativa por padrão quando uma página é carregada.</span><span class="sxs-lookup"><span data-stu-id="61708-123">This property specifies the tab that should be active by default when a page is loaded.</span></span> <span data-ttu-id="61708-124">Se nenhum valor for fornecido, o primeiro item da guia ficará ativo por padrão.</span><span class="sxs-lookup"><span data-stu-id="61708-124">If no value is provided, the first tab item is active by default.</span></span> |

## <a name="tab-item-module-properties"></a><span data-ttu-id="61708-125">Propriedades do módulo de item de guia</span><span class="sxs-lookup"><span data-stu-id="61708-125">Tab item module properties</span></span>

| <span data-ttu-id="61708-126">Nome da propriedade</span><span class="sxs-lookup"><span data-stu-id="61708-126">Property name</span></span> | <span data-ttu-id="61708-127">Valores</span><span class="sxs-lookup"><span data-stu-id="61708-127">Values</span></span> | <span data-ttu-id="61708-128">descrição</span><span class="sxs-lookup"><span data-stu-id="61708-128">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="61708-129">Cargo</span><span class="sxs-lookup"><span data-stu-id="61708-129">Title</span></span> | <span data-ttu-id="61708-130">Texto</span><span class="sxs-lookup"><span data-stu-id="61708-130">Text</span></span> | <span data-ttu-id="61708-131">Esta propriedade especifica o texto do título para o módulo de item de guia.</span><span class="sxs-lookup"><span data-stu-id="61708-131">This property specifies the title text for the tab item module.</span></span> |

## <a name="add-a-tab-module-to-a-page"></a><span data-ttu-id="61708-132">Adicionar um módulo de guia a uma página</span><span class="sxs-lookup"><span data-stu-id="61708-132">Add a tab module to a page</span></span>

<span data-ttu-id="61708-133">Para adicionar um módulo de guia a uma página e definir as propriedades, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="61708-133">To add a tab module to a page and set the properties, follow these steps.</span></span>

1. <span data-ttu-id="61708-134">Use o modelo de marketing da Fabrikam (ou qualquer modelo que não tenha restrições) para criar uma nova página denominada **Página Armazenar políticas**.</span><span class="sxs-lookup"><span data-stu-id="61708-134">Use the Fabrikam marketing template (or any template that has no restrictions) to create a new page that is named **Store policies page**.</span></span>
1. <span data-ttu-id="61708-135">No slot **Principal** da **Página padrão**, selecione as reticências (**...**) e, em seguida, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61708-135">In the **Main** slot of the **Default page**, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61708-136">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Contêiner** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61708-136">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61708-137">No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61708-137">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61708-138">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Guia** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61708-138">In the **Add Module** dialog box, select the **Tab** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61708-139">No painel de propriedades do módulo de guia, selecione **Título** ao lado do símbolo de lápis.</span><span class="sxs-lookup"><span data-stu-id="61708-139">In the property pane of the tab module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="61708-140">Na caixa de diálogo **Título**, em **Texto do Título**, insira o texto do título (por exemplo, **Políticas**).</span><span class="sxs-lookup"><span data-stu-id="61708-140">In the **Heading** dialog box, under **Heading Text**, enter heading text (for example, **Policies**).</span></span> <span data-ttu-id="61708-141">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="61708-141">Then select **OK**.</span></span>
1. <span data-ttu-id="61708-142">No slot **Guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61708-142">In the **Tab** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61708-143">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Item da guia** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61708-143">In the **Add Module** dialog box, select the **Tab item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61708-144">No painel de propriedades do módulo de item de guia, em **Título**, digite o texto do título (por exemplo, **Entrega**).</span><span class="sxs-lookup"><span data-stu-id="61708-144">In the property pane of the tab item module, under **Title**, enter title text (for example, **Delivery**).</span></span>
1. <span data-ttu-id="61708-145">No slot **Item de guia**, selecione as reticências (**...**) e, depois, **Adicionar Módulo**.</span><span class="sxs-lookup"><span data-stu-id="61708-145">In the **Tab item** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="61708-146">Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Bloco de texto** e, depois, **OK**.</span><span class="sxs-lookup"><span data-stu-id="61708-146">In the **Add Module** dialog box, select the **Text block** module, and then select **OK**.</span></span>
1. <span data-ttu-id="61708-147">No painel de propriedades do módulo de bloco de texto, em **Texto rico**, insira um parágrafo de texto.</span><span class="sxs-lookup"><span data-stu-id="61708-147">In the property pane of the text block module, under **Rich text**, enter a paragraph of text.</span></span>
1. <span data-ttu-id="61708-148">No slot **Guia**, adicione mais alguns módulos de itens de guia com títulos.</span><span class="sxs-lookup"><span data-stu-id="61708-148">In the **Tab** slot, add a few more tab item modules that have titles.</span></span> <span data-ttu-id="61708-149">Em cada módulo de item de guia, adicione um módulo de bloco de texto que tenha conteúdo.</span><span class="sxs-lookup"><span data-stu-id="61708-149">In each tab item module, add a text block module that has content.</span></span>
1. <span data-ttu-id="61708-150">Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.</span><span class="sxs-lookup"><span data-stu-id="61708-150">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="61708-151">A página mostrará um módulo de guia que contém módulos de itens de guia com o conteúdo adicionado.</span><span class="sxs-lookup"><span data-stu-id="61708-151">The page will show a tab module that contains tab item modules have the content that you added.</span></span>
1. <span data-ttu-id="61708-152">Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.</span><span class="sxs-lookup"><span data-stu-id="61708-152">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61708-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="61708-153">Additional resources</span></span>

[<span data-ttu-id="61708-154">Visão geral do kit de início</span><span class="sxs-lookup"><span data-stu-id="61708-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="61708-155">Módulo de contêiner</span><span class="sxs-lookup"><span data-stu-id="61708-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="61708-156">Módulo de acordeão</span><span class="sxs-lookup"><span data-stu-id="61708-156">Accordion module</span></span>](add-accordion.md)

[<span data-ttu-id="61708-157">Módulo de bloco de texto</span><span class="sxs-lookup"><span data-stu-id="61708-157">Text block module</span></span>](add-content-rich-block.md)
