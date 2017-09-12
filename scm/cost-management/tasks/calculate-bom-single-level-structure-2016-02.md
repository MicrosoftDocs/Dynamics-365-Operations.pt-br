--- 
title: "Calcular uma BOM usando uma estrutura de um único nível (apenas fevereiro de 2016)"
description: "Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de nível único baseado na folha de custos."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 0e6829238b244cc01b070fde6acdf37bdaeb9670
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016-only"></a><span data-ttu-id="c04ed-103">Calcular uma BOM usando uma estrutura de um único nível (apenas fevereiro de 2016)</span><span class="sxs-lookup"><span data-stu-id="c04ed-103">Calculate a BOM by using a single level structure (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c04ed-104">Este procedimento mostra como calcular o custo de um produto finalizado usando detalhamento de nível único baseado na folha de custos.</span><span class="sxs-lookup"><span data-stu-id="c04ed-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="c04ed-105">Trata-se da sexta tarefa na série de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="c04ed-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="c04ed-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="c04ed-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="c04ed-107">Vá para Produtos liberados.</span><span class="sxs-lookup"><span data-stu-id="c04ed-107">Go to Released products.</span></span>
2. <span data-ttu-id="c04ed-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c04ed-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c04ed-109">Selecione o produto BOM_1.</span><span class="sxs-lookup"><span data-stu-id="c04ed-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="c04ed-110">No Painel de Ação, clique em Gerenciar custos.</span><span class="sxs-lookup"><span data-stu-id="c04ed-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="c04ed-111">Clique em Preço de item.</span><span class="sxs-lookup"><span data-stu-id="c04ed-111">Click Item price.</span></span>
5. <span data-ttu-id="c04ed-112">Clique em Calcular custo do item.</span><span class="sxs-lookup"><span data-stu-id="c04ed-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="c04ed-113">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="c04ed-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="c04ed-114">No campo Versão do custo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c04ed-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="c04ed-115">Nesta demonstração, selecione 10.</span><span class="sxs-lookup"><span data-stu-id="c04ed-115">For this demo, select 10.</span></span> <span data-ttu-id="c04ed-116">Trata-se da mesma versão de custos usada para adicionar o preço de custo aos componentes.</span><span class="sxs-lookup"><span data-stu-id="c04ed-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="c04ed-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c04ed-117">Click OK.</span></span>
8. <span data-ttu-id="c04ed-118">Clique em Exibir detalhes do cálculo.</span><span class="sxs-lookup"><span data-stu-id="c04ed-118">Click View calculation details.</span></span>
    * <span data-ttu-id="c04ed-119">Você pode clicar nas reticências (...) para ver essa opção no menu superior.</span><span class="sxs-lookup"><span data-stu-id="c04ed-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="c04ed-120">Esta é a composição do custo:  •    10 é derivado do ITEM_A, 10 do ITEM_B, 10 do BOM_2.</span><span class="sxs-lookup"><span data-stu-id="c04ed-120">Here's the composition of the cost:  •    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="c04ed-121">Neste caso, não há detalhes para BOM_2 porque ele foi inserido como um custo padrão de 10, mas isso não foi feito por meio de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c04ed-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="c04ed-122">•  7 é derivado do tempo de preparação, que é um custo constante, e o 7 adicional é derivado da operação de tempo de execução (Processo).</span><span class="sxs-lookup"><span data-stu-id="c04ed-122">•  7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="c04ed-123">•   Também há outros valores que correspondem a custos indiretos.</span><span class="sxs-lookup"><span data-stu-id="c04ed-123">•   There are also other amounts that correspond to indirect costs.</span></span>  
9. @SysTaskRecorder:_RequestClose


