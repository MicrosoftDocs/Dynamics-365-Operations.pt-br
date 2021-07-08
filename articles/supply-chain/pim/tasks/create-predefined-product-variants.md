---
title: Criar grades de produtos predefinidas
description: Este procedimento mostra como criar variantes de produto para um produto mestre que usam as combinações de dimensões do produto.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 442a5f5b321833c170cfecc4069e62a1254605cd
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270471"
---
# <a name="predefined-product-variants"></a><span data-ttu-id="36924-103">Grades de produtos predefinidas</span><span class="sxs-lookup"><span data-stu-id="36924-103">Predefined product variants</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a><span data-ttu-id="36924-104">Cenário de exemplo: Criar grades de produtos predefinidas</span><span class="sxs-lookup"><span data-stu-id="36924-104">Example scenario: Create predefined product variants</span></span>

<span data-ttu-id="36924-105">Este cenário de exemplo mostra como criar variantes de produto para um produto mestre usando combinações de dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="36924-105">This example scenario shows how to create product variants for a product master using a combinations of product dimensions.</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="36924-106">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="36924-106">Make demo data available</span></span>

<span data-ttu-id="36924-107">Para seguir este cenário usando os valores sugeridos aqui, você deve ter dados de demonstração instalados e deve selecionar a entidade legal *USMF*.</span><span class="sxs-lookup"><span data-stu-id="36924-107">To follow this scenario using the values suggested here, you must have demo data installed, and you must select the *USMF* legal entity.</span></span>

### <a name="step-1-create-a-product-master"></a><span data-ttu-id="36924-108">Etapa 1: criar um produto mestre</span><span class="sxs-lookup"><span data-stu-id="36924-108">Step 1: Create a product master</span></span>

<span data-ttu-id="36924-109">Para criar um produto mestre:</span><span class="sxs-lookup"><span data-stu-id="36924-109">To create a product master:</span></span>

1. <span data-ttu-id="36924-110">Vá para **Gerenciamento de informações sobre produtos > Produtos > Produtos mestres**.</span><span class="sxs-lookup"><span data-stu-id="36924-110">Go to **Product information management > Products > Product masters**.</span></span>
1. <span data-ttu-id="36924-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="36924-111">Select **New**.</span></span>
1. <span data-ttu-id="36924-112">Se o campo **Número do produto** ainda não mostrar um número, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="36924-112">If the **Product number** field doesn't already show a number, then enter a value.</span></span> <span data-ttu-id="36924-113">Isso só é necessário se nenhuma sequência numérica foi definida para este campo.</span><span class="sxs-lookup"><span data-stu-id="36924-113">This is only required if no number sequence has been set for this field.</span></span>
1. <span data-ttu-id="36924-114">Insira um nome no campo **Nome do produto**.</span><span class="sxs-lookup"><span data-stu-id="36924-114">Enter a name in the **Product name** field.</span></span>
1. <span data-ttu-id="36924-115">No campo **Grupo de dimensões do produto**, selecione o grupo de dimensões do produto *SizeCol* (Tamanho e Cor).</span><span class="sxs-lookup"><span data-stu-id="36924-115">In the **Product dimension group** field, select the product dimension group *SizeCol* (Size and Color).</span></span>
1. <span data-ttu-id="36924-116">Selecione **OK** para criar e abrir o novo produto mestre.</span><span class="sxs-lookup"><span data-stu-id="36924-116">Select **OK** to create and open the new product master.</span></span>

### <a name="step-2-add-product-dimensions"></a><span data-ttu-id="36924-117">Etapa 2: adicionar dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="36924-117">Step 2: Add product dimensions</span></span>

<span data-ttu-id="36924-118">Este exemplo a seguir mostra como inserir manualmente as dimensões do produto.</span><span class="sxs-lookup"><span data-stu-id="36924-118">This example shows how to manually enter product dimensions.</span></span> <span data-ttu-id="36924-119">Você pode optar por selecionar um tamanho, cor ou grupo de estilo que inclui os valores de dimensão de produto que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="36924-119">You can also choose to select a size, color, or style group that includes the product dimension values you want to use.</span></span>

<span data-ttu-id="36924-120">Para adicionar dimensões do produto:</span><span class="sxs-lookup"><span data-stu-id="36924-120">To add product dimensions:</span></span>

1. <span data-ttu-id="36924-121">Com o novo produto mestre ainda aberto, selecione **Dimensões do produto** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="36924-121">With your new product master still open, select **Product dimensions** on the Action Pane.</span></span>
1. <span data-ttu-id="36924-122">Abra a guia **Tamanho** e selecione **Novo** na barra de ferramentas para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="36924-122">Open the **Size** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="36924-123">Faça as seguintes configurações para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="36924-123">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="36924-124">**Tamanho:** Selecione um valor de tamanho.</span><span class="sxs-lookup"><span data-stu-id="36924-124">**Size:** Select a size value.</span></span>
    - <span data-ttu-id="36924-125">**Nome:** – Insira um nome do tamanho.</span><span class="sxs-lookup"><span data-stu-id="36924-125">**Name:** Enter a name for the size.</span></span>
1. <span data-ttu-id="36924-126">Selecione **Novo** na barra de ferramentas e adicione um segundo tamanho à grade com um novo **Tamanho** e **Nome**.</span><span class="sxs-lookup"><span data-stu-id="36924-126">Select **New** on the toolbar and add a second size to the grid with a new **Size** and **Name**.</span></span>
1. <span data-ttu-id="36924-127">Abra a guia **Cores** e selecione **Novo** na barra de ferramentas para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="36924-127">Open the **Colors** tab and select **New** on the toolbar to add a row to the grid.</span></span> <span data-ttu-id="36924-128">Faça as seguintes configurações para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="36924-128">Make the following settings for the new row:</span></span>
    - <span data-ttu-id="36924-129">**Cor:** selecione um valor de cor.</span><span class="sxs-lookup"><span data-stu-id="36924-129">**Color:** Select a color value.</span></span>
    - <span data-ttu-id="36924-130">**Nome:** insira um nome para a cor.</span><span class="sxs-lookup"><span data-stu-id="36924-130">**Name:** Enter a name for the color.</span></span>
1. <span data-ttu-id="36924-131">Selecione **Novo** na barra de ferramentas e adicione uma segunda cor à grade com **Cor** e **Nome** novos.</span><span class="sxs-lookup"><span data-stu-id="36924-131">Select **New** on the toolbar and add a second color to the grid with a new **Color** and **Name**.</span></span>
1. <span data-ttu-id="36924-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="36924-132">Select **Save**.</span></span>
1. <span data-ttu-id="36924-133">Feche a página para retornar ao novo produto mestre.</span><span class="sxs-lookup"><span data-stu-id="36924-133">Close the page to return to your new product master.</span></span>

### <a name="step-3-generate-product-variants"></a><span data-ttu-id="36924-134">Etapa 3: gerar grades de produtos</span><span class="sxs-lookup"><span data-stu-id="36924-134">Step 3: Generate product variants</span></span>

> [!NOTE]
> <span data-ttu-id="36924-135">Esta seção descreve como gerar grades de produto quando o recurso *Aperfeiçoamentos de página sugestões de grade* não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="36924-135">This section describes how to generate product variants when the *Variant suggestions page improvements* feature isn't enabled.</span></span> <span data-ttu-id="36924-136">Consulte a próxima seção para obter detalhes sobre como gerar grades de produto quando esse recurso estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="36924-136">See the next section for details about how to generate product variants when that feature is available.</span></span>

<span data-ttu-id="36924-137">Para gerar grades de produtos:</span><span class="sxs-lookup"><span data-stu-id="36924-137">To generate product variants:</span></span>

1. <span data-ttu-id="36924-138">Com o novo produto mestre ainda aberto, selecione **Grades do produto** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="36924-138">With your new product master still open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="36924-139">Selecione **Sugestões de grade** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="36924-139">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="36924-140">O sistema gera uma lista com todas as combinações possíveis dos tamanhos e cores definidos para o produto.</span><span class="sxs-lookup"><span data-stu-id="36924-140">The system generates a list with all possible combinations of the sizes and colors you defined for the product.</span></span> <span data-ttu-id="36924-141">Escolha **Selecionar tudo** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="36924-141">Select **Select all** on the toolbar.</span></span>
    - <span data-ttu-id="36924-142">Neste exemplo, selecione todas as grades possíveis.</span><span class="sxs-lookup"><span data-stu-id="36924-142">In this example, select all of the possible variants.</span></span> <span data-ttu-id="36924-143">Se você só quiser usar um subconjunto das combinações de dimensão de produto possíveis, marque somente as caixas de seleção necessárias, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="36924-143">If you only want to use a subset of the possible product dimension combinations, select only the required check boxes as needed.</span></span>  
1. <span data-ttu-id="36924-144">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="36924-144">Select **Create**.</span></span>
1. <span data-ttu-id="36924-145">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="36924-145">Select **Save**.</span></span>

## <a name="improved-variant-suggestions"></a><span data-ttu-id="36924-146">Sugestões de grade aprimoradas</span><span class="sxs-lookup"><span data-stu-id="36924-146">Improved variant suggestions</span></span>

<span data-ttu-id="36924-147">O recurso *Aperfeiçoamentos de páginas de sugestões de grade* melhora a página **Sugestões de grade** para tratar das questões de desempenho e usabilidade de empresas que têm um alto número de combinações de dimensões de produtos.</span><span class="sxs-lookup"><span data-stu-id="36924-147">The *Variant suggestions page improvements* feature improves the **Variant suggestions** page to address performance and usability issues for companies that have a high number of product dimension combinations.</span></span> <span data-ttu-id="36924-148">O processo avançado para selecionar os valores de dimensão do produto para os quais gerar sugestões de grade torna mais rápido e fácil identificar e liberar o conjunto relevante de grades de produto.</span><span class="sxs-lookup"><span data-stu-id="36924-148">The enhanced process for selecting the product dimension values for which to generate variant suggestions makes it faster and easier to identify and release the relevant set of product variants.</span></span>

<span data-ttu-id="36924-149">Os aprimoramentos a seguir são adicionados por esse recurso:</span><span class="sxs-lookup"><span data-stu-id="36924-149">The following improvements are added by this feature:</span></span>

- <span data-ttu-id="36924-150">**Geração adiada de sugestões de grade:** a página **Sugestões de grade** não mostra mais sugestões quando você a abre pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="36924-150">**Deferred generation of variant suggestions:** The **Variant suggestions** page no longer shows suggestions when you first open it.</span></span> <span data-ttu-id="36924-151">Em vez disso, você deve escolher explicitamente quais valores serão necessários e, em seguida, selecionar o botão **Sugerir** para gerar as combinações.</span><span class="sxs-lookup"><span data-stu-id="36924-151">Instead, you must explicitly choose which values you will need and then select the **Suggest** button to generate the combinations.</span></span> <span data-ttu-id="36924-152">Isso torna o processo mais visível e interativo.</span><span class="sxs-lookup"><span data-stu-id="36924-152">This makes the process more visible and interactive.</span></span>
- <span data-ttu-id="36924-153">**Seleção de valores de dimensões:** quando você tem vários valores de dimensão, geralmente está interessado em gerar sugestões de grade que incluam apenas alguns deles (como ao introduzir um novo conjunto de cores ou estilos).</span><span class="sxs-lookup"><span data-stu-id="36924-153">**Selection of dimensions values:** When you have many dimension values, you are typically interested in generating variant suggestions that include just a few of them (such as when introducing a new set of colors or styles).</span></span> <span data-ttu-id="36924-154">Com o design aprimorado, você pode selecionar os valores de dimensão para os quais deseja gerar sugestões de grade de produtos.</span><span class="sxs-lookup"><span data-stu-id="36924-154">With the improved design, you can select the dimension values for which you want to generate product variant suggestions.</span></span> <span data-ttu-id="36924-155">Isso aumenta bastante a relevância das variantes sugeridas e melhora o desempenho do sistema e a produtividade do usuário.</span><span class="sxs-lookup"><span data-stu-id="36924-155">This greatly increases the relevance of the suggested variants and improves both system performance and user productivity.</span></span>

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a><span data-ttu-id="36924-156">Habilitar o recurso de aperfeiçoamentos de páginas de sugestões de grade</span><span class="sxs-lookup"><span data-stu-id="36924-156">Turn on the Variant suggestions page improvements feature</span></span>

<span data-ttu-id="36924-157">Para que você possa usar o recurso *Aperfeiçoamentos de página de sugestões de grade*, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="36924-157">Before you can use *Variant suggestions page improvements* feature, it must be turned on in your system.</span></span> <span data-ttu-id="36924-158">Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="36924-158">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="36924-159">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="36924-159">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="36924-160">**Módulo:** *Gerenciamento de informações sobre produtos*</span><span class="sxs-lookup"><span data-stu-id="36924-160">**Module:** *Product information management*</span></span>
- <span data-ttu-id="36924-161">**Nome do recurso:** *Aperfeiçoamentos de página de sugestões de grade*</span><span class="sxs-lookup"><span data-stu-id="36924-161">**Feature name:** *Variant suggestions page improvements*</span></span>

### <a name="work-with-the-improved-variant-suggestions"></a><span data-ttu-id="36924-162">Trabalhar com as sugestões de grade aprimoradas</span><span class="sxs-lookup"><span data-stu-id="36924-162">Work with the improved variant suggestions</span></span>

<span data-ttu-id="36924-163">Para gerar sugestões de grade de produto quando o recurso *Aperfeiçoamentos de página de sugestões de grade* estiver habilitado:</span><span class="sxs-lookup"><span data-stu-id="36924-163">To generate product variant suggestions when the *Variant suggestions page improvements* feature is enabled:</span></span>

1. <span data-ttu-id="36924-164">Abra ou crie um produto mestre e adicione as dimensões de produto necessárias a ele, conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="36924-164">Open or create a product master and add the required product dimensions to it, as described in the previous section.</span></span>
1. <span data-ttu-id="36924-165">Com o produto mestre aberto, selecione **Grades do produto** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="36924-165">With the product master open, select **Product variants** on the Action Pane.</span></span>
1. <span data-ttu-id="36924-166">Selecione **Sugestões de grade** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="36924-166">Select **Variant suggestions** on the Action Pane.</span></span>
1. <span data-ttu-id="36924-167">Selecione os valores que deseja usar para cada uma das dimensões.</span><span class="sxs-lookup"><span data-stu-id="36924-167">Select the values that you want to use for each of the dimensions.</span></span>
1. <span data-ttu-id="36924-168">Na barra de ferramentas superior, selecione **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="36924-168">On the top toolbar, select **Suggest**.</span></span>
1. <span data-ttu-id="36924-169">O sistema gera uma lista com todas as combinações possíveis dos tamanhos e cores selecionados.</span><span class="sxs-lookup"><span data-stu-id="36924-169">The system generates a list with all possible combinations of the sizes and colors you selected.</span></span> <span data-ttu-id="36924-170">Na FastTab **Variantes sugeridas**, marque a caixa de seleção para cada combinação de dimensão de produto que deseja usar ou escolha **Selecionar tudo** na barra de ferramentas para selecionar todas elas.</span><span class="sxs-lookup"><span data-stu-id="36924-170">On the **Suggested variants** FastTab, select the check box for each product dimension combination that you want to use, or select **Select all** on the toolbar to select all of them.</span></span>  
1. <span data-ttu-id="36924-171">Selecione **Criar** para adicionar as grades ao produto mestre atual.</span><span class="sxs-lookup"><span data-stu-id="36924-171">Select **Create** to add the variants to the current product master.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
