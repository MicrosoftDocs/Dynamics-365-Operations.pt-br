--- 
title: "Calcular sugestões de quantidade de kanbans"
description: "Este procedimento foca na otimização das quantidades e tamanho kanban para uma regra kanban específica através do uso do cálculo da quantidade kanban."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9ba09bfba52cd576782e61802e44fa4b80f4711f
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="de352-103">Calcular sugestões de quantidade de kanbans</span><span class="sxs-lookup"><span data-stu-id="de352-103">Calculate kanban quantity suggestions</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="de352-104">Este procedimento foca na otimização das quantidades e tamanho kanban para uma regra kanban específica através do uso do cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="de352-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="de352-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="de352-106">Esse procedimento é destinado ao gerente de fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="de352-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="de352-107">A conclusão do procedimento Adicionar uma nova política de cálculo da quantidade kanban à uma regra kanban é um pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="de352-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="de352-108">Crie um cálculo da quantidade kanban</span><span class="sxs-lookup"><span data-stu-id="de352-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="de352-109">Vá para Controle de produção > Tarefas periódicas > Cálculo da quantidade de kanbans > Calcular quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="de352-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="de352-110">Click New.</span></span>
3. <span data-ttu-id="de352-111">No campo Nome, digite 'Spearker2016'.</span><span class="sxs-lookup"><span data-stu-id="de352-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="de352-112">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="de352-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="de352-113">Selecione a política que você criou durante o procedimento Adicionar uma nova política de cálculo de quantidade kanban à uma regra kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="de352-114">Por exemplo, Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="de352-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="de352-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="de352-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="de352-116">No campo Regra ativa a partir da data, defina a data e a hora para '2012-12-17T08:00:00'.</span><span class="sxs-lookup"><span data-stu-id="de352-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="de352-117">Essa data serve como base para determinar quais regras fixas kanban estão incluídas no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="de352-118">No campo Data de início do período de demanda cumprida, defina a data e a hora para '2012-11-17T09:00:00'.</span><span class="sxs-lookup"><span data-stu-id="de352-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="de352-119">A data a partir da qual transações de demanda passadas são incluídas no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="de352-120">No campo Data de término do período de demanda cumprida, defina a data e a hora para '2012-12-17T07:59:59'.</span><span class="sxs-lookup"><span data-stu-id="de352-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="de352-121">A data até a qual as transações de demanda passadas são incluídas no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="de352-122">No campo Data de início do período de demanda, defina a data e a hora para '2012-12-17T08:00:00'.</span><span class="sxs-lookup"><span data-stu-id="de352-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="de352-123">A data a partir da qual as transações de demanda atuais são incluídas no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="de352-124">No campo Data de término do período de demanda, defina a data e a hora para '2013-01-16T07:59:59'.</span><span class="sxs-lookup"><span data-stu-id="de352-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="de352-125">A data até a qual as transações de demanda atuais são incluídas no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="de352-126">Gere a proposta da quantidade kanban</span><span class="sxs-lookup"><span data-stu-id="de352-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="de352-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="de352-127">Click Save.</span></span>
2. <span data-ttu-id="de352-128">Clique em Gerar.</span><span class="sxs-lookup"><span data-stu-id="de352-128">Click Generate.</span></span>
    * <span data-ttu-id="de352-129">Isso gera uma linha de proposta da quantidade kanban para a regra kanban 000020.</span><span class="sxs-lookup"><span data-stu-id="de352-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="de352-130">Execute o cálculo da quantidade kanban</span><span class="sxs-lookup"><span data-stu-id="de352-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="de352-131">Clique em Calcular.</span><span class="sxs-lookup"><span data-stu-id="de352-131">Click Calculate.</span></span>
    * <span data-ttu-id="de352-132">Isso calcula a proposta da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="de352-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de352-133">Click OK.</span></span>
3. <span data-ttu-id="de352-134">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="de352-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="de352-135">Observe que a quantidade kanban sugerida é 2.</span><span class="sxs-lookup"><span data-stu-id="de352-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="de352-136">Altere a quantidade do produto e calcule novamente</span><span class="sxs-lookup"><span data-stu-id="de352-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="de352-137">Defina Quantidade de produto para '5'.</span><span class="sxs-lookup"><span data-stu-id="de352-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="de352-138">Clique em Calcular.</span><span class="sxs-lookup"><span data-stu-id="de352-138">Click Calculate.</span></span>
3. <span data-ttu-id="de352-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de352-139">Click OK.</span></span>
    * <span data-ttu-id="de352-140">Observe que com uma quantidade kanban de 5, a sugestão é alterada para uma quantidade kanban de 4.</span><span class="sxs-lookup"><span data-stu-id="de352-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="de352-141">Isso é causado pelo fato de que com uma quantidade menor de produto, são necessários mais kanbans para atender a demanda.</span><span class="sxs-lookup"><span data-stu-id="de352-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="de352-142">Atualize a regra kanban</span><span class="sxs-lookup"><span data-stu-id="de352-142">Update kanban rule</span></span>
1. <span data-ttu-id="de352-143">No campo Data efetiva da regra, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="de352-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="de352-144">Defina 'Regra ativa a partir da data' para uma data futura.</span><span class="sxs-lookup"><span data-stu-id="de352-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="de352-145">Por exemplo, hoje + um ano.</span><span class="sxs-lookup"><span data-stu-id="de352-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="de352-146">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="de352-146">Click Update.</span></span>
3. <span data-ttu-id="de352-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="de352-147">Click OK.</span></span>
4. <span data-ttu-id="de352-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="de352-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="de352-149">Valide a alteração na regra kanban</span><span class="sxs-lookup"><span data-stu-id="de352-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="de352-150">Vá para Gerenciamento de informações dos produtos > Lean manufacturing > Regras kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="de352-151">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="de352-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="de352-152">Selecione a regra kanban que foi criada na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="de352-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="de352-153">Esta deve ser a primeira regra kanban na lista classificada por número.</span><span class="sxs-lookup"><span data-stu-id="de352-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="de352-154">Ative a expansão da seção Detalhes.</span><span class="sxs-lookup"><span data-stu-id="de352-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="de352-155">Observe a data efetiva, o que significa que esta regra não estará ativada até essa data.</span><span class="sxs-lookup"><span data-stu-id="de352-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="de352-156">Ative a expansão da seção Quantidades.</span><span class="sxs-lookup"><span data-stu-id="de352-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="de352-157">Observe que esta é a quantidade padrão que você inseriu no cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="de352-158">Observe que esta é a quantidade kanban fixa de 4 do cálculo da quantidade kanban.</span><span class="sxs-lookup"><span data-stu-id="de352-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="de352-159">Clique na guia Painel de Lista.</span><span class="sxs-lookup"><span data-stu-id="de352-159">Click the ListPanel tab.</span></span>


