---
title: ER Configurar formato para fazer contagem e soma (Parte 2 - Configurar cálculos)
description: Este tópico descreve como configurar um formato de relatório eletrônico para contar e somar com base nos dados da saída de texto já gerada. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERDataSourceAddDropDialog, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6eb3d686e8f60de51001deffb4c2460c181a4ab
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565156"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-2---configure-computations"></a><span data-ttu-id="b83a9-104">ER Configurar formato para fazer contagem e soma (Parte 2 - Configurar cálculos)</span><span class="sxs-lookup"><span data-stu-id="b83a9-104">ER Configure format to do counting and summing (Part 2 - Configure computations)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b83a9-105">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="b83a9-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="b83a9-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="b83a9-107">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 1: criar formato)".</span><span class="sxs-lookup"><span data-stu-id="b83a9-107">To complete these steps, you must first complete the steps in the "ER Configure format to do counting and summing (Part 1: Create format)" procedure.</span></span>

<span data-ttu-id="b83a9-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="b83a9-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="b83a9-109">Criar uma configuração de formato para adicionar detalhes de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="b83a9-109">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="b83a9-110">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b83a9-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b83a9-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="b83a9-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="b83a9-112">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-112">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="b83a9-113">Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-113">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="b83a9-114">Suponha que você precise personalizar o formato fornecido pela Microsoft adicionando linhas com os detalhes do resumo no final do relatório intrastat.</span><span class="sxs-lookup"><span data-stu-id="b83a9-114">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="b83a9-115">Você precisa fazer isso derivando nossa própria instância da configuração do intrastat a partir da instância da Microsoft para fazer as modificações.</span><span class="sxs-lookup"><span data-stu-id="b83a9-115">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="b83a9-116">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-116">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="b83a9-117">No campo Novo, insira 'Derivar de Nome: Intrastat (DE), Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-117">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="b83a9-118">No campo Nome, digite "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="b83a9-118">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="b83a9-119">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="b83a9-119">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="b83a9-120">Configurar este relatório para fazer a contagem e soma baseadas nos detalhes de saída</span><span class="sxs-lookup"><span data-stu-id="b83a9-120">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="b83a9-121">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="b83a9-121">Click Designer.</span></span>
2. <span data-ttu-id="b83a9-122">Selecione Sim no campo Coletar detalhes de saída.</span><span class="sxs-lookup"><span data-stu-id="b83a9-122">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="b83a9-123">Este sinalizador será ativado no tempo de execução do processo de coleta dos detalhes de saída para gerar o arquivo do intrastat.</span><span class="sxs-lookup"><span data-stu-id="b83a9-123">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="b83a9-124">Você precisa fazer a contagem das diferentes direções do intrastat, portanto adicione uma enumeração do modelo dedicada à lista de fontes de dados desta configuração de formato.</span><span class="sxs-lookup"><span data-stu-id="b83a9-124">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources' list of this format configuration.</span></span>  
3. <span data-ttu-id="b83a9-125">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="b83a9-125">Click the Mapping tab.</span></span>
4. <span data-ttu-id="b83a9-126">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-126">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="b83a9-127">Na árvore, selecione 'Modelo de dados\Enumeração'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-127">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="b83a9-128">No campo Nome, digite 'Direção'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-128">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="b83a9-129">No campo Enumeração do modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b83a9-129">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="b83a9-130">Selecione o valor Direção.</span><span class="sxs-lookup"><span data-stu-id="b83a9-130">Select the value Direction.</span></span>  
8. <span data-ttu-id="b83a9-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b83a9-131">Click OK.</span></span>
9. <span data-ttu-id="b83a9-132">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-132">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="b83a9-133">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-133">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="b83a9-134">No campo Nome, digite '$BlockName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-134">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="b83a9-135">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b83a9-135">Click Edit formula.</span></span>
13. <span data-ttu-id="b83a9-136">No campo Fórmula, insira '"bloco"'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-136">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="b83a9-137">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-137">Click Save.</span></span>
15. <span data-ttu-id="b83a9-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-138">Close the page.</span></span>
16. <span data-ttu-id="b83a9-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b83a9-139">Click OK.</span></span>
17. <span data-ttu-id="b83a9-140">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-140">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="b83a9-141">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-141">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="b83a9-142">No campo Nome, digite '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-142">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="b83a9-143">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b83a9-143">Click Edit formula.</span></span>
21. <span data-ttu-id="b83a9-144">No campo Fórmula, insira '"registro"'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-144">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="b83a9-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-145">Click Save.</span></span>
23. <span data-ttu-id="b83a9-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-146">Close the page.</span></span>
24. <span data-ttu-id="b83a9-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b83a9-147">Click OK.</span></span>
25. <span data-ttu-id="b83a9-148">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="b83a9-148">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="b83a9-149">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-149">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="b83a9-150">No campo Nome, digite '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-150">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="b83a9-151">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b83a9-151">Click Edit formula.</span></span>
29. <span data-ttu-id="b83a9-152">No campo Fórmula, insira '"InvoicedAmountEUR"'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-152">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="b83a9-153">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-153">Click Save.</span></span>
31. <span data-ttu-id="b83a9-154">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-154">Close the page.</span></span>
32. <span data-ttu-id="b83a9-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b83a9-155">Click OK.</span></span>
33. <span data-ttu-id="b83a9-156">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-156">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="b83a9-157">Clique no botão Editar do campo "Nome da chave de dados coletada"</span><span class="sxs-lookup"><span data-stu-id="b83a9-157">Click Edit button for the 'Collected data key name' field</span></span>
35. <span data-ttu-id="b83a9-158">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b83a9-158">Click Add data source.</span></span>
    * <span data-ttu-id="b83a9-159">$BlockName</span><span class="sxs-lookup"><span data-stu-id="b83a9-159">$BlockName</span></span>  
36. <span data-ttu-id="b83a9-160">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-160">Click Save.</span></span>
37. <span data-ttu-id="b83a9-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-161">Close the page.</span></span>
38. <span data-ttu-id="b83a9-162">Clique no botão Editar do campo Valor da chave de dados coletada.</span><span class="sxs-lookup"><span data-stu-id="b83a9-162">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="b83a9-163">No campo Fórmula, insira 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-163">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="b83a9-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span><span class="sxs-lookup"><span data-stu-id="b83a9-164">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="b83a9-165">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-165">Click Save.</span></span>
41. <span data-ttu-id="b83a9-166">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-166">Close the page.</span></span>
    * <span data-ttu-id="b83a9-167">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="b83a9-167">Count the lines of this sequence.</span></span> <span data-ttu-id="b83a9-168">Os resultados serão usados com o nome "bloco" separadamente para as diferentes direções.</span><span class="sxs-lookup"><span data-stu-id="b83a9-168">The results will be used with the name "block" separately for different directions.</span></span> <span data-ttu-id="b83a9-169">O valor "Importar" será usado para todas as transações intrastat de entrada.</span><span class="sxs-lookup"><span data-stu-id="b83a9-169">Value "Import" will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="b83a9-170">O valor "Exportar" será usado para todas as transações intrastat de expedição.</span><span class="sxs-lookup"><span data-stu-id="b83a9-170">The value "Export" will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="b83a9-171">Considere isso como uma planilha de Excel virtual.</span><span class="sxs-lookup"><span data-stu-id="b83a9-171">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="b83a9-172">Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente.</span><span class="sxs-lookup"><span data-stu-id="b83a9-172">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span>  
42. <span data-ttu-id="b83a9-173">Na árvore, expanda 'Intrastat\Dados: Sequência'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-173">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="b83a9-174">Na árvore, selecione 'Intrastat\Dados: Sequência\Entradas?'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-174">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="b83a9-175">Clique no botão Editar do campo "Nome da chave de dados coletada".</span><span class="sxs-lookup"><span data-stu-id="b83a9-175">Click Edit button for the 'Collected data key name' field.</span></span>
    * <span data-ttu-id="b83a9-176">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="b83a9-176">Count the lines of this sequence.</span></span> <span data-ttu-id="b83a9-177">Os resultados serão memorizados usando o nome "registro".</span><span class="sxs-lookup"><span data-stu-id="b83a9-177">The results will be memorized using the name "record".</span></span>  
45. <span data-ttu-id="b83a9-178">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-178">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="b83a9-179">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b83a9-179">Click Add data source.</span></span>
47. <span data-ttu-id="b83a9-180">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-180">Click Save.</span></span>
48. <span data-ttu-id="b83a9-181">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-181">Close the page.</span></span>
49. <span data-ttu-id="b83a9-182">Clique no botão Editar do campo "Valor da chave de dados coletada"</span><span class="sxs-lookup"><span data-stu-id="b83a9-182">Click Edit button for the 'Collected data key value' field</span></span>
50. <span data-ttu-id="b83a9-183">No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-183">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="b83a9-184">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-184">Click Save.</span></span>
52. <span data-ttu-id="b83a9-185">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-185">Close the page.</span></span>
    * <span data-ttu-id="b83a9-186">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="b83a9-186">Count the lines of this sequence.</span></span> <span data-ttu-id="b83a9-187">Os resultados serão usados com o nome "registro" separadamente para os diferentes códigos de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="b83a9-187">The results will be used with the name "record" separately for different commodity codes.</span></span> <span data-ttu-id="b83a9-188">Considere isso como uma planilha de Excel virtual.</span><span class="sxs-lookup"><span data-stu-id="b83a9-188">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="b83a9-189">Para cada transação, uma linha na primeira coluna "bloco" será preenchida com valores "Importar" e "Exportar" consequentemente e o segundo bloco "registro" será preenchido com o valor do código de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="b83a9-189">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly and the second block "record" is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="b83a9-190">Na árvore, selecione 'Intrastat\Dados: Sequência\Expedições?'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-190">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="b83a9-191">Clique no botão Editar do campo "Nome da chave de dados coletada"</span><span class="sxs-lookup"><span data-stu-id="b83a9-191">Click Edit button for the 'Collected data key name' field</span></span>
55. <span data-ttu-id="b83a9-192">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-192">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="b83a9-193">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b83a9-193">Click Add data source.</span></span>
57. <span data-ttu-id="b83a9-194">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-194">Click Save.</span></span>
58. <span data-ttu-id="b83a9-195">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-195">Close the page.</span></span>
59. <span data-ttu-id="b83a9-196">Clique no botão Editar do campo "Valor da chave de dados coletada".</span><span class="sxs-lookup"><span data-stu-id="b83a9-196">Click the Edit button for the 'Collected data key value' field.</span></span>
60. <span data-ttu-id="b83a9-197">No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-197">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="b83a9-198">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-198">Click Save.</span></span>
62. <span data-ttu-id="b83a9-199">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-199">Close the page.</span></span>
63. <span data-ttu-id="b83a9-200">Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="b83a9-201">Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?\Registro =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-201">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="b83a9-202">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="b83a9-202">Click the Format tab.</span></span>
66. <span data-ttu-id="b83a9-203">Na árvore, selecione 'Intrastat\Dados\Expedições\Registro\Valor da fatura em EUR'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-203">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="b83a9-204">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="b83a9-204">Click the Mapping tab.</span></span>
68. <span data-ttu-id="b83a9-205">Clique no botão Editar do campo "Nome da chave de dados coletada",</span><span class="sxs-lookup"><span data-stu-id="b83a9-205">Click the Edit button for the 'Collected data key name' field.</span></span>
69. <span data-ttu-id="b83a9-206">Na árvore, selecione '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-206">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="b83a9-207">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b83a9-207">Click Add data source.</span></span>
71. <span data-ttu-id="b83a9-208">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-208">Click Save.</span></span>
72. <span data-ttu-id="b83a9-209">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-209">Close the page.</span></span>
    * <span data-ttu-id="b83a9-210">Resuma os valores do valor faturado das linhas desta sequência.</span><span class="sxs-lookup"><span data-stu-id="b83a9-210">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="b83a9-211">Os resultados serão usados com o nome "InvoicedAmountEUR" separadamente para as diferentes direções intrastat e os códigos de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="b83a9-211">The results will be used with the name "InvoicedAmountEUR" separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="b83a9-212">Considere isso como uma criação virtual em planilha de Excel.</span><span class="sxs-lookup"><span data-stu-id="b83a9-212">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="b83a9-213">Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente.</span><span class="sxs-lookup"><span data-stu-id="b83a9-213">For each transaction a row where the first column "block" is filled with the values "Import" and "Export" accordingly.</span></span> <span data-ttu-id="b83a9-214">O segundo bloco "registro" será preenchido com o valor do código de mercadoria e a terceira coluna "InvoicedAmountEUR" será preenchida com o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="b83a9-214">The second block "record" is filled with the commodity code value, and the third column "InvoicedAmountEUR" is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="b83a9-215">Na árvore, expanda 'Intrastat\Dados\Entradas?'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-215">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="b83a9-216">Na árvore, expanda 'Intrastat\Dados\Entradas?\Registro =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-216">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="b83a9-217">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="b83a9-217">Click the Format tab.</span></span>
76. <span data-ttu-id="b83a9-218">Na árvore, selecione 'Intrastat\Dados\Entradas\Registro\Valor da fatura em EUR'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-218">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="b83a9-219">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="b83a9-219">Click the Mapping tab.</span></span>
78. <span data-ttu-id="b83a9-220">Clique no botão Editar do campo "Nome da chave de dados coletada",</span><span class="sxs-lookup"><span data-stu-id="b83a9-220">Click the Edit button for the 'Collected data key name' field.</span></span>
79. <span data-ttu-id="b83a9-221">Na árvore, selecione '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="b83a9-221">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="b83a9-222">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b83a9-222">Click Add data source.</span></span>
81. <span data-ttu-id="b83a9-223">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-223">Click Save.</span></span>
82. <span data-ttu-id="b83a9-224">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-224">Close the page.</span></span>
83. <span data-ttu-id="b83a9-225">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b83a9-225">Click Save.</span></span>
84. <span data-ttu-id="b83a9-226">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b83a9-226">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]