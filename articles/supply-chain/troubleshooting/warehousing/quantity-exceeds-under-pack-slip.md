---
title: A quantidade excede a porcentagem de entrega insuficiente durante a geração da guia de remessa
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega insuficiente.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249056"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="fd03b-103">A quantidade excede a porcentagem de entrega insuficiente durante a geração da guia de remessa</span><span class="sxs-lookup"><span data-stu-id="fd03b-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="fd03b-104">Código de erro: SYS24921</span><span class="sxs-lookup"><span data-stu-id="fd03b-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="fd03b-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="fd03b-105">Symptoms</span></span>

<span data-ttu-id="fd03b-106">Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="fd03b-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="fd03b-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="fd03b-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="fd03b-108">A entrega insuficiente da linha é de %1%, mas o percentual permitido para entrega insuficiente é de apenas %2%.</span><span class="sxs-lookup"><span data-stu-id="fd03b-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="fd03b-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="fd03b-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="fd03b-110">Causa</span><span class="sxs-lookup"><span data-stu-id="fd03b-110">Cause</span></span>

<span data-ttu-id="fd03b-111">A quantidade escolhida para a carga ou remessa é menor do que a quantidade da ordem e não está dentro do intervalo da porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="fd03b-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="fd03b-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="fd03b-112">Resolution</span></span>

<span data-ttu-id="fd03b-113">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="fd03b-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="fd03b-114">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="fd03b-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="fd03b-115">Ajuste a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="fd03b-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="fd03b-116">Inverta e faça ajustes.</span><span class="sxs-lookup"><span data-stu-id="fd03b-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="fd03b-117">Ajustar a porcentagem de entrega insuficiente</span><span class="sxs-lookup"><span data-stu-id="fd03b-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="fd03b-118">Use o seguinte procedimento para ajustar a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="fd03b-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="fd03b-119">Vá para **Contas a receber \> Ordens \> Todas as ordens**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="fd03b-120">Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.</span><span class="sxs-lookup"><span data-stu-id="fd03b-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="fd03b-121">Na guia  **Linhas da ordem de venda**, selecione a linha da ordem de venda do item que excede a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="fd03b-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="fd03b-122">Na guia  **Detalhes da linha**, selecione **Entrega**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="fd03b-123">Defina o campo **Entrega insuficiente** como uma porcentagem maior que acomode a quantidade que foi separada em relação à quantidade de carga, de forma que a guia de remessa possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="fd03b-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="fd03b-124">Inverter e fazer ajustes</span><span class="sxs-lookup"><span data-stu-id="fd03b-124">Reverse and make adjustments</span></span>

<span data-ttu-id="fd03b-125">Reverta tudo o que foi lançado para a carga (por exemplo, a guia de remessa, confirmação de remessa e trabalho), faça ajustes a ordens de venda, libere novamente o pedido para depósito e conclua o procedimento de remessa.</span><span class="sxs-lookup"><span data-stu-id="fd03b-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="fd03b-126">Use o procedimento a seguir para cancelar uma guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="fd03b-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="fd03b-127">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="fd03b-128">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Cancelar guias de remessa**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="fd03b-129">Use o procedimento a seguir para reverter a confirmação de remessa.</span><span class="sxs-lookup"><span data-stu-id="fd03b-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="fd03b-130">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="fd03b-131">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="fd03b-132">Use o procedimento a seguir para reverter o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fd03b-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="fd03b-133">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="fd03b-134">No Painel de Ação, na guia  **Cargas**, no grupo  **Trabalho**, selecione  **Reverter trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd03b-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
