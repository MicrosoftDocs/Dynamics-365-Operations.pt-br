---
title: Atribuir listas de tarefas a lojas ou funcionários
description: Este tópico descreve como atribuir listas de tarefas a lojas ou funcionários no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ee924f5bf95d47814e7ca09b392a3d10b5e9b9dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006251"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="4ce47-103">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="4ce47-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4ce47-104">Este tópico descreve como atribuir listas de tarefas a lojas ou funcionários no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4ce47-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="4ce47-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="4ce47-105">Overview</span></span>

<span data-ttu-id="4ce47-106">O gerenciamento de tarefas no Dynamics 365 Commerce permite atribuir uma lista de tarefas a vários armazenamentos ou funcionários, ou a uma combinação de lojas e funcionários.</span><span class="sxs-lookup"><span data-stu-id="4ce47-106">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="4ce47-107">Por exemplo, um gerente regional de 20 lojas pode desejar atribuir a lista de tarefas **Preparação para o período de festas** a todas as 20 lojas.</span><span class="sxs-lookup"><span data-stu-id="4ce47-107">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="4ce47-108">Iniciar o processo de atribuição da lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="4ce47-108">Start the task list assignment process</span></span>

<span data-ttu-id="4ce47-109">Para iniciar o processo de atribuição de uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4ce47-109">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="4ce47-110">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-110">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="4ce47-111">Selecione a lista de tarefas a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="4ce47-111">Select the task list to assign.</span></span>
1. <span data-ttu-id="4ce47-112">Selecione **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-112">Select **Start process**.</span></span>
1. <span data-ttu-id="4ce47-113">Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome (por exemplo, **Lojas da região leste**).</span><span class="sxs-lookup"><span data-stu-id="4ce47-113">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="4ce47-114">No campo **Data de destino**, especifique uma data.</span><span class="sxs-lookup"><span data-stu-id="4ce47-114">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="4ce47-115">Para atribuir a lista de tarefas às lojas, na guia **Lojas**, use o filtro **Hierarquia da organização** para localizar e selecionar os armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="4ce47-115">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="4ce47-116">Para atribuir a lista de tarefas aos funcionários, na guia **trabalhadores**, localize e selecione os funcionários.</span><span class="sxs-lookup"><span data-stu-id="4ce47-116">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="4ce47-117">Selecione **OK** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="4ce47-117">Select **OK** to start the process.</span></span> <span data-ttu-id="4ce47-118">A lista de tarefas é atribuída às lojas ou aos funcionários selecionados.</span><span class="sxs-lookup"><span data-stu-id="4ce47-118">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="4ce47-119">A ilustração a seguir mostra um exemplo de como localizar e selecionar armazenamentos na caixa de diálogo **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-119">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Localizando e selecionando armazenamentos na caixa de diálogo Iniciar processo](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="4ce47-121">Atribuir listas de tarefas em uma base recorrente</span><span class="sxs-lookup"><span data-stu-id="4ce47-121">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="4ce47-122">Às vezes varejistas têm tarefas recorrentes, como "lista de verificação de feriados da quinta-feira" ou "primeiro dia do mês".</span><span class="sxs-lookup"><span data-stu-id="4ce47-122">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="4ce47-123">Portanto, eles podem desejar atribuir a lista de tarefas em uma base recorrente.</span><span class="sxs-lookup"><span data-stu-id="4ce47-123">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="4ce47-124">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-124">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="4ce47-125">Selecione a lista de tarefas a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="4ce47-125">Select the task list to assign.</span></span>
1. <span data-ttu-id="4ce47-126">Selecione **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-126">Select **Start process**.</span></span>
1. <span data-ttu-id="4ce47-127">Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome.</span><span class="sxs-lookup"><span data-stu-id="4ce47-127">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="4ce47-128">Defina a opção **Recorrência** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-128">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="4ce47-129">No campo **Deslocamento de data de destino recorrente em dias**, insira um número de dias.</span><span class="sxs-lookup"><span data-stu-id="4ce47-129">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="4ce47-130">Por exemplo, se você inserir **4**, a data de destino será a data de recorrência mais quatro dias.</span><span class="sxs-lookup"><span data-stu-id="4ce47-130">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="4ce47-131">Na guia **Executar em segundo plano**, selecione **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-131">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="4ce47-132">Na caixa de diálogo **Definir recorrência**, insira os critérios de frequência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-132">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="4ce47-133">A ilustração a seguir mostra um exemplo de como inserir critérios de frequência na caixa de diálogo **Definir recorrência**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-133">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Inserindo critérios de frequência na caixa de diálogo Definir recorrência](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="4ce47-135">Rastrear status da lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="4ce47-135">Track task list status</span></span>

<span data-ttu-id="4ce47-136">Se você for gerente regional ou gerente de armazenamento, talvez queira rastrear o status das listas de tarefas que foram atribuídas a vários armazenamentos ou funcionários.</span><span class="sxs-lookup"><span data-stu-id="4ce47-136">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="4ce47-137">Em seguida, você poderá acompanhar os armazenamentos ou trabalhadores que não concluíram as tarefas atribuídas no tempo.</span><span class="sxs-lookup"><span data-stu-id="4ce47-137">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="4ce47-138">O back-office do Commerce permite que você exiba o status das listas de tarefas, reatribua tarefas ou altere o status de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="4ce47-138">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="4ce47-139">Para rastrear o status da lista de tarefas de todas as tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4ce47-139">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="4ce47-140">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-140">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="4ce47-141">Selecione a guia **Todas as listas de tarefas** para exibir o status de todas as listas de tarefas atribuídas a vários armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="4ce47-141">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="4ce47-142">Para rastrear o status da lista de tarefas de todas as tarefas atribuídas a você, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4ce47-142">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="4ce47-143">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="4ce47-143">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="4ce47-144">Selecione a guia **Minhas tarefas** ou **Todas as tarefas** para exibir ou atualizar o status das tarefas atribuídas a você.</span><span class="sxs-lookup"><span data-stu-id="4ce47-144">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4ce47-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4ce47-145">Additional resources</span></span>

[<span data-ttu-id="4ce47-146">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="4ce47-146">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="4ce47-147">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="4ce47-147">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="4ce47-148">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="4ce47-148">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="4ce47-149">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="4ce47-149">Task management in POS</span></span>](task-mgmt-POS.md)
