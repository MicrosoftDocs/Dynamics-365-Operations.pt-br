---
title: Visão geral da Otimização de Planejamento
description: Este tópico mostra uma visão geral da Otimização de Planejamento
author: ChristianRytt
manager: AnnBe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: aae9ea56fc2174df56274776993c68b11c0521d0
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773900"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="planning-optimization-overview"></a><span data-ttu-id="73afe-103">Visão geral da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="73afe-103">Planning Optimization overview</span></span>

<span data-ttu-id="73afe-104">O Suplemento Otimização de Planejamento para o Microsoft Dynamics 365 Supply Chain Management permite que o cálculo de planejamento mestre ocorra fora do Dynamics 365 Supply Chain Management e do banco de dados SQL relacionado.</span><span class="sxs-lookup"><span data-stu-id="73afe-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="73afe-105">Os benefícios associados à funcionalidade Otimização de Planejamento incluem o desempenho aprimorado e o impacto mínimo no banco de dados SQL durante as execuções do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="73afe-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="73afe-106">As execuções de planejamento rápido podem ser feitas mesmo durante o horário de expediente, para que os planejadores possam reagir imediatamente à demanda ou às alterações de parâmetro.</span><span class="sxs-lookup"><span data-stu-id="73afe-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="73afe-107">Para usar a Otimização de Planejamento, você deverá instalar o Suplemento Otimização de Planejamento do seu projeto no Microsoft Dynamics Lifecycle Services (LCS) e ativar a funcionalidade Otimização de Planejamento no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="73afe-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="73afe-108">Para obter mais informações, consulte [Introdução à Otimização de Planejamento](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="73afe-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="73afe-109">A ilustração a seguir mostra a vantagem da execução da Otimização de Planejamento no horário de expediente.</span><span class="sxs-lookup"><span data-stu-id="73afe-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Vantagem de executar a Otimização de planejamento durante o horário de expediente](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="73afe-111">Desempenho aprimorado</span><span class="sxs-lookup"><span data-stu-id="73afe-111">Improved performance</span></span>

<span data-ttu-id="73afe-112">A Otimização de Planejamento pode ser usada em cenários que envolvam planos mestres de execução longa.</span><span class="sxs-lookup"><span data-stu-id="73afe-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="73afe-113">Ela foi especificamente projetada para cálculos muito rápidos envolvendo volumes de dados muito grandes.</span><span class="sxs-lookup"><span data-stu-id="73afe-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="73afe-114">Como foi criada como um serviço multilocatário hiperescalável, várias instâncias podem trabalhar juntas simultaneamente para calcular o plano.</span><span class="sxs-lookup"><span data-stu-id="73afe-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="73afe-115">Além disso, o serviço de planejamento remove a carga do planejamento mestre do sistema e trabalha com um fluxo de dados que minimiza a carga do servidor.</span><span class="sxs-lookup"><span data-stu-id="73afe-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="73afe-116">A Otimização de Planejamento pode ajudá-lo a atingir as seguintes metas:</span><span class="sxs-lookup"><span data-stu-id="73afe-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="73afe-117">Aumentar o desempenho do planejamento com um runtime mais curto.</span><span class="sxs-lookup"><span data-stu-id="73afe-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="73afe-118">Reduzir o impacto em outros processos durante a execução do planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="73afe-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="73afe-119">Fazer execuções mais frequentes de planejamento.</span><span class="sxs-lookup"><span data-stu-id="73afe-119">Do more frequent planning runs.</span></span> <span data-ttu-id="73afe-120">(Você não está limitado às execuções diárias).</span><span class="sxs-lookup"><span data-stu-id="73afe-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="73afe-121">Ficar confiante de que o crescimento futuro dos negócios não sobrecarregará o sistema de planejamento.</span><span class="sxs-lookup"><span data-stu-id="73afe-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="73afe-122">Arquitetura e fluxo de dados</span><span class="sxs-lookup"><span data-stu-id="73afe-122">Architecture and data flow</span></span>

<span data-ttu-id="73afe-123">Quando o Suplemento de Otimização de Planejamento for instalado do LCS, uma conexão segura para o serviço Otimização de Planejamento será estabelecida.</span><span class="sxs-lookup"><span data-stu-id="73afe-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="73afe-124">O serviço está localizado no mesmo país ou região do data center da instância do Supply Chain Management relacionado.</span><span class="sxs-lookup"><span data-stu-id="73afe-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="73afe-125">Após a configuração da Otimização de Planejamento, quando o planejamento mestre é executado, os dados mestre e os dados transacionais são enviados do Supply Chain Management para o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="73afe-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="73afe-126">Se o Suplemento Otimização de Planejamento for desinstalado, todos os dados relacionados no serviço Otimização de Planejamento serão removidos.</span><span class="sxs-lookup"><span data-stu-id="73afe-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="73afe-127">Fluxo de dados de alto nível para execuções de regeneração</span><span class="sxs-lookup"><span data-stu-id="73afe-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="73afe-128">O cliente do Supply Chain Management envia um sinal para solicitar uma execução de planejamento desde a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="73afe-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="73afe-129">A Otimização de Planejamento solicita os dados necessários por meio do conector integrado.</span><span class="sxs-lookup"><span data-stu-id="73afe-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="73afe-130">O banco de dados SQL envia as informações solicitadas sobre a configuração, os dados mestre e os dados transacionais para a Otimização de Planejamento por meio do conector.</span><span class="sxs-lookup"><span data-stu-id="73afe-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="73afe-131">O conector converte as informações entre o Supply Chain Management e o serviço Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="73afe-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="73afe-132">O serviço Otimização de Planejamento contém os dados relacionados ao planejamento em memória e faz os cálculos necessários.</span><span class="sxs-lookup"><span data-stu-id="73afe-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="73afe-133">O resultado do planejamento é enviado para o banco de dados do Supply Chain Management por meio do conector.</span><span class="sxs-lookup"><span data-stu-id="73afe-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="73afe-134">Os resultados incluem informações como as ordens planejadas e as informações de vinculação.</span><span class="sxs-lookup"><span data-stu-id="73afe-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="73afe-135">A Otimização de Planejamento envia um sinal para o Supply Chain Management para indicar que o planejamento foi concluído.</span><span class="sxs-lookup"><span data-stu-id="73afe-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="73afe-136">Ele também envia as mensagens e avisos relevantes.</span><span class="sxs-lookup"><span data-stu-id="73afe-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="73afe-137">A ilustração a seguir mostra o fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="73afe-137">The following illustration shows the data flow.</span></span>

![Fluxo de dados para execuções de regeneração](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="73afe-139">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="73afe-139">Related resources</span></span>

[<span data-ttu-id="73afe-140">Introdução à Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="73afe-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="73afe-141">Análise de ajuste da Otimização de Planejamento</span><span class="sxs-lookup"><span data-stu-id="73afe-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="73afe-142">Exibir logs de histórico de plano e de planejamento</span><span class="sxs-lookup"><span data-stu-id="73afe-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="73afe-143">Aplicar filtros a um plano</span><span class="sxs-lookup"><span data-stu-id="73afe-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="73afe-144">Cancelar um trabalho de planejamento</span><span class="sxs-lookup"><span data-stu-id="73afe-144">Cancel a planning job</span></span>](cancel-planning-job.md)
