--- 
title: "Trabalhos de produção sequencial para manufatura de processos"
description: Este procedimento usa produtos de pintura como um exemplo para mostrar como sequenciar ordens planejadas de acordo com a prioridade de cor e de tamanho de pacote.
author: ChristianRytt
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: eacf61e432bd9b8c6b90f25e2cf0a2528a2ad932
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="65798-103">Trabalhos de produção sequencial para manufatura de processos</span><span class="sxs-lookup"><span data-stu-id="65798-103">Sequence production jobs for process manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65798-104">Este procedimento usa produtos de pintura como um exemplo para mostrar como sequenciar ordens planejadas de acordo com a prioridade de cor e de tamanho de pacote.</span><span class="sxs-lookup"><span data-stu-id="65798-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="65798-105">A empresa de dados demo usada para criar este procedimento é USPI.</span><span class="sxs-lookup"><span data-stu-id="65798-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="65798-106">Esse procedimento é criado para o planejador de produção.</span><span class="sxs-lookup"><span data-stu-id="65798-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="65798-107">Executar planejamento mestre para USPI</span><span class="sxs-lookup"><span data-stu-id="65798-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="65798-108">Vá para Planejamento mestre > Planejamento mestre > Executar > Planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="65798-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="65798-109">No campo Plano mestre, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="65798-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="65798-110">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="65798-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="65798-111">Selecionar MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="65798-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="65798-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="65798-112">Click OK.</span></span>
    * <span data-ttu-id="65798-113">Isso inicia o planejamento mestre, incluindo o processo de sequência.</span><span class="sxs-lookup"><span data-stu-id="65798-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="65798-114">Esse processo pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="65798-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="65798-115">Exibir ordens planejadas para os produtos de pintura</span><span class="sxs-lookup"><span data-stu-id="65798-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="65798-116">Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="65798-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="65798-117">Expanda a FactBox detalhes do item.</span><span class="sxs-lookup"><span data-stu-id="65798-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="65798-118">Expanda a FactBox detalhes da programação.</span><span class="sxs-lookup"><span data-stu-id="65798-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="65798-119">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="65798-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="65798-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="65798-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="65798-121">Selecionar MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="65798-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="65798-122">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="65798-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="65798-123">Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="65798-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="65798-124">Desbloquear para rolar à direita para ver a data da ordem e a data de entrega.</span><span class="sxs-lookup"><span data-stu-id="65798-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="65798-125">Observe que esses itens têm uma data de pedido de Hoje e as datas de entrega para as ordens planejadas não estão em sequência após a prioridade de cor e tamanho de pacote, como exibido no nome do produto.</span><span class="sxs-lookup"><span data-stu-id="65798-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="65798-126">Você pode passar o mouse sobre um número de item para ver o nome do produto e a prioridade.</span><span class="sxs-lookup"><span data-stu-id="65798-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="65798-127">Ordens planejadas em sequência para pintura</span><span class="sxs-lookup"><span data-stu-id="65798-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="65798-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="65798-128">Close the page.</span></span>
2. <span data-ttu-id="65798-129">Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas sequenciais.</span><span class="sxs-lookup"><span data-stu-id="65798-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="65798-130">Expanda a FactBox detalhes do item.</span><span class="sxs-lookup"><span data-stu-id="65798-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="65798-131">Expanda a FactBox detalhes da programação.</span><span class="sxs-lookup"><span data-stu-id="65798-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="65798-132">Observação: Aqui você verá que a data de início/hora das ordens planejadas é arranjada na sequência de acordo com a cor e tamanho da embalagem dentro de um período de classificação de 28 dias.</span><span class="sxs-lookup"><span data-stu-id="65798-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="65798-133">Os períodos são definidos por um número no campo Campanha.</span><span class="sxs-lookup"><span data-stu-id="65798-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="65798-134">O formulário de ordem planejada sequenciado atua como o formulário de ordem planejada típico, e o planejador de produção pode confirmar ordens planejadas aqui.</span><span class="sxs-lookup"><span data-stu-id="65798-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="65798-135">Marcar todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="65798-135">Mark all rows.</span></span>
6. <span data-ttu-id="65798-136">Clique em Aceitar.</span><span class="sxs-lookup"><span data-stu-id="65798-136">Click Accept.</span></span>
    * <span data-ttu-id="65798-137">Isso atualizará as ordens planejadas com a ação selecionada da sequência de Adiar ou Avançar.</span><span class="sxs-lookup"><span data-stu-id="65798-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="65798-138">Verifique a sequência das ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="65798-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="65798-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="65798-139">Close the page.</span></span>
2. <span data-ttu-id="65798-140">Vá para Planejamento mestre > Planejamento mestre > Ordens planejadas.</span><span class="sxs-lookup"><span data-stu-id="65798-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="65798-141">Expanda a FactBox detalhes do item.</span><span class="sxs-lookup"><span data-stu-id="65798-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="65798-142">Expanda a FactBox detalhes da programação.</span><span class="sxs-lookup"><span data-stu-id="65798-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="65798-143">No campo Plano, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="65798-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="65798-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="65798-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="65798-145">Selecionar MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="65798-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="65798-146">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="65798-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="65798-147">Use o Filtro Rápido para filtrar o campo Número do item com o valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="65798-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="65798-148">Observe que as ordens são arranjadas agora na sequência de acordo com a prioridade de cor e tamanho e as ordens planejadas se iniciam na data de ordem mais antiga e data de entrega.</span><span class="sxs-lookup"><span data-stu-id="65798-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="65798-149">Validar a coluna Data da ordem ou Data de início no Quadro de Fatos de detalhes do plano.</span><span class="sxs-lookup"><span data-stu-id="65798-149">Validate the Order date column or the Start date in the Schedule details FactBox.</span></span>  


