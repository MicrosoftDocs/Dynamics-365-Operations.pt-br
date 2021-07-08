---
title: A quantidade que você está tentando atualizar excede a quantidade recebida/entregue.
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a quantidade que foi separada e reservada para a ordem de venda.
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
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249061"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="957a5-103">A quantidade que você está tentando atualizar excede a quantidade recebida/entregue</span><span class="sxs-lookup"><span data-stu-id="957a5-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="957a5-104">Código de erro: SYS7676</span><span class="sxs-lookup"><span data-stu-id="957a5-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="957a5-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="957a5-105">Symptoms</span></span>

<span data-ttu-id="957a5-106">Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que excede a quantidade que foi separada e reservada para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="957a5-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="957a5-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="957a5-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="957a5-108">A quantidade que você está tentando atualizar excede a quantidade recebida/entregue.</span><span class="sxs-lookup"><span data-stu-id="957a5-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="957a5-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="957a5-110">Causa</span><span class="sxs-lookup"><span data-stu-id="957a5-110">Cause</span></span>

<span data-ttu-id="957a5-111">A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="957a5-112">Por exemplo, esse problema pode ocorrer se a quantidade de linha de carga, a quantidade de trabalho criada ou a quantidade separada não for exata.</span><span class="sxs-lookup"><span data-stu-id="957a5-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="957a5-113">Resolução</span><span class="sxs-lookup"><span data-stu-id="957a5-113">Resolution</span></span>

<span data-ttu-id="957a5-114">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="957a5-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="957a5-115">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="957a5-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="957a5-116">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="957a5-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="957a5-117">Ajuste a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="957a5-118">Inverta todos os registros de separação e refaça a separação.</span><span class="sxs-lookup"><span data-stu-id="957a5-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="957a5-119">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem</span><span class="sxs-lookup"><span data-stu-id="957a5-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="957a5-120">Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="957a5-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="957a5-121">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="957a5-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="957a5-122">Selecione a carga para a qual a remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="957a5-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="957a5-123">Na FastTab **Linhas de carga**, selecione a linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="957a5-124">Anote o valor do campo **Quantidade de trabalho criado**.</span><span class="sxs-lookup"><span data-stu-id="957a5-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="957a5-125">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="957a5-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="957a5-126">Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="957a5-127">Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="957a5-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="957a5-128">Ajustar a quantidade da linha de carga</span><span class="sxs-lookup"><span data-stu-id="957a5-128">Adjust the load line quantity</span></span>

<span data-ttu-id="957a5-129">Use o seguinte procedimento para ajustar a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="957a5-130">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="957a5-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="957a5-131">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="957a5-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="957a5-132">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="957a5-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="957a5-133">Na guia  **Linhas de carga**, selecione a linha de carga para o item que causa um problema.</span><span class="sxs-lookup"><span data-stu-id="957a5-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="957a5-134">Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.</span><span class="sxs-lookup"><span data-stu-id="957a5-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="957a5-135">Defina o campo **Reduzir linha de carga** para refletir os ajustes na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="957a5-136">Inverta todos os registros de separação e refaça a separação</span><span class="sxs-lookup"><span data-stu-id="957a5-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="957a5-137">Se alguém tiver usado o registro de separação para fechar uma linha de carga sem trabalho, poderá ocorrer uma discrepância entre a quantidade de linha de carga e a quantidade separada.</span><span class="sxs-lookup"><span data-stu-id="957a5-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="957a5-138">Neste caso, o registro manual de escolha deve ser invertido, e a escolha deve ser concluída usando o aplicativo móvel Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="957a5-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="957a5-139">Use o procedimento a seguir para reverter o registro de escolha.</span><span class="sxs-lookup"><span data-stu-id="957a5-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="957a5-140">Vá para **Contas a receber \> Ordens \> Todas as ordens**.</span><span class="sxs-lookup"><span data-stu-id="957a5-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="957a5-141">Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.</span><span class="sxs-lookup"><span data-stu-id="957a5-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="957a5-142">Na guia  **Linhas de ordem de venda**, selecione a linha de ordem de venda para a qual o registro de escolha foi feito.</span><span class="sxs-lookup"><span data-stu-id="957a5-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="957a5-143">Selecione **Atualizar linha \> Escolher** para cancelar a seleção dos itens.</span><span class="sxs-lookup"><span data-stu-id="957a5-143">Select **Update line \> Pick** to unpick the items.</span></span>
