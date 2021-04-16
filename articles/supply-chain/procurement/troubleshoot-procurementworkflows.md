---
title: Solucionar problemas de fluxos de trabalho de compras e fornecimento
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com fluxos de trabalho de compras e fornecimento.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 100adef4dfd257ba86dd394b401766d2cb00394c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832025"
---
# <a name="troubleshoot-procurement-and-sourcing-workflows"></a><span data-ttu-id="8fce5-103">Solucionar problemas de fluxos de trabalho de compras e fornecimento</span><span class="sxs-lookup"><span data-stu-id="8fce5-103">Troubleshoot procurement and sourcing workflows</span></span>

<span data-ttu-id="8fce5-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com fluxos de trabalho de compras e fornecimento.</span><span class="sxs-lookup"><span data-stu-id="8fce5-104">This topic describes how to fix issues that you might encounter while you work with procurement and sourcing workflows.</span></span>

## <a name="error-when-re-submitting-a-purchase-order-to-the-workflow-after-a-change-changes-to-purchase-order-x-are-allowed-only-in-a-draft-state-when-change-management-is-activated"></a><span data-ttu-id="8fce5-105">Erro ao enviar novamente uma ordem de compra para o fluxo de trabalho após uma alteração: "As alterações na ordem de compra X são permitidas somente em um estado de rascunho quando o gerenciamento de alterações é ativado"</span><span class="sxs-lookup"><span data-stu-id="8fce5-105">Error when re-submitting a purchase order to the workflow after a change: "Changes to purchase order X are allowed only in a Draft state when change management is activated"</span></span>

<span data-ttu-id="8fce5-106">Esse problema ocorre apenas se a ordem de compra estiver em um estado *Confirmado* antes da solicitação de alterações.</span><span class="sxs-lookup"><span data-stu-id="8fce5-106">This issue occurs only if the purchase order was in a *Confirmed* state before you requested changes.</span></span> <span data-ttu-id="8fce5-107">Se você solicitar alterações enquanto a ordem de compra estiver em um estado *Aprovado*, o fluxo de trabalho poderá ser processado com êxito.</span><span class="sxs-lookup"><span data-stu-id="8fce5-107">If you request changes while the purchase order is in an *Approved* state, the workflow can be processed successfully.</span></span>

### <a name="error-description"></a><span data-ttu-id="8fce5-108">Descrição do erro</span><span class="sxs-lookup"><span data-stu-id="8fce5-108">Error description</span></span>

<span data-ttu-id="8fce5-109">O seguinte erro ocorre no fluxo de trabalho quando uma ordem de compra é reenviada após uma alteração:</span><span class="sxs-lookup"><span data-stu-id="8fce5-109">The following error occurs in the workflow when a purchase order is resubmitted after a change:</span></span>

> <span data-ttu-id="8fce5-110">Parado (erro): Exceção X++: Alterações na ordem de compra PO0000569 só são permitidas no estado de rascunho quando o gerenciamento de alterações for ativado em</span><span class="sxs-lookup"><span data-stu-id="8fce5-110">Stopped (error): X++ Exception: Changes to purchase order PO0000569 are only allowed in state Draft when change management is activated at</span></span><br>
<span data-ttu-id="8fce5-111">SysWorkflowParticipantProvider-resolve</span><span class="sxs-lookup"><span data-stu-id="8fce5-111">SysWorkflowParticipantProvider-resolve</span></span><br>
<span data-ttu-id="8fce5-112">SysWorkflowParticipantProvider-resolveParticipants</span><span class="sxs-lookup"><span data-stu-id="8fce5-112">SysWorkflowParticipantProvider-resolveParticipants</span></span><br>
<span data-ttu-id="8fce5-113">SysWorkflowServiceProvider-resolveParticipant</span><span class="sxs-lookup"><span data-stu-id="8fce5-113">SysWorkflowServiceProvider-resolveParticipant</span></span><br>
<span data-ttu-id="8fce5-114">SysWorkflowQueue-resume</span><span class="sxs-lookup"><span data-stu-id="8fce5-114">SysWorkflowQueue-resume</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8fce5-115">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="8fce5-115">Issue resolution</span></span>

<span data-ttu-id="8fce5-116">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="8fce5-116">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="8fce5-117">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="8fce5-117">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="8fce5-118">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="8fce5-118">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

<span data-ttu-id="8fce5-119">O problema será corrigido através [deste artigo da Base de Dados de Conhecimento (KB) da Microsoft](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span><span class="sxs-lookup"><span data-stu-id="8fce5-119">The issue will be fixed through [this Microsoft Knowledge Base (KB) article](https://msdyneng.visualstudio.com/FinOps/_workitems/edit/467138).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="8fce5-120">Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas.</span><span class="sxs-lookup"><span data-stu-id="8fce5-120">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

<span data-ttu-id="8fce5-121">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="8fce5-121">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="8fce5-122">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="8fce5-122">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="8fce5-123">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="8fce5-123">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="if-a-delivery-remainder-is-canceled-on-a-purchase-order-where-change-management-is-turned-on-the-purchase-order-goes-to-a-confirmed-state"></a><span data-ttu-id="8fce5-124">Se um resto da entrega for cancelado em uma ordem de compra na qual o gerenciamento de alterações está ativado, a ordem de compra vai para um estado Confirmado.</span><span class="sxs-lookup"><span data-stu-id="8fce5-124">If a delivery remainder is canceled on a purchase order where change management is turned on, the purchase order goes to a Confirmed state.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8fce5-125">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="8fce5-125">Issue description</span></span>

<span data-ttu-id="8fce5-126">Para uma ordem de compra sujeita ao gerenciamento de alterações, se a única alteração solicitada for o cancelamento de uma entrega pendente em uma ou mais linhas, a ordem de compra irá diretamente para um estado *Confirmado* quando for aprovada e nenhum diário será criado.</span><span class="sxs-lookup"><span data-stu-id="8fce5-126">For a purchase order that is subject to change management, if the only change that is requested is the cancellation of a delivery remainder on one or more of the lines, the purchase order will go directly to a *Confirmed* state when it's approved, and no journal will be created.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8fce5-127">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="8fce5-127">Issue resolution</span></span>

<span data-ttu-id="8fce5-128">O cancelamento de uma pendência de entrega não afeta o conteúdo do diário de confirmação.</span><span class="sxs-lookup"><span data-stu-id="8fce5-128">Cancellation of a delivery remainder doesn't affect the contents of the confirmation journal.</span></span> <span data-ttu-id="8fce5-129">Essa funcionalidade deve ser usada quando a linha foi parcialmente recebida e a qualidade final deve ser cancelada na etapa do processo após a confirmação da ordem de compra com o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8fce5-129">This functionality should be used when the line has been partially received, and the remainder quality should be canceled in the process step after the purchase order has been confirmed with the vendor.</span></span>

<span data-ttu-id="8fce5-130">Se isso deve ser refletido na confirmação da ordem de compra, a quantidade deve ser ajustada na linha da ordem de compra para que a confirmação seja obrigatória.</span><span class="sxs-lookup"><span data-stu-id="8fce5-130">If this should be reflected on the purchase order confirmation, the quantity should be adjusted on the purchase order line so that the confirmation will be required.</span></span> <span data-ttu-id="8fce5-131">Como alternativa, se nada foi recebido na linha, a quantidade pode ser removida.</span><span class="sxs-lookup"><span data-stu-id="8fce5-131">Alternatively, if nothing has been received on the line, the quantity can be removed.</span></span> <span data-ttu-id="8fce5-132">Nesse caso, será necessário reconfirmar.</span><span class="sxs-lookup"><span data-stu-id="8fce5-132">In this case, reconfirmation will be required.</span></span>

## <a name="canceled-purchase-orders-appear-in-the-draft-list-in-the-purchase-order-preparation-workspace"></a><span data-ttu-id="8fce5-133">As ordens de compra canceladas aparecem na lista de rascunhos no espaço de trabalho de preparação da Ordem de Compra.</span><span class="sxs-lookup"><span data-stu-id="8fce5-133">Canceled purchase orders appear in the draft list in the Purchase order preparation workspace.</span></span>

### <a name="issue-description"></a><span data-ttu-id="8fce5-134">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="8fce5-134">Issue description</span></span>

<span data-ttu-id="8fce5-135">Depois de cancelar as ordens de compra que estavam em um estado *Confirmado*, as ordens de compra canceladas ainda aparecem na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="8fce5-135">After you cancel purchase orders that were in a *Confirmed* state, the canceled purchase orders still appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="8fce5-136">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="8fce5-136">Issue resolution</span></span>

<span data-ttu-id="8fce5-137">Esse problema ocorre apenas para ordens de compra sujeitas ao gerenciamento de alterações.</span><span class="sxs-lookup"><span data-stu-id="8fce5-137">This issue occurs only for purchase orders that are subject to change management.</span></span> <span data-ttu-id="8fce5-138">Ele ocorre porque o cancelamento é considerado uma alteração que deve ser aprovada.</span><span class="sxs-lookup"><span data-stu-id="8fce5-138">It occurs because the cancellation is considered a change that must be approved.</span></span> <span data-ttu-id="8fce5-139">A aprovação pode ser feita automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="8fce5-139">The approval can be done automatically by the system.</span></span> <span data-ttu-id="8fce5-140">Portanto, o processo é enviar a ordem de compra cancelada para o fluxo de trabalho de aprovação, de forma que possa ir para um estado *Aprovado*.</span><span class="sxs-lookup"><span data-stu-id="8fce5-140">Therefore, the process is to submit the canceled purchase order to the approval workflow so that it can go to an *Approved* state.</span></span> <span data-ttu-id="8fce5-141">Nesse ponto, a ordem de compra não será mais exibida na lista de ordens de compra de rascunho no espaço de trabalho **Preparação da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="8fce5-141">At that point, the purchase order will no longer appear in the list of draft purchase orders in the **Purchase order preparation** workspace.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]