---
title: Consolidar remessas quando a política de consolidação de remessa for substituída da página Liberar para depósito
description: Este tópico apresenta um cenário em que uma ou mais linhas de venda devem ser liberadas manualmente para o depósito da página Liberar para depósito e a política de consolidação de remessa definida pelo sistema deve ser substituída antes da liberação.
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
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 23379b76367336157edad1bf2e534bf0f10799cb
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383716"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a><span data-ttu-id="0aeee-103">Consolidar remessas quando a política de consolidação de remessa for substituída da página Liberar para depósito</span><span class="sxs-lookup"><span data-stu-id="0aeee-103">Consolidate shipments when the shipment consolidation policy is overridden from the Release to warehouse page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0aeee-104">Este tópico apresenta um cenário em que uma ou mais linhas de venda devem ser liberadas manualmente para o depósito da página **Liberar para depósito** e a política de consolidação de remessa definida pelo sistema deve ser substituída antes da liberação.</span><span class="sxs-lookup"><span data-stu-id="0aeee-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="0aeee-105">Uma substituição da política de consolidação de remessa poderá ser necessária se, por exemplo, uma ordem que não costume ser consolidada com remessas abertas precise ser consolidada com remessas abertas.</span><span class="sxs-lookup"><span data-stu-id="0aeee-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="0aeee-106">Durante o cenário, você criará um conjunto de ordens de venda e, em seguida, substituirá a política de consolidação de remessa padrão antes de liberar as ordens para o depósito.</span><span class="sxs-lookup"><span data-stu-id="0aeee-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="0aeee-107">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="0aeee-107">Make demo data available</span></span>

<span data-ttu-id="0aeee-108">O cenário neste tópico faz referência a valores e registros incluídos nos dados de demonstração padrão que são fornecidos para o Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0aeee-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="0aeee-109">Se você deseja usar os valores fornecidos aqui ao fazer os exercícios, procure trabalhar em um ambiente no qual os dados de demonstração estejam instalados e defina a entidade legal como **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="0aeee-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="0aeee-110">Configure políticas de consolidação de remessa e filtros de produtos</span><span class="sxs-lookup"><span data-stu-id="0aeee-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="0aeee-111">O cenário descrito aqui pressupõe que você já ativou o recurso, fez os exercícios em [Configurar políticas de consolidação de remessa](configure-shipment-consolidation-policies.md) e criou as políticas e outros registros descritos ali.</span><span class="sxs-lookup"><span data-stu-id="0aeee-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="0aeee-112">Lembre-se de fazer os exercícios antes de continuar este cenário.</span><span class="sxs-lookup"><span data-stu-id="0aeee-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="0aeee-113">Crie as ordens de venda para este cenário</span><span class="sxs-lookup"><span data-stu-id="0aeee-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="0aeee-114">Vá para **Contas a receber \> Ordens \> Todas as ordens de venda** e crie três ordens de venda idênticas com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="0aeee-114">Go to **Accounts receivable \> Orders \> All sales orders**, and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="0aeee-115">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="0aeee-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="0aeee-116">Adicione uma linha da ordem com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="0aeee-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="0aeee-117">**Número do item:** *A0001* (um item ao qual nenhum filtro de **Código 4** está atribuído)</span><span class="sxs-lookup"><span data-stu-id="0aeee-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="0aeee-118">**Quantidade:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="0aeee-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="0aeee-119">Selecione **Estoque \> Reserva** e, no Painel de Ações, selecione **Reservar lote** para reservar a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="0aeee-119">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="0aeee-120">Libere as ordens de venda da página Liberar para depósito</span><span class="sxs-lookup"><span data-stu-id="0aeee-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="0aeee-121">Siga estas etapas para substituir a política de consolidação de remessa durante a liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="0aeee-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="0aeee-122">Vá para **Gerenciamento de depósito \> Liberar para depósito \> Liberar para depósito**.</span><span class="sxs-lookup"><span data-stu-id="0aeee-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="0aeee-123">No painel superior, selecione a primeira ordem de venda criada para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="0aeee-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="0aeee-124">Selecione **Adicionar** para adicionar a linha à liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="0aeee-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="0aeee-125">Observe que a política de consolidação de remessa *padrão* é aplicada no painel inferior.</span><span class="sxs-lookup"><span data-stu-id="0aeee-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="0aeee-126">No painel inferior, selecione **Selecionar nova política de consolidação de remessa**.</span><span class="sxs-lookup"><span data-stu-id="0aeee-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="0aeee-127">Selecione uma política que permita a consolidação com outras remessas abertas da mesma política.</span><span class="sxs-lookup"><span data-stu-id="0aeee-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="0aeee-128">Por exemplo, selecione a política *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="0aeee-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="0aeee-129">Selecione **Liberar para depósito**.</span><span class="sxs-lookup"><span data-stu-id="0aeee-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="0aeee-130">Selecione a segunda e a terceira ordens de venda criadas para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="0aeee-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="0aeee-131">Selecione **Adicionar** para adicionar as linhas à liberação para o depósito.</span><span class="sxs-lookup"><span data-stu-id="0aeee-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="0aeee-132">Observe que a política *padrão* é aplicada no painel inferior.</span><span class="sxs-lookup"><span data-stu-id="0aeee-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="0aeee-133">Selecione a segunda linha e, em seguida, no campo **Selecionar nova política de consolidação de remessa**, selecione a política *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="0aeee-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="0aeee-134">Selecione **Liberar para depósito** para as duas linhas.</span><span class="sxs-lookup"><span data-stu-id="0aeee-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="0aeee-135">Verifique as remessas</span><span class="sxs-lookup"><span data-stu-id="0aeee-135">Verify the shipments</span></span>

<span data-ttu-id="0aeee-136">Duas remessas devem ter sido criadas:</span><span class="sxs-lookup"><span data-stu-id="0aeee-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="0aeee-137">A primeira remessa contém duas linhas e foi criada usando a política de consolidação de remessa *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="0aeee-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="0aeee-138">A segunda remessa contém uma linha e foi criada usando a política de consolidação de remessa *padrão*.</span><span class="sxs-lookup"><span data-stu-id="0aeee-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="0aeee-139">Siga estas etapas para revisar as remessas que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="0aeee-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="0aeee-140">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="0aeee-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="0aeee-141">Localize e selecione a remessa necessária.</span><span class="sxs-lookup"><span data-stu-id="0aeee-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="0aeee-142">No campo **Política de consolidação de remessa**, revise a política de consolidação usada quando a remessa foi criada.</span><span class="sxs-lookup"><span data-stu-id="0aeee-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0aeee-143">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="0aeee-143">Additional resources</span></span>

- [<span data-ttu-id="0aeee-144">Políticas de consolidação da remessa</span><span class="sxs-lookup"><span data-stu-id="0aeee-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="0aeee-145">Configurar políticas de consolidação de remessa</span><span class="sxs-lookup"><span data-stu-id="0aeee-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)