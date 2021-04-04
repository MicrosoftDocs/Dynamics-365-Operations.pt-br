---
title: ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 3)
author: NickSelin
manager: AnnBe
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
ms.openlocfilehash: af95399118b9059b9bead3a1b84203cf3b6e74c2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567107"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-3---use-computations-to-make-the-output"></a><span data-ttu-id="1622d-104">ER Configurar o formato para fazer contagem e soma (Parte 3 - Usar cálculos para criar a saída)</span><span class="sxs-lookup"><span data-stu-id="1622d-104">ER Configure format to do counting and summing (Part 3 - Use computations to make the output)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1622d-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="1622d-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="1622d-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="1622d-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="1622d-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 2: configurar cálculos)".</span><span class="sxs-lookup"><span data-stu-id="1622d-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 2: Configure computations)" procedure.</span></span>

<span data-ttu-id="1622d-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="1622d-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="1622d-109">Configurar este relatório para usar as informações de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="1622d-109">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="1622d-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="1622d-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="1622d-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="1622d-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1622d-112">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="1622d-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="1622d-113">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="1622d-113">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="1622d-114">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="1622d-114">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="1622d-115">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="1622d-115">Click Designer.</span></span>
7. <span data-ttu-id="1622d-116">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1622d-116">Click the Mapping tab.</span></span>
8. <span data-ttu-id="1622d-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1622d-117">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="1622d-118">Adicione uma nova fonte de dados para obter a lista de blocos memorizados.</span><span class="sxs-lookup"><span data-stu-id="1622d-118">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="1622d-119">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="1622d-119">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="1622d-120">No campo Nome, digite '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="1622d-120">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="1622d-121">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="1622d-121">$BlocksList</span></span>  
11. <span data-ttu-id="1622d-122">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="1622d-122">Click Edit formula.</span></span>
12. <span data-ttu-id="1622d-123">Na árvore, selecione 'Funções de coleta de dados\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="1622d-123">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="1622d-124">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="1622d-124">Click Add function.</span></span>
14. <span data-ttu-id="1622d-125">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1622d-125">Click Add data source.</span></span>
15. <span data-ttu-id="1622d-126">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="1622d-126">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="1622d-127">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="1622d-127">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="1622d-128">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="1622d-128">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="1622d-129">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="1622d-129">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="1622d-130">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1622d-130">Click Save.</span></span>
    * <span data-ttu-id="1622d-131">O padrão "\*" significa que todos os blocos serão incluídos na lista para este registro.</span><span class="sxs-lookup"><span data-stu-id="1622d-131">The pattern "\*" means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="1622d-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1622d-132">Close the page.</span></span>
19. <span data-ttu-id="1622d-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1622d-133">Click OK.</span></span>
20. <span data-ttu-id="1622d-134">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="1622d-134">Click the Format tab.</span></span>
21. <span data-ttu-id="1622d-135">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="1622d-135">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="1622d-136">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1622d-136">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="1622d-137">Na árvore, selecione 'Texto\Sequência'.</span><span class="sxs-lookup"><span data-stu-id="1622d-137">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="1622d-138">No campo Nome, digite 'Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="1622d-138">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="1622d-139">Totais por blocos</span><span class="sxs-lookup"><span data-stu-id="1622d-139">Totals by blocks</span></span>  
25. <span data-ttu-id="1622d-140">No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="1622d-140">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="1622d-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1622d-141">Click OK.</span></span>
27. <span data-ttu-id="1622d-142">Na árvore, selecione 'Intrastat\Dados\Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="1622d-142">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="1622d-143">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1622d-143">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="1622d-144">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="1622d-144">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="1622d-145">No campo Nome, digite 'Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="1622d-145">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="1622d-146">Código do bloco</span><span class="sxs-lookup"><span data-stu-id="1622d-146">Block code</span></span>  
31. <span data-ttu-id="1622d-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1622d-147">Click OK.</span></span>
32. <span data-ttu-id="1622d-148">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1622d-148">Click Add String.</span></span>
33. <span data-ttu-id="1622d-149">No campo Nome, digite 'Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="1622d-149">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="1622d-150">Contagem de linhas</span><span class="sxs-lookup"><span data-stu-id="1622d-150">Lines counting</span></span>  
34. <span data-ttu-id="1622d-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1622d-151">Click OK.</span></span>
35. <span data-ttu-id="1622d-152">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="1622d-152">Click Add String.</span></span>
36. <span data-ttu-id="1622d-153">No campo Nome, digite 'Valor total'.</span><span class="sxs-lookup"><span data-stu-id="1622d-153">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="1622d-154">Valor total</span><span class="sxs-lookup"><span data-stu-id="1622d-154">Total amount</span></span>  
37. <span data-ttu-id="1622d-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1622d-155">Click OK.</span></span>
38. <span data-ttu-id="1622d-156">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1622d-156">Click the Mapping tab.</span></span>
39. <span data-ttu-id="1622d-157">Na árvore, selecione '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="1622d-157">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="1622d-158">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="1622d-158">Click Bind.</span></span>
    * <span data-ttu-id="1622d-159">Crie uma linha de resumo para cada bloco memorizado.</span><span class="sxs-lookup"><span data-stu-id="1622d-159">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="1622d-160">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="1622d-160">Click the Format tab.</span></span>
42. <span data-ttu-id="1622d-161">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="1622d-161">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="1622d-162">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1622d-162">Click the Mapping tab.</span></span>
44. <span data-ttu-id="1622d-163">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="1622d-163">Click Edit formula.</span></span>
45. <span data-ttu-id="1622d-164">No campo Fórmula, insira '"Id do bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="1622d-164">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="1622d-165">"Id do bloco: " &</span><span class="sxs-lookup"><span data-stu-id="1622d-165">"Block id: " &</span></span>  
46. <span data-ttu-id="1622d-166">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="1622d-166">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="1622d-167">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="1622d-167">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="1622d-168">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1622d-168">Click Add data source.</span></span>
49. <span data-ttu-id="1622d-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1622d-169">Click Save.</span></span>
50. <span data-ttu-id="1622d-170">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1622d-170">Close the page.</span></span>
51. <span data-ttu-id="1622d-171">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="1622d-171">Click the Format tab.</span></span>
52. <span data-ttu-id="1622d-172">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="1622d-172">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="1622d-173">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1622d-173">Click the Mapping tab.</span></span>
54. <span data-ttu-id="1622d-174">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="1622d-174">Click Edit formula.</span></span>
    * <span data-ttu-id="1622d-175">Crie saídas para o número de linhas para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="1622d-175">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="1622d-176">No campo Fórmula, insira '"Número de linhas neste bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="1622d-176">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="1622d-177">"Número de linhas neste bloco: " &</span><span class="sxs-lookup"><span data-stu-id="1622d-177">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="1622d-178">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="1622d-178">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="1622d-179">"Número de linhas neste bloco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="1622d-179">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="1622d-180">Na árvore, selecione 'Funções de coleta de dados\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="1622d-180">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="1622d-181">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="1622d-181">Click Add function.</span></span>
59. <span data-ttu-id="1622d-182">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1622d-182">Click Add data source.</span></span>
60. <span data-ttu-id="1622d-183">No campo de fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="1622d-183">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="1622d-184">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="1622d-184">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="1622d-185">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="1622d-185">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="1622d-186">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="1622d-186">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="1622d-187">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1622d-187">Click Add data source.</span></span>
64. <span data-ttu-id="1622d-188">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="1622d-188">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="1622d-189">"Número de linhas neste bloco: " & TEXT(COUNTIFS ('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="1622d-189">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="1622d-190">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="1622d-190">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="1622d-191">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1622d-191">Click Add data source.</span></span>
67. <span data-ttu-id="1622d-192">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="1622d-192">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="1622d-193">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="1622d-193">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="1622d-194">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1622d-194">Click Save.</span></span>
69. <span data-ttu-id="1622d-195">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1622d-195">Close the page.</span></span>
70. <span data-ttu-id="1622d-196">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="1622d-196">Click the Format tab.</span></span>
71. <span data-ttu-id="1622d-197">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Valor total'.</span><span class="sxs-lookup"><span data-stu-id="1622d-197">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="1622d-198">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1622d-198">Click the Mapping tab.</span></span>
73. <span data-ttu-id="1622d-199">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="1622d-199">Click Edit formula.</span></span>
    * <span data-ttu-id="1622d-200">Crie saídas que serão o total do valor da fatura para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="1622d-200">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="1622d-201">No campo Fórmula, insira '"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="1622d-201">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="1622d-202">"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="1622d-202">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="1622d-203">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1622d-203">Click Save.</span></span>
76. <span data-ttu-id="1622d-204">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1622d-204">Close the page.</span></span>
77. <span data-ttu-id="1622d-205">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1622d-205">Click Save.</span></span>
78. <span data-ttu-id="1622d-206">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1622d-206">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]