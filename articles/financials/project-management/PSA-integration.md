---
title: Project Service Automation
description: "Esta solução usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service (CDS)."
author: KimANelson
manager: AnnBe
ms.date: 11/27/2017
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 0ad9e6ba7fe8dd915681da8e671ff210de887b1e
ms.contentlocale: pt-br
ms.lasthandoff: 05/29/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="beaac-103">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="beaac-103">Project Service Automation</span></span>

<span data-ttu-id="beaac-104">A solução de integração do Project Service Automation para o Finance and Operations usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="beaac-104">The Project Service Automation to Finance and Operations integration solution uses the Data Integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via the Common Data Service (CDS).</span></span> <span data-ttu-id="beaac-105">Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de projetos, contratos de projeto, linhas de contrato de projeto, marcos de linha do contrato de projeto, tarefas de projeto, categorias de transação de despesa, estimativas de horas e estimativas de despesas do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-105">The integration templates that are available with the Data Integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE] 
> <span data-ttu-id="beaac-106">Se estiver usando o Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, instale o KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="beaac-106">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="beaac-107">Isso permitirá que você integre projetos de preço fixo.</span><span class="sxs-lookup"><span data-stu-id="beaac-107">This will allow you to integrate fixed price projects.</span></span>
>
> <span data-ttu-id="beaac-108">Se estiver usando o Dynamics 365 for Finance and Operations versão 8.0, você poderá usar a integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="beaac-108">If you are using Dynamics 365 for Finance and Operations version 8.0, you will be able to use project tasks integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
>
> <span data-ttu-id="beaac-109">Se estiver usando o Dynamics 365 for Finance and Operations versão 8.0.1, você poderá sincronizar números reais.</span><span class="sxs-lookup"><span data-stu-id="beaac-109">If you are using Dynamics 365 for Finance and Operations version 8.0.1, you will be able to synchronize actuals.</span></span>
>
> <span data-ttu-id="beaac-110">Se estiver usando o Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="beaac-110">If you are using Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="beaac-111">Se você precisa redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="beaac-111">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>

<span data-ttu-id="beaac-112">Para integrar o Project Service Automation ao Finance and Operations, configure os parâmetros de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="beaac-112">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="beaac-113">Para obter mais informações, consulte os parâmetros de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="beaac-113">For more information, see Project Service Automation integration parameters.</span></span>

<span data-ttu-id="beaac-114">Esta solução de integração permite a sincronização direta nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="beaac-114">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="beaac-115">Manter contratos de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-115">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-116">Criar projetos no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-116">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-117">Manter linhas de contratos do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-117">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-118">Manter marcos de linhas de contratos do projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-118">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-119">Manter tarefas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-119">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-120">Manter categorias de transação de despesas no Finance and Operations e sincronizá-las diretamente do Finance and Operations para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="beaac-120">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="beaac-121">Criar estimativas de horas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-121">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="beaac-122">Criar estimativas de despesas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-122">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="beaac-123">Sincronização de dados</span><span class="sxs-lookup"><span data-stu-id="beaac-123">Data synchronization</span></span>
<span data-ttu-id="beaac-124">A ilustração a seguir mostra como os dados são sincronizados como parte da integração entre o Project Service Automation e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="beaac-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="beaac-125">Nem todos os modelos estão disponíveis atualmente.</span><span class="sxs-lookup"><span data-stu-id="beaac-125">Not all templates are currently available.</span></span> <span data-ttu-id="beaac-126">Os modelos serão liberados ao serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="beaac-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="beaac-127">[![Integração do Project Service Automation com o Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="beaac-127">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="beaac-128">Requisitos de sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="beaac-128">System requirements for Finance and Operations</span></span>

<span data-ttu-id="beaac-129">Para usar a solução do Project Service Automation para o Finance and Operations, você deve instalar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 com a atualização 12 da plataforma ou posterior.</span><span class="sxs-lookup"><span data-stu-id="beaac-129">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="beaac-130">Requisitos do sistema para o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="beaac-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="beaac-131">Para usar a solução de integração do Project Service Automation para o Finance and Operations, você deve instalar os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="beaac-131">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="beaac-132">Microsoft Dynamics 365 for Project Service Automation versão 9.0.0.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="beaac-132">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later.</span></span>
- <span data-ttu-id="beaac-133">Solução Prospect to cash para Dynamics 365 for Sales, versão 1.14.0.0 (v14) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="beaac-133">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>
- <span data-ttu-id="beaac-134">O Project Service Automation para a solução Operations do Dynamics 365 for Project Service Automation versão 1.0.0.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="beaac-134">Project Service Automation to Operations solution for Dynamics 365 for Project Service Automation version 1.0.0.0 or later.</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="beaac-135">Instale o Project Service Automation para a solução de integração Finance and Operations na sua instância do Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="beaac-135">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>



