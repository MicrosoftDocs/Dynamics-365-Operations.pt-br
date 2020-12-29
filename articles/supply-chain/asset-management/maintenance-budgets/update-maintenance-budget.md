---
title: Atualizar orçamentos de manutenção
description: Este tópico explica como atualizar um orçamento de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e43abd4644eec8c91606ec48bbecf30f12600856
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422246"
---
# <a name="update-maintenance-budgets"></a><span data-ttu-id="1c107-103">Atualizar orçamentos de manutenção</span><span class="sxs-lookup"><span data-stu-id="1c107-103">Update maintenance budgets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="1c107-104">A página **Linhas de orçamento de manutenção** exibe todas as linhas de orçamento que foram criadas para o orçamento selecionado na página **Orçamentos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="1c107-104">The **Maintenance budget lines** page shows all the budget lines that have been created for the budget that is selected on the **Maintenance budgets** page.</span></span> <span data-ttu-id="1c107-105">(Para obter mais informações, consulte [Criar orçamentos de manutenção](create-maintenance-budget.md).) Você pode calcular novamente e ajudar linhas de orçamento de manutenção até que o orçamento de manutenção seja aprovado.</span><span class="sxs-lookup"><span data-stu-id="1c107-105">(For more information, see [Create maintenance budgets](create-maintenance-budget.md).) You can recalculate and adjust maintenance budget lines until the maintenance budget is approved.</span></span> <span data-ttu-id="1c107-106">Depois de o período de orçamento ter passado e custos tiverem sido lançados no Gerenciamento de Ativos, você também pode atualizar as linhas de orçamento com custos reais.</span><span class="sxs-lookup"><span data-stu-id="1c107-106">After the budget period has passed, and costs have been posted in Asset Management, you can also update the budget lines with actual costs.</span></span>

## <a name="recalculate-a-maintenance-budget"></a><span data-ttu-id="1c107-107">Calcular novamente um orçamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="1c107-107">Recalculate a maintenance budget</span></span>

<span data-ttu-id="1c107-108">Você pode recalcular um orçamento de manutenção na página **Linhas de orçamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="1c107-108">You can recalculate a maintenance budget on the **Maintenance budget lines** page.</span></span> <span data-ttu-id="1c107-109">Quando você recalcula um orçamento de manutenção, as linhas de orçamento existentes são excluídas e um novo cálculo é realizado.</span><span class="sxs-lookup"><span data-stu-id="1c107-109">When you recalculate a maintenance budget, the existing budget lines are deleted, and a new calculation is done.</span></span>

1. <span data-ttu-id="1c107-110">Na página **Linhas de orçamento de manutenção**, selecione **Recalcular**.</span><span class="sxs-lookup"><span data-stu-id="1c107-110">On the **Maintenance budget lines** page, select **Recalculate**.</span></span>
2. <span data-ttu-id="1c107-111">Na caixa de diálogo **Recalcular orçamento**, faça as alterações necessárias para o novo cálculo e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c107-111">In the **Recalculate budget** dialog box, make the required changes for the new calculation, and then select **OK**.</span></span>

<span data-ttu-id="1c107-112">As novas linhas de orçamento são criadas conforme os valores definidos.</span><span class="sxs-lookup"><span data-stu-id="1c107-112">New budget lines are created according to the values that you set.</span></span>

## <a name="adjust-budget-lines"></a><span data-ttu-id="1c107-113">Ajustar linhas de orçamento</span><span class="sxs-lookup"><span data-stu-id="1c107-113">Adjust budget lines</span></span>

<span data-ttu-id="1c107-114">Em vez de recalcular o orçamento de manutenção completo, você pode ajustar as linhas selecionadas que são relacionadas a custos de orçamento.</span><span class="sxs-lookup"><span data-stu-id="1c107-114">Instead of recalculating the whole maintenance budget, you can adjust selected lines that are related to budget costs.</span></span>

1. <span data-ttu-id="1c107-115">Na página **Linhas de orçamento de manutenção**, selecione as linhas para atualizar o custo de orçamento.</span><span class="sxs-lookup"><span data-stu-id="1c107-115">On the **Maintenance budget lines** page, select the lines to update the budget cost for.</span></span>
2. <span data-ttu-id="1c107-116">Selecione **Ajustar**.</span><span class="sxs-lookup"><span data-stu-id="1c107-116">Select **Adjust**.</span></span>
3. <span data-ttu-id="1c107-117">Para adicionar um valor nas linhas selecionadas, marque a caixa de seleção **Adicionar custos**, e insira o valor no campo **Adicionar o valor**.</span><span class="sxs-lookup"><span data-stu-id="1c107-117">To add an amount to the selected lines, select the **Add cost** check box, and then enter the value in the **Add value** field.</span></span>
4. <span data-ttu-id="1c107-118">Para multiplicar os custos de orçamento nas linhas de orçamento selecionado por um fator, marque a caixa de seleção **Multiplicar custo**, e insira o fator no campo **Multiplicar valor**.</span><span class="sxs-lookup"><span data-stu-id="1c107-118">To multiply the budget cost on the selected budget lines by a factor, select the **Multiply cost** check box, and enter the factor in the **Multiply value** field.</span></span>

    <span data-ttu-id="1c107-119">Por exemplo, se você insere **1,2** no campo **Multiplicar valor**, você aumenta o custo de orçamento nas linhas selecionadas em 20%.</span><span class="sxs-lookup"><span data-stu-id="1c107-119">For example, if you enter **1.2** in the **Multiply value** field, you increase the budget cost on the selected lines by 20 percent.</span></span> <span data-ttu-id="1c107-120">Se inserir **0,7**, você reduz os custos de orçamento nas linhas selecionadas em 30%.</span><span class="sxs-lookup"><span data-stu-id="1c107-120">If you enter **0.7**, you reduce the budget cost on the selected lines by 30 percent.</span></span>

5. <span data-ttu-id="1c107-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c107-121">Select **OK**.</span></span>

<span data-ttu-id="1c107-122">As linhas de orçamento selecionadas são atualizadas de acordo com os valores definidos na etapa 3 ou 4.</span><span class="sxs-lookup"><span data-stu-id="1c107-122">The selected budget lines are updated according to the values that you set in step 3 or 4.</span></span>

## <a name="update-actual-costs"></a><span data-ttu-id="1c107-123">Atualizar custos reais</span><span class="sxs-lookup"><span data-stu-id="1c107-123">Update actual costs</span></span>

<span data-ttu-id="1c107-124">Depois das datas nas linhas de orçamento terem passado e custos reais tiverem sido lançados no Gerenciamento de ativo, você pode atualizar os custos reais no orçamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="1c107-124">After the dates on the budget lines have passed, and actual costs have been posted in Asset Management, you can update the actual costs on the maintenance budget.</span></span>

1. <span data-ttu-id="1c107-125">Na página **Linhas de orçamento de manutenção**, selecione **Atualizar custo**.</span><span class="sxs-lookup"><span data-stu-id="1c107-125">On the **Maintenance budget lines** page, select **Update cost**.</span></span>
2. <span data-ttu-id="1c107-126">Na caixa diálogo **Calcular custos reais**, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c107-126">In the **Calculate actual cost** dialog box, select **OK**.</span></span>

<span data-ttu-id="1c107-127">Os campos **Custos reais** nas linhas de orçamento serão atualizados se os custos reais forem lançados.</span><span class="sxs-lookup"><span data-stu-id="1c107-127">The **Actual cost** fields on the budget lines are updated if actual costs have been posted.</span></span> <span data-ttu-id="1c107-128">As novas linhas de orçamento podem ser geradas se novos tipos de ativo forem criados, já que você criou o orçamento, e se esses tipos de ativo foram usados nos ativos para as quais as ordens de serviço foram criadas e custos relacionados para os quais foram postados.</span><span class="sxs-lookup"><span data-stu-id="1c107-128">New budget lines might be generated if new asset types have been created since you created the budget, and if those asset types have been used on assets that work orders have been created for and related costs have been posted for.</span></span> <span data-ttu-id="1c107-129">As novas linhas de orçamento só mostram custos reais, pois nenhum custo de orçamento é calculado para eles.</span><span class="sxs-lookup"><span data-stu-id="1c107-129">New budget lines show only actual costs, because no budget costs were calculated for them.</span></span>

> [!NOTE]
> <span data-ttu-id="1c107-130">Para ver uma visão geral dos custos reais divididos em preventivo, custos corretivos e de investimento, você pode criar um cálculo para o mesmo período na página **Controle de custo de ativo**.</span><span class="sxs-lookup"><span data-stu-id="1c107-130">To see an overview of actual costs divided into preventive, corrective, and investment costs, you can do a calculation for the same period on the **Asset cost control** page.</span></span> 

## <a name="manually-add-budget-lines"></a><span data-ttu-id="1c107-131">Adicionar linhas de orçamento manualmente</span><span class="sxs-lookup"><span data-stu-id="1c107-131">Manually add budget lines</span></span>

<span data-ttu-id="1c107-132">Na página **Linhas de orçamento de serviço**, você poderá adicionar manualmente uma nova linha de orçamento selecionando **Novo** e escolhendo seleções na linha.</span><span class="sxs-lookup"><span data-stu-id="1c107-132">On the **Maintenance budget lines** page, you can manually add a new budget line by selecting **New** and then making selections on the line.</span></span> <span data-ttu-id="1c107-133">Veja alguns exemplos das situações onde essa abordagem pode ser útil:</span><span class="sxs-lookup"><span data-stu-id="1c107-133">Here are some examples of situations where this approach might be useful:</span></span>

- <span data-ttu-id="1c107-134">Você sabe que a restauração de alguns ativos está atualmente na fase de planejamento, mas trabalhos relacionados não foram criados no Gerenciamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="1c107-134">You know that refurbishment of some assets is currently in the planning phase, but related jobs haven't yet been created in Asset Management.</span></span> <span data-ttu-id="1c107-135">Entretanto, você deseja que custos de orçamento para esses trabalhos sejam incluídos no orçamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="1c107-135">However, you want budget costs for those jobs to be included in the maintenance budget.</span></span>
- <span data-ttu-id="1c107-136">Novos ativos ou tipos de ativos foram criados já que você realizou o orçamento de manutenção, mas planos de manutenção não foram configurados para esses ativos ou tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="1c107-136">New assets or asset types have been created since you made the maintenance budget, but maintenance plans haven't yet been set up on those assets or asset types.</span></span> <span data-ttu-id="1c107-137">Entretanto, você deseja que custos de orçamento para esses tipos de ativos sejam incluídos no orçamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="1c107-137">However, you want budget costs for those asset types to be included in the maintenance budget.</span></span>
