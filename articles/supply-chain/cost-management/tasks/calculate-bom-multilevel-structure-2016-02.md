--- 
title: "Calcular uma BOM usando uma estrutura de vários níveis (apenas fevereiro de 2016)"
description: "Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos."
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 16c2cacaf70df5455c3ed49b8dcb5756e89f8cb8
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016-only"></a><span data-ttu-id="cdb98-103">Calcular uma BOM usando uma estrutura de vários níveis (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="cdb98-103">Calculate a BOM by using a multilevel structure (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cdb98-104">Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos.</span><span class="sxs-lookup"><span data-stu-id="cdb98-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="cdb98-105">Trata-se da sétima tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="cdb98-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="cdb98-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="cdb98-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="cdb98-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="cdb98-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="cdb98-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="cdb98-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="cdb98-109">Selecione o produto BOM_1.</span><span class="sxs-lookup"><span data-stu-id="cdb98-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="cdb98-110">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="cdb98-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="cdb98-111">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="cdb98-111">Click Item price.</span></span>
5. <span data-ttu-id="cdb98-112">Clique em Calcular custo do item.</span><span class="sxs-lookup"><span data-stu-id="cdb98-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="cdb98-113">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="cdb98-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="cdb98-114">No campo Versão do custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cdb98-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="cdb98-115">Selecione Versão do custo 20, porque é um tipo Custo planejado e o Modo de detalhamento tem vários níveis.</span><span class="sxs-lookup"><span data-stu-id="cdb98-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="cdb98-116">O modo de detalhamento de vários níveis destina-se a custos planejados e simulações.</span><span class="sxs-lookup"><span data-stu-id="cdb98-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="cdb98-117">Não é usado para custo padrão.</span><span class="sxs-lookup"><span data-stu-id="cdb98-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="cdb98-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cdb98-118">Click OK.</span></span>
8. <span data-ttu-id="cdb98-119">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="cdb98-119">Click View calculation details.</span></span>
    * <span data-ttu-id="cdb98-120">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="cdb98-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="cdb98-121">Nesse caso, observe como o BOM_2 foi calculado levando em consideração a matéria-prima, o processo e os custos gerais indiretos com um total de 29,40 em vez do custo padrão de 10 que foi ativado na guia de tarefas inicial nesta série.</span><span class="sxs-lookup"><span data-stu-id="cdb98-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="cdb98-122">Clique na guia Folha de custos.</span><span class="sxs-lookup"><span data-stu-id="cdb98-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="cdb98-123">Seguindo para a guia Folha de custos, os totais por grupo de custos são diferentes em comparação ao cálculo feito na guia de tarefas anterior.</span><span class="sxs-lookup"><span data-stu-id="cdb98-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="cdb98-124">No campo Nível, selecione "Vários".</span><span class="sxs-lookup"><span data-stu-id="cdb98-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="cdb98-125">Ao selecionar Vários, os custos são classificados de acordo com a composição de BOM_2, na qual 10 é derivado do grupo de custos M1 (ITEM_C) e 15,60 é derivado de sua fabricação na qual o grupo de custos é L2.</span><span class="sxs-lookup"><span data-stu-id="cdb98-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="cdb98-126">Os custos indiretos também variam.</span><span class="sxs-lookup"><span data-stu-id="cdb98-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="cdb98-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cdb98-127">Close the page.</span></span>
12. <span data-ttu-id="cdb98-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cdb98-128">Close the page.</span></span>


