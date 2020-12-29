---
title: Calcular uma BOM usando uma estrutura de vários níveis (Fevereiro de 2016)
description: Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0f0ec28a20d32fc38cd6e77a76a02fc9544db3ca
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422262"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="83398-103">Calcular uma BOM usando uma estrutura de vários níveis (Fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="83398-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83398-104">Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de vários níveis baseado na folha de custos.</span><span class="sxs-lookup"><span data-stu-id="83398-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="83398-105">Trata-se da sétima tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="83398-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="83398-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="83398-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="83398-107">Vá para Gerenciamento de informações do produto > Produtos > Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="83398-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="83398-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="83398-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="83398-109">Selecione o produto BOM_1.</span><span class="sxs-lookup"><span data-stu-id="83398-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="83398-110">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="83398-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="83398-111">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="83398-111">Click Item price.</span></span>
5. <span data-ttu-id="83398-112">Clique em Calcular custo do item.</span><span class="sxs-lookup"><span data-stu-id="83398-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="83398-113">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="83398-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="83398-114">No campo Versão do custo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="83398-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="83398-115">Selecione Versão do custo 20, porque é um tipo Custo planejado e o Modo de detalhamento tem vários níveis.</span><span class="sxs-lookup"><span data-stu-id="83398-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="83398-116">O modo de detalhamento de vários níveis destina-se a custos planejados e simulações.</span><span class="sxs-lookup"><span data-stu-id="83398-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="83398-117">Não é usado para custo padrão.</span><span class="sxs-lookup"><span data-stu-id="83398-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="83398-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="83398-118">Click OK.</span></span>
8. <span data-ttu-id="83398-119">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="83398-119">Click View calculation details.</span></span>
    * <span data-ttu-id="83398-120">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="83398-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="83398-121">Nesse caso, observe como o BOM_2 foi calculado levando em consideração a matéria-prima, o processo e os custos gerais indiretos com um total de 29,40 em vez do custo padrão de 10 que foi ativado na guia de tarefas inicial nesta série.</span><span class="sxs-lookup"><span data-stu-id="83398-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="83398-122">Clique na guia Folha de custos.</span><span class="sxs-lookup"><span data-stu-id="83398-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="83398-123">Seguindo para a guia Folha de custos, os totais por grupo de custos são diferentes em comparação ao cálculo feito na guia de tarefas anterior.</span><span class="sxs-lookup"><span data-stu-id="83398-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="83398-124">No campo Nível, selecione "Vários".</span><span class="sxs-lookup"><span data-stu-id="83398-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="83398-125">Ao selecionar Vários, os custos são classificados de acordo com a composição de BOM_2, na qual 10 é derivado do grupo de custos M1 (ITEM_C) e 15,60 é derivado de sua fabricação na qual o grupo de custos é L2.</span><span class="sxs-lookup"><span data-stu-id="83398-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="83398-126">Os custos indiretos também variam.</span><span class="sxs-lookup"><span data-stu-id="83398-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="83398-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83398-127">Close the page.</span></span>
12. <span data-ttu-id="83398-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="83398-128">Close the page.</span></span>

