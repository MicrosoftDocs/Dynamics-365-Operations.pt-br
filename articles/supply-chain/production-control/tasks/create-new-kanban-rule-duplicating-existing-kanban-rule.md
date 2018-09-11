--- 
title: Criar uma nova regra kanban duplicando uma regra kanban existente
description: "Este procedimento tem como foco a criação de uma duplicata de uma regra kanban existente."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 880262f8f453581ea93b5fd8edefe0fc62ac49c5
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="368b4-103">Criar uma nova regra kanban duplicando uma regra kanban existente</span><span class="sxs-lookup"><span data-stu-id="368b4-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="368b4-104">Este procedimento tem como foco a criação de uma duplicata de uma regra kanban existente.</span><span class="sxs-lookup"><span data-stu-id="368b4-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="368b4-105">Ele é útil se você quiser criar regras kanban com base em regras kanban existentes.</span><span class="sxs-lookup"><span data-stu-id="368b4-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="368b4-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="368b4-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="368b4-107">Este procedimento destina-se ao engenheiro do processo ou gerente de fluxo de valor, pois eles preparam a produção para uma produção de fluxo ou um produto novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="368b4-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="368b4-108">Selecionar uma regra kanban</span><span class="sxs-lookup"><span data-stu-id="368b4-108">Select a kanban rule</span></span>
1. <span data-ttu-id="368b4-109">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="368b4-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="368b4-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="368b4-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="368b4-111">Selecione a regra kanban 000017 para produto M0006.</span><span class="sxs-lookup"><span data-stu-id="368b4-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="368b4-112">Duplicar uma regra kanban</span><span class="sxs-lookup"><span data-stu-id="368b4-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="368b4-113">Clique em Duplicar regra kanban.</span><span class="sxs-lookup"><span data-stu-id="368b4-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="368b4-114">Ao duplicar uma regra kanban, é possível alterar tipo, data, atividades e a seleção do produto.</span><span class="sxs-lookup"><span data-stu-id="368b4-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="368b4-115">Altere o produto para o procedimento na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="368b4-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="368b4-116">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="368b4-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="368b4-117">Selecione M0007.</span><span class="sxs-lookup"><span data-stu-id="368b4-117">Select M0007.</span></span>  
3. <span data-ttu-id="368b4-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="368b4-118">Click OK.</span></span>
    * <span data-ttu-id="368b4-119">Note que uma duplicata da regra kanban 000017 é criada.</span><span class="sxs-lookup"><span data-stu-id="368b4-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    


