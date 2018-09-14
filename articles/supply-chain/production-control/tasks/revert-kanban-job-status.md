--- 
title: Reverter status do trabalho kanban
description: Esse procedimento se concentra em reverter um status incorreto do trabalho kanban.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 27874f89cede151b52b869fa0d58e320d548e6d3
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="cf53d-103">Reverter status do trabalho kanban</span><span class="sxs-lookup"><span data-stu-id="cf53d-103">Revert kanban job status</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf53d-104">Esse procedimento se concentra em reverter um status incorreto do trabalho kanban.</span><span class="sxs-lookup"><span data-stu-id="cf53d-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="cf53d-105">Isso é útil, se o operador da máquina atualiza o trabalho errado ou define o status errado por engano.</span><span class="sxs-lookup"><span data-stu-id="cf53d-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="cf53d-106">Nesse procedimento, um trabalho kanban é registrado como preparado por engano, e o status é revertido.</span><span class="sxs-lookup"><span data-stu-id="cf53d-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="cf53d-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="cf53d-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="cf53d-108">Esse procedimento se destina ao supervisor de loja ou ao operador de máquina que trabalha em uma empresa de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="cf53d-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="cf53d-109">Abra o quadro de processo para a célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="cf53d-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="cf53d-110">Vá para o quadro kanban para processar trabalhos.</span><span class="sxs-lookup"><span data-stu-id="cf53d-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="cf53d-111">No campo Célula de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cf53d-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="cf53d-112">Selecione a célula de trabalho 1260.</span><span class="sxs-lookup"><span data-stu-id="cf53d-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="cf53d-113">Prepare o trabalho kanban</span><span class="sxs-lookup"><span data-stu-id="cf53d-113">Prepare kanban job</span></span>
1. <span data-ttu-id="cf53d-114">Clique em Preparar.</span><span class="sxs-lookup"><span data-stu-id="cf53d-114">Click Prepare.</span></span>
    * <span data-ttu-id="cf53d-115">Se você não puder clicar em Preparar porque está esmaecida, certifique-se de que o trabalho kanban selecionado tem o status Planejado, que é indicado pelo ícone vazio de kanban.</span><span class="sxs-lookup"><span data-stu-id="cf53d-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="cf53d-116">Se a opção Preparar falhar, certifique-se de que todos os materiais da Lista de separação estarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="cf53d-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="cf53d-117">Na lista, selecione o trabalho preparado.</span><span class="sxs-lookup"><span data-stu-id="cf53d-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="cf53d-118">Selecione o primeiro trabalho que você acabou de preparar.</span><span class="sxs-lookup"><span data-stu-id="cf53d-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="cf53d-119">Observe que os status dos trabalhos são preparados, que é indicado com um triângulo no ícone do kanban.</span><span class="sxs-lookup"><span data-stu-id="cf53d-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="cf53d-120">Reverta o status do trabalho kanban preparado</span><span class="sxs-lookup"><span data-stu-id="cf53d-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="cf53d-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf53d-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="cf53d-122">Selecione o primeiro trabalho que você preparou.</span><span class="sxs-lookup"><span data-stu-id="cf53d-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="cf53d-123">No painel de Ação, clique em Fabricar.</span><span class="sxs-lookup"><span data-stu-id="cf53d-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="cf53d-124">Clique em Reverter status.</span><span class="sxs-lookup"><span data-stu-id="cf53d-124">Click Revert status.</span></span>
    * <span data-ttu-id="cf53d-125">Você pode usar uma regra kanban alternativa quando as seguintes condições forem verdadeiras: - a estratégia de reabastecimento é a mesma para ambas as regras.</span><span class="sxs-lookup"><span data-stu-id="cf53d-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="cf53d-126">- A versão do fluxo de produção for a mesma para ambas as regras.</span><span class="sxs-lookup"><span data-stu-id="cf53d-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="cf53d-127">- O produto que for fornecido for o mesmo para ambas as regras.</span><span class="sxs-lookup"><span data-stu-id="cf53d-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="cf53d-128">- Todas as atividades downstream que estão configuradas para a última atividade das regras kanban devem ser iguais para ambas as regras.</span><span class="sxs-lookup"><span data-stu-id="cf53d-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="cf53d-129">- As mesmas dimensões de estoque fornecidas devem ser configuradas para ambas as regras.</span><span class="sxs-lookup"><span data-stu-id="cf53d-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="cf53d-130">- O status da unidade de manuseio de material Não deve ser atribuído.</span><span class="sxs-lookup"><span data-stu-id="cf53d-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="cf53d-131">- A configuração de kanbans de evento deve ser a mesma.</span><span class="sxs-lookup"><span data-stu-id="cf53d-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="cf53d-132">Verifique se o novo status é Planejado.</span><span class="sxs-lookup"><span data-stu-id="cf53d-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="cf53d-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cf53d-133">Click OK.</span></span>
5. <span data-ttu-id="cf53d-134">Na lista, desmarque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cf53d-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="cf53d-135">Selecione o mesmo trabalho.</span><span class="sxs-lookup"><span data-stu-id="cf53d-135">Select the same job.</span></span>  
    * <span data-ttu-id="cf53d-136">Observe que o status do trabalho para o trabalho kanban será revertido para Planejado, que é indicado por um ícone kanban vazio.</span><span class="sxs-lookup"><span data-stu-id="cf53d-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  


