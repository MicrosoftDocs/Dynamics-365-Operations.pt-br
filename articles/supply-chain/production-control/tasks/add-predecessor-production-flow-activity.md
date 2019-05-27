---
title: Adicionar um antecessor à atividade do fluxo de produção
description: Em uma versão de fluxo de produção, todas as atividades devem ser sequenciadas.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9acb1c2672af70f535f3dce1c8f5a97e8d479158
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552290"
---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a><span data-ttu-id="996b1-103">Adicionar um antecessor à atividade do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="996b1-103">Add a predecessor to a production flow activity</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="996b1-104">Em uma versão de fluxo de produção, todas as atividades devem ser sequenciadas.</span><span class="sxs-lookup"><span data-stu-id="996b1-104">In a production flow version, all activities must be sequenced.</span></span> <span data-ttu-id="996b1-105">Uma atividade poderá ter um ou vários predecessores ou sucessores.</span><span class="sxs-lookup"><span data-stu-id="996b1-105">An activity can have one or multiple predecessors or successors.</span></span> 

<span data-ttu-id="996b1-106">Este procedimento mostra como associar um predecessor a uma atividade.</span><span class="sxs-lookup"><span data-stu-id="996b1-106">This procedure shows how to associate a predecessor to an activity.</span></span> 

<span data-ttu-id="996b1-107">Para executar esta tarefa, será necessário um fluxo de produção que tenha a versão de rascunho com pelo menos duas atividades que possam ser conectadas.</span><span class="sxs-lookup"><span data-stu-id="996b1-107">To perform this task, you need a production flow that has the Draft version with at least two activities that can be connected.</span></span> 

<span data-ttu-id="996b1-108">Para saber mais, leia o white paper "Fluxos de produção e atividades em lean manufacturing".</span><span class="sxs-lookup"><span data-stu-id="996b1-108">To learn more, read the white paper "Production flows and activities in lean manufacturing."</span></span>


## <a name="find-the-production-flow-and-version"></a><span data-ttu-id="996b1-109">Localizar o fluxo de produção e a versão</span><span class="sxs-lookup"><span data-stu-id="996b1-109">Find the production flow and version</span></span>
1. <span data-ttu-id="996b1-110">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="996b1-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="996b1-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="996b1-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="996b1-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="996b1-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="996b1-113">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="996b1-113">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="996b1-114">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="996b1-114">Click Activities.</span></span>

## <a name="select-an-activity-and-add-a-predecessor"></a><span data-ttu-id="996b1-115">Selecionar uma atividade e adicionar um predecessor</span><span class="sxs-lookup"><span data-stu-id="996b1-115">Select an activity and add a predecessor</span></span>
1. <span data-ttu-id="996b1-116">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="996b1-116">In the list, find and select the desired record.</span></span>
2. <span data-ttu-id="996b1-117">Clique em Adicionar predecessor.</span><span class="sxs-lookup"><span data-stu-id="996b1-117">Click Add predecessor.</span></span>
3. <span data-ttu-id="996b1-118">No campo Atividade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="996b1-118">In the Activity field, enter or select a value.</span></span>
4. <span data-ttu-id="996b1-119">No campo Razão do tempo de ciclo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="996b1-119">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="996b1-120">A razão do tempo de ciclo padrão de uma relação de atividade é 1.</span><span class="sxs-lookup"><span data-stu-id="996b1-120">The default cycle time ratio of an activity relation is 1.</span></span> <span data-ttu-id="996b1-121">Isso presume que as duas atividades são executadas no mesmo ritmo ou takt time.</span><span class="sxs-lookup"><span data-stu-id="996b1-121">This assumes that both activities run at the same pace or takt time.</span></span> <span data-ttu-id="996b1-122">Se o predecessor for executado em um ritmo maior (takt time menor), a taxa deverá ser menor que 1. Se o predecessor for executado em um ritmo mais lento (takt time maior), a taxa do ciclo de tempo será maior que 1.</span><span class="sxs-lookup"><span data-stu-id="996b1-122">If the predecessor runs at a higher pace (lower takt time), the ratio should be lower than 1, if the predecessor runs at a slower pace (higher takt time) the cycle time ratio is greater than 1.</span></span>  
5. <span data-ttu-id="996b1-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="996b1-123">Click OK.</span></span>

