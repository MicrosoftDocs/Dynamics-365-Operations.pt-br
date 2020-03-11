---
title: Gerenciamento de tarefas em PDV
description: Este tópico descreve o gerenciamento de tarefas no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: cc685fcd584fe2ab5cd9282e8fbefbd284d5b2a2
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036777"
---
# <a name="task-management-in-pos"></a><span data-ttu-id="94a52-103">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="94a52-103">Task management in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="94a52-104">Este tópico descreve o gerenciamento de tarefas no aplicativo de ponto de venda (PDV) do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="94a52-104">This topic describes task management in the Microsoft Dynamics 365 Commerce point of sale (POS) application.</span></span>

## <a name="overview"></a><span data-ttu-id="94a52-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="94a52-105">Overview</span></span>

<span data-ttu-id="94a52-106">O aplicativo de PDV Dynamics 365 Commerce tem recursos de gerenciamento de tarefas que permitem que gerentes e funcionários de armazenamento gerenciem tarefas e atualizem o status da tarefa.</span><span class="sxs-lookup"><span data-stu-id="94a52-106">The Dynamics 365 Commerce POS application has task management features that let store managers and workers manage tasks and update task status.</span></span> <span data-ttu-id="94a52-107">Os trabalhadores do armazenamento podem acessar as tarefas selecionando o bloco **Tarefas** na página inicial do PDV ou selecionando notificações de tarefas.</span><span class="sxs-lookup"><span data-stu-id="94a52-107">Store workers can access tasks either by selecting the **Tasks** tile on the POS home page or by selecting task notifications.</span></span> <span data-ttu-id="94a52-108">Por padrão, os trabalhadores da loja são levados para a guia **Minhas tarefas**, na qual eles podem exibir as tarefas atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="94a52-108">By default, store workers are taken to the **My tasks** tab, where they can view the tasks that are assigned to them.</span></span> <span data-ttu-id="94a52-109">No entanto, eles podem alternar facilmente para as guias **Tarefas atrasadas**, **Tarefas abertas** e **Listas de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="94a52-109">However, they can easily switch to the **Overdue tasks**, **Open tasks**, and **Task lists** tabs.</span></span>

## <a name="task-operations-for-store-managers"></a><span data-ttu-id="94a52-110">Operações de tarefas para os gerentes de armazenamento</span><span class="sxs-lookup"><span data-stu-id="94a52-110">Task operations for store managers</span></span>

<span data-ttu-id="94a52-111">Os gerentes de armazenamento podem executar as seguintes operações de tarefas no aplicativo de PDV usando os botões na barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="94a52-111">Store managers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="94a52-112">**Atribuir** – Atribua tarefas selecionadas a um trabalhador de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="94a52-112">**Assign** – Assign selected tasks to a store worker.</span></span>
- <span data-ttu-id="94a52-113">**Status da tarefa** – Altere o status das tarefas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="94a52-113">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="94a52-114">**Filtrar** – Por padrão, somente as tarefas ativas são mostradas.</span><span class="sxs-lookup"><span data-stu-id="94a52-114">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="94a52-115">No entanto, aplicando filtros, os gerentes podem exibir todas as tarefas, até mesmo as que foram concluídas ou canceladas.</span><span class="sxs-lookup"><span data-stu-id="94a52-115">However, by applying filters, managers can view all tasks, even tasks that have been completed or canceled.</span></span>
- <span data-ttu-id="94a52-116">**Nova tarefa** – Cria uma tarefa em uma lista de tarefas existente ou cria uma tarefa de finalidade única.</span><span class="sxs-lookup"><span data-stu-id="94a52-116">**New task** – Create a task under an existing task list, or create an single-purpose task.</span></span>

<span data-ttu-id="94a52-117">Os trabalhadores de armazenamento podem executar as seguintes operações de tarefas no aplicativo de PDV usando os botões na barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="94a52-117">Store workers can perform the following task operations in the POS application by using the buttons on the command bar:</span></span>

- <span data-ttu-id="94a52-118">**Status da tarefa** – Altere o status das tarefas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="94a52-118">**Task status** – Change the status of selected tasks.</span></span>
- <span data-ttu-id="94a52-119">**Filtrar** – Por padrão, somente as tarefas ativas são mostradas.</span><span class="sxs-lookup"><span data-stu-id="94a52-119">**Filter** – By default, only active tasks are shown.</span></span> <span data-ttu-id="94a52-120">No entanto, aplicando filtros, os trabalhadores podem exibir todas as tarefas, até mesmo as que foram concluídas ou canceladas.</span><span class="sxs-lookup"><span data-stu-id="94a52-120">However, by applying filters, workers can view all tasks, even tasks that have been completed or canceled.</span></span>

<span data-ttu-id="94a52-121">A ilustração a seguir mostra a guia **Minhas tarefas** no aplicativo de PDV Commerce.</span><span class="sxs-lookup"><span data-stu-id="94a52-121">The following illustration shows the **My tasks** tab in the Commerce POS application.</span></span>

![Guia Minhas tarefas no aplicativo PDV do Commerce](media/POS-task-management.png)

<span data-ttu-id="94a52-123">A ilustração a seguir mostra a guia **Listas de tarefas**.</span><span class="sxs-lookup"><span data-stu-id="94a52-123">The following illustration shows the **Task lists** tab.</span></span>

![Guia Listas de tarefas no aplicativo PDV do Commerce](media/POS-task-lists-management.png)

## <a name="additional-resources"></a><span data-ttu-id="94a52-125">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="94a52-125">Additional resources</span></span>

[<span data-ttu-id="94a52-126">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="94a52-126">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="94a52-127">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="94a52-127">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="94a52-128">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="94a52-128">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="94a52-129">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="94a52-129">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)
