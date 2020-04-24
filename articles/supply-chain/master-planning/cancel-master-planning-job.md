---
title: Cancelar um trabalho mestre de planejamento
description: Este tópico explica como cancelar um trabalho de planejamento ativo que usa funcionalidade de planejamento integrado.
author: ChristianRytt
manager: tfehr
ms.date: 01/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 08dd612d9fb01ba2db6d4fcc7db9507a41a4b29f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203908"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="1ea1b-103">Cancelar um trabalho mestre de planejamento</span><span class="sxs-lookup"><span data-stu-id="1ea1b-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1ea1b-104">No Microsoft Dynamics 365 Supply Chain Management, há várias opções para cancelar um trabalho de planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="1ea1b-105">Por exemplo, talvez você queira cancelar um trabalho de planejamento mestre se ele tiver sido iniciado por engano ou estiver sendo executado mais tempo do que o esperado e desejar encerrá-lo.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="1ea1b-106">A melhor maneira de cancelar um trabalho de planejamento é a partir da página **Processos de planejamento inacabados**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="1ea1b-107">As opções alternativas das páginas **Trabalhos em lotes** e **Trabalhos em lotes avançados** só devem ser usadas se o cancelamento do trabalho de planejamento mestre da página **Processos de planejamento não concluídos** não tiver sido concluído em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="1ea1b-108">Opção de cancelamento preferencial</span><span class="sxs-lookup"><span data-stu-id="1ea1b-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="1ea1b-109">Cancelar o trabalho de planejamento mestre a partir da página **Processos de planejamento não concluídos**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="1ea1b-110">Vá para **Planejamento mestre > Consultas e relatórios > Planejamento mestre > Processos de planejamento não concluídos**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="1ea1b-111">Selecione a linha com o processo de planejamento que você deseja cancelar.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="1ea1b-112">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="1ea1b-113">Opções de cancelamento adicionais</span><span class="sxs-lookup"><span data-stu-id="1ea1b-113">Additional cancel options</span></span>
<span data-ttu-id="1ea1b-114">Eles devem ser usados somente se o cancelamento do trabalho de planejamento mestre da página **Processos de planejamento não concluídos** não foram concluídas em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="1ea1b-115">Excluir trabalho de planejamento mestre da página **Trabalho em lotes**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="1ea1b-116">Vá para **Administração do sistema > Consultas > Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="1ea1b-117">Selecione a linha com o trabalho de planejamento que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="1ea1b-118">Clique em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="1ea1b-119">Cancelar tarefa de planejamento mestre da página **Trabalho em lotes aprimorado**</span><span class="sxs-lookup"><span data-stu-id="1ea1b-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="1ea1b-120">Vá para **Administração do sistema > Consultas > Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="1ea1b-121">Se a ID do trabalho não for mostrada na lista, clique em **Alterar para formulário avançado**, caso contrário, continue com a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="1ea1b-122">Abrir o trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-122">Open the batch job.</span></span> <span data-ttu-id="1ea1b-123">Clique em **ID de trabalho** para o trabalho em lotes com as tarefas que você deseja encerrar.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="1ea1b-124">Em **Tarefas em lotes**, selecione as tarefas a serem encerradas.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="1ea1b-125">Na guia rápida **Tarefas em lotes** clique em **Anular**.</span><span class="sxs-lookup"><span data-stu-id="1ea1b-125">On the **Batch tasks** FastTab, click **Abort**.</span></span>
