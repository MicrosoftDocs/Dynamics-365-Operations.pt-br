---
title: Consolide as remessas manualmente usando a página Consolidar remessas
description: Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas posteriormente usando a página Consolidar remessas.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: e4e6dac1d1b4a304062e852526235eeee6579540
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840380"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a><span data-ttu-id="92aa4-103">Consolide as remessas manualmente usando a página Consolidar remessas</span><span class="sxs-lookup"><span data-stu-id="92aa4-103">Consolidate shipments manually by using the Consolidate shipments page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92aa4-104">Este tópico apresenta um cenário em que várias ordens são liberadas para o depósito e consolidadas posteriormente usando a página **Consolidar remessas**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated later by using the **Consolidate shipments** page.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="92aa4-105">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="92aa4-105">Make demo data available</span></span>

<span data-ttu-id="92aa4-106">O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="92aa4-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="92aa4-107">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="92aa4-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="92aa4-108">Configure políticas de consolidação de remessa e filtros de produtos</span><span class="sxs-lookup"><span data-stu-id="92aa4-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="92aa4-109">O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali.</span><span class="sxs-lookup"><span data-stu-id="92aa4-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="92aa4-110">Lembre-se de fazer os exercícios antes de continuar este cenário.</span><span class="sxs-lookup"><span data-stu-id="92aa4-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="92aa4-111">Crie as ordens de venda para este cenário</span><span class="sxs-lookup"><span data-stu-id="92aa4-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="92aa4-112">Comece criando uma coleção de ordens de venda com as quais possa trabalhar.</span><span class="sxs-lookup"><span data-stu-id="92aa4-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="92aa4-113">Você deve trabalhar com um depósito habilitado para processos de depósito avançados (WMS).</span><span class="sxs-lookup"><span data-stu-id="92aa4-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="92aa4-114">A menos que um depósito diferente seja explicitamente mencionado, esse mesmo depósito deve ser usado para cada um dos conjuntos de ordens a seguir.</span><span class="sxs-lookup"><span data-stu-id="92aa4-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="92aa4-115">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie uma coleção de ordens de venda que tenha as configurações descritas nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="92aa4-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-sales-orders-1-and-2"></a><span data-ttu-id="92aa4-116">Criar as ordens de venda 1 e 2</span><span class="sxs-lookup"><span data-stu-id="92aa4-116">Create sales orders 1 and 2</span></span>

1. <span data-ttu-id="92aa4-117">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="92aa4-117">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="92aa4-118">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="92aa4-118">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="92aa4-119">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="92aa4-119">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="92aa4-120">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="92aa4-120">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="92aa4-121">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="92aa4-121">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="92aa4-122">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="92aa4-122">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="92aa4-123">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="92aa4-123">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-sales-orders-3-and-4"></a><span data-ttu-id="92aa4-124">Criar as ordens de venda 3 e 4</span><span class="sxs-lookup"><span data-stu-id="92aa4-124">Create sales orders 3 and 4</span></span>

1. <span data-ttu-id="92aa4-125">Crie duas ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="92aa4-125">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="92aa4-126">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="92aa4-126">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="92aa4-127">**Grupo:** Deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="92aa4-127">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="92aa4-128">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="92aa4-128">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="92aa4-129">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="92aa4-129">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="92aa4-130">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="92aa4-130">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="92aa4-131">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="92aa4-131">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="92aa4-132">Libere as ordens para o depósito</span><span class="sxs-lookup"><span data-stu-id="92aa4-132">Release the orders to the warehouse</span></span>

<span data-ttu-id="92aa4-133">Siga estas etapas para liberar cada ordem de venda criada para esse cenário para o depósito.</span><span class="sxs-lookup"><span data-stu-id="92aa4-133">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="92aa4-134">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-134">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="92aa4-135">Encontre e selecione a ordem de venda a ser liberada.</span><span class="sxs-lookup"><span data-stu-id="92aa4-135">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="92aa4-136">No Painel de Ações, na guia **Depósito**, selecione **Ações \> Liberar para depósito** para liberar a ordem de venda selecionada.</span><span class="sxs-lookup"><span data-stu-id="92aa4-136">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="92aa4-137">Repita este procedimento para todas as outras ordens de venda criadas para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="92aa4-137">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-shipments"></a><span data-ttu-id="92aa4-138">Consolidar remessas</span><span class="sxs-lookup"><span data-stu-id="92aa4-138">Consolidate shipments</span></span>

1. <span data-ttu-id="92aa4-139">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-139">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="92aa4-140">Localize e selecione uma remessa que foi criada quando a ordem de venda 1 foi liberada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="92aa4-140">Find and select a shipment that was created when sales order 1 was released to the warehouse.</span></span> <span data-ttu-id="92aa4-141">(o campo **Política de consolidação de remessa** deve ser definido como *Grupo de ordens*.)</span><span class="sxs-lookup"><span data-stu-id="92aa4-141">(Its **Shipment consolidation policy** field should be set to *Order pool*.)</span></span>
1. <span data-ttu-id="92aa4-142">No Painel de Ações, na guia **Remessas**, selecione **Remessas \> Consolidar remessas**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-142">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="92aa4-143">Verifique as remessas sugeridas para consolidação.</span><span class="sxs-lookup"><span data-stu-id="92aa4-143">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="92aa4-144">Somente uma remessa com a mesma política deve ser sugerida para consolidação.</span><span class="sxs-lookup"><span data-stu-id="92aa4-144">Only one shipment that has the same policy should be suggested for consolidation.</span></span>
1. <span data-ttu-id="92aa4-145">Feche a página **Consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-145">Close the **Shipment consolidation** page.</span></span>
1. <span data-ttu-id="92aa4-146">Localize e selecione uma remessa que foi criada quando a ordem de venda 3 foi liberada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="92aa4-146">Find and select a shipment that was created when sales order 3 was released to the warehouse.</span></span> <span data-ttu-id="92aa4-147">(o campo **Política de consolidação de remessa** deve ser definido como *Padrão*.)</span><span class="sxs-lookup"><span data-stu-id="92aa4-147">(Its **Shipment consolidation policy** field should be set to *Default*.)</span></span>
1. <span data-ttu-id="92aa4-148">No Painel de Ações, na guia **Remessas**, selecione **Remessas \> Consolidar remessas**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-148">On the Action Pane, on the **Shipments** tab, select **Shipments \> Consolidate shipments**.</span></span>
1. <span data-ttu-id="92aa4-149">Verifique se não há remessas sugeridas para consolidação.</span><span class="sxs-lookup"><span data-stu-id="92aa4-149">Verify that no shipments are suggested for consolidation.</span></span>
1. <span data-ttu-id="92aa4-150">Selecione **Mostrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-150">Select **Show filters**.</span></span>
1. <span data-ttu-id="92aa4-151">No painel **Filtros**, remova o filtro **Número da ordem** e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="92aa4-151">In the **Filters** pane, remove the **Order number** filter, and then select **Apply**.</span></span>
1. <span data-ttu-id="92aa4-152">Verifique as remessas sugeridas para consolidação.</span><span class="sxs-lookup"><span data-stu-id="92aa4-152">Verify the shipments that are suggested for consolidation.</span></span> <span data-ttu-id="92aa4-153">Somente uma remessa com a mesma política deve ser sugerida para consolidação.</span><span class="sxs-lookup"><span data-stu-id="92aa4-153">Only one shipment that has the same policy should be suggested for consolidation.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92aa4-154">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="92aa4-154">Additional resources</span></span>

- [<span data-ttu-id="92aa4-155">Políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="92aa4-155">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="92aa4-156">Configurar políticas de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="92aa4-156">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]