---
title: Consolidar remessas quando são liberadas para o depósito usando a liberação automática de ordens de venda
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito no mesmo procedimento periódico automatizado de liberação para o depósito.
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
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f4d095456435a3401daa173d79b80b81176a3c17
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987109"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="81725-103">Consolidar remessas quando são liberadas para o depósito usando a liberação automática de ordens de venda</span><span class="sxs-lookup"><span data-stu-id="81725-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81725-104">Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito no mesmo procedimento periódico automatizado de liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="81725-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="81725-105">As ordens serão automaticamente consolidadas em remessas, com base em regras definidas como políticas de consolidação de remessa.</span><span class="sxs-lookup"><span data-stu-id="81725-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="81725-106">Durante o cenário, você criará conjuntos de ordens de venda e liberará cada conjunto para o depósito.</span><span class="sxs-lookup"><span data-stu-id="81725-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="81725-107">Em seguida, você verificará as remessas criadas ou atualizadas durante a consolidação da remessa, com base nas políticas configuradas.</span><span class="sxs-lookup"><span data-stu-id="81725-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="81725-108">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="81725-108">Make demo data available</span></span>

<span data-ttu-id="81725-109">O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="81725-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="81725-110">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="81725-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="81725-111">Configure políticas de consolidação de remessa e filtros de produtos</span><span class="sxs-lookup"><span data-stu-id="81725-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="81725-112">O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali.</span><span class="sxs-lookup"><span data-stu-id="81725-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="81725-113">Lembre-se de fazer os exercícios antes de continuar este cenário.</span><span class="sxs-lookup"><span data-stu-id="81725-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="81725-114">Crie as ordens de venda para este cenário</span><span class="sxs-lookup"><span data-stu-id="81725-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="81725-115">Comece criando uma coleção de ordens de venda com as quais possa trabalhar.</span><span class="sxs-lookup"><span data-stu-id="81725-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="81725-116">Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS).</span><span class="sxs-lookup"><span data-stu-id="81725-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="81725-117">A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.</span><span class="sxs-lookup"><span data-stu-id="81725-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="81725-118">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="81725-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="81725-119">Crie o conjunto de ordens 1</span><span class="sxs-lookup"><span data-stu-id="81725-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="81725-120">Ordem de venda 1-1</span><span class="sxs-lookup"><span data-stu-id="81725-120">Sales order 1-1</span></span>

1. <span data-ttu-id="81725-121">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-122">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-123">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="81725-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="81725-124">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-125">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-126">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="81725-127">Ordem de venda 1-2</span><span class="sxs-lookup"><span data-stu-id="81725-127">Sales order 1-2</span></span>

1. <span data-ttu-id="81725-128">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-129">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-130">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="81725-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="81725-131">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-132">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-133">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="81725-134">Ordem de venda 1-3</span><span class="sxs-lookup"><span data-stu-id="81725-134">Sales order 1-3</span></span>

1. <span data-ttu-id="81725-135">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-136">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-137">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="81725-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="81725-138">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-139">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-140">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="81725-141">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-142">**Número do item:** *A0002* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-143">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="81725-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="81725-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="81725-145">Crie o conjunto de ordens 2</span><span class="sxs-lookup"><span data-stu-id="81725-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="81725-146">Ordens de venda 2-1 e 2-2</span><span class="sxs-lookup"><span data-stu-id="81725-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="81725-147">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-148">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="81725-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="81725-149">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-150">**Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)</span><span class="sxs-lookup"><span data-stu-id="81725-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="81725-151">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="81725-152">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-153">**Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="81725-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="81725-154">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="81725-155">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="81725-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="81725-156">Crie o conjunto de ordens 3</span><span class="sxs-lookup"><span data-stu-id="81725-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="81725-157">Ordem de venda 3-1</span><span class="sxs-lookup"><span data-stu-id="81725-157">Sales order 3-1</span></span>

1. <span data-ttu-id="81725-158">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-159">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="81725-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="81725-160">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-161">**Número do item:** *M9200* (um item no qual o filtro **Código 4** está definido como *Inflamável*)</span><span class="sxs-lookup"><span data-stu-id="81725-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="81725-162">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="81725-163">Adicione uma segunda linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-164">**Número do item:** *M9201* (um item no qual o filtro **Código 4** está definido como *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="81725-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="81725-165">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="81725-166">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="81725-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="81725-167">Essa ordem é idêntica às duas ordens criadas para o conjunto de ordens 2.</span><span class="sxs-lookup"><span data-stu-id="81725-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="81725-168">No entanto, ela está listada como seu próprio conjunto de ordens, pois será liberada separadamente mais adiante neste cenário.</span><span class="sxs-lookup"><span data-stu-id="81725-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="81725-169">Crie o conjunto de ordens 4</span><span class="sxs-lookup"><span data-stu-id="81725-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="81725-170">Ordem de venda 4-1</span><span class="sxs-lookup"><span data-stu-id="81725-170">Sales order 4-1</span></span>

1. <span data-ttu-id="81725-171">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-172">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-173">**Requisição de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="81725-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="81725-174">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-175">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-176">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="81725-177">Crie o conjunto de ordens 5</span><span class="sxs-lookup"><span data-stu-id="81725-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="81725-178">Ordens de venda 5-1 e 5-2</span><span class="sxs-lookup"><span data-stu-id="81725-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="81725-179">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-180">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-181">**Requisição de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="81725-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="81725-182">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-183">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-184">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="81725-185">Ordem de venda 5-3</span><span class="sxs-lookup"><span data-stu-id="81725-185">Sales order 5-3</span></span>

1. <span data-ttu-id="81725-186">Crie uma ordem de venda com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="81725-187">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="81725-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="81725-188">**Requisição de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="81725-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="81725-189">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-190">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-191">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="81725-192">Crie o conjunto de ordens 6</span><span class="sxs-lookup"><span data-stu-id="81725-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="81725-193">Ordens de venda 6-1 e 6-2</span><span class="sxs-lookup"><span data-stu-id="81725-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="81725-194">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-195">**Conta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="81725-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="81725-196">**Requisição de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="81725-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="81725-197">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-198">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-199">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="81725-200">Ordens de venda 6-3 e 6-4</span><span class="sxs-lookup"><span data-stu-id="81725-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="81725-201">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-202">**Conta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="81725-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="81725-203">**Requisição de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="81725-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="81725-204">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-205">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-206">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="81725-207">Ordens de venda 6-5 e 6-6</span><span class="sxs-lookup"><span data-stu-id="81725-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="81725-208">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-209">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="81725-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="81725-210">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="81725-210">**Site:** *6*</span></span>
    - <span data-ttu-id="81725-211">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="81725-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="81725-212">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="81725-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="81725-213">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-214">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-215">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="81725-216">Ordens de venda 6-7 e 6-8</span><span class="sxs-lookup"><span data-stu-id="81725-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="81725-217">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="81725-218">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="81725-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="81725-219">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="81725-219">**Site:** *6*</span></span>
    - <span data-ttu-id="81725-220">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="81725-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="81725-221">**Grupo:** Deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="81725-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="81725-222">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="81725-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="81725-223">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="81725-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="81725-224">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="81725-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="81725-225">Liberação automática de ordens de venda para o depósito</span><span class="sxs-lookup"><span data-stu-id="81725-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="81725-226">Para cada conjunto de ordens de venda criadas anteriormente, você concluirá um procedimento para liberação automática para o depósito.</span><span class="sxs-lookup"><span data-stu-id="81725-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="81725-227">Em cada caso, você trabalhará no [procedimento básico de liberação para depósito](#release-procedure) que é fornecido aqui.</span><span class="sxs-lookup"><span data-stu-id="81725-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="81725-228">Procedimento básico de liberação para depósito</span><span class="sxs-lookup"><span data-stu-id="81725-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="81725-229">Para cada conjunto de ordens de venda criadas anteriormente, você concluirá os três procedimentos descritos nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="81725-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="81725-230">Atualize o modelo de onda que será usado durante a liberação</span><span class="sxs-lookup"><span data-stu-id="81725-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="81725-231">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="81725-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="81725-232">Defina o campo **Tipo de modelo de onda** como *Remessa*.</span><span class="sxs-lookup"><span data-stu-id="81725-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="81725-233">Localize e selecione o modelo de onda associado ao depósito que você usou nos conjuntos de ordens criados para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="81725-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="81725-234">Por exemplo, se você usou depósito *24*, selecione o modelo de onda **Padrão de 24 remessas**.</span><span class="sxs-lookup"><span data-stu-id="81725-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="81725-235">Se você usou depósito *61*, selecione o modelo de onda **61 remessas**.</span><span class="sxs-lookup"><span data-stu-id="81725-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="81725-236">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="81725-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="81725-237">Defina a opção **Processar onda na liberação para o depósito** como *Não*.</span><span class="sxs-lookup"><span data-stu-id="81725-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="81725-238">Libere para o depósito</span><span class="sxs-lookup"><span data-stu-id="81725-238">Release to the warehouse</span></span>

1. <span data-ttu-id="81725-239">Vá para **Gerenciamento de depósito \> Liberar para depósito \> Liberação automática de ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="81725-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="81725-240">Defina o campo **Quantidade para liberação** como *Todos*.</span><span class="sxs-lookup"><span data-stu-id="81725-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="81725-241">Na Guia Rápida **Registros para incluir**, selecione **Filtro** para abrir a caixa de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="81725-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="81725-242">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha com as seguintes configurações à grade:</span><span class="sxs-lookup"><span data-stu-id="81725-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="81725-243">**Tabela:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="81725-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="81725-244">**Tabela derivada:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="81725-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="81725-245">**Campo:** *Ordem de venda*</span><span class="sxs-lookup"><span data-stu-id="81725-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="81725-246">**Critérios:** Insira uma lista separada por vírgulas dos números da ordem de venda no conjunto de ordens desejado.</span><span class="sxs-lookup"><span data-stu-id="81725-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="81725-247">Selecione **OK** para salvar a consulta.</span><span class="sxs-lookup"><span data-stu-id="81725-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="81725-248">Selecione **OK** para iniciar o procedimento *Liberar automaticamente para o depósito*.</span><span class="sxs-lookup"><span data-stu-id="81725-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="81725-249">Avalie a remessa criada ou atualizada</span><span class="sxs-lookup"><span data-stu-id="81725-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="81725-250">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="81725-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="81725-251">Localize e selecione a remessa necessária.</span><span class="sxs-lookup"><span data-stu-id="81725-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="81725-252">Se uma política de consolidação foi usada quando a remessa foi criada ou atualizada, você verá a mesma no campo **Política de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="81725-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="81725-253">Libere ordens de venda do conjunto de ordens 1</span><span class="sxs-lookup"><span data-stu-id="81725-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="81725-254">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 1.</span><span class="sxs-lookup"><span data-stu-id="81725-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="81725-255">Quando terminar, você verá que duas remessas foram criadas:</span><span class="sxs-lookup"><span data-stu-id="81725-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="81725-256">A primeira remessa contém três linhas e foi criada usando a política de consolidação de remessa *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="81725-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="81725-257">A segunda remessa, que não usa o modo de entrega *Airways*, foi criada usando a política de consolidação de remessa *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="81725-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="81725-258">Libere ordens de venda do conjunto de ordens 2</span><span class="sxs-lookup"><span data-stu-id="81725-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="81725-259">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 2.</span><span class="sxs-lookup"><span data-stu-id="81725-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="81725-260">Quando terminar, você verá que três remessas foram criadas:</span><span class="sxs-lookup"><span data-stu-id="81725-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="81725-261">A primeira remessa contém itens *Inflamáveis*.</span><span class="sxs-lookup"><span data-stu-id="81725-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="81725-262">Cada uma das outras duas remessas contém uma linha com o item *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="81725-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="81725-263">Libere ordens de venda do conjunto de ordens 3</span><span class="sxs-lookup"><span data-stu-id="81725-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="81725-264">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 3.</span><span class="sxs-lookup"><span data-stu-id="81725-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="81725-265">Quando terminar, você verá que as seguintes ações ocorreram:</span><span class="sxs-lookup"><span data-stu-id="81725-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="81725-266">Uma remessa existente (a remessa que foi criada quando o conjunto de ordens 2 foi liberado para o depósito) foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="81725-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="81725-267">Uma linha com o item *Inflamável* foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="81725-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="81725-268">Uma nova remessa foi criada que contém o item *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="81725-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="81725-269">Libere ordens de venda do conjunto de ordens 4</span><span class="sxs-lookup"><span data-stu-id="81725-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="81725-270">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 4.</span><span class="sxs-lookup"><span data-stu-id="81725-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="81725-271">Quando terminar, você verá que uma remessa existente (em que o campo **Requisição do cliente** está definido como *1*) foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="81725-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="81725-272">Uma nova linha foi adicionada.</span><span class="sxs-lookup"><span data-stu-id="81725-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="81725-273">Libere ordens de venda do conjunto de ordens 5</span><span class="sxs-lookup"><span data-stu-id="81725-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="81725-274">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 5.</span><span class="sxs-lookup"><span data-stu-id="81725-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="81725-275">Quando terminar, você verá que as seguintes ações ocorreram:</span><span class="sxs-lookup"><span data-stu-id="81725-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="81725-276">Uma remessa existente (em que o campo **Requisição do cliente** é definido como *1*) foi atualizada.</span><span class="sxs-lookup"><span data-stu-id="81725-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="81725-277">Uma linha da ordem de venda 5-3 (em que o campo **Requisição do cliente** está definido como *1*) foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="81725-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="81725-278">Uma nova remessa foi criada, na qual as linhas das ordens de venda 5-1 e 5-2 são agrupadas em uma remessa.</span><span class="sxs-lookup"><span data-stu-id="81725-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="81725-279">Libere ordens de venda do conjunto de ordens 6</span><span class="sxs-lookup"><span data-stu-id="81725-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="81725-280">Siga o [procedimento básico de liberação para depósito](#release-procedure) para liberar as ordens de venda do conjunto de ordens 6.</span><span class="sxs-lookup"><span data-stu-id="81725-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="81725-281">Quando terminar, você verá que quatro remessas foram criadas:</span><span class="sxs-lookup"><span data-stu-id="81725-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="81725-282">As linhas de duas ordens de cliente *US-003* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="81725-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="81725-283">As linhas de duas ordens de cliente *US-004* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="81725-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="81725-284">As linhas de ordens de venda 6-5 e 6-6 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *Grupo de ordens*.</span><span class="sxs-lookup"><span data-stu-id="81725-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="81725-285">As linhas de ordens de venda 6-7 e 6-8 de cliente *US-007* foram agrupadas em uma remessa usando a política de consolidação de remessa de *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="81725-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81725-286">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="81725-286">Additional resources</span></span>

- [<span data-ttu-id="81725-287">Políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="81725-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="81725-288">Configurar políticas de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="81725-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
