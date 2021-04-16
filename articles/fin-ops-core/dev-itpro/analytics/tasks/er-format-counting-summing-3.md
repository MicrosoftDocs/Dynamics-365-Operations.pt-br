---
title: ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 3)
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7073539ed4c1d9d5acbb0ca84b43538d87fc8b4b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748988"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="7e310-104">ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)</span><span class="sxs-lookup"><span data-stu-id="7e310-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7e310-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="7e310-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="7e310-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="7e310-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="7e310-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 2: configurar cálculos)".</span><span class="sxs-lookup"><span data-stu-id="7e310-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="7e310-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="7e310-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="7e310-109">Configurar este relatório para usar as informações de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="7e310-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="7e310-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7e310-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7e310-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="7e310-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="7e310-112">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="7e310-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="7e310-113">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="7e310-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="7e310-114">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="7e310-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="7e310-115">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="7e310-115">Click Designer.</span></span>
7. <span data-ttu-id="7e310-116">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7e310-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="7e310-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7e310-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="7e310-118">Adicione uma nova fonte de dados para obter a lista de blocos memorizados.</span><span class="sxs-lookup"><span data-stu-id="7e310-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="7e310-119">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="7e310-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="7e310-120">No campo Nome, digite '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="7e310-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="7e310-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="7e310-121">$BlocksList</span></span>  
11. <span data-ttu-id="7e310-122">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="7e310-122">Click Edit formula.</span></span>
12. <span data-ttu-id="7e310-123">Na árvore, selecione 'Funções de coleta de dados\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="7e310-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="7e310-124">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="7e310-124">Click Add function.</span></span>
14. <span data-ttu-id="7e310-125">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e310-125">Click Add data source.</span></span>
15. <span data-ttu-id="7e310-126">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="7e310-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="7e310-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="7e310-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="7e310-128">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="7e310-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="7e310-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="7e310-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="7e310-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7e310-130">Click Save.</span></span>
    * <span data-ttu-id="7e310-131">O padrão "\*" significa que todos os blocos serão incluídos na lista para este registro.</span><span class="sxs-lookup"><span data-stu-id="7e310-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="7e310-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e310-132">Close the page.</span></span>
19. <span data-ttu-id="7e310-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e310-133">Click OK.</span></span>
20. <span data-ttu-id="7e310-134">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="7e310-134">Click the Format tab.</span></span>
21. <span data-ttu-id="7e310-135">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="7e310-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="7e310-136">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7e310-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="7e310-137">Na árvore, selecione 'Texto\Sequência'.</span><span class="sxs-lookup"><span data-stu-id="7e310-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="7e310-138">No campo Nome, digite 'Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="7e310-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="7e310-139">Totais por blocos</span><span class="sxs-lookup"><span data-stu-id="7e310-139">Totals by blocks</span></span>  
25. <span data-ttu-id="7e310-140">No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="7e310-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="7e310-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e310-141">Click OK.</span></span>
27. <span data-ttu-id="7e310-142">Na árvore, selecione 'Intrastat\Dados\Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="7e310-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="7e310-143">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7e310-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="7e310-144">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="7e310-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="7e310-145">No campo Nome, digite 'Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="7e310-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="7e310-146">Código do bloco</span><span class="sxs-lookup"><span data-stu-id="7e310-146">Block code</span></span>  
31. <span data-ttu-id="7e310-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e310-147">Click OK.</span></span>
32. <span data-ttu-id="7e310-148">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7e310-148">Click Add String.</span></span>
33. <span data-ttu-id="7e310-149">No campo Nome, digite 'Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="7e310-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="7e310-150">Contagem de linhas</span><span class="sxs-lookup"><span data-stu-id="7e310-150">Lines counting</span></span>  
34. <span data-ttu-id="7e310-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e310-151">Click OK.</span></span>
35. <span data-ttu-id="7e310-152">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="7e310-152">Click Add String.</span></span>
36. <span data-ttu-id="7e310-153">No campo Nome, digite 'Valor total'.</span><span class="sxs-lookup"><span data-stu-id="7e310-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="7e310-154">Valor total</span><span class="sxs-lookup"><span data-stu-id="7e310-154">Total amount</span></span>  
37. <span data-ttu-id="7e310-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7e310-155">Click OK.</span></span>
38. <span data-ttu-id="7e310-156">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7e310-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="7e310-157">Na árvore, selecione '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="7e310-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="7e310-158">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7e310-158">Click Bind.</span></span>
    * <span data-ttu-id="7e310-159">Crie uma linha de resumo para cada bloco memorizado.</span><span class="sxs-lookup"><span data-stu-id="7e310-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="7e310-160">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="7e310-160">Click the Format tab.</span></span>
42. <span data-ttu-id="7e310-161">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="7e310-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="7e310-162">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7e310-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="7e310-163">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="7e310-163">Click Edit formula.</span></span>
45. <span data-ttu-id="7e310-164">No campo Fórmula, insira '"Id do bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="7e310-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="7e310-165">"Id do bloco: " &</span><span class="sxs-lookup"><span data-stu-id="7e310-165">"Block id: " &</span></span>  
46. <span data-ttu-id="7e310-166">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="7e310-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="7e310-167">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="7e310-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="7e310-168">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e310-168">Click Add data source.</span></span>
49. <span data-ttu-id="7e310-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7e310-169">Click Save.</span></span>
50. <span data-ttu-id="7e310-170">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e310-170">Close the page.</span></span>
51. <span data-ttu-id="7e310-171">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="7e310-171">Click the Format tab.</span></span>
52. <span data-ttu-id="7e310-172">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="7e310-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="7e310-173">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7e310-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="7e310-174">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="7e310-174">Click Edit formula.</span></span>
    * <span data-ttu-id="7e310-175">Crie saídas para o número de linhas para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="7e310-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="7e310-176">No campo Fórmula, insira '"Número de linhas neste bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="7e310-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="7e310-177">"Número de linhas neste bloco: " &</span><span class="sxs-lookup"><span data-stu-id="7e310-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="7e310-178">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="7e310-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="7e310-179">"Número de linhas neste bloco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="7e310-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="7e310-180">Na árvore, selecione 'Funções de coleta de dados\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="7e310-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="7e310-181">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="7e310-181">Click Add function.</span></span>
59. <span data-ttu-id="7e310-182">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e310-182">Click Add data source.</span></span>
60. <span data-ttu-id="7e310-183">No campo de fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="7e310-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="7e310-184">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="7e310-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="7e310-185">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="7e310-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="7e310-186">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="7e310-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="7e310-187">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e310-187">Click Add data source.</span></span>
64. <span data-ttu-id="7e310-188">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="7e310-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="7e310-189">"Número de linhas neste bloco: " & TEXT(COUNTIFS ('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="7e310-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="7e310-190">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="7e310-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="7e310-191">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e310-191">Click Add data source.</span></span>
67. <span data-ttu-id="7e310-192">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="7e310-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="7e310-193">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="7e310-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="7e310-194">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7e310-194">Click Save.</span></span>
69. <span data-ttu-id="7e310-195">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e310-195">Close the page.</span></span>
70. <span data-ttu-id="7e310-196">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="7e310-196">Click the Format tab.</span></span>
71. <span data-ttu-id="7e310-197">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Valor total'.</span><span class="sxs-lookup"><span data-stu-id="7e310-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="7e310-198">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="7e310-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="7e310-199">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="7e310-199">Click Edit formula.</span></span>
    * <span data-ttu-id="7e310-200">Crie saídas que serão o total do valor da fatura para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="7e310-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="7e310-201">No campo Fórmula, insira '"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="7e310-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="7e310-202">"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="7e310-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="7e310-203">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7e310-203">Click Save.</span></span>
76. <span data-ttu-id="7e310-204">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e310-204">Close the page.</span></span>
77. <span data-ttu-id="7e310-205">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7e310-205">Click Save.</span></span>
78. <span data-ttu-id="7e310-206">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7e310-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]