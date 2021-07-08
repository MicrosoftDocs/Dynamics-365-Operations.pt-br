---
title: A quantidade escolhida não é suficiente durante a geração de guias de remessa
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade escolhida que não corresponde à quantidade de trabalho criada na linha de carga.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249060"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="48b81-103">A quantidade escolhida não é suficiente durante a geração de guias de remessa</span><span class="sxs-lookup"><span data-stu-id="48b81-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="48b81-104">Código de erro: SYS54073</span><span class="sxs-lookup"><span data-stu-id="48b81-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="48b81-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="48b81-105">Symptoms</span></span>

<span data-ttu-id="48b81-106">Quando você gera uma guia de remessa, a carga de saída contém uma quantidade escolhida que não corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="48b81-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="48b81-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="48b81-108">Foram separados %1, o que não é suficiente para atualizar %2, quando, subsequentemente, o pendente deve ser %3.</span><span class="sxs-lookup"><span data-stu-id="48b81-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="48b81-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="48b81-110">Causa</span><span class="sxs-lookup"><span data-stu-id="48b81-110">Cause</span></span>

<span data-ttu-id="48b81-111">A guia de remessa não pode ser gerada no estado atual porque pode existir uma das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="48b81-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="48b81-112">O trabalho relacionado ainda não foi separado e movido para o local de remessa final.</span><span class="sxs-lookup"><span data-stu-id="48b81-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="48b81-113">A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="48b81-114">A quantidade de linha da carga, a quantidade criada de trabalho e a quantidade escolhida não correspondem.</span><span class="sxs-lookup"><span data-stu-id="48b81-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="48b81-115">Resolução</span><span class="sxs-lookup"><span data-stu-id="48b81-115">Resolution</span></span>

<span data-ttu-id="48b81-116">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="48b81-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="48b81-117">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="48b81-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="48b81-118">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="48b81-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="48b81-119">Ajuste a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="48b81-120">Inverta todos os registros de separação e refaça a separação.</span><span class="sxs-lookup"><span data-stu-id="48b81-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="48b81-121">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem</span><span class="sxs-lookup"><span data-stu-id="48b81-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="48b81-122">Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="48b81-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="48b81-123">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="48b81-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="48b81-124">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="48b81-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="48b81-125">Na FastTab **Linhas de carga**, selecione a linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="48b81-126">Anote o valor do campo **Quantidade de trabalho criado**.</span><span class="sxs-lookup"><span data-stu-id="48b81-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="48b81-127">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="48b81-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="48b81-128">Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="48b81-129">Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="48b81-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="48b81-130">Ajustar a quantidade da linha de carga</span><span class="sxs-lookup"><span data-stu-id="48b81-130">Adjust the load line quantity</span></span>

<span data-ttu-id="48b81-131">Use o seguinte procedimento para ajustar a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="48b81-132">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="48b81-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="48b81-133">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="48b81-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="48b81-134">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="48b81-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="48b81-135">Na guia  **Linhas de carga**, selecione a linha de carga para o item que causa um problema.</span><span class="sxs-lookup"><span data-stu-id="48b81-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="48b81-136">Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.</span><span class="sxs-lookup"><span data-stu-id="48b81-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="48b81-137">Defina o campo **Reduzir linha de carga** para refletir os ajustes na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="48b81-138">Inverta todos os registros de separação e refaça a separação</span><span class="sxs-lookup"><span data-stu-id="48b81-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="48b81-139">O problema pode ocorrer porque alguém usou o registro de escolha para fechar uma linha de carga sem trabalho.</span><span class="sxs-lookup"><span data-stu-id="48b81-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="48b81-140">Neste caso, o registro manual de escolha deve ser invertido, e a escolha deve ser concluída usando o aplicativo móvel Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="48b81-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="48b81-141">Use o procedimento a seguir para reverter o registro de escolha.</span><span class="sxs-lookup"><span data-stu-id="48b81-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="48b81-142">Vá para **Contas a receber \> Ordens \> Todas as ordens**.</span><span class="sxs-lookup"><span data-stu-id="48b81-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="48b81-143">Selecione a ordem de venda para a qual você não pode postar uma guia de remessa para a carga.</span><span class="sxs-lookup"><span data-stu-id="48b81-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="48b81-144">Na guia  **Linhas de ordem de venda**, selecione a linha de ordem de venda para a qual o registro de escolha foi feito.</span><span class="sxs-lookup"><span data-stu-id="48b81-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="48b81-145">Selecione **Atualizar linha \> Escolher** para cancelar a seleção dos itens.</span><span class="sxs-lookup"><span data-stu-id="48b81-145">Select **Update line \> Pick** to unpick the items.</span></span>
