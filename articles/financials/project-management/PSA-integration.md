---
title: Project Service Automation
description: "Este tópico fornece informações sobre a solução de integração do Project Service Automation para o Finance and Operations. Esta solução de integração usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service."
author: KimANelson
manager: AnnBe
ms.date: 06/29/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 841ea53f754f61c2930e77fdafc85eac72f47d7a
ms.openlocfilehash: 4b1d2ae69899a2937d47f6547ee4ba72b2d1ece4
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---

# <a name="project-service-automation"></a><span data-ttu-id="734b0-104">Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="734b0-104">Project Service Automation</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="734b0-105">A solução de integração do Project Service Automation para o Finance and Operations usa o recurso Integração de dados para sincronizar dados em instâncias do Microsoft Dynamics 365 for Finance and Operations e do Microsoft Dynamics 365 for Project Service Automation por meio do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="734b0-105">The Project Service Automation to Finance and Operations integration solution uses the Data integration feature to synchronize data across instances of Microsoft Dynamics 365 for Finance and Operations and Microsoft Dynamics 365 for Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="734b0-106">Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de projetos, contratos de projeto, linhas de contrato de projeto, marcos de linha do contrato de projeto, tarefas de projeto, categorias de transação de despesa, estimativas de horas e estimativas de despesas do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-106">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance and Operations.</span></span>

> [!NOTE]
> - <span data-ttu-id="734b0-107">Se estiver usando o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, após instalar o KB 4132657 e o KB 4132660, você poderá usar os modelos para integrar tarefas de projeto, categorias de transação de despesa, estimativas de horas, estimativas de despesas e números reais e para configurar o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="734b0-107">If you're using Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3.0, after you install KB 4132657 and KB 4132660, you will be able to use the templates to integrate project tasks, expense transaction categories, hour estimates, expense estimates, and actuals, and to configure functionality locking.</span></span> <span data-ttu-id="734b0-108">Se você precisar redefinir as distribuições contábeis, é recomendável também instalar o KB 4131710.</span><span class="sxs-lookup"><span data-stu-id="734b0-108">If you must reset the accounting distributions, we recommend that you also install KB 4131710.</span></span>
> - <span data-ttu-id="734b0-109">Se estiver usando o Finance and Operations 7.3.0, é preciso instalar o KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="734b0-109">If you're using Finance and Operations 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="734b0-110">Isso permitirá que você integre projetos de preço fixo.</span><span class="sxs-lookup"><span data-stu-id="734b0-110">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="734b0-111">Se você estiver usando o Finance and Operations 7.3.0 e estiver transferindo as transações de taxa do Project Service Automation, instale o KB 4345320 para incluir essas taxas na fatura do projeto.</span><span class="sxs-lookup"><span data-stu-id="734b0-111">If you're using Finance and Operations 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="734b0-112">Se estiver usando o Microsoft Dynamics 365 for Finance and Operations versão 8.0, você poderá usar a integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="734b0-112">If you're using Microsoft Dynamics 365 for Finance and Operations version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="734b0-113">Se estiver usando o Microsoft Dynamics 365 for Finance and Operations versão 8.0.1 ou posterior, você poderá sincronizar números reais.</span><span class="sxs-lookup"><span data-stu-id="734b0-113">If you're using Microsoft Dynamics 365 for Finance and Operations version 8.0.1, or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="734b0-114">Para integrar o Project Service Automation ao Finance and Operations, configure os parâmetros de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="734b0-114">Before you can integrate Project Service Automation with Finance and Operations, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="734b0-115">Para obter mais informações, consulte os [Parâmetros de integração do Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="734b0-115">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="734b0-116">Esta solução de integração permite a sincronização direta nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="734b0-116">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="734b0-117">Manter contratos de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-117">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-118">Criar projetos no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-118">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-119">Manter linhas de contratos do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-119">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-120">Manter marcos de linhas de contratos do projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-120">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-121">Manter tarefas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-121">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-122">Manter categorias de transação de despesas no Finance and Operations e sincronizá-las diretamente do Finance and Operations para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="734b0-122">Maintain expense transaction categories in Finance and Operations, and synchronize them directly from Finance and Operations to Project Service Automation.</span></span>
- <span data-ttu-id="734b0-123">Criar estimativas de horas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-123">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-124">Criar estimativas de despesas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-124">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance and Operations.</span></span>
- <span data-ttu-id="734b0-125">Crie hora de projeto, despesa e valores reais de taxas no Project Service Automation, bem como transações do projeto no diário de integração do Project Service Automation para que possam ser publicados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-125">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance and Operations.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="734b0-126">Sincronização de dados</span><span class="sxs-lookup"><span data-stu-id="734b0-126">Data synchronization</span></span>

<span data-ttu-id="734b0-127">A ilustração a seguir mostra como os dados são sincronizados como parte da integração entre o Project Service Automation e o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="734b0-127">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance and Operations.</span></span>

> [!NOTE]
> <span data-ttu-id="734b0-128">Nem todos os modelos estão disponíveis atualmente.</span><span class="sxs-lookup"><span data-stu-id="734b0-128">Not all templates are currently available.</span></span> <span data-ttu-id="734b0-129">Os modelos serão liberados ao serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="734b0-129">Templates will be released as they are completed.</span></span>

<span data-ttu-id="734b0-130">[![Integração do Project Service Automation com o Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="734b0-130">[![Project Service Automation integration with Finance and Operations](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="734b0-131">Requisitos de sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="734b0-131">System requirements for Finance and Operations</span></span>

<span data-ttu-id="734b0-132">Para usar a solução do Project Service Automation para o Finance and Operations, você deve instalar o Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 com a atualização 12 da plataforma ou posterior.</span><span class="sxs-lookup"><span data-stu-id="734b0-132">To use the Project Service Automation to Finance and Operations integration solution, you must install Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 with platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="734b0-133">Requisitos do sistema para o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="734b0-133">System requirements for Project Service Automation</span></span>

<span data-ttu-id="734b0-134">Para usar a solução de integração do Project Service Automation para o Finance and Operations, você deve instalar os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="734b0-134">To use the Project Service Automation to Finance and Operations integration solution, you must install the following components:</span></span>

- <span data-ttu-id="734b0-135">Microsoft Dynamics 365 for Project Service Automation versão 9.0.0.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="734b0-135">Microsoft Dynamics 365 for Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="734b0-136">Solução Prospect to cash para Microsoft Dynamics 365 for Sales, versão 1.14.0.0 (v14) ou posterior</span><span class="sxs-lookup"><span data-stu-id="734b0-136">Prospect to cash solution for Microsoft Dynamics 365 for Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="734b0-137">O Project Service Automation para a solução Finance and Operations do Microsoft Dynamics 365 for Project Service Automation versão 1.0.0.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="734b0-137">Project Service Automation to Finance and Operations solution for Microsoft Dynamics 365 for Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-and-operations-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="734b0-138">Instale o Project Service Automation para a solução de integração Finance and Operations na sua instância do Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="734b0-138">Install the Project Service Automation to Finance and Operations integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="734b0-139">Baixe a solução de integração do Project Service Automation para o Finance and Operations em [Centro de Download Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=57016) e siga as instruções incluídas na solução.</span><span class="sxs-lookup"><span data-stu-id="734b0-139">Download the Project Service Automation to Finance and Operations integration solution from [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>

