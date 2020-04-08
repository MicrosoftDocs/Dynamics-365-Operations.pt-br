---
title: Criar um trabalho em lotes
description: Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6eee5c6dd7daf2b0c79dd34d15a7dde919bdd60
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143664"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="a4d55-103">Criar um trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="a4d55-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4d55-104">Um trabalho em lotes é um grupo de tarefas que são enviadas para uma instância do Application Object Server (AOS) para processamento automático.</span><span class="sxs-lookup"><span data-stu-id="a4d55-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="a4d55-105">Os trabalhos em lotes são executados usando as credenciais de segurança do usuário que criou o trabalho.</span><span class="sxs-lookup"><span data-stu-id="a4d55-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="a4d55-106">Use o procedimento a seguir para criar um trabalho de lote.</span><span class="sxs-lookup"><span data-stu-id="a4d55-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="a4d55-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="a4d55-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="a4d55-108">Criar o trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="a4d55-108">Create the batch job</span></span>
1. <span data-ttu-id="a4d55-109">Vá para **Painel de navegação > Módulos > Administração do sistema > Consultas > Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="a4d55-110">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-110">Click **New**.</span></span>
3. <span data-ttu-id="a4d55-111">No campo **Descrição do trabalho**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="a4d55-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="a4d55-112">No campo **Data/hora inicial agendada**, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="a4d55-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="a4d55-113">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="a4d55-114">Criar uma recorrência</span><span class="sxs-lookup"><span data-stu-id="a4d55-114">Create a recurrence</span></span>
1. <span data-ttu-id="a4d55-115">No Painel de Ação, clique em **Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="a4d55-116">Clique em **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-116">Click **Recurrence**.</span></span> <span data-ttu-id="a4d55-117">Use estas opções para inserir um intervalo e um padrão para a recorrência.</span><span class="sxs-lookup"><span data-stu-id="a4d55-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="a4d55-118">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="a4d55-119">Adicionar alertas</span><span class="sxs-lookup"><span data-stu-id="a4d55-119">Add alerts</span></span>
1. <span data-ttu-id="a4d55-120">No Painel de Ação, clique em **Trabalho em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="a4d55-121">Clique em **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-121">Click **Alerts**.</span></span> <span data-ttu-id="a4d55-122">Indique se você quer que mensagens de alertas sejam enviadas quando as extremidades do trabalho de grupo, tiverem um erro ou forem canceladas.</span><span class="sxs-lookup"><span data-stu-id="a4d55-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="a4d55-123">Especifique então se você quer que os alertas indiquem como mensagens pop-up.</span><span class="sxs-lookup"><span data-stu-id="a4d55-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="a4d55-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="a4d55-125">Ajuste o status de trabalho em lotes</span><span class="sxs-lookup"><span data-stu-id="a4d55-125">Adjust batch job status</span></span>
1. <span data-ttu-id="a4d55-126">Vá para **Administração do sistema > Consultas > Trabalhos em lotes**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="a4d55-127">Selecione o trabalho em lotes apropriado.</span><span class="sxs-lookup"><span data-stu-id="a4d55-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="a4d55-128">No Painel de Ação, clique em **Trabalho em lotes > Funções > Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="a4d55-129">Selecione o status apropriado:</span><span class="sxs-lookup"><span data-stu-id="a4d55-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="a4d55-130">**Reter**: definir o trabalho em lotes como **reter** para que seja retido do agendador de trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="a4d55-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="a4d55-131">Equivalente a *parar*.</span><span class="sxs-lookup"><span data-stu-id="a4d55-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="a4d55-132">**Aguardar**: definir o trabalho em lotes como **aguardar** para que aguarde para ser retirado pelo agendador de trabalho em lotes.</span><span class="sxs-lookup"><span data-stu-id="a4d55-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="a4d55-133">Equivalente a *ir*.</span><span class="sxs-lookup"><span data-stu-id="a4d55-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="a4d55-134">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a4d55-134">Click **OK**.</span></span>
