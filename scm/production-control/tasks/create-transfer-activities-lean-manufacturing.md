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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e5f28b26cee2501f1294cd34a495ee925e6b1ba8
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="194fa-103">Criar atividades de transferência para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="194fa-103">Create transfer activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="194fa-104">Crie uma atividade de transferência para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="194fa-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="194fa-105">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="194fa-105">Prerequisites:</span></span> 

1. <span data-ttu-id="194fa-106">Um fluxo de produção e versão que não estão ativos devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="194fa-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="194fa-107">É necessário criar os depósitos de origem e de destino e os locais.</span><span class="sxs-lookup"><span data-stu-id="194fa-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="194fa-108">Opcionalmente, o reabastecimento ou a célula de trabalho reabastecida devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="194fa-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="194fa-109">Localizar a versão do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="194fa-109">Find the production flow version</span></span>
1. <span data-ttu-id="194fa-110">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="194fa-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="194fa-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="194fa-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="194fa-112">Observe que o fluxo de produção deve ter uma versão em status de rascunho.</span><span class="sxs-lookup"><span data-stu-id="194fa-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="194fa-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="194fa-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="194fa-114">Criar uma atividade</span><span class="sxs-lookup"><span data-stu-id="194fa-114">Create a new activity</span></span>
1. <span data-ttu-id="194fa-115">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="194fa-115">Click Activities.</span></span>
    * <span data-ttu-id="194fa-116">Verifique se o fluxo de produção selecionado tem uma versão de rascunho e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="194fa-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="194fa-117">Clique em Criar uma atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="194fa-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="194fa-118">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="194fa-118">Click Next.</span></span>
4. <span data-ttu-id="194fa-119">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="194fa-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="194fa-120">No campo Tipo de atividade, selecione 'Transferência'.</span><span class="sxs-lookup"><span data-stu-id="194fa-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="194fa-121">No campo Quantidade processada, insira um número.</span><span class="sxs-lookup"><span data-stu-id="194fa-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="194fa-122">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="194fa-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="194fa-123">Selecionar as células de trabalho</span><span class="sxs-lookup"><span data-stu-id="194fa-123">Select the Work cells</span></span>
1. <span data-ttu-id="194fa-124">No campo Reabastecimento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="194fa-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="194fa-125">Para usar o local de saída da célula de trabalho como o local de origem na atividade de transferência, selecione uma célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="194fa-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="194fa-126">O mesmo pode ser feito com a célula de trabalho reabastecida, que define o local de destino da atividade de transferência.</span><span class="sxs-lookup"><span data-stu-id="194fa-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="194fa-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="194fa-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="194fa-128">Definir as atualizações de estoque</span><span class="sxs-lookup"><span data-stu-id="194fa-128">Define the inventory updates</span></span>
1. <span data-ttu-id="194fa-129">No campo Tipo de produto, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="194fa-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="194fa-130">Observe que uma transferência não altera o tipo de produto.</span><span class="sxs-lookup"><span data-stu-id="194fa-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="194fa-131">Você pode transferir produtos finalizados ou semifinalizados (transferência entre duas atividades de um fluxo de produto e possivelmente um fluxo kanban).</span><span class="sxs-lookup"><span data-stu-id="194fa-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="194fa-132">Na transferência de produtos finalizados, você pode selecionar se deseja separar ou receber resultados em uma transação de estoque.</span><span class="sxs-lookup"><span data-stu-id="194fa-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="194fa-133">Definir os locais de transferência</span><span class="sxs-lookup"><span data-stu-id="194fa-133">Define the transfer locations</span></span>
1. <span data-ttu-id="194fa-134">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="194fa-134">Click Next.</span></span>
2. <span data-ttu-id="194fa-135">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="194fa-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="194fa-136">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="194fa-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="194fa-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="194fa-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="194fa-138">No campo Localização, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="194fa-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="194fa-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="194fa-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="194fa-140">No campo Fretado por, selecione 'Expedidor'.</span><span class="sxs-lookup"><span data-stu-id="194fa-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="194fa-141">As opções incluem: Expedidor - a organização que opera o depósito de remessa, Destinatário - a organização que opera o depósito de recebimento, Transportadora - um fornecedor externo.</span><span class="sxs-lookup"><span data-stu-id="194fa-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="194fa-142">Se a organização operacional for um fornecedor, a atividade de transferência precisará de um contrato de subcontratação.</span><span class="sxs-lookup"><span data-stu-id="194fa-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="194fa-143">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="194fa-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="194fa-144">Definir os períodos de atividade</span><span class="sxs-lookup"><span data-stu-id="194fa-144">Define the activity times</span></span>
1. <span data-ttu-id="194fa-145">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="194fa-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="194fa-146">A definição de um tempo de execução é necessária.</span><span class="sxs-lookup"><span data-stu-id="194fa-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="194fa-147">O tempo de execução é usado para calcular custos e as horas de produtividade dos trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="194fa-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="194fa-148">Os tempos de execução não são usados para calcular a carga de capacidade e o consumo, que são calculados pelo ciclo de tempo, derivadas da tarefa de versão do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="194fa-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="194fa-149">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="194fa-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="194fa-150">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="194fa-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="194fa-151">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="194fa-151">Select the Time unit.</span></span>
5. <span data-ttu-id="194fa-152">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="194fa-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="194fa-153">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="194fa-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="194fa-154">Tempos de espera são opcionais.</span><span class="sxs-lookup"><span data-stu-id="194fa-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="194fa-155">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="194fa-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="194fa-156">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="194fa-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="194fa-157">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="194fa-157">Select the Time unit.</span></span>
10. <span data-ttu-id="194fa-158">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="194fa-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="194fa-159">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="194fa-159">Click Next.</span></span>
12. <span data-ttu-id="194fa-160">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="194fa-160">Click Finish.</span></span>
13. <span data-ttu-id="194fa-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="194fa-161">Close the page.</span></span>


