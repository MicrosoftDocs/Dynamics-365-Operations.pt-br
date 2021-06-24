---
title: Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente
description: Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm, WHSContainerCloseDiag_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: beef0909d41e69f3e7bcc1021527be35b7e6fd44
ms.sourcegitcommit: c2c6d687a89bc1534c029109315c23e92865b63b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2021
ms.locfileid: "6123834"
---
# <a name="you-cant-confirm-a-shipment-because-of-incomplete-or-missing-work"></a><span data-ttu-id="2856b-103">Não é possível confirmar uma remessa devido a trabalho incompleto ou ausente</span><span class="sxs-lookup"><span data-stu-id="2856b-103">You can't confirm a shipment because of incomplete or missing work</span></span>

<span data-ttu-id="2856b-104">Código de erro: WAX515</span><span class="sxs-lookup"><span data-stu-id="2856b-104">Error code: WAX515</span></span>

## <a name="symptoms"></a><span data-ttu-id="2856b-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="2856b-105">Symptoms</span></span>

<span data-ttu-id="2856b-106">Ao tentar confirmar uma remessa, o sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="2856b-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="2856b-107">Não foi possível confirmar a remessa da carga %1 porque todos os trabalhos da carga devem ser concluídos.</span><span class="sxs-lookup"><span data-stu-id="2856b-107">The shipment for load %1 could not be confirmed because all work for the load must be complete.</span></span>

<span data-ttu-id="2856b-108">Portanto, não é possível confirmar a remessa da carga.</span><span class="sxs-lookup"><span data-stu-id="2856b-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="2856b-109">Causa</span><span class="sxs-lookup"><span data-stu-id="2856b-109">Cause</span></span>

<span data-ttu-id="2856b-110">A carga ou a remessa estão em um estado no qual a confirmação de remessa falha.</span><span class="sxs-lookup"><span data-stu-id="2856b-110">The load or shipment is currently in a state where shipment confirmation fails.</span></span> <span data-ttu-id="2856b-111">Para poder confirmar a remessa, deve existir pelo menos um trabalho para a carga e todo esse trabalho deve ter o status *Fechado* ou *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="2856b-111">Before you can confirm the shipment, at least some work must exist for the load, and all that work must have a status of *Closed* or *Canceled*.</span></span>

## <a name="resolution"></a><span data-ttu-id="2856b-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="2856b-112">Resolution</span></span>

<span data-ttu-id="2856b-113">Verifique as ordens de venda relacionadas ou as ordens de transferência para a carga ou remessa e verifique se todos os trabalhos relacionados foram concluídos ou cancelados.</span><span class="sxs-lookup"><span data-stu-id="2856b-113">Check the related sales orders or transfer orders for the load or shipment, and make sure that all the related work has been completed or canceled.</span></span>

<span data-ttu-id="2856b-114">Você pode trabalhar com remessas e cargas em várias páginas.</span><span class="sxs-lookup"><span data-stu-id="2856b-114">You can work with shipments and loads on several pages.</span></span> <span data-ttu-id="2856b-115">As subseções a seguir fornecem alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="2856b-115">The following subsections provide a few examples.</span></span>

### <a name="all-loads-page"></a><span data-ttu-id="2856b-116">Página todas as cargas</span><span class="sxs-lookup"><span data-stu-id="2856b-116">All loads page</span></span>

1. <span data-ttu-id="2856b-117">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="2856b-117">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="2856b-118">Selecione a carga para a qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="2856b-118">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="2856b-119">No Painel de Ações, na guia **Cargas**, no grupo **Informações relacionadas**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2856b-119">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="2856b-120">Inspecione o status de cada ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2856b-120">Inspect the status of each work ID.</span></span> <span data-ttu-id="2856b-121">Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="2856b-121">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="2856b-122">Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.</span><span class="sxs-lookup"><span data-stu-id="2856b-122">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-shipments-page"></a><span data-ttu-id="2856b-123">Página Todas as remessas</span><span class="sxs-lookup"><span data-stu-id="2856b-123">All shipments page</span></span>

1. <span data-ttu-id="2856b-124">Acesse **Gerenciamento de depósito \> Remessas \> Todas as remessas**.</span><span class="sxs-lookup"><span data-stu-id="2856b-124">Go to **Warehouse management \> Shipments\> All shipments**.</span></span>
1. <span data-ttu-id="2856b-125">Selecione a remessa que não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="2856b-125">Select the shipment that can't be confirmed.</span></span>
1. <span data-ttu-id="2856b-126">No Painel de Ações, na guia **Remessas**, no grupo **Trabalho**, selecione **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2856b-126">On the Action Pane, on the **Shipments** tab, in the **Work** group, select **Work details**.</span></span>
1. <span data-ttu-id="2856b-127">Inspecione o status de cada ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2856b-127">Inspect the status of each work ID.</span></span> <span data-ttu-id="2856b-128">Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="2856b-128">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="2856b-129">Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.</span><span class="sxs-lookup"><span data-stu-id="2856b-129">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>

### <a name="all-work-page"></a><span data-ttu-id="2856b-130">Página Todos os trabalhos</span><span class="sxs-lookup"><span data-stu-id="2856b-130">All work page</span></span>

1. <span data-ttu-id="2856b-131">Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos**.</span><span class="sxs-lookup"><span data-stu-id="2856b-131">Go to **Warehouse management \> Work\> All work**.</span></span>
1. <span data-ttu-id="2856b-132">Selecione o trabalho para o número da ordem para o qual a remessa não pode ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="2856b-132">Select the work for the order number that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="2856b-133">No painel de Ações, na guia **Remessa** , no grupo **Remessa** , selecione **Confirmar remessa**.</span><span class="sxs-lookup"><span data-stu-id="2856b-133">On the Action Pane, on the **Shipment** tab, in the **Shipment** group, select **Confirm shipment**.</span></span>
1. <span data-ttu-id="2856b-134">Inspecione o status de cada ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2856b-134">Inspect the status of each work ID.</span></span> <span data-ttu-id="2856b-135">Acompanhamento de cada ID de trabalho sem status *Fechado* ou *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="2856b-135">Follow up on each work ID that doesn't have a status of *Closed* or *Canceled*.</span></span>
1. <span data-ttu-id="2856b-136">Quando cada ID de trabalho tiver um status *Fechado* ou *Cancelado*, tente confirmar novamente a remessa.</span><span class="sxs-lookup"><span data-stu-id="2856b-136">When every work ID has a status of *Closed* or *Canceled*, try again to confirm the shipment.</span></span>
