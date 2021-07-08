---
title: A quantidade física remanescente na unidade não pode ser zero
description: Quando você gera um guia de remessa, os dados fornecidos a ela têm uma quantidade de estoque não zero, mas uma quantidade de venda zero.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248766"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="c7af7-103">A quantidade física remanescente na unidade não pode ser zero</span><span class="sxs-lookup"><span data-stu-id="c7af7-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="c7af7-104">Código de erro: SYS19591</span><span class="sxs-lookup"><span data-stu-id="c7af7-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="c7af7-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="c7af7-105">Symptoms</span></span>

<span data-ttu-id="c7af7-106">Quando você gera um guia de remessa, os dados fornecidos a ela têm uma quantidade de estoque não zero, mas uma quantidade de venda zero.</span><span class="sxs-lookup"><span data-stu-id="c7af7-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="c7af7-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="c7af7-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="c7af7-108">A quantidade física restante na unidade %1 deve ser diferente de zero.</span><span class="sxs-lookup"><span data-stu-id="c7af7-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="c7af7-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="c7af7-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="c7af7-110">Causa</span><span class="sxs-lookup"><span data-stu-id="c7af7-110">Cause</span></span>

<span data-ttu-id="c7af7-111">O sistema avalia a quantidade física remanescente na unidade de estoque e a quantidade física restante na unidade de transporte.</span><span class="sxs-lookup"><span data-stu-id="c7af7-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="c7af7-112">Se o sistema descobrir que a quantidade física restante na unidade de transporte é 0 (zero), mas a quantidade física restante na unidade de estoque não é 0, você não poderá gerar a guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="c7af7-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="c7af7-113">Por exemplo, esse problema pode ocorrer se a unidade de vendas e a unidade de estoque do item forem diferentes, e a conversão entre as unidades não for precisa.</span><span class="sxs-lookup"><span data-stu-id="c7af7-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="c7af7-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="c7af7-114">Resolution</span></span>

<span data-ttu-id="c7af7-115">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="c7af7-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="c7af7-116">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="c7af7-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="c7af7-117">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="c7af7-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="c7af7-118">Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="c7af7-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="c7af7-119">Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.</span><span class="sxs-lookup"><span data-stu-id="c7af7-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="c7af7-120">Certifique-se de que a unidade de inventário da medida é menor do que a unidade de medida da venda.</span><span class="sxs-lookup"><span data-stu-id="c7af7-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="c7af7-121">Revise suas linhas de carga e verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem</span><span class="sxs-lookup"><span data-stu-id="c7af7-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="c7af7-122">Use o seguinte procedimento para revisar suas linhas de carga e verificar se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="c7af7-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="c7af7-123">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c7af7-124">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="c7af7-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="c7af7-125">Na FastTab **Linhas de carga**, selecione a linha de carga.</span><span class="sxs-lookup"><span data-stu-id="c7af7-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="c7af7-126">Anote o valor do campo **Quantidade de trabalho criado**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="c7af7-127">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="c7af7-128">Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="c7af7-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="c7af7-129">Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="c7af7-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="c7af7-130">Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento</span><span class="sxs-lookup"><span data-stu-id="c7af7-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="c7af7-131">Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="c7af7-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="c7af7-132">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c7af7-133">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="c7af7-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="c7af7-134">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="c7af7-135">Na guia  **Linhas de carga**, selecione a linha de carga do item que excede a entrega excedente.</span><span class="sxs-lookup"><span data-stu-id="c7af7-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="c7af7-136">Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.</span><span class="sxs-lookup"><span data-stu-id="c7af7-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="c7af7-137">Na guia  **Detalhes da linha**, selecione **Ordem**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="c7af7-138">Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="c7af7-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="c7af7-139">Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade</span><span class="sxs-lookup"><span data-stu-id="c7af7-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="c7af7-140">Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.</span><span class="sxs-lookup"><span data-stu-id="c7af7-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="c7af7-141">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="c7af7-142">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="c7af7-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="c7af7-143">Na FastTab **Linhas de carga**, selecione a linha de carga para o item que causa um problema.</span><span class="sxs-lookup"><span data-stu-id="c7af7-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="c7af7-144">Anote o valor dos campos **Quantidade** e **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="c7af7-145">Vá para **Administração de organização \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="c7af7-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="c7af7-146">Selecione a unidade para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="c7af7-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="c7af7-147">Ajuste o valor do campo **Precisão decimal** conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c7af7-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="c7af7-148">Certifique-se de que a unidade de medida do estoque é menor do que a unidade de medida da venda</span><span class="sxs-lookup"><span data-stu-id="c7af7-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="c7af7-149">Certifique-se de que a unidade de inventário da medida é menor do que a unidade de medida da venda.</span><span class="sxs-lookup"><span data-stu-id="c7af7-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="c7af7-150">Considere reconfigurar a unidade de medida para o item conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="c7af7-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
