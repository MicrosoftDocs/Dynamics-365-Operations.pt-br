--- 
title: "Criar atividades de transferência para lean manufacturing"
description: "Crie uma atividade de transferência para lean manufacturing."
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 010ac08fa96ead49b6ecbbe083e59fb96427e29e
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="913a2-103">Criar atividades de transferência para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="913a2-103">Create transfer activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="913a2-104">Crie uma atividade de transferência para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="913a2-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="913a2-105">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="913a2-105">Prerequisites:</span></span> 

1. <span data-ttu-id="913a2-106">Um fluxo de produção e versão que não estão ativos devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="913a2-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="913a2-107">É necessário criar os depósitos de origem e de destino e os locais.</span><span class="sxs-lookup"><span data-stu-id="913a2-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="913a2-108">Opcionalmente, o reabastecimento ou a célula de trabalho reabastecida devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="913a2-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="913a2-109">Localizar a versão do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="913a2-109">Find the production flow version</span></span>
1. <span data-ttu-id="913a2-110">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="913a2-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="913a2-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="913a2-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="913a2-112">Observe que o fluxo de produção deve ter uma versão em status de rascunho.</span><span class="sxs-lookup"><span data-stu-id="913a2-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="913a2-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="913a2-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="913a2-114">Criar uma atividade</span><span class="sxs-lookup"><span data-stu-id="913a2-114">Create a new activity</span></span>
1. <span data-ttu-id="913a2-115">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="913a2-115">Click Activities.</span></span>
    * <span data-ttu-id="913a2-116">Verifique se o fluxo de produção selecionado tem uma versão de rascunho e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="913a2-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="913a2-117">Clique em Criar uma atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="913a2-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="913a2-118">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="913a2-118">Click Next.</span></span>
4. <span data-ttu-id="913a2-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="913a2-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="913a2-120">No campo Tipo de atividade, selecione 'Transferência'.</span><span class="sxs-lookup"><span data-stu-id="913a2-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="913a2-121">No campo Quantidade processada, insira um número.</span><span class="sxs-lookup"><span data-stu-id="913a2-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="913a2-122">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="913a2-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="913a2-123">Selecionar as células de trabalho</span><span class="sxs-lookup"><span data-stu-id="913a2-123">Select the Work cells</span></span>
1. <span data-ttu-id="913a2-124">No campo Reabastecimento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="913a2-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="913a2-125">Para usar o local de saída da célula de trabalho como o local de origem na atividade de transferência, selecione uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="913a2-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="913a2-126">O mesmo pode ser feito com a célula de trabalho reabastecida, que define o local de destino da atividade de transferência.</span><span class="sxs-lookup"><span data-stu-id="913a2-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="913a2-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="913a2-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="913a2-128">Definir as atualizações de estoque</span><span class="sxs-lookup"><span data-stu-id="913a2-128">Define the inventory updates</span></span>
1. <span data-ttu-id="913a2-129">No campo Tipo de produto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="913a2-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="913a2-130">Observe que uma transferência não altera o tipo de produto.</span><span class="sxs-lookup"><span data-stu-id="913a2-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="913a2-131">Você pode transferir produtos finalizados ou semifinalizados (transferência entre duas atividades de um fluxo de produto e possivelmente um fluxo kanban).</span><span class="sxs-lookup"><span data-stu-id="913a2-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="913a2-132">Na transferência de produtos finalizados, você pode selecionar se deseja separar ou receber resultados em uma transação de estoque.</span><span class="sxs-lookup"><span data-stu-id="913a2-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="913a2-133">Definir os locais de transferência</span><span class="sxs-lookup"><span data-stu-id="913a2-133">Define the transfer locations</span></span>
1. <span data-ttu-id="913a2-134">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="913a2-134">Click Next.</span></span>
2. <span data-ttu-id="913a2-135">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="913a2-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="913a2-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="913a2-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="913a2-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="913a2-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="913a2-138">No campo Localização, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="913a2-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="913a2-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="913a2-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="913a2-140">No campo Fretado por, selecione 'Expedidor'.</span><span class="sxs-lookup"><span data-stu-id="913a2-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="913a2-141">As opções incluem: Expedidor - a organização que opera o depósito de remessa, Destinatário - a organização que opera o depósito de recebimento, Transportadora - um fornecedor externo.</span><span class="sxs-lookup"><span data-stu-id="913a2-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="913a2-142">Se a organização operacional for um fornecedor, a atividade de transferência precisará de um contrato de subcontratação.</span><span class="sxs-lookup"><span data-stu-id="913a2-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="913a2-143">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="913a2-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="913a2-144">Definir os períodos de atividade</span><span class="sxs-lookup"><span data-stu-id="913a2-144">Define the activity times</span></span>
1. <span data-ttu-id="913a2-145">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="913a2-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="913a2-146">A definição de um tempo de execução é necessária.</span><span class="sxs-lookup"><span data-stu-id="913a2-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="913a2-147">O tempo de execução é usado para calcular custos e as horas de produtividade dos trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="913a2-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="913a2-148">Os tempos de execução não são usados para calcular a carga de capacidade e o consumo, que são calculados pelo ciclo de tempo, derivadas da tarefa de versão do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="913a2-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="913a2-149">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="913a2-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="913a2-150">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="913a2-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="913a2-151">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="913a2-151">Select the Time unit.</span></span>
5. <span data-ttu-id="913a2-152">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="913a2-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="913a2-153">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="913a2-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="913a2-154">Tempos de espera são opcionais.</span><span class="sxs-lookup"><span data-stu-id="913a2-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="913a2-155">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="913a2-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="913a2-156">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="913a2-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="913a2-157">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="913a2-157">Select the Time unit.</span></span>
10. <span data-ttu-id="913a2-158">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="913a2-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="913a2-159">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="913a2-159">Click Next.</span></span>
12. <span data-ttu-id="913a2-160">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="913a2-160">Click Finish.</span></span>
13. <span data-ttu-id="913a2-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="913a2-161">Close the page.</span></span>


