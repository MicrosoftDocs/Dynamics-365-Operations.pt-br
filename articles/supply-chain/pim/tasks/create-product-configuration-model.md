---
title: Criar um modelo de configuração do produto
description: Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2cb9e33d7bab6ca9cd378ec40baa796d1a933ece
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921356"
---
# <a name="create-a-product-configuration-model"></a><span data-ttu-id="cf04f-103">Criar um modelo de configuração do produto</span><span class="sxs-lookup"><span data-stu-id="cf04f-103">Create a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="cf04f-104">Este procedimento mostra como criar um modelo de configuração do produto e especificar as informações básicas, como atributos e subcomponentes.</span><span class="sxs-lookup"><span data-stu-id="cf04f-104">This procedure shows how to create a product configuration model and enter basic information such as attributes and subcomponents.</span></span> <span data-ttu-id="cf04f-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="cf04f-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-product-model"></a><span data-ttu-id="cf04f-106">Criar um modelo de produto</span><span class="sxs-lookup"><span data-stu-id="cf04f-106">Create a product model</span></span>

1. <span data-ttu-id="cf04f-107">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="cf04f-108">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-108">Select **New**.</span></span>
1. <span data-ttu-id="cf04f-109">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-109">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="cf04f-110">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-110">In the **Description** field, type a value.</span></span>
1. <span data-ttu-id="cf04f-111">No campo **Estratégia do agente de resolução**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cf04f-111">In the **Solver strategy** field, select an option.</span></span>
    * <span data-ttu-id="cf04f-112">A estratégia do agente de resolução determina como as restrições no modelo de configuração de produto baseada em restrições são processadas.</span><span class="sxs-lookup"><span data-stu-id="cf04f-112">The solver strategy determines how the constraints in a constraint-based product configuration model are processed.</span></span> <span data-ttu-id="cf04f-113">A seleção pode ter impacto sobre o desempenho do modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="cf04f-113">This selection can have an impact on the performance of the product configuration model.</span></span>  
1. <span data-ttu-id="cf04f-114">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-114">In the **Name** field, type a value.</span></span>
    * <span data-ttu-id="cf04f-115">O componente raiz representa o modelo de configuração de produto, mas ele pode ser usado em outros modelos de produto.</span><span class="sxs-lookup"><span data-stu-id="cf04f-115">The root component represents the product configuration model, but it can also be used in other product models.</span></span>  
1. <span data-ttu-id="cf04f-116">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-116">Select **OK**.</span></span>
1. <span data-ttu-id="cf04f-117">No campo **Reutilizar configurações**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cf04f-117">In the **Reuse configurations** field, select an option.</span></span>
    * <span data-ttu-id="cf04f-118">Se o parâmetro de reutilização de configurações for definido como Sim, o sistema verificará se há configurações idênticas após a sessão de configuração e fará o reuso quando uma combinação exata for encontrada.</span><span class="sxs-lookup"><span data-stu-id="cf04f-118">If the reuse configurations parameter is set to Yes, the system will check for identical configurations after each configuration session and reuse if an exact match is found.</span></span>  

## <a name="add-attributes"></a><span data-ttu-id="cf04f-119">Adicionar atributos</span><span class="sxs-lookup"><span data-stu-id="cf04f-119">Add attributes</span></span>

1. <span data-ttu-id="cf04f-120">Expanda a seção **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-120">Expand the **Attributes** section.</span></span>
2. <span data-ttu-id="cf04f-121">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-121">Select **Add**.</span></span>
3. <span data-ttu-id="cf04f-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf04f-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="cf04f-123">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-123">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cf04f-124">No campo **Nome do agente de resolução**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-124">In the **Solver name** field, type a value.</span></span>
    * <span data-ttu-id="cf04f-125">O nome do agente de resolução é usado pelo agente de resolução de restrição do configurador de produtos.</span><span class="sxs-lookup"><span data-stu-id="cf04f-125">The solver name is used by the constraint solver of the product configurator.</span></span> <span data-ttu-id="cf04f-126">Ele não deve incluir espaços ou caracteres especiais, exceto _ (sublinhado).</span><span class="sxs-lookup"><span data-stu-id="cf04f-126">It must not include spaces or special characters except _ (underscore).</span></span>  
6. <span data-ttu-id="cf04f-127">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-127">In the **Description** field, type a value.</span></span>
    * <span data-ttu-id="cf04f-128">O texto de descrição é exibido ao usuário da configuração e, portanto, pode ajudar na seleção do valor de atributo correto.</span><span class="sxs-lookup"><span data-stu-id="cf04f-128">The description text is displayed to the configuration user and can therefore serve as help in selecting the right attribute value.</span></span>  
7. <span data-ttu-id="cf04f-129">No campo **Tipo de atributo** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-129">In the **Attribute type** field, enter or select a value.</span></span>
    * <span data-ttu-id="cf04f-130">O tipo de atributo determina quais valores estão disponíveis para o atributo.</span><span class="sxs-lookup"><span data-stu-id="cf04f-130">The attribute type determines which values are available for the attribute.</span></span>  
8. <span data-ttu-id="cf04f-131">Marque a caixa de seleção **Incluir em reutilização**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-131">Select the **Include in reuse** check box.</span></span>
    * <span data-ttu-id="cf04f-132">Essa opção só está disponível quando a opção Reutilizar configurações for selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf04f-132">This option is only available when the Reuse configurations option is selected.</span></span> <span data-ttu-id="cf04f-133">A inclusão do atributo na caixa de seleção de reutilização significa que esse atributo será considerado quando o sistema estiver à procura de uma combinação exata.</span><span class="sxs-lookup"><span data-stu-id="cf04f-133">Including the attribute in the reuse check box means that this attribute will be considered when the system is looking for an exact match.</span></span>  

## <a name="add-subcomponents"></a><span data-ttu-id="cf04f-134">Adicionar subcomponentes</span><span class="sxs-lookup"><span data-stu-id="cf04f-134">Add subcomponents</span></span>

1. <span data-ttu-id="cf04f-135">Expanda a seção **Subcomponentes**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-135">Expand the **Subcomponents** section.</span></span>
2. <span data-ttu-id="cf04f-136">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-136">Select **Add**.</span></span>
3. <span data-ttu-id="cf04f-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf04f-137">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="cf04f-138">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-138">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="cf04f-139">No campo **Nome do agente de resolução**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-139">In the **Solver name** field, type a value.</span></span>
6. <span data-ttu-id="cf04f-140">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-140">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="cf04f-141">No campo **Componente** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-141">In the **Component** field, enter or select a value.</span></span>
    * <span data-ttu-id="cf04f-142">Cada subcomponente deve fazer referência a uma definição de componente.</span><span class="sxs-lookup"><span data-stu-id="cf04f-142">Each subcomponent must reference a component definition.</span></span> <span data-ttu-id="cf04f-143">Esse design oferece suporte a componentes reutilizáveis e garante que, após ser definido, o componente possa ser usado em muitos modelos de produto.</span><span class="sxs-lookup"><span data-stu-id="cf04f-143">This design supports reusable components and ensures that once a component has been defined it can be used in many product models.</span></span>  
8. <span data-ttu-id="cf04f-144">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-144">Select **Save**.</span></span>
9. <span data-ttu-id="cf04f-145">Selecione **Detalhes da linha de BOM**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-145">Select **BOM line details**.</span></span>
    * <span data-ttu-id="cf04f-146">O formulário Detalhes da linha de BOM permite que o usuário selecione as propriedades necessárias para o subcomponente.</span><span class="sxs-lookup"><span data-stu-id="cf04f-146">The BOM line details form enables the user to select the required properties for the subcomponent.</span></span> <span data-ttu-id="cf04f-147">Cada propriedade pode receber um valor fixo ou mapeada para um atributo.</span><span class="sxs-lookup"><span data-stu-id="cf04f-147">Each property can be given a fixed value or mapped to an attribute.</span></span> <span data-ttu-id="cf04f-148">O mapeamento para um atributo resultará na propriedade de linha de BOM obtendo diferentes valores conforme a seleção de configuração.</span><span class="sxs-lookup"><span data-stu-id="cf04f-148">Mapping to an attribute will result in the BOM line property getting different values depending on the configuration selection.</span></span>  
10. <span data-ttu-id="cf04f-149">No campo **Número do item**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf04f-149">In the **Item number** field, enter or select a value.</span></span>
    * <span data-ttu-id="cf04f-150">Cada subcomponente representa um produto mestre configurável com a tecnologia de configuração baseada em restrições.</span><span class="sxs-lookup"><span data-stu-id="cf04f-150">Each subcomponent represents a configurable product master with constraint-based configuration technology.</span></span> <span data-ttu-id="cf04f-151">A referência é feita por meio do número do item.</span><span class="sxs-lookup"><span data-stu-id="cf04f-151">The reference is made through the item number.</span></span>  
11. <span data-ttu-id="cf04f-152">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-152">Select the **Set** check box.</span></span>
12. <span data-ttu-id="cf04f-153">Selecione **Sim** no campo **Cálculo**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-153">Select **Yes** in the **Calculation** field.</span></span>
    * <span data-ttu-id="cf04f-154">Definir a opção de cálculo garante que o produto será incluído ao executar um cálculo de custo para o produto.</span><span class="sxs-lookup"><span data-stu-id="cf04f-154">Setting the calculation option ensures that the product will be included when running a cost calculation for the product.</span></span>  
13. <span data-ttu-id="cf04f-155">Selecione a guia **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-155">Select the **Setup** tab.</span></span>
14. <span data-ttu-id="cf04f-156">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-156">Select the **Set** check box.</span></span>
15. <span data-ttu-id="cf04f-157">No campo **Quantidade.**, insira um número</span><span class="sxs-lookup"><span data-stu-id="cf04f-157">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="cf04f-158">O campo quantidade determina o quanto desse produto será consumido no produto configurado.</span><span class="sxs-lookup"><span data-stu-id="cf04f-158">The quantity field determines how much of this product will be consumed in the configured product.</span></span>  
16. <span data-ttu-id="cf04f-159">Marque a caixa de seleção **Definir**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-159">Select the **Set** check box.</span></span>
17. <span data-ttu-id="cf04f-160">No campo **Por série**, informe um número.</span><span class="sxs-lookup"><span data-stu-id="cf04f-160">In the **Per series** field, enter a number.</span></span>
18. <span data-ttu-id="cf04f-161">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="cf04f-161">Select **OK**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]