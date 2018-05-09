--- 
title: Criar uma regra kanban de retirada
description: "Este procedimento mostra a configuração necessária para criar uma regra kanban de saída para transferir o material em um ambiente de lean."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: b533d1b7b0c92fd6072500f2856036f0dffb7809
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="5a527-103">Criar uma regra kanban de retirada</span><span class="sxs-lookup"><span data-stu-id="5a527-103">Create a withdrawal kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a527-104">Este procedimento mostra a configuração necessária para criar uma regra kanban de saída para transferir o material em um ambiente de lean.</span><span class="sxs-lookup"><span data-stu-id="5a527-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="5a527-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="5a527-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="5a527-106">Este procedimento destina-se ao Engenheiro do processo ou Gerente de fluxo de valor, pois eles preparam o reabastecimento de um material novo ou modificado.</span><span class="sxs-lookup"><span data-stu-id="5a527-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="5a527-107">Criar regra kanban</span><span class="sxs-lookup"><span data-stu-id="5a527-107">Create new kanban rule</span></span>
1. <span data-ttu-id="5a527-108">Vá para Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="5a527-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="5a527-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5a527-109">Click New.</span></span>
3. <span data-ttu-id="5a527-110">No campo Tipo, selecione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="5a527-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="5a527-111">O tipo de retirada é usado para que as regras kanban transfiram o material ou as mercadorias.</span><span class="sxs-lookup"><span data-stu-id="5a527-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="5a527-112">No campo Primeira atividade do plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5a527-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="5a527-113">Selecione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="5a527-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="5a527-114">Essa atividade é configurada para mover os componentes do depósito 11, do local 11 para o armazenamento 12, do local 12.</span><span class="sxs-lookup"><span data-stu-id="5a527-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="5a527-115">No campo Produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5a527-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="5a527-116">Selecione M0007.</span><span class="sxs-lookup"><span data-stu-id="5a527-116">Select M0007.</span></span>  
6. <span data-ttu-id="5a527-117">No campo Prazo de entrega, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5a527-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="5a527-118">Por exemplo, 60.</span><span class="sxs-lookup"><span data-stu-id="5a527-118">For example, 60.</span></span>  
7. <span data-ttu-id="5a527-119">No campo Unidade de medida, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5a527-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="5a527-120">Por exemplo, Minutos.</span><span class="sxs-lookup"><span data-stu-id="5a527-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="5a527-121">Definir quantidades de kanban</span><span class="sxs-lookup"><span data-stu-id="5a527-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="5a527-122">Defina Quantidade padrão como '5'.</span><span class="sxs-lookup"><span data-stu-id="5a527-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="5a527-123">Esta é a quantidade que será transferida para cada kanban.</span><span class="sxs-lookup"><span data-stu-id="5a527-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="5a527-124">No campo Quantidade kanban fixo, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="5a527-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="5a527-125">Este é o valor de kanbans que deve ser ativado.</span><span class="sxs-lookup"><span data-stu-id="5a527-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="5a527-126">Neste caso, 2 kanbans que transferem 5 de cada.</span><span class="sxs-lookup"><span data-stu-id="5a527-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="5a527-127">No campo Valor mínimo de limite de alerta, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="5a527-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="5a527-128">Usado para manter o controle do valor mínimo de kanbans completos que devem estar no destino.</span><span class="sxs-lookup"><span data-stu-id="5a527-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="5a527-129">Por exemplo, ele é usado na visão geral da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="5a527-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="5a527-130">No campo Valor máximo de limite de alerta, insira '2'.</span><span class="sxs-lookup"><span data-stu-id="5a527-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="5a527-131">Usado para manter o controle do valor máximo de kanbans completos que devem estar no destino.</span><span class="sxs-lookup"><span data-stu-id="5a527-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="5a527-132">Por exemplo, ele é usado na visão geral da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="5a527-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="5a527-133">Criar kanbans</span><span class="sxs-lookup"><span data-stu-id="5a527-133">Create kanbans</span></span>
1. <span data-ttu-id="5a527-134">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5a527-134">Click Save.</span></span>
    * <span data-ttu-id="5a527-135">A regra kanban precisa ser salva antes de kanbans poderem ser criados.</span><span class="sxs-lookup"><span data-stu-id="5a527-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="5a527-136">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="5a527-136">Click Add.</span></span>
    * <span data-ttu-id="5a527-137">Observe que, como não há kanbans ativos, o 'Número de novos kanbans' sugerido é 2, sendo igual à 'Quantidade de kanbans fixa'.</span><span class="sxs-lookup"><span data-stu-id="5a527-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="5a527-138">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="5a527-138">Click Create.</span></span>
    * <span data-ttu-id="5a527-139">Isso criará dois kanbans.</span><span class="sxs-lookup"><span data-stu-id="5a527-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="5a527-140">Note que 2 kanbans, para cada 5, foram criados para essa regra kanban de retirada.</span><span class="sxs-lookup"><span data-stu-id="5a527-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="5a527-141">Esta é a última etapa do procedimento.</span><span class="sxs-lookup"><span data-stu-id="5a527-141">This is the last step in this procedure.</span></span>  


