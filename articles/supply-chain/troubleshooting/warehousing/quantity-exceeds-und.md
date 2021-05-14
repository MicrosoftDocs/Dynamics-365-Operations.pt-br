---
title: Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente
description: Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5339b9d800f7454e2a00c230a8d5deca3979c074
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938418"
---
# <a name="you-cant-confirm-a-shipment-because-the-quantity-exceeds-the-underdelivery-percentage"></a><span data-ttu-id="72b33-103">Não é possível confirmar uma remessa porque a quantidade excede a porcentagem de entrega insuficiente</span><span class="sxs-lookup"><span data-stu-id="72b33-103">You can't confirm a shipment because the quantity exceeds the underdelivery percentage</span></span>

<span data-ttu-id="72b33-104">Código de erro: WAX1687</span><span class="sxs-lookup"><span data-stu-id="72b33-104">Error code: WAX1687</span></span>

## <a name="symptoms"></a><span data-ttu-id="72b33-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="72b33-105">Symptoms</span></span>

<span data-ttu-id="72b33-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="72b33-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="72b33-107">Não foi possível confirmar a remessa da carga %1 porque a quantidade do item %2 excede a porcentagem definida de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="72b33-107">The shipment for load %1 could not be confirmed because the quantity for item %2 exceeds the percentage that is defined for underdelivery.</span></span>

<span data-ttu-id="72b33-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="72b33-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="72b33-109">Causa</span><span class="sxs-lookup"><span data-stu-id="72b33-109">Cause</span></span>

<span data-ttu-id="72b33-110">A quantidade da carga ou remessa foi apenas parcialmente separada.</span><span class="sxs-lookup"><span data-stu-id="72b33-110">The quantity of the load or shipment has been only partially picked.</span></span> <span data-ttu-id="72b33-111">A quantidade é atualmente inferior à quantidade separada por uma porcentagem que está fora da porcentagem de entrega insuficiente permitida.</span><span class="sxs-lookup"><span data-stu-id="72b33-111">The quantity is currently less than the picked quantity by a percentage that is outside the allowed underdelivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="72b33-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="72b33-112">Resolution</span></span>

<span data-ttu-id="72b33-113">Para corrigir esse problema, execute uma das seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="72b33-113">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="72b33-114">Defina a quantidade da linha de carga.</span><span class="sxs-lookup"><span data-stu-id="72b33-114">Set the load line quantity.</span></span>
- <span data-ttu-id="72b33-115">Defina a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="72b33-115">Set the underdelivery percentage.</span></span>

### <a name="set-the-load-line-quantity"></a><span data-ttu-id="72b33-116">Definir a quantidade da linha de carga</span><span class="sxs-lookup"><span data-stu-id="72b33-116">Set the load line quantity</span></span>

<span data-ttu-id="72b33-117">Para definir a quantidade da linha de carga, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72b33-117">To set the load line quantity, follow these steps.</span></span>

1. <span data-ttu-id="72b33-118">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="72b33-118">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="72b33-119">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="72b33-119">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="72b33-120">Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="72b33-120">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="72b33-121">Na FastTab **Detalhes da linha**, selecione **Ordem**.</span><span class="sxs-lookup"><span data-stu-id="72b33-121">On the **Line details** FastTab, select **Order**.</span></span>
1. <span data-ttu-id="72b33-122">No campo **Quantidade**, defina o valor como a quantidade separada (ou seja, como o valor **Quantidade de trabalho criado**), de forma que a confirmação da remessa possa ocorrer.</span><span class="sxs-lookup"><span data-stu-id="72b33-122">In the **Quantity** field, set the value to the picked quantity (that is, to the **Work created quantity** value), so that shipment confirmation can occur.</span></span>

### <a name="set-the-underdelivery-percentage"></a><span data-ttu-id="72b33-123">Definir a porcentagem de entrega insuficiente</span><span class="sxs-lookup"><span data-stu-id="72b33-123">Set the underdelivery percentage</span></span>

<span data-ttu-id="72b33-124">Para definir a porcentagem de entrega insuficiente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="72b33-124">To set the underdelivery percentage, follow these steps.</span></span>

1. <span data-ttu-id="72b33-125">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="72b33-125">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="72b33-126">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="72b33-126">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="72b33-127">Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="72b33-127">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="72b33-128">Na FastTab **Detalhes da linha**, selecione **Geral**.</span><span class="sxs-lookup"><span data-stu-id="72b33-128">On the **Line details** FastTab, select **General**.</span></span>
1. <span data-ttu-id="72b33-129">No campo **Entrega insuficiente**, defina o valor como uma porcentagem maior que acomode a quantidade separada em relação à quantidade de carga, de forma que a confirmação da remessa possa ocorrer.</span><span class="sxs-lookup"><span data-stu-id="72b33-129">In the **Underdelivery** field, set the value to a larger percentage that accommodates the quantity that has been picked against the load quantity, so that shipment confirmation can occur.</span></span>
