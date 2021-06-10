---
title: Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management
description: Este tópico descreve como atribuir ícones e títulos de etapas para fluxos de tarefas novos ou personalizados para o aplicativo móvel Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 9523492d766669e6c38579fba7b5ddd6b3d282fc
ms.sourcegitcommit: c53de2c09b9296b41653e739178edf29f79e0679
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049355"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a><span data-ttu-id="73a20-103">Atribuir títulos e ícones de etapa ao aplicativo móvel Warehouse Management</span><span class="sxs-lookup"><span data-stu-id="73a20-103">Assign step icons and titles for the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73a20-104">Este tópico descreve como atribuir ícones e títulos de etapas para fluxos de tarefas novos ou personalizados para o aplicativo móvel Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="73a20-104">This topic describes how to assign step icons and step titles for new or customized task flows for the Warehouse Management mobile app.</span></span>

<span data-ttu-id="73a20-105">As ilustrações a seguir mostram como os ícones e títulos de etapas aparecem no aplicativo móvel Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="73a20-105">The following illustrations shows how step icons and titles appear in the Warehouse Management mobile app.</span></span>

<span data-ttu-id="73a20-106">![Exemplo de um ícone e um título de etapa no aplicativo móvel Warehouse Management](media/step-icon-example.png "Exemplo de um ícone e um título de etapa no aplicativo móvel Warehouse Management")</span><span class="sxs-lookup"><span data-stu-id="73a20-106">![Example of a step icon and a step title in the Warehouse Management mobile app](media/step-icon-example.png "Example of a step icon and a step title in the Warehouse Management mobile app")</span></span>

## <a name="turn-on-this-feature-in-your-system"></a><span data-ttu-id="73a20-107">Ative este recurso no seu sistema</span><span class="sxs-lookup"><span data-stu-id="73a20-107">Turn on this feature in your system</span></span>

<span data-ttu-id="73a20-108">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="73a20-108">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="73a20-109">Os administradores podem usar as configurações do [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="73a20-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="73a20-110">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="73a20-110">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="73a20-111">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="73a20-111">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="73a20-112">**Nome do recurso:** *configurações do usuário, ícones e títulos de etapa do novo aplicativo de depósito*</span><span class="sxs-lookup"><span data-stu-id="73a20-112">**Feature name:** *User settings, icons, and step titles for the new warehouse app*</span></span>

## <a name="standard-step-ids-classes-and-icons"></a><span data-ttu-id="73a20-113">IDs, classes e ícones de etapa padrão</span><span class="sxs-lookup"><span data-stu-id="73a20-113">Standard step IDs, classes, and icons</span></span>

<span data-ttu-id="73a20-114">Cada etapa em um fluxo de tarefa é identificada por uma ID de etapa e cada ID de etapa possui uma classe de etapa correspondente.</span><span class="sxs-lookup"><span data-stu-id="73a20-114">Each step in a task flow is identified by a step ID, and each step ID has a corresponding step class.</span></span> <span data-ttu-id="73a20-115">O ícone e o título da etapa são especificados em cada classe da etapa.</span><span class="sxs-lookup"><span data-stu-id="73a20-115">The step icon and title are specified in each step class.</span></span>

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a><span data-ttu-id="73a20-116">IDs de etapa e classes de etapa</span><span class="sxs-lookup"><span data-stu-id="73a20-116">Step IDs and step classes</span></span>

<span data-ttu-id="73a20-117">A tabela a seguir lista cada ID de etapa que está disponível atualmente e sua classe de etapa correspondente.</span><span class="sxs-lookup"><span data-stu-id="73a20-117">The following table lists every step ID that is currently available, and its corresponding step class.</span></span> <span data-ttu-id="73a20-118">O nome de controle do campo de entrada principal é usado como a ID da etapa.</span><span class="sxs-lookup"><span data-stu-id="73a20-118">The control name of the primary input field is used as the step ID.</span></span>

<span data-ttu-id="73a20-119">Para ter um exemplo que mostra como essas IDs e classes de etapa são usadas, consulte a implementação do método `WHSMobileAppStepInfoBuilder.stepId()` na seção [Exemplo: Atribuir ícones e títulos de etapa para um fluxo personalizado](#example) a seguir neste tópico.</span><span class="sxs-lookup"><span data-stu-id="73a20-119">For an example that shows how these step IDs and classes are used, see the implementation of the `WHSMobileAppStepInfoBuilder.stepId()` method in the [Example: Assign step icons and titles for a custom flow](#example) section later in this topic.</span></span>

| <span data-ttu-id="73a20-120">ID da etapa</span><span class="sxs-lookup"><span data-stu-id="73a20-120">Step ID</span></span> | <span data-ttu-id="73a20-121">Classe da etapa</span><span class="sxs-lookup"><span data-stu-id="73a20-121">Step Class</span></span> |
|-|-|
| <span data-ttu-id="73a20-122">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-122">BatchDisposition</span></span> | <span data-ttu-id="73a20-123">WHSMobileAppStepBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-123">WHSMobileAppStepBatchDisposition</span></span> |
| <span data-ttu-id="73a20-124">Transportadora</span><span class="sxs-lookup"><span data-stu-id="73a20-124">Carrier</span></span> | <span data-ttu-id="73a20-125">WHSMobileAppStepCarrier</span><span class="sxs-lookup"><span data-stu-id="73a20-125">WHSMobileAppStepCarrier</span></span> |
| <span data-ttu-id="73a20-126">CatchWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-126">CatchWeight</span></span> | <span data-ttu-id="73a20-127">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-127">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="73a20-128">CatchWeightQtyOutboundWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-128">CatchWeightQtyOutboundWeight</span></span> | <span data-ttu-id="73a20-129">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-129">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="73a20-130">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="73a20-130">CatchWeightTag</span></span> | <span data-ttu-id="73a20-131">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="73a20-131">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="73a20-132">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-132">CatchWeightTagWeight</span></span> | <span data-ttu-id="73a20-133">WHSMobileAppStepCatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-133">WHSMobileAppStepCatchWeightTagWeight</span></span> |
| <span data-ttu-id="73a20-134">ChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="73a20-134">ChangeWarehouseSuccess</span></span> | <span data-ttu-id="73a20-135">WHSMobileAppStepChangeWarehouseSuccess</span><span class="sxs-lookup"><span data-stu-id="73a20-135">WHSMobileAppStepChangeWarehouseSuccess</span></span> |
| <span data-ttu-id="73a20-136">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="73a20-136">CheckDigit</span></span> | <span data-ttu-id="73a20-137">WHSMobileAppStepCheckDigit</span><span class="sxs-lookup"><span data-stu-id="73a20-137">WHSMobileAppStepCheckDigit</span></span> |
| <span data-ttu-id="73a20-138">ClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-138">ClusterId</span></span> | <span data-ttu-id="73a20-139">WHSMobileAppStepClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-139">WHSMobileAppStepClusterId</span></span> |
| <span data-ttu-id="73a20-140">ClusterPickQtyVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-140">ClusterPickQtyVerification</span></span> | <span data-ttu-id="73a20-141">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-141">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="73a20-142">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="73a20-142">ClusterPosition</span></span> | <span data-ttu-id="73a20-143">WHSMobileAppStepClusterPosition</span><span class="sxs-lookup"><span data-stu-id="73a20-143">WHSMobileAppStepClusterPosition</span></span> |
| <span data-ttu-id="73a20-144">ConfigId</span><span class="sxs-lookup"><span data-stu-id="73a20-144">ConfigId</span></span> | <span data-ttu-id="73a20-145">WHSMobileAppStepConfigId</span><span class="sxs-lookup"><span data-stu-id="73a20-145">WHSMobileAppStepConfigId</span></span> |
| <span data-ttu-id="73a20-146">Confirmação</span><span class="sxs-lookup"><span data-stu-id="73a20-146">Confirmation</span></span> | <span data-ttu-id="73a20-147">WHSMobileAppStepConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-147">WHSMobileAppStepConfirmation</span></span> |
| <span data-ttu-id="73a20-148">ConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-148">ConsolidateFromLicensePlateId</span></span> | <span data-ttu-id="73a20-149">WHSMobileAppStepConsolidateFromLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-149">WHSMobileAppStepConsolidateFromLicensePlateId</span></span> |
| <span data-ttu-id="73a20-150">ConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-150">ConsolidateLPConfirmation</span></span> | <span data-ttu-id="73a20-151">WHSMobileAppStepConsolidateLPConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-151">WHSMobileAppStepConsolidateLPConfirmation</span></span> |
| <span data-ttu-id="73a20-152">ConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-152">ConsolidateToLicensePlateId</span></span> | <span data-ttu-id="73a20-153">WHSMobileAppStepConsolidateToLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-153">WHSMobileAppStepConsolidateToLicensePlateId</span></span> |
| <span data-ttu-id="73a20-154">ContainerType</span><span class="sxs-lookup"><span data-stu-id="73a20-154">ContainerType</span></span> | <span data-ttu-id="73a20-155">WHSMobileAppStepContainerType</span><span class="sxs-lookup"><span data-stu-id="73a20-155">WHSMobileAppStepContainerType</span></span> |
| <span data-ttu-id="73a20-156">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="73a20-156">CountingReasonCode</span></span> | <span data-ttu-id="73a20-157">WHSMobileAppStepCountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="73a20-157">WHSMobileAppStepCountingReasonCode</span></span> |
| <span data-ttu-id="73a20-158">CycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="73a20-158">CycleCountingAddLPOrFinish</span></span> | <span data-ttu-id="73a20-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span><span class="sxs-lookup"><span data-stu-id="73a20-159">WHSMobileAppStepCycleCountingAddLPOrFinish</span></span> |
| <span data-ttu-id="73a20-160">CycleCountQty1</span><span class="sxs-lookup"><span data-stu-id="73a20-160">CycleCountQty1</span></span> | <span data-ttu-id="73a20-161">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="73a20-161">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="73a20-162">CycleCountQty2</span><span class="sxs-lookup"><span data-stu-id="73a20-162">CycleCountQty2</span></span> | <span data-ttu-id="73a20-163">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="73a20-163">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="73a20-164">CycleCountQty3</span><span class="sxs-lookup"><span data-stu-id="73a20-164">CycleCountQty3</span></span> | <span data-ttu-id="73a20-165">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="73a20-165">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="73a20-166">CycleCountQty4</span><span class="sxs-lookup"><span data-stu-id="73a20-166">CycleCountQty4</span></span> | <span data-ttu-id="73a20-167">WHSMobileAppStepCycleCountQty</span><span class="sxs-lookup"><span data-stu-id="73a20-167">WHSMobileAppStepCycleCountQty</span></span> |
| <span data-ttu-id="73a20-168">Disposition</span><span class="sxs-lookup"><span data-stu-id="73a20-168">Disposition</span></span> | <span data-ttu-id="73a20-169">WHSMobileAppStepDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-169">WHSMobileAppStepDisposition</span></span> |
| <span data-ttu-id="73a20-170">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-170">DriverCheckInConfirmation</span></span> | <span data-ttu-id="73a20-171">WHSMobileAppStepDriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-171">WHSMobileAppStepDriverCheckInConfirmation</span></span> |
| <span data-ttu-id="73a20-172">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="73a20-172">DriverCheckInId</span></span> | <span data-ttu-id="73a20-173">WHSMobileAppStepDriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="73a20-173">WHSMobileAppStepDriverCheckInId</span></span> |
| <span data-ttu-id="73a20-174">DriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-174">DriverCheckOutConfirmation</span></span> | <span data-ttu-id="73a20-175">WHSMobileAppStepDriverCheckOutConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-175">WHSMobileAppStepDriverCheckOutConfirmation</span></span> |
| <span data-ttu-id="73a20-176">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="73a20-176">DriverCheckOutId</span></span> | <span data-ttu-id="73a20-177">WHSMobileAppStepDriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="73a20-177">WHSMobileAppStepDriverCheckOutId</span></span> |
| <span data-ttu-id="73a20-178">ExpDate</span><span class="sxs-lookup"><span data-stu-id="73a20-178">ExpDate</span></span> | <span data-ttu-id="73a20-179">WHSMobileAppStepExpDate</span><span class="sxs-lookup"><span data-stu-id="73a20-179">WHSMobileAppStepExpDate</span></span> |
| <span data-ttu-id="73a20-180">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-180">FromBatchDisposition</span></span> | <span data-ttu-id="73a20-181">WHSMobileAppStepFromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-181">WHSMobileAppStepFromBatchDisposition</span></span> |
| <span data-ttu-id="73a20-182">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="73a20-182">FromInventoryStatus</span></span> | <span data-ttu-id="73a20-183">WHSMobileAppStepInventoryStatusFrom</span><span class="sxs-lookup"><span data-stu-id="73a20-183">WHSMobileAppStepInventoryStatusFrom</span></span> |
| <span data-ttu-id="73a20-184">FullQty</span><span class="sxs-lookup"><span data-stu-id="73a20-184">FullQty</span></span> | <span data-ttu-id="73a20-185">WHSMobileAppStepFullQty</span><span class="sxs-lookup"><span data-stu-id="73a20-185">WHSMobileAppStepFullQty</span></span> |
| <span data-ttu-id="73a20-186">InboundPut</span><span class="sxs-lookup"><span data-stu-id="73a20-186">InboundPut</span></span> | <span data-ttu-id="73a20-187">WHSMobileAppStepInboundPut</span><span class="sxs-lookup"><span data-stu-id="73a20-187">WHSMobileAppStepInboundPut</span></span> |
| <span data-ttu-id="73a20-188">InventBatchId</span><span class="sxs-lookup"><span data-stu-id="73a20-188">InventBatchId</span></span> | <span data-ttu-id="73a20-189">WHSMobileAppStepBatch</span><span class="sxs-lookup"><span data-stu-id="73a20-189">WHSMobileAppStepBatch</span></span> |
| <span data-ttu-id="73a20-190">InventColorId</span><span class="sxs-lookup"><span data-stu-id="73a20-190">InventColorId</span></span> | <span data-ttu-id="73a20-191">WHSMobileAppStepInventColorId</span><span class="sxs-lookup"><span data-stu-id="73a20-191">WHSMobileAppStepInventColorId</span></span> |
| <span data-ttu-id="73a20-192">InventLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-192">InventLocation</span></span> | <span data-ttu-id="73a20-193">WHSMobileAppStepInventLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-193">WHSMobileAppStepInventLocation</span></span> |
| <span data-ttu-id="73a20-194">InventLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-194">InventLocationId</span></span> | <span data-ttu-id="73a20-195">WHSMobileAppStepWarehouse</span><span class="sxs-lookup"><span data-stu-id="73a20-195">WHSMobileAppStepWarehouse</span></span> |
| <span data-ttu-id="73a20-196">InventSerialId</span><span class="sxs-lookup"><span data-stu-id="73a20-196">InventSerialId</span></span> | <span data-ttu-id="73a20-197">WHSMobileAppStepInventSerialId</span><span class="sxs-lookup"><span data-stu-id="73a20-197">WHSMobileAppStepInventSerialId</span></span> |
| <span data-ttu-id="73a20-198">InventSizeId</span><span class="sxs-lookup"><span data-stu-id="73a20-198">InventSizeId</span></span> | <span data-ttu-id="73a20-199">WHSMobileAppStepInventSizeId</span><span class="sxs-lookup"><span data-stu-id="73a20-199">WHSMobileAppStepInventSizeId</span></span> |
| <span data-ttu-id="73a20-200">InventStatusId</span><span class="sxs-lookup"><span data-stu-id="73a20-200">InventStatusId</span></span> | <span data-ttu-id="73a20-201">WHSMobileAppStepInventStatus</span><span class="sxs-lookup"><span data-stu-id="73a20-201">WHSMobileAppStepInventStatus</span></span> |
| <span data-ttu-id="73a20-202">InventStyleId</span><span class="sxs-lookup"><span data-stu-id="73a20-202">InventStyleId</span></span> | <span data-ttu-id="73a20-203">WHSMobileAppStepInventStyleId</span><span class="sxs-lookup"><span data-stu-id="73a20-203">WHSMobileAppStepInventStyleId</span></span> |
| <span data-ttu-id="73a20-204">InventVersionId</span><span class="sxs-lookup"><span data-stu-id="73a20-204">InventVersionId</span></span> | <span data-ttu-id="73a20-205">WHSMobileAppStepInventVersionId</span><span class="sxs-lookup"><span data-stu-id="73a20-205">WHSMobileAppStepInventVersionId</span></span> |
| <span data-ttu-id="73a20-206">ItemId</span><span class="sxs-lookup"><span data-stu-id="73a20-206">ItemId</span></span> | <span data-ttu-id="73a20-207">WHSMobileAppStepItem</span><span class="sxs-lookup"><span data-stu-id="73a20-207">WHSMobileAppStepItem</span></span> |
| <span data-ttu-id="73a20-208">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="73a20-208">ITMContainerID</span></span> | <span data-ttu-id="73a20-209">ITMMobileAppStepContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-209">ITMMobileAppStepContainerId</span></span> |
| <span data-ttu-id="73a20-210">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="73a20-210">ITMShipmentID</span></span> | <span data-ttu-id="73a20-211">ITMMobileAppStepShipmentId</span><span class="sxs-lookup"><span data-stu-id="73a20-211">ITMMobileAppStepShipmentId</span></span> |
| <span data-ttu-id="73a20-212">KanbanCardId</span><span class="sxs-lookup"><span data-stu-id="73a20-212">KanbanCardId</span></span> | <span data-ttu-id="73a20-213">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="73a20-213">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="73a20-214">KanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="73a20-214">KanbanCardToEmpty</span></span> | <span data-ttu-id="73a20-215">WHSMobileAppStepKanbanCardToEmpty</span><span class="sxs-lookup"><span data-stu-id="73a20-215">WHSMobileAppStepKanbanCardToEmpty</span></span> |
| <span data-ttu-id="73a20-216">KanbanOrCardId</span><span class="sxs-lookup"><span data-stu-id="73a20-216">KanbanOrCardId</span></span> | <span data-ttu-id="73a20-217">WHSMobileAppStepKanbanCard</span><span class="sxs-lookup"><span data-stu-id="73a20-217">WHSMobileAppStepKanbanCard</span></span> |
| <span data-ttu-id="73a20-218">LicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-218">LicensePlateId</span></span> | <span data-ttu-id="73a20-219">WHSMobileAppStepLicensePlate</span><span class="sxs-lookup"><span data-stu-id="73a20-219">WHSMobileAppStepLicensePlate</span></span> |
| <span data-ttu-id="73a20-220">LoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-220">LoadId</span></span> | <span data-ttu-id="73a20-221">WHSMobileAppStepLoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-221">WHSMobileAppStepLoadId</span></span> |
| <span data-ttu-id="73a20-222">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="73a20-222">LocationLicensePlatePosition</span></span> | <span data-ttu-id="73a20-223">WHSMobileAppStepLocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="73a20-223">WHSMobileAppStepLocationLicensePlatePosition</span></span> |
| <span data-ttu-id="73a20-224">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-224">LocOrLP</span></span> | <span data-ttu-id="73a20-225">WHSMobileAppStepLocOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-225">WHSMobileAppStepLocOrLP</span></span> |
| <span data-ttu-id="73a20-226">LocOrLP_From</span><span class="sxs-lookup"><span data-stu-id="73a20-226">LocOrLP_From</span></span> | <span data-ttu-id="73a20-227">WHSMobileAppStepLocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="73a20-227">WHSMobileAppStepLocOrLPFrom</span></span> |
| <span data-ttu-id="73a20-228">LocOrLP_To</span><span class="sxs-lookup"><span data-stu-id="73a20-228">LocOrLP_To</span></span> | <span data-ttu-id="73a20-229">WHSMobileAppStepLocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="73a20-229">WHSMobileAppStepLocOrLPTo</span></span> |
| <span data-ttu-id="73a20-230">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="73a20-230">LocOrLPCheck</span></span> | <span data-ttu-id="73a20-231">WHSMobileAppStepLocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="73a20-231">WHSMobileAppStepLocOrLPCheck</span></span> |
| <span data-ttu-id="73a20-232">LocVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-232">LocVerification</span></span> | <span data-ttu-id="73a20-233">WHSMobileAppStepLocVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-233">WHSMobileAppStepLocVerification</span></span> |
| <span data-ttu-id="73a20-234">LPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="73a20-234">LPAdjustIn</span></span> | <span data-ttu-id="73a20-235">WHSMobileAppStepLPAdjustIn</span><span class="sxs-lookup"><span data-stu-id="73a20-235">WHSMobileAppStepLPAdjustIn</span></span> |
| <span data-ttu-id="73a20-236">LPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="73a20-236">LPBreakChildLP</span></span> | <span data-ttu-id="73a20-237">WHSMobileAppStepLPBreakChildLP</span><span class="sxs-lookup"><span data-stu-id="73a20-237">WHSMobileAppStepLPBreakChildLP</span></span> |
| <span data-ttu-id="73a20-238">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-238">LPBreakParentLP</span></span> | <span data-ttu-id="73a20-239">WHSMobileAppStepLPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-239">WHSMobileAppStepLPBreakParentLP</span></span> |
| <span data-ttu-id="73a20-240">LPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="73a20-240">LPBuildChildLP</span></span> | <span data-ttu-id="73a20-241">WHSMobileAppStepLPBuildChildLP</span><span class="sxs-lookup"><span data-stu-id="73a20-241">WHSMobileAppStepLPBuildChildLP</span></span> |
| <span data-ttu-id="73a20-242">LPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-242">LPBuildParentLP</span></span> | <span data-ttu-id="73a20-243">WHSMobileAppStepLPBuildParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-243">WHSMobileAppStepLPBuildParentLP</span></span> |
| <span data-ttu-id="73a20-244">LPVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-244">LPVerification</span></span> | <span data-ttu-id="73a20-245">WHSMobileAppStepLPVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-245">WHSMobileAppStepLPVerification</span></span> |
| <span data-ttu-id="73a20-246">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-246">MergeContainerId</span></span> | <span data-ttu-id="73a20-247">WHSMobileAppStepMergeContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-247">WHSMobileAppStepMergeContainerId</span></span> |
| <span data-ttu-id="73a20-248">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-248">MixedLPLineNum</span></span> | <span data-ttu-id="73a20-249">WHSMobileAppStepMixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-249">WHSMobileAppStepMixedLPLineNum</span></span> |
| <span data-ttu-id="73a20-250">MobileDeviceQueueMessageCollectionIdentifierId</span><span class="sxs-lookup"><span data-stu-id="73a20-250">MobileDeviceQueueMessageCollectionIdentifierId</span></span> | <span data-ttu-id="73a20-251">WHSMobileAppStepSelectOrder</span><span class="sxs-lookup"><span data-stu-id="73a20-251">WHSMobileAppStepSelectOrder</span></span> |
| <span data-ttu-id="73a20-252">MovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="73a20-252">MovementConfirmCancel</span></span> | <span data-ttu-id="73a20-253">WHSMobileAppStepMovementConfirmCancel</span><span class="sxs-lookup"><span data-stu-id="73a20-253">WHSMobileAppStepMovementConfirmCancel</span></span> |
| <span data-ttu-id="73a20-254">NewCaptureWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-254">NewCaptureWeight</span></span> | <span data-ttu-id="73a20-255">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-255">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="73a20-256">NewQty</span><span class="sxs-lookup"><span data-stu-id="73a20-256">NewQty</span></span> | <span data-ttu-id="73a20-257">WHSMobileAppStepNewQty</span><span class="sxs-lookup"><span data-stu-id="73a20-257">WHSMobileAppStepNewQty</span></span> |
| <span data-ttu-id="73a20-258">OutboundCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="73a20-258">OutboundCatchWeightTag</span></span> | <span data-ttu-id="73a20-259">WHSMobileAppStepCatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="73a20-259">WHSMobileAppStepCatchWeightTag</span></span> |
| <span data-ttu-id="73a20-260">OutboundPut</span><span class="sxs-lookup"><span data-stu-id="73a20-260">OutboundPut</span></span> | <span data-ttu-id="73a20-261">WHSMobileAppStepOutboundPut</span><span class="sxs-lookup"><span data-stu-id="73a20-261">WHSMobileAppStepOutboundPut</span></span> |
| <span data-ttu-id="73a20-262">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-262">OutboundWeight</span></span> | <span data-ttu-id="73a20-263">WHSMobileAppStepCatchWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-263">WHSMobileAppStepCatchWeight</span></span> |
| <span data-ttu-id="73a20-264">OverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-264">OverridePutNewLocation</span></span> | <span data-ttu-id="73a20-265">WHSMobileAppStepOverridePutNewLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-265">WHSMobileAppStepOverridePutNewLocation</span></span> |
| <span data-ttu-id="73a20-266">PieceByPieceConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-266">PieceByPieceConfirmation</span></span> | <span data-ttu-id="73a20-267">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-267">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="73a20-268">POLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-268">POLineNum</span></span> | <span data-ttu-id="73a20-269">WHSMobileAppStepPOLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-269">WHSMobileAppStepPOLineNum</span></span> |
| <span data-ttu-id="73a20-270">Nº da OC</span><span class="sxs-lookup"><span data-stu-id="73a20-270">PONum</span></span> | <span data-ttu-id="73a20-271">WHSMobileAppStepPONum</span><span class="sxs-lookup"><span data-stu-id="73a20-271">WHSMobileAppStepPONum</span></span> |
| <span data-ttu-id="73a20-272">PositionFull</span><span class="sxs-lookup"><span data-stu-id="73a20-272">PositionFull</span></span> | <span data-ttu-id="73a20-273">WHSMobileAppStepPositionFull</span><span class="sxs-lookup"><span data-stu-id="73a20-273">WHSMobileAppStepPositionFull</span></span> |
| <span data-ttu-id="73a20-274">PositionFullQty</span><span class="sxs-lookup"><span data-stu-id="73a20-274">PositionFullQty</span></span> | <span data-ttu-id="73a20-275">WHSMobileAppStepPositionFullQty</span><span class="sxs-lookup"><span data-stu-id="73a20-275">WHSMobileAppStepPositionFullQty</span></span> |
| <span data-ttu-id="73a20-276">Concentração</span><span class="sxs-lookup"><span data-stu-id="73a20-276">Potency</span></span> | <span data-ttu-id="73a20-277">WHSMobileAppStepPotency</span><span class="sxs-lookup"><span data-stu-id="73a20-277">WHSMobileAppStepPotency</span></span> |
| <span data-ttu-id="73a20-278">PrinterName</span><span class="sxs-lookup"><span data-stu-id="73a20-278">PrinterName</span></span> | <span data-ttu-id="73a20-279">WHSMobileAppStepPrinterName</span><span class="sxs-lookup"><span data-stu-id="73a20-279">WHSMobileAppStepPrinterName</span></span> |
| <span data-ttu-id="73a20-280">ProdId</span><span class="sxs-lookup"><span data-stu-id="73a20-280">ProdId</span></span> | <span data-ttu-id="73a20-281">WHSMobileAppStepProdId</span><span class="sxs-lookup"><span data-stu-id="73a20-281">WHSMobileAppStepProdId</span></span> |
| <span data-ttu-id="73a20-282">ProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-282">ProdLastPalletConfirmation</span></span> | <span data-ttu-id="73a20-283">WHSMobileAppStepProdLastPalletConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-283">WHSMobileAppStepProdLastPalletConfirmation</span></span> |
| <span data-ttu-id="73a20-284">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-284">ProductConfirmation</span></span> | <span data-ttu-id="73a20-285">WHSMobileAppStepProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-285">WHSMobileAppStepProductConfirmation</span></span> |
| <span data-ttu-id="73a20-286">ProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-286">ProductionScrapConfirmation</span></span> | <span data-ttu-id="73a20-287">WHSMobileAppStepProductionScrapConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-287">WHSMobileAppStepProductionScrapConfirmation</span></span> |
| <span data-ttu-id="73a20-288">Colocar</span><span class="sxs-lookup"><span data-stu-id="73a20-288">Put</span></span> | <span data-ttu-id="73a20-289">WHSMobileAppStepPut</span><span class="sxs-lookup"><span data-stu-id="73a20-289">WHSMobileAppStepPut</span></span> |
| <span data-ttu-id="73a20-290">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-290">PutawayClusterId</span></span> | <span data-ttu-id="73a20-291">WHSMobileAppStepPutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-291">WHSMobileAppStepPutawayClusterId</span></span> |
| <span data-ttu-id="73a20-292">Qtd.</span><span class="sxs-lookup"><span data-stu-id="73a20-292">Qty</span></span> | <span data-ttu-id="73a20-293">WHSMobileAppStepQty</span><span class="sxs-lookup"><span data-stu-id="73a20-293">WHSMobileAppStepQty</span></span> |
| <span data-ttu-id="73a20-294">QtyAdjust</span><span class="sxs-lookup"><span data-stu-id="73a20-294">QtyAdjust</span></span> | <span data-ttu-id="73a20-295">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="73a20-295">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="73a20-296">QtyShort</span><span class="sxs-lookup"><span data-stu-id="73a20-296">QtyShort</span></span> | <span data-ttu-id="73a20-297">WHSMobileAppStepQtyShort</span><span class="sxs-lookup"><span data-stu-id="73a20-297">WHSMobileAppStepQtyShort</span></span> |
| <span data-ttu-id="73a20-298">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-298">QtyToConsume</span></span> | <span data-ttu-id="73a20-299">WHSMobileAppStepQtyToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-299">WHSMobileAppStepQtyToConsume</span></span> |
| <span data-ttu-id="73a20-300">QtyToPick</span><span class="sxs-lookup"><span data-stu-id="73a20-300">QtyToPick</span></span> | <span data-ttu-id="73a20-301">WHSMobileAppStepQtyToPick</span><span class="sxs-lookup"><span data-stu-id="73a20-301">WHSMobileAppStepQtyToPick</span></span> |
| <span data-ttu-id="73a20-302">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="73a20-302">QtyToPut</span></span> | <span data-ttu-id="73a20-303">WHSMobileAppStepQtyToPut</span><span class="sxs-lookup"><span data-stu-id="73a20-303">WHSMobileAppStepQtyToPut</span></span> |
| <span data-ttu-id="73a20-304">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="73a20-304">QtyToScrap</span></span> | <span data-ttu-id="73a20-305">WHSMobileAppStepQtyToScrap</span><span class="sxs-lookup"><span data-stu-id="73a20-305">WHSMobileAppStepQtyToScrap</span></span> |
| <span data-ttu-id="73a20-306">QtyVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-306">QtyVerification</span></span> | <span data-ttu-id="73a20-307">WHSMobileAppStepQtyVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-307">WHSMobileAppStepQtyVerification</span></span> |
| <span data-ttu-id="73a20-308">QtyWithScanningLimit</span><span class="sxs-lookup"><span data-stu-id="73a20-308">QtyWithScanningLimit</span></span> | <span data-ttu-id="73a20-309">WHSMobileAppStepQtyAdjust</span><span class="sxs-lookup"><span data-stu-id="73a20-309">WHSMobileAppStepQtyAdjust</span></span> |
| <span data-ttu-id="73a20-310">ReasonString</span><span class="sxs-lookup"><span data-stu-id="73a20-310">ReasonString</span></span> | <span data-ttu-id="73a20-311">WHSMobileAppStepReasonString</span><span class="sxs-lookup"><span data-stu-id="73a20-311">WHSMobileAppStepReasonString</span></span> |
| <span data-ttu-id="73a20-312">RecvLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-312">RecvLocationId</span></span> | <span data-ttu-id="73a20-313">WHSMobileAppStepRecvLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-313">WHSMobileAppStepRecvLocationId</span></span> |
| <span data-ttu-id="73a20-314">RemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-314">RemoveContainerId</span></span> | <span data-ttu-id="73a20-315">WHSMobileAppStepRemoveContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-315">WHSMobileAppStepRemoveContainerId</span></span> |
| <span data-ttu-id="73a20-316">ReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-316">ReprintLabelConfirmation</span></span> | <span data-ttu-id="73a20-317">WHSMobileAppStepReprintLabelConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-317">WHSMobileAppStepReprintLabelConfirmation</span></span> |
| <span data-ttu-id="73a20-318">RMANum</span><span class="sxs-lookup"><span data-stu-id="73a20-318">RMANum</span></span> | <span data-ttu-id="73a20-319">WHSMobileAppStepRMANum</span><span class="sxs-lookup"><span data-stu-id="73a20-319">WHSMobileAppStepRMANum</span></span> |
| <span data-ttu-id="73a20-320">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="73a20-320">ShortPickReason</span></span> | <span data-ttu-id="73a20-321">WHSMobileAppStepShortPickReason</span><span class="sxs-lookup"><span data-stu-id="73a20-321">WHSMobileAppStepShortPickReason</span></span> |
| <span data-ttu-id="73a20-322">SortConOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-322">SortConOrLP</span></span> | <span data-ttu-id="73a20-323">WHSMobileAppStepSortConOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-323">WHSMobileAppStepSortConOrLP</span></span> |
| <span data-ttu-id="73a20-324">SortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-324">SortLicensePlateId</span></span> | <span data-ttu-id="73a20-325">WHSMobileAppStepSortLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-325">WHSMobileAppStepSortLicensePlateId</span></span> |
| <span data-ttu-id="73a20-326">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="73a20-326">SortPositionId</span></span> | <span data-ttu-id="73a20-327">WHSMobileAppStepSortPositionId</span><span class="sxs-lookup"><span data-stu-id="73a20-327">WHSMobileAppStepSortPositionId</span></span> |
| <span data-ttu-id="73a20-328">SortVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-328">SortVerification</span></span> | <span data-ttu-id="73a20-329">WHSMobileAppStepSortVerification</span><span class="sxs-lookup"><span data-stu-id="73a20-329">WHSMobileAppStepSortVerification</span></span> |
| <span data-ttu-id="73a20-330">StartLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-330">StartLocationId</span></span> | <span data-ttu-id="73a20-331">WHSMobileAppStepStartLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-331">WHSMobileAppStepStartLocationId</span></span> |
| <span data-ttu-id="73a20-332">StartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-332">StartProdOrderConfirmation</span></span> | <span data-ttu-id="73a20-333">WHSMobileAppStepStartProdOrderConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-333">WHSMobileAppStepStartProdOrderConfirmation</span></span> |
| <span data-ttu-id="73a20-334">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-334">TargetLicensePlateId</span></span> | <span data-ttu-id="73a20-335">WHSMobileAppStepTargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-335">WHSMobileAppStepTargetLicensePlateId</span></span> |
| <span data-ttu-id="73a20-336">TOLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-336">TOLineNum</span></span> | <span data-ttu-id="73a20-337">WHSMobileAppStepTOLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-337">WHSMobileAppStepTOLineNum</span></span> |
| <span data-ttu-id="73a20-338">ToLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-338">ToLocation</span></span> | <span data-ttu-id="73a20-339">WHSMobileAppStepToLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-339">WHSMobileAppStepToLocation</span></span> |
| <span data-ttu-id="73a20-340">TONum</span><span class="sxs-lookup"><span data-stu-id="73a20-340">TONum</span></span> | <span data-ttu-id="73a20-341">WHSMobileAppStepTONum</span><span class="sxs-lookup"><span data-stu-id="73a20-341">WHSMobileAppStepTONum</span></span> |
| <span data-ttu-id="73a20-342">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="73a20-342">ToWarehouse</span></span> | <span data-ttu-id="73a20-343">WHSMobileAppStepWarehouseTo</span><span class="sxs-lookup"><span data-stu-id="73a20-343">WHSMobileAppStepWarehouseTo</span></span> |
| <span data-ttu-id="73a20-344">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-344">TransportLoadId</span></span> | <span data-ttu-id="73a20-345">WHSMobileAppStepTransportLoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-345">WHSMobileAppStepTransportLoadId</span></span> |
| <span data-ttu-id="73a20-346">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="73a20-346">WaveLabelId</span></span> | <span data-ttu-id="73a20-347">WHSMobileAppStepWaveLabelId</span><span class="sxs-lookup"><span data-stu-id="73a20-347">WHSMobileAppStepWaveLabelId</span></span> |
| <span data-ttu-id="73a20-348">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="73a20-348">WaveLblQty</span></span> | <span data-ttu-id="73a20-349">WHSMobileAppStepWaveLblQty</span><span class="sxs-lookup"><span data-stu-id="73a20-349">WHSMobileAppStepWaveLblQty</span></span> |
| <span data-ttu-id="73a20-350">Peso</span><span class="sxs-lookup"><span data-stu-id="73a20-350">Weight</span></span> | <span data-ttu-id="73a20-351">WHSMobileAppStepWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-351">WHSMobileAppStepWeight</span></span> |
| <span data-ttu-id="73a20-352">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-352">WeightToConsume</span></span> | <span data-ttu-id="73a20-353">WHSMobileAppStepWeightToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-353">WHSMobileAppStepWeightToConsume</span></span> |
| <span data-ttu-id="73a20-354">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="73a20-354">WHSAdjustmentType</span></span> | <span data-ttu-id="73a20-355">WHSMobileAppStepWHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="73a20-355">WHSMobileAppStepWHSAdjustmentType</span></span> |
| <span data-ttu-id="73a20-356">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="73a20-356">WHSReceivingException</span></span> | <span data-ttu-id="73a20-357">WHSMobileAppStepWHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="73a20-357">WHSMobileAppStepWHSReceivingException</span></span> |
| <span data-ttu-id="73a20-358">WHSWorkException</span><span class="sxs-lookup"><span data-stu-id="73a20-358">WHSWorkException</span></span> | <span data-ttu-id="73a20-359">WHSMobileAppStepWHSWorkException</span><span class="sxs-lookup"><span data-stu-id="73a20-359">WHSMobileAppStepWHSWorkException</span></span> |
| <span data-ttu-id="73a20-360">WHSWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-360">WHSWorkLicensePlateId</span></span> | <span data-ttu-id="73a20-361">WHSMobileAppStepWorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-361">WHSMobileAppStepWorkLicensePlateId</span></span> |
| <span data-ttu-id="73a20-362">WMSLocationId</span><span class="sxs-lookup"><span data-stu-id="73a20-362">WMSLocationId</span></span> | <span data-ttu-id="73a20-363">WHSMobileAppStepLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-363">WHSMobileAppStepLocation</span></span> |
| <span data-ttu-id="73a20-364">WorkId</span><span class="sxs-lookup"><span data-stu-id="73a20-364">WorkId</span></span> | <span data-ttu-id="73a20-365">WHSMobileAppStepWorkId</span><span class="sxs-lookup"><span data-stu-id="73a20-365">WHSMobileAppStepWorkId</span></span> |
| <span data-ttu-id="73a20-366">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="73a20-366">WorkIdToCancel</span></span> | <span data-ttu-id="73a20-367">WHSMobileAppStepWorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="73a20-367">WHSMobileAppStepWorkIdToCancel</span></span> |
| <span data-ttu-id="73a20-368">WorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="73a20-368">WorkLPIdPutawayCluster</span></span> | <span data-ttu-id="73a20-369">WHSMobileAppStepWorkLPIdPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="73a20-369">WHSMobileAppStepWorkLPIdPutawayCluster</span></span> |
| <span data-ttu-id="73a20-370">WorkPoolId</span><span class="sxs-lookup"><span data-stu-id="73a20-370">WorkPoolId</span></span> | <span data-ttu-id="73a20-371">WHSMobileAppStepWorkPoolId</span><span class="sxs-lookup"><span data-stu-id="73a20-371">WHSMobileAppStepWorkPoolId</span></span> |
| <span data-ttu-id="73a20-372">ZoneId</span><span class="sxs-lookup"><span data-stu-id="73a20-372">ZoneId</span></span> | <span data-ttu-id="73a20-373">WHSMobileAppStepZoneId</span><span class="sxs-lookup"><span data-stu-id="73a20-373">WHSMobileAppStepZoneId</span></span> |

### <a name="available-step-icons"></a><a name="step-icons"></a><span data-ttu-id="73a20-374">Ícones de etapas disponíveis</span><span class="sxs-lookup"><span data-stu-id="73a20-374">Available step icons</span></span>

<span data-ttu-id="73a20-375">O sistema inclui uma coleção de ícones de etapas padrão que você também pode usar para suas etapas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="73a20-375">The system includes a collection of standard step icons that you can also use for your custom steps.</span></span> <span data-ttu-id="73a20-376">No momento, não é possível carregar ícones de etapas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="73a20-376">You can't currently upload custom step icons.</span></span> <span data-ttu-id="73a20-377">Portanto, você deve sempre selecionar um dos ícones de etapa padrão.</span><span class="sxs-lookup"><span data-stu-id="73a20-377">Therefore, you must always select one of the standard step icons.</span></span>

<span data-ttu-id="73a20-378">A tabela a seguir mostra cada ícone de etapa padrão atualmente disponível e seu nome.</span><span class="sxs-lookup"><span data-stu-id="73a20-378">The following table shows every standard step icon that is currently available, and its name.</span></span>

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Sobre o ícone de etapa"><br><span data-ttu-id="73a20-380">Sobre</span><span class="sxs-lookup"><span data-stu-id="73a20-380">About</span></span></td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Adicionar placa de licença ou ícone de etapa de item"><br><span data-ttu-id="73a20-382">AddLpOrItem</span><span class="sxs-lookup"><span data-stu-id="73a20-382">AddLpOrItem</span></span></td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Ícone de etapa de disposição de lote"><br><span data-ttu-id="73a20-384">BatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-384">BatchDisposition</span></span></td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Ícone de etapa da operadora"><br><span data-ttu-id="73a20-386">Transportadora</span><span class="sxs-lookup"><span data-stu-id="73a20-386">Carrier</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Ícone de etapa do rótulo de peso variável"><br><span data-ttu-id="73a20-388">CatchWeightTag</span><span class="sxs-lookup"><span data-stu-id="73a20-388">CatchWeightTag</span></span></td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Ícone de etapa de peso do rótulo de peso variável"><br><span data-ttu-id="73a20-390">CatchWeightTagWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-390">CatchWeightTagWeight</span></span></td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Ícone de etapa de dígito de verificação"><br><span data-ttu-id="73a20-392">CheckDigit</span><span class="sxs-lookup"><span data-stu-id="73a20-392">CheckDigit</span></span></td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Ícone de etapa de ID de check-in ou check-out"><br><span data-ttu-id="73a20-394">CheckInOutId</span><span class="sxs-lookup"><span data-stu-id="73a20-394">CheckInOutId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Ícone de etapa da placa de licença secundária"><br><span data-ttu-id="73a20-396">ChildLP</span><span class="sxs-lookup"><span data-stu-id="73a20-396">ChildLP</span></span></td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Ícone de etapa de ID de cluster"><br><span data-ttu-id="73a20-398">ClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-398">ClusterId</span></span></td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Ícone de etapa de posição de cluster"><br><span data-ttu-id="73a20-400">ClusterPosition</span><span class="sxs-lookup"><span data-stu-id="73a20-400">ClusterPosition</span></span></td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Ícone de etapa de ID de configuração"><br><span data-ttu-id="73a20-402">ConfigId</span><span class="sxs-lookup"><span data-stu-id="73a20-402">ConfigId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Ícone de etapa de campo configurado"><br><span data-ttu-id="73a20-404">ConfiguredField</span><span class="sxs-lookup"><span data-stu-id="73a20-404">ConfiguredField</span></span></td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Ícone de etapa Con ou LP"><br><span data-ttu-id="73a20-406">ConOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-406">ConOrLP</span></span></td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="ID de etapa Consolidar a partir da ID de placa de licença"><br><span data-ttu-id="73a20-408">ConsolidateFromLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="73a20-408">ConsolidateFromLicensePlateID</span></span></td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="ID de etapa Consolidar para a ID de placa de licença"><br><span data-ttu-id="73a20-410">ConsolidateToLicensePlateID</span><span class="sxs-lookup"><span data-stu-id="73a20-410">ConsolidateToLicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Ícone de etapa do tipo de contêiner"><br><span data-ttu-id="73a20-412">ContainerType</span><span class="sxs-lookup"><span data-stu-id="73a20-412">ContainerType</span></span></td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Ícone de etapa de contagem"><br><span data-ttu-id="73a20-414">Contagem</span><span class="sxs-lookup"><span data-stu-id="73a20-414">Counting</span></span></td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Ícone de etapa do código do motivo de contagem"><br><span data-ttu-id="73a20-416">CountingReasonCode</span><span class="sxs-lookup"><span data-stu-id="73a20-416">CountingReasonCode</span></span></td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Ícone de etapa do código do país de origem"><br><span data-ttu-id="73a20-418">CountryOfOrigin</span><span class="sxs-lookup"><span data-stu-id="73a20-418">CountryOfOrigin</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Ícone da etapa de disposição"><br><span data-ttu-id="73a20-420">Disposition</span><span class="sxs-lookup"><span data-stu-id="73a20-420">Disposition</span></span></td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Ícone de etapa concluída"><br><span data-ttu-id="73a20-422">Concluídos</span><span class="sxs-lookup"><span data-stu-id="73a20-422">Done</span></span></td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Ícone da etapa de confirmação de verificação do motorista"><br><span data-ttu-id="73a20-424">DriverCheckInConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-424">DriverCheckInConfirmation</span></span></td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Ícone de etapa de verificação de identificação do motorista"><br><span data-ttu-id="73a20-426">DriverCheckInId</span><span class="sxs-lookup"><span data-stu-id="73a20-426">DriverCheckInId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Ícone de etapa de verificação de registro de saída do motorista"><br><span data-ttu-id="73a20-428">DriverCheckOutId</span><span class="sxs-lookup"><span data-stu-id="73a20-428">DriverCheckOutId</span></span></td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Ícone de etapa da data de expiração"><br><span data-ttu-id="73a20-430">ExpDate</span><span class="sxs-lookup"><span data-stu-id="73a20-430">ExpDate</span></span></td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Ícone de etapa de campo"><br><span data-ttu-id="73a20-432">Campo</span><span class="sxs-lookup"><span data-stu-id="73a20-432">Field</span></span></td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Ícone da etapa Da disposição em lote"><br><span data-ttu-id="73a20-434">FromBatchDisposition</span><span class="sxs-lookup"><span data-stu-id="73a20-434">FromBatchDisposition</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Ícone de etapa Do status de estoque"><br><span data-ttu-id="73a20-436">FromInventoryStatus</span><span class="sxs-lookup"><span data-stu-id="73a20-436">FromInventoryStatus</span></span></td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Ícone de etapa de atributo de ID"><br><span data-ttu-id="73a20-438">IdAttribute</span><span class="sxs-lookup"><span data-stu-id="73a20-438">IdAttribute</span></span></td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Ícone de etapa de ID de lote de estoque"><br><span data-ttu-id="73a20-440">InventBatchID</span><span class="sxs-lookup"><span data-stu-id="73a20-440">InventBatchID</span></span></td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Ícone de etapa de ID da cor de estoque"><br><span data-ttu-id="73a20-442">InventColorID</span><span class="sxs-lookup"><span data-stu-id="73a20-442">InventColorID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Ícone de etapa de localização de estoque"><br><span data-ttu-id="73a20-444">InventLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-444">InventLocation</span></span></td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Ícone de etapa de ID da série de estoque"><br><span data-ttu-id="73a20-446">InventSerialID</span><span class="sxs-lookup"><span data-stu-id="73a20-446">InventSerialID</span></span></td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Ícone de etapa de ID do tamanho do estoque"><br><span data-ttu-id="73a20-448">InventSizeID</span><span class="sxs-lookup"><span data-stu-id="73a20-448">InventSizeID</span></span></td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Ícone de etapa da ID do status do estoque"><br><span data-ttu-id="73a20-450">InventStatusID</span><span class="sxs-lookup"><span data-stu-id="73a20-450">InventStatusID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Ícone de etapa de ID do estilo do estoque"><br><span data-ttu-id="73a20-452">InventStyleID</span><span class="sxs-lookup"><span data-stu-id="73a20-452">InventStyleID</span></span></td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Ícone de etapa da ID da versão do estoque"><br><span data-ttu-id="73a20-454">InventVersionID</span><span class="sxs-lookup"><span data-stu-id="73a20-454">InventVersionID</span></span></td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Ícone de etapa de ID de item"><br><span data-ttu-id="73a20-456">ItemID</span><span class="sxs-lookup"><span data-stu-id="73a20-456">ItemID</span></span></td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Ícone de etapa da ID do contêiner ITM"><br><span data-ttu-id="73a20-458">ITMContainerID</span><span class="sxs-lookup"><span data-stu-id="73a20-458">ITMContainerID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ícone de etapa da ID de remessa ITM"><br><span data-ttu-id="73a20-460">ITMShipmentID</span><span class="sxs-lookup"><span data-stu-id="73a20-460">ITMShipmentID</span></span></td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Ícone de etapa de identificação do cartão kanban"><br><span data-ttu-id="73a20-462">KanbanCardID</span><span class="sxs-lookup"><span data-stu-id="73a20-462">KanbanCardID</span></span></td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Ícone de etapa de identificação do cartão ou kanban"><br><span data-ttu-id="73a20-464">KanbanOrCardID</span><span class="sxs-lookup"><span data-stu-id="73a20-464">KanbanOrCardID</span></span></td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Ícone de etapa da ID da placa de licença"><br><span data-ttu-id="73a20-466">LicensePlateID</span><span class="sxs-lookup"><span data-stu-id="73a20-466">LicensePlateID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Ícone de etapa de ID de carregamento"><br><span data-ttu-id="73a20-468">LoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-468">LoadId</span></span></td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Ícone de etapa de posição de placa de licença de localização"><br><span data-ttu-id="73a20-470">LocationLicensePlatePosition</span><span class="sxs-lookup"><span data-stu-id="73a20-470">LocationLicensePlatePosition</span></span></td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Ícone da etapa de localização ou placa de licença"><br><span data-ttu-id="73a20-472">LocOrLP</span><span class="sxs-lookup"><span data-stu-id="73a20-472">LocOrLP</span></span></td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Ícone da etapa de verificação de localização ou placa de licença"><br><span data-ttu-id="73a20-474">LocOrLPCheck</span><span class="sxs-lookup"><span data-stu-id="73a20-474">LocOrLPCheck</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Ícone da etapa de a partir de localização ou placa de licença"><br><span data-ttu-id="73a20-476">LocOrLPFrom</span><span class="sxs-lookup"><span data-stu-id="73a20-476">LocOrLPFrom</span></span></td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Ícone da etapa de para localização ou placa de licença"><br><span data-ttu-id="73a20-478">LocOrLPTo</span><span class="sxs-lookup"><span data-stu-id="73a20-478">LocOrLPTo</span></span></td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Ícone de etapa de processo longo concluído"><br><span data-ttu-id="73a20-480">LongProcessCompleted</span><span class="sxs-lookup"><span data-stu-id="73a20-480">LongProcessCompleted</span></span></td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Ícone de etapa de LP principal de interrupção de LP"><br><span data-ttu-id="73a20-482">LPBreakParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-482">LPBreakParentLP</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Ícone de etapa da ID de mesclagem de contêiner"><br><span data-ttu-id="73a20-484">MergeContainerId</span><span class="sxs-lookup"><span data-stu-id="73a20-484">MergeContainerId</span></span></td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Ícone de etapa do número de linha da placa de licença"><br><span data-ttu-id="73a20-486">MixedLPLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-486">MixedLPLineNum</span></span></td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Ícone de etapa de peso de saída"><br><span data-ttu-id="73a20-488">OutboundWeight</span><span class="sxs-lookup"><span data-stu-id="73a20-488">OutboundWeight</span></span></td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Ícone de etapa de proprietário"><br><span data-ttu-id="73a20-490">Proprietário</span><span class="sxs-lookup"><span data-stu-id="73a20-490">Owner</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Ícone de etapa da placa de licença principal"><br><span data-ttu-id="73a20-492">ParentLP</span><span class="sxs-lookup"><span data-stu-id="73a20-492">ParentLP</span></span></td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Ícone de etapa de confirmação"><br><span data-ttu-id="73a20-494">PleaseConfirm</span><span class="sxs-lookup"><span data-stu-id="73a20-494">PleaseConfirm</span></span></td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Ícone de etapa de número de linha da ordem de compra"><br><span data-ttu-id="73a20-496">POLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-496">POLineNum</span></span></td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Ícone de etapa de número da ordem de compra"><br><span data-ttu-id="73a20-498">Nº da OC</span><span class="sxs-lookup"><span data-stu-id="73a20-498">PONum</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Ícone de etapa de posição completa"><br><span data-ttu-id="73a20-500">PositionFull</span><span class="sxs-lookup"><span data-stu-id="73a20-500">PositionFull</span></span></td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Ícone de etapa de concentração"><br><span data-ttu-id="73a20-502">Concentração</span><span class="sxs-lookup"><span data-stu-id="73a20-502">Potency</span></span></td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Ícone de etapa de nome da impressora"><br><span data-ttu-id="73a20-504">PrinterName</span><span class="sxs-lookup"><span data-stu-id="73a20-504">PrinterName</span></span></td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Ícone de etapa de ID de produção"><br><span data-ttu-id="73a20-506">ProdId</span><span class="sxs-lookup"><span data-stu-id="73a20-506">ProdId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Ícone de etapa de confirmação do produto"><br><span data-ttu-id="73a20-508">ProductConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-508">ProductConfirmation</span></span></td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Ícone de etapa de colocação"><br><span data-ttu-id="73a20-510">Colocar</span><span class="sxs-lookup"><span data-stu-id="73a20-510">Put</span></span></td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Ícone de etapa de ID de cluster de armazenamento"><br><span data-ttu-id="73a20-512">PutawayClusterId</span><span class="sxs-lookup"><span data-stu-id="73a20-512">PutawayClusterId</span></span></td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Ícone de etapa de quantidade"><br><span data-ttu-id="73a20-514">Qtd.</span><span class="sxs-lookup"><span data-stu-id="73a20-514">Qty</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Ícone de etapa de ajuste de quantidade em"><br><span data-ttu-id="73a20-516">QtyAdjustIn</span><span class="sxs-lookup"><span data-stu-id="73a20-516">QtyAdjustIn</span></span></td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Ícone de etapa de quantidade curta"><br><span data-ttu-id="73a20-518">QtyShort</span><span class="sxs-lookup"><span data-stu-id="73a20-518">QtyShort</span></span></td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Ícone de etapa de quantidade para consumo"><br><span data-ttu-id="73a20-520">QtyToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-520">QtyToConsume</span></span></td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Ícone de etapa de quantidade para colocação"><br><span data-ttu-id="73a20-522">QtyToPut</span><span class="sxs-lookup"><span data-stu-id="73a20-522">QtyToPut</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Ícone de etapa de quantidade para sucata"><br><span data-ttu-id="73a20-524">QtyToScrap</span><span class="sxs-lookup"><span data-stu-id="73a20-524">QtyToScrap</span></span></td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Ícone de etapa de confirmação da quantidade"><br><span data-ttu-id="73a20-526">QuantityConfirmation</span><span class="sxs-lookup"><span data-stu-id="73a20-526">QuantityConfirmation</span></span></td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Ícone de etapa de relatório como trabalho final concluído"><br><span data-ttu-id="73a20-528">RAFEndJob</span><span class="sxs-lookup"><span data-stu-id="73a20-528">RAFEndJob</span></span></td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Ícone de etapa de ID de recebimento de localização"><br><span data-ttu-id="73a20-530">RecvLocationID</span><span class="sxs-lookup"><span data-stu-id="73a20-530">RecvLocationID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Ícone de etapa da ID de remoção de contêiner"><br><span data-ttu-id="73a20-532">RemoveContainerID</span><span class="sxs-lookup"><span data-stu-id="73a20-532">RemoveContainerID</span></span></td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Ícone de etapa de número de ADM"><br><span data-ttu-id="73a20-534">RMANum</span><span class="sxs-lookup"><span data-stu-id="73a20-534">RMANum</span></span></td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Ícone de etapa de seleção de ordem"><br><span data-ttu-id="73a20-536">SelectOrder</span><span class="sxs-lookup"><span data-stu-id="73a20-536">SelectOrder</span></span></td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Ícone de etapa do motivo de separação insuficiente"><br><span data-ttu-id="73a20-538">ShortPickReason</span><span class="sxs-lookup"><span data-stu-id="73a20-538">ShortPickReason</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Ícone de etapa de ID de posição insuficiente"><br><span data-ttu-id="73a20-540">SortPositionId</span><span class="sxs-lookup"><span data-stu-id="73a20-540">SortPositionId</span></span></td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Ícone de etapa da ID da placa de licença alvo"><br><span data-ttu-id="73a20-542">TargetLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-542">TargetLicensePlateId</span></span></td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Ícone de etapa de para número de linha"><br><span data-ttu-id="73a20-544">ToLineNum</span><span class="sxs-lookup"><span data-stu-id="73a20-544">ToLineNum</span></span></td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Ícone de etapa para localização"><br><span data-ttu-id="73a20-546">ToLocation</span><span class="sxs-lookup"><span data-stu-id="73a20-546">ToLocation</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Ícone de etapa para número"><br><span data-ttu-id="73a20-548">ToNum</span><span class="sxs-lookup"><span data-stu-id="73a20-548">ToNum</span></span></td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Ícone de etapa para depósito"><br><span data-ttu-id="73a20-550">ToWarehouse</span><span class="sxs-lookup"><span data-stu-id="73a20-550">ToWarehouse</span></span></td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Ícone de etapa de ID de carga de transporte"><br><span data-ttu-id="73a20-552">TransportLoadId</span><span class="sxs-lookup"><span data-stu-id="73a20-552">TransportLoadId</span></span></td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Ícone de etapa de ID de lote de fornecedor"><br><span data-ttu-id="73a20-554">VendBatchId</span><span class="sxs-lookup"><span data-stu-id="73a20-554">VendBatchId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Ícone de etapa da ID da etiqueta do ciclo"><br><span data-ttu-id="73a20-556">WaveLabelId</span><span class="sxs-lookup"><span data-stu-id="73a20-556">WaveLabelId</span></span></td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Ícone de etapa da quantidade da etiqueta do ciclo"><br><span data-ttu-id="73a20-558">WaveLblQty</span><span class="sxs-lookup"><span data-stu-id="73a20-558">WaveLblQty</span></span></td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Ícone de etapa de peso"><br><span data-ttu-id="73a20-560">Peso</span><span class="sxs-lookup"><span data-stu-id="73a20-560">Weight</span></span></td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Ícone de etapa do peso para consumo"><br><span data-ttu-id="73a20-562">WeightToConsume</span><span class="sxs-lookup"><span data-stu-id="73a20-562">WeightToConsume</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Ícone de etapa do tipo de ajuste WHS"><br><span data-ttu-id="73a20-564">WHSAdjustmentType</span><span class="sxs-lookup"><span data-stu-id="73a20-564">WHSAdjustmentType</span></span></td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Ícone de etapa de exceção de recebimento WHS"><br><span data-ttu-id="73a20-566">WHSReceivingException</span><span class="sxs-lookup"><span data-stu-id="73a20-566">WHSReceivingException</span></span></td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Ícone de etapa de ID de localização WMS"><br><span data-ttu-id="73a20-568">WMSLocationID</span><span class="sxs-lookup"><span data-stu-id="73a20-568">WMSLocationID</span></span></td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Ícone de etapa de ID de trabalho"><br><span data-ttu-id="73a20-570">WorkId</span><span class="sxs-lookup"><span data-stu-id="73a20-570">WorkId</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Ícone de etapa de ID de trabalho para cancelamento"><br><span data-ttu-id="73a20-572">WorkIdToCancel</span><span class="sxs-lookup"><span data-stu-id="73a20-572">WorkIdToCancel</span></span></td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Ícone de etapa da ID da placa de licença de trabalho"><br><span data-ttu-id="73a20-574">WorkLicensePlateId</span><span class="sxs-lookup"><span data-stu-id="73a20-574">WorkLicensePlateId</span></span></td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Ícone de etapa de cluster de armazenamento da ID da placa de licença de trabalho"><br><span data-ttu-id="73a20-576">WorkLPIDPutawayCluster</span><span class="sxs-lookup"><span data-stu-id="73a20-576">WorkLPIDPutawayCluster</span></span></td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Ícone de etapa de ID de pool de trabalho"><br><span data-ttu-id="73a20-578">WorkPoolID</span><span class="sxs-lookup"><span data-stu-id="73a20-578">WorkPoolID</span></span></td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Ícone de etapa de ID de zona"><br><span data-ttu-id="73a20-580">ZoneID</span><span class="sxs-lookup"><span data-stu-id="73a20-580">ZoneID</span></span></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a><span data-ttu-id="73a20-581">Exemplo: Atribuir ícones e títulos de etapa para um fluxo personalizado</span><span class="sxs-lookup"><span data-stu-id="73a20-581">Example: Assign step icons and titles for a custom flow</span></span>

<span data-ttu-id="73a20-582">Este exemplo explica como configurar ícones e títulos de etapas para um fluxo de tarefa personalizado.</span><span class="sxs-lookup"><span data-stu-id="73a20-582">This example explains how to set up step icons and titles for a custom task flow.</span></span> <span data-ttu-id="73a20-583">O cenário é baseado em um exemplo de fluxo de tarefa personalizada que é apresentado e explorado em mais detalhes na seguinte postagem do blog: [Personalização do aplicativo móvel de depósito](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span><span class="sxs-lookup"><span data-stu-id="73a20-583">The scenario is built on an example of a custom task flow that is presented and explored in more detail in the following blog post: [Customizing the Warehousing Mobile App](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app).</span></span> <span data-ttu-id="73a20-584">O fluxo de tarefas funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="73a20-584">The task flow works in the following way:</span></span>

1. <span data-ttu-id="73a20-585">O aplicativo mostra uma página que solicita que o trabalhador forneça uma ID de contêiner (por exemplo, lendo um código de barras).</span><span class="sxs-lookup"><span data-stu-id="73a20-585">The app shows a page that prompts the worker to provide a container ID (for example, by scanning a bar code).</span></span>
1. <span data-ttu-id="73a20-586">Se a ID do contêiner for válida, o aplicativo abre uma nova página que solicita ao trabalhador o peso.</span><span class="sxs-lookup"><span data-stu-id="73a20-586">If the container ID is valid, the app opens a new page that prompts the worker for the weight.</span></span> <span data-ttu-id="73a20-587">(Se a ID do contêiner não for válida, o trabalhador será redirecionado à primeira página.)</span><span class="sxs-lookup"><span data-stu-id="73a20-587">(If the container ID isn't valid, the worker is returned to the first page.)</span></span>
1. <span data-ttu-id="73a20-588">Quando o trabalhador insere um peso válido, o sistema armazena o peso e redireciona o trabalhador à primeira página.</span><span class="sxs-lookup"><span data-stu-id="73a20-588">When the worker enters a valid weight, the system stores the weight and returns the worker to the first page.</span></span>

<span data-ttu-id="73a20-589">A ilustração a seguir mostra esse fluxo de tarefa.</span><span class="sxs-lookup"><span data-stu-id="73a20-589">The following illustration shows this task flow.</span></span>

<span data-ttu-id="73a20-590">![Diagrama de fluxo de tarefas](media/step-icons-example-task-flow.png "Diagrama de fluxo de tarefas")</span><span class="sxs-lookup"><span data-stu-id="73a20-590">![Task flow diagram](media/step-icons-example-task-flow.png "Task flow diagram")</span></span>

### <a name="create-a-step-class-for-the-container-input-page"></a><span data-ttu-id="73a20-591">Criar uma classe de etapa para a página de entrada do contêiner</span><span class="sxs-lookup"><span data-stu-id="73a20-591">Create a step class for the container input page</span></span>

<span data-ttu-id="73a20-592">A página de entrada do contêiner permite que o trabalhador faça a digitalização ou insira uma ID de contêiner.</span><span class="sxs-lookup"><span data-stu-id="73a20-592">The container input page lets the worker scan or enter a container ID.</span></span>

<span data-ttu-id="73a20-593">![Página de entrada do contêiner](media/step-icons-example-container-input.png "Página de entrada do contêiner")</span><span class="sxs-lookup"><span data-stu-id="73a20-593">![Container input page](media/step-icons-example-container-input.png "Container input page")</span></span>

<span data-ttu-id="73a20-594">Na página de entrada do contêiner, o nome do controle do campo de entrada é `ContainerId`.</span><span class="sxs-lookup"><span data-stu-id="73a20-594">On the container input page, the control name of the input field is `ContainerId`.</span></span> <span data-ttu-id="73a20-595">Como esse nome de controle não está na [lista de IDs de etapa](#step-ids-classes), você não encontrará uma etapa existente baseada nele.</span><span class="sxs-lookup"><span data-stu-id="73a20-595">Because this control name isn't in the [list of step IDs](#step-ids-classes), you won't find an existing step that is based on it.</span></span> <span data-ttu-id="73a20-596">Portanto, você deve criar uma classe de etapa que representa a etapa.</span><span class="sxs-lookup"><span data-stu-id="73a20-596">Therefore, you must create a step class that represents the step.</span></span> <span data-ttu-id="73a20-597">Veja aqui um exemplo.</span><span class="sxs-lookup"><span data-stu-id="73a20-597">Here is an example.</span></span>

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

<span data-ttu-id="73a20-598">O identificador do ícone da etapa é armazenado no membro da classe `defaultStepIcon`, e o título da etapa é armazenado no membro da classe `defaultStepTitle`.</span><span class="sxs-lookup"><span data-stu-id="73a20-598">The identifier of the step icon is stored in the `defaultStepIcon` class member, and the step title is stored in the `defaultStepTitle` class member.</span></span>

<span data-ttu-id="73a20-599">Para atribuir um ícone de etapa, defina `defaultStepIcon` para uma das IDs de ícone que estão listadas na seção [Ícones de etapas disponíveis](#step-icons) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="73a20-599">To assign a step icon, set `defaultStepIcon` to one of the icon IDs that are listed in the [Available step icons](#step-icons) section earlier in this topic.</span></span>

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a><span data-ttu-id="73a20-600">Usar um ícone de etapa padrão ou personalizado e um título para a entrada de peso</span><span class="sxs-lookup"><span data-stu-id="73a20-600">Use a standard or custom step icon and title for the weight input</span></span>

<span data-ttu-id="73a20-601">A página de entrada de peso permite que o trabalhador insira um peso.</span><span class="sxs-lookup"><span data-stu-id="73a20-601">The weight input page lets the worker enter a weight.</span></span>

<span data-ttu-id="73a20-602">![Página entrada de peso](media/step-icons-example-weight-input.png "Página entrada de peso")</span><span class="sxs-lookup"><span data-stu-id="73a20-602">![Weight input page](media/step-icons-example-weight-input.png "Weight input page")</span></span>

<span data-ttu-id="73a20-603">Na página de entrada de peso, o nome do controle do campo de entrada é `Weight`, que está na [lista de IDs de etapa](#step-ids-classes).</span><span class="sxs-lookup"><span data-stu-id="73a20-603">On the weight input page, the control name of the input field is `Weight`, which is in the [list of step IDs](#step-ids-classes).</span></span> <span data-ttu-id="73a20-604">Portanto, se o ícone e o título da etapa definidos na classe `WHSMobileAppStepWeight` são aceitáveis para você, não é necessário alterar nada nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="73a20-604">Therefore, if the step icon and title that are defined in the `WHSMobileAppStepWeight` class are acceptable to you, you don't have to change anything for this step.</span></span>

<span data-ttu-id="73a20-605">No entanto, se você preferir usar um ícone ou título diferente para esta etapa, você pode substituir o método `stepId()` ou o método `stepInfo()` na classe de construtor.</span><span class="sxs-lookup"><span data-stu-id="73a20-605">However, if you prefer to use a different icon or title for this step, you can override either the `stepId()` method or the `stepInfo()` method in the builder class.</span></span> <span data-ttu-id="73a20-606">Cada fluxo de tarefa tem seu próprio construtor de informações de etapa.</span><span class="sxs-lookup"><span data-stu-id="73a20-606">Each task flow has its own step info builder.</span></span>

#### <a name="override-the-stepid-method"></a><span data-ttu-id="73a20-607">Substituir o método stepId()</span><span class="sxs-lookup"><span data-stu-id="73a20-607">Override the stepId() method</span></span>

<span data-ttu-id="73a20-608">O exemplo a seguir mostra uma maneira de modificar uma classe de construtor substituindo o método `stepId()`.</span><span class="sxs-lookup"><span data-stu-id="73a20-608">The following example shows one way that you can modify a builder class by overriding the `stepId()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

<span data-ttu-id="73a20-609">Em seguida, você cria uma classe de etapa para a etapa `NewWeight`.</span><span class="sxs-lookup"><span data-stu-id="73a20-609">You then create a step class for the `NewWeight` step.</span></span> <span data-ttu-id="73a20-610">O código deve ser semelhante ao código do exemplo `ContainerId` mostrado anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="73a20-610">The code should resemble the code for the `ContainerId` example that was shown earlier in this topic.</span></span>

#### <a name="override-the-stepinfo-method"></a><span data-ttu-id="73a20-611">Substituir o método stepInfo()</span><span class="sxs-lookup"><span data-stu-id="73a20-611">Override the stepInfo() method</span></span>

<span data-ttu-id="73a20-612">O exemplo a seguir mostra uma maneira de modificar uma classe de construtor substituindo o método `stepInfo()`.</span><span class="sxs-lookup"><span data-stu-id="73a20-612">The following example shows one way that you can modify a builder class by overriding the `stepInfo()` method.</span></span>

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

<span data-ttu-id="73a20-613">Depois, você constrói um objeto `WHSMobileAppStepInfo` e define o ícone e/ou título diretamente.</span><span class="sxs-lookup"><span data-stu-id="73a20-613">You then construct a `WHSMobileAppStepInfo` object, and set the icon and/or title directly.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73a20-614">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="73a20-614">Additional resources</span></span>

- [<span data-ttu-id="73a20-615">Instalar e conectar o aplicativo móvel Gerenciamento de Depósito</span><span class="sxs-lookup"><span data-stu-id="73a20-615">Install and connect the Warehouse Management mobile app</span></span>](install-configure-warehouse-management-app.md)
- [<span data-ttu-id="73a20-616">Configurações do usuário do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="73a20-616">Mobile device user settings</span></span>](mobile-device-user-settings.md)
