---
title: Criar uma regra kanban de quantidade fixa para fabricação
description: Este procedimento tem como foco a configuração necessária para criar uma regra kanban de fabricação fixa para ativação de atividades de transformação, em uma célula de trabalho, em um ambiente de lean manufacturing.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fcf2aa32ee9f89649ce8ce0afaf50b0facf053ce
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838694"
---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="4e872-103">Criar uma regra kanban de quantidade fixa para fabricação</span><span class="sxs-lookup"><span data-stu-id="4e872-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e872-104">Este procedimento tem como foco a configuração necessária para criar uma regra kanban de fabricação fixa para ativação de atividades de transformação, em uma célula de trabalho, em um ambiente de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="4e872-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="4e872-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="4e872-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4e872-106">Este procedimento destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam a produção de um produto novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="4e872-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="4e872-107">Criar regra kanban</span><span class="sxs-lookup"><span data-stu-id="4e872-107">Create new kanban rule</span></span>
1. <span data-ttu-id="4e872-108">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="4e872-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="4e872-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4e872-109">Click New.</span></span>
    * <span data-ttu-id="4e872-110">Observe que o tipo padrão é fabricação e a estratégia de reabastecimento é fixa.</span><span class="sxs-lookup"><span data-stu-id="4e872-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="4e872-111">Você não precisa alterar esses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="4e872-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="4e872-112">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4e872-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="4e872-113">Esta é a atividade que será realizada para kanbans criados com base nesta regra kanban.</span><span class="sxs-lookup"><span data-stu-id="4e872-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="4e872-114">Selecione 'SpeakerTestAndPackaging'.</span><span class="sxs-lookup"><span data-stu-id="4e872-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="4e872-115">Expanda a seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="4e872-115">Expand the Details section.</span></span>
5. <span data-ttu-id="4e872-116">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4e872-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="4e872-117">Selecione L0050.</span><span class="sxs-lookup"><span data-stu-id="4e872-117">Select L0050.</span></span>  
6. <span data-ttu-id="4e872-118">No campo Unidade de medida, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4e872-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="4e872-119">Selecione minutos.</span><span class="sxs-lookup"><span data-stu-id="4e872-119">Select minutes.</span></span>  
7. <span data-ttu-id="4e872-120">No campo Prazo de entrega, insira um número.</span><span class="sxs-lookup"><span data-stu-id="4e872-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="4e872-121">Digite 5.</span><span class="sxs-lookup"><span data-stu-id="4e872-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="4e872-122">Definir quantidades</span><span class="sxs-lookup"><span data-stu-id="4e872-122">Set quantities</span></span>
1. <span data-ttu-id="4e872-123">Expanda a seção Quantidades.</span><span class="sxs-lookup"><span data-stu-id="4e872-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="4e872-124">Defina Quantidade padrão como '10'.</span><span class="sxs-lookup"><span data-stu-id="4e872-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="4e872-125">Esta é a quantidade que será transferida para cada kanban.</span><span class="sxs-lookup"><span data-stu-id="4e872-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="4e872-126">Marque a caixa de seleção Variação de quantidade de produto.</span><span class="sxs-lookup"><span data-stu-id="4e872-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="4e872-127">Com ela, os kanbans selecionados podem ser concluídos com uma variação da quantidade padrão.</span><span class="sxs-lookup"><span data-stu-id="4e872-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="4e872-128">Para permitir que os kanbans sejam concluídos com a quantidade de 8 a 12, defina ambas as variações como 2.</span><span class="sxs-lookup"><span data-stu-id="4e872-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="4e872-129">Defina Variação abaixo como '2'.</span><span class="sxs-lookup"><span data-stu-id="4e872-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="4e872-130">Isso permitirá a conclusão até 10 - 2 = 8</span><span class="sxs-lookup"><span data-stu-id="4e872-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="4e872-131">Defina Variação acima como '2'.</span><span class="sxs-lookup"><span data-stu-id="4e872-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="4e872-132">Isso permitirá a conclusão até 10 + 2 = 12</span><span class="sxs-lookup"><span data-stu-id="4e872-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="4e872-133">No campo Quantidade de kanbans fixa, insira um número.</span><span class="sxs-lookup"><span data-stu-id="4e872-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="4e872-134">Este é o valor de kanbans que deve ser ativado.</span><span class="sxs-lookup"><span data-stu-id="4e872-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="4e872-135">Neste caso, 5 kanbans que processam 10 de cada.</span><span class="sxs-lookup"><span data-stu-id="4e872-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="4e872-136">No campo Valor mínimo de limite de alerta, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="4e872-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="4e872-137">Usado para manter o controle do valor mínimo de kanbans completos que devem estar no destino.</span><span class="sxs-lookup"><span data-stu-id="4e872-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="4e872-138">Por exemplo, ele é usado na visão geral da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="4e872-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="4e872-139">No campo Valor máximo de limite de alerta, insira '4'.</span><span class="sxs-lookup"><span data-stu-id="4e872-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="4e872-140">Usado para manter o controle do valor máximo de kanbans completos que devem estar no destino.</span><span class="sxs-lookup"><span data-stu-id="4e872-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="4e872-141">Por exemplo, ele é usado na visão geral da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="4e872-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="4e872-142">No campo Quantidade de planejamento automático, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="4e872-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="4e872-143">A liquidação dele até 1 significa que cada kanban será planejado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4e872-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="4e872-144">Se inseríssemos 3, os kanbans não seriam planejados até 3 kanbans vazios estarem prontos para planejamento.</span><span class="sxs-lookup"><span data-stu-id="4e872-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="4e872-145">Isso é útil para agrupar trabalho e evitar excesso de configuração.</span><span class="sxs-lookup"><span data-stu-id="4e872-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="4e872-146">Criar Kanbans</span><span class="sxs-lookup"><span data-stu-id="4e872-146">Create Kanbans</span></span>
1. <span data-ttu-id="4e872-147">Expanda a seção kanbans.</span><span class="sxs-lookup"><span data-stu-id="4e872-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="4e872-148">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e872-148">Click Save.</span></span>
    * <span data-ttu-id="4e872-149">A regra kanban precisa ser salva antes de kanbans poderem ser criados.</span><span class="sxs-lookup"><span data-stu-id="4e872-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="4e872-150">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4e872-150">Click Add.</span></span>
    * <span data-ttu-id="4e872-151">Observe que não há kanbans ativos, por isso, o 'Número de novos kanbans' sugerido é 5.</span><span class="sxs-lookup"><span data-stu-id="4e872-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="4e872-152">É o mesmo número da 'Quantidade fixa de kanbans'.</span><span class="sxs-lookup"><span data-stu-id="4e872-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="4e872-153">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="4e872-153">Click Create.</span></span>
    * <span data-ttu-id="4e872-154">Isso criará 5 kanbans.</span><span class="sxs-lookup"><span data-stu-id="4e872-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="4e872-155">Note que 5 kanbans, para cada 10, foram criados para essa regra kanban de fabricação.</span><span class="sxs-lookup"><span data-stu-id="4e872-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="4e872-156">Esta é a última etapa do procedimento.</span><span class="sxs-lookup"><span data-stu-id="4e872-156">This is the last step in this procedure.</span></span>  

