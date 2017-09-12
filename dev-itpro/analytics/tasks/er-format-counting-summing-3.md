--- 
title: "Usar cálculos para criar a saída para contagem e soma para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 121f00efea6aee8d9df45d67f8f252bbf6b97176
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="c424a-103">Usar cálculos para criar a saída para contagem e soma para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="c424a-103">Use computations to make the output for counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c424a-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="c424a-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="c424a-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="c424a-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c424a-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 2: configurar cálculos)".</span><span class="sxs-lookup"><span data-stu-id="c424a-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="c424a-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c424a-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="c424a-108">Configurar este relatório para usar as informações de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="c424a-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="c424a-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c424a-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c424a-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c424a-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c424a-111">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="c424a-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="c424a-112">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="c424a-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="c424a-113">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="c424a-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="c424a-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="c424a-114">Click Designer.</span></span>
7. <span data-ttu-id="c424a-115">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c424a-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="c424a-116">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c424a-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="c424a-117">Adicione uma nova fonte de dados para obter a lista de blocos memorizados.</span><span class="sxs-lookup"><span data-stu-id="c424a-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="c424a-118">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="c424a-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="c424a-119">No campo Nome, digite '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c424a-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="c424a-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="c424a-120">$BlocksList</span></span>  
11. <span data-ttu-id="c424a-121">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c424a-121">Click Edit formula.</span></span>
12. <span data-ttu-id="c424a-122">Na árvore, selecione 'Funções de coleta de dados\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="c424a-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="c424a-123">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="c424a-123">Click Add function.</span></span>
14. <span data-ttu-id="c424a-124">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c424a-124">Click Add data source.</span></span>
15. <span data-ttu-id="c424a-125">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="c424a-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="c424a-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="c424a-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="c424a-127">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', "*")'.</span><span class="sxs-lookup"><span data-stu-id="c424a-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "*")'.</span></span>
    * <span data-ttu-id="c424a-128">COLLECTEDLIST('$BlockName', "*")</span><span class="sxs-lookup"><span data-stu-id="c424a-128">COLLECTEDLIST('$BlockName', "*")</span></span>  
17. <span data-ttu-id="c424a-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c424a-129">Click Save.</span></span>
    * <span data-ttu-id="c424a-130">O padrão"*" significa que todos os blocos serão incluídos na lista para este registro.</span><span class="sxs-lookup"><span data-stu-id="c424a-130">The pattern “*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="c424a-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c424a-131">Close the page.</span></span>
19. <span data-ttu-id="c424a-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c424a-132">Click OK.</span></span>
20. <span data-ttu-id="c424a-133">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c424a-133">Click the Format tab.</span></span>
21. <span data-ttu-id="c424a-134">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="c424a-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="c424a-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c424a-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="c424a-136">Na árvore, selecione 'Texto\Sequência'.</span><span class="sxs-lookup"><span data-stu-id="c424a-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="c424a-137">No campo Nome, digite 'Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="c424a-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="c424a-138">Totais por blocos</span><span class="sxs-lookup"><span data-stu-id="c424a-138">Totals by blocks</span></span>  
25. <span data-ttu-id="c424a-139">No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="c424a-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="c424a-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c424a-140">Click OK.</span></span>
27. <span data-ttu-id="c424a-141">Na árvore, selecione 'Intrastat\Dados\Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="c424a-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="c424a-142">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c424a-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="c424a-143">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="c424a-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="c424a-144">No campo Nome, digite 'Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="c424a-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="c424a-145">Código do bloco</span><span class="sxs-lookup"><span data-stu-id="c424a-145">Block code</span></span>  
31. <span data-ttu-id="c424a-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c424a-146">Click OK.</span></span>
32. <span data-ttu-id="c424a-147">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c424a-147">Click Add String.</span></span>
33. <span data-ttu-id="c424a-148">No campo Nome, digite 'Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="c424a-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="c424a-149">Contagem de linhas</span><span class="sxs-lookup"><span data-stu-id="c424a-149">Lines counting</span></span>  
34. <span data-ttu-id="c424a-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c424a-150">Click OK.</span></span>
35. <span data-ttu-id="c424a-151">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c424a-151">Click Add String.</span></span>
36. <span data-ttu-id="c424a-152">No campo Nome, digite 'Valor total'.</span><span class="sxs-lookup"><span data-stu-id="c424a-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="c424a-153">Valor total</span><span class="sxs-lookup"><span data-stu-id="c424a-153">Total amount</span></span>  
37. <span data-ttu-id="c424a-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c424a-154">Click OK.</span></span>
38. <span data-ttu-id="c424a-155">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c424a-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="c424a-156">Na árvore, selecione '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c424a-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="c424a-157">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c424a-157">Click Bind.</span></span>
    * <span data-ttu-id="c424a-158">Crie uma linha de resumo para cada bloco memorizado.</span><span class="sxs-lookup"><span data-stu-id="c424a-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="c424a-159">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c424a-159">Click the Format tab.</span></span>
42. <span data-ttu-id="c424a-160">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="c424a-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="c424a-161">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c424a-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="c424a-162">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c424a-162">Click Edit formula.</span></span>
45. <span data-ttu-id="c424a-163">No campo Fórmula, insira '"Id do bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="c424a-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="c424a-164">"Id do bloco: " &</span><span class="sxs-lookup"><span data-stu-id="c424a-164">"Block id: " &</span></span>  
46. <span data-ttu-id="c424a-165">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c424a-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="c424a-166">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="c424a-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="c424a-167">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c424a-167">Click Add data source.</span></span>
49. <span data-ttu-id="c424a-168">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c424a-168">Click Save.</span></span>
50. <span data-ttu-id="c424a-169">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c424a-169">Close the page.</span></span>
51. <span data-ttu-id="c424a-170">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c424a-170">Click the Format tab.</span></span>
52. <span data-ttu-id="c424a-171">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="c424a-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="c424a-172">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c424a-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="c424a-173">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c424a-173">Click Edit formula.</span></span>
    * <span data-ttu-id="c424a-174">Crie saídas para o número de linhas para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="c424a-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="c424a-175">No campo Fórmula, insira '"Número de linhas neste bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="c424a-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="c424a-176">"Número de linhas neste bloco: " &</span><span class="sxs-lookup"><span data-stu-id="c424a-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="c424a-177">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="c424a-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="c424a-178">"Número de linhas neste bloco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="c424a-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="c424a-179">Na árvore, selecione 'Funções de coleta de dados\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="c424a-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="c424a-180">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="c424a-180">Click Add function.</span></span>
59. <span data-ttu-id="c424a-181">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c424a-181">Click Add data source.</span></span>
60. <span data-ttu-id="c424a-182">No campo de fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="c424a-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="c424a-183">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="c424a-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="c424a-184">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c424a-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="c424a-185">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="c424a-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="c424a-186">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c424a-186">Click Add data source.</span></span>
64. <span data-ttu-id="c424a-187">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="c424a-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="c424a-188">"Número de linhas neste bloco: " & TEXT(COUNTIFS ('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="c424a-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="c424a-189">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="c424a-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="c424a-190">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c424a-190">Click Add data source.</span></span>
67. <span data-ttu-id="c424a-191">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span><span class="sxs-lookup"><span data-stu-id="c424a-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="c424a-192">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="c424a-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
68. <span data-ttu-id="c424a-193">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c424a-193">Click Save.</span></span>
69. <span data-ttu-id="c424a-194">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c424a-194">Close the page.</span></span>
70. <span data-ttu-id="c424a-195">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c424a-195">Click the Format tab.</span></span>
71. <span data-ttu-id="c424a-196">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Valor total'.</span><span class="sxs-lookup"><span data-stu-id="c424a-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="c424a-197">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c424a-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="c424a-198">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c424a-198">Click Edit formula.</span></span>
    * <span data-ttu-id="c424a-199">Crie saídas que serão o total do valor da fatura para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="c424a-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="c424a-200">No campo Fórmula, insira '"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span><span class="sxs-lookup"><span data-stu-id="c424a-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))'.</span></span>
    * <span data-ttu-id="c424a-201">"Soma do valor faturado: " & TEXT(SUMIFS (SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span><span class="sxs-lookup"><span data-stu-id="c424a-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "*"))</span></span>  
75. <span data-ttu-id="c424a-202">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c424a-202">Click Save.</span></span>
76. <span data-ttu-id="c424a-203">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c424a-203">Close the page.</span></span>
77. <span data-ttu-id="c424a-204">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c424a-204">Click Save.</span></span>
78. <span data-ttu-id="c424a-205">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c424a-205">Close the page.</span></span>


