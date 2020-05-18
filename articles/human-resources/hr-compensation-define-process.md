---
title: Definir processo de remuneração e calcular resultados
description: Os processos de remuneração são usados para determinar os novos valores e prêmios de remuneração para os funcionários inscritos em planos de remuneração fixos e variáveis.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 058102b369ec7ed79874017e50a06d265b96b424
ms.sourcegitcommit: 1852f08f015acd106f4cefd03fa07985dc009123
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198757"
---
# <a name="define-compensation-process-and-calculate-results"></a><span data-ttu-id="47f27-103">Definir processo de remuneração e calcular resultados</span><span class="sxs-lookup"><span data-stu-id="47f27-103">Define compensation process and calculate results</span></span>

<span data-ttu-id="47f27-104">Os processos de remuneração são usados para determinar os novos valores e prêmios de remuneração para os funcionários inscritos em planos de remuneração fixos e variáveis.</span><span class="sxs-lookup"><span data-stu-id="47f27-104">Compensation processes are used to determine new compensation amounts and awards for employees enrolled in fixed and variable compensation plans.</span></span> <span data-ttu-id="47f27-105">Os processos de remuneração pode ser executados várias vezes para executar análises de hipótese para verificar se todas as alterações e definições estão corretas.</span><span class="sxs-lookup"><span data-stu-id="47f27-105">Compensation processes can be run multiple times to perform "what-if" analysis, to verify all changes and settings are correct.</span></span> <span data-ttu-id="47f27-106">Este procedimento criará um processo de remuneração, executará o processo e exibirá os resultados.</span><span class="sxs-lookup"><span data-stu-id="47f27-106">This procedure will create a compensation process, run the process, and view the results.</span></span> <span data-ttu-id="47f27-107">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="47f27-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-compensation-process"></a><span data-ttu-id="47f27-108">Crie um processo de remuneração</span><span class="sxs-lookup"><span data-stu-id="47f27-108">Create a compensation process</span></span>
1. <span data-ttu-id="47f27-109">Vá para Recursos humanos > Remuneração > Processo > Processos de remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-109">Go to Human resources > Compensation > Process > Compensation processes.</span></span>
2. <span data-ttu-id="47f27-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="47f27-110">Click New.</span></span>
3. <span data-ttu-id="47f27-111">No campo Processo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="47f27-111">In the Process field, type a value.</span></span>
4. <span data-ttu-id="47f27-112">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="47f27-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="47f27-113">No campo Tipo de processo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="47f27-113">In the Process type field, select an option.</span></span>
    * <span data-ttu-id="47f27-114">Um ciclo especifica o período avaliado para determinar a remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-114">A cycle specifies the time period evaluated to determine compensation.</span></span> <span data-ttu-id="47f27-115">A avaliação considera as posições que foram mantidas pelos funcionários, as classificações de desempenho a serem incluídas, o cálculo da porcentagem de tempo no qual o funcionário foi empregado durante o ciclo e muito mais.</span><span class="sxs-lookup"><span data-stu-id="47f27-115">The evaluation considers which positions were held by employees, which performance ratings to include, calculation of the percentage of time the employee was employed during the cycle, and more.</span></span> <span data-ttu-id="47f27-116">Um exemplo de uma data de início do ciclo pode ser o primeiro dia do ano fiscal anterior.</span><span class="sxs-lookup"><span data-stu-id="47f27-116">An example of a cycle start date might be the first day of the past fiscal year.</span></span>  
6. <span data-ttu-id="47f27-117">No campo Início do ciclo, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="47f27-117">In the Cycle start field, enter a date.</span></span>
    * <span data-ttu-id="47f27-118">A data final do ciclo é importante porque é a data usada para determinar os funcionários que estavam empregados e inscritos ativamente em um ou mais planos de remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-118">The cycle end date is  important because it is the date used to determine which employees were actively employed and enrolled in one or more compensation plans.</span></span>  
7. <span data-ttu-id="47f27-119">No campo Fim do ciclo, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="47f27-119">In the Cycle end field, enter a date.</span></span>
    * <span data-ttu-id="47f27-120">A data ativa da transação é a data na qual as novas taxas de remuneração devem entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="47f27-120">The transaction active date is the date the new compensation rates should take effect.</span></span> <span data-ttu-id="47f27-121">Muitas empresas incluem alguns meses entre a fim de um ciclo e o tempo no qual as novas taxas de remuneração entram em vigor.</span><span class="sxs-lookup"><span data-stu-id="47f27-121">Many companies include a few months between their end of a cycle and the time the new compensation rates go into effect.</span></span> <span data-ttu-id="47f27-122">O tempo adicional é usado para processamento e revisão da nova remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-122">The additional time is used for processing and reviewing the new compensation.</span></span>  
8. <span data-ttu-id="47f27-123">No campo Data de ativação da transação, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="47f27-123">In the Transaction active date field, enter a date.</span></span>
    * <span data-ttu-id="47f27-124">A data pontual é usada para planos de remuneração de variável que determinam o valor do prêmio de um funcionário com base na taxa de remuneração nesse momento.</span><span class="sxs-lookup"><span data-stu-id="47f27-124">The point-in-time date is used for variable compensation plans that determine an employee's award amount based on their compensation rate at this point in time.</span></span>  
    * <span data-ttu-id="47f27-125">A data de contratação proporcional para pagamento fixo é usada com planos de remuneração fixa com uma regra de contratação de porcentagem.</span><span class="sxs-lookup"><span data-stu-id="47f27-125">The fixed pay pro rated hire date is used with fixed compensation plans with a hire rule of Percent.</span></span>  <span data-ttu-id="47f27-126">Os funcionários que são contratados entre o início do ciclo e a data de contratação proporcional para pagamento fixo receberão 100% do aumento calculado de remuneração, em vez de porcentagem proporcional.</span><span class="sxs-lookup"><span data-stu-id="47f27-126">Employees who are hired between the cycle start and the fixed pay pro rated hire date will receive 100% of their calculated compensation increase, instead of pro-rated percentage.</span></span>  
9. <span data-ttu-id="47f27-127">No campo Data de contratação proporcional para pagamento fixo, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="47f27-127">In the Fixed pay pro rated hire date field, enter a date.</span></span>
    * <span data-ttu-id="47f27-128">O prazo da revisão é a data na qual todos os resultados do processo devem ser revisados, de modo que possam ser carregados no registro de remuneração do funcionário antes da data ativa da transação.</span><span class="sxs-lookup"><span data-stu-id="47f27-128">The review deadline is the date by which all process results should be reviewed so that they can be loaded into an employee's compensation record before the transaction active date.</span></span> <span data-ttu-id="47f27-129">Este campo serve somente para informar.</span><span class="sxs-lookup"><span data-stu-id="47f27-129">This field is informational only.</span></span>  
10. <span data-ttu-id="47f27-130">No campo Prazo final de revisão, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="47f27-130">In the Review deadline field, enter a date.</span></span>
11. <span data-ttu-id="47f27-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="47f27-131">Click Save.</span></span>

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a><span data-ttu-id="47f27-132">Configure os planos de remuneração e ações de um processo de remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-132">Setup the compensation plans and actions for a compensation process</span></span>
1. <span data-ttu-id="47f27-133">Clique em Configuração.</span><span class="sxs-lookup"><span data-stu-id="47f27-133">Click Setup.</span></span>
    * <span data-ttu-id="47f27-134">A página Configuração é usada para selecionar os planos a serem processados como parte desse processo de remuneração, bem como as ações que devem ser executadas em relação a cada plano.</span><span class="sxs-lookup"><span data-stu-id="47f27-134">The Setup page is used to select which plans to process as part of this compensation process, as well as which actions should be taken against each plan.</span></span>  
2. <span data-ttu-id="47f27-135">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="47f27-135">In the Plan field, enter or select a value.</span></span>
3. <span data-ttu-id="47f27-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="47f27-136">Click Save.</span></span>
4. <span data-ttu-id="47f27-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-137">Click Add.</span></span>
5. <span data-ttu-id="47f27-138">No campo Ação, selecione um tipo de ação de Capital próprio.</span><span class="sxs-lookup"><span data-stu-id="47f27-138">In the Action field, select an Equity type of action.</span></span>
6. <span data-ttu-id="47f27-139">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-139">Click Add.</span></span>
7. <span data-ttu-id="47f27-140">No campo Ação, selecione um tipo de ação de Mérito.</span><span class="sxs-lookup"><span data-stu-id="47f27-140">In the Action field, select a Merit type of action.</span></span>
    * <span data-ttu-id="47f27-141">As ações de remuneração podem ser "encadeadas" juntas usando o campo Usar resultado anterior para indicar se a ação selecionada deve usar o pagamento base de funcionários ou o resultado da ação anterior, como ponto de partida para o cálculo dessa ação.</span><span class="sxs-lookup"><span data-stu-id="47f27-141">Compensation actions can be "chained" together using the Use previous result field to indicate whether the selected action should use the employees base pay or the result of the previous action as the starting point for this action's calculation.</span></span>  
8. <span data-ttu-id="47f27-142">Selecione Sim no campo Usar resultado anterior.</span><span class="sxs-lookup"><span data-stu-id="47f27-142">Select Yes in the Use previous result field.</span></span>
9. <span data-ttu-id="47f27-143">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-143">Click Add.</span></span>
10. <span data-ttu-id="47f27-144">No campo Ação, selecione um tipo de ação Geral.</span><span class="sxs-lookup"><span data-stu-id="47f27-144">In the Action field, select a General type of Action.</span></span>
    * <span data-ttu-id="47f27-145">Os diferentes tipos de ação de remuneração permitem campos diferentes.</span><span class="sxs-lookup"><span data-stu-id="47f27-145">Different compensation action types enable different fields.</span></span> <span data-ttu-id="47f27-146">Para um tipo de ação de remuneração Geral, podem ser especificados um valor de aumento ou uma porcentagem de aumento.</span><span class="sxs-lookup"><span data-stu-id="47f27-146">For a General compensation action type, an increase percent or increase amount can be specified.</span></span>  
11. <span data-ttu-id="47f27-147">Selecione a opção Selecionar valor de aumento.</span><span class="sxs-lookup"><span data-stu-id="47f27-147">Select the Select increase amount option.</span></span>
12. <span data-ttu-id="47f27-148">No campo Aumentar valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="47f27-148">In the Increase amount field, enter a number.</span></span>
13. <span data-ttu-id="47f27-149">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-149">Click Add.</span></span>
14. <span data-ttu-id="47f27-150">No campo Ação, selecione um tipo de ação Promoção.</span><span class="sxs-lookup"><span data-stu-id="47f27-150">In the Action field, select a Promotion type of Action.</span></span>
    * <span data-ttu-id="47f27-151">Os tipos de ação de Promoção e Outra alteração de nível habilitam usuários para fazer ajustes manuais na remuneração do funcionário.</span><span class="sxs-lookup"><span data-stu-id="47f27-151">Promotion and Other level change action types enable users to make manual adjustments to employee compensation.</span></span> <span data-ttu-id="47f27-152">As recomendações podem ser habilitadas para esses tipos de ação, bem como para outros tipos de ação para que seja possível inserir um novo valor recomendado de remuneração de um funcionário.</span><span class="sxs-lookup"><span data-stu-id="47f27-152">Recommendations can be enabled for these action types, as well as other action types to enable you to enter a new recommended compensation value for an employee.</span></span>  
15. <span data-ttu-id="47f27-153">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-153">Click Add.</span></span>
16. <span data-ttu-id="47f27-154">No campo Tipo, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="47f27-154">In the Type field, select an option.</span></span>
    * <span data-ttu-id="47f27-155">Os planos de remuneração fixa e variável podem ser realizados no mesmo processo de remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-155">Fixed and variable compensation plans can be run in the same compensation process.</span></span>  
17. <span data-ttu-id="47f27-156">No campo Plano, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="47f27-156">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="47f27-157">Use a caixa de seleção Habilitar pagamento por desempenho para determinar se os valores de remuneração fixos e variáveis devem ser ajustados com base na classificação de desempenho do funcionário.</span><span class="sxs-lookup"><span data-stu-id="47f27-157">Use the Enable pay for performance check box to determined whether fixed and variable compensation amounts should be adjusted based on the employee's performance rating.</span></span>  
    * <span data-ttu-id="47f27-158">O aproveitamento pode ser substituído em planos de remuneração variável.</span><span class="sxs-lookup"><span data-stu-id="47f27-158">Leverage can be overridden on variable compensation plans.</span></span>  
18. <span data-ttu-id="47f27-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="47f27-159">Click Save.</span></span>
19. <span data-ttu-id="47f27-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="47f27-160">Click Add.</span></span>
20. <span data-ttu-id="47f27-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="47f27-161">Close the page.</span></span>

## <a name="run-the-compensation-process"></a><span data-ttu-id="47f27-162">Execute o processo de remuneração</span><span class="sxs-lookup"><span data-stu-id="47f27-162">Run the compensation process</span></span>
1. <span data-ttu-id="47f27-163">Clique em Executar processo.</span><span class="sxs-lookup"><span data-stu-id="47f27-163">Click Run process.</span></span>
    * <span data-ttu-id="47f27-164">O controle Mostrar resultados do processamento permite exibir mensagens de processamento para o processo de remuneração completo quando processando for concluído.</span><span class="sxs-lookup"><span data-stu-id="47f27-164">The Show processing results control lets you view processing messages for the complete compensation process when processing has finished.</span></span>  
2. <span data-ttu-id="47f27-165">Selecione Sim no campo Mostrar resultados do processamento.</span><span class="sxs-lookup"><span data-stu-id="47f27-165">Select Yes in the Show processing results field.</span></span>
3. <span data-ttu-id="47f27-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="47f27-166">Click OK.</span></span>

## <a name="view-the-results"></a><span data-ttu-id="47f27-167">Exiba os resultados</span><span class="sxs-lookup"><span data-stu-id="47f27-167">View the results</span></span>
1. <span data-ttu-id="47f27-168">Clique em Resultados do processo.</span><span class="sxs-lookup"><span data-stu-id="47f27-168">Click Process results.</span></span>
2. <span data-ttu-id="47f27-169">Clique em Resultados de funcionários.</span><span class="sxs-lookup"><span data-stu-id="47f27-169">Click Employee results.</span></span>
3. <span data-ttu-id="47f27-170">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="47f27-170">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="47f27-171">Expanda a seção Remuneração fixa.</span><span class="sxs-lookup"><span data-stu-id="47f27-171">Expand the Fixed compensation section.</span></span>
    * <span data-ttu-id="47f27-172">Expanda as Guias Rápidas para exibir os resultados do processo.</span><span class="sxs-lookup"><span data-stu-id="47f27-172">Expand the FastTabs to view the results of the process.</span></span> <span data-ttu-id="47f27-173">Se Habilitar recomendações foi marcado para uma ação de remuneração, os campos Recomendação serão ativados para essa ação.</span><span class="sxs-lookup"><span data-stu-id="47f27-173">If Enable recommendations was marked for a compensation action, the Recommendation fields will be enabled for that action.</span></span>  
5. <span data-ttu-id="47f27-174">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="47f27-174">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="47f27-175">Os resultados de um único funcionário podem ser exibidos clicando no botão Exibir resultados.</span><span class="sxs-lookup"><span data-stu-id="47f27-175">The results for a single employee can be viewed by clicking the View results button.</span></span>  
    * <span data-ttu-id="47f27-176">Você pode substituir o valor calculado de remuneração ajustando a porcentagem ou o valor do aumento nos campos Recomendação.</span><span class="sxs-lookup"><span data-stu-id="47f27-176">You can overwrite the calculated compensation amount by adjusting the percent or the increase amount in the Recommendation fields.</span></span>  
6. <span data-ttu-id="47f27-177">No campo Porcentagem recomendada, insira um número.</span><span class="sxs-lookup"><span data-stu-id="47f27-177">In the percent recommended field, enter a number.</span></span>
7. <span data-ttu-id="47f27-178">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="47f27-178">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="47f27-179">No campo Porcentagem recomendada, insira um número.</span><span class="sxs-lookup"><span data-stu-id="47f27-179">In the percent recommended field, enter a number.</span></span>
    * <span data-ttu-id="47f27-180">Recalcular pode ser usado para ignorar todas as alterações feitas no registro existente e para gerar um novo resultado de remuneração do funcionário selecionado.</span><span class="sxs-lookup"><span data-stu-id="47f27-180">Recalculate can be used to ignore any changes made to the existing record and generate a new compensation result for the selected employee.</span></span>  
    * <span data-ttu-id="47f27-181">Quando todas as alterações forem concluídas para um funcionário, altere o status para Aprovado.</span><span class="sxs-lookup"><span data-stu-id="47f27-181">When all changes are complete for an employee, change the status to Approved.</span></span>  
9. <span data-ttu-id="47f27-182">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="47f27-182">Click Change status.</span></span>
10. <span data-ttu-id="47f27-183">Clique em Aprovado.</span><span class="sxs-lookup"><span data-stu-id="47f27-183">Click Approved.</span></span>
    * <span data-ttu-id="47f27-184">Depois que o registro for aprovado, ele poderá ser carregado para o registro oficial de remuneração do funcionário.</span><span class="sxs-lookup"><span data-stu-id="47f27-184">After the record has been approved it can be loaded to the employee's official compensation record.</span></span> <span data-ttu-id="47f27-185">A nova remuneração será efetiva a partir da data da transação definida no processo de remuneração.</span><span class="sxs-lookup"><span data-stu-id="47f27-185">The new compensation will be effective as of the transaction date set on the compensation process.</span></span>  
