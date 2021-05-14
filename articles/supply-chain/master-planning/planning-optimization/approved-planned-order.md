---
title: Exibir, gerenciar e aprovar ordens planejadas
description: Este tópico fornece informações sobre como exibir, gerenciar e aprovar ordens planejadas na Otimização de Planejamento.
author: ChristianRytt
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-08-21
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 3b9b5274481e693f9fa05eb084ec5505ce5bc2eb
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935648"
---
# <a name="view-manage-and-approve-planned-orders"></a><span data-ttu-id="45ac5-103">Exibir, gerenciar e aprovar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-103">View, manage, and approve planned orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="45ac5-104">Este tópico fornece informações sobre como exibir, gerenciar e aprovar ordens planejadas na Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="45ac5-104">This topic provides information about how to view, manage, and approve planned orders in Planning Optimization.</span></span>

## <a name="view-and-manage-planned-orders"></a><a name="view-planned-orders"></a><span data-ttu-id="45ac5-105">Exibir e gerenciar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-105">View and manage planned orders</span></span>

<span data-ttu-id="45ac5-106">Você pode exibir e gerenciar ordens planejadas em qualquer página de lista de ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="45ac5-106">You can view and manage planned orders on any planned orders list page.</span></span> <span data-ttu-id="45ac5-107">Vá para um dos seguintes locais, dependendo do tipo de ordens planejadas com as quais você deseja trabalhar:</span><span class="sxs-lookup"><span data-stu-id="45ac5-107">Go to one of the following places, depending on the type of planned orders that you want to work with:</span></span>

- <span data-ttu-id="45ac5-108">Planejamento mestre \> Espaços de trabalho \> Planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="45ac5-108">Master planning \> Workspaces \> Master planning</span></span>
- <span data-ttu-id="45ac5-109">Planejamento mestre \> Planejamento mestre \> Ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-109">Master planning \> Master planning \> Planned orders</span></span>
- <span data-ttu-id="45ac5-110">Controle de produção \> Ordens de produção \> Ordens de produção planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-110">Production control \> Production orders \> Planned production orders</span></span>
- <span data-ttu-id="45ac5-111">Compras e fornecimento \> Ordens de compra \> Ordens de compra planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-111">Procurement and sourcing \> Purchase orders \> Planned purchase orders</span></span>
- <span data-ttu-id="45ac5-112">Gerenciamento de estoque \> Ordens de entrada \> Transferências planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-112">Inventory management \> Inbound orders \> Planned transfers</span></span>
- <span data-ttu-id="45ac5-113">Gerenciamento de estoque \> Ordens de saída \> Transferências planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-113">Inventory management \> Outbound orders \> Planned transfers</span></span>

## <a name="view-and-edit-the-status-of-planned-orders"></a><span data-ttu-id="45ac5-114">Exiba e edite o status das ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-114">View and edit the status of planned orders</span></span>

<span data-ttu-id="45ac5-115">Você pode usar o campo **Status** de cada ordem planejada para ajudar a rastrear seu progresso ou alterar a forma como uma ordem planejada será processada.</span><span class="sxs-lookup"><span data-stu-id="45ac5-115">You can use the **Status** field of each planned order to help track your progress or change how a planned order will be processed.</span></span> <span data-ttu-id="45ac5-116">Os seguintes valores de **Status** estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="45ac5-116">The following **Status** values are available:</span></span>

- <span data-ttu-id="45ac5-117">**Não processado** – Quando o planejamento mestre gera ordens planejadas, elas recebem este status.</span><span class="sxs-lookup"><span data-stu-id="45ac5-117">**Unprocessed** – When master planning generates planned orders, they are given this status.</span></span> <span data-ttu-id="45ac5-118">As ordens planejadas com esse status serão excluídas durante a próxima execução de planejamento.</span><span class="sxs-lookup"><span data-stu-id="45ac5-118">Planned orders that have this status will be deleted during the next planning run.</span></span>
- <span data-ttu-id="45ac5-119">**Concluído** – este status indica que a ordem planejada foi concluída.</span><span class="sxs-lookup"><span data-stu-id="45ac5-119">**Completed** – This status indicates that the planned order has been completed.</span></span> <span data-ttu-id="45ac5-120">Se você optar por não confirmar uma ordem planejada, poderá atribuir manualmente seu status para *Concluído*.</span><span class="sxs-lookup"><span data-stu-id="45ac5-120">If you decide not to firm a planned order, you can manually change its status to *Completed*.</span></span> <span data-ttu-id="45ac5-121">Observe que o sistema trata os status *Não processado* e *Concluído* da mesma forma.</span><span class="sxs-lookup"><span data-stu-id="45ac5-121">Note that the system treats the *Unprocessed* and *Completed* statuses in the same way.</span></span>
- <span data-ttu-id="45ac5-122">**Aprovado** – este status indica que a ordem planejada foi aprovada para confirmação.</span><span class="sxs-lookup"><span data-stu-id="45ac5-122">**Approved** – This status indicates that the planned order is approved for firming.</span></span> <span data-ttu-id="45ac5-123">Se você desejar confirmar uma ordem planejada, poderá alterar seu status para *Aprovado*.</span><span class="sxs-lookup"><span data-stu-id="45ac5-123">If you want to firm a planned order, you can change its status to *Approved*.</span></span> <span data-ttu-id="45ac5-124">Se desejar manter as edições que foram feitas em uma ordem planejada ou se estiver planejando confirmar uma ordem planejada, altere seu status para *Aprovado*.</span><span class="sxs-lookup"><span data-stu-id="45ac5-124">If you want to keep the edits that have been made to a planned order, or if you're planning to firm a planned order, change its status to *Approved*.</span></span> <span data-ttu-id="45ac5-125">As ordens planejadas com o status *Aprovado* são consideradas de fornecimento fixo e esperado pelo planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="45ac5-125">Planned orders that have a status of *Approved* are considered fixed and expected supply by master planning.</span></span> <span data-ttu-id="45ac5-126">Portanto, elas não serão modificadas ou excluídas durante a execução do planejamento mestre posterior.</span><span class="sxs-lookup"><span data-stu-id="45ac5-126">Therefore, they aren't modified or deleted during later master planning runs.</span></span> <span data-ttu-id="45ac5-127">Para atingir este procedimento, a lógica de planejamento copia as ordens planejadas com status *Aprovado* da versão anterior do plano para a nova versão do plano durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="45ac5-127">To achieve this behavior, the planning logic copies planned orders that have a status of *Approved* from the old plan version to the new plan version during master planning.</span></span> <span data-ttu-id="45ac5-128">Observe que as ordens planejadas com o status *Aprovado* só são consideradas fornecimento no plano mestre específico.</span><span class="sxs-lookup"><span data-stu-id="45ac5-128">Note that planned orders that have a status of *Approved*\* are considered supply only within the specific master plan.</span></span>

<span data-ttu-id="45ac5-129">Para alterar o status de uma ordem planejada única, [abra qualquer página de lista de ordens planejadas](#view-planned-orders)abra a ordem e siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="45ac5-129">To change the status of a single planned order, [open any planned orders list page](#view-planned-orders), open the order, and then follow one of these steps:</span></span>

- <span data-ttu-id="45ac5-130">Na FastTab **Geral**, altere o valor do campo **Status**.</span><span class="sxs-lookup"><span data-stu-id="45ac5-130">On the **General** FastTab, change the value of the **Status** field.</span></span>
- <span data-ttu-id="45ac5-131">No Painel de Ações, na guia **Ordem de alteração**, no grupo **Processo**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="45ac5-131">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="45ac5-132">No Painel de Ações, selecione **Aprovar** para marcar a ordem como aprovada.</span><span class="sxs-lookup"><span data-stu-id="45ac5-132">On the Action Pane, select **Approve** to mark the order as approved.</span></span>

<span data-ttu-id="45ac5-133">Para alterar o status de várias ordens planejadas ao mesmo tempo, [abra qualquer página de lista de ordens planejadas](#view-planned-orders), marque a caixa de seleção para cada ordem que deseja alterar e siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="45ac5-133">To change the status of several planned orders at the same time, [open any planned orders list page](#view-planned-orders), select the check box for each order that you want to change, and then follow one of these steps:</span></span>

- <span data-ttu-id="45ac5-134">No Painel de Ações, na guia **Ordem de alteração**, no grupo **Processo**, selecione **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="45ac5-134">On the Action Pane, on the **Planned order** tab, in the **Process** group, select **Change status**.</span></span>
- <span data-ttu-id="45ac5-135">No Painel de Ações, selecione **Aprovar** para marcar as ordens como aprovadas.</span><span class="sxs-lookup"><span data-stu-id="45ac5-135">On the Action Pane, select **Approve** to mark the orders as approved.</span></span>

## <a name="approve-planned-orders"></a><span data-ttu-id="45ac5-136">Aprovar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-136">Approve planned orders</span></span>

<span data-ttu-id="45ac5-137">A aprovação de ordens planejadas é uma etapa opcional no processo de criação de uma ordem confirmada com base em uma ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="45ac5-137">Approval of planned orders is an optional step in the process of creating a firmed order from a planned order.</span></span>

<span data-ttu-id="45ac5-138">A ilustração a seguir mostra como você pode usar o valor **Status** que é atribuído a cada ordem planejada para implementar um fluxo de trabalho de aprovação.</span><span class="sxs-lookup"><span data-stu-id="45ac5-138">The following illustration shows how you can use the **Status** value that is assigned to each planned order to implement an approval workflow.</span></span> <span data-ttu-id="45ac5-139">Para implementar um processo de aprovação, ajuste manualmente o valor do **Status** de cada ordem planejada, conforme descrito na seção anterior.</span><span class="sxs-lookup"><span data-stu-id="45ac5-139">To implement an approval process, manually adjust the **Status** value for each planned order as described in the previous section.</span></span>

![Fluxo de ordem planejada](media/approved-planned-orders-1.png)

> [!TIP]
> <span data-ttu-id="45ac5-141">Recomendamos que você aprove quaisquer ordens planejadas modificadas.</span><span class="sxs-lookup"><span data-stu-id="45ac5-141">We recommend that you approve any modified planned orders.</span></span> <span data-ttu-id="45ac5-142">Caso contrário, as edições serão ignoradas e sobrescritas pela próxima execução de planejamento.</span><span class="sxs-lookup"><span data-stu-id="45ac5-142">Otherwise, the edits will be ignored and overwritten by the next planning run.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="45ac5-143">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="45ac5-143">Additional resources</span></span>

- [<span data-ttu-id="45ac5-144">Confirmar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="45ac5-144">Firm planned orders</span></span>](planned-order-firming.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
