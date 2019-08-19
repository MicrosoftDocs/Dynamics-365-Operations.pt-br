---
title: Adicionar uma política de cálculo de quantidade de kanbans a uma regra kanban
description: Este procedimento foca na criação de uma política de cálculo da quantidade kanban e na sua adição à uma regra kanban visando otimizar as quantidades e tamanho kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanQuantityPolicy, KanbanRules
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 401b01a6128babd6ed345342a65705a0262540e8
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837941"
---
# <a name="add-a-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="698ae-103">Adicionar uma política de cálculo de quantidade de kanbans a uma regra kanban</span><span class="sxs-lookup"><span data-stu-id="698ae-103">Add a kanban quantity calculation policy to a kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="698ae-104">Este procedimento foca na criação de uma política de cálculo da quantidade kanban e na sua adição à uma regra kanban visando otimizar as quantidades e tamanho kanban.</span><span class="sxs-lookup"><span data-stu-id="698ae-104">This procedure focuses on creating a kanban quantity calculation policy and adding it to a kanban rule to optimize the kanban size and quantities.</span></span> <span data-ttu-id="698ae-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="698ae-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="698ae-106">Esse procedimento é destinado ao gerente de fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="698ae-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="698ae-107">Esse procedimento é um pré-requisito para a criação do procedimento Calcular sugestões da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="698ae-107">This procedure is a prerequisite for creating the procedure Calculate kanban quantity suggestions.</span></span> 


## <a name="create-a-kanban-quantity-calculation-policy"></a><span data-ttu-id="698ae-108">Crie uma política de cálculo de quantidade kanban</span><span class="sxs-lookup"><span data-stu-id="698ae-108">Create a kanban quantity calculation policy</span></span>
1. <span data-ttu-id="698ae-109">Vá para Controle de produção > Tarefas periódicas > Cálculo da quantidade de kanbans > Políticas de cálculo da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="698ae-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban quantity calculation policies.</span></span>
2. <span data-ttu-id="698ae-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="698ae-110">Click New.</span></span>
3. <span data-ttu-id="698ae-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="698ae-111">In the Name field, type a value.</span></span>
    * <span data-ttu-id="698ae-112">Por exemplo, tipo Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="698ae-112">For example, type Speaker2016.</span></span>  
4. <span data-ttu-id="698ae-113">No campo Plano mestre, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="698ae-113">In the Master plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="698ae-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="698ae-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="698ae-115">Selecione StaticPlan para calcular a demanda.</span><span class="sxs-lookup"><span data-stu-id="698ae-115">Select StaticPlan to calculate demand.</span></span>  
6. <span data-ttu-id="698ae-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="698ae-116">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="698ae-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="698ae-117">Click Save.</span></span>
8. <span data-ttu-id="698ae-118">No campo Quantidade kanban mínima, insira '1'.</span><span class="sxs-lookup"><span data-stu-id="698ae-118">In the Minimum kanban quantity field, enter '1'.</span></span>
    * <span data-ttu-id="698ae-119">Este é o número adicional de kanbans incluído no cálculo da quantidade de kanbans.</span><span class="sxs-lookup"><span data-stu-id="698ae-119">This is the additional number of kanbans that is included in the kanban quantity calculation.</span></span>  
9. <span data-ttu-id="698ae-120">Defina Fator de segurança como '1'.</span><span class="sxs-lookup"><span data-stu-id="698ae-120">Set Safety factor to '1'.</span></span>
    * <span data-ttu-id="698ae-121">Este é o fator usado para calcular a quantidade adicional de estoque de segurança.</span><span class="sxs-lookup"><span data-stu-id="698ae-121">This is the factor that is used to calculate additional quantity of safety stock.</span></span>  
10. <span data-ttu-id="698ae-122">No campo Dias de antecedência, insira '30'.</span><span class="sxs-lookup"><span data-stu-id="698ae-122">In the Days ahead field, enter '30'.</span></span>
    * <span data-ttu-id="698ae-123">Este é o número de dias antes da data de cálculo da quantidade de kanbans em que a demanda é incluída no cálculo</span><span class="sxs-lookup"><span data-stu-id="698ae-123">This is the number of days prior to the kanban quantity calculation date that is included in the demand calculation.</span></span>  
11. <span data-ttu-id="698ae-124">No campo Dias atrasados, insira '30'.</span><span class="sxs-lookup"><span data-stu-id="698ae-124">In the Days behind field, enter '30'.</span></span>
    * <span data-ttu-id="698ae-125">Este é o número de dias à frente da data de cálculo da quantidade de kanbans em que a demanda é incluída no cálculo.</span><span class="sxs-lookup"><span data-stu-id="698ae-125">This is the number of days forward from the kanban quantity calculation date that is included in the demand calculation.</span></span>  <span data-ttu-id="698ae-126">A fórmula usada para o cálculo é mostrada com os valores reais.</span><span class="sxs-lookup"><span data-stu-id="698ae-126">The formula used for the calculation is shown with the actual values.</span></span> <span data-ttu-id="698ae-127">Por exemplo, quantidade de kanbans = ((demanda diária média x prazo de entrega x 2,00 / quantidade de produtos por unidade de manuseio de material) + 1</span><span class="sxs-lookup"><span data-stu-id="698ae-127">For example,  Kanban quantity = ((Average daily demand x lead time x 2.00) / Product quantity per handling unit) + 1</span></span>  
12. <span data-ttu-id="698ae-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="698ae-128">Close the page.</span></span>

## <a name="add-the-kanban-quantity-calculation-policy-to-a-kanban-rule"></a><span data-ttu-id="698ae-129">Adicione a política de cálculo da quantidade kanban à uma regra kanban</span><span class="sxs-lookup"><span data-stu-id="698ae-129">Add the kanban quantity calculation policy to a kanban rule</span></span>
1. <span data-ttu-id="698ae-130">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="698ae-130">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="698ae-131">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="698ae-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="698ae-132">Selecione a regra kanban 000020 para esse procedimento.</span><span class="sxs-lookup"><span data-stu-id="698ae-132">Select kanban rule 000020 for this procedure.</span></span>  
3. <span data-ttu-id="698ae-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="698ae-133">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="698ae-134">Ative a expansão da seção Políticas de cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="698ae-134">Toggle the expansion of the Kanban quantity calculation policies section.</span></span>
5. <span data-ttu-id="698ae-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="698ae-135">Click Add.</span></span>
    * <span data-ttu-id="698ae-136">Adicione a política de cálculo da quantidade kanban que você acabou de criar na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="698ae-136">Add the kanban quantity calculation policy that you have just created in the previous sub-task.</span></span>  
6. <span data-ttu-id="698ae-137">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="698ae-137">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="698ae-138">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="698ae-138">In the Name field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="698ae-139">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="698ae-139">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="698ae-140">Selecione a política Speaker2016 que você acabou de criar na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="698ae-140">Select the policy Speaker2016 that you have just created in the previous sub-task.</span></span>  

