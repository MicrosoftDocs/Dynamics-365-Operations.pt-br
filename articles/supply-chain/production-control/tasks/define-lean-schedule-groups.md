--- 
title: Definir grupos de agendamento de lean manufacturing
description: "Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: a5bc20c0a9e2396365caebeb3751d2090e4575a4
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="f42a0-103">Definir grupos de agendamento de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="f42a0-103">Define lean schedule groups</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f42a0-104">Os grupos de agendamento de lean manufacturing são definidos para agrupar e distinguir produtos na programação do kanban.</span><span class="sxs-lookup"><span data-stu-id="f42a0-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="f42a0-105">O agrupamento pode ser feito como a associação genérica por empresa ou ser específico de uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f42a0-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="f42a0-106">Cada grupo tem um código de cor atribuído para a indicação visual na página de lista da programação kanban.</span><span class="sxs-lookup"><span data-stu-id="f42a0-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="f42a0-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="f42a0-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="f42a0-108">Definir grupo de agendamento de lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="f42a0-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="f42a0-109">Vá para Gerenciamento de informações do produto > Lean manufacturing > Grupos de agendamento de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="f42a0-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="f42a0-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f42a0-110">Click New.</span></span>
3. <span data-ttu-id="f42a0-111">No campo Grupo de agendamento, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f42a0-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="f42a0-112">Um grupo de agendamento pode ser definido como o grupo global ou específico para uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f42a0-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="f42a0-113">Neste exemplo simples, definimos um grupo global e a célula de trabalho é mantida em branco.</span><span class="sxs-lookup"><span data-stu-id="f42a0-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="f42a0-114">As configurações deste grupo se aplicam a todas as células de trabalho que não tenham grupos de agendamento específicos.</span><span class="sxs-lookup"><span data-stu-id="f42a0-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="f42a0-115">Selecione uma cor da seleção de cor.</span><span class="sxs-lookup"><span data-stu-id="f42a0-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="f42a0-116">As cores são usadas para realçar os trabalhos na página de lista da agenda kanban ou no quadro do processo do kanban.</span><span class="sxs-lookup"><span data-stu-id="f42a0-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="f42a0-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f42a0-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="f42a0-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f42a0-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="f42a0-119">Produtos associados</span><span class="sxs-lookup"><span data-stu-id="f42a0-119">Associate product</span></span>
1. <span data-ttu-id="f42a0-120">Associar um produto específico</span><span class="sxs-lookup"><span data-stu-id="f42a0-120">Associate a specific product</span></span>
    * <span data-ttu-id="f42a0-121">Há duas maneiras de associar a grupos de agendamento de lean manufacturing, como um produto específico (Tipo de relação de itens = Item) ou como parte de uma chave de alocação de itens (tipo de relação de item = grupo).</span><span class="sxs-lookup"><span data-stu-id="f42a0-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="f42a0-122">No campo Tipo de relação de itens, selecione Item</span><span class="sxs-lookup"><span data-stu-id="f42a0-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="f42a0-123">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f42a0-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="f42a0-124">No campo Índice de produtividade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f42a0-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="f42a0-125">O Índice de produtividade padrão é 1, o que significa que os produtos relacionados consomem exatamente a capacidade especificada em activites do processo dos fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="f42a0-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="f42a0-126">O Índice de produtividade > 1 define um consumo de recursos mais alto, e o Índice de produtividade < 1 define um consumo de recursos mais baixo.</span><span class="sxs-lookup"><span data-stu-id="f42a0-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="f42a0-127">O índice é usado no cálculo do custo e no cálculo do consumo de trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="f42a0-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="f42a0-128">Associe chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="f42a0-128">Associate item allocation key</span></span>
1. <span data-ttu-id="f42a0-129">Associe uma chave de alocação de item</span><span class="sxs-lookup"><span data-stu-id="f42a0-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="f42a0-130">Adicionar uma associação a uma chave de alocação de item usando o Grupo do tipo de relação de itens.</span><span class="sxs-lookup"><span data-stu-id="f42a0-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="f42a0-131">Observe que para esse processo, você precisa de uma chave de alocação de item de previsão definida em seus dados.</span><span class="sxs-lookup"><span data-stu-id="f42a0-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="f42a0-132">No campo Tipo de relação de itens, selecione Grupo</span><span class="sxs-lookup"><span data-stu-id="f42a0-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="f42a0-133">No campo Chave de alocação de itens, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f42a0-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f42a0-134">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f42a0-134">In the list, click the link in the selected row.</span></span>


