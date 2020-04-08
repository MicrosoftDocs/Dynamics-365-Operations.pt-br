---
title: Alterar regras kanban para um trabalho de processamento
description: Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 485afff3747a87a6e36f0249b146a39361d81b23
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147126"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="fe875-103">Alterar regras kanban para um trabalho de processamento</span><span class="sxs-lookup"><span data-stu-id="fe875-103">Change kanban rules for a process job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fe875-104">Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico.</span><span class="sxs-lookup"><span data-stu-id="fe875-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="fe875-105">Isso é útil para nivelar recursos de carga ou no caso de divisão.</span><span class="sxs-lookup"><span data-stu-id="fe875-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="fe875-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="fe875-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="fe875-107">Esse procedimento é destinado ao planejador que trabalha em uma empresa de lean manufacturing, responsável pelo fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="fe875-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="fe875-108">Copiar regra kanban</span><span class="sxs-lookup"><span data-stu-id="fe875-108">Copy kanban rule</span></span>
1. <span data-ttu-id="fe875-109">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="fe875-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="fe875-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fe875-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="fe875-111">Selecione a regra kanban de evento 000022 para L0001.</span><span class="sxs-lookup"><span data-stu-id="fe875-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="fe875-112">Clique em Duplicar regra kanban.</span><span class="sxs-lookup"><span data-stu-id="fe875-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="fe875-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fe875-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="fe875-114">Alterar a regra kanban</span><span class="sxs-lookup"><span data-stu-id="fe875-114">Change kanban rule</span></span>
1. <span data-ttu-id="fe875-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fe875-115">Close the page.</span></span>
2. <span data-ttu-id="fe875-116">Vá para Agendamento do trabalho kanban.</span><span class="sxs-lookup"><span data-stu-id="fe875-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="fe875-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fe875-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="fe875-118">Selecione a linha com kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="fe875-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="fe875-119">Clique em Usar regra kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="fe875-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="fe875-120">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="fe875-120">Click Next.</span></span>
6. <span data-ttu-id="fe875-121">No campo Regra kanban, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="fe875-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="fe875-122">Selecione a regra kanban que criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fe875-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="fe875-123">Esta é a regra kanban com o número mais alto.</span><span class="sxs-lookup"><span data-stu-id="fe875-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="fe875-124">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="fe875-124">Click Finish.</span></span>
    * <span data-ttu-id="fe875-125">Agora o trabalho kanban está usando uma outra regra kanban.</span><span class="sxs-lookup"><span data-stu-id="fe875-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="fe875-126">Isso pode ser útil para nivelar células de trabalho de carga.</span><span class="sxs-lookup"><span data-stu-id="fe875-126">This can be useful to level load work cells.</span></span>  

