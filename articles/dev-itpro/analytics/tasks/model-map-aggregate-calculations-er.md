---
title: Usar configurações de mapeamento de modelo para cálculos agregados no nível do banco de dados
description: Este procedimento fornece informações sobre como criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a462a3997644a494b5cea89c9530ddba67c32450
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544348"
---
# <a name="use-model-mapping-configurations-for-aggregate-calculations-at-the-database-level"></a><span data-ttu-id="5071b-103">Usar configurações de mapeamento de modelo para cálculos agregados no nível do banco de dados</span><span class="sxs-lookup"><span data-stu-id="5071b-103">Use model mapping configurations for aggregate calculations at the database level</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5071b-104">Este procedimento fornece informações sobre como criar uma nova configuração de mapeamento de modelo de Relatório eletrônico (ER) e usar funções de ER internas para obter cálculos agregados eficientes.</span><span class="sxs-lookup"><span data-stu-id="5071b-104">This procedure provides information about how to design a new Electronic reporting (ER) model mapping configuration and use built-in ER functions for efficient aggregate calculations.</span></span> <span data-ttu-id="5071b-105">Neste procedimento, você criará uma configuração para a empresa de exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="5071b-105">In this procedure you will create a configuration for the sample company, Litware, Inc.</span></span> 

<span data-ttu-id="5071b-106">Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="5071b-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="5071b-107">Estas etapas podem ser concluídas usando qualquer conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="5071b-107">These steps can be completed using any dataset.</span></span>

 <span data-ttu-id="5071b-108">Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento "O ER melhora a eficiência de cálculos agregados executando-os no nível do banco de dados (Parte 1: Preparar configurações)”.</span><span class="sxs-lookup"><span data-stu-id="5071b-108">To complete these steps, you must first complete the steps in the procedure, “ER improves the efficiency of aggregate calculations by performing them on database level (Part 1: Prepare configurations).”</span></span>

1. <span data-ttu-id="5071b-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="5071b-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="5071b-110">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="5071b-110">In the tree, expand 'Intrastat model'.</span></span>
3. <span data-ttu-id="5071b-111">Na árvore, selecione "Intrastat model\Intrastat sample mapping".</span><span class="sxs-lookup"><span data-stu-id="5071b-111">In the tree, select 'Intrastat model\Intrastat sample mapping'.</span></span>
4. <span data-ttu-id="5071b-112">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="5071b-112">Click Designer.</span></span>
5. <span data-ttu-id="5071b-113">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="5071b-113">Click Designer.</span></span>
6. <span data-ttu-id="5071b-114">Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.</span><span class="sxs-lookup"><span data-stu-id="5071b-114">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
7. <span data-ttu-id="5071b-115">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="5071b-115">Click Add root.</span></span>
    * <span data-ttu-id="5071b-116">Adicionar uma nova fonte de dados que represente os registros que deseja agrupar.</span><span class="sxs-lookup"><span data-stu-id="5071b-116">Add a new data source representing records you want to group.</span></span>  
8. <span data-ttu-id="5071b-117">No campo Nome, digite 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="5071b-117">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="5071b-118">Transações</span><span class="sxs-lookup"><span data-stu-id="5071b-118">Transactions</span></span>  
9. <span data-ttu-id="5071b-119">No campo Tabela, digite 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="5071b-119">In the Table field, type 'Intrastat'.</span></span>
    * <span data-ttu-id="5071b-120">Intrastat</span><span class="sxs-lookup"><span data-stu-id="5071b-120">Intrastat</span></span>  
10. <span data-ttu-id="5071b-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5071b-121">Click OK.</span></span>
11. <span data-ttu-id="5071b-122">Na árvore, selecione 'Funções\Agrupar por'.</span><span class="sxs-lookup"><span data-stu-id="5071b-122">In the tree, select 'Functions\Group by'.</span></span>
    * <span data-ttu-id="5071b-123">Este tipo de fonte de dados é usado para apresentar uma nova fonte de dados no tempo de execução para agrupar registros e calcular agregações necessárias.</span><span class="sxs-lookup"><span data-stu-id="5071b-123">This data source type is used to introduce a new data source at run-time to group records and to calculate required aggregations.</span></span>  
12. <span data-ttu-id="5071b-124">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="5071b-124">Click Add root.</span></span>
13. <span data-ttu-id="5071b-125">No campo Nome, digite 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-125">In the Name field, type 'TransactionsGroups'.</span></span>
    * <span data-ttu-id="5071b-126">TransactionsGroups</span><span class="sxs-lookup"><span data-stu-id="5071b-126">TransactionsGroups</span></span>  
14. <span data-ttu-id="5071b-127">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="5071b-127">Click Edit group by.</span></span>
15. <span data-ttu-id="5071b-128">Na árvore, selecione 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="5071b-128">In the tree, select 'Transactions'.</span></span>
    * <span data-ttu-id="5071b-129">Selecione a fonte de dados adicionada do tipo 'Lista de registros' que represente os registros que deseja agrupar.</span><span class="sxs-lookup"><span data-stu-id="5071b-129">Select the added data source of the ‘Record list’ type that represents the records that you want to group.</span></span>  
16. <span data-ttu-id="5071b-130">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="5071b-130">Click Add field to.</span></span>
17. <span data-ttu-id="5071b-131">Clique em O que agrupar.</span><span class="sxs-lookup"><span data-stu-id="5071b-131">Click What to group.</span></span>
18. <span data-ttu-id="5071b-132">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="5071b-132">In the tree, expand 'Transactions'.</span></span>
19. <span data-ttu-id="5071b-133">Na árvore, selecione "Transactions\Direction".</span><span class="sxs-lookup"><span data-stu-id="5071b-133">In the tree, select 'Transactions\Direction'.</span></span>
20. <span data-ttu-id="5071b-134">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="5071b-134">Click Add field to.</span></span>
21. <span data-ttu-id="5071b-135">Clique em Campos agrupados.</span><span class="sxs-lookup"><span data-stu-id="5071b-135">Click Grouped fields.</span></span>
    * <span data-ttu-id="5071b-136">Selecione o campo para especificar o nível de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="5071b-136">Select the field to specify the grouping level.</span></span> <span data-ttu-id="5071b-137">Com base nessa seleção, a fonte de dados retornará no tempo de execução a mesma quantidade de grupos de transações e códigos de direção que serão encontrados na tabela intrastat.</span><span class="sxs-lookup"><span data-stu-id="5071b-137">Based on this selection, the data source will return at run-time as many groups of transactions as there are direction codes that will be met in the Intrastat table.</span></span>  
22. <span data-ttu-id="5071b-138">Na árvore, selecione "Transactions\Invoice amount(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="5071b-138">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
    * <span data-ttu-id="5071b-139">Selecione o campo para especificar a fonte para o cálculo de agregação.</span><span class="sxs-lookup"><span data-stu-id="5071b-139">Select the field to specify the source for aggregation calculation.</span></span>  
23. <span data-ttu-id="5071b-140">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="5071b-140">Click Add field to.</span></span>
24. <span data-ttu-id="5071b-141">Clique em Campos de agregação.</span><span class="sxs-lookup"><span data-stu-id="5071b-141">Click Aggregation fields.</span></span>
25. <span data-ttu-id="5071b-142">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5071b-142">In the list, mark the selected row.</span></span>
26. <span data-ttu-id="5071b-143">No campo Método, selecione 'Soma'.</span><span class="sxs-lookup"><span data-stu-id="5071b-143">In the Method field, select 'Sum'.</span></span>
    * <span data-ttu-id="5071b-144">Selecione o tipo de agregação.</span><span class="sxs-lookup"><span data-stu-id="5071b-144">Select the aggregation type.</span></span>  
27. <span data-ttu-id="5071b-145">No campo Nome, digite 'SumOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="5071b-145">In the Name field, type 'SumOfAmountMST'.</span></span>
    * <span data-ttu-id="5071b-146">Especifique o nome dessa agregação na fonte de dados configurada.</span><span class="sxs-lookup"><span data-stu-id="5071b-146">Specify the name of this aggregation in the configured data source.</span></span>  
28. <span data-ttu-id="5071b-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5071b-147">Click Save.</span></span>
    * <span data-ttu-id="5071b-148">Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução no banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="5071b-148">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in the SQL database.</span></span>  
29. <span data-ttu-id="5071b-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5071b-149">Close the page.</span></span>
30. <span data-ttu-id="5071b-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5071b-150">Click OK.</span></span>
31. <span data-ttu-id="5071b-151">Na árvore, expanda 'Totais'.</span><span class="sxs-lookup"><span data-stu-id="5071b-151">In the tree, expand 'Totals'.</span></span>
32. <span data-ttu-id="5071b-152">Na árvore, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-152">In the tree, expand 'TransactionsGroups'.</span></span>
33. <span data-ttu-id="5071b-153">Na árvore, expanda "TransactionsGroups\aggregated".</span><span class="sxs-lookup"><span data-stu-id="5071b-153">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
34. <span data-ttu-id="5071b-154">Na árvore, selecione "TransactionsGroups\aggregated\SumOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="5071b-154">In the tree, select 'TransactionsGroups\aggregated\SumOfAmountMST'.</span></span>
35. <span data-ttu-id="5071b-155">Na árvore, selecione "Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')".</span><span class="sxs-lookup"><span data-stu-id="5071b-155">In the tree, select 'Totals\Total invoice value(TotalInvoiceValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$AmountMSTRounded')'.</span></span>
36. <span data-ttu-id="5071b-156">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="5071b-156">Click Bind.</span></span>
    * <span data-ttu-id="5071b-157">Com base nessa configuração, essa fonte de dados calculará a soma dos valores do campo 'AmountMST' para cada grupo de transações.</span><span class="sxs-lookup"><span data-stu-id="5071b-157">Based on this setting, this data source will calculate the sum of values of the ‘AmountMST’ field for each groups of transactions.</span></span> <span data-ttu-id="5071b-158">Esse cálculo de agregação estará disponível como o item TransactionsGroups.aggregated.TotalAmount.</span><span class="sxs-lookup"><span data-stu-id="5071b-158">This aggregation calculation will be available as TransactionsGroups.aggregated.TotalAmount item.</span></span>  
37. <span data-ttu-id="5071b-159">Na árvore, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-159">In the tree, expand 'TransactionsGroups'.</span></span>
38. <span data-ttu-id="5071b-160">Na árvore, selecione 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-160">In the tree, select 'TransactionsGroups'.</span></span>
39. <span data-ttu-id="5071b-161">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="5071b-161">Click Edit.</span></span>
40. <span data-ttu-id="5071b-162">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="5071b-162">Click Edit group by.</span></span>
41. <span data-ttu-id="5071b-163">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="5071b-163">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="5071b-164">Na árvore, selecione "Transactions\Invoice amount(AmountMST)".</span><span class="sxs-lookup"><span data-stu-id="5071b-164">In the tree, select 'Transactions\Invoice amount(AmountMST)'.</span></span>
43. <span data-ttu-id="5071b-165">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="5071b-165">Click Add field to.</span></span>
44. <span data-ttu-id="5071b-166">Clique em Campos de agregação.</span><span class="sxs-lookup"><span data-stu-id="5071b-166">Click Aggregation fields.</span></span>
45. <span data-ttu-id="5071b-167">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5071b-167">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="5071b-168">No campo Método, selecione 'Máx.'.</span><span class="sxs-lookup"><span data-stu-id="5071b-168">In the Method field, select 'Max'.</span></span>
47. <span data-ttu-id="5071b-169">No campo Nome, digite 'MaxOfAmountMST'.</span><span class="sxs-lookup"><span data-stu-id="5071b-169">In the Name field, type 'MaxOfAmountMST'.</span></span>
48. <span data-ttu-id="5071b-170">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5071b-170">Click Save.</span></span>
    * <span data-ttu-id="5071b-171">Atualmente, a execução de fontes de dados GROUPBY pode ser traduzida para o nível do banco de dados SQL com algumas limitações.</span><span class="sxs-lookup"><span data-stu-id="5071b-171">Currently, the execution of GROUPBY data sources can be translated to the SQL database level with some limitations.</span></span> <span data-ttu-id="5071b-172">A tradução pode ser feita para fontes de dados do tipo 'Lista de registros' ou fontes de dados representadas como uma expressão usando a função FILTER.</span><span class="sxs-lookup"><span data-stu-id="5071b-172">Translation can be done for either data sources of the ‘Record list’ type or data sources represented as an expression using the FILTER function.</span></span> <span data-ttu-id="5071b-173">Também pode ser feita quando a única agregação estiver configurada para um único campo dos registros de agrupamento.</span><span class="sxs-lookup"><span data-stu-id="5071b-173">It can also be done when the only one aggregation is configured for a single field of the grouping records.</span></span>  
    * <span data-ttu-id="5071b-174">Observe que, apesar de mais de uma agregação ter sido configurada para o campo AmountMST, o campo 'Execução em' ainda indica que esse agrupamento será executado no tempo de execução no banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="5071b-174">Note that even though more than one aggregation was configured for the AmountMST field, the ‘Execution at’ field still indicates that this grouping will be performed at run-time in the SQL database.</span></span> <span data-ttu-id="5071b-175">Isso porque somente uma agregação é associada ao item do modelo de dados e será usada no tempo de execução para receber dados dessa fonte.</span><span class="sxs-lookup"><span data-stu-id="5071b-175">This is because only one aggregation is bound to the data model item and will be used at run-time to pull data from this data source.</span></span>  
49. <span data-ttu-id="5071b-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5071b-176">Close the page.</span></span>
50. <span data-ttu-id="5071b-177">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5071b-177">Click OK.</span></span>
51. <span data-ttu-id="5071b-178">Na árvore, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-178">In the tree, expand 'TransactionsGroups'.</span></span>
52. <span data-ttu-id="5071b-179">Na árvore, expanda "TransactionsGroups\aggregated".</span><span class="sxs-lookup"><span data-stu-id="5071b-179">In the tree, expand 'TransactionsGroups\aggregated'.</span></span>
53. <span data-ttu-id="5071b-180">Na árvore, selecione "TransactionsGroups\aggregated\MaxOfAmountMST".</span><span class="sxs-lookup"><span data-stu-id="5071b-180">In the tree, select 'TransactionsGroups\aggregated\MaxOfAmountMST'.</span></span>
54. <span data-ttu-id="5071b-181">Na árvore, selecione "Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')".</span><span class="sxs-lookup"><span data-stu-id="5071b-181">In the tree, select 'Totals\Total statistical value(TotalStatisticalValue) = IF(ISEMPTY(IntrastatTotals), 0.0, IntrastatTotals.aggregated.'$StatisticalValueRounded')'.</span></span>
55. <span data-ttu-id="5071b-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="5071b-182">Click Bind.</span></span>
56. <span data-ttu-id="5071b-183">Na árvore, expanda 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-183">In the tree, expand 'TransactionsGroups'.</span></span>
57. <span data-ttu-id="5071b-184">Na árvore, selecione 'TransactionsGroups'.</span><span class="sxs-lookup"><span data-stu-id="5071b-184">In the tree, select 'TransactionsGroups'.</span></span>
58. <span data-ttu-id="5071b-185">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="5071b-185">Click Edit.</span></span>
59. <span data-ttu-id="5071b-186">Clique em Editar grupo por.</span><span class="sxs-lookup"><span data-stu-id="5071b-186">Click Edit group by.</span></span>
    * <span data-ttu-id="5071b-187">Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução na memória porque as duas agregações do mesmo campo estão associadas aos itens do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="5071b-187">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory because both aggregations of the same field are bound to the data model items.</span></span>   
60. <span data-ttu-id="5071b-188">Na lista, marque ou desmarque todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="5071b-188">In the list, mark or unmark all rows.</span></span>
61. <span data-ttu-id="5071b-189">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="5071b-189">Click Delete.</span></span>
62. <span data-ttu-id="5071b-190">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="5071b-190">Click Yes.</span></span>
63. <span data-ttu-id="5071b-191">Clique em Excluir.</span><span class="sxs-lookup"><span data-stu-id="5071b-191">Click Delete.</span></span>
64. <span data-ttu-id="5071b-192">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="5071b-192">Click Yes.</span></span>
65. <span data-ttu-id="5071b-193">Clique em Adicionar campo a.</span><span class="sxs-lookup"><span data-stu-id="5071b-193">Click Add field to.</span></span>
66. <span data-ttu-id="5071b-194">Clique em O que agrupar.</span><span class="sxs-lookup"><span data-stu-id="5071b-194">Click What to group.</span></span>
67. <span data-ttu-id="5071b-195">Na árvore, expanda 'Registro de mercadoria(Intrastat)'.</span><span class="sxs-lookup"><span data-stu-id="5071b-195">In the tree, expand 'Commodity record(Intrastat)'.</span></span>
68. <span data-ttu-id="5071b-196">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5071b-196">Click Save.</span></span>
    * <span data-ttu-id="5071b-197">Observe que o campo 'Execução em' indica que esse agrupamento será executado no tempo de execução na memória mesmo que não haja nenhuma agregação definida e a fonte de dados selecionada do tipo 'Registros da tabela' refira-se à mesma tabela ‘Intrastat’.</span><span class="sxs-lookup"><span data-stu-id="5071b-197">Note that the ‘Execution at’ field indicates that this grouping will be performed at run-time in memory even though there are no aggregations defined and the selected data source of ‘Table records’ type refers to the same ‘Intrastat’ table.</span></span> <span data-ttu-id="5071b-198">Isso é porque a fonte de dados contém alguns campos calculados que ainda não podem ser traduzidos para o nível do banco de dados SQL.</span><span class="sxs-lookup"><span data-stu-id="5071b-198">This is because the data source contains some calculated fields which can’t yet be translated to the SQL database level.</span></span>  

