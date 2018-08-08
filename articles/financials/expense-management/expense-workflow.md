---
title: Fluxo de trabalho de despesas
description: "Este tópico explica como você pode usar o sistema fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations, para configurar um processo de revisão para despesas relatório no gerenciamento de despesas."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: bd5b4ca2f7316b3e691ee5c11c6e47969370b95b
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="expense-workflow"></a><span data-ttu-id="d4b1e-103">Fluxo de trabalho de despesas</span><span class="sxs-lookup"><span data-stu-id="d4b1e-103">Expense workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d4b1e-104">Você pode usar o sistema de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations para configurar um processo de revisão para relatório de despesas no gerenciamento de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-104">You can use the workflow system in Microsoft Dynamics 365 for Finance and Operations, to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="d4b1e-105">É possível configurar um fluxo de trabalho que usa os seguintes critérios para determinar quem aprova os relatórios de despesas:</span><span class="sxs-lookup"><span data-stu-id="d4b1e-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="d4b1e-106">A hierarquia de relatórios de funcionários e os limites de aprovação predefinidos</span><span class="sxs-lookup"><span data-stu-id="d4b1e-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="d4b1e-107">Aprovação de vários níveis que suporta aprovadores provisórios e um aprovador final</span><span class="sxs-lookup"><span data-stu-id="d4b1e-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="d4b1e-108">Dimensões financeiras e responsabilidade do projeto</span><span class="sxs-lookup"><span data-stu-id="d4b1e-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="d4b1e-109">Atribuição a usuários ou grupos de usuários específicos</span><span class="sxs-lookup"><span data-stu-id="d4b1e-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="d4b1e-110">As aprovações do fluxo de trabalho podem ser criadas para relatórios de despesas, requisições de viagem, adiantamentos em dinheiro e recuperação do imposto sobre valor agregado (IVA).</span><span class="sxs-lookup"><span data-stu-id="d4b1e-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="d4b1e-111">**Exemplo**</span><span class="sxs-lookup"><span data-stu-id="d4b1e-111">**Example**</span></span>

<span data-ttu-id="d4b1e-112">O processo a seguir é um exemplo do fluxo de trabalho de gerenciamento de despesas para um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="d4b1e-113">Um funcionário cria e salva um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="d4b1e-114">O funcionário envia o relatório para aprovação.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="d4b1e-115">O aprovador é identificado com base nas regras definidas quando o fluxo de trabalho foi configurado.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="d4b1e-116">O aprovador recebe uma notificação de que um relatório de despesas está pronto para aprovação.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="d4b1e-117">O aprovador examina o relatório de despesas e verifica se as seguintes condições são atendidas:</span><span class="sxs-lookup"><span data-stu-id="d4b1e-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="d4b1e-118">As despesas não violam nenhuma política de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="d4b1e-119">Se uma despesa violar uma política, o aprovador verificará se o relatório de despesas tem uma justificativa de negócios válida.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="d4b1e-120">Recibos de equipamentos eletrônicos estão anexados ao relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="d4b1e-121">O aprovador aprova o relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="d4b1e-122">O relatório de despesas é atribuído ao coordenador de contas a pagar para lançamento.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="d4b1e-123">Uma das seguintes etapas ocorre, se o lançamento automático for configurado.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="d4b1e-124">Se o lançamento automático for configurado, o relatório de despesas será processado para pagamento e o status do relatório será atualizado.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="d4b1e-125">Se o lançamento automático não for configurado, o coordenador de contas a pagar verificará se todos os recibos originais foram enviados e se eles correspondem às despesas contidas no relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="d4b1e-126">Todos os códigos de imposto inseridos no relatório de despesas também devem ser confirmados como corretos.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="d4b1e-127">Após a verificação desses requisitos, o relatório de despesas será lançado.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="d4b1e-128">Após o lançamento do relatório de despesas, o pagamento do relatório é autorizado e o funcionário é reembolsado.</span><span class="sxs-lookup"><span data-stu-id="d4b1e-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>

