---
title: A quantidade excede a porcentagem de entrega excedente durante a geração da guia de remessa
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega excedente.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249058"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="e515a-103">A quantidade excede a porcentagem de entrega excedente durante a geração da guia de remessa</span><span class="sxs-lookup"><span data-stu-id="e515a-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="e515a-104">Código de erro: SYS24920</span><span class="sxs-lookup"><span data-stu-id="e515a-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="e515a-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="e515a-105">Symptoms</span></span>

<span data-ttu-id="e515a-106">Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="e515a-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="e515a-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="e515a-108">A entrega excedente da linha é de %1%, mas o percentual permitido para entrega excedente é de apenas %2%.</span><span class="sxs-lookup"><span data-stu-id="e515a-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="e515a-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="e515a-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="e515a-110">Causa</span><span class="sxs-lookup"><span data-stu-id="e515a-110">Cause</span></span>

<span data-ttu-id="e515a-111">A quantidade escolhida para a carga ou remessa é maior do que a quantidade da ordem e não está dentro do intervalo da porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="e515a-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="e515a-112">Resolution</span></span>

<span data-ttu-id="e515a-113">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="e515a-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="e515a-114">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="e515a-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="e515a-115">Ajuste a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="e515a-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="e515a-116">Ajustar a porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="e515a-117">Inverta e faça ajustes.</span><span class="sxs-lookup"><span data-stu-id="e515a-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="e515a-118">Ajustar a quantidade da linha de carga</span><span class="sxs-lookup"><span data-stu-id="e515a-118">Adjust the load line quantity</span></span>

<span data-ttu-id="e515a-119">Use o seguinte procedimento para ajustar a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="e515a-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="e515a-120">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="e515a-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e515a-121">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="e515a-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="e515a-122">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="e515a-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="e515a-123">Na guia  **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="e515a-124">Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.</span><span class="sxs-lookup"><span data-stu-id="e515a-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="e515a-125">Na guia  **Detalhes da linha**, selecione **Ordem**.</span><span class="sxs-lookup"><span data-stu-id="e515a-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="e515a-126">Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="e515a-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="e515a-127">Ajustar a porcentagem de entrega excedente</span><span class="sxs-lookup"><span data-stu-id="e515a-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="e515a-128">Use o seguinte procedimento para ajustar a porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="e515a-129">Vá para **Contas a receber \> Ordens \> Todas as ordens**.</span><span class="sxs-lookup"><span data-stu-id="e515a-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="e515a-130">Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.</span><span class="sxs-lookup"><span data-stu-id="e515a-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="e515a-131">Na guia  **Linhas da ordem de venda**, selecione a linha da ordem de venda do item que excede a porcentagem de entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="e515a-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="e515a-132">Na guia  **Detalhes da linha**, selecione **Entrega**.</span><span class="sxs-lookup"><span data-stu-id="e515a-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="e515a-133">Defina o campo **Entrega excedente** como uma porcentagem maior que acomode a quantidade que foi separada em relação à quantidade de carga, de forma que a guia de remessa possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="e515a-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="e515a-134">Inverter e fazer ajustes</span><span class="sxs-lookup"><span data-stu-id="e515a-134">Reverse and make adjustments</span></span>

<span data-ttu-id="e515a-135">Reverta tudo o que foi lançado para a carga (por exemplo, a guia de remessa, confirmação de remessa e trabalho), faça ajustes a ordens de venda, libere novamente o pedido para depósito e conclua o procedimento de remessa.</span><span class="sxs-lookup"><span data-stu-id="e515a-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="e515a-136">Use o procedimento a seguir para cancelar uma guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="e515a-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="e515a-137">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="e515a-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e515a-138">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Cancelar guias de remessa**.</span><span class="sxs-lookup"><span data-stu-id="e515a-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="e515a-139">Use o procedimento a seguir para reverter a confirmação de remessa.</span><span class="sxs-lookup"><span data-stu-id="e515a-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="e515a-140">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="e515a-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e515a-141">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="e515a-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="e515a-142">Use o procedimento a seguir para reverter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e515a-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="e515a-143">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="e515a-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="e515a-144">No Painel de Ação, na guia  **Cargas**, no grupo  **Trabalho**, selecione  **Reverter trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e515a-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
