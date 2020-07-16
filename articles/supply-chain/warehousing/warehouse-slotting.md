---
title: Slots de depósito
description: Este tópico fornece informações sobre slots de depósito. Os slots de depósito permitem consolidar a demanda por item e unidade de medida de ordens com um status de Encomendado, Reservado ou Liberado. Eles ajudam os gerentes de depósito a planejar de forma inteligente os locais de separação antes de liberar as ordens para o depósito e criar um trabalho de separação.
author: mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: d9080f192db0c59b4b4bc74468491e86ba0b7471
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530342"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="c190c-105">Slots de depósito</span><span class="sxs-lookup"><span data-stu-id="c190c-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c190c-106">Os slots de depósito permitem consolidar a demanda por item e unidade de medida de ordens com um status de *Encomendado*, *Reservado* ou *Liberado*.</span><span class="sxs-lookup"><span data-stu-id="c190c-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="c190c-107">A demanda gerada pode ser aplicada a locais que serão usados para separação, com base na quantidade, unidade, dimensões físicas, locais fixos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="c190c-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="c190c-108">Depois que o plano de slots for estabelecido, o trabalho de reabastecimento poderá ser criado para agregar o valor apropriado de estoque a cada local.</span><span class="sxs-lookup"><span data-stu-id="c190c-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="c190c-109">Esta funcionalidade ajuda os gerentes de depósito a planejar de forma inteligente os locais de separação antes de liberar as ordens para o depósito e criar um trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="c190c-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="c190c-110">Ativar o recurso Slots de depósito</span><span class="sxs-lookup"><span data-stu-id="c190c-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="c190c-111">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="c190c-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="c190c-112">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="c190c-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c190c-113">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="c190c-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c190c-114">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="c190c-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c190c-115">**Nome do recurso:** *Recurso Slots de depósito*</span><span class="sxs-lookup"><span data-stu-id="c190c-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="c190c-116">Configurar slots de depósito</span><span class="sxs-lookup"><span data-stu-id="c190c-116">Set up warehouse slotting</span></span>

<span data-ttu-id="c190c-117">Para usar slots de depósito, é necessário configurar os elementos a seguir no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="c190c-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="c190c-118">Criar níveis de unidade de medida para slots</span><span class="sxs-lookup"><span data-stu-id="c190c-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="c190c-119">Os níveis de unidade de medida permitem que várias unidades de medida sejam agrupadas para fins de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="c190c-120">Por exemplo, se vários tamanhos de caixas são separados na mesma área de separação de caixa, um nível pode ser criado para todos os tamanhos.</span><span class="sxs-lookup"><span data-stu-id="c190c-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="c190c-121">**Uma linha deve ser criada para cada unidade de medida que deve fazer parte do nível.**</span><span class="sxs-lookup"><span data-stu-id="c190c-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="c190c-122">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Slots de níveis da unidade de medida**.</span><span class="sxs-lookup"><span data-stu-id="c190c-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="c190c-123">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c190c-123">Select **New**.</span></span>
1. <span data-ttu-id="c190c-124">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c190c-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="c190c-125">**Nível da unidade de medida:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="c190c-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="c190c-126">**Descrição:** *Cada palete de caixa*</span><span class="sxs-lookup"><span data-stu-id="c190c-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="c190c-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c190c-127">Select **Save**.</span></span>
1. <span data-ttu-id="c190c-128">Na FastTab **Unidades de medida**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c190c-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="c190c-129">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-130">**Unidade:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="c190c-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="c190c-131">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="c190c-132">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c190c-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="c190c-133">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="c190c-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="c190c-134">Selecione **Novo** para adicionar uma segunda linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c190c-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="c190c-135">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-136">**Unidade:** *ea*</span><span class="sxs-lookup"><span data-stu-id="c190c-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="c190c-137">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="c190c-138">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c190c-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="c190c-139">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="c190c-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="c190c-140">Selecione **Novo** para adicionar uma terceira linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c190c-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="c190c-141">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-142">**Unidade:** *PL*</span><span class="sxs-lookup"><span data-stu-id="c190c-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="c190c-143">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="c190c-144">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="c190c-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="c190c-145">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="c190c-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="c190c-146">Selecione **Salvar** para salvar o nível.</span><span class="sxs-lookup"><span data-stu-id="c190c-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="c190c-147">Criar um código de diretiva para slots</span><span class="sxs-lookup"><span data-stu-id="c190c-147">Create a directive code for slotting</span></span>

<span data-ttu-id="c190c-148">Você deve selecionar o código de diretiva que deve ser associado a um modelo.</span><span class="sxs-lookup"><span data-stu-id="c190c-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="c190c-149">Vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.</span><span class="sxs-lookup"><span data-stu-id="c190c-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="c190c-150">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c190c-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c190c-151">No campo **Código de diretiva**, insira *Slots*.</span><span class="sxs-lookup"><span data-stu-id="c190c-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="c190c-152">No campo **Descrição de diretiva**, insira *Slots*.</span><span class="sxs-lookup"><span data-stu-id="c190c-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="c190c-153">Configurar modelos de slots</span><span class="sxs-lookup"><span data-stu-id="c190c-153">Set up slotting templates</span></span>

<span data-ttu-id="c190c-154">Cada modelo de slots controla como o estoque é atribuído a locais para um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="c190c-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="c190c-155">Cada modelo deve incluir uma linha para cada especificação de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="c190c-156">Use os procedimentos desta seção para configurar os modelos de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="c190c-157">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots**.</span><span class="sxs-lookup"><span data-stu-id="c190c-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="c190c-158">Selecione **Novo** para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="c190c-158">Select **New** to create a template.</span></span>

<span data-ttu-id="c190c-159">Em seguida, você deve configurar o cabeçalho do modelo, as especificações de slots e as diretivas de localização, conforme explicado nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="c190c-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="c190c-160">Configurar um cabeçalho de modelo de slots</span><span class="sxs-lookup"><span data-stu-id="c190c-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="c190c-161">No cabeçalho do modelo, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c190c-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="c190c-162">**Modelos de slots:** _61_</span><span class="sxs-lookup"><span data-stu-id="c190c-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="c190c-163">**Descrição:** _61_</span><span class="sxs-lookup"><span data-stu-id="c190c-163">**Description:** _61_</span></span>
    - <span data-ttu-id="c190c-164">**Tipo de demanda:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="c190c-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="c190c-165">Atualmente, *Ordem de venda* é o único tipo de demanda com suporte.</span><span class="sxs-lookup"><span data-stu-id="c190c-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="c190c-166">**Estratégia de demanda:** _Encomendada_</span><span class="sxs-lookup"><span data-stu-id="c190c-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="c190c-167">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="c190c-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="c190c-168">**Encomendado** – a quantidade encomendada completa na ordem de venda deve ser considerada demanda.</span><span class="sxs-lookup"><span data-stu-id="c190c-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="c190c-169">**Reservado** – somente as quantidades de linha de ordem de venda que são reservadas (físicas e encomendadas) devem ser consideradas demandas.</span><span class="sxs-lookup"><span data-stu-id="c190c-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="c190c-170">**Depósito:** _61_</span><span class="sxs-lookup"><span data-stu-id="c190c-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="c190c-171">**Permitir que a demanda de onda use quantidades não reservadas:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="c190c-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="c190c-172">Você também pode especificar uma consulta para restringir o escopo da demanda avaliada.</span><span class="sxs-lookup"><span data-stu-id="c190c-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="c190c-173">Configure especificações de slots para cada modelo</span><span class="sxs-lookup"><span data-stu-id="c190c-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="c190c-174">Para cada modelo criado, siga estas etapas para adicionar uma linha a cada especificação de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="c190c-175">Na FastTab **Detalhes do modelo de slots**, selecione **Novo** para criar uma linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="c190c-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="c190c-176">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-177">**Sequência:** _1_</span><span class="sxs-lookup"><span data-stu-id="c190c-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="c190c-178">**Descrição:** _Local fixo_</span><span class="sxs-lookup"><span data-stu-id="c190c-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="c190c-179">**Quantidade mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="c190c-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="c190c-180">Este campo define a quantidade mínima de demanda necessária para a linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="c190c-181">**Quantidade máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="c190c-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="c190c-182">Este campo define a quantidade máxima de demanda que é válida para a linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="c190c-183">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="c190c-184">Este campo define a unidade de medida à qual as quantidades mínima e máxima se referem.</span><span class="sxs-lookup"><span data-stu-id="c190c-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="c190c-185">**Nível da Unidade de Medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="c190c-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="c190c-186">Este campo define as unidades de medida de demanda que são válidas para a linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="c190c-187">(Para obter mais informações, consulte a seção [Configurar níveis de unidade de medida para slots](#unit-tiers) anteriormente neste tópico.)</span><span class="sxs-lookup"><span data-stu-id="c190c-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="c190c-188">**Atribuir critérios de slot:** _Considerar quantidade_</span><span class="sxs-lookup"><span data-stu-id="c190c-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="c190c-189">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="c190c-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="c190c-190">**Supor vazio** – este sistema deve supor que todos os locais na área de separação estão vazios e não devem verificar esses locais para estoque.</span><span class="sxs-lookup"><span data-stu-id="c190c-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="c190c-191">**Considerar qtd** – o sistema deve verificar os locais na área de separação do estoque e deve manter locais que não estão vazios.</span><span class="sxs-lookup"><span data-stu-id="c190c-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="c190c-192">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="c190c-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="c190c-193">Este campo define a diretiva de localização que é usada para encontrar o local de separação do trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="c190c-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="c190c-194">**Local de excesso:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="c190c-195">Este campo define o local em que o estoque é colocado, caso um local não possa ser encontrado para a quantidade quando a linha é processada.</span><span class="sxs-lookup"><span data-stu-id="c190c-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="c190c-196">**Permitir pausa:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="c190c-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="c190c-197">Quando esta opção for definida como *Sim*, se uma demanda não puder ser encaixada, o trabalho de movimento será criado para retirar o estoque dos locais onde há estoque, mas onde nada foi encaixado.</span><span class="sxs-lookup"><span data-stu-id="c190c-197">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="c190c-198">O modelo será reexecutado.</span><span class="sxs-lookup"><span data-stu-id="c190c-198">The template is then run again.</span></span> <span data-ttu-id="c190c-199">Desta vez, ele ignora o estoque nos locais.</span><span class="sxs-lookup"><span data-stu-id="c190c-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="c190c-200">Essa funcionalidade funciona melhor quando o campo **Atribuir critérios de slot** é definido como _Considerar qtd_.</span><span class="sxs-lookup"><span data-stu-id="c190c-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="c190c-201">**Uso de local fixo:** _Somente localizações fixas do produto_</span><span class="sxs-lookup"><span data-stu-id="c190c-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="c190c-202">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="c190c-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="c190c-203">**Locais fixos e não fixos** – o sistema não deve se limitar a usar apenas locais fixos.</span><span class="sxs-lookup"><span data-stu-id="c190c-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="c190c-204">**Apenas locais fixos do produto** – o sistema deve ter slots apenas para locais fixos do produto.</span><span class="sxs-lookup"><span data-stu-id="c190c-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="c190c-205">**Apenas locais fixos da grade de produto** – o sistema deve ter slots apenas para locais fixos da grade de produto.</span><span class="sxs-lookup"><span data-stu-id="c190c-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="c190c-206">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c190c-206">Select **Save**.</span></span>
1. <span data-ttu-id="c190c-207">Selecione **Novo** para criar uma segunda linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="c190c-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="c190c-208">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-209">**Sequência:** _2_</span><span class="sxs-lookup"><span data-stu-id="c190c-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="c190c-210">**Descrição:** _Outro_</span><span class="sxs-lookup"><span data-stu-id="c190c-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="c190c-211">**Qtd. mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="c190c-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="c190c-212">**Qtd. máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="c190c-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="c190c-213">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="c190c-214">**Nível da unidade de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="c190c-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="c190c-215">**Atribuir critérios de slot:** _Considerar quantidade_</span><span class="sxs-lookup"><span data-stu-id="c190c-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="c190c-216">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="c190c-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="c190c-217">**Local de excesso:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="c190c-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="c190c-218">**Permitir pausa:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="c190c-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="c190c-219">**Usar locais fixos:** _Locais fixos e não fixos_</span><span class="sxs-lookup"><span data-stu-id="c190c-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="c190c-220">Na consulta da segunda linha, você agora especificará os critérios usados para determinar os locais nos quais a demanda da linha pode ser encaixada.</span><span class="sxs-lookup"><span data-stu-id="c190c-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="c190c-221">Selecione a linha em que o campo **Sequência** está definido como *2*.</span><span class="sxs-lookup"><span data-stu-id="c190c-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="c190c-222">Selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="c190c-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="c190c-223">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c190c-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="c190c-224">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-225">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="c190c-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="c190c-226">**Tabela derivada:** *Locais*</span><span class="sxs-lookup"><span data-stu-id="c190c-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="c190c-227">**Campo:** *ID de perfil da localização*</span><span class="sxs-lookup"><span data-stu-id="c190c-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="c190c-228">**Critérios:** *Separar-06* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Separar-06* - *Site de Separação 6*).</span><span class="sxs-lookup"><span data-stu-id="c190c-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="c190c-229">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c190c-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="c190c-230">Configurar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="c190c-230">Set up location directives</span></span>

<span data-ttu-id="c190c-231">Pelo menos uma diretiva de localização deve ser configurada para dar suporte a seleções de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="c190c-232">Use os procedimentos desta seção para configurar uma nova *diretiva de local de reabastecimento* para separações de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="c190c-233">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="c190c-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="c190c-234">No painel esquerdo, no campo **Tipo de ordem de serviço**, selecione *Reabastecimento*.</span><span class="sxs-lookup"><span data-stu-id="c190c-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="c190c-235">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c190c-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c190c-236">No cabeçalho da nova diretiva de localização, no campo **Nome**, insira *Seleção de slots 61*.</span><span class="sxs-lookup"><span data-stu-id="c190c-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="c190c-237">Configurar a FastTab Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="c190c-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="c190c-238">Na FastTab **Diretivas de localização**, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="c190c-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="c190c-239">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="c190c-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="c190c-240">**Tipo de trabalho:** _Separar_</span><span class="sxs-lookup"><span data-stu-id="c190c-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="c190c-241">**Local:** _6_</span><span class="sxs-lookup"><span data-stu-id="c190c-241">**Site:** _6_</span></span>
    - <span data-ttu-id="c190c-242">**Depósito:** _61_</span><span class="sxs-lookup"><span data-stu-id="c190c-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="c190c-243">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="c190c-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="c190c-244">Selecione **Salvar** para disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="c190c-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="c190c-245">Configurar a FastTab Linhas</span><span class="sxs-lookup"><span data-stu-id="c190c-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="c190c-246">Na FastTab **Linhas**, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="c190c-247">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="c190c-247">On the new line, set the following values.</span></span> <span data-ttu-id="c190c-248">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="c190c-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="c190c-249">**Quantidade inicial:** _0_</span><span class="sxs-lookup"><span data-stu-id="c190c-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="c190c-250">**Quantidade final:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="c190c-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="c190c-251">Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="c190c-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="c190c-252">Configurar a FastTab Ações de Diretiva</span><span class="sxs-lookup"><span data-stu-id="c190c-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="c190c-253">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="c190c-254">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="c190c-254">On the new line, set the following values.</span></span> <span data-ttu-id="c190c-255">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="c190c-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="c190c-256">**Nome:** _Massa_</span><span class="sxs-lookup"><span data-stu-id="c190c-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="c190c-257">**Estratégia:** _Nenhuma_</span><span class="sxs-lookup"><span data-stu-id="c190c-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="c190c-258">Selecione **Salvar** para disponibilizar o botão **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="c190c-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="c190c-259">Editar a consulta</span><span class="sxs-lookup"><span data-stu-id="c190c-259">Edit the query</span></span>

1. <span data-ttu-id="c190c-260">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="c190c-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="c190c-261">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c190c-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="c190c-262">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c190c-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c190c-263">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="c190c-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="c190c-264">**Tabela derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="c190c-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="c190c-265">**Campo:** *ID da zona*</span><span class="sxs-lookup"><span data-stu-id="c190c-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="c190c-266">**Critérios:** *Massa* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Massa*.)</span><span class="sxs-lookup"><span data-stu-id="c190c-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="c190c-267">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c190c-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="c190c-268">Cenário</span><span class="sxs-lookup"><span data-stu-id="c190c-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="c190c-269">Configurar o cenário</span><span class="sxs-lookup"><span data-stu-id="c190c-269">Set up the scenario</span></span>

<span data-ttu-id="c190c-270">Para esse cenário, use os dados de exemplo internos e crie os registros descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="c190c-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="c190c-271">Usar os dados de exemplo USMF</span><span class="sxs-lookup"><span data-stu-id="c190c-271">Use the USMF sample data</span></span>

<span data-ttu-id="c190c-272">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="c190c-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="c190c-273">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="c190c-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="c190c-274">Criar demanda</span><span class="sxs-lookup"><span data-stu-id="c190c-274">Create demand</span></span>

<span data-ttu-id="c190c-275">Siga as etapas a seguir para criar a solicitação à qual você aplicará slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="c190c-276">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="c190c-277">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="c190c-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="c190c-278">Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-007_.</span><span class="sxs-lookup"><span data-stu-id="c190c-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="c190c-279">No campo **Depósito**, selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="c190c-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="c190c-280">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c190c-280">Select **OK**.</span></span>
1. <span data-ttu-id="c190c-281">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="c190c-281">The new sales order is opened.</span></span> <span data-ttu-id="c190c-282">Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c190c-283">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c190c-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="c190c-284">**Item:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="c190c-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="c190c-285">**Quantidade:** _20_</span><span class="sxs-lookup"><span data-stu-id="c190c-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="c190c-286">Selecione **Adicionar linha** para adicionar uma nova linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c190c-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="c190c-287">**Item:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="c190c-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="c190c-288">**Quantidade:** _8_</span><span class="sxs-lookup"><span data-stu-id="c190c-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="c190c-289">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c190c-289">Select **Save**.</span></span>
1. <span data-ttu-id="c190c-290">Selecione **Novo** para criar uma segunda ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="c190c-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="c190c-291">Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-008_.</span><span class="sxs-lookup"><span data-stu-id="c190c-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="c190c-292">No campo **Depósito**, selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="c190c-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="c190c-293">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="c190c-293">The new sales order is opened.</span></span> <span data-ttu-id="c190c-294">Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c190c-295">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c190c-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="c190c-296">**Item:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="c190c-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="c190c-297">**Quantidade:** _1_</span><span class="sxs-lookup"><span data-stu-id="c190c-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="c190c-298">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c190c-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="c190c-299">Examine um cenário típico de slots</span><span class="sxs-lookup"><span data-stu-id="c190c-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="c190c-300">Depois que todos os elementos de pré-requisito estiverem em uso, conforme descrito na seção anterior, você estará pronto para testar o recurso, executando cada exercício desta seção.</span><span class="sxs-lookup"><span data-stu-id="c190c-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="c190c-301">Gerar demanda</span><span class="sxs-lookup"><span data-stu-id="c190c-301">Generate demand</span></span>

1. <span data-ttu-id="c190c-302">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots** e selecione o modelo de slots que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="c190c-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="c190c-303">No Painel de Ações, selecione **Gerar demanda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="c190c-304">Este comando avalia toda a demanda que está no sistema e corresponde à consulta do modelo de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="c190c-305">A demanda total em todas as ordens é consolidada em uma linha por quantidade/unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="c190c-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="c190c-306">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="c190c-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="c190c-307">Demanda de slots</span><span class="sxs-lookup"><span data-stu-id="c190c-307">Slotting demand</span></span>

<span data-ttu-id="c190c-308">A *demanda de slots* mostra os resultados da geração de demanda, com base na configuração do modelo de slots.</span><span class="sxs-lookup"><span data-stu-id="c190c-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="c190c-309">No Painel de Ações, selecione **Demanda de slots** para exibir os resultados do comando **Gerar demanda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="c190c-310">As linhas na demanda de slots podem ser editadas.</span><span class="sxs-lookup"><span data-stu-id="c190c-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="c190c-311">Você pode excluir uma linha, adicionar uma nova linha ou editar detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="c190c-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="c190c-312">Você pode editar manualmente a demanda ou pode importá-la de um sistema externo usando o gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="c190c-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="c190c-313">Seja qual for a demanda de slots, ela será usada na próxima etapa, independentemente da origem.</span><span class="sxs-lookup"><span data-stu-id="c190c-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="c190c-314">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="c190c-314">Locate demand</span></span>

<span data-ttu-id="c190c-315">Depois que a demanda for gerada, utilize o comando **Localizar demanda** para gerar o *plano de slots*.</span><span class="sxs-lookup"><span data-stu-id="c190c-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="c190c-316">No Painel de Ações, selecione **Localizar demanda**.</span><span class="sxs-lookup"><span data-stu-id="c190c-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="c190c-317">O processo de slots é executado.</span><span class="sxs-lookup"><span data-stu-id="c190c-317">The slotting process runs.</span></span> <span data-ttu-id="c190c-318">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="c190c-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="c190c-319">Plano de slots</span><span class="sxs-lookup"><span data-stu-id="c190c-319">Slotting plan</span></span>

<span data-ttu-id="c190c-320">O plano de slots mostra o local ao qual cada item/quantidade foi atribuído, se o estouro foi usado, se o trabalho de pausa foi criado e a linha de modelo que foi usada.</span><span class="sxs-lookup"><span data-stu-id="c190c-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="c190c-321">**Qualquer demanda que não possa ser encaixada será realçada em vermelho.**</span><span class="sxs-lookup"><span data-stu-id="c190c-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="c190c-322">No Painel de Ações, selecione **Plano de slots** para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="c190c-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="c190c-323">Criar reabastecimento</span><span class="sxs-lookup"><span data-stu-id="c190c-323">Create replenishment</span></span>

<span data-ttu-id="c190c-324">Após a criação do plano de slots, você deverá criar um *trabalho de reabastecimento*, com base no plano.</span><span class="sxs-lookup"><span data-stu-id="c190c-324">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="c190c-325">No Painel de Ações, selecione **Executar reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="c190c-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="c190c-326">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="c190c-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="c190c-327">Esta mensagem indica o número de cabeçalhos que foram criados para a ID de criação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="c190c-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="c190c-328">As diretivas de localização que serão usadas são identificadas com base no código de diretiva especificado em cada linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="c190c-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="c190c-329">Dicas</span><span class="sxs-lookup"><span data-stu-id="c190c-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="c190c-330">Configurar slots automáticos</span><span class="sxs-lookup"><span data-stu-id="c190c-330">Set up automatic slotting</span></span>

<span data-ttu-id="c190c-331">Quando todos os elementos necessários estiverem ativos, você poderá configurar slots para execução automática seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="c190c-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="c190c-332">Vá para **Gerenciamento de depósito \> Reabastecimento \> Executar slots**.</span><span class="sxs-lookup"><span data-stu-id="c190c-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="c190c-333">Especifique as etapas de slots a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="c190c-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="c190c-334">Selecione uma ou mais das seguintes etapas de slots:</span><span class="sxs-lookup"><span data-stu-id="c190c-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="c190c-335">Gerar demanda</span><span class="sxs-lookup"><span data-stu-id="c190c-335">Generate demand</span></span>
    - <span data-ttu-id="c190c-336">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="c190c-336">Locate demand</span></span>
    - <span data-ttu-id="c190c-337">Criar trabalho de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="c190c-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="c190c-338">As etapas de slots são progressivas.</span><span class="sxs-lookup"><span data-stu-id="c190c-338">The slotting steps are progressive.</span></span> <span data-ttu-id="c190c-339">Se desejar selecionar *Localizar demanda*, primeiro selecione *Gerar demanda*.</span><span class="sxs-lookup"><span data-stu-id="c190c-339">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="c190c-340">Especifique o modelo de slots a ser usado.</span><span class="sxs-lookup"><span data-stu-id="c190c-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="c190c-341">Defina que a recorrência seja executada automaticamente, se desejar.</span><span class="sxs-lookup"><span data-stu-id="c190c-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="c190c-342">Para os exercícios no cenário, **não** configure slots automáticos.</span><span class="sxs-lookup"><span data-stu-id="c190c-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
