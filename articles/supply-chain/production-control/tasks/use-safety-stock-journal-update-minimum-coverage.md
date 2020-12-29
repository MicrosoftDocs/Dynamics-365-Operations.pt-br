---
title: Usar o diário de estoque de segurança para atualizar a cobertura mínima
description: Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas.
author: ChristianRytt
manager: tfehr
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqItemJournalName, ReqItemJournalSafetyStock, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0d69daf3d307ba72ff6017d91849e3d22bd0bd85
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422413"
---
# <a name="use-the-safety-stock-journal-to-update-minimum-coverage"></a><span data-ttu-id="7cece-103">Usar o diário de estoque de segurança para atualizar a cobertura mínima</span><span class="sxs-lookup"><span data-stu-id="7cece-103">Use the safety stock journal to update minimum coverage</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7cece-104">Este procedimento mostra como calcular propostas de cobertura mínima baseadas em transações históricas e, em seguida, atualizar a cobertura do item com as propostas.</span><span class="sxs-lookup"><span data-stu-id="7cece-104">This procedure shows how to calculate minimum coverage proposals based on historical transactions and then update the item coverage with the proposals.</span></span> <span data-ttu-id="7cece-105">Isso é feito usando o diário de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="7cece-105">This is done using the safety stock journal.</span></span> <span data-ttu-id="7cece-106">A empresa de dados demo usada para criar esta tarefa é USMF.</span><span class="sxs-lookup"><span data-stu-id="7cece-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="7cece-107">Essa tarefa é pretendida para o planejador da produção, para ajudar a manter a cobertura mínima.</span><span class="sxs-lookup"><span data-stu-id="7cece-107">This task is intended for the production planner, to help maintain minimum coverage.</span></span>


## <a name="create-a-new-safety-stock-journal-name"></a><span data-ttu-id="7cece-108">Crie um novo nome de diário de estoque seguro</span><span class="sxs-lookup"><span data-stu-id="7cece-108">Create a new safety stock journal name</span></span>
1. <span data-ttu-id="7cece-109">No **Painel de navegação**, acesse **Planejamento mestre > Configuração > Nomes do diário de estoque de segurança**.</span><span class="sxs-lookup"><span data-stu-id="7cece-109">In the **Navigation pane**, go to **Master planning > Setup > Safety stock journal names**.</span></span>
2. <span data-ttu-id="7cece-110">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7cece-110">Click **New**.</span></span>
3. <span data-ttu-id="7cece-111">No campo **Nome**, digite "Material".</span><span class="sxs-lookup"><span data-stu-id="7cece-111">In the **Name** field, type 'Material'.</span></span>
4. <span data-ttu-id="7cece-112">No campo **Descrição**, digite "Material".</span><span class="sxs-lookup"><span data-stu-id="7cece-112">In the **Description** field, type 'Material'.</span></span>
5. <span data-ttu-id="7cece-113">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7cece-113">Close the page.</span></span>

## <a name="create-a-safety-stock-journal"></a><span data-ttu-id="7cece-114">Criar um diário de estoque de segurança</span><span class="sxs-lookup"><span data-stu-id="7cece-114">Create a safety stock journal</span></span>
1. <span data-ttu-id="7cece-115">No **Painel de navegação**, acesse **Planejamento mestre > Planejamento mestre > Executar > Cálculo de estoque de segurança**.</span><span class="sxs-lookup"><span data-stu-id="7cece-115">In the **Navigation pane**, go to **Master planning > Master planning > Run > Safety stock calculation**.</span></span>
2. <span data-ttu-id="7cece-116">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7cece-116">Click **New**.</span></span>
3. <span data-ttu-id="7cece-117">No campo **Nome**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7cece-117">In the **Name** field, enter or select a value.</span></span> <span data-ttu-id="7cece-118">Selecione o nome do diário de estoque de segurança que você criou, por exemplo, Material.</span><span class="sxs-lookup"><span data-stu-id="7cece-118">Select the safety stock journal name that you created, for example, Material.</span></span>  
4. <span data-ttu-id="7cece-119">Clique em **Criar linhas**.</span><span class="sxs-lookup"><span data-stu-id="7cece-119">Click **Create lines**.</span></span>
5. <span data-ttu-id="7cece-120">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7cece-120">In the **From date** field, enter a date.</span></span>  
6. <span data-ttu-id="7cece-121">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7cece-121">In the **To date** field, enter a date.</span></span>
7. <span data-ttu-id="7cece-122">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cece-122">Click **OK**.</span></span> <span data-ttu-id="7cece-123">Isso criará linhas para as dimensões que têm transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="7cece-123">This will create lines for the dimensions that have inventory transactions.</span></span>  

## <a name="calculate-proposal"></a><span data-ttu-id="7cece-124">Calcular proposta</span><span class="sxs-lookup"><span data-stu-id="7cece-124">Calculate proposal</span></span>
1. <span data-ttu-id="7cece-125">Clique em **Calcular proposta**.</span><span class="sxs-lookup"><span data-stu-id="7cece-125">Click **Calculate proposal**.</span></span>
2. <span data-ttu-id="7cece-126">Selecione a opção **Usar média de saídas durante o prazo de entrega**.</span><span class="sxs-lookup"><span data-stu-id="7cece-126">Select the **Use average issue during lead time** option.</span></span>
3. <span data-ttu-id="7cece-127">Defina o **Fator de multiplicação** como "10".</span><span class="sxs-lookup"><span data-stu-id="7cece-127">Set **Multiplication factor** to '10'.</span></span> <span data-ttu-id="7cece-128">O fator da multiplicação é usado para ajustar a proposta.</span><span class="sxs-lookup"><span data-stu-id="7cece-128">The Multiply factor is used to adjust the proposal.</span></span> <span data-ttu-id="7cece-129">Como os dados de demonstração têm somente algumas transações, você precisará definir o fator para obter uma proposta realística.</span><span class="sxs-lookup"><span data-stu-id="7cece-129">Because demo data only has a few transactions, you will need to set the factor to get a realistic proposal.</span></span>  
4. <span data-ttu-id="7cece-130">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cece-130">Click **OK**.</span></span> <span data-ttu-id="7cece-131">Role para baixo para encontrar M0002 e M0003.</span><span class="sxs-lookup"><span data-stu-id="7cece-131">Scroll down to find M0002 and M0003.</span></span> <span data-ttu-id="7cece-132">Veja a coluna **Quantidade mínima calculada**.</span><span class="sxs-lookup"><span data-stu-id="7cece-132">View the **Calculated minimum** quantity column.</span></span>   

## <a name="update-minimum-quantity"></a><span data-ttu-id="7cece-133">Atualizar quantidade mínima</span><span class="sxs-lookup"><span data-stu-id="7cece-133">Update minimum quantity</span></span>
1. <span data-ttu-id="7cece-134">No campo **Nova quantidade mínima**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7cece-134">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="7cece-135">Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="7cece-135">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="7cece-136">Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado.</span><span class="sxs-lookup"><span data-stu-id="7cece-136">If the Calculated minimum is zero,  you can enter the desired future value.</span></span> <span data-ttu-id="7cece-137">Por exemplo, você pode inserir a Quantidade mínima calculada neste campo para o M0002 que tem o armazém 12.</span><span class="sxs-lookup"><span data-stu-id="7cece-137">For example, you can enter the Calculated minimum quantity in this field for M0002 that has warehouse 12.</span></span>  
2. <span data-ttu-id="7cece-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7cece-138">In the list, find and select the desired record.</span></span> <span data-ttu-id="7cece-139">Por exemplo, você pode selecionar o M0002 que tem o armazém 12.</span><span class="sxs-lookup"><span data-stu-id="7cece-139">For example, you can select M0002 that has warehouse 12.</span></span>  
3. <span data-ttu-id="7cece-140">No campo **Nova quantidade mínima**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7cece-140">In the **New minimum quantity** field, enter a number.</span></span> <span data-ttu-id="7cece-141">Atualize a Nova quantidade mínima para corresponder ao valor na Quantidade mínima calculada.</span><span class="sxs-lookup"><span data-stu-id="7cece-141">Update the New minimum quantity to match the value in the Calculated minimum quantity.</span></span> <span data-ttu-id="7cece-142">Se o mínimo calculado for zero, você poderá inserir o valor futuro desejado.</span><span class="sxs-lookup"><span data-stu-id="7cece-142">If the Calculated minimum is zero you can enter the desired future value.</span></span>  

## <a name="post-the-new-minimum-quantity-and-validate-the-result"></a><span data-ttu-id="7cece-143">Lançar a nova quantidade mínima e validar o resultado</span><span class="sxs-lookup"><span data-stu-id="7cece-143">Post the new minimum quantity and validate the result</span></span>
1. <span data-ttu-id="7cece-144">Clique em **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="7cece-144">Click **Post**.</span></span>
2. <span data-ttu-id="7cece-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="7cece-145">Click **OK**.</span></span>
3. <span data-ttu-id="7cece-146">Clique para seguir o link no campo **Número de item**.</span><span class="sxs-lookup"><span data-stu-id="7cece-146">Click to follow the link in the **Item number** field.</span></span>
4. <span data-ttu-id="7cece-147">Clique para seguir o link no campo **Número de item**.</span><span class="sxs-lookup"><span data-stu-id="7cece-147">Click to follow the link in the **Item number** field.</span></span>
5. <span data-ttu-id="7cece-148">No **Painel de Ação**, clique em Plano.</span><span class="sxs-lookup"><span data-stu-id="7cece-148">On the **Action Pane**, click Plan.</span></span>
6. <span data-ttu-id="7cece-149">Clique em **Cobertura de item**.</span><span class="sxs-lookup"><span data-stu-id="7cece-149">Click **Item coverage**.</span></span> <span data-ttu-id="7cece-150">Observe que a **Quantidade mínima** foi atualizada com a nova quantidade mínima do diário de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="7cece-150">Notice that the **Minimum quantity** has been updated with the new minimum quantity from the safety stock journal.</span></span>  

