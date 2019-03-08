---
title: 'Definir processo de contagem cíclica de localização parcial '
description: Quando você usa planos de contagem cíclica para criar trabalhos de contagem, você pode orientar operações de contagem real solicitando que somente os produtos e as grades do produto foram contados específicos, em vez de todo estoque disponível no local.
author: ShylaThompson
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
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3aafb42cea1664b0629f57fe4492736601902cc1
ms.sourcegitcommit: bacad87e2b9146e08e6fe16af01356954eb90574
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2019
ms.locfileid: "373384"
---
# <a name="define-partial-location-cycle-counting-process"></a><span data-ttu-id="0f356-103">Definir processo de contagem cíclica de localização parcial </span><span class="sxs-lookup"><span data-stu-id="0f356-103">Define partial location cycle counting process</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0f356-104">Quando você usa planos de contagem cíclica para criar trabalhos de contagem, você pode orientar operações de contagem real solicitando que somente os produtos e as grades do produto foram contados específicos, em vez de todo estoque disponível no local.</span><span class="sxs-lookup"><span data-stu-id="0f356-104">When you use cycle count plans to create counting work, you can guide the actual counting operations by requesting that only specific products and product variants be counted instead of all on-hand inventory at the location.</span></span> <span data-ttu-id="0f356-105">Ao filtrar produtos específicos, o gerente do depósito pode reduzir custos indiretos de revisão, ajudar a evitar erros de consolidação e economizar tempo.</span><span class="sxs-lookup"><span data-stu-id="0f356-105">By filtering on specific products, the warehouse manager can reduce review overhead, help prevent consolidation mistakes, and save time.</span></span> <span data-ttu-id="0f356-106">Geralmente, um gerente de depósito executa as tarefas de configuração.</span><span class="sxs-lookup"><span data-stu-id="0f356-106">Typically, a warehouse manager performs the setup tasks.</span></span> <span data-ttu-id="0f356-107">Você pode ver todo esse procedimento na empresa de dados de demonstração USMF ou em seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="0f356-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="create-a-cycle-counting-work-template"></a><span data-ttu-id="0f356-108">Criar um modelo de trabalho de contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="0f356-108">Create a cycle counting work template</span></span>
1. <span data-ttu-id="0f356-109">Vá para Gerenciamento de depósito > Configuração > Trabalho > Modelos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f356-109">Go to Warehouse management > Setup > Work > Work templates.</span></span>
2. <span data-ttu-id="0f356-110">No campo Tipo de ordem de trabalho, selecione "Contagem cíclica".</span><span class="sxs-lookup"><span data-stu-id="0f356-110">In the Work order type field, select 'Cycle counting'.</span></span>
3. <span data-ttu-id="0f356-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f356-111">Click New.</span></span>
4. <span data-ttu-id="0f356-112">No campo de número de sequência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f356-112">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="0f356-113">A ordem de classificação é do número menor para o número maior.</span><span class="sxs-lookup"><span data-stu-id="0f356-113">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="0f356-114">O valor deve ser maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="0f356-114">The value must be more than 0 (zero).</span></span>  
5. <span data-ttu-id="0f356-115">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f356-115">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="0f356-116">No campo Modelo de trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-116">In the Work template field, type a value.</span></span>
7. <span data-ttu-id="0f356-117">No campo Descrição do modelo do trabalho, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-117">In the Work template description field, type a value.</span></span>
8. <span data-ttu-id="0f356-118">No campo ID do grupo de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-118">In the Work pool ID field, enter or select a value.</span></span>
9. <span data-ttu-id="0f356-119">No campo Prioridade de trabalho, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f356-119">In the Work priority field, enter a number.</span></span>
10. <span data-ttu-id="0f356-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f356-120">Click Save.</span></span>
11. <span data-ttu-id="0f356-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f356-121">Click New.</span></span>
12. <span data-ttu-id="0f356-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f356-122">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="0f356-123">No campo Tipo de trabalho, selecione 'Contagem'.</span><span class="sxs-lookup"><span data-stu-id="0f356-123">In the Work type field, select 'Counting'.</span></span>
14. <span data-ttu-id="0f356-124">No campo ID de classe de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-124">In the Work class ID field, enter or select a value.</span></span>
15. <span data-ttu-id="0f356-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f356-125">Click Save.</span></span>
16. <span data-ttu-id="0f356-126">Clique em Divisões de linha de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0f356-126">Click Work line breaks.</span></span>
17. <span data-ttu-id="0f356-127">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f356-127">Click New.</span></span>
18. <span data-ttu-id="0f356-128">No campo de número de sequência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f356-128">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="0f356-129">A ordem de classificação é do número menor para o número maior.</span><span class="sxs-lookup"><span data-stu-id="0f356-129">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="0f356-130">O valor deve ser maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="0f356-130">The value must be more than 0 (zero).</span></span>  
19. <span data-ttu-id="0f356-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f356-131">Click Save.</span></span>
20. <span data-ttu-id="0f356-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f356-132">Close the page.</span></span>
21. <span data-ttu-id="0f356-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f356-133">Close the page.</span></span>

## <a name="create-a-cycle-counting-plan"></a><span data-ttu-id="0f356-134">Criar um plano de contagem cíclica</span><span class="sxs-lookup"><span data-stu-id="0f356-134">Create a cycle counting plan</span></span>
1. <span data-ttu-id="0f356-135">Vá para Gerenciamento de depósito > Configuração > Contagem cíclica > Planos de contagem cíclica.</span><span class="sxs-lookup"><span data-stu-id="0f356-135">Go to Warehouse management > Setup > Cycle counting > Cycle count plans.</span></span>
2. <span data-ttu-id="0f356-136">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f356-136">Click New.</span></span>
3. <span data-ttu-id="0f356-137">No campo ID do plano de contagem cíclica, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-137">In the Cycle counting plan ID field, type a value.</span></span>
4. <span data-ttu-id="0f356-138">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-138">In the Description field, type a value.</span></span>
5. <span data-ttu-id="0f356-139">No campo Número máximo de contagens cíclicas, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f356-139">In the Maximum number of cycle counts field, enter a number.</span></span>
6. <span data-ttu-id="0f356-140">No campo Modelo de trabalho, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-140">In the Work template field, enter or select a value.</span></span>
7. <span data-ttu-id="0f356-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="0f356-141">Click New.</span></span>
8. <span data-ttu-id="0f356-142">No campo de número de sequência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="0f356-142">In the Sequence number field, enter a number.</span></span>
    * <span data-ttu-id="0f356-143">A ordem de classificação é do número menor para o número maior.</span><span class="sxs-lookup"><span data-stu-id="0f356-143">The sort order is from the smallest number to the largest number.</span></span> <span data-ttu-id="0f356-144">O valor deve ser maior que 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="0f356-144">The value must be more than 0 (zero).</span></span>  
9. <span data-ttu-id="0f356-145">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-145">In the Description field, type a value.</span></span>
10. <span data-ttu-id="0f356-146">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0f356-146">Click Save.</span></span>
11. <span data-ttu-id="0f356-147">Clique em Definir consulta de produto.</span><span class="sxs-lookup"><span data-stu-id="0f356-147">Click Define product query.</span></span>
12. <span data-ttu-id="0f356-148">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="0f356-148">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="0f356-149">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0f356-149">In the Criteria field, enter or select a value.</span></span>
14. <span data-ttu-id="0f356-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0f356-150">Click OK.</span></span>
15. <span data-ttu-id="0f356-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0f356-151">Close the page.</span></span>

