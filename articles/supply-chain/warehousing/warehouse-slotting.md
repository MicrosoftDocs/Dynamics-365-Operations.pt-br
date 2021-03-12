---
title: Slots de depósito
description: Este tópico fornece informações sobre slots de depósito. Os slots de depósito permitem consolidar a demanda por item e unidade de medida de ordens com um status de Encomendado, Reservado ou Liberado. Eles ajudam os gerentes de depósito a planejar de forma inteligente os locais de separação antes de liberar as ordens para o depósito e criar um trabalho de separação.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fb39daba393944471ee5d412b1eb61754843926f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993744"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="efc09-105">Slots de depósito</span><span class="sxs-lookup"><span data-stu-id="efc09-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="efc09-106">Vários recursos de slots de depósito estão disponíveis para ajudar os gerentes de depósito a planejar os locais de separação de forma inteligente antes de liberar as ordens para o depósito e criar um trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="efc09-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="efc09-107">O *Recurso Slots de depósito* permite consolidar a demanda por item e unidade de medida de ordens com um status de *Encomendado*, *Reservado* ou *Liberado*.</span><span class="sxs-lookup"><span data-stu-id="efc09-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="efc09-108">A demanda gerada pode ser aplicada a locais que serão usados para separação, com base na quantidade, unidade, dimensões físicas, locais fixos e muito mais.</span><span class="sxs-lookup"><span data-stu-id="efc09-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="efc09-109">Depois que o plano de slots for estabelecido, o trabalho de reabastecimento poderá ser criado para agregar o valor apropriado de estoque a cada local.</span><span class="sxs-lookup"><span data-stu-id="efc09-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="efc09-110">O recurso *Slots de depósito para ordens de transferência* permite que os gerentes de depósito reabasteçam os locais de separação, com base na demanda de ordens de transferência que ainda não foram liberadas para o depósito.</span><span class="sxs-lookup"><span data-stu-id="efc09-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="efc09-111">Isso garante que os locais de separação incluirão todos os itens necessários para as ordens de transferência após serem liberados para o depósito.</span><span class="sxs-lookup"><span data-stu-id="efc09-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="efc09-112">Esse recurso requer que você também ative o recurso *Slots de depósito*.</span><span class="sxs-lookup"><span data-stu-id="efc09-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="efc09-113">O recurso *Aprimoramentos de alocação de slots de depósito* adiciona uma opção para as linhas de modelo que são usadas pelo recurso *Slots de depósito*.</span><span class="sxs-lookup"><span data-stu-id="efc09-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="efc09-114">A opção permite que o sistema considere o estoque disponível existente em um local de destino.</span><span class="sxs-lookup"><span data-stu-id="efc09-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="efc09-115">Portanto, menos reabastecimentos podem ser gerados para alocação.</span><span class="sxs-lookup"><span data-stu-id="efc09-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="efc09-116">O recurso *Aprimoramentos de alocação de slots de depósito* requer que você também ative o recurso *Slots de depósito*.</span><span class="sxs-lookup"><span data-stu-id="efc09-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="efc09-117">Opcionalmente, ele pode ser usado juntamente com o recurso *Slots de depósito para ordens de transferência*.</span><span class="sxs-lookup"><span data-stu-id="efc09-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="efc09-118">Ativar os recursos de slots de depósito</span><span class="sxs-lookup"><span data-stu-id="efc09-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="efc09-119">Antes de usar esses recursos, eles devem ser ativados em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="efc09-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="efc09-120">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status desses recursos e ativá-los, se necessário.</span><span class="sxs-lookup"><span data-stu-id="efc09-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="efc09-121">Ative os seguintes recursos conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="efc09-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="efc09-122">Recurso de slots de depósito</span><span class="sxs-lookup"><span data-stu-id="efc09-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="efc09-123">Slots de depósito para ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="efc09-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="efc09-124">O recurso *Slots de depósito* deve ser ativado antes desse recurso.</span><span class="sxs-lookup"><span data-stu-id="efc09-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="efc09-125">Aprimoramentos de alocação de slots de depósito</span><span class="sxs-lookup"><span data-stu-id="efc09-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="efc09-126">O recurso *Slots de depósito* deve ser ativado antes desse recurso.</span><span class="sxs-lookup"><span data-stu-id="efc09-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="efc09-127">Configurar slots de depósito</span><span class="sxs-lookup"><span data-stu-id="efc09-127">Set up warehouse slotting</span></span>

<span data-ttu-id="efc09-128">Para usar slots de depósito, é necessário configurar os elementos a seguir no seu sistema:</span><span class="sxs-lookup"><span data-stu-id="efc09-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="efc09-129">Camadas de unidade de medida em slots</span><span class="sxs-lookup"><span data-stu-id="efc09-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="efc09-130">Códigos de diretiva</span><span class="sxs-lookup"><span data-stu-id="efc09-130">Directive codes</span></span>
- <span data-ttu-id="efc09-131">Modelos de slots</span><span class="sxs-lookup"><span data-stu-id="efc09-131">Slotting templates</span></span>
- <span data-ttu-id="efc09-132">Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="efc09-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="efc09-133">Criar níveis de unidade de medida para slots</span><span class="sxs-lookup"><span data-stu-id="efc09-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="efc09-134">Os níveis de unidade de medida permitem que várias unidades de medida sejam agrupadas para fins de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="efc09-135">Por exemplo, se vários tamanhos de caixas são separados na mesma área de separação de caixa, um nível pode ser criado para todos os tamanhos.</span><span class="sxs-lookup"><span data-stu-id="efc09-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="efc09-136">**Uma linha deve ser criada para cada unidade de medida que deve fazer parte do nível.**</span><span class="sxs-lookup"><span data-stu-id="efc09-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="efc09-137">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Slots de níveis da unidade de medida**.</span><span class="sxs-lookup"><span data-stu-id="efc09-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="efc09-138">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="efc09-138">Select **New**.</span></span>
1. <span data-ttu-id="efc09-139">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="efc09-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="efc09-140">**Nível da unidade de medida:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="efc09-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="efc09-141">**Descrição:** *Cada palete de caixa*</span><span class="sxs-lookup"><span data-stu-id="efc09-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="efc09-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efc09-142">Select **Save**.</span></span>
1. <span data-ttu-id="efc09-143">Na FastTab **Unidades de medida**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="efc09-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="efc09-144">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-145">**Unidade:** *Caixa*</span><span class="sxs-lookup"><span data-stu-id="efc09-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="efc09-146">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="efc09-147">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="efc09-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="efc09-148">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="efc09-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="efc09-149">Selecione **Novo** para adicionar uma segunda linha à grade.</span><span class="sxs-lookup"><span data-stu-id="efc09-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="efc09-150">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-151">**Unidade:** *ea*</span><span class="sxs-lookup"><span data-stu-id="efc09-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="efc09-152">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="efc09-153">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="efc09-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="efc09-154">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="efc09-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="efc09-155">Selecione **Novo** para adicionar uma terceira linha à grade.</span><span class="sxs-lookup"><span data-stu-id="efc09-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="efc09-156">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-157">**Unidade:** *PL*</span><span class="sxs-lookup"><span data-stu-id="efc09-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="efc09-158">**Descrição:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="efc09-159">Ele será preenchido automaticamente quando você salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="efc09-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="efc09-160">**Classe de unidade:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="efc09-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="efc09-161">Selecione **Salvar** para salvar o nível.</span><span class="sxs-lookup"><span data-stu-id="efc09-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="efc09-162">Criar um código de diretiva para slots</span><span class="sxs-lookup"><span data-stu-id="efc09-162">Create a directive code for slotting</span></span>

<span data-ttu-id="efc09-163">Você deve selecionar o código de diretiva que deve ser associado a um modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="efc09-164">Vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.</span><span class="sxs-lookup"><span data-stu-id="efc09-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="efc09-165">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="efc09-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="efc09-166">No campo **Código de diretiva**, insira *Slots*.</span><span class="sxs-lookup"><span data-stu-id="efc09-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="efc09-167">No campo **Descrição de diretiva**, insira *Slots*.</span><span class="sxs-lookup"><span data-stu-id="efc09-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="efc09-168">Configurar modelos de slots</span><span class="sxs-lookup"><span data-stu-id="efc09-168">Set up slotting templates</span></span>

<span data-ttu-id="efc09-169">Cada modelo de slots controla como o estoque é atribuído a locais para um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="efc09-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="efc09-170">Cada modelo deve incluir uma linha para cada especificação de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="efc09-171">Use os procedimentos desta seção para configurar os modelos de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="efc09-172">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots**.</span><span class="sxs-lookup"><span data-stu-id="efc09-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="efc09-173">Selecione **Novo** para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-173">Select **New** to create a template.</span></span>

<span data-ttu-id="efc09-174">Em seguida, você deve configurar o cabeçalho do modelo, as especificações de slots e as diretivas de localização, conforme explicado nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="efc09-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="efc09-175">A configuração para alocação para ordens de transferência é semelhante à configuração para alocação para ordens de venda, mas o campo **Ordens de transferência** é definido como *Ordens de transferência* em vez de *Ordem de venda*.</span><span class="sxs-lookup"><span data-stu-id="efc09-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="efc09-176">Configurar o cabeçalho para um modelo de slots de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="efc09-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="efc09-177">No cabeçalho do modelo, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="efc09-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="efc09-178">**Modelos de slots:** _61_</span><span class="sxs-lookup"><span data-stu-id="efc09-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="efc09-179">**Descrição:** _61_</span><span class="sxs-lookup"><span data-stu-id="efc09-179">**Description:** _61_</span></span>
    - <span data-ttu-id="efc09-180">**Tipo de demanda:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="efc09-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="efc09-181">Atualmente, *Ordens de venda* e *Ordens de transferência* são os únicos tipos de demanda compatíveis.</span><span class="sxs-lookup"><span data-stu-id="efc09-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="efc09-182">Você pode selecionar *Ordens de transferência* somente se o recurso *Slots de depósito para ordens de transferência* estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="efc09-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="efc09-183">**Estratégia de demanda:** _Encomendada_</span><span class="sxs-lookup"><span data-stu-id="efc09-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="efc09-184">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="efc09-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="efc09-185">**Encomendado** – a quantidade encomendada completa na ordem de venda deve ser considerada demanda.</span><span class="sxs-lookup"><span data-stu-id="efc09-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="efc09-186">**Reservado** – somente as quantidades de linha de ordem de venda que são reservadas (físicas e encomendadas) devem ser consideradas demandas.</span><span class="sxs-lookup"><span data-stu-id="efc09-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="efc09-187">**Liberado** – A quantidade liberada deve ser considerada demanda.</span><span class="sxs-lookup"><span data-stu-id="efc09-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="efc09-188">**Depósito:** _61_</span><span class="sxs-lookup"><span data-stu-id="efc09-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="efc09-189">**Permitir que a demanda de onda use quantidades não reservadas:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="efc09-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="efc09-190">Você também pode especificar uma consulta para restringir o escopo da demanda avaliada.</span><span class="sxs-lookup"><span data-stu-id="efc09-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="efc09-191">Configure especificações de slots para cada modelo</span><span class="sxs-lookup"><span data-stu-id="efc09-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="efc09-192">Para cada modelo de ordem de venda criado, siga estas etapas para adicionar uma linha a cada especificação de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="efc09-193">Na FastTab **Detalhes do modelo de slots**, selecione **Novo** para criar uma linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="efc09-194">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-195">**Sequência:** _1_</span><span class="sxs-lookup"><span data-stu-id="efc09-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="efc09-196">**Descrição:** _Local fixo_</span><span class="sxs-lookup"><span data-stu-id="efc09-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="efc09-197">**Quantidade mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="efc09-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="efc09-198">Este campo define a quantidade mínima de demanda necessária para a linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="efc09-199">**Quantidade máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="efc09-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="efc09-200">Este campo define a quantidade máxima de demanda que é válida para a linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="efc09-201">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="efc09-202">Este campo define a unidade de medida à qual as quantidades mínima e máxima se referem.</span><span class="sxs-lookup"><span data-stu-id="efc09-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="efc09-203">**Nível da Unidade de Medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="efc09-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="efc09-204">Este campo define as unidades de medida de demanda que são válidas para a linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="efc09-205">(Para obter mais informações, consulte a seção [Configurar níveis de unidade de medida para slots](#unit-tiers) anteriormente neste tópico.)</span><span class="sxs-lookup"><span data-stu-id="efc09-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="efc09-206">**Atribuir critérios de slot:** _Considerar quantidade_</span><span class="sxs-lookup"><span data-stu-id="efc09-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="efc09-207">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="efc09-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="efc09-208">**Supor vazio** – este sistema deve supor que todos os locais na área de separação estão vazios e não devem verificar esses locais para estoque.</span><span class="sxs-lookup"><span data-stu-id="efc09-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="efc09-209">**Considerar qtd** – o sistema deve verificar os locais na área de separação do estoque e deve manter locais que não estão vazios.</span><span class="sxs-lookup"><span data-stu-id="efc09-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="efc09-210">**Considerar disponível** – O sistema deve verificar se algum local de destino contém quantidades não reservadas para o item na linha de demanda.</span><span class="sxs-lookup"><span data-stu-id="efc09-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="efc09-211">Se a quantidade for grande o suficiente para satisfazer pelo menos uma unidade da linha de demanda, o registro do plano de slots gerado é reduzido pela quantidade disponível.</span><span class="sxs-lookup"><span data-stu-id="efc09-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="efc09-212">Por exemplo, se a demanda for de 10 casos e um caso estiver disponível, a demanda localizada será de 9 casos.</span><span class="sxs-lookup"><span data-stu-id="efc09-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="efc09-213">Se a demanda for de 10 casos e cada um estiver disponível, a demanda localizada será de 10 casos.</span><span class="sxs-lookup"><span data-stu-id="efc09-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="efc09-214">Esse valor está disponível apenas quando o recurso *Aprimoramentos de alocação de slots de depósito* está ativado.</span><span class="sxs-lookup"><span data-stu-id="efc09-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="efc09-215">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="efc09-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="efc09-216">Este campo define a diretiva de localização que é usada para encontrar o local de separação do trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="efc09-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="efc09-217">**Local de excesso:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="efc09-218">Este campo define o local em que o estoque é colocado, caso um local não possa ser encontrado para a quantidade quando a linha é processada.</span><span class="sxs-lookup"><span data-stu-id="efc09-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="efc09-219">**Permitir pausa:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="efc09-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="efc09-220">Quando esta opção for definida como *Sim*, se uma demanda não puder ser encaixada, o trabalho de movimento será criado para retirar o estoque dos locais onde há estoque, mas onde nada foi encaixado.</span><span class="sxs-lookup"><span data-stu-id="efc09-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="efc09-221">O modelo será reexecutado.</span><span class="sxs-lookup"><span data-stu-id="efc09-221">The template is then run again.</span></span> <span data-ttu-id="efc09-222">Desta vez, ele ignora o estoque nos locais.</span><span class="sxs-lookup"><span data-stu-id="efc09-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="efc09-223">Essa funcionalidade funciona melhor quando o campo **Atribuir critérios de slot** é definido como _Considerar qtd_.</span><span class="sxs-lookup"><span data-stu-id="efc09-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="efc09-224">**Uso de local fixo:** _Somente localizações fixas do produto_</span><span class="sxs-lookup"><span data-stu-id="efc09-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="efc09-225">Os seguintes valores estão disponíveis neste campo:</span><span class="sxs-lookup"><span data-stu-id="efc09-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="efc09-226">**Locais fixos e não fixos** – o sistema não deve se limitar a usar apenas locais fixos.</span><span class="sxs-lookup"><span data-stu-id="efc09-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="efc09-227">**Apenas locais fixos do produto** – o sistema deve ter slots apenas para locais fixos do produto.</span><span class="sxs-lookup"><span data-stu-id="efc09-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="efc09-228">**Apenas locais fixos da grade de produto** – o sistema deve ter slots apenas para locais fixos da grade de produto.</span><span class="sxs-lookup"><span data-stu-id="efc09-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="efc09-229">Se o modelo de slots contiver pelo menos uma linha em que o campo **Atribuir critérios de slot** for definido como *Considerar disponível*, não serão mais permitidas pausas nas linhas do modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="efc09-230">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efc09-230">Select **Save**.</span></span>
1. <span data-ttu-id="efc09-231">Selecione **Novo** para criar uma segunda linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="efc09-232">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-233">**Sequência:** _2_</span><span class="sxs-lookup"><span data-stu-id="efc09-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="efc09-234">**Descrição:** _Outro_</span><span class="sxs-lookup"><span data-stu-id="efc09-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="efc09-235">**Qtd. mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="efc09-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="efc09-236">**Qtd. máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="efc09-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="efc09-237">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="efc09-238">**Nível da unidade de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="efc09-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="efc09-239">**Atribuir critérios de slot:** _Considerar quantidade_</span><span class="sxs-lookup"><span data-stu-id="efc09-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="efc09-240">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="efc09-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="efc09-241">**Local de excesso:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="efc09-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="efc09-242">**Permitir pausa:** _Sim_</span><span class="sxs-lookup"><span data-stu-id="efc09-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="efc09-243">**Usar locais fixos:** _Locais fixos e não fixos_</span><span class="sxs-lookup"><span data-stu-id="efc09-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="efc09-244">Na consulta da segunda linha, você agora especificará os critérios usados para determinar os locais nos quais a demanda da linha pode ser encaixada.</span><span class="sxs-lookup"><span data-stu-id="efc09-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="efc09-245">Selecione a linha em que o campo **Sequência** está definido como *2*.</span><span class="sxs-lookup"><span data-stu-id="efc09-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="efc09-246">Selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="efc09-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="efc09-247">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="efc09-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="efc09-248">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-249">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="efc09-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="efc09-250">**Tabela derivada:** *Locais*</span><span class="sxs-lookup"><span data-stu-id="efc09-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="efc09-251">**Campo:** *ID de perfil da localização*</span><span class="sxs-lookup"><span data-stu-id="efc09-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="efc09-252">**Critérios:** *Separar-06* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Separar-06* - *Site de Separação 6*).</span><span class="sxs-lookup"><span data-stu-id="efc09-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="efc09-253">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="efc09-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="efc09-254">Configurar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="efc09-254">Set up location directives</span></span>

<span data-ttu-id="efc09-255">Pelo menos uma diretiva de localização deve ser configurada para dar suporte a seleções de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="efc09-256">Use os procedimentos desta seção para configurar uma nova *diretiva de local de reabastecimento* para separações de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="efc09-257">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="efc09-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="efc09-258">No painel esquerdo, no campo **Tipo de ordem de serviço**, selecione *Reabastecimento*.</span><span class="sxs-lookup"><span data-stu-id="efc09-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="efc09-259">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="efc09-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="efc09-260">No cabeçalho da nova diretiva de localização, no campo **Nome**, insira *Seleção de slots 61*.</span><span class="sxs-lookup"><span data-stu-id="efc09-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="efc09-261">No campo **Número de sequência**, aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="efc09-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="efc09-262">Configurar a FastTab Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="efc09-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="efc09-263">Na FastTab **Diretivas de localização**, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="efc09-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="efc09-264">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="efc09-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="efc09-265">**Tipo de trabalho:** _Separar_</span><span class="sxs-lookup"><span data-stu-id="efc09-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="efc09-266">**Local:** _6_</span><span class="sxs-lookup"><span data-stu-id="efc09-266">**Site:** _6_</span></span>
    - <span data-ttu-id="efc09-267">**Depósito:** _61_</span><span class="sxs-lookup"><span data-stu-id="efc09-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="efc09-268">**Código de diretiva:** _Slots_</span><span class="sxs-lookup"><span data-stu-id="efc09-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="efc09-269">Selecione **Salvar** para disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="efc09-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="efc09-270">Configurar a FastTab Linhas</span><span class="sxs-lookup"><span data-stu-id="efc09-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="efc09-271">Na FastTab **Linhas**, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="efc09-272">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="efc09-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="efc09-273">**Quantidade inicial:** _0_</span><span class="sxs-lookup"><span data-stu-id="efc09-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="efc09-274">**Quantidade final:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="efc09-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="efc09-275">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="efc09-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="efc09-276">Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="efc09-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="efc09-277">Configurar a FastTab Ações de Diretiva</span><span class="sxs-lookup"><span data-stu-id="efc09-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="efc09-278">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="efc09-279">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="efc09-279">On the new line, set the following values.</span></span> <span data-ttu-id="efc09-280">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="efc09-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="efc09-281">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="efc09-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="efc09-282">**Nome:** _Massa_</span><span class="sxs-lookup"><span data-stu-id="efc09-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="efc09-283">**Estratégia:** _Nenhuma_</span><span class="sxs-lookup"><span data-stu-id="efc09-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="efc09-284">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="efc09-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="efc09-285">Selecione **Salvar** para disponibilizar o botão **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="efc09-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="efc09-286">Editar a consulta</span><span class="sxs-lookup"><span data-stu-id="efc09-286">Edit the query</span></span>

1. <span data-ttu-id="efc09-287">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="efc09-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="efc09-288">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="efc09-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="efc09-289">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="efc09-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="efc09-290">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="efc09-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="efc09-291">**Tabela derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="efc09-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="efc09-292">**Campo:** *ID da zona*</span><span class="sxs-lookup"><span data-stu-id="efc09-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="efc09-293">**Critérios:** *Massa* (selecione o sinal de adição duplo \[**++**\] no campo para expandir a lista e selecione *Massa*.)</span><span class="sxs-lookup"><span data-stu-id="efc09-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="efc09-294">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="efc09-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="efc09-295">Cenário</span><span class="sxs-lookup"><span data-stu-id="efc09-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="efc09-296">Configurar o cenário</span><span class="sxs-lookup"><span data-stu-id="efc09-296">Set up the scenario</span></span>

<span data-ttu-id="efc09-297">Para esse cenário, use os dados de exemplo internos e crie os registros descritos nesta seção.</span><span class="sxs-lookup"><span data-stu-id="efc09-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="efc09-298">Usar os dados de exemplo USMF</span><span class="sxs-lookup"><span data-stu-id="efc09-298">Use the USMF sample data</span></span>

<span data-ttu-id="efc09-299">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="efc09-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="efc09-300">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="efc09-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="efc09-301">Criar demanda</span><span class="sxs-lookup"><span data-stu-id="efc09-301">Create demand</span></span>

<span data-ttu-id="efc09-302">Siga as etapas a seguir para criar a solicitação à qual você aplicará slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="efc09-303">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="efc09-304">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="efc09-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="efc09-305">Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-007_.</span><span class="sxs-lookup"><span data-stu-id="efc09-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="efc09-306">No campo **Depósito**, selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="efc09-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="efc09-307">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="efc09-307">Select **OK**.</span></span>
1. <span data-ttu-id="efc09-308">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="efc09-308">The new sales order is opened.</span></span> <span data-ttu-id="efc09-309">Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="efc09-310">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="efc09-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="efc09-311">**Item:** _L0101_</span><span class="sxs-lookup"><span data-stu-id="efc09-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="efc09-312">**Quantidade:** _20_</span><span class="sxs-lookup"><span data-stu-id="efc09-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="efc09-313">Selecione **Adicionar linha** para adicionar uma nova linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="efc09-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="efc09-314">**Item:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="efc09-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="efc09-315">**Quantidade:** _8_</span><span class="sxs-lookup"><span data-stu-id="efc09-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="efc09-316">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efc09-316">Select **Save**.</span></span>
1. <span data-ttu-id="efc09-317">Selecione **Novo** para criar uma segunda ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="efc09-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="efc09-318">Na caixa de diálogo **Criar ordem de venda**, no campo **Conta do cliente**, selecione _US-008_.</span><span class="sxs-lookup"><span data-stu-id="efc09-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="efc09-319">No campo **Depósito**, selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="efc09-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="efc09-320">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="efc09-320">The new sales order is opened.</span></span> <span data-ttu-id="efc09-321">Ela inclui uma linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="efc09-322">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="efc09-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="efc09-323">**Item:** _T0100_</span><span class="sxs-lookup"><span data-stu-id="efc09-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="efc09-324">**Quantidade:** _1_</span><span class="sxs-lookup"><span data-stu-id="efc09-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="efc09-325">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efc09-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="efc09-326">Examine um cenário típico de slots</span><span class="sxs-lookup"><span data-stu-id="efc09-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="efc09-327">Depois que todos os elementos de pré-requisito estiverem em uso, conforme descrito na seção anterior, você estará pronto para testar o recurso, executando cada exercício desta seção.</span><span class="sxs-lookup"><span data-stu-id="efc09-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="efc09-328">Gerar demanda</span><span class="sxs-lookup"><span data-stu-id="efc09-328">Generate demand</span></span>

1. <span data-ttu-id="efc09-329">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de slots** e selecione o modelo de slots que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="efc09-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="efc09-330">No Painel de Ações, selecione **Gerar demanda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="efc09-331">Este comando avalia toda a demanda que está no sistema e corresponde à consulta do modelo de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="efc09-332">A demanda total em todas as ordens é consolidada em uma linha por quantidade/unidade de medida.</span><span class="sxs-lookup"><span data-stu-id="efc09-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="efc09-333">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="efc09-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="efc09-334">Demanda de slots</span><span class="sxs-lookup"><span data-stu-id="efc09-334">Slotting demand</span></span>

<span data-ttu-id="efc09-335">A *demanda de slots* mostra os resultados da geração de demanda, com base na configuração do modelo de slots.</span><span class="sxs-lookup"><span data-stu-id="efc09-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="efc09-336">No Painel de Ações, selecione **Demanda de slots** para exibir os resultados do comando **Gerar demanda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="efc09-337">As linhas na demanda de slots podem ser editadas.</span><span class="sxs-lookup"><span data-stu-id="efc09-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="efc09-338">Você pode excluir uma linha, adicionar uma nova linha ou editar detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="efc09-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="efc09-339">Você pode editar manualmente a demanda ou pode importá-la de um sistema externo usando o gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="efc09-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="efc09-340">Seja qual for a demanda de slots, ela será usada na próxima etapa, independentemente da origem.</span><span class="sxs-lookup"><span data-stu-id="efc09-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="efc09-341">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="efc09-341">Locate demand</span></span>

<span data-ttu-id="efc09-342">Depois que a demanda for gerada, utilize o comando **Localizar demanda** para gerar o *plano de slots*.</span><span class="sxs-lookup"><span data-stu-id="efc09-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="efc09-343">No Painel de Ações, selecione **Localizar demanda**.</span><span class="sxs-lookup"><span data-stu-id="efc09-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="efc09-344">O processo de slots é executado.</span><span class="sxs-lookup"><span data-stu-id="efc09-344">The slotting process runs.</span></span> <span data-ttu-id="efc09-345">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="efc09-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="efc09-346">Plano de slots</span><span class="sxs-lookup"><span data-stu-id="efc09-346">Slotting plan</span></span>

<span data-ttu-id="efc09-347">O plano de slots mostra o local ao qual cada item/quantidade foi atribuído, se o estouro foi usado, se o trabalho de pausa foi criado e a linha de modelo que foi usada.</span><span class="sxs-lookup"><span data-stu-id="efc09-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="efc09-348">*Qualquer demanda que não possa ser encaixada será realçada em vermelho.*</span><span class="sxs-lookup"><span data-stu-id="efc09-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="efc09-349">No Painel de Ações, selecione **Plano de slots** para exibir os resultados.</span><span class="sxs-lookup"><span data-stu-id="efc09-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="efc09-350">Os processos **Gerar demanda**, **Localizar demanda** e **Executar reabastecimento** agora são executados em uma área restrita.</span><span class="sxs-lookup"><span data-stu-id="efc09-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="efc09-351">(Esses processos estão disponíveis no Painel de Ações na página **Modelos de slots**.)</span><span class="sxs-lookup"><span data-stu-id="efc09-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="efc09-352">Os processos **Gerar demanda**, **Localizar demanda** e **Executar reabastecimento** têm um bloqueio para garantir que não possam ser acionados ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="efc09-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="efc09-353">Caso contrário, os dados usados podem ser excluídos.</span><span class="sxs-lookup"><span data-stu-id="efc09-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="efc09-354">Os processos **Gerar demanda** e **Localizar demanda** mostram um aviso se a execução não gerou registros ou se faltam informações nos registros.</span><span class="sxs-lookup"><span data-stu-id="efc09-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="efc09-355">Quando você seleciona **Plano de slots**, a página não tem os botões **Novo**, **Editar** ou **Excluir** no Painel de Ações, porque não é possível editar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="efc09-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="efc09-356">Quando você seleciona **Executar reabastecimento**, o sistema valida o modelo de slot e os processos selecionados.</span><span class="sxs-lookup"><span data-stu-id="efc09-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="efc09-357">Criar reabastecimento</span><span class="sxs-lookup"><span data-stu-id="efc09-357">Create replenishment</span></span>

<span data-ttu-id="efc09-358">Após a criação do plano de slots, você deverá criar um *trabalho de reabastecimento*, com base no plano.</span><span class="sxs-lookup"><span data-stu-id="efc09-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="efc09-359">No Painel de Ações, selecione **Executar reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="efc09-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="efc09-360">Uma mensagem informativa é exibida quando o processo é concluído.</span><span class="sxs-lookup"><span data-stu-id="efc09-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="efc09-361">Esta mensagem indica o número de cabeçalhos que foram criados para a ID de criação do trabalho.</span><span class="sxs-lookup"><span data-stu-id="efc09-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="efc09-362">As diretivas de localização que serão usadas são identificadas com base no código de diretiva especificado em cada linha de modelo.</span><span class="sxs-lookup"><span data-stu-id="efc09-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="efc09-363">Dicas</span><span class="sxs-lookup"><span data-stu-id="efc09-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="efc09-364">Configurar slots automáticos</span><span class="sxs-lookup"><span data-stu-id="efc09-364">Set up automatic slotting</span></span>

<span data-ttu-id="efc09-365">Quando todos os elementos necessários estiverem ativos, você poderá configurar slots para execução automática seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="efc09-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="efc09-366">Vá para **Gerenciamento de depósito \> Reabastecimento \> Executar slots**.</span><span class="sxs-lookup"><span data-stu-id="efc09-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="efc09-367">Especifique as etapas de slots a serem executadas.</span><span class="sxs-lookup"><span data-stu-id="efc09-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="efc09-368">Selecione uma ou mais das seguintes etapas de slots:</span><span class="sxs-lookup"><span data-stu-id="efc09-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="efc09-369">Gerar demanda</span><span class="sxs-lookup"><span data-stu-id="efc09-369">Generate demand</span></span>
    - <span data-ttu-id="efc09-370">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="efc09-370">Locate demand</span></span>
    - <span data-ttu-id="efc09-371">Criar trabalho de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="efc09-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="efc09-372">As etapas de slots são progressivas.</span><span class="sxs-lookup"><span data-stu-id="efc09-372">The slotting steps are progressive.</span></span> <span data-ttu-id="efc09-373">Se desejar selecionar *Localizar demanda*, primeiro selecione *Gerar demanda*.</span><span class="sxs-lookup"><span data-stu-id="efc09-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="efc09-374">Especifique o modelo de slots a ser usado.</span><span class="sxs-lookup"><span data-stu-id="efc09-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="efc09-375">Defina que a recorrência seja executada automaticamente, se desejar.</span><span class="sxs-lookup"><span data-stu-id="efc09-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="efc09-376">Para os exercícios no cenário, **não** configure slots automáticos.</span><span class="sxs-lookup"><span data-stu-id="efc09-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
