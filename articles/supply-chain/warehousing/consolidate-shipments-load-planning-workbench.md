---
title: Consolide remessas usando Liberar para o depósito da bancada de planejamento de carga
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito na mesma carga e são consolidadas automaticamente em remessas.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 396a038dbf2f4b6835ecbb5fd8cb39a3a3608af7
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383714"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="b39d2-103">Consolide remessas usando Liberar para o depósito da bancada de planejamento de carga</span><span class="sxs-lookup"><span data-stu-id="b39d2-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b39d2-104">Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito na mesma carga e são consolidadas automaticamente em remessas.</span><span class="sxs-lookup"><span data-stu-id="b39d2-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="b39d2-105">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="b39d2-105">Make demo data available</span></span>

<span data-ttu-id="b39d2-106">O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b39d2-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b39d2-107">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="b39d2-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="b39d2-108">Configure políticas de consolidação de remessa e filtros de produtos</span><span class="sxs-lookup"><span data-stu-id="b39d2-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="b39d2-109">O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali.</span><span class="sxs-lookup"><span data-stu-id="b39d2-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="b39d2-110">Lembre-se de fazer os exercícios antes de continuar este cenário.</span><span class="sxs-lookup"><span data-stu-id="b39d2-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="b39d2-111">Crie as ordens de venda para este cenário</span><span class="sxs-lookup"><span data-stu-id="b39d2-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="b39d2-112">Comece criando uma coleção de ordens de venda com as quais possa trabalhar.</span><span class="sxs-lookup"><span data-stu-id="b39d2-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="b39d2-113">Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS).</span><span class="sxs-lookup"><span data-stu-id="b39d2-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="b39d2-114">A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.</span><span class="sxs-lookup"><span data-stu-id="b39d2-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="b39d2-115">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="b39d2-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="b39d2-116">Crie o conjunto de ordens 1</span><span class="sxs-lookup"><span data-stu-id="b39d2-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="b39d2-117">Ordem de venda 1-1</span><span class="sxs-lookup"><span data-stu-id="b39d2-117">Sales order 1-1</span></span>

1. <span data-ttu-id="b39d2-118">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-119">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b39d2-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b39d2-120">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b39d2-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b39d2-121">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-122">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-123">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-124">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="b39d2-125">Ordem de venda 1-2</span><span class="sxs-lookup"><span data-stu-id="b39d2-125">Sales order 1-2</span></span>

1. <span data-ttu-id="b39d2-126">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-127">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b39d2-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b39d2-128">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b39d2-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b39d2-129">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-130">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-131">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-132">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="b39d2-133">Ordem de venda 1-3</span><span class="sxs-lookup"><span data-stu-id="b39d2-133">Sales order 1-3</span></span>

1. <span data-ttu-id="b39d2-134">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-135">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b39d2-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b39d2-136">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="b39d2-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="b39d2-137">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-138">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-139">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-140">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="b39d2-141">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-142">**Número do item:** *A0002* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-143">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="b39d2-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b39d2-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b39d2-145">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="b39d2-146">Crie o conjunto de ordens 2</span><span class="sxs-lookup"><span data-stu-id="b39d2-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="b39d2-147">Ordens de venda 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="b39d2-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="b39d2-148">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-149">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b39d2-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="b39d2-150">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-151">**Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)</span><span class="sxs-lookup"><span data-stu-id="b39d2-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="b39d2-152">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-153">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="b39d2-154">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-155">**Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="b39d2-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="b39d2-156">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="b39d2-157">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="b39d2-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="b39d2-158">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="b39d2-159">Crie o conjunto de ordens 3</span><span class="sxs-lookup"><span data-stu-id="b39d2-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="b39d2-160">Ordens de venda 3-1 e 3-2</span><span class="sxs-lookup"><span data-stu-id="b39d2-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="b39d2-161">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-162">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b39d2-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b39d2-163">**Requisição de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="b39d2-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="b39d2-164">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-165">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-166">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-167">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="b39d2-168">Ordens de venda 3-3 e 3-4</span><span class="sxs-lookup"><span data-stu-id="b39d2-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="b39d2-169">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-170">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="b39d2-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="b39d2-171">**Requisição de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="b39d2-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="b39d2-172">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-173">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-174">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-175">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="b39d2-176">Crie o conjunto de ordens 4</span><span class="sxs-lookup"><span data-stu-id="b39d2-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="b39d2-177">Ordens de venda 4-1 e 4-2</span><span class="sxs-lookup"><span data-stu-id="b39d2-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="b39d2-178">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-179">**Conta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="b39d2-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="b39d2-180">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-181">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-182">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-183">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="b39d2-184">Ordens de venda 4-3 e 4-4</span><span class="sxs-lookup"><span data-stu-id="b39d2-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="b39d2-185">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-186">**Conta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="b39d2-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="b39d2-187">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-188">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-189">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-190">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="b39d2-191">Ordens de venda 4-5 e 4-6</span><span class="sxs-lookup"><span data-stu-id="b39d2-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="b39d2-192">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-193">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b39d2-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b39d2-194">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="b39d2-194">**Site:** *6*</span></span>
    - <span data-ttu-id="b39d2-195">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="b39d2-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="b39d2-196">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="b39d2-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="b39d2-197">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-198">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-199">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-200">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="b39d2-201">Ordens de venda 4-7 e 4-8</span><span class="sxs-lookup"><span data-stu-id="b39d2-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="b39d2-202">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="b39d2-203">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b39d2-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b39d2-204">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="b39d2-204">**Site:** *6*</span></span>
    - <span data-ttu-id="b39d2-205">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="b39d2-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="b39d2-206">**Grupo:** Deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="b39d2-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="b39d2-207">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b39d2-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="b39d2-208">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="b39d2-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="b39d2-209">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="b39d2-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="b39d2-210">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="b39d2-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="b39d2-211">Use a bancada de planejamento de carga para criar cargas e liberá-las para o depósito</span><span class="sxs-lookup"><span data-stu-id="b39d2-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="b39d2-212">Siga estas etapas para criar uma carga para cada conjunto de ordens que você criou para esse cenário e, em seguida, liberá-lo para o depósito.</span><span class="sxs-lookup"><span data-stu-id="b39d2-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="b39d2-213">Vá para **Gerenciamento de depósito \> Cargas \> Bancada de planejamento de carga**.</span><span class="sxs-lookup"><span data-stu-id="b39d2-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="b39d2-214">Na guia **Linhas de venda**, localize e selecione todas as linhas da ordem de venda em um dos conjuntos de ordens criados para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="b39d2-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="b39d2-215">No Painel de Ações, na guia **Oferta e demanda**, selecione **Adicionar \> Para nova carga** para adicionar as linhas de ordem selecionadas a uma nova carga.</span><span class="sxs-lookup"><span data-stu-id="b39d2-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="b39d2-216">Na caixa de diálogo **Atribuição de modelo de carga**, no campo **ID do modelo de carga**, selecione um modelo de carga, como *Modelo de Carga Padrão*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="b39d2-217">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b39d2-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="b39d2-218">Na seção **Cargas**, localize e selecione a carga que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="b39d2-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="b39d2-219">Selecione **Liberar \> Liberar para depósito** para liberar a carga selecionada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="b39d2-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="b39d2-220">Repita este procedimento para os outros três conjuntos de ordens criados para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="b39d2-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="b39d2-221">Verifique as remessas</span><span class="sxs-lookup"><span data-stu-id="b39d2-221">Verify the shipments</span></span>

<span data-ttu-id="b39d2-222">O procedimento a seguir permite verificar as remessas que foram criadas ou atualizadas como resultado da consolidação de remessa.</span><span class="sxs-lookup"><span data-stu-id="b39d2-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="b39d2-223">Use-o para revisar cada conjunto de ordens criado para esse cenário e, em seguida, analisar as subseções a seguir para garantir que você obtenha os resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="b39d2-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="b39d2-224">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="b39d2-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="b39d2-225">Localize e selecione a remessa necessária.</span><span class="sxs-lookup"><span data-stu-id="b39d2-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="b39d2-226">Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="b39d2-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="b39d2-227">Libere o conjunto de ordens 1 em uma carga</span><span class="sxs-lookup"><span data-stu-id="b39d2-227">Release order set 1 in one load</span></span>

<span data-ttu-id="b39d2-228">Duas remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="b39d2-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="b39d2-229">A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="b39d2-230">A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="b39d2-231">Libere o conjunto de ordens 2 em uma carga</span><span class="sxs-lookup"><span data-stu-id="b39d2-231">Release order set 2 in one load</span></span>

<span data-ttu-id="b39d2-232">Três remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="b39d2-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="b39d2-233">A primeira remessa contém os itens *inflamáveis*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="b39d2-234">Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="b39d2-235">Libere o conjunto de ordens 3 em uma carga</span><span class="sxs-lookup"><span data-stu-id="b39d2-235">Release order set 3 in one load</span></span>

<span data-ttu-id="b39d2-236">Duas remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="b39d2-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="b39d2-237">A primeira remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *1*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="b39d2-238">A segunda remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *2*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="b39d2-239">Libere o conjunto de ordens 4 em uma carga</span><span class="sxs-lookup"><span data-stu-id="b39d2-239">Release order set 4 in one load</span></span>

<span data-ttu-id="b39d2-240">Quatro remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="b39d2-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="b39d2-241">As linhas de duas ordens de conta de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b39d2-242">As linhas de duas ordens de conta de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b39d2-243">As linhas de ordens de venda 4-5 e 4-6 da conta de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="b39d2-244">As linhas de ordens de venda 4-7 e 4-8 da conta de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="b39d2-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b39d2-245">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="b39d2-245">Additional resources</span></span>

- [<span data-ttu-id="b39d2-246">Políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="b39d2-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="b39d2-247">Configurar políticas de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="b39d2-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)