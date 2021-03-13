---
title: Fluxos de trabalho de Compras
description: Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação. Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.
author: RichardLuan
manager: tfehr
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2074
ms.assetid: e54a1d59-b9fb-421b-821d-01f32878aa9b
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af614b7f29144d02a853ef15b008f2a21d3d3aa5
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019742"
---
# <a name="procurement-and-sourcing-workflows"></a><span data-ttu-id="d19bd-104">Fluxos de trabalho de compras</span><span class="sxs-lookup"><span data-stu-id="d19bd-104">Procurement and sourcing workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d19bd-105">Algumas organizações exigem que as requisições de compra e as ordens de compra sejam aprovadas por um usuário diferente daquele que iniciou a transação.</span><span class="sxs-lookup"><span data-stu-id="d19bd-105">Some organizations require that purchase requisitions and purchase orders are approved by a user other than the person who entered the transaction.</span></span> <span data-ttu-id="d19bd-106">Para configurar um processo de aprovação, você pode criar um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d19bd-106">To set up an approval process, you can create a workflow.</span></span>

<span data-ttu-id="d19bd-107">Um fluxo de trabalho representa um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="d19bd-107">A workflow represents a business process.</span></span> <span data-ttu-id="d19bd-108">Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento.</span><span class="sxs-lookup"><span data-stu-id="d19bd-108">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="d19bd-109">O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="d19bd-109">There are several benefits of using the workflow system in your organization:</span></span>

- <span data-ttu-id="d19bd-110">**Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="d19bd-110">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="d19bd-111">O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="d19bd-111">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>
- <span data-ttu-id="d19bd-112">**Visibilidade do processo** — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d19bd-112">**Process visibility** — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="d19bd-113">Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.</span><span class="sxs-lookup"><span data-stu-id="d19bd-113">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>
- <span data-ttu-id="d19bd-114">**Lista de trabalho centralizada** — os usuários podem exibir uma lista de trabalho centralizada para exibir as tarefas do fluxo de trabalho e as aprovações atribuídas a eles em todos os fluxos de trabalho de que participam.</span><span class="sxs-lookup"><span data-stu-id="d19bd-114">**Centralized work list** — Users can view a centralized work list to view the workflow tasks and approvals assigned to them across all workflows they participate in.</span></span> <span data-ttu-id="d19bd-115">Isso está disponível na página Itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d19bd-115">This is available in the Work items page.</span></span>

## <a name="the-types-of-workflows-that-you-can-create"></a><span data-ttu-id="d19bd-116">Os tipos de fluxo de trabalho que você pode criar</span><span class="sxs-lookup"><span data-stu-id="d19bd-116">The types of workflows that you can create</span></span>

<span data-ttu-id="d19bd-117">Os tipos de fluxo de trabalho a seguir estão disponíveis para Compras.</span><span class="sxs-lookup"><span data-stu-id="d19bd-117">The following workflow types are available for Procurement and sourcing.</span></span>

| <span data-ttu-id="d19bd-118">Tipo</span><span class="sxs-lookup"><span data-stu-id="d19bd-118">Type</span></span> | <span data-ttu-id="d19bd-119">Use este tipo para</span><span class="sxs-lookup"><span data-stu-id="d19bd-119">Use this type to</span></span> |
|---|---|
| <span data-ttu-id="d19bd-120">Revisão da requisição de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-120">Purchase requisition review</span></span> | <span data-ttu-id="d19bd-121">Criar fluxos de trabalho de aprovação e revisão para requisições de compra.</span><span class="sxs-lookup"><span data-stu-id="d19bd-121">Create review and approval workflows for purchase requisitions.</span></span> |
| <span data-ttu-id="d19bd-122">Revisão de linha de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-122">Purchase requisition line review</span></span> | <span data-ttu-id="d19bd-123">Criar fluxos de trabalho de revisão e aprovação para linhas de requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="d19bd-123">Create review and approval workflows for purchase requisition lines.</span></span> |
| <span data-ttu-id="d19bd-124">Fluxo de trabalho da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-124">Purchase order workflow</span></span> | <span data-ttu-id="d19bd-125">Criar fluxos de trabalho de revisão e aprovação para ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d19bd-125">Create review and approval workflows for purchase orders.</span></span> |
| <span data-ttu-id="d19bd-126">Fluxo de trabalho da linha da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-126">Purchase order line workflow</span></span> | <span data-ttu-id="d19bd-127">Criar fluxos de trabalho de revisão e aprovação para linhas de ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d19bd-127">Create review and approve workflows for purchase order lines.</span></span> |
| <span data-ttu-id="d19bd-128">Fluxo de trabalho da solicitação de emprego adicionada pelo fornecedor</span><span class="sxs-lookup"><span data-stu-id="d19bd-128">Vendor add application workflow</span></span> | <span data-ttu-id="d19bd-129">Criar fluxos de trabalho da revisão e de aprovação para adicionar novos fornecedores por meio de solicitações de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="d19bd-129">Create review and approval workflows for adding new vendors via vendor requests.</span></span> |

> [!IMPORTANT]
> <span data-ttu-id="d19bd-130">Ao adicionar um novo fluxo de trabalho, talvez você também veja os seguintes fluxos de trabalho obsoletos listados na caixa de diálogo **Criar fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d19bd-130">When you are adding a new workflow, you might also see the following obsolete workflows listed in the **Create workflow** dialog box.</span></span> <span data-ttu-id="d19bd-131">Eles estão relacionados à funcionalidade *confirmação de recebimento* que estava disponível no [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), mas que agora foi preterida.</span><span class="sxs-lookup"><span data-stu-id="d19bd-131">These are related to the *confirmation of receipt* functionality that was available in [Dynamics AX 2012](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-procurement-and-sourcing-workflows), but which has now been deprecated.</span></span> <span data-ttu-id="d19bd-132">Não há suporte para esses fluxos de trabalho no momento.</span><span class="sxs-lookup"><span data-stu-id="d19bd-132">These workflows are currently unsupported.</span></span>
> 
> - <span data-ttu-id="d19bd-133">Fluxo de trabalho da notificação de data de vencimento da entrega</span><span class="sxs-lookup"><span data-stu-id="d19bd-133">Delivery due date notification workflow</span></span>
> - <span data-ttu-id="d19bd-134">Fatura recebeu fluxo de trabalho da notificação</span><span class="sxs-lookup"><span data-stu-id="d19bd-134">Invoice received notification workflow</span></span>
> - <span data-ttu-id="d19bd-135">Falha de recebimento de produtos no fluxo de trabalho de notificação</span><span class="sxs-lookup"><span data-stu-id="d19bd-135">Product receipt failed notification workflow</span></span>
> - <span data-ttu-id="d19bd-136">Fluxo de trabalho da notificação de rejeição do recebimento de produtos não confirmados</span><span class="sxs-lookup"><span data-stu-id="d19bd-136">Unconfirmed product receipt rejection notification workflow</span></span>

## <a name="creating-a-workflow"></a><span data-ttu-id="d19bd-137">Criação de um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d19bd-137">Creating a workflow</span></span>

<span data-ttu-id="d19bd-138">Para criar um fluxo de trabalho, vá para Compras &gt; Configuração &gt; Fluxos de trabalho de compras e crie um novo fluxo de trabalho ao selecionar o tipo de fluxo de trabalho que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="d19bd-138">To create a workflow, go to Procurement and sourcing &gt; Setup &gt; Procurement and sourcing workflows and create a new workflow by selecting the type of workflow you want to create.</span></span> 

<span data-ttu-id="d19bd-139">Na tela do fluxo de trabalho, você pode arrastar elementos de fluxo de trabalho para o designer e vincular os elementos a um fluxo.</span><span class="sxs-lookup"><span data-stu-id="d19bd-139">In the workflow canvas you can drag workflow elements into the designer and link the elements into a flow.</span></span> <span data-ttu-id="d19bd-140">Os elementos de fluxo de trabalho devem ser configurados.</span><span class="sxs-lookup"><span data-stu-id="d19bd-140">The workflow elements should be configured.</span></span> <span data-ttu-id="d19bd-141">Para os elementos do fluxo de trabalho de aprovação e de tarefa, você pode configurar qual participante deverá executar a ação.</span><span class="sxs-lookup"><span data-stu-id="d19bd-141">For approval and task workflow elements you can configure which participant should take action.</span></span>

## <a name="types-of-participants"></a><span data-ttu-id="d19bd-142">Tipos de participantes</span><span class="sxs-lookup"><span data-stu-id="d19bd-142">Types of participants</span></span>

<span data-ttu-id="d19bd-143">Você pode atribuir uma etapa de aprovação aos grupos de participantes a seguir.</span><span class="sxs-lookup"><span data-stu-id="d19bd-143">You can assign an approval step to the following groups of participants.</span></span>

| <span data-ttu-id="d19bd-144">Grupo de usuários</span><span class="sxs-lookup"><span data-stu-id="d19bd-144">User group</span></span> | <span data-ttu-id="d19bd-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="d19bd-145">Description</span></span> |
|---|---|
| <span data-ttu-id="d19bd-146">Participante</span><span class="sxs-lookup"><span data-stu-id="d19bd-146">Participant</span></span> | <span data-ttu-id="d19bd-147">Atribuir a etapa de aprovação aos membros de um grupo ou de uma função.</span><span class="sxs-lookup"><span data-stu-id="d19bd-147">Assign the approval step to members of a group or role.</span></span> |
| <span data-ttu-id="d19bd-148">Hierarquia</span><span class="sxs-lookup"><span data-stu-id="d19bd-148">Hierarchy</span></span> | <span data-ttu-id="d19bd-149">Atribuir a etapa de aprovação aos usuários em uma hierarquia organizacional específica.</span><span class="sxs-lookup"><span data-stu-id="d19bd-149">Assign the approval step to users in a specific organizational hierarchy.</span></span> |
| <span data-ttu-id="d19bd-150">Usuário de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="d19bd-150">Workflow user</span></span> | <span data-ttu-id="d19bd-151">Atribuir a etapa de aprovação aos usuários desse fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d19bd-151">Assign the approval step to users of this workflow.</span></span> |
| <span data-ttu-id="d19bd-152">Fila</span><span class="sxs-lookup"><span data-stu-id="d19bd-152">Queue</span></span> | <span data-ttu-id="d19bd-153">Atribua a etapa de aprovação em uma fila de itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d19bd-153">Assign the approval step to a work item queue.</span></span> |
| <span data-ttu-id="d19bd-154">Usuário</span><span class="sxs-lookup"><span data-stu-id="d19bd-154">User</span></span> | <span data-ttu-id="d19bd-155">Atribua a etapa de aprovação a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="d19bd-155">Assign the approval step to specific users.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="d19bd-156">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d19bd-156">Additional resources</span></span>

- [<span data-ttu-id="d19bd-157">Definir fluxos de trabalho de processos de negócios para requisições de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-157">Defining business process workflows for purchase requisitions</span></span>](https://www.microsoft.com/download/details.aspx?id=101821)
- [<span data-ttu-id="d19bd-158">Fluxo de trabalho de requisição de compra</span><span class="sxs-lookup"><span data-stu-id="d19bd-158">Purchase requisition workflow</span></span>](purchase-requisitions-workflow.md)
- [<span data-ttu-id="d19bd-159">Integração de fornecedores</span><span class="sxs-lookup"><span data-stu-id="d19bd-159">Onboard vendors</span></span>](vendor-onboarding.md)
