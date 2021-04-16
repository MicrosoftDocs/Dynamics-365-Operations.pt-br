---
title: 'Criar relação de atividade: Sucessor'
description: O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46dda12d4ad2b23ee86d240e6cdd8a1d46f1838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829225"
---
# <a name="create-activity-relation---successor"></a><span data-ttu-id="585bc-103">Criar relação de atividade: Sucessor</span><span class="sxs-lookup"><span data-stu-id="585bc-103">Create activity relation - Successor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="585bc-104">O fluxo de atividades em um fluxo de produção de lean é documentado por meio de relações de atividade.</span><span class="sxs-lookup"><span data-stu-id="585bc-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="585bc-105">O registro mostra como criar uma relação de atividade.</span><span class="sxs-lookup"><span data-stu-id="585bc-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="585bc-106">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="585bc-106">Prerequisites:</span></span>

- <span data-ttu-id="585bc-107">Uma versão e um fluxo de produção no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="585bc-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="585bc-108">Duas atividades sucessivas no fluxo de produção são criadas mas não relacionadas.</span><span class="sxs-lookup"><span data-stu-id="585bc-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="585bc-109">Localizar a versão do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="585bc-109">Find the production flow version</span></span> 
1. <span data-ttu-id="585bc-110">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="585bc-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="585bc-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="585bc-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="585bc-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="585bc-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="585bc-113">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="585bc-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="585bc-114">Na lista, selecione uma versão de rascunho.</span><span class="sxs-lookup"><span data-stu-id="585bc-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="585bc-115">Relacionamentos de atividade podem ser adicionados a versões de rascunho ou ativas de um fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="585bc-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="585bc-116">Abrir a visão geral da atividade</span><span class="sxs-lookup"><span data-stu-id="585bc-116">Open the activity overview</span></span>
1. <span data-ttu-id="585bc-117">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="585bc-117">Click Activities.</span></span>
    * <span data-ttu-id="585bc-118">Observe que o formulário mostra todas as atividades do fluxo de produção que estão alocadas para a versão dos fluxos de produção nos quais você está trabalhando.</span><span class="sxs-lookup"><span data-stu-id="585bc-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="585bc-119">Adicionar um sucessor</span><span class="sxs-lookup"><span data-stu-id="585bc-119">Add a Successor</span></span>
1. <span data-ttu-id="585bc-120">Clique em Adicionar sucessor.</span><span class="sxs-lookup"><span data-stu-id="585bc-120">Click Add successor.</span></span>
2. <span data-ttu-id="585bc-121">No campo Atividade, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="585bc-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="585bc-122">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="585bc-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="585bc-123">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="585bc-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="585bc-124">Marque a caixa de seleção Restrição.</span><span class="sxs-lookup"><span data-stu-id="585bc-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="585bc-125">No campo Valor de restrição, insira um número.</span><span class="sxs-lookup"><span data-stu-id="585bc-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="585bc-126">O horário de restrição é o horário que será agendado entre o final agendado do predecessor (data e horário de vencimento) e o início agendado do predecessor.</span><span class="sxs-lookup"><span data-stu-id="585bc-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="585bc-127">No campo Unidades, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="585bc-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="585bc-128">No campo Razão do tempo de ciclo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="585bc-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="585bc-129">Se ambas as atividades forem executadas no mesmo takt, a razão do tempo de ciclo deverá ser 1.</span><span class="sxs-lookup"><span data-stu-id="585bc-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="585bc-130">Se o antecessor for executado com o dobro da velocidade do sucessor, a razão deverá ser 2.</span><span class="sxs-lookup"><span data-stu-id="585bc-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="585bc-131">As razões do tempo de ciclo são usadas para calcular os tempos de ciclo individuais das atividades do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="585bc-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="585bc-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="585bc-132">Click OK.</span></span>
10. <span data-ttu-id="585bc-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="585bc-133">Close the page.</span></span>
11. <span data-ttu-id="585bc-134">Clique na guia GridPanel.</span><span class="sxs-lookup"><span data-stu-id="585bc-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="585bc-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="585bc-135">Close the page.</span></span>
13. <span data-ttu-id="585bc-136">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="585bc-136">Refresh the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]