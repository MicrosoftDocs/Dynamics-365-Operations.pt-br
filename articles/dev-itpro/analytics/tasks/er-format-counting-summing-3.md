--- 
title: "Usar cálculos para criar a saída para a contagem e soma"
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 34cd443b09f784ef3db7599b6b1ed030428bf692
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="use-computations-to-make-the-output-for-counting-and-summing"></a><span data-ttu-id="c6bd1-103">Usar cálculos para criar a saída para a contagem e soma</span><span class="sxs-lookup"><span data-stu-id="c6bd1-103">Use computations to make the output for counting and summing</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c6bd1-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="c6bd1-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c6bd1-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 2: configurar cálculos)".</span><span class="sxs-lookup"><span data-stu-id="c6bd1-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 2: Configure computations)” procedure.</span></span>

<span data-ttu-id="c6bd1-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="configure-this-report-to-use-counting-and-summing-info"></a><span data-ttu-id="c6bd1-108">Configurar este relatório para usar as informações de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="c6bd1-108">Configure this report to use counting and summing info</span></span>
1. <span data-ttu-id="c6bd1-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="c6bd1-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="c6bd1-111">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="c6bd1-112">Na árvore, expanda 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-112">In the tree, expand 'Intrastat model\Intrastat (DE)'.</span></span>
5. <span data-ttu-id="c6bd1-113">Na árvore, selecione "Modelo intrastat\Intrastat (DE)\Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="c6bd1-113">In the tree, select 'Intrastat model\Intrastat (DE)\Intrastat (DE) with counting & summing'.</span></span>
6. <span data-ttu-id="c6bd1-114">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-114">Click Designer.</span></span>
7. <span data-ttu-id="c6bd1-115">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-115">Click the Mapping tab.</span></span>
8. <span data-ttu-id="c6bd1-116">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-116">Click Add root to open the drop dialog.</span></span>
    * <span data-ttu-id="c6bd1-117">Adicione uma nova fonte de dados para obter a lista de blocos memorizados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-117">Add a new data source to get the list of memorized blocks.</span></span>  
9. <span data-ttu-id="c6bd1-118">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-118">In the tree, select 'Functions\Calculated field'.</span></span>
10. <span data-ttu-id="c6bd1-119">No campo Nome, digite '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-119">In the Name field, type '$BlocksList'.</span></span>
    * <span data-ttu-id="c6bd1-120">$BlocksList</span><span class="sxs-lookup"><span data-stu-id="c6bd1-120">$BlocksList</span></span>  
11. <span data-ttu-id="c6bd1-121">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-121">Click Edit formula.</span></span>
12. <span data-ttu-id="c6bd1-122">Na árvore, selecione 'Funções de coleta de dados\COLLECTEDLIST'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-122">In the tree, select 'Data collection functions\COLLECTEDLIST'.</span></span>
13. <span data-ttu-id="c6bd1-123">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-123">Click Add function.</span></span>
14. <span data-ttu-id="c6bd1-124">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-124">Click Add data source.</span></span>
15. <span data-ttu-id="c6bd1-125">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-125">In the Formula field, enter 'COLLECTEDLIST('$BlockName', '.</span></span>
    * <span data-ttu-id="c6bd1-126">COLLECTEDLIST('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="c6bd1-126">COLLECTEDLIST('$BlockName',</span></span>  
16. <span data-ttu-id="c6bd1-127">No campo Fórmula, insira 'COLLECTEDLIST('$BlockName', "\*")'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-127">In the Formula field, enter 'COLLECTEDLIST('$BlockName', "\*")'.</span></span>
    * <span data-ttu-id="c6bd1-128">COLLECTEDLIST('$BlockName', "\*")</span><span class="sxs-lookup"><span data-stu-id="c6bd1-128">COLLECTEDLIST('$BlockName', "\*")</span></span>  
17. <span data-ttu-id="c6bd1-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-129">Click Save.</span></span>
    * <span data-ttu-id="c6bd1-130">O padrão"\*" significa que todos os blocos serão incluídos na lista para este registro.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-130">The pattern “\*” means that all blocks will be included to the list for this record.</span></span>  
18. <span data-ttu-id="c6bd1-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-131">Close the page.</span></span>
19. <span data-ttu-id="c6bd1-132">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-132">Click OK.</span></span>
20. <span data-ttu-id="c6bd1-133">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-133">Click the Format tab.</span></span>
21. <span data-ttu-id="c6bd1-134">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-134">In the tree, select 'Intrastat\Data'.</span></span>
22. <span data-ttu-id="c6bd1-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-135">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="c6bd1-136">Na árvore, selecione 'Texto\Sequência'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-136">In the tree, select 'Text\Sequence'.</span></span>
24. <span data-ttu-id="c6bd1-137">No campo Nome, digite 'Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-137">In the Name field, type 'Totals by blocks'.</span></span>
    * <span data-ttu-id="c6bd1-138">Totais por blocos</span><span class="sxs-lookup"><span data-stu-id="c6bd1-138">Totals by blocks</span></span>  
25. <span data-ttu-id="c6bd1-139">No campo Caracteres especiais, selecione 'Nova linha - Windows (CR LF)'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-139">In the Special characters field, select 'New line - Windows (CR LF)'.</span></span>
26. <span data-ttu-id="c6bd1-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-140">Click OK.</span></span>
27. <span data-ttu-id="c6bd1-141">Na árvore, selecione 'Intrastat\Dados\Totais por blocos'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-141">In the tree, select 'Intrastat\Data\Totals by blocks'.</span></span>
28. <span data-ttu-id="c6bd1-142">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-142">Click Add to open the drop dialog.</span></span>
29. <span data-ttu-id="c6bd1-143">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-143">In the tree, select 'Text\String'.</span></span>
30. <span data-ttu-id="c6bd1-144">No campo Nome, digite 'Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-144">In the Name field, type 'Block code'.</span></span>
    * <span data-ttu-id="c6bd1-145">Código do bloco</span><span class="sxs-lookup"><span data-stu-id="c6bd1-145">Block code</span></span>  
31. <span data-ttu-id="c6bd1-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-146">Click OK.</span></span>
32. <span data-ttu-id="c6bd1-147">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c6bd1-147">Click Add String.</span></span>
33. <span data-ttu-id="c6bd1-148">No campo Nome, digite 'Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-148">In the Name field, type 'Lines counting'.</span></span>
    * <span data-ttu-id="c6bd1-149">Contagem de linhas</span><span class="sxs-lookup"><span data-stu-id="c6bd1-149">Lines counting</span></span>  
34. <span data-ttu-id="c6bd1-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-150">Click OK.</span></span>
35. <span data-ttu-id="c6bd1-151">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c6bd1-151">Click Add String.</span></span>
36. <span data-ttu-id="c6bd1-152">No campo Nome, digite 'Valor total'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-152">In the Name field, type 'Total amount'.</span></span>
    * <span data-ttu-id="c6bd1-153">Valor total</span><span class="sxs-lookup"><span data-stu-id="c6bd1-153">Total amount</span></span>  
37. <span data-ttu-id="c6bd1-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-154">Click OK.</span></span>
38. <span data-ttu-id="c6bd1-155">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-155">Click the Mapping tab.</span></span>
39. <span data-ttu-id="c6bd1-156">Na árvore, selecione '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-156">In the tree, select '$BlocksList'.</span></span>
40. <span data-ttu-id="c6bd1-157">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-157">Click Bind.</span></span>
    * <span data-ttu-id="c6bd1-158">Crie uma linha de resumo para cada bloco memorizado.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-158">Create a summary line for each memorized block.</span></span>  
41. <span data-ttu-id="c6bd1-159">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-159">Click the Format tab.</span></span>
42. <span data-ttu-id="c6bd1-160">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Código do bloco'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-160">In the tree, select 'Intrastat\Data\Totals by blocks\Block code'.</span></span>
43. <span data-ttu-id="c6bd1-161">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-161">Click the Mapping tab.</span></span>
44. <span data-ttu-id="c6bd1-162">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-162">Click Edit formula.</span></span>
45. <span data-ttu-id="c6bd1-163">No campo Fórmula, insira '"Id do bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-163">In the Formula field, enter '"Block id: " & '.</span></span>
    * <span data-ttu-id="c6bd1-164">"Id do bloco: " &</span><span class="sxs-lookup"><span data-stu-id="c6bd1-164">"Block id: " &</span></span>  
46. <span data-ttu-id="c6bd1-165">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-165">In the tree, expand '$BlocksList'.</span></span>
47. <span data-ttu-id="c6bd1-166">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-166">In the tree, select '$BlocksList\Value'.</span></span>
48. <span data-ttu-id="c6bd1-167">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-167">Click Add data source.</span></span>
49. <span data-ttu-id="c6bd1-168">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-168">Click Save.</span></span>
50. <span data-ttu-id="c6bd1-169">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-169">Close the page.</span></span>
51. <span data-ttu-id="c6bd1-170">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-170">Click the Format tab.</span></span>
52. <span data-ttu-id="c6bd1-171">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Contagem de linhas'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-171">In the tree, select 'Intrastat\Data\Totals by blocks\Lines counting'.</span></span>
53. <span data-ttu-id="c6bd1-172">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-172">Click the Mapping tab.</span></span>
54. <span data-ttu-id="c6bd1-173">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-173">Click Edit formula.</span></span>
    * <span data-ttu-id="c6bd1-174">Crie saídas para o número de linhas para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-174">Create output for the number of lines for each block presented in this report.</span></span>  
55. <span data-ttu-id="c6bd1-175">No campo Fórmula, insira '"Número de linhas neste bloco: " & '.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-175">In the Formula field, enter '"Number of lines in this block: " & '.</span></span>
    * <span data-ttu-id="c6bd1-176">"Número de linhas neste bloco: " &</span><span class="sxs-lookup"><span data-stu-id="c6bd1-176">"Number of lines in this block: " &</span></span>  
56. <span data-ttu-id="c6bd1-177">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT('.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-177">In the Formula field, enter '"Number of lines in this block: " & TEXT('.</span></span>
    * <span data-ttu-id="c6bd1-178">"Número de linhas neste bloco: " & TEXT(</span><span class="sxs-lookup"><span data-stu-id="c6bd1-178">"Number of lines in this block: " & TEXT(</span></span>  
57. <span data-ttu-id="c6bd1-179">Na árvore, selecione 'Funções de coleta de dados\COUNTIFS'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-179">In the tree, select 'Data collection functions\COUNTIFS'.</span></span>
58. <span data-ttu-id="c6bd1-180">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-180">Click Add function.</span></span>
59. <span data-ttu-id="c6bd1-181">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-181">Click Add data source.</span></span>
60. <span data-ttu-id="c6bd1-182">No campo de fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-182">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '.</span></span>
    * <span data-ttu-id="c6bd1-183">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName',</span><span class="sxs-lookup"><span data-stu-id="c6bd1-183">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName',</span></span>  
61. <span data-ttu-id="c6bd1-184">Na árvore, expanda '$BlocksList'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-184">In the tree, expand '$BlocksList'.</span></span>
62. <span data-ttu-id="c6bd1-185">Na árvore, selecione '$BlocksList\Valor'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-185">In the tree, select '$BlocksList\Value'.</span></span>
63. <span data-ttu-id="c6bd1-186">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-186">Click Add data source.</span></span>
64. <span data-ttu-id="c6bd1-187">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-187">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '.</span></span>
    * <span data-ttu-id="c6bd1-188">"Número de linhas neste bloco: " & TEXT(COUNTIFS ('$BlockName', '$BlocksList'.Value,</span><span class="sxs-lookup"><span data-stu-id="c6bd1-188">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value,</span></span>  
65. <span data-ttu-id="c6bd1-189">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-189">In the tree, select '$RecName'.</span></span>
66. <span data-ttu-id="c6bd1-190">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-190">Click Add data source.</span></span>
67. <span data-ttu-id="c6bd1-191">No campo Fórmula, insira '"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-191">In the Formula field, enter '"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="c6bd1-192">"Número de linhas neste bloco: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="c6bd1-192">"Number of lines in this block: " & TEXT(COUNTIFS('$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
68. <span data-ttu-id="c6bd1-193">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-193">Click Save.</span></span>
69. <span data-ttu-id="c6bd1-194">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-194">Close the page.</span></span>
70. <span data-ttu-id="c6bd1-195">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-195">Click the Format tab.</span></span>
71. <span data-ttu-id="c6bd1-196">Na árvore, selecione 'Intrastat\Dados\Totais por blocos\Valor total'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-196">In the tree, select 'Intrastat\Data\Totals by blocks\Total amount'.</span></span>
72. <span data-ttu-id="c6bd1-197">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-197">Click the Mapping tab.</span></span>
73. <span data-ttu-id="c6bd1-198">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-198">Click Edit formula.</span></span>
    * <span data-ttu-id="c6bd1-199">Crie saídas que serão o total do valor da fatura para cada bloco apresentado neste relatório.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-199">Create output that will be the total of the invoiced amount for each block presented in this report.</span></span>  
74. <span data-ttu-id="c6bd1-200">No campo Fórmula, insira '"Soma do valor faturado: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-200">In the Formula field, enter '"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))'.</span></span>
    * <span data-ttu-id="c6bd1-201">"Soma do valor faturado: " & TEXT(SUMIFS (SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span><span class="sxs-lookup"><span data-stu-id="c6bd1-201">"Sum of invoiced amount: " & TEXT(SUMIFS('$InvName', '$BlockName', '$BlocksList'.Value, '$RecName', "\*"))</span></span>  
75. <span data-ttu-id="c6bd1-202">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-202">Click Save.</span></span>
76. <span data-ttu-id="c6bd1-203">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-203">Close the page.</span></span>
77. <span data-ttu-id="c6bd1-204">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-204">Click Save.</span></span>
78. <span data-ttu-id="c6bd1-205">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6bd1-205">Close the page.</span></span>


