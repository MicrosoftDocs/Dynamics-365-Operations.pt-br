---
title: Criar um modelo de configuração do produto
description: Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 199ee5cd20a064bc6e1fd480f52c9c01ced8b1ba
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844744"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="daf81-103">Criar um modelo de configuração do produto</span><span class="sxs-lookup"><span data-stu-id="daf81-103">Create a product configuration model</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="daf81-104">Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="daf81-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="daf81-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="daf81-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="daf81-106">Criar um modelo de produto</span><span class="sxs-lookup"><span data-stu-id="daf81-106">Create a product model</span></span>
1. <span data-ttu-id="daf81-107">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="daf81-108">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="daf81-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="daf81-109">Click New.</span></span>
4. <span data-ttu-id="daf81-110">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-110">In the Name field, type a value.</span></span>
5. <span data-ttu-id="daf81-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="daf81-112">No campo Estratégia do agente de resolução, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="daf81-112">In the Solver strategy field, select an option.</span></span>
    * <span data-ttu-id="daf81-113">A estratégia do agente de resolução determina como as restrições no modelo de configuração de produto baseada em restrições são processadas.</span><span class="sxs-lookup"><span data-stu-id="daf81-113">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="daf81-114">A seleção pode ter impacto sobre o desempenho do modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-114">This selection can have an impact on the performance of the product configuration model.</span></span>  
7. <span data-ttu-id="daf81-115">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="daf81-116">O componente raiz representa o modelo de configuração de produto, mas ele pode ser usado em outros modelos de produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-116">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
8. <span data-ttu-id="daf81-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="daf81-117">Click OK.</span></span>
9. <span data-ttu-id="daf81-118">No campo Reutilizar configurações, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="daf81-118">In the Reuse configurations field, select an option.</span></span>
    * <span data-ttu-id="daf81-119">Se o parâmetro de reutilização de configurações for definido como Sim, o sistema verificará se há configurações idênticas após a sessão de configuração e fará o reuso quando uma combinação exata for encontrada.</span><span class="sxs-lookup"><span data-stu-id="daf81-119">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="daf81-120">Adicionar atributos</span><span class="sxs-lookup"><span data-stu-id="daf81-120">Add attributes</span></span>
1. <span data-ttu-id="daf81-121">Expanda a seção Atributos.</span><span class="sxs-lookup"><span data-stu-id="daf81-121">Expand the Attributes section.</span></span>
2. <span data-ttu-id="daf81-122">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="daf81-122">Click Add.</span></span>
3. <span data-ttu-id="daf81-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daf81-123">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="daf81-124">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-124">In the Name field, type a value.</span></span>
5. <span data-ttu-id="daf81-125">No campo Nome do agente de resolução, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-125">In the Solver name field, type a value.</span></span>
    * <span data-ttu-id="daf81-126">O nome do agente de resolução é usado pelo agente de resolução de restrição do configurador de produtos.</span><span class="sxs-lookup"><span data-stu-id="daf81-126">The Solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="daf81-127">Ele não deve incluir espaços ou caracteres especiais, exceto _ (sublinhado).</span><span class="sxs-lookup"><span data-stu-id="daf81-127">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="daf81-128">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-128">In the Description field, type a value.</span></span>
    * <span data-ttu-id="daf81-129">O texto de descrição é exibido ao usuário da configuração e, portanto, pode ajudar na seleção do valor de atributo correto.</span><span class="sxs-lookup"><span data-stu-id="daf81-129">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="daf81-130">No campo Tipo de atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-130">In the Attribute type field, enter or select a value.</span></span>
    * <span data-ttu-id="daf81-131">O tipo de atributo determina quais valores estão disponíveis para o atributo.</span><span class="sxs-lookup"><span data-stu-id="daf81-131">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="daf81-132">Marque a caixa de seleção Incluir em reutilização.</span><span class="sxs-lookup"><span data-stu-id="daf81-132">Select the Include in reuse check box.</span></span>
    * <span data-ttu-id="daf81-133">Essa opção só está disponível quando a opção Reutilizar configurações for selecionada.</span><span class="sxs-lookup"><span data-stu-id="daf81-133">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="daf81-134">A inclusão do atributo na caixa de seleção de reutilização significa que esse atributo será considerado quando o sistema estiver à procura de uma combinação exata.</span><span class="sxs-lookup"><span data-stu-id="daf81-134">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="daf81-135">Adicionar subcomponentes</span><span class="sxs-lookup"><span data-stu-id="daf81-135">Add subcomponents</span></span>
1. <span data-ttu-id="daf81-136">Expanda a seção Subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="daf81-136">Expand the Subcomponents section.</span></span>
2. <span data-ttu-id="daf81-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="daf81-137">Click Add.</span></span>
3. <span data-ttu-id="daf81-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="daf81-138">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="daf81-139">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-139">In the Name field, type a value.</span></span>
5. <span data-ttu-id="daf81-140">No campo Nome do agente de resolução, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-140">In the Solver name field, type a value.</span></span>
6. <span data-ttu-id="daf81-141">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-141">In the Description field, type a value.</span></span>
7. <span data-ttu-id="daf81-142">No campo Componente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-142">In the Component field, enter or select a value.</span></span>
    * <span data-ttu-id="daf81-143">Cada subcomponente deve fazer referência a uma definição de componente.</span><span class="sxs-lookup"><span data-stu-id="daf81-143">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="daf81-144">Esse design oferece suporte a componentes reutilizáveis e garante que, após ser definido, o componente possa ser usado em muitos modelos de produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-144">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="daf81-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="daf81-145">Click Save.</span></span>
9. <span data-ttu-id="daf81-146">Clique em Detalhes da linha de BOM.</span><span class="sxs-lookup"><span data-stu-id="daf81-146">Click BOM line details.</span></span>
    * <span data-ttu-id="daf81-147">O formulário Detalhes da linha de BOM permite que o usuário selecione as propriedades necessárias para o subcomponente.</span><span class="sxs-lookup"><span data-stu-id="daf81-147">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="daf81-148">Cada propriedade pode receber um valor fixo ou mapeada para um atributo.</span><span class="sxs-lookup"><span data-stu-id="daf81-148">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="daf81-149">O mapeamento para um atributo resultará na propriedade de linha de BOM obtendo diferentes valores conforme a seleção de configuração.</span><span class="sxs-lookup"><span data-stu-id="daf81-149">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="daf81-150">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="daf81-150">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="daf81-151">Cada subcomponente representa um produto mestre configurável com a tecnologia de configuração baseada em restrições.</span><span class="sxs-lookup"><span data-stu-id="daf81-151">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="daf81-152">A referência é feita por meio do número do item.</span><span class="sxs-lookup"><span data-stu-id="daf81-152">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="daf81-153">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="daf81-153">Select the Set check box.</span></span>
12. <span data-ttu-id="daf81-154">Selecione Sim no campo Cálculo.</span><span class="sxs-lookup"><span data-stu-id="daf81-154">Select Yes in the Calculation field.</span></span>
    * <span data-ttu-id="daf81-155">Definir a opção de cálculo garante que o produto será incluído ao executar um cálculo de custo para o produto.</span><span class="sxs-lookup"><span data-stu-id="daf81-155">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="daf81-156">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="daf81-156">Click the Setup tab.</span></span>
14. <span data-ttu-id="daf81-157">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="daf81-157">Select the Set check box.</span></span>
15. <span data-ttu-id="daf81-158">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="daf81-158">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="daf81-159">O campo quantidade determina o quanto desse produto será consumido no produto configurado.</span><span class="sxs-lookup"><span data-stu-id="daf81-159">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="daf81-160">Marque a caixa de seleção Definir.</span><span class="sxs-lookup"><span data-stu-id="daf81-160">Select the Set check box.</span></span>
17. <span data-ttu-id="daf81-161">No campo Por série, insira um número.</span><span class="sxs-lookup"><span data-stu-id="daf81-161">In the Per series field, enter a number.</span></span>
18. <span data-ttu-id="daf81-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="daf81-162">Click OK.</span></span>

