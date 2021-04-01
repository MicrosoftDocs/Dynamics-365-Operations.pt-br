---
title: Alterar regras kanban para um trabalho de processamento
description: Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, KanbanJobSchedulingListPage, LeanRuleReassignmentWizard, KanbanReassignRuleLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ba77197f51b871f452c2aa94320aa2a68cf314df
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255364"
---
# <a name="change-kanban-rules-for-a-process-job"></a><span data-ttu-id="0710e-103">Alterar regras kanban para um trabalho de processamento</span><span class="sxs-lookup"><span data-stu-id="0710e-103">Change kanban rules for a process job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0710e-104">Esse procedimento se concentra em alterar a regra kanban usada para um kanban específico.</span><span class="sxs-lookup"><span data-stu-id="0710e-104">This procedure focuses on changing the used kanban rule for a given kanban.</span></span> <span data-ttu-id="0710e-105">Isso é útil para nivelar recursos de carga ou no caso de divisão.</span><span class="sxs-lookup"><span data-stu-id="0710e-105">This is useful to level load resources or in case of breakdown.</span></span> <span data-ttu-id="0710e-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="0710e-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="0710e-107">Esse procedimento é destinado ao planejador que trabalha em uma empresa de lean manufacturing, responsável pelo fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="0710e-107">This procedure is intended for the planner, working at a lean manufacturing company, responsible for the value stream.</span></span>


## <a name="copy-kanban-rule"></a><span data-ttu-id="0710e-108">Copiar regra kanban</span><span class="sxs-lookup"><span data-stu-id="0710e-108">Copy kanban rule</span></span>
1. <span data-ttu-id="0710e-109">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="0710e-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="0710e-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0710e-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0710e-111">Selecione a regra kanban de evento 000022 para L0001.</span><span class="sxs-lookup"><span data-stu-id="0710e-111">Select Event Kanban rule 000022 for L0001.</span></span>  
3. <span data-ttu-id="0710e-112">Clique em Duplicar regra kanban.</span><span class="sxs-lookup"><span data-stu-id="0710e-112">Click Duplicate kanban rule.</span></span>
4. <span data-ttu-id="0710e-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0710e-113">Click OK.</span></span>

## <a name="change-kanban-rule"></a><span data-ttu-id="0710e-114">Alterar a regra kanban</span><span class="sxs-lookup"><span data-stu-id="0710e-114">Change kanban rule</span></span>
1. <span data-ttu-id="0710e-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0710e-115">Close the page.</span></span>
2. <span data-ttu-id="0710e-116">Vá para Agendamento do trabalho kanban.</span><span class="sxs-lookup"><span data-stu-id="0710e-116">Go to Kanban job scheduling.</span></span>
3. <span data-ttu-id="0710e-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0710e-117">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0710e-118">Selecione a linha com kanban 000177.</span><span class="sxs-lookup"><span data-stu-id="0710e-118">Select line with Kanban 000177.</span></span>  
4. <span data-ttu-id="0710e-119">Clique em Usar regra kanban alternativa.</span><span class="sxs-lookup"><span data-stu-id="0710e-119">Click Use alternative kanban rule.</span></span>
5. <span data-ttu-id="0710e-120">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0710e-120">Click Next.</span></span>
6. <span data-ttu-id="0710e-121">No campo Regra kanban, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0710e-121">In the Kanban rule field, enter or select a value.</span></span>
    * <span data-ttu-id="0710e-122">Selecione a regra kanban que criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0710e-122">Select the kanban rule that was created earlier.</span></span> <span data-ttu-id="0710e-123">Esta é a regra kanban com o número mais alto.</span><span class="sxs-lookup"><span data-stu-id="0710e-123">This is the kanban rule with the highest number.</span></span>  
7. <span data-ttu-id="0710e-124">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="0710e-124">Click Finish.</span></span>
    * <span data-ttu-id="0710e-125">Agora o trabalho kanban está usando uma outra regra kanban.</span><span class="sxs-lookup"><span data-stu-id="0710e-125">Now the kanban job is using an another kanban rule.</span></span> <span data-ttu-id="0710e-126">Isso pode ser útil para nivelar células de trabalho de carga.</span><span class="sxs-lookup"><span data-stu-id="0710e-126">This can be useful to level load work cells.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]