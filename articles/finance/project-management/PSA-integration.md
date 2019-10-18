---
title: Visão geral do Project Service Automation
description: Este tópico fornece informações sobre o Dynamics 365 Project Service Automation para a solução de integração do Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
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
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 31d72591041f8d8cc327aa7c6578c15731ba13c5
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250544"
---
# <a name="project-service-automation-overview"></a><span data-ttu-id="d5b2f-103">Visão geral do Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d5b2f-103">Project Service Automation overview</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d5b2f-104">A solução de integração Project Service Automation para o Finance usa o recurso Integração de dados para sincronizar dados em instâncias do Dynamics 365 Finance e do Dynamics 365 Project Service Automation por meio do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-104">The Project Service Automation to Finance integration solution uses the Data integration feature to synchronize data across instances of Dynamics 365 Finance and Dynamics 365 Project Service Automation via Common Data Service.</span></span> <span data-ttu-id="d5b2f-105">Os modelos de integração disponíveis com o recurso Integração de dados permitem o fluxo de projetos, contratos de projeto, linhas de contrato de projeto, marcos de linha do contrato de projeto, tarefas de projeto, categorias de transação de despesa, estimativas de horas e estimativas de despesas do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-105">The integration templates that are available with the Data integration feature enable the flow of projects, project contracts, project contract lines, project contract line milestones, project tasks, expense transaction categories, hour estimates, and expense estimates from Project Service Automation to Finance.</span></span>

> [!NOTE]
> - <span data-ttu-id="d5b2f-106">Se estiver usando a versão 7.3.0, instale o KB 4074835.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-106">If you're using version 7.3.0, you must install KB 4074835.</span></span> <span data-ttu-id="d5b2f-107">Isso permitirá que você integre projetos de preço fixo.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-107">You will then be able to integrate fixed price projects.</span></span>
> - <span data-ttu-id="d5b2f-108">Se você estiver usando a versão 7.3.0 e estiver transferindo as transações de taxa do Project Service Automation, instale o KB 4345320 para incluir essas taxas na fatura do projeto.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-108">If you're using version 7.3.0, and you are bringing fee transactions over from Project Service Automation, you must install KB 4345320 in order to include those fees in the project invoice.</span></span>
> - <span data-ttu-id="d5b2f-109">Se estiver usando a versão 8.0, você poderá usar a integração de tarefas do projeto, as categorias de transação de despesa, as estimativas de horas, as estimativas de despesas e o bloqueio de funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-109">If you're using version 8.0, you will be able to use project task integration, expense transaction categories, hour estimates, expense estimates, and functionality locking.</span></span>
> - <span data-ttu-id="d5b2f-110">Se estiver usando a versão 8.0.1 ou posterior, você poderá sincronizar números reais.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-110">If you're using version 8.0.1 or later, you will be able to synchronize actuals.</span></span>

<span data-ttu-id="d5b2f-111">Para integrar o Project Service Automation Finance, configure os parâmetros de integração do Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-111">Before you can integrate Project Service Automation Finance, you must configure the Project Service Automation integration parameters.</span></span> <span data-ttu-id="d5b2f-112">Para obter mais informações, consulte os [Parâmetros de integração do Project Service Automation](PSA-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="d5b2f-112">For more information, see [Project Service Automation integration parameters](PSA-parameters.md).</span></span>

<span data-ttu-id="d5b2f-113">Esta solução de integração permite a sincronização direta nos seguintes cenários:</span><span class="sxs-lookup"><span data-stu-id="d5b2f-113">This integration solution enables direct synchronization in the following scenarios:</span></span>

- <span data-ttu-id="d5b2f-114">Manter contratos de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-114">Maintain project contracts in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-115">Criar projetos no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-115">Create projects in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-116">Manter linhas de contrato de projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-116">Maintain project contract lines in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-117">Manter marcos de linha de contrato de projeto no Project Service Automation e sincronizá-los diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-117">Maintain project contract line milestones in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-118">Manter tarefas de projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-118">Maintain project tasks in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-119">Manter categorias de transação de despesas no Finance e sincronizá-las diretamente do Finance para o Project Service Automation.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-119">Maintain expense transaction categories in Finance, and synchronize them directly from Finance to Project Service Automation.</span></span>
- <span data-ttu-id="d5b2f-120">Criar estimativas de horas do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-120">Create project hour estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-121">Criar estimativas de despesa do projeto no Project Service Automation e sincronizá-las diretamente do Project Service Automation para o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-121">Create project expense estimates in Project Service Automation, and synchronize them directly from Project Service Automation to Finance.</span></span>
- <span data-ttu-id="d5b2f-122">Criar tempo, despesa e valores reais de taxas do projeto no Project Service Automation, bem como transações do projeto no diário de integração do Project Service Automation para que possam ser publicados no Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-122">Create project time, expense, and fee actuals in Project Service Automation, and create project transactions in the Project Service Automation integration journal so that they can be posted in Finance.</span></span>

## <a name="data-synchronization"></a><span data-ttu-id="d5b2f-123">Sincronização de dados</span><span class="sxs-lookup"><span data-stu-id="d5b2f-123">Data synchronization</span></span>

<span data-ttu-id="d5b2f-124">A ilustração a seguir mostra como os dados são sincronizados como parte da integração entre o Project Service Automation e o Finance.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-124">The following illustration shows how data is synchronized as part of the integration between Project Service Automation and Finance.</span></span>

> [!NOTE]
> <span data-ttu-id="d5b2f-125">Nem todos os modelos estão disponíveis atualmente.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-125">Not all templates are currently available.</span></span> <span data-ttu-id="d5b2f-126">Os modelos serão liberados ao serem concluídos.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-126">Templates will be released as they are completed.</span></span>

<span data-ttu-id="d5b2f-127">[![Integração do Project Service Automation ao Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span><span class="sxs-lookup"><span data-stu-id="d5b2f-127">[![Project Service Automation integration with Finance](./media/PSA-integration.png)](./media/PSA-integration.png)</span></span>

## <a name="system-requirements-for-finance"></a><span data-ttu-id="d5b2f-128">Requisitos do sistema para Finance</span><span class="sxs-lookup"><span data-stu-id="d5b2f-128">System requirements for Finance</span></span>

<span data-ttu-id="d5b2f-129">Para usar a solução de integração Project Service Automation para o Finance, você deve instalar o Enterprise Edition 7.3 com a atualização 12 ou posterior da plataforma.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-129">To use the Project Service Automation to Finance integration solution, you must install Enterprise edition 7.3 with Platform update 12 or later.</span></span>

## <a name="system-requirements-for-project-service-automation"></a><span data-ttu-id="d5b2f-130">Requisitos do sistema para o Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d5b2f-130">System requirements for Project Service Automation</span></span>

<span data-ttu-id="d5b2f-131">Para usar a solução de integração Project Service Automation para o Finance, você deve instalar os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="d5b2f-131">To use the Project Service Automation to Finance integration solution, you must install the following components:</span></span>

- <span data-ttu-id="d5b2f-132">Dynamics 365 Project Service Automation versão 9.0.0.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5b2f-132">Dynamics 365 Project Service Automation version 9.0.0.0 or later</span></span>
- <span data-ttu-id="d5b2f-133">Solução Prospect to cash para Dynamics 365 Sales, versão 1.14.0.0 (v14) ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5b2f-133">Prospect to cash solution for Dynamics 365 Sales, version 1.14.0.0 (v14) or later</span></span>
- <span data-ttu-id="d5b2f-134">A solução Project Service Automation para o Finance do Dynamics 365 Project Service Automation versão 1.0.0.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="d5b2f-134">Project Service Automation to Finance solution for Dynamics 365 Project Service Automation version 1.0.0.0 or later</span></span>

## <a name="install-the-project-service-automation-to-finance-integration-solution-in-your-project-service-automation-instance"></a><span data-ttu-id="d5b2f-135">Instale a solução de integração Project Service Automation para o Finance na sua instância do Project Service Automation</span><span class="sxs-lookup"><span data-stu-id="d5b2f-135">Install the Project Service Automation to Finance integration solution in your Project Service Automation instance</span></span>

<span data-ttu-id="d5b2f-136">Baixe a solução de integração Project Service Automation para o Finance em [Centro de Download Microsoft](https://www.microsoft.com/download/details.aspx?id=57016) e siga as instruções incluídas na solução.</span><span class="sxs-lookup"><span data-stu-id="d5b2f-136">Download the Project Service Automation to Finance integration solution from [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=57016), and follow the instructions that are included with the solution.</span></span>
