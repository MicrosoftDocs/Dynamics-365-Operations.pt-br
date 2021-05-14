---
title: Não é possível confirmar uma remessa porque os itens não foram separados
description: Não é possível confirmar uma remessa porque os itens não foram separados
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
ms.openlocfilehash: 23a517e7769dc86ebec30e4f17c62172a6ad8801
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938420"
---
# <a name="you-cant-confirm-a-shipment-because-items-havent-been-picked"></a><span data-ttu-id="f13b4-103">Não é possível confirmar uma remessa porque os itens não foram separados</span><span class="sxs-lookup"><span data-stu-id="f13b4-103">You can't confirm a shipment because items haven't been picked</span></span>

<span data-ttu-id="f13b4-104">Código de erro: LoadNotPickedAndMovedToFinalShippingLocation</span><span class="sxs-lookup"><span data-stu-id="f13b4-104">Error code: LoadNotPickedAndMovedToFinalShippingLocation</span></span>

## <a name="symptoms"></a><span data-ttu-id="f13b4-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="f13b4-105">Symptoms</span></span>

<span data-ttu-id="f13b4-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="f13b4-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="f13b4-107">Alguns dos itens necessários para carregar %1 ainda não foram separados e movidos para a localização de remessa final.</span><span class="sxs-lookup"><span data-stu-id="f13b4-107">Some of the items that are needed for load %1 have not yet been picked and moved to the final shipping location.</span></span>

<span data-ttu-id="f13b4-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="f13b4-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="f13b4-109">Causa</span><span class="sxs-lookup"><span data-stu-id="f13b4-109">Cause</span></span>

<span data-ttu-id="f13b4-110">A carga ou a remessa não pode ser confirmada no estado atual porque pode existir uma das seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="f13b4-110">The load or shipment can't be confirmed in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="f13b4-111">O trabalho relacionado ainda não foi separado e movido para o local de remessa final.</span><span class="sxs-lookup"><span data-stu-id="f13b4-111">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="f13b4-112">A quantidade de trabalho separada não corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="f13b4-112">The picked work quantity doesn't match the created work quantity on the load line.</span></span>

## <a name="resolution"></a><span data-ttu-id="f13b4-113">Resolução</span><span class="sxs-lookup"><span data-stu-id="f13b4-113">Resolution</span></span>

<span data-ttu-id="f13b4-114">Verifique as ordens de venda relacionadas ou as ordens de transferência para a carga ou remessa.</span><span class="sxs-lookup"><span data-stu-id="f13b4-114">Check the related sales orders or transfer orders for the load or shipment.</span></span> <span data-ttu-id="f13b4-115">Verifique se todos os trabalhos relacionados foram concluídos no local de remessa final e se as quantidades coincidem.</span><span class="sxs-lookup"><span data-stu-id="f13b4-115">Make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="f13b4-116">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="f13b4-116">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f13b4-117">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="f13b4-117">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="f13b4-118">Na FastTab **Linhas de carga**, selecione a linha de carga.</span><span class="sxs-lookup"><span data-stu-id="f13b4-118">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="f13b4-119">Anote o valor do campo **Quantidade de trabalho criado**.</span><span class="sxs-lookup"><span data-stu-id="f13b4-119">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="f13b4-120">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f13b4-120">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="f13b4-121">Verifique se o trabalho foi concluído no local de remessa final e se a quantidade de trabalho separada corresponde à quantidade de trabalho criada na linha de carga.</span><span class="sxs-lookup"><span data-stu-id="f13b4-121">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="f13b4-122">Repita este procedimento para todas as linhas de carga para garantir que todos os critérios sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="f13b4-122">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>
