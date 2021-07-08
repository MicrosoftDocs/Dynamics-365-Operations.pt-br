---
title: O arredondamento decimal da quantidade de atualização física está incorreto
description: Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que não corresponde à precisão decimal definida na unidade.
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
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248767"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="7ea8b-103">O arredondamento decimal da quantidade de atualização física está incorreto</span><span class="sxs-lookup"><span data-stu-id="7ea8b-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="7ea8b-104">Código de erro: SYS19589</span><span class="sxs-lookup"><span data-stu-id="7ea8b-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="7ea8b-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="7ea8b-105">Symptoms</span></span>

<span data-ttu-id="7ea8b-106">Quando você gera uma guia de remessa, a carga de saída contém uma quantidade que não corresponde à precisão decimal definida na unidade.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="7ea8b-107">Ao tentar gerar uma guia de remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="7ea8b-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="7ea8b-108">O arredondamento decimal da quantidade de atualização física na unidade %1 está incorreto.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="7ea8b-109">Portanto, não é possível gerar a guia de remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="7ea8b-110">Causa</span><span class="sxs-lookup"><span data-stu-id="7ea8b-110">Cause</span></span>

<span data-ttu-id="7ea8b-111">O sistema avalia se o arredondamento decimal da quantidade de transporte corresponde à precisão decimal definida para a unidade de transporte.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="7ea8b-112">Quando o sistema arredondar a quantidade de envio para o número especificado de casas decimais, se descobrir que a quantidade arredondada de envio não corresponde à quantidade de envio real, você não poderá gerar o deslizamento de embalagem.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="7ea8b-113">Por exemplo, esse problema pode ocorrer se a quantidade de vendas for de 1,75 kg (kg), mas a precisão decimal estiver definida como *1*.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="7ea8b-114">Resolução</span><span class="sxs-lookup"><span data-stu-id="7ea8b-114">Resolution</span></span>

<span data-ttu-id="7ea8b-115">A carga ou a remessa estão em um estado no qual a geração da guia de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="7ea8b-116">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="7ea8b-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="7ea8b-117">Revise suas linhas de carga e faça ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="7ea8b-118">Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="7ea8b-119">Revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais</span><span class="sxs-lookup"><span data-stu-id="7ea8b-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="7ea8b-120">Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a quantidade possa ser convertida de forma limpa sem problemas de arredondamento e de números decimais.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="7ea8b-121">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="7ea8b-122">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="7ea8b-123">No Painel de Ações, na guia  **Enviar e receber**, no grupo  **Reverter**, selecione  **Confirmação de envio reverso**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="7ea8b-124">Na guia  **Linhas de carga**, selecione a linha de carga para o item que causa um problema.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="7ea8b-125">Selecione **Reduzir a quantidade escolhida** para ajustar a quantidade escolhida.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="7ea8b-126">Na guia  **Detalhes da linha**, selecione **Ordem**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="7ea8b-127">Defina o campo **Quantidade** como a quantidade separada (ou seja, o valor do campo **Quantidade de trabalho criado**), de forma que a guia de remessa possa ser gerada.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="7ea8b-128">Revise suas linhas de carga e faça ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade</span><span class="sxs-lookup"><span data-stu-id="7ea8b-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="7ea8b-129">Use o seguinte procedimento para revisar suas linhas de carga e fazer ajustes para garantir que a unidade e a quantidade estejam alinhadas com a precisão decimal da unidade.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="7ea8b-130">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="7ea8b-131">Selecione a carga para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="7ea8b-132">Na FastTab **Linhas de carga**, selecione a linha de carga para o item que causa um problema.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="7ea8b-133">Anote o valor dos campos **Quantidade** e **Unidade**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="7ea8b-134">Vá para **Administração de organização \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="7ea8b-135">Selecione a unidade para a qual a guia de remessa não pode ser gerada.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="7ea8b-136">Ajuste o valor do campo **Precisão decimal** conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="7ea8b-136">Adjust the value of the **Decimal precision** field as required.</span></span>
