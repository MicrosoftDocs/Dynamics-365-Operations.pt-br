---
title: Desenvolver uma estrutura de remuneração
description: Este artigo mostra como criar um plano de remuneração fixa e inserir funcionários no plano com a qualificação.
author: andreabichsel
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: abdca618aa544e32b68f4bbf2578afb9ef1a5905
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052880"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="7604e-103">Desenvolver uma estrutura de remuneração</span><span class="sxs-lookup"><span data-stu-id="7604e-103">Develop a compensation structure</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="7604e-104">Este artigo mostra como criar um plano de remuneração fixa e inserir funcionários no plano com a qualificação.</span><span class="sxs-lookup"><span data-stu-id="7604e-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="7604e-105">Este artigo usa os dados de demonstração de USMF e se aplica aos gerentes de remuneração e benefícios.</span><span class="sxs-lookup"><span data-stu-id="7604e-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="7604e-106">Crie um plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="7604e-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="7604e-107">Selecione **Gerenciamento de remuneração**.</span><span class="sxs-lookup"><span data-stu-id="7604e-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="7604e-108">Selecione **Planos de remuneração fixa**.</span><span class="sxs-lookup"><span data-stu-id="7604e-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="7604e-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7604e-109">Select **New**.</span></span>

4. <span data-ttu-id="7604e-110">No campo **Plano**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="7604e-111">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="7604e-112">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7604e-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="7604e-113">No campo **Tipo**, selecione se o plano de remuneração fixa é um plano **Faixa**, **Classificação** ou **Etapa**.</span><span class="sxs-lookup"><span data-stu-id="7604e-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="7604e-114">A caixa de seleção **Recomendação permitida** atua como um valor padrão para todas as ações adicionadas a esse plano em um evento de processo.</span><span class="sxs-lookup"><span data-stu-id="7604e-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="7604e-115">Recomendações para permitir que seja possível substituir o valor de diretriz calculado ao processar a compensação.</span><span class="sxs-lookup"><span data-stu-id="7604e-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="7604e-116">O campo **Fora da tolerância de faixa salarial** permite que você especifique como deseja manipular os valores de remuneração que estejam fora do intervalo especificado da estrutura de remuneração para o nível específico.</span><span class="sxs-lookup"><span data-stu-id="7604e-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="7604e-117">Definir o campo **Fora da tolerância de faixa salarial** como **Nenhum** permite usar qualquer valor de remuneração.</span><span class="sxs-lookup"><span data-stu-id="7604e-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="7604e-118">A **tolerância de meios** adverte os usuários se o valor da remuneração for menor que o valor mínimo ou maior que o valor máximo de ponto de referência para esse nível.</span><span class="sxs-lookup"><span data-stu-id="7604e-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="7604e-119">Os usuários podem ignorar o aviso e continuar.</span><span class="sxs-lookup"><span data-stu-id="7604e-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="7604e-120">Uma **tolerância em vigor** gera uma mensagem de erro se a remuneração de um funcionário estiver fora dos pontos de referência mínimo e máximo para o nível e ajustará automaticamente a remuneração do funcionário para estar no intervalo.</span><span class="sxs-lookup"><span data-stu-id="7604e-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="7604e-121">O campo **Regra de contratação** calcula a remuneração de um funcionário durante um evento do processo.</span><span class="sxs-lookup"><span data-stu-id="7604e-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="7604e-122">Uma **Regra de contratação** de **Porcentagem** calcula um aumento que é distribuído para o período de tempo no qual o funcionário foi contratado no ciclo.</span><span class="sxs-lookup"><span data-stu-id="7604e-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="7604e-123">No campo **Moeda**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="7604e-124">No campo **Conversão da taxa de pagamento**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="7604e-125">Expandir a seção **Matriz de variação de utilização**.</span><span class="sxs-lookup"><span data-stu-id="7604e-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="7604e-126">Opcionalmente, adicione registros de utilização do intervalo para obter funcionários no valor médio mais rápido e lento para alcançar o máximo do intervalo.</span><span class="sxs-lookup"><span data-stu-id="7604e-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="7604e-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7604e-127">Select **Save**.</span></span> <span data-ttu-id="7604e-128">Isso habilita o botão **Configurar remuneração** e continua definindo sua estrutura de remuneração para o plano.</span><span class="sxs-lookup"><span data-stu-id="7604e-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="7604e-129">Selecione **Configurar remuneração**.</span><span class="sxs-lookup"><span data-stu-id="7604e-129">Select **Set up compensation**.</span></span> <span data-ttu-id="7604e-130">É possível criar uma estrutura de remuneração usando um destes três métodos:</span><span class="sxs-lookup"><span data-stu-id="7604e-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="7604e-131">Criar uma estrutura totalmente nova selecionando um conjunto de pontos de referência e adicionando os níveis para criar sua própria estrutura.</span><span class="sxs-lookup"><span data-stu-id="7604e-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="7604e-132">Copiar uma estrutura de remuneração de um plano existente como ponto de partida e altera-la para o novo plano.</span><span class="sxs-lookup"><span data-stu-id="7604e-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="7604e-133">Selecionar uma grade de remuneração existente.</span><span class="sxs-lookup"><span data-stu-id="7604e-133">Select an existing compensation grid.</span></span> <span data-ttu-id="7604e-134">Se um plano já estiver usando a grade de remuneração, o outro plano também refletirá todas as alterações feitas na grade.</span><span class="sxs-lookup"><span data-stu-id="7604e-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="7604e-135">Selecione **Criar nova matriz de remuneração a partir de uma existente**.</span><span class="sxs-lookup"><span data-stu-id="7604e-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="7604e-136">No campo **Copiar da grade**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="7604e-137">Opcionalmente, você pode alterar o nome da grade de remuneração criada, copiando a grade selecionada.</span><span class="sxs-lookup"><span data-stu-id="7604e-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="7604e-138">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7604e-138">Select **OK**.</span></span>

19. <span data-ttu-id="7604e-139">Selecione **Alteração em massa**.</span><span class="sxs-lookup"><span data-stu-id="7604e-139">Select **Mass change**.</span></span> <span data-ttu-id="7604e-140">A **alteração em massa** permite que você mantenha os valores da matriz de remuneração aplicando uma porcentagem ou um valor de aumento liso a um ou vários níveis ou pontos de referência.</span><span class="sxs-lookup"><span data-stu-id="7604e-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="7604e-141">No campo **Valor do ajuste**, insira um número.</span><span class="sxs-lookup"><span data-stu-id="7604e-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="7604e-142">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="7604e-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="7604e-143">Clique em **Aplicar à grade**.</span><span class="sxs-lookup"><span data-stu-id="7604e-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="7604e-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7604e-144">Close the page.</span></span> <span data-ttu-id="7604e-145">Depois de criar a estrutura de remuneração, é possível selecionar qual dos pontos de referência usar como ponto de controle para o plano de remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="7604e-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="7604e-146">O ponto de controle é usado para calcular a taxa de Compa de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="7604e-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="7604e-147">No campo **Ponto de controle**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="7604e-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7604e-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="7604e-149">Criar uma regra de qualificação para o plano de remuneração fixa</span><span class="sxs-lookup"><span data-stu-id="7604e-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="7604e-150">Não é possível atribuir um plano de remuneração fixa a um funcionário até definir regras de qualificação para o plano.</span><span class="sxs-lookup"><span data-stu-id="7604e-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="7604e-151">Selecione **Regras de qualificação**.</span><span class="sxs-lookup"><span data-stu-id="7604e-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="7604e-152">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7604e-152">Select **New**.</span></span>

3. <span data-ttu-id="7604e-153">No campo **Qualificação**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="7604e-154">No campo **Descrição**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="7604e-155">No campo **Data efetiva**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="7604e-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="7604e-156">Os planos de remuneração fixa e variável usam regras de qualificação.</span><span class="sxs-lookup"><span data-stu-id="7604e-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="7604e-157">No campo **Tipo**, selecione o tipo de plano.</span><span class="sxs-lookup"><span data-stu-id="7604e-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="7604e-158">No campo **Plano**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7604e-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="7604e-159">Selecione os critérios que funcionário deve atender aos requisitos a seguir para serem qualificados para a inscrição em um plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="7604e-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="7604e-160">Os critérios podem incluir:</span><span class="sxs-lookup"><span data-stu-id="7604e-160">Criteria can include:</span></span>

    - <span data-ttu-id="7604e-161">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="7604e-161">**Department**</span></span>
    - <span data-ttu-id="7604e-162">**Sindicato**</span><span class="sxs-lookup"><span data-stu-id="7604e-162">**Labor union**</span></span>
    - <span data-ttu-id="7604e-163">**Localização** (**Região de remuneração**)</span><span class="sxs-lookup"><span data-stu-id="7604e-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="7604e-164">**Trabalho**</span><span class="sxs-lookup"><span data-stu-id="7604e-164">**Job**</span></span>
    - <span data-ttu-id="7604e-165">**Função**</span><span class="sxs-lookup"><span data-stu-id="7604e-165">**Function**</span></span>
    - <span data-ttu-id="7604e-166">**Tipo de trabalho**</span><span class="sxs-lookup"><span data-stu-id="7604e-166">**Job type**</span></span>
    - <span data-ttu-id="7604e-167">**Nível salarial**</span><span class="sxs-lookup"><span data-stu-id="7604e-167">**Compensation level**</span></span>
    
    <span data-ttu-id="7604e-168">O funcionário deve atender todos os requisitos especificados para ser qualificado para a inscrição em um plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="7604e-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="7604e-169">Se nenhum critério for especificado, todos os funcionários estão qualificadas para o plano de remuneração.</span><span class="sxs-lookup"><span data-stu-id="7604e-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="7604e-170">Se um funcionário não atender aos critérios especificados na regra de qualificação, ou uma regra de qualificação não tiver sido especificada para um plano de remuneração, o plano de remuneração não aparecerá na pesquisa ao criar um registro de compensação fixa para um funcionário.</span><span class="sxs-lookup"><span data-stu-id="7604e-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="7604e-171">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7604e-171">Close the page.</span></span>

8. <span data-ttu-id="7604e-172">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7604e-172">Close the page.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]