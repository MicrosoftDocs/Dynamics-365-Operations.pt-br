--- 
title: Criar atividades de processo para lean manufacturing
description: Crie uma atividade de processo para lean manufacturing.
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c1e7cb939c9b936a58486de13f73150aebccb548
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="0f30a-103">Criar atividades de processo para lean manufacturing</span><span class="sxs-lookup"><span data-stu-id="0f30a-103">Create process activities for lean manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f30a-104">Crie uma atividade de processo para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="0f30a-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="0f30a-105">Pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="0f30a-105">Prerequisites:</span></span> 

1. <span data-ttu-id="0f30a-106">Um fluxo de produção e versão que não estão ativos devem ser criados.</span><span class="sxs-lookup"><span data-stu-id="0f30a-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="0f30a-107">Uma célula de trabalho deve ser criada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="0f30a-108">Localizar a versão do fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="0f30a-108">Find the production flow version</span></span>
1. <span data-ttu-id="0f30a-109">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="0f30a-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="0f30a-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f30a-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="0f30a-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="0f30a-112">Criar uma atividade</span><span class="sxs-lookup"><span data-stu-id="0f30a-112">Create a new activity</span></span>
1. <span data-ttu-id="0f30a-113">Clique em Atividades.</span><span class="sxs-lookup"><span data-stu-id="0f30a-113">Click Activities.</span></span>
    * <span data-ttu-id="0f30a-114">Verifique se o fluxo de produção selecionado tem uma versão de rascunho e selecione-a.</span><span class="sxs-lookup"><span data-stu-id="0f30a-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="0f30a-115">Clique em Criar uma atividade do plano.</span><span class="sxs-lookup"><span data-stu-id="0f30a-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="0f30a-116">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-116">Click Next.</span></span>
4. <span data-ttu-id="0f30a-117">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f30a-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="0f30a-118">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f30a-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="0f30a-119">Vale notar que o nome deve ser exclusivo para um determinado fluxo de produção para todas as versões.</span><span class="sxs-lookup"><span data-stu-id="0f30a-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="0f30a-120">No campo Quantidade processada, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f30a-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="0f30a-121">Independentemente da quantidade de trabalho a ser processada, essa é a quantidade mínima por trabalho para cálculo do custo de mão de obra.</span><span class="sxs-lookup"><span data-stu-id="0f30a-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="0f30a-122">Se as quantidades de trabalho divergirem dessa quantidade, uma variação de custo de mão de obra será criada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="0f30a-123">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="0f30a-124">Selecionar a célula de trabalho</span><span class="sxs-lookup"><span data-stu-id="0f30a-124">Select the work cell</span></span>
1. <span data-ttu-id="0f30a-125">No campo Célula de trabalho, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f30a-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="0f30a-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="0f30a-127">Definir as atualizações de estoque</span><span class="sxs-lookup"><span data-stu-id="0f30a-127">Define the inventory updates</span></span>
1. <span data-ttu-id="0f30a-128">Selecione ou desmarque a caixa de seleção Atualizar recebimento disponível.</span><span class="sxs-lookup"><span data-stu-id="0f30a-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="0f30a-129">Em caso de Atualizar disponibilidade = Não, você pode definir a atividade para receber um produto semifinalizado (a atividade não chega ao próximo nível de BOM).</span><span class="sxs-lookup"><span data-stu-id="0f30a-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="0f30a-130">Você também pode optar por consumir produtos semifinalizados.</span><span class="sxs-lookup"><span data-stu-id="0f30a-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="0f30a-131">Definir as atividades de separação</span><span class="sxs-lookup"><span data-stu-id="0f30a-131">Define the picking activities</span></span>
1. <span data-ttu-id="0f30a-132">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-132">Click Next.</span></span>
2. <span data-ttu-id="0f30a-133">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="0f30a-134">Uma atividade de separação padrão é criada para o local de entrada da célula de trabalho selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="0f30a-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-135">Click Add.</span></span>
    * <span data-ttu-id="0f30a-136">Você pode criar atividades de separação adicionais para produtos específicos, que não são preparados na atividade de entrada da célula de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f30a-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="0f30a-137">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f30a-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="0f30a-138">No campo Número de item, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f30a-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="0f30a-139">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="0f30a-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="0f30a-140">Com essa definição, todos os materiais consumidos na atividade são separados no depósito e local de entrada padrão, com exceção do item que é definido na segunda atividade de separação.</span><span class="sxs-lookup"><span data-stu-id="0f30a-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="0f30a-141">Esse item será separado em um depósito e local diferentes.</span><span class="sxs-lookup"><span data-stu-id="0f30a-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="0f30a-142">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f30a-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="0f30a-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f30a-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="0f30a-144">Selecione ou desmarque a caixa de seleção Registrar sucata.</span><span class="sxs-lookup"><span data-stu-id="0f30a-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="0f30a-145">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="0f30a-146">Definir os períodos de atividade</span><span class="sxs-lookup"><span data-stu-id="0f30a-146">Define the activity times</span></span>
1. <span data-ttu-id="0f30a-147">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f30a-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0f30a-148">A definição de um tempo de execução é necessária.</span><span class="sxs-lookup"><span data-stu-id="0f30a-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="0f30a-149">O tempo de execução é usado para calcular custos e as horas de produtividade dos trabalhos kanban.</span><span class="sxs-lookup"><span data-stu-id="0f30a-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="0f30a-150">Os tempos de execução não são usados para calcular a capacidade máxima e o consumo, que são calculados pelo tempo de ciclo, derivados da tarefa de versão do fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="0f30a-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="0f30a-151">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f30a-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="0f30a-152">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f30a-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="0f30a-153">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="0f30a-153">Select the Time unit.</span></span>
5. <span data-ttu-id="0f30a-154">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f30a-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="0f30a-155">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="0f30a-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="0f30a-156">Tempos de espera são opcionais.</span><span class="sxs-lookup"><span data-stu-id="0f30a-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="0f30a-157">No campo Hora, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f30a-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="0f30a-158">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f30a-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="0f30a-159">Selecione a unidade Hora.</span><span class="sxs-lookup"><span data-stu-id="0f30a-159">Select the Time unit.</span></span>
10. <span data-ttu-id="0f30a-160">No campo Por quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f30a-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="0f30a-161">Clique em Avançar.</span><span class="sxs-lookup"><span data-stu-id="0f30a-161">Click Next.</span></span>
12. <span data-ttu-id="0f30a-162">Clique em Finish (Concluir).</span><span class="sxs-lookup"><span data-stu-id="0f30a-162">Click Finish.</span></span>
13. <span data-ttu-id="0f30a-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f30a-163">Close the page.</span></span>


