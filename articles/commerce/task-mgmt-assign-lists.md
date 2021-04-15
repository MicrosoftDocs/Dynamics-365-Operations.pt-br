---
title: Atribuir listas de tarefas a lojas ou funcionários
description: Este tópico descreve como atribuir listas de tarefas a lojas ou funcionários no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 0c4f028367c894c54392963ffc4f6a0f0c04c03a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795252"
---
# <a name="assign-task-lists-to-stores-or-employees"></a><span data-ttu-id="f0f60-103">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="f0f60-103">Assign task lists to stores or employees</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0f60-104">Este tópico descreve como atribuir listas de tarefas a lojas ou funcionários no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0f60-104">This topic describes how to assign task lists to stores or employees in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f0f60-105">O gerenciamento de tarefas no Dynamics 365 Commerce permite atribuir uma lista de tarefas a vários armazenamentos ou funcionários, ou a uma combinação de lojas e funcionários.</span><span class="sxs-lookup"><span data-stu-id="f0f60-105">Task management in Dynamics 365 Commerce lets you assign a task list to multiple stores or employees, or to a combination of stores and employees.</span></span> <span data-ttu-id="f0f60-106">Por exemplo, um gerente regional de 20 lojas pode desejar atribuir a lista de tarefas **Preparação para o período de festas** a todas as 20 lojas.</span><span class="sxs-lookup"><span data-stu-id="f0f60-106">For example, a regional manager for 20 stores might want to assign the **Holiday season preparation** task list to all 20 stores.</span></span>

## <a name="start-the-task-list-assignment-process"></a><span data-ttu-id="f0f60-107">Iniciar o processo de atribuição da lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0f60-107">Start the task list assignment process</span></span>

<span data-ttu-id="f0f60-108">Para iniciar o processo de atribuição de uma lista de tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0f60-108">To start the process of assigning a task list, follow these steps.</span></span>

1. <span data-ttu-id="f0f60-109">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-109">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="f0f60-110">Selecione a lista de tarefas a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="f0f60-110">Select the task list to assign.</span></span>
1. <span data-ttu-id="f0f60-111">Selecione **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-111">Select **Start process**.</span></span>
1. <span data-ttu-id="f0f60-112">Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome (por exemplo, **Lojas da região leste**).</span><span class="sxs-lookup"><span data-stu-id="f0f60-112">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name (for example, **East region stores**).</span></span>
1. <span data-ttu-id="f0f60-113">No campo **Data de destino**, especifique uma data.</span><span class="sxs-lookup"><span data-stu-id="f0f60-113">In the **Target date** field, specify a date.</span></span>
1. <span data-ttu-id="f0f60-114">Para atribuir a lista de tarefas às lojas, na guia **Lojas**, use o filtro **Hierarquia da organização** para localizar e selecionar os armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="f0f60-114">To assign the task list to stores, on the **Stores** tab, use the **Organization hierarchy** filter to find and select the stores.</span></span>

    <span data-ttu-id="f0f60-115">Para atribuir a lista de tarefas aos funcionários, na guia **trabalhadores**, localize e selecione os funcionários.</span><span class="sxs-lookup"><span data-stu-id="f0f60-115">To assign the task list to employees, on the **Workers** tab, find and select the employees.</span></span>

1. <span data-ttu-id="f0f60-116">Selecione **OK** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="f0f60-116">Select **OK** to start the process.</span></span> <span data-ttu-id="f0f60-117">A lista de tarefas é atribuída às lojas ou aos funcionários selecionados.</span><span class="sxs-lookup"><span data-stu-id="f0f60-117">The tasks list is assigned to the selected stores or employees.</span></span>

<span data-ttu-id="f0f60-118">A ilustração a seguir mostra um exemplo de como localizar e selecionar armazenamentos na caixa de diálogo **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-118">The following illustration shows an example of how to find and select stores in the **Start process** dialog box.</span></span>

![Localizando e selecionando armazenamentos na caixa de diálogo Iniciar processo](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a><span data-ttu-id="f0f60-120">Atribuir listas de tarefas em uma base recorrente</span><span class="sxs-lookup"><span data-stu-id="f0f60-120">Assign task lists on a recurring basis</span></span>

<span data-ttu-id="f0f60-121">Às vezes varejistas têm tarefas recorrentes, como "lista de verificação de feriados da quinta-feira" ou "primeiro dia do mês".</span><span class="sxs-lookup"><span data-stu-id="f0f60-121">Retailer sometimes have recurrent tasks, such as "Thursday closure checklist" or "First day of the month checklist."</span></span> <span data-ttu-id="f0f60-122">Portanto, eles podem desejar atribuir a lista de tarefas em uma base recorrente.</span><span class="sxs-lookup"><span data-stu-id="f0f60-122">Therefore, they might want to assign the task list on a recurring basis.</span></span>

1. <span data-ttu-id="f0f60-123">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Administração de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-123">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="f0f60-124">Selecione a lista de tarefas a ser atribuída.</span><span class="sxs-lookup"><span data-stu-id="f0f60-124">Select the task list to assign.</span></span>
1. <span data-ttu-id="f0f60-125">Selecione **Iniciar processo**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-125">Select **Start process**.</span></span>
1. <span data-ttu-id="f0f60-126">Na caixa de diálogo **Iniciar processo**, na guia **Geral**, no campo **Nome do processo**, digite um nome.</span><span class="sxs-lookup"><span data-stu-id="f0f60-126">In the **Start process** dialog box, on the **General** tab, in the **Process name** field, enter a name.</span></span>
1. <span data-ttu-id="f0f60-127">Defina a opção **Recorrência** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-127">Set the **Recurrence** option to **Yes**.</span></span>
1. <span data-ttu-id="f0f60-128">No campo **Deslocamento de data de destino recorrente em dias**, insira um número de dias.</span><span class="sxs-lookup"><span data-stu-id="f0f60-128">In the **Recurrence target date offset in days** field, enter a number of days.</span></span> <span data-ttu-id="f0f60-129">Por exemplo, se você inserir **4**, a data de destino será a data de recorrência mais quatro dias.</span><span class="sxs-lookup"><span data-stu-id="f0f60-129">For example, if you enter **4**, the target date is the recurrence date plus four days.</span></span>
1. <span data-ttu-id="f0f60-130">Na guia **Executar em segundo plano**, selecione **Recorrência**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-130">On the **Run in the background** tab, select **Recurrence**.</span></span>
1. <span data-ttu-id="f0f60-131">Na caixa de diálogo **Definir recorrência**, insira os critérios de frequência e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-131">In the **Define recurrence** dialog box, enter the frequency criteria, and then select **OK**.</span></span>

<span data-ttu-id="f0f60-132">A ilustração a seguir mostra um exemplo de como inserir critérios de frequência na caixa de diálogo **Definir recorrência**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-132">The following illustration shows an example of how to enter frequency criteria in the **Define recurrence** dialog box.</span></span>

![Inserindo critérios de frequência na caixa de diálogo Definir recorrência](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a><span data-ttu-id="f0f60-134">Rastrear status da lista de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0f60-134">Track task list status</span></span>

<span data-ttu-id="f0f60-135">Se você for gerente regional ou gerente de armazenamento, talvez queira rastrear o status das listas de tarefas que foram atribuídas a vários armazenamentos ou funcionários.</span><span class="sxs-lookup"><span data-stu-id="f0f60-135">If you're a regional manager or store manager, you might want to track the status of task lists that have been assigned to multiple stores or employees.</span></span> <span data-ttu-id="f0f60-136">Em seguida, você poderá acompanhar os armazenamentos ou trabalhadores que não concluíram as tarefas atribuídas no tempo.</span><span class="sxs-lookup"><span data-stu-id="f0f60-136">You can then follow up with stores or workers that didn't complete their assigned tasks on time.</span></span> <span data-ttu-id="f0f60-137">O back-office do Commerce permite que você exiba o status das listas de tarefas, reatribua tarefas ou altere o status de uma tarefa.</span><span class="sxs-lookup"><span data-stu-id="f0f60-137">Commerce back office lets you view the status of task lists, reassign tasks, or change the status of a task.</span></span>

<span data-ttu-id="f0f60-138">Para rastrear o status da lista de tarefas de todas as tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0f60-138">To track the task list status for all tasks, follow these steps.</span></span>

1. <span data-ttu-id="f0f60-139">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-139">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="f0f60-140">Selecione a guia **Todas as listas de tarefas** para exibir o status de todas as listas de tarefas atribuídas a vários armazenamentos.</span><span class="sxs-lookup"><span data-stu-id="f0f60-140">Select the **All task lists** tab to view the status of all task lists that are assigned to various stores.</span></span>

<span data-ttu-id="f0f60-141">Para rastrear o status da lista de tarefas de todas as tarefas atribuídas a você, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0f60-141">To track the task list status for all tasks that are assigned to you, follow these steps.</span></span>

1. <span data-ttu-id="f0f60-142">Vá para **Retail e Commerce \> Gerenciamento de tarefas \> Processos de gerenciamento de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="f0f60-142">Go to **Retail and Commerce \> Task management \> Task management processes**.</span></span>
1. <span data-ttu-id="f0f60-143">Selecione a guia **Minhas tarefas** ou **Todas as tarefas** para exibir ou atualizar o status das tarefas atribuídas a você.</span><span class="sxs-lookup"><span data-stu-id="f0f60-143">Select the **My tasks** or **All tasks** tab to view or update the status of tasks that are assigned to you.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0f60-144">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f0f60-144">Additional resources</span></span>

[<span data-ttu-id="f0f60-145">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0f60-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="f0f60-146">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0f60-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="f0f60-147">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="f0f60-147">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="f0f60-148">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="f0f60-148">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
