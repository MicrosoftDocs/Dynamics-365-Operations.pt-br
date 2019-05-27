---
title: 'Definir contagem cíclica '
description: A contagem cíclica é um processo de depósito que você pode usar para auditar itens de estoque disponíveis.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2832547f81b0153d42ac4664184f18bd66f1acdd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571653"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="f62c7-103">Definir contagem cíclica </span><span class="sxs-lookup"><span data-stu-id="f62c7-103">Define cycle counting</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f62c7-104">A contagem cíclica é um processo de depósito que você pode usar para auditar itens de estoque disponíveis.</span><span class="sxs-lookup"><span data-stu-id="f62c7-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="f62c7-105">Essa gravação de tarefa mostra como: definir a prioridade de trabalho de contagem padrão; habilitar um item de menu de dispositivo móvel para processar operações de separação e contagem; habilitar um gatilho de limite de contagem quando um local ficar vazio e habilitar um plano de contagem cíclica de um item específico em um depósito específico.</span><span class="sxs-lookup"><span data-stu-id="f62c7-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="f62c7-106">Geralmente, essas tarefas são realizadas por um gerente de depósito.</span><span class="sxs-lookup"><span data-stu-id="f62c7-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="f62c7-107">Você pode ver todo esse procedimento na empresa de dados de demonstração USMF ou em seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="f62c7-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="f62c7-108">Definir a prioridade do trabalho de contagem</span><span class="sxs-lookup"><span data-stu-id="f62c7-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="f62c7-109">Vá para Gerenciamento de depósito > Configuração > Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="f62c7-109">Go to Warehouse management > Setup > Warehouse management parameters.</span></span>
2. <span data-ttu-id="f62c7-110">Clique na guia Contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="f62c7-110">Click the Cycle counting tab.</span></span>
3. <span data-ttu-id="f62c7-111">No campo Prioridade de trabalho de contagem cíclica padrão, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f62c7-111">In the Default cycle count work priority field, enter a number.</span></span>
    * <span data-ttu-id="f62c7-112">Esta etapa altera a prioridade de trabalho da contagem cíclica comparada a outros tipos de trabalho no depósito.</span><span class="sxs-lookup"><span data-stu-id="f62c7-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="f62c7-113">Inserindo um número menor que o número de outros tipos de trabalho você aumenta a prioridade do trabalho de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="f62c7-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="f62c7-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-114">Click Save.</span></span>
5. <span data-ttu-id="f62c7-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f62c7-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="f62c7-116">Habilitar o dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="f62c7-116">Enable the mobile device</span></span>
1. <span data-ttu-id="f62c7-117">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Itens de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f62c7-117">Go to Warehouse management > Setup > Mobile device > Mobile device menu items.</span></span>
2. <span data-ttu-id="f62c7-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-118">Click New.</span></span>
3. <span data-ttu-id="f62c7-119">No campo Item de menu, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-119">In the Menu item name field, type a value.</span></span>
4. <span data-ttu-id="f62c7-120">No campo Título, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-120">In the Title field, type a value.</span></span>
5. <span data-ttu-id="f62c7-121">No campo Modo, selecione 'Trabalho'.</span><span class="sxs-lookup"><span data-stu-id="f62c7-121">In the Mode field, select 'Work'.</span></span>
6. <span data-ttu-id="f62c7-122">Defina a opção Usar trabalho existente como Sim.</span><span class="sxs-lookup"><span data-stu-id="f62c7-122">Set the Use existing work option to Yes.</span></span>
    * <span data-ttu-id="f62c7-123">Ao definir esta opção como Sim, o sistema procurará um trabalho existente quando o item de menu de dispositivo móvel for usado.</span><span class="sxs-lookup"><span data-stu-id="f62c7-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="f62c7-124">No campo Direcionado por, selecione 'Direcionada pelo sistema'.</span><span class="sxs-lookup"><span data-stu-id="f62c7-124">In the Directed by field, select 'System directed'.</span></span>
    * <span data-ttu-id="f62c7-125">Quando "Sistema direcionado" for selecionado, o trabalhador de depósito será direcionado para abrir os trabalhos que estão em classes de trabalho definidas.</span><span class="sxs-lookup"><span data-stu-id="f62c7-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="f62c7-126">(Criaremos essas classes de trabalho em seguida.)</span><span class="sxs-lookup"><span data-stu-id="f62c7-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="f62c7-127">Expandir ou recolher a seção Classes de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f62c7-127">Expand or collapse the Work classes section.</span></span>
    * <span data-ttu-id="f62c7-128">Em seguida, vamos criar duas classes de trabalho que serão usadas com esse item de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f62c7-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="f62c7-129">Quando o item de menu for usado, essas classes de trabalho serão consultadas, o trabalho que tiver a prioridade maior será mostrado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="f62c7-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="f62c7-130">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-130">Click New.</span></span>
10. <span data-ttu-id="f62c7-131">No campo ID de classe de trabalho, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-131">In the Work class ID field, select a value.</span></span>
11. <span data-ttu-id="f62c7-132">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-132">Click New.</span></span>
12. <span data-ttu-id="f62c7-133">No campo ID de classe de trabalho, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-133">In the Work class ID field, select a value.</span></span>
13. <span data-ttu-id="f62c7-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-134">Click Save.</span></span>
14. <span data-ttu-id="f62c7-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f62c7-135">Close the page.</span></span>
15. <span data-ttu-id="f62c7-136">Vá para Gerenciamento de depósito > Configuração > Dispositivo móvel > Menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="f62c7-136">Go to Warehouse management > Setup > Mobile device > Mobile device menu.</span></span>
16. <span data-ttu-id="f62c7-137">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="f62c7-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="f62c7-138">Na árvore, selecione o item de menu que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="f62c7-139">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-139">Click Edit.</span></span>
19. <span data-ttu-id="f62c7-140">Clique na seta para adicionar o item de menu ao menu.</span><span class="sxs-lookup"><span data-stu-id="f62c7-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="f62c7-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-141">Click Save.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="f62c7-142">Criar um limite de contagem</span><span class="sxs-lookup"><span data-stu-id="f62c7-142">Create a counting threshold</span></span>
1. <span data-ttu-id="f62c7-143">Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Limites de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="f62c7-143">Go to Warehouse management > Setup > Cycle counting > Cycle count thresholds.</span></span>
2. <span data-ttu-id="f62c7-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-144">Click New.</span></span>
3. <span data-ttu-id="f62c7-145">No campo ID do limite de contagem cíclica, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-145">In the Cycle counting threshold ID field, type a value.</span></span>
4. <span data-ttu-id="f62c7-146">Defina a opção Processar contagem cíclica imediatamente como Sim.</span><span class="sxs-lookup"><span data-stu-id="f62c7-146">Set the Process cycle counting immediately option to Yes.</span></span>
5. <span data-ttu-id="f62c7-147">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-147">In the Description field, type a value.</span></span>
6. <span data-ttu-id="f62c7-148">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-148">Click Save.</span></span>
7. <span data-ttu-id="f62c7-149">Clique em Selecionar localizações.</span><span class="sxs-lookup"><span data-stu-id="f62c7-149">Click Select locations.</span></span>
8. <span data-ttu-id="f62c7-150">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f62c7-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="f62c7-151">No campo Critérios, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-151">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="f62c7-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f62c7-152">Click OK.</span></span>
11. <span data-ttu-id="f62c7-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f62c7-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="f62c7-154">Criar um plano de contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="f62c7-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="f62c7-155">Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Planos de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="f62c7-155">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="f62c7-156">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-156">Click New.</span></span>
3. <span data-ttu-id="f62c7-157">No campo ID do plano de contagem cíclica, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-157">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="f62c7-158">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-158">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f62c7-159">No campo Número máximo de contagens cíclicas, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f62c7-159">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="f62c7-160">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-160">Click Save.</span></span>
7. <span data-ttu-id="f62c7-161">Clique em Selecionar localizações.</span><span class="sxs-lookup"><span data-stu-id="f62c7-161">Click Select locations.</span></span>
8. <span data-ttu-id="f62c7-162">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f62c7-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="f62c7-163">No campo Critérios, selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-163">In the Criteria field, select a value.</span></span>
10. <span data-ttu-id="f62c7-164">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f62c7-164">Click OK.</span></span>
11. <span data-ttu-id="f62c7-165">No campo Dias entre a contagem cíclica, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f62c7-165">In the Days between cycle counting field, enter a number.</span></span>
    * <span data-ttu-id="f62c7-166">Por exemplo, se o campo Dias entre a contagem cíclica for 5, o trabalho de contagem cíclica será criado a cada cinco dias.</span><span class="sxs-lookup"><span data-stu-id="f62c7-166">For example, if the Days between cycle counting field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="f62c7-167">No entanto, se o trabalho de contagem cíclica for processado no dia três, o próximo trabalho de contagem cíclica será criado cinco dias após a última contagem cíclica ter sido processada, no dia oito.</span><span class="sxs-lookup"><span data-stu-id="f62c7-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="f62c7-168">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-168">Click Save.</span></span>
13. <span data-ttu-id="f62c7-169">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f62c7-169">Click New.</span></span>
14. <span data-ttu-id="f62c7-170">No campo de número de sequência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="f62c7-170">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="f62c7-171">A ordem de classificação é do número menor para o número maior.</span><span class="sxs-lookup"><span data-stu-id="f62c7-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="f62c7-172">O valor deve ser maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="f62c7-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="f62c7-173">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f62c7-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="f62c7-174">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-174">In the Description field, type a value.</span></span>
17. <span data-ttu-id="f62c7-175">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f62c7-175">Click Save.</span></span>
18. <span data-ttu-id="f62c7-176">Clique em Definir consulta de produto.</span><span class="sxs-lookup"><span data-stu-id="f62c7-176">Click Define product query.</span></span>
19. <span data-ttu-id="f62c7-177">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f62c7-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="f62c7-178">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f62c7-178">In the Criteria field, enter or select a value.</span></span>
21. <span data-ttu-id="f62c7-179">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f62c7-179">Click OK.</span></span>
22. <span data-ttu-id="f62c7-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f62c7-180">Close the page.</span></span>

