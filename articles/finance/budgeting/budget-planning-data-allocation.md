---
title: Alocação de dados do planejamento de orçamento
description: Este tópico descreve os métodos de alocação disponíveis no Microsoft Dynamics 365 Finance e como eles podem ser usados.
author: ShylaThompson
manager: AnnBe
ms.date: 03/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetPlanningConfiguration
audience: Application User
ms.reviewer: roschlom
ms.custom: 15191
ms.assetid: 89a918e8-59a4-4711-a2e9-b41989ddd0f1
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f3ce04e8936ace70d83febc6be1e39c210fecfa7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210376"
---
# <a name="budget-planning-data-allocation"></a><span data-ttu-id="b7bb7-103">Alocação de dados do planejamento de orçamento</span><span class="sxs-lookup"><span data-stu-id="b7bb7-103">Budget planning data allocation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b7bb7-104">Este tópico descreve os métodos de alocação disponíveis no Microsoft Dynamics 365 Finance e como eles podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-104">This topic describes the allocation methods that are available in Microsoft Dynamics 365 Finance and how they can be used.</span></span>  

<span data-ttu-id="b7bb7-105">Você pode distribuir os dados em um plano de orçamento de várias formas para retratar com precisão os valores projetados.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-105">You can distribute the data in a budget plan in a number of ways to accurately portray the projected amounts.</span></span>

## <a name="allocation-methods"></a><span data-ttu-id="b7bb7-106">Métodos de alocação</span><span class="sxs-lookup"><span data-stu-id="b7bb7-106">Allocation methods</span></span>
<span data-ttu-id="b7bb7-107">Três métodos de alocação (alocar entre períodos, Alocar para dimensões e Usar regras de alocação do razão) podem criar linhas de plano de orçamento baseadas nas linhas do mesmo plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-107">Three allocation methods (Allocate across periods, Allocate to dimensions, and Use ledger allocation rules) can create budget plan lines that are based on lines in the same budget plan.</span></span> <span data-ttu-id="b7bb7-108">Outros três métodos (Agregar, Distribuir e Copiar do plano de orçamento) podem criar linhas do plano de orçamento em outros planos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-108">Three other methods (Aggregate, Distribute, and Copy from budget plan) can create budget plan lines in other budget plans.</span></span> <span data-ttu-id="b7bb7-109">Para todos os seis métodos de alocação, você especifica o cenário de destino.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-109">For all six allocation methods, you specify the destination scenario.</span></span> <span data-ttu-id="b7bb7-110">O cenário de destino pode ser igual ao cenário de origem ou diferente do cenário de origem.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-110">The destination scenario can be either the same as the source scenario or different from the source scenario.</span></span> <span data-ttu-id="b7bb7-111">Além disso, você pode especificar se novas linhas são anexadas ao plano de orçamento, ou substituir as linhas atuais no plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-111">Additionally, you can specify whether new lines are appended to the budget plan or replace the current lines in the budget plan.</span></span>

> [!NOTE] 
> <span data-ttu-id="b7bb7-112">Deve-se usar um cenário exclusivo para agregação diferente do cenário para distribuição ou outras modificações executadas anteriormente no plano principal.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-112">A unique scenario should be used for aggregation that is different from the scenario that was used for distribution or other modifications that were previously performed  in the parent plan.</span></span>  

<span data-ttu-id="b7bb7-113">[![Método de alocação Alocar entre períodos](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Alocar entre períodos** – Uma categoria de alocação de período é usada para alocar as linhas do plano de orçamento do cenário do plano de orçamento de origem entre períodos no cenário de destino.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-113">[![Allocate across Periods allocation method](./media/allocateacrossperiods-300x259.png)](./media/allocateacrossperiods.png)
**Allocate across periods** – A period allocation category is used to allocate the budget plan lines from the source budget plan scenario across periods in the destination scenario.</span></span> <span data-ttu-id="b7bb7-114">O valor de origem é atribuído a várias linhas no cenário de destino, com base na porcentagem e na data definidas na categoria de alocação de período.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-114">The source amount is assigned to multiple lines in the destination scenario, based on the percentage and date that are defined in the period allocation category.</span></span>         

<span data-ttu-id="b7bb7-115">[![Método de alocação Alocar para dimensões](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Alocar para dimensões** – As linhas do plano de orçamento são alocadas do cenário de planejamento de orçamento de origem para uma ou mais linhas no cenário de destino, com base nas porcentagens e dimensões financeiras definidas em uma condição de alocação de orçamento selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-115">[![Allocate to Dimensions allocation method](./media/allocatetodimensions.jpg)](./media/allocatetodimensions.jpg)
**Allocate to dimensions** – The budget plan lines are allocated from the source budget planning scenario to one or more lines in the destination scenario, based on the percentages and financial dimensions that are defined in a selected budget allocation term.</span></span>           

<span data-ttu-id="b7bb7-116">![Gráfico Agregar](./media/aggregatechart-300x230.png)
**Agregar** – As linhas do plano de orçamento são agregadas do cenário do plano de orçamento de origem nos planos de orçamento associados (filhos) ao cenário de destino no plano de orçamento pai.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-116">![Aggregate chart](./media/aggregatechart-300x230.png)
**Aggregate** – The budget plan lines are aggregated from the source budget plan scenario in the associated (child) budget plans to the destination scenario in the parent budget plan.</span></span> <span data-ttu-id="b7bb7-117">Esse método permite que os valores de orçamento que são preparados em um nível inferior da organização sejam consolidados em um nível superior.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-117">This method enables budget amounts that are prepared at a lower level in the organization to be consolidated at a higher level.</span></span>          

<span data-ttu-id="b7bb7-118">[![Gráfico Distribuir](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribuir** – As linhas do plano de orçamento são distribuídas do cenário de planejamento de orçamento de origem no plano de orçamento pai para o cenário de destino nos planos de orçamento associados (filhos), com base nas dimensões financeiras das unidades organizacionais dos planos associados.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-118">[![Distribute chart](./media/distributechart-300x230.png)](./media/distributechart.png)
**Distribute** – The budget plan lines are distributed from the source budget planning scenario in the parent budget plan to the destination scenario in the associated (child) budget plans, based on the financial dimensions of the organization units of the associated plans.</span></span> <span data-ttu-id="b7bb7-119">Este método permite que os valores de orçamento que são preparados em um nível superior da organização sejam difundidos para uma análise mais localizada.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-119">This method enables budget amounts that are prepared at a higher level in the organization to be spread out for more localized review.</span></span>           

<span data-ttu-id="b7bb7-120">[![Regras de alocação do razão](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Usar regras de alocação do razão** – As linhas do plano de orçamento são distribuídas do cenário de planejamento de orçamento de origem para o cenário de destino, com base na regra de alocação do razão selecionada.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-120">[![Ledger allocation rules](./media/ledgerallocationrules-300x202.png)](./media/ledgerallocationrules.png)
**Use ledger allocation rules** – The budget plan lines are distributed from the source budget planning scenario to the destination scenario, based on the ledger allocation rule that is selected.</span></span> 

<span data-ttu-id="b7bb7-121">[![Copiar do plano de orçamento](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copiar do plano de orçamento** – Como no método de alocação Distribuir, as linhas do plano de orçamento são criadas no destino, com base em linhas de um plano de orçamento relacionado.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-121">[![Copy from budget plan](./media/copyfrombudgetplan-187x300.png)](./media/copyfrombudgetplan.png)
**Copy from budget plan** – As in the Distribute allocation method, budget plan lines are created in the destination, based on lines in a related budget plan.</span></span> <span data-ttu-id="b7bb7-122">No entanto, neste método, o plano de orçamento de origem não precisa ser o pai, mas pode estar em um nível superior na hierarquia do plano de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-122">However, for this method, the source budget plan doesn't have to be the parent but can be at any higher level in the budget plan hierarchy.</span></span> <span data-ttu-id="b7bb7-123">Esse método de alocação é útil se os valores consolidados são orçados originalmente em um nível superior, e devem ser transferidos para um nível inferior da organização para análise e ajuste detalhados para poder receber a aprovação de nível superior.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-123">This allocation method is useful if consolidated amounts are originally budgeted at a much higher level, and must be transferred to a lower level of the organization for detailed review and adjustment before they can receive upper-level approval.</span></span>          

## <a name="using-allocation-methods-in-a-budget-plan"></a><span data-ttu-id="b7bb7-124">Uso de métodos de alocação em um plano de orçamento</span><span class="sxs-lookup"><span data-stu-id="b7bb7-124">Using allocation methods in a budget plan</span></span>
<span data-ttu-id="b7bb7-125">Para executar alocações na página do plano de orçamento, selecione as linhas para alocação e clique em **Alocar orçamento**.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-125">To perform allocations on the budget plan page, select the lines to allocate, and then click **Allocate budget**.</span></span>

<span data-ttu-id="b7bb7-126">[![Botão Distribuir orçamento](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span><span class="sxs-lookup"><span data-stu-id="b7bb7-126">[![Allocate budget button](./media/allocatebudgetbutton-300x84.png)](./media/allocatebudgetbutton.png)</span></span> 

<span data-ttu-id="b7bb7-127">Em seguida, selecione um método de alocação.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-127">Next, select an allocation method.</span></span> <span data-ttu-id="b7bb7-128">Os campos restantes são definidos com base no método selecionado.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-128">The remaining fields are then set, based on the method that you selected.</span></span> <span data-ttu-id="b7bb7-129">Esses campos incluem a origem e o destino dos dados do plano de orçamento, e uma opção que permite multiplicar a origem por um fator especificado quando os valores de destino são criados, para simplificar o ajuste em massa.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-129">These fields include the source and destination of the budget plan data, and an option that lets you multiply the source by a specified factor when the destination amounts are created, to simplify bulk adjustment.</span></span> <span data-ttu-id="b7bb7-130">Também é possível definir a opção **Acrescentar ao plano**.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-130">You can also set the **Append to plan** option.</span></span> <span data-ttu-id="b7bb7-131">Selecione **Não** para substituir as linhas existentes do plano de orçamento, ou selecione **Sim** para reter as linhas existentes do plano de orçamento e adicionar novas linhas aos valores alocados.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-131">Select **No** to replace the existing budget plan lines, or select **Yes** to retain the existing budget plan lines and add new lines for the allocated amounts.</span></span>

## <a name="automating-allocations-during-a-workflow"></a><span data-ttu-id="b7bb7-132">Automatização de alocações durante um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b7bb7-132">Automating allocations during a workflow</span></span>
<span data-ttu-id="b7bb7-133">Um recurso avançado permite que as alocações sejam executadas automaticamente, como parte de um fluxo de trabalho do planejamento de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-133">One powerful feature enables allocations to be performed automatically as part of a budget planning workflow.</span></span> <span data-ttu-id="b7bb7-134">Como um plano de orçamento se move no fluxo de trabalho, as tarefas automatizadas podem invocar uma alocação em uma fase específica de planejamento de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-134">As a budget plan moves through its workflow, automated tasks can invoke an allocation at a specified budget planning stage.</span></span> 

<span data-ttu-id="b7bb7-135">Para configurar a alocação automatizada, primeiro você deve criar uma agenda de alocação na página **Configuração de planejamento de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-135">To set up automated allocation, you must first create an allocation schedule on the **Budget planning configuration** page.</span></span> <span data-ttu-id="b7bb7-136">A agenda de alocação define o método de alocação que será usado quando a alocação automatizada for executada, e os valores das várias opções de alocação (consulte a seção anterior para obter descrições).</span><span class="sxs-lookup"><span data-stu-id="b7bb7-136">The allocation schedule defines the allocation method that will be used when the automated allocation is run, and the values of the various allocation options (see the previous section for descriptions).</span></span> 

<span data-ttu-id="b7bb7-137">Em seguida, crie uma alocação de fase na página **Configuração de planejamento de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-137">Next, you create a stage allocation on the **Budget planning configuration** page.</span></span> <span data-ttu-id="b7bb7-138">A alocação de fase atribui uma agenda de alocação ao fluxo de trabalho e fase do planejamento de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-138">The stage allocation assigns an allocation schedule to the budget planning workflow and stage.</span></span> 

<span data-ttu-id="b7bb7-139">Por fim, adicione uma tarefa automatizada para alocação de fase de planejamento de orçamento na fase de fluxo de trabalho desejada.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-139">Finally, add an automated task for budget planning stage allocation at the desired workflow stage.</span></span> <span data-ttu-id="b7bb7-140">No exemplo a seguir, duas alocações de fase de planejamento de orçamento (delineadas em vermelho) foram inseridas no fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b7bb7-140">In the following example, two budget planning stage allocations (outlined in red) have been inserted into the workflow.</span></span>

<span data-ttu-id="b7bb7-141">[![Alocações de fase do planejamento de orçamento](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span><span class="sxs-lookup"><span data-stu-id="b7bb7-141">[![Budget planning stage allocations](./media/budgetplanningstageallocations-300x300.png)](./media/budgetplanningstageallocations.png)</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]