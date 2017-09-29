--- 
title: Criar um trabalho em lotes
description: "Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 31c8e2ba87ef8c17a3147e1159104585258d4164
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-batch-job"></a><span data-ttu-id="e06e7-103">Criar um trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="e06e7-103">Create a batch job</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e06e7-104">Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático.</span><span class="sxs-lookup"><span data-stu-id="e06e7-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="e06e7-105">Os trabalhos em lotes são executados usando as credenciais de segurança do usuário que criou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e06e7-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="e06e7-106">Use o procedimento a seguir para criar um trabalho de lote.</span><span class="sxs-lookup"><span data-stu-id="e06e7-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="e06e7-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e06e7-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="e06e7-108">Criar o trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="e06e7-108">Create the batch job</span></span>
1. <span data-ttu-id="e06e7-109">Vá para Administração do sistema > Consultas > Trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="e06e7-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="e06e7-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e06e7-110">Click New.</span></span>
3. <span data-ttu-id="e06e7-111">No campo Descrição do trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e06e7-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="e06e7-112">No campo Data/hora inicial agendada, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="e06e7-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="e06e7-113">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e06e7-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="e06e7-114">Criar uma recorrência</span><span class="sxs-lookup"><span data-stu-id="e06e7-114">Create a recurrence</span></span>
1. <span data-ttu-id="e06e7-115">No Painel de Ação, clique em Trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="e06e7-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e06e7-116">Clique em Recorrência.</span><span class="sxs-lookup"><span data-stu-id="e06e7-116">Click Recurrence.</span></span>
    * <span data-ttu-id="e06e7-117">Use estas opções para inserir um intervalo e um padrão para a recorrência.</span><span class="sxs-lookup"><span data-stu-id="e06e7-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="e06e7-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e06e7-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="e06e7-119">Adicionar alertas</span><span class="sxs-lookup"><span data-stu-id="e06e7-119">Add alerts</span></span>
1. <span data-ttu-id="e06e7-120">No Painel de Ação, clique em Trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="e06e7-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="e06e7-121">Clique em Alertas.</span><span class="sxs-lookup"><span data-stu-id="e06e7-121">Click Alerts.</span></span>
    * <span data-ttu-id="e06e7-122">Indique se você quer que mensagens de alertas sejam enviadas quando as extremidades do trabalho de grupo, tiverem um erro ou forem canceladas.</span><span class="sxs-lookup"><span data-stu-id="e06e7-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="e06e7-123">Especifique então se você quer que os alertas indiquem como mensagens pop-up.</span><span class="sxs-lookup"><span data-stu-id="e06e7-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="e06e7-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e06e7-124">Click OK.</span></span>


