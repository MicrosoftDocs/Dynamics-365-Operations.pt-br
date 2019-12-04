---
title: Configurar fluxos de trabalho para despesa
description: Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 86cadf7277fbb7e08dad4b5dc2a46e1c6ce5a888
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176409"
---
# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="ba9ce-103">Configurar fluxos de trabalho para despesa</span><span class="sxs-lookup"><span data-stu-id="ba9ce-103">Set up workflows for expense</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba9ce-104"> Você pode configurar um processo de fluxo de trabalho que é usado para revisar e aprovar documentos viagem e despesas.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="ba9ce-105">Os documentos para os quais os fluxos de trabalho podem ser definidos incluem os relatórios de despesas, requisições de viagem e solicitações de adiantamento de dinheiro.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="ba9ce-106">Um fluxo de trabalho representa um processo comercial.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-106">A workflow represents a business process.</span></span> <span data-ttu-id="ba9ce-107">Ele define como um documento flui pelo sistema e indica quem deve concluir uma tarefa ou aprovar um documento.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="ba9ce-108">O uso do sistema de fluxo de trabalho em sua organização traz vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="ba9ce-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="ba9ce-109">**Processos consistentes** — você pode definir o processo de aprovação de documentos específicos, como requisições de compra e relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="ba9ce-110">O uso desse sistema ajuda a garantir que os documentos sejam processados e aprovados de maneira consistente e eficiente.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="ba9ce-111">Visibilidade do processo — você pode rastrear o status, o histórico e as métricas de desempenho de uma instância específica do fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="ba9ce-112">Isso ajuda a determinar se alterações devem ser feitas no fluxo de trabalho para aumentar a eficiência.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="ba9ce-113">Lista de trabalho centralizada — os usuários podem exibir uma lista de trabalho centralizada para ver as tarefas do Fluxo de Trabalho e as aprovações atribuídas a elas.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="ba9ce-114">**Os tipos de fluxo de trabalho que você pode criar**</span><span class="sxs-lookup"><span data-stu-id="ba9ce-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="ba9ce-115">A tabela a seguir lista os tipos de fluxos de trabalho que podem ser criados em **Despesa**.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="ba9ce-116"><strong>Tipo</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="ba9ce-117"><strong>Use este tipo para</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="ba9ce-118"><strong>Relatório de Despesas</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="ba9ce-119">Criar fluxos de trabalho de aprovação para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="ba9ce-120"><strong>Lançamento automático de relatório de despesas</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="ba9ce-121">Criar fluxos de trabalho de lançamento automático para relatórios de despesas.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="ba9ce-122"><strong>Item de linha de despesa</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="ba9ce-123">Criar fluxos de trabalho de aprovação para itens de linha em relatórios de despesa.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="ba9ce-124"><strong>Lançamento automático de itens de linha de despesa</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="ba9ce-125">Criar fluxos de trabalho de lançamento automático para itens de linha em relatórios de despesa.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="ba9ce-126"><strong>Requisição de viagem</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="ba9ce-127">Criar fluxos de trabalho de aprovação para requisições de viagem.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="ba9ce-128"><strong>Solicitação de adiantamento de dinheiro</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="ba9ce-129">Criar fluxos de trabalho de aprovação das solicitações de adiantamento em dinheiro.</span><span class="sxs-lookup"><span data-stu-id="ba9ce-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="ba9ce-130"><strong>Restituição de imposto IVA</strong></span><span class="sxs-lookup"><span data-stu-id="ba9ce-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="ba9ce-131">Criar fluxos de trabalho de aprovação para a recuperação de imposto sobre valor agregado (VAT).</span><span class="sxs-lookup"><span data-stu-id="ba9ce-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |
