---
title: Configurar fluxos de trabalho para despesa
description: "Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: fb729a56919eb50cdff8318138986152bb65a083
ms.contentlocale: pt-br
ms.lasthandoff: 01/19/2018

---

# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="790c5-103">Configurar fluxos de trabalho para despesa</span><span class="sxs-lookup"><span data-stu-id="790c5-103">Set up workflows for expense</span></span>

[!include[banner](../includes/banner.md)]<span data-ttu-id="790c5-104"> Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas.</span><span class="sxs-lookup"><span data-stu-id="790c5-104"> You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="790c5-105">Os documentos para os quais os fluxos de trabalho podem ser definidos incluem os relatórios de despesas, requisições de viagem e solicitações de adiantamento de dinheiro.</span><span class="sxs-lookup"><span data-stu-id="790c5-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="790c5-106">Um fluxo de trabalho representa um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="790c5-106">A workflow represents a business process.</span></span> <span data-ttu-id="790c5-107">Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento.</span><span class="sxs-lookup"><span data-stu-id="790c5-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="790c5-108">O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="790c5-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="790c5-109">**Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="790c5-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="790c5-110">O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="790c5-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="790c5-111">Visibilidade do processo — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="790c5-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="790c5-112">Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.</span><span class="sxs-lookup"><span data-stu-id="790c5-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="790c5-113">Lista de trabalho centralizada — os usuários podem exibir uma lista de trabalho centralizada para ver as tarefas do Fluxo de Trabalho e as aprovações atribuídas a elas.</span><span class="sxs-lookup"><span data-stu-id="790c5-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="790c5-114">**Os tipos de fluxo de trabalho que você pode criar**</span><span class="sxs-lookup"><span data-stu-id="790c5-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="790c5-115">A tabela a seguir lista os tipos de fluxos de trabalho que podem ser criados em **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="790c5-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>

| <span data-ttu-id="790c5-116">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="790c5-116">**Type**</span></span>                           | <span data-ttu-id="790c5-117">**Use este tipo para**</span><span class="sxs-lookup"><span data-stu-id="790c5-117">**Use this type to**</span></span>                                                 |     
|------------------------------------|----------------------------------------------------------------------|
| <span data-ttu-id="790c5-118">**Relatório de Despesas**</span><span class="sxs-lookup"><span data-stu-id="790c5-118">**Expense report**</span></span>                 | <span data-ttu-id="790c5-119">Criar fluxos de trabalho de aprovação para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="790c5-119">Create approval workflows for expense reports.</span></span>                       |      
| <span data-ttu-id="790c5-120">**Lançamento automático de relatório de despesas**</span><span class="sxs-lookup"><span data-stu-id="790c5-120">**Expense report auto posting**</span></span>    | <span data-ttu-id="790c5-121">Criar fluxos de trabalho de lançamento automático para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="790c5-121">Create automatic posting workflows for expense reports.</span></span>              |     
| <span data-ttu-id="790c5-122">**Item de linha de despesa**</span><span class="sxs-lookup"><span data-stu-id="790c5-122">**Expense line item**</span></span>              | <span data-ttu-id="790c5-123">Criar fluxos de trabalho de aprovação para itens de linha em relatórios de despesa.</span><span class="sxs-lookup"><span data-stu-id="790c5-123">Create approval workflows for line items on expense reports.</span></span>         |     
| <span data-ttu-id="790c5-124">**Lançamento automático de itens de linha de despesa**</span><span class="sxs-lookup"><span data-stu-id="790c5-124">**Expense line item auto posting**</span></span> | <span data-ttu-id="790c5-125">Criar fluxos de trabalho de lançamento automático para itens de linha em relatórios de despesa.</span><span class="sxs-lookup"><span data-stu-id="790c5-125">Create automatic posting workflows for line items on expense reports.</span></span>|
| <span data-ttu-id="790c5-126">**Requisição de viagem**</span><span class="sxs-lookup"><span data-stu-id="790c5-126">**Travel requisition**</span></span>             | <span data-ttu-id="790c5-127">Criar fluxos de trabalho de aprovação para requisições de viagem.</span><span class="sxs-lookup"><span data-stu-id="790c5-127">Create approval workflows for travel requisitions.</span></span>                   |    
| <span data-ttu-id="790c5-128">**Solicitação de adiantamento de dinheiro**</span><span class="sxs-lookup"><span data-stu-id="790c5-128">**Cash advance request**</span></span>           | <span data-ttu-id="790c5-129">Criar fluxos de trabalho de aprovação das solicitações de adiantamento em dinheiro.</span><span class="sxs-lookup"><span data-stu-id="790c5-129">Create approval workflows for cash advance requests.</span></span>                 |     
| <span data-ttu-id="790c5-130">**Restituição de imposto IVA**</span><span class="sxs-lookup"><span data-stu-id="790c5-130">**VAT tax recovery**</span></span>               | <span data-ttu-id="790c5-131">Criar fluxos de trabalho de aprovação para a recuperação de imposto sobre valor agregado (VAT).</span><span class="sxs-lookup"><span data-stu-id="790c5-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span> |       

