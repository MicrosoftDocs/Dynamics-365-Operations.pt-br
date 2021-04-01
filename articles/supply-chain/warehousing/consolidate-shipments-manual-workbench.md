---
title: Consolidar remessas usando a bancada de consolidação de remessa
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas em remessas posteriormente usando a bancada de consolidação de remessas.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSShipConsolidationSetShipment
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9b7dc72d789fd331c3636c406ac6a45566ba81ca
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5242172"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="48739-103">Consolidar remessas usando a bancada de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="48739-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48739-104">Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas em remessas posteriormente usando a bancada de consolidação de remessas.</span><span class="sxs-lookup"><span data-stu-id="48739-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="48739-105">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="48739-105">Make demo data available</span></span>

<span data-ttu-id="48739-106">O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="48739-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="48739-107">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="48739-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="48739-108">Configure políticas de consolidação de remessa e filtros de produtos</span><span class="sxs-lookup"><span data-stu-id="48739-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="48739-109">O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali.</span><span class="sxs-lookup"><span data-stu-id="48739-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="48739-110">Lembre-se de fazer os exercícios antes de continuar este cenário.</span><span class="sxs-lookup"><span data-stu-id="48739-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="48739-111">Ative o recurso de consolidação de remessa manual</span><span class="sxs-lookup"><span data-stu-id="48739-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="48739-112">Para usar o recurso *Consolidação de remessa manual*, você precisa ativá-lo no sistema.</span><span class="sxs-lookup"><span data-stu-id="48739-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="48739-113">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="48739-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="48739-114">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="48739-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="48739-115">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="48739-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="48739-116">**Nome do recurso:** *Consolidação de remessa manual*</span><span class="sxs-lookup"><span data-stu-id="48739-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="48739-117">Como foi mencionado em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md), você também deve ativar o recurso *Consolidar remessa* para poder criar políticas.</span><span class="sxs-lookup"><span data-stu-id="48739-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="48739-118">No entanto, você já deve ter concluído essa etapa.</span><span class="sxs-lookup"><span data-stu-id="48739-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="48739-119">Crie as ordens de venda para este cenário</span><span class="sxs-lookup"><span data-stu-id="48739-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="48739-120">Comece criando uma coleção de ordens de venda com as quais possa trabalhar.</span><span class="sxs-lookup"><span data-stu-id="48739-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="48739-121">Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS).</span><span class="sxs-lookup"><span data-stu-id="48739-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="48739-122">A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.</span><span class="sxs-lookup"><span data-stu-id="48739-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="48739-123">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="48739-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="48739-124">Crie o conjunto de ordens 1</span><span class="sxs-lookup"><span data-stu-id="48739-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="48739-125">Ordens de venda 1-1 e 1-2</span><span class="sxs-lookup"><span data-stu-id="48739-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="48739-126">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-127">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="48739-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="48739-128">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="48739-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="48739-129">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-130">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-131">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-132">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="48739-133">Ordem de venda 1-3</span><span class="sxs-lookup"><span data-stu-id="48739-133">Sales order 1-3</span></span>

1. <span data-ttu-id="48739-134">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="48739-135">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="48739-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="48739-136">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="48739-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="48739-137">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-138">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-139">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-140">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="48739-141">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-142">**Número do item:** *A0002* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-143">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="48739-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="48739-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="48739-145">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="48739-146">Crie o conjunto de ordens 2</span><span class="sxs-lookup"><span data-stu-id="48739-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="48739-147">Ordens de venda 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="48739-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="48739-148">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-149">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="48739-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="48739-150">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="48739-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="48739-151">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-152">**Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)</span><span class="sxs-lookup"><span data-stu-id="48739-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="48739-153">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-154">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="48739-155">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-156">**Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="48739-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="48739-157">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="48739-158">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="48739-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="48739-159">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a segunda linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="48739-160">Crie o conjunto de ordens 3</span><span class="sxs-lookup"><span data-stu-id="48739-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="48739-161">Ordens de venda 3-1 e 3-2</span><span class="sxs-lookup"><span data-stu-id="48739-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="48739-162">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-163">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="48739-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="48739-164">**Requisição de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="48739-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="48739-165">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-166">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-167">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-168">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="48739-169">Ordens de venda 3-3 e 3-4</span><span class="sxs-lookup"><span data-stu-id="48739-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="48739-170">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-171">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="48739-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="48739-172">**Requisição de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="48739-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="48739-173">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-174">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-175">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-176">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="48739-177">Crie o conjunto de ordens 4</span><span class="sxs-lookup"><span data-stu-id="48739-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="48739-178">Ordens de venda 4-1 e 4-2</span><span class="sxs-lookup"><span data-stu-id="48739-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="48739-179">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-180">**Conta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="48739-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="48739-181">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-182">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-183">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-184">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="48739-185">Ordens de venda 4-3 e 4-4</span><span class="sxs-lookup"><span data-stu-id="48739-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="48739-186">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-187">**Conta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="48739-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="48739-188">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-189">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-190">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-191">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="48739-192">Ordens de venda 4-5 e 4-6</span><span class="sxs-lookup"><span data-stu-id="48739-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="48739-193">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-194">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="48739-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="48739-195">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="48739-195">**Site:** *6*</span></span>
    - <span data-ttu-id="48739-196">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="48739-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="48739-197">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="48739-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="48739-198">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-199">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-200">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-201">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="48739-202">Ordens de venda 4-7 e 4-8</span><span class="sxs-lookup"><span data-stu-id="48739-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="48739-203">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="48739-204">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="48739-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="48739-205">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="48739-205">**Site:** *6*</span></span>
    - <span data-ttu-id="48739-206">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="48739-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="48739-207">**Grupo:** Deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="48739-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="48739-208">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="48739-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="48739-209">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="48739-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="48739-210">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="48739-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="48739-211">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="48739-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="48739-212">Libere as ordens para o depósito</span><span class="sxs-lookup"><span data-stu-id="48739-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="48739-213">Siga estas etapas para liberar cada ordem de venda criada para esse cenário para o depósito.</span><span class="sxs-lookup"><span data-stu-id="48739-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="48739-214">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="48739-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="48739-215">Encontre e selecione a ordem de venda a ser liberada.</span><span class="sxs-lookup"><span data-stu-id="48739-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="48739-216">No Painel de Ações, na guia **Depósito**, selecione **Ações \> Liberar para depósito** para liberar a ordem de venda selecionada.</span><span class="sxs-lookup"><span data-stu-id="48739-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="48739-217">Repita este procedimento para todas as outras ordens de venda criadas para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="48739-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="48739-218">Consolidar as remessas usando a bancada de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="48739-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="48739-219">Vá para **Gerenciamento de depósito \> Liberar para depósito \> Bancada de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="48739-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="48739-220">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="48739-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="48739-221">Na caixa de diálogo do editor de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:</span><span class="sxs-lookup"><span data-stu-id="48739-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="48739-222">**Tabela:** *Ordens de venda*</span><span class="sxs-lookup"><span data-stu-id="48739-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="48739-223">**Campo:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="48739-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="48739-224">**Critérios:** Insira uma lista separada por vírgulas dos números de ordem de venda para cada conjunto de ordens criado para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="48739-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="48739-225">Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="48739-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="48739-226">No Painel de Ações, selecione **Consolidar remessas**.</span><span class="sxs-lookup"><span data-stu-id="48739-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="48739-227">Selecione todas as remessas e, depois, no Painel de Ações, selecione **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="48739-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="48739-228">Verifique as remessas</span><span class="sxs-lookup"><span data-stu-id="48739-228">Verify the shipments</span></span>

<span data-ttu-id="48739-229">O procedimento a seguir permite verificar as remessas que foram criadas ou atualizadas como resultado da consolidação de remessa.</span><span class="sxs-lookup"><span data-stu-id="48739-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="48739-230">Use-o para revisar cada conjunto de ordens criado para esse cenário e, em seguida, analisar as subseções a seguir para garantir que você obtenha os resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="48739-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="48739-231">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="48739-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="48739-232">Localize e selecione a remessa necessária.</span><span class="sxs-lookup"><span data-stu-id="48739-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="48739-233">Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="48739-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="48739-234">Remessas relacionadas para o conjunto de ordens 1</span><span class="sxs-lookup"><span data-stu-id="48739-234">Related shipments for order set 1</span></span>

<span data-ttu-id="48739-235">Duas remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="48739-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="48739-236">A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="48739-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="48739-237">A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="48739-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="48739-238">Remessas relacionadas para o conjunto de ordens 2</span><span class="sxs-lookup"><span data-stu-id="48739-238">Related shipments for order set 2</span></span>

<span data-ttu-id="48739-239">Três remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="48739-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="48739-240">A primeira remessa contém itens *Inflamáveis*.</span><span class="sxs-lookup"><span data-stu-id="48739-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="48739-241">Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="48739-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="48739-242">Remessas relacionadas para o conjunto de ordens 3</span><span class="sxs-lookup"><span data-stu-id="48739-242">Related shipments for order set 3</span></span>

<span data-ttu-id="48739-243">Duas remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="48739-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="48739-244">A primeira remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *1*.</span><span class="sxs-lookup"><span data-stu-id="48739-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="48739-245">A segunda remessa contém linhas de ordem da ordem de venda em que o campo **Requisição do cliente** está definido como *2*.</span><span class="sxs-lookup"><span data-stu-id="48739-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="48739-246">Remessas relacionadas para o conjunto de ordens 4</span><span class="sxs-lookup"><span data-stu-id="48739-246">Related shipments for order set 4</span></span>

<span data-ttu-id="48739-247">Quatro remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="48739-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="48739-248">As linhas de duas ordens de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="48739-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="48739-249">As linhas de duas ordens de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="48739-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="48739-250">As linhas de ordens de venda 4-5 e 4-6 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="48739-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="48739-251">As linhas de ordens de venda 4-7 e 4-8 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="48739-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="48739-252">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="48739-252">Additional resources</span></span>

- [<span data-ttu-id="48739-253">Políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="48739-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="48739-254">Configurar políticas de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="48739-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]