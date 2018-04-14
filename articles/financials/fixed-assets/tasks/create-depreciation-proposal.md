--- 
title: "Criar uma proposta de depreciação"
description: "Este procedimento descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos."
author: saraschi2
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ad87cc2ac2d8ce47369168ddbd7f310ec1275c4e
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-depreciation-proposal"></a><span data-ttu-id="3bd57-103">Criar uma proposta de depreciação</span><span class="sxs-lookup"><span data-stu-id="3bd57-103">Create a depreciation proposal</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3bd57-104">Este procedimento descreve como as propostas de depreciação em lote funcionam e explica como propor a depreciação para ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="3bd57-104">This procedure describes how depreciation batch proposals work and explains how to propose depreciation for fixed assets.</span></span> <span data-ttu-id="3bd57-105">A empresa usa essa tarefa de demonstração de USMF e a função de contador.</span><span class="sxs-lookup"><span data-stu-id="3bd57-105">This task uses the USMF demo company and the accountant role.</span></span>


## <a name="create-depreciation-proposal"></a><span data-ttu-id="3bd57-106">Criar proposta de depreciação</span><span class="sxs-lookup"><span data-stu-id="3bd57-106">Create depreciation proposal</span></span>
1. <span data-ttu-id="3bd57-107">Ir para Ativos fixos > Entradas de diário > Criar proposta de depreciação.</span><span class="sxs-lookup"><span data-stu-id="3bd57-107">Go to Fixed assets > Journal entries > Create depreciation proposal.</span></span>
2. <span data-ttu-id="3bd57-108">No campo Nome do diário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="3bd57-108">In the Name of journal field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3bd57-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="3bd57-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3bd57-110">No campo Até, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="3bd57-110">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="3bd57-111">Selecione a opção Resumir depreciação para resumir as depreciações mensais em uma linha do diário.</span><span class="sxs-lookup"><span data-stu-id="3bd57-111">Select the Summarize depreciation option to summarize monthly depreciations into one journal line.</span></span>  
    * <span data-ttu-id="3bd57-112">Por exemplo, se o valor "Até" for 31 de março de 2015, a seguinte descrição será gerada: "Depreciação desde 31 de janeiro de 2015."</span><span class="sxs-lookup"><span data-stu-id="3bd57-112">For example, if the To date value is March 31, 2015, the following description is generated: “Depreciation since January 31, 2015.”</span></span> <span data-ttu-id="3bd57-113">O campo Data nas linhas de diário propostas é então definido para 31 de março de 2015.</span><span class="sxs-lookup"><span data-stu-id="3bd57-113">The Date field on the proposed journal lines is then set to March 31, 2015.</span></span>  
    * <span data-ttu-id="3bd57-114">A proposta de depreciação pode ser filtrada por ativo, por grupo de ativos, ou por outros critérios usando a opção de filtragem.</span><span class="sxs-lookup"><span data-stu-id="3bd57-114">The depreciation proposal can be filtered by asset, asset group, or other criteria using the Filter option.</span></span>  
    * <span data-ttu-id="3bd57-115">Quando você usa a aquisição de criação ou as propostas de depreciação para formulário de ativos fixos, você pode propor a depreciação em lotes.</span><span class="sxs-lookup"><span data-stu-id="3bd57-115">When you use the Create acquisition or depreciation proposals for fixed assets form, you can propose depreciation in batches.</span></span> <span data-ttu-id="3bd57-116">Isso é recomendado para as propostas maiores que usarão mais recursos do sistema.</span><span class="sxs-lookup"><span data-stu-id="3bd57-116">This is recommended for larger proposals that will use more system resources.</span></span> <span data-ttu-id="3bd57-117">Se você selecionar a opção de lote, você ainda poderá concluir outras tarefas durante esse período.</span><span class="sxs-lookup"><span data-stu-id="3bd57-117">If you select the batch option, you can still complete other tasks during that time.</span></span> <span data-ttu-id="3bd57-118">Ao propor a depreciação dessa forma, a depreciação é calculada para os modelos de depreciação para ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="3bd57-118">When you propose depreciation in this way, depreciation is calculated for value models for fixed assets.</span></span>  
5. <span data-ttu-id="3bd57-119">Clique em Criar diário.</span><span class="sxs-lookup"><span data-stu-id="3bd57-119">Click Create journal.</span></span>

## <a name="review-depreciation-entries"></a><span data-ttu-id="3bd57-120">Entradas de depreciação de revisão</span><span class="sxs-lookup"><span data-stu-id="3bd57-120">Review depreciation entries</span></span>
1. <span data-ttu-id="3bd57-121">Ir para Ativos fixos > Entradas de diário > Diário de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="3bd57-121">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="3bd57-122">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="3bd57-122">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="3bd57-123">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="3bd57-123">Click Lines.</span></span>
4. <span data-ttu-id="3bd57-124">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="3bd57-124">Click Post.</span></span>


