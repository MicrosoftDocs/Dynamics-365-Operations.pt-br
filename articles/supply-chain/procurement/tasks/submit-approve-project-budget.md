---
title: Enviar e aprovar orçamento de projeto
description: Este procedimento mostra como criar e enviar o orçamento para um projeto.
author: mkirknel
manager: tfehr
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjBudget, WorkflowSubmitDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 14683554c45db72061ecbbf4a528656df3132692
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207431"
---
# <a name="submit-and-approve-project-budget"></a><span data-ttu-id="52842-103">Enviar e aprovar orçamento de projeto</span><span class="sxs-lookup"><span data-stu-id="52842-103">Submit and approve project budget</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="52842-104">Este procedimento mostra como criar e enviar o orçamento para um projeto.</span><span class="sxs-lookup"><span data-stu-id="52842-104">This procedure shows you how to create and submit the budget for a project.</span></span> 

<span data-ttu-id="52842-105">Quando você cria um orçamento do projeto, você pode inserir receitas e custos estimados para um projeto e, em seguida, usá-los para controlar as transações reais do projeto.</span><span class="sxs-lookup"><span data-stu-id="52842-105">When you create a project budget, you can enter estimated revenues and costs for a project, and then use those to control actual project transactions.</span></span> <span data-ttu-id="52842-106">No orçamento do projeto, todos os orçamentos originais e revisões devem ser enviados ao fluxo de trabalho do projeto para aprovação.</span><span class="sxs-lookup"><span data-stu-id="52842-106">In project budgeting, all original budgets and revisions must be sent to project workflow for approval.</span></span> <span data-ttu-id="52842-107">O fluxo de trabalho oferece maior controle sobre o processo e cria um registro de histórico de alteração.</span><span class="sxs-lookup"><span data-stu-id="52842-107">Workflow gives you increased control over the process and creates a change history record.</span></span>

<span data-ttu-id="52842-108">Essa tarefa foi criada usando o conjunto de dados de USSI.</span><span class="sxs-lookup"><span data-stu-id="52842-108">This task was created using the USSI data set.</span></span>

1. <span data-ttu-id="52842-109">No **Painel de navegação**, acesse **Módulos > Gerenciamento e contabilidade do projeto > Projetos > Todos os projetos**.</span><span class="sxs-lookup"><span data-stu-id="52842-109">In the **Navigation pane**, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="52842-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="52842-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="52842-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="52842-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="52842-112">No **Painel de Ação**, clique em **Plano**.</span><span class="sxs-lookup"><span data-stu-id="52842-112">On the **Action Pane**, click **Plan**.</span></span>
5. <span data-ttu-id="52842-113">Clique em **Orçamento do projeto**.</span><span class="sxs-lookup"><span data-stu-id="52842-113">Click **Project budget**.</span></span>
6. <span data-ttu-id="52842-114">No campo **Descrição**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="52842-114">In the **Description** field, type a value.</span></span>
7. <span data-ttu-id="52842-115">Expanda a Guia Rápida **Custo**.</span><span class="sxs-lookup"><span data-stu-id="52842-115">Expand the **Cost** fastTab.</span></span>
8. <span data-ttu-id="52842-116">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="52842-116">Click **New**.</span></span>
9. <span data-ttu-id="52842-117">No campo **Tipo de transação**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="52842-117">In the **Transaction type** field, select an option.</span></span>
10. <span data-ttu-id="52842-118">No campo **Categoria**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="52842-118">In the **Category** field, enter or select a value.</span></span>
11. <span data-ttu-id="52842-119">No campo **Orçamento original**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="52842-119">In the **Original budget** field, enter a number.</span></span>
12. <span data-ttu-id="52842-120">Expanda a Guia Rápida **Receitas**.</span><span class="sxs-lookup"><span data-stu-id="52842-120">Expand the **Revenues** fastTab.</span></span>
13. <span data-ttu-id="52842-121">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="52842-121">Click **New**.</span></span>
14. <span data-ttu-id="52842-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="52842-122">In the list, mark the selected row.</span></span>
15. <span data-ttu-id="52842-123">No campo **Tipo de transação**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="52842-123">In the **Transaction type** field, select an option.</span></span>
16. <span data-ttu-id="52842-124">No campo **Categoria**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="52842-124">In the **Category** field, enter or select a value.</span></span>
17. <span data-ttu-id="52842-125">No campo **Orçamento original**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="52842-125">In the **Original budget** field, enter a number.</span></span>
18. <span data-ttu-id="52842-126">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="52842-126">Click **Save**.</span></span>
19. <span data-ttu-id="52842-127">Clique em **Fluxo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="52842-127">Click **Workflow**.</span></span>
20. <span data-ttu-id="52842-128">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="52842-128">Click **Submit**.</span></span>
21. <span data-ttu-id="52842-129">No campo **Comentário**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="52842-129">In the **Comment** field, type a value.</span></span>
22. <span data-ttu-id="52842-130">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="52842-130">Click **Submit**.</span></span>

