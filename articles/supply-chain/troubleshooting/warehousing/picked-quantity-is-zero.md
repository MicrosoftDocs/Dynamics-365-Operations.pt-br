---
title: Não é possível confirmar uma remessa porque há quantidade zero
description: Não é possível confirmar uma remessa porque há quantidade zero
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
ms.openlocfilehash: 7a06f0651db741a867e1e9fe7dbab841a928c22b
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938419"
---
# <a name="you-cant-confirm-a-shipment-because-there-is-zero-quantity"></a><span data-ttu-id="16654-103">Não é possível confirmar uma remessa porque há quantidade zero</span><span class="sxs-lookup"><span data-stu-id="16654-103">You can't confirm a shipment because there is zero quantity</span></span>

<span data-ttu-id="16654-104">Código de erro: LoadLineWarningUpdatedToZero</span><span class="sxs-lookup"><span data-stu-id="16654-104">Error code: LoadLineWarningUpdatedToZero</span></span>

## <a name="symptoms"></a><span data-ttu-id="16654-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="16654-105">Symptoms</span></span>

<span data-ttu-id="16654-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="16654-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="16654-107">A linha de carga para o item %1 e a remessa %2 foi atualizado para ter quantidade zero devido a uma configuração de entrega insuficiente, o que permite não enviar nenhuma quantidade para este item.</span><span class="sxs-lookup"><span data-stu-id="16654-107">Load line for item %1 and shipment %2 has been updated to have zero quantity due to underdelivery setup allowing not to ship any quantities for this item.</span></span>

<span data-ttu-id="16654-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="16654-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="16654-109">Causa</span><span class="sxs-lookup"><span data-stu-id="16654-109">Cause</span></span>

<span data-ttu-id="16654-110">O sistema avalia se a quantidade separada está dentro dos limites esperados, com base na quantidade separada, na quantidade da linha de carga e na porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="16654-110">The system evaluates whether the picked quantity is within the expected limits, based on the picked quantity, load line quantity, and underdelivery percentage.</span></span> <span data-ttu-id="16654-111">Se o sistema descobrir que a quantidade separada na linha de carga é 0 (zero), você não poderá confirmar a remessa.</span><span class="sxs-lookup"><span data-stu-id="16654-111">If the system finds that the picked quantity on the load line is 0 (zero), you can't confirm the shipment.</span></span> <span data-ttu-id="16654-112">Por exemplo, esse problema poderá ocorrer se o trabalho tiver sido cancelado, e a porcentagem de entrega insuficiente na linha de carga for 100%.</span><span class="sxs-lookup"><span data-stu-id="16654-112">For example, this issue might occur if work has been canceled, and the underdelivery percentage on the load line is 100 percent.</span></span>

## <a name="resolution"></a><span data-ttu-id="16654-113">Resolução</span><span class="sxs-lookup"><span data-stu-id="16654-113">Resolution</span></span>

<span data-ttu-id="16654-114">Verifique as linhas de carga para garantir que a porcentagem de entrega insuficiente e as quantidades estejam alinhadas com o trabalho separado.</span><span class="sxs-lookup"><span data-stu-id="16654-114">Check your load lines to make sure that the underdelivery percentage and quantities are aligned with the picked work.</span></span>

1. <span data-ttu-id="16654-115">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="16654-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="16654-116">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="16654-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="16654-117">Na FastTab **Linhas de carga**, selecione a linha de carga do item que excede a porcentagem de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="16654-117">On the **Load lines** FastTab, select the load line for the item that exceeds the underdelivery percentage.</span></span>
1. <span data-ttu-id="16654-118">Ajuste o valor do campo **Entrega insuficiente** ou o campo **Quantidade**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="16654-118">Adjust the value of the **Underdelivery** field or the **Quantity** field as required.</span></span>

> [!TIP]
> <span data-ttu-id="16654-119">Se o problema ainda não for corrigido, talvez seja necessário concluir mais trabalho de separação para as ordens de venda ou ordens de transferência relacionadas até que a quantidade disponível esteja alinhada com a carga ou a remessa.</span><span class="sxs-lookup"><span data-stu-id="16654-119">If the issue still isn't fixed, you might have to complete more picking work for the related sales orders or transfer orders until the available quantity is aligned with the load or shipment.</span></span>
