---
title: Sincronizar tarefas de projeto diretamente do Project Service Automation para o Finance and Operations.
description: Este tópico descreve o modelo e a tarefa subjacente usados para sincronizar tarefas de projeto diretamente do Microsoft Dynamics 365 Project Service Automation para o Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ba475721b69e7c75dfd2197597b54050a3598d37
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770257"
---
# <a name="synchronize-project-tasks-directly-from-project-service-automation-to-finance-and-operations"></a><span data-ttu-id="7da20-103">Sincronizar tarefas de projeto diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="7da20-103">Synchronize project tasks directly from Project Service Automation to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="7da20-104">Este tópico descreve o modelo e a tarefa subjacente usados para sincronizar tarefas de projeto diretamente do Dynamics 365 Project Service Automation para o Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="7da20-104">This topic describes the template and underlying task that are used to synchronize project tasks directly from Dynamics 365 Project Service Automation to Dynamics 365 Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="7da20-105">A integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade estão disponíveis na versão 8.0.</span><span class="sxs-lookup"><span data-stu-id="7da20-105">Project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking are available in version 8.0.</span></span>
> - <span data-ttu-id="7da20-106">Se estiver usando o Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e valores reais. Também poderá usá-los para configurar o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="7da20-106">If you're using Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="7da20-107">Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="7da20-107">If you must reset the accounting distributions, we recommended that you also install KB 4131710.</span></span>
> - <span data-ttu-id="7da20-108">A integração de valores reais está disponível na versão 8.0.1 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="7da20-108">Actuals integration is available in version 8.0.1 or later.</span></span>

## <a name="data-flow-for-project-service-automation-to-finance"></a><span data-ttu-id="7da20-109">Fluxo de dados do Project Service Automation para o Finance</span><span class="sxs-lookup"><span data-stu-id="7da20-109">Data flow for Project Service Automation to Finance</span></span>

<span data-ttu-id="7da20-110">A solução de integração do Project Service Automation para o Finance utiliza o recurso Integração de Dados para sincronizar dados nas instâncias do Project Service Automation e do Finance.</span><span class="sxs-lookup"><span data-stu-id="7da20-110">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Project Service Automation and Finance.</span></span> <span data-ttu-id="7da20-111">O modelo de integração disponível com o recurso Integração de Dados permite o fluxo de dados sobre tarefas do projeto do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="7da20-111">The integration template that is available with the Data integration feature enables the flow of data about project tasks from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7da20-112">A ilustração a seguir mostra como os dados são sincronizados entre o Project Service Automation e o Finance.</span><span class="sxs-lookup"><span data-stu-id="7da20-112">The following illustration shows how the data is synchronized between Project Service Automation and Finance.</span></span>

<span data-ttu-id="7da20-113">[![Fluxo de dados da integração do Project Service Automation com o Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span><span class="sxs-lookup"><span data-stu-id="7da20-113">[![Data flow for Project Service Automation integration with Finance](./media/ProjectTasksFlow.png)](./media/ProjectTasksFlow.png)</span></span>

## <a name="template-and-task"></a><span data-ttu-id="7da20-114">Modelo e tarefa</span><span class="sxs-lookup"><span data-stu-id="7da20-114">Template and task</span></span>

<span data-ttu-id="7da20-115">Para acessar o modelo, no Centro de administração do Microsoft Power Apps, selecione **Projetos** e, no canto superior direito, marque **Novo projeto** para selecionar modelos públicos.</span><span class="sxs-lookup"><span data-stu-id="7da20-115">To access the template, in the Microsoft Power Apps admin center, select **Projects**, and then, in the upper-right corner, select **New project** to select public templates.</span></span>

<span data-ttu-id="7da20-116">O seguinte modelo e a tarefa subjacente são usados para sincronizar tarefas do projeto do Project Service Automation com o Finance:</span><span class="sxs-lookup"><span data-stu-id="7da20-116">The following template and underlying task are used to synchronize project tasks from Project Service Automation to Finance:</span></span>

- <span data-ttu-id="7da20-117">**Nome do modelo na Integração de dados:** tarefas de projeto (do PSA para o Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="7da20-117">**Name of the template in Data integration:** Project tasks (PSA to Fin and Ops)</span></span>
- <span data-ttu-id="7da20-118">**Nome da tarefa no projeto:** tarefas de projeto</span><span class="sxs-lookup"><span data-stu-id="7da20-118">**Name of the task in the project:** Project tasks</span></span>

<span data-ttu-id="7da20-119">Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.</span><span class="sxs-lookup"><span data-stu-id="7da20-119">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="entity-set"></a><span data-ttu-id="7da20-120">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="7da20-120">Entity set</span></span>

| <span data-ttu-id="7da20-121">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="7da20-121">Project Service Automation</span></span> | <span data-ttu-id="7da20-122">Finanças</span><span class="sxs-lookup"><span data-stu-id="7da20-122">Finance</span></span>                             |
|----------------------------|-------------------------------------|
| <span data-ttu-id="7da20-123">Tarefas de projetos</span><span class="sxs-lookup"><span data-stu-id="7da20-123">Project Tasks</span></span>              | <span data-ttu-id="7da20-124">Entidade de integração para a tarefa do projeto</span><span class="sxs-lookup"><span data-stu-id="7da20-124">Integration entity for project task</span></span> |

## <a name="entity-flow"></a><span data-ttu-id="7da20-125">Fluxo de entidades</span><span class="sxs-lookup"><span data-stu-id="7da20-125">Entity flow</span></span>

<span data-ttu-id="7da20-126">As tarefas de projeto são gerenciadas no Project Service Automation e são sincronizados com o Finance como atividades do projeto.</span><span class="sxs-lookup"><span data-stu-id="7da20-126">Project tasks are managed in Project Service Automation, and they are synchronized to Finance as project activities.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="7da20-127">Pré-requisitos e configuração de mapeamento</span><span class="sxs-lookup"><span data-stu-id="7da20-127">Prerequisites and mapping setup</span></span>

<span data-ttu-id="7da20-128">Antes da sincronização de tarefas do projeto, você deve sincronizar contratos do projeto e projetos.</span><span class="sxs-lookup"><span data-stu-id="7da20-128">Before synchronization of project tasks can occur, you must synchronize project contracts and projects.</span></span>

## <a name="power-query"></a><span data-ttu-id="7da20-129">Power Query</span><span class="sxs-lookup"><span data-stu-id="7da20-129">Power Query</span></span>

<span data-ttu-id="7da20-130">Você deverá usar o Microsoft Power Query para Excel para filtrar dados se essa condição for atendida:</span><span class="sxs-lookup"><span data-stu-id="7da20-130">You must use Microsoft Power Query for Excel to filter data if this condition is met:</span></span>

- <span data-ttu-id="7da20-131">Você tem registros específicos do recurso em uma tarefa de projeto.</span><span class="sxs-lookup"><span data-stu-id="7da20-131">You have resource-specific records in a project task.</span></span>

<span data-ttu-id="7da20-132">Se você precisar usar o Power Query, consulte a diretriz a seguir:</span><span class="sxs-lookup"><span data-stu-id="7da20-132">If you must use Power Query, follow this guideline:</span></span>

- <span data-ttu-id="7da20-133">O modelo de tarefas de projeto (PSA para Fin and Ops) tem um filtro padrão que exclui os registros específicos de recurso de uma tarefa de projeto. Basta definir o filtro **IsLineTask** como **False**.</span><span class="sxs-lookup"><span data-stu-id="7da20-133">The Project tasks (PSA to Fin and Ops) template has a default filter that excludes resource-specific records from a project task by setting the filter on **IsLineTask** to **False**.</span></span> <span data-ttu-id="7da20-134">Se você criar seu próprio modelo, adicione esse filtro.</span><span class="sxs-lookup"><span data-stu-id="7da20-134">If you create your own template, you must add this filter.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="7da20-135">Mapeamento de modelo na Integração de dados</span><span class="sxs-lookup"><span data-stu-id="7da20-135">Template mapping in Data integration</span></span>

<span data-ttu-id="7da20-136">A ilustração a seguir mostra um exemplo de mapeamentos de tarefas de modelo na Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="7da20-136">The following illustration shows an example of the template task mappings in Data integration.</span></span> <span data-ttu-id="7da20-137">O mapeamento mostra as informações de campo que serão sincronizadas do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="7da20-137">The mapping shows the field information that will be synchronized from Project Service Automation to Finance.</span></span>

<span data-ttu-id="7da20-138">[![Mapeamento de modelo](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span><span class="sxs-lookup"><span data-stu-id="7da20-138">[![Template mapping](./media/ProjectTasksMapping.png)](./media/ProjectTasksMapping.png)</span></span>
