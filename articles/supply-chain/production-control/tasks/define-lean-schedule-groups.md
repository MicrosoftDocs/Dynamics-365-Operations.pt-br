---
title: Definir grupos de agendamento de lean manufacturing
description: Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0cb17c68abbc4979a65e33c50450be575df3d93
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1836255"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="e63af-103">Definir grupos de agendamento de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="e63af-103">Define lean schedule groups</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e63af-104">Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban.</span><span class="sxs-lookup"><span data-stu-id="e63af-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="e63af-105">O agrupamento pode ser feito como a associação genérica por empresa ou ser específico de uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e63af-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="e63af-106">Cada grupo tem um código de cor atribuído para a indicação visual na página de lista da programação kanban.</span><span class="sxs-lookup"><span data-stu-id="e63af-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="e63af-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="e63af-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="e63af-108">Definir grupo de agendamento de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="e63af-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="e63af-109">Vá para Gerenciamento de informações do produto > Lean manufacturing > Grupos de agendamento de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="e63af-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="e63af-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="e63af-110">Click New.</span></span>
3. <span data-ttu-id="e63af-111">No campo Grupo de agendamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e63af-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="e63af-112">Um grupo de agendamento pode ser definido como o grupo global ou específico para uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e63af-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="e63af-113">Neste exemplo simples, definimos um grupo global e a célula de trabalho é mantida em branco.</span><span class="sxs-lookup"><span data-stu-id="e63af-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="e63af-114">As configurações deste grupo se aplicam a todas as células de trabalho que não tenham grupos de agendamento específicos.</span><span class="sxs-lookup"><span data-stu-id="e63af-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="e63af-115">Selecione uma cor da seleção de cor.</span><span class="sxs-lookup"><span data-stu-id="e63af-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="e63af-116">As cores são usadas para realçar os trabalhos na página de lista da agenda kanban ou no quadro do processo do kanban.</span><span class="sxs-lookup"><span data-stu-id="e63af-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="e63af-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e63af-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="e63af-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e63af-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="e63af-119">Produtos associados</span><span class="sxs-lookup"><span data-stu-id="e63af-119">Associate product</span></span>
1. <span data-ttu-id="e63af-120">Associar um produto específico</span><span class="sxs-lookup"><span data-stu-id="e63af-120">Associate a specific product</span></span>
    * <span data-ttu-id="e63af-121">Há duas maneiras de associar a grupos de agendamento de lean manufacturing, como um produto específico (Tipo de relação de itens = Item) ou como parte de uma chave de alocação de itens (tipo de relação de item = grupo).</span><span class="sxs-lookup"><span data-stu-id="e63af-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="e63af-122">No campo Tipo de relação de itens, selecione Item</span><span class="sxs-lookup"><span data-stu-id="e63af-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="e63af-123">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="e63af-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="e63af-124">No campo Índice de produtividade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="e63af-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="e63af-125">O Índice de produtividade padrão é 1, o que significa que os produtos relacionados consomem exatamente a capacidade especificada em activites do processo dos fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="e63af-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="e63af-126">O Índice de produtividade > 1 define um consumo de recursos mais alto, e o Índice de produtividade < 1 define um consumo de recursos mais baixo.</span><span class="sxs-lookup"><span data-stu-id="e63af-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="e63af-127">O índice é usado no cálculo do custo e no cálculo do consumo de trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="e63af-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="e63af-128">Associe chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="e63af-128">Associate item allocation key</span></span>
1. <span data-ttu-id="e63af-129">Associe uma chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="e63af-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="e63af-130">Adicionar uma associação a uma chave de alocação de item usando o Grupo do tipo de relação de itens.</span><span class="sxs-lookup"><span data-stu-id="e63af-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="e63af-131">Observe que para esse processo, você precisa de uma chave de alocação de item de previsão definida em seus dados.</span><span class="sxs-lookup"><span data-stu-id="e63af-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="e63af-132">No campo Tipo de relação de itens, selecione Grupo</span><span class="sxs-lookup"><span data-stu-id="e63af-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="e63af-133">No campo Chave de alocação de itens, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="e63af-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e63af-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="e63af-134">In the list, click the link in the selected row.</span></span>

