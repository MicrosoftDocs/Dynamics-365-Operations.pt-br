---
title: Como sincronizar tarefas do projeto a partir do Project Service Automation
description: "Este tópico descreve o modelo e a tarefa subjacente usada para sincronizar tarefas do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 399b519ab0da4de405aeb06f3e7f4bf29a6c5cc3
ms.openlocfilehash: 89df0d99d780441ad08cd6bff3e1fd203694eb8e
ms.contentlocale: pt-br
ms.lasthandoff: 05/30/2018

---

# <a name="synchronize-project-tasks-from-project-service-automation-directly-to-project-activities-in-finance-and-operations"></a><span data-ttu-id="f9963-103">Sincronizar tarefas de projeto do Project Service Automation diretamente para atividades de projeto do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-103">Synchronize project tasks from Project Service Automation directly to project activities in Finance and Operations</span></span>

<span data-ttu-id="f9963-104">Este tópico descreve o modelo e a tarefa subjacente usada para sincronizar tarefas do projeto diretamente do Microsoft Dynamics 365 for Project Service Automation para o Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-104">This topic describes the template and underlying task that is used to synchronize project tasks directly from Microsoft Dynamics 365 for Project Service Automation to Dynamics 365 for Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="f9963-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis no Dynamics 365 for Finance and Operations versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="f9963-105">Project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking is available in Dynamics 365 for Finance and Operations version 8.0.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="f9963-106">Fluxo de dados do Project Service Automation para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f9963-106">Data flow for Project Service Automation to Finance and Operations</span></span>

<span data-ttu-id="f9963-107">A solução de integração do Project Service Automation para o Finance and Operations utiliza o recurso Integração de dados para sincronizar dados nas instâncias do Project Service Automation e do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-107">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance and Operations.</span></span> <span data-ttu-id="f9963-108">O modelo de integração disponível com o recurso Integração de dados permite o fluxo de dados sobre tarefas de projeto do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-108">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="f9963-109">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-109">The following illustration shows how the data is synchronized between Project Service Automation and Finance and Operations.</span></span>

<span data-ttu-id="f9963-110">[![Fluxo de dados da integração do Project Service Automation com o Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="f9963-110">[![Data flow for Project Service Automation integration with Finance and Operations](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="f9963-111">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="f9963-111">Template and task</span></span>

<span data-ttu-id="f9963-112">Para acessar o modelo, no Centro de administração do Microsoft PowerApps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="f9963-112">To access the template, in the Microsoft PowerApps Admin Center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="f9963-113">O seguinte modelo e a tarefa subjacente são usados para sincronizar tarefas do projeto do Project Service Automation para o Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="f9963-113">The following template and underlying task is used to synchronize project tasks from Project Service Automation to Finance and Operations:</span></span>

<span data-ttu-id="f9963-114">-**Nome do modelo na Integração de dados:** tarefas do projeto (PSA para Fin and Ops) -**Nome da tarefa no projeto:** tarefas do projeto</span><span class="sxs-lookup"><span data-stu-id="f9963-114">-**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops) -**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="f9963-115">Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.</span><span class="sxs-lookup"><span data-stu-id="f9963-115">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="f9963-116">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="f9963-116">Entity set</span></span>

|<span data-ttu-id="f9963-117">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="f9963-117">Project Service Automation</span></span>               | <span data-ttu-id="f9963-118">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f9963-118">Finance and Operations</span></span>                |
|-----------------------------------------|---------------------------------------|
| <span data-ttu-id="f9963-119">Tarefas de projetos</span><span class="sxs-lookup"><span data-stu-id="f9963-119">Project Tasks</span></span>                           | <span data-ttu-id="f9963-120">Entidade de integração para a tarefa do projeto.</span><span class="sxs-lookup"><span data-stu-id="f9963-120">Integration entity for project task.</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="f9963-121">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="f9963-121">Entity flow</span></span>

<span data-ttu-id="f9963-122">As tarefas de projeto são gerenciadas no Project Service Automation e são sincronizados para o Finance and Operations como atividades do projeto.</span><span class="sxs-lookup"><span data-stu-id="f9963-122">Project tasks are managed in Project Service Automation, and they are synchronized to Finance and Operations as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f9963-123">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="f9963-123">Prerequisites and mapping setup</span></span>

<span data-ttu-id="f9963-124">Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.</span><span class="sxs-lookup"><span data-stu-id="f9963-124">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="f9963-125">Power Query</span><span class="sxs-lookup"><span data-stu-id="f9963-125">Power Query</span></span>

<span data-ttu-id="f9963-126">Você deverá usar o Microsoft Power Query para filtrar dados se estas condições forem atendidas:</span><span class="sxs-lookup"><span data-stu-id="f9963-126">You must use Microsoft Power Query to filter data if these conditions are met:</span></span>

- <span data-ttu-id="f9963-127">Você tem registros específicos do recurso em uma tarefa de projeto.</span><span class="sxs-lookup"><span data-stu-id="f9963-127">You have resource specific records within a project task.</span></span>

<span data-ttu-id="f9963-128">Se você precisar usar o Power Query, consulte as seguintes diretrizes:</span><span class="sxs-lookup"><span data-stu-id="f9963-128">If you must use Power Query, follow these guidelines:</span></span>

- <span data-ttu-id="f9963-129">O modelo Tarefas de projeto (PSA para Fin and Ops) tem um filtro padrão para excluir os registros específicos de recurso de uma tarefa de projeto. Basta definir o filtro **IsLineTask** como **False**.</span><span class="sxs-lookup"><span data-stu-id="f9963-129">The Project tasks (PSA to Fin and Ops) template has a default filter to exclude resource specific records from within a project task by setting the filter on the **IsLineTask** to **False**.</span></span> <span data-ttu-id="f9963-130">Se você criar seu próprio modelo, adicione esse filtro.</span><span class="sxs-lookup"><span data-stu-id="f9963-130">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f9963-131">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="f9963-131">Template mapping in Data integration</span></span>

<span data-ttu-id="f9963-132">A ilustração a seguir mostra um exemplo de mapeamentos de tarefas de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="f9963-132">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="f9963-133">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f9963-133">The mapping shows the field information that will be synchronized from Project Service Automation to Finance and Operations.</span></span>

<span data-ttu-id="f9963-134">[![Mapeamento de modelo](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="f9963-134">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>


