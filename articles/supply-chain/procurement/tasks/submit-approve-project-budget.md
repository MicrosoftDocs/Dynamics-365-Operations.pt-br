---
title: Enviar e aprovar orçamento de projeto
description: Este procedimento mostra como criar e enviar o orçamento para um projeto.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f727e19d3f8c424b1c59e52602b7e907151f4492
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569836"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="be44e-103">Enviar e aprovar orçamento de projeto</span><span class="sxs-lookup"><span data-stu-id="be44e-103">Submit and approve project budget</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="be44e-104">Este procedimento mostra como criar e enviar o orçamento para um projeto.</span><span class="sxs-lookup"><span data-stu-id="be44e-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="be44e-105">Quando você cria um orçamento do projeto, você pode inserir receitas e custos estimados para um projeto e, em seguida, usá-los para controlar as transações reais do projeto.</span><span class="sxs-lookup"><span data-stu-id="be44e-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="be44e-106">No orçamento do projeto, todos os orçamentos originais e revisões devem ser enviados ao fluxo de trabalho do projeto para aprovação.</span><span class="sxs-lookup"><span data-stu-id="be44e-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="be44e-107">O fluxo de trabalho oferece maior controle sobre o processo e cria um registro de histórico de alteração.</span><span class="sxs-lookup"><span data-stu-id="be44e-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="be44e-108">Essa tarefa foi criada usando o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="be44e-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="be44e-109">Vá para Gerenciamento e contabilidade de projeto > Projetos > Todos os projetos.</span><span class="sxs-lookup"><span data-stu-id="be44e-109">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="be44e-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="be44e-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="be44e-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="be44e-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="be44e-112">No Painel de Ação, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="be44e-112">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="be44e-113">Clique em Orçamento do projeto.</span><span class="sxs-lookup"><span data-stu-id="be44e-113">Click Project budget.</span></span>
6. <span data-ttu-id="be44e-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="be44e-114">In the Description field, type a value.</span></span>
7. <span data-ttu-id="be44e-115">Expanda a seção Custos</span><span class="sxs-lookup"><span data-stu-id="be44e-115">Expand the Cost section</span></span>
8. <span data-ttu-id="be44e-116">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="be44e-116">Click New.</span></span>
9. <span data-ttu-id="be44e-117">No campo Tipo de transação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="be44e-117">In the Transaction type field, select an option.</span></span>
10. <span data-ttu-id="be44e-118">No campo Categoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="be44e-118">In the Category field, enter or select a value.</span></span>
11. <span data-ttu-id="be44e-119">No campo Orçamento original, insira um número.</span><span class="sxs-lookup"><span data-stu-id="be44e-119">In the Original budget field, enter a number.</span></span>
12. <span data-ttu-id="be44e-120">Expanda a seção Receitas.</span><span class="sxs-lookup"><span data-stu-id="be44e-120">Expand the Revenues section.</span></span>
13. <span data-ttu-id="be44e-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="be44e-121">Click New.</span></span>
14. <span data-ttu-id="be44e-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="be44e-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="be44e-123">No campo Tipo de transação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="be44e-123">In the Transaction type field, select an option.</span></span>
16. <span data-ttu-id="be44e-124">No campo Categoria, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="be44e-124">In the Category field, enter or select a value.</span></span>
17. <span data-ttu-id="be44e-125">No campo Orçamento original, insira um número.</span><span class="sxs-lookup"><span data-stu-id="be44e-125">In the Original budget field, enter a number.</span></span>
18. <span data-ttu-id="be44e-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="be44e-126">Click Save.</span></span>
19. <span data-ttu-id="be44e-127">Clique em Fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="be44e-127">Click Workflow.</span></span>
20. <span data-ttu-id="be44e-128">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="be44e-128">Click Submit.</span></span>
21. <span data-ttu-id="be44e-129">No campo Comentário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="be44e-129">In the Comment field, type a value.</span></span>
22. <span data-ttu-id="be44e-130">Clique em Enviar.</span><span class="sxs-lookup"><span data-stu-id="be44e-130">Click Submit.</span></span>

