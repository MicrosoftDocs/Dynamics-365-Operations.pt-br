--- 
title: "Configurar cálculos para contagem e soma para relatório eletrônico (ER)"
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
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7b9035d8e7baf3c7ecb063b104b9a567be60840
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="configure-computations-to-do-counting-and-summing-for-electronic-reporting-er"></a><span data-ttu-id="d2662-103">Configurar cálculos para contagem e soma para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="d2662-103">Configure computations to do counting and summing for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2662-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou de desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para fazer a contagem e soma com base nos dados já gerados do texto de saída.</span><span class="sxs-lookup"><span data-stu-id="d2662-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to do counting and summing based on data of the already generated text output.</span></span> <span data-ttu-id="d2662-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="d2662-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="d2662-106">Para concluir estas etapas, primeiramente você deve concluir as etapas no procedimento "ER Configurar o formato para fazer a contagem e soma (Parte 1: criar formato)".</span><span class="sxs-lookup"><span data-stu-id="d2662-106">To complete these steps, you must first complete the steps in the “ER Configure format to do counting and summing (Part 1: Create format)” procedure.</span></span>

<span data-ttu-id="d2662-107">Este procedimento é para um recurso que foi adicionado à versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="d2662-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="create-a-format-configuration-to-add-counting-and-summing-details"></a><span data-ttu-id="d2662-108">Criar uma configuração de formato para adicionar detalhes de contagem e soma</span><span class="sxs-lookup"><span data-stu-id="d2662-108">Create a format configuration to add counting and summing details</span></span>
1. <span data-ttu-id="d2662-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d2662-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="d2662-110">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="d2662-110">Click Reporting configurations.</span></span>
3. <span data-ttu-id="d2662-111">Na árvore, expanda 'Modelo intrastat'.</span><span class="sxs-lookup"><span data-stu-id="d2662-111">In the tree, expand 'Intrastat model'.</span></span>
4. <span data-ttu-id="d2662-112">Na árvore, selecione 'Modelo intrastat\Intrastat (DE)'.</span><span class="sxs-lookup"><span data-stu-id="d2662-112">In the tree, select 'Intrastat model\Intrastat (DE)'.</span></span>
    * <span data-ttu-id="d2662-113">Suponha que você precise personalizar o formato fornecido pela Microsoft adicionando linhas com os detalhes do resumo no final do relatório intrastat.</span><span class="sxs-lookup"><span data-stu-id="d2662-113">Assume that you need to customize the format provided by Microsoft by adding lines with summary details at the end of the Intrastat report.</span></span> <span data-ttu-id="d2662-114">Você precisa fazer isso derivando nossa própria instância da configuração do intrastat a partir da instância da Microsoft para fazer as modificações.</span><span class="sxs-lookup"><span data-stu-id="d2662-114">You need to do that by deriving our own instance of the Intrastat configuration from the Microsoft instance to make modifications.</span></span>  
5. <span data-ttu-id="d2662-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2662-115">Click Create configuration to open the drop dialog.</span></span>
6. <span data-ttu-id="d2662-116">No campo Novo, insira 'Derivar de Nome: Intrastat (DE), Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="d2662-116">In the New field, enter 'Derive from Name: Intrastat (DE), Microsoft'.</span></span>
7. <span data-ttu-id="d2662-117">No campo Nome, digite "Intrastat (DE) com contagem e soma".</span><span class="sxs-lookup"><span data-stu-id="d2662-117">In the Name field, type 'Intrastat (DE) with counting & summing'.</span></span>
8. <span data-ttu-id="d2662-118">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="d2662-118">Click Create configuration.</span></span>

## <a name="configure-this-report-to-do-counting-and-summation-based-on-output-details"></a><span data-ttu-id="d2662-119">Configurar este relatório para fazer a contagem e soma baseadas nos detalhes de saída</span><span class="sxs-lookup"><span data-stu-id="d2662-119">Configure this report to do counting and summation based on output details</span></span>
1. <span data-ttu-id="d2662-120">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="d2662-120">Click Designer.</span></span>
2. <span data-ttu-id="d2662-121">Selecione Sim no campo Coletar detalhes de saída.</span><span class="sxs-lookup"><span data-stu-id="d2662-121">Select Yes in the Collect output details field.</span></span>
    * <span data-ttu-id="d2662-122">Este sinalizador será ativado no tempo de execução do processo de coleta dos detalhes de saída para gerar o arquivo do intrastat.</span><span class="sxs-lookup"><span data-stu-id="d2662-122">This flag will activate at run-time the process of collecting output details for generating the Intrastat file.</span></span>  
    * <span data-ttu-id="d2662-123">Você precisa fazer a contagem das diferentes direções do intrastat, portanto adicione uma enumeração do modelo dedicada à lista de fontes de dados desta configuração de formato.</span><span class="sxs-lookup"><span data-stu-id="d2662-123">You need to do counting for different Intrastat directions, so add a dedicated model enumeration to the data sources’ list of this format configuration.</span></span>  
3. <span data-ttu-id="d2662-124">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d2662-124">Click the Mapping tab.</span></span>
4. <span data-ttu-id="d2662-125">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2662-125">Click Add root to open the drop dialog.</span></span>
5. <span data-ttu-id="d2662-126">Na árvore, selecione 'Modelo de dados\Enumeração'.</span><span class="sxs-lookup"><span data-stu-id="d2662-126">In the tree, select 'Data model\Enumeration '.</span></span>
6. <span data-ttu-id="d2662-127">No campo Nome, digite 'Direção'.</span><span class="sxs-lookup"><span data-stu-id="d2662-127">In the Name field, type 'Direction'.</span></span>
7. <span data-ttu-id="d2662-128">No campo Enumeração do modelo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d2662-128">In the Model enumeration field, enter or select a value.</span></span>
    * <span data-ttu-id="d2662-129">Selecione o valor Direção.</span><span class="sxs-lookup"><span data-stu-id="d2662-129">Select the value Direction.</span></span>  
8. <span data-ttu-id="d2662-130">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2662-130">Click OK.</span></span>
9. <span data-ttu-id="d2662-131">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2662-131">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="d2662-132">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="d2662-132">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="d2662-133">No campo Nome, digite '$BlockName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-133">In the Name field, type '$BlockName'.</span></span>
12. <span data-ttu-id="d2662-134">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="d2662-134">Click Edit formula.</span></span>
13. <span data-ttu-id="d2662-135">No campo Fórmula, insira '"bloco"'.</span><span class="sxs-lookup"><span data-stu-id="d2662-135">In the Formula field, enter '"block"'.</span></span>
14. <span data-ttu-id="d2662-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-136">Click Save.</span></span>
15. <span data-ttu-id="d2662-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-137">Close the page.</span></span>
16. <span data-ttu-id="d2662-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2662-138">Click OK.</span></span>
17. <span data-ttu-id="d2662-139">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2662-139">Click Add root to open the drop dialog.</span></span>
18. <span data-ttu-id="d2662-140">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="d2662-140">In the tree, select 'Functions\Calculated field'.</span></span>
19. <span data-ttu-id="d2662-141">No campo Nome, digite '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-141">In the Name field, type '$RecName'.</span></span>
20. <span data-ttu-id="d2662-142">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="d2662-142">Click Edit formula.</span></span>
21. <span data-ttu-id="d2662-143">No campo Fórmula, insira '"registro"'.</span><span class="sxs-lookup"><span data-stu-id="d2662-143">In the Formula field, enter '"record"'.</span></span>
22. <span data-ttu-id="d2662-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-144">Click Save.</span></span>
23. <span data-ttu-id="d2662-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-145">Close the page.</span></span>
24. <span data-ttu-id="d2662-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2662-146">Click OK.</span></span>
25. <span data-ttu-id="d2662-147">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d2662-147">Click Add root to open the drop dialog.</span></span>
26. <span data-ttu-id="d2662-148">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="d2662-148">In the tree, select 'Functions\Calculated field'.</span></span>
27. <span data-ttu-id="d2662-149">No campo Nome, digite '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-149">In the Name field, type '$InvName'.</span></span>
28. <span data-ttu-id="d2662-150">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="d2662-150">Click Edit formula.</span></span>
29. <span data-ttu-id="d2662-151">No campo Fórmula, insira '"InvoicedAmountEUR"'.</span><span class="sxs-lookup"><span data-stu-id="d2662-151">In the Formula field, enter '"InvoicedAmountEUR"'.</span></span>
30. <span data-ttu-id="d2662-152">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-152">Click Save.</span></span>
31. <span data-ttu-id="d2662-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-153">Close the page.</span></span>
32. <span data-ttu-id="d2662-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2662-154">Click OK.</span></span>
33. <span data-ttu-id="d2662-155">Na árvore, selecione 'Intrastat\Dados'.</span><span class="sxs-lookup"><span data-stu-id="d2662-155">In the tree, select 'Intrastat\Data'.</span></span>
34. <span data-ttu-id="d2662-156">Clique no botão Editar do campo 'Nome da chave de dados coletada'</span><span class="sxs-lookup"><span data-stu-id="d2662-156">Click Edit button for the ‘Collected data key name’ field</span></span>
35. <span data-ttu-id="d2662-157">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d2662-157">Click Add data source.</span></span>
    * <span data-ttu-id="d2662-158">$BlockName</span><span class="sxs-lookup"><span data-stu-id="d2662-158">$BlockName</span></span>  
36. <span data-ttu-id="d2662-159">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-159">Click Save.</span></span>
37. <span data-ttu-id="d2662-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-160">Close the page.</span></span>
38. <span data-ttu-id="d2662-161">Clique no botão Editar do campo Valor da chave de dados coletada.</span><span class="sxs-lookup"><span data-stu-id="d2662-161">Click the Edit button for the Collected data key value field.</span></span>
39. <span data-ttu-id="d2662-162">No campo Fórmula, insira 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span><span class="sxs-lookup"><span data-stu-id="d2662-162">In the Formula field, enter 'IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")'.</span></span>
    * <span data-ttu-id="d2662-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span><span class="sxs-lookup"><span data-stu-id="d2662-163">IF(Intrastat.CommodityRecord.Direction=Direction.Import, "Import", "Export")</span></span>  
40. <span data-ttu-id="d2662-164">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-164">Click Save.</span></span>
41. <span data-ttu-id="d2662-165">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-165">Close the page.</span></span>
    * <span data-ttu-id="d2662-166">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="d2662-166">Count the lines of this sequence.</span></span> <span data-ttu-id="d2662-167">Os resultados serão usados com o nome "bloco" separadamente para as diferentes direções.</span><span class="sxs-lookup"><span data-stu-id="d2662-167">The results will be used with the name “block” separately for different directions.</span></span> <span data-ttu-id="d2662-168">O valor "Importar" será usado para todas as transações intrastat de entrada.</span><span class="sxs-lookup"><span data-stu-id="d2662-168">Value “Import” will be used for any arrivals Intrastat transactions.</span></span> <span data-ttu-id="d2662-169">O valor "Exportar" será usado para todas as transações intrastat de expedição.</span><span class="sxs-lookup"><span data-stu-id="d2662-169">The value “Export” will be used for any Intrastat dispatches transactions.</span></span> <span data-ttu-id="d2662-170">Considere isso como uma planilha de Excel virtual.</span><span class="sxs-lookup"><span data-stu-id="d2662-170">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="d2662-171">Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente.</span><span class="sxs-lookup"><span data-stu-id="d2662-171">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span>  
42. <span data-ttu-id="d2662-172">Na árvore, expanda 'Intrastat\Dados: Sequência'.</span><span class="sxs-lookup"><span data-stu-id="d2662-172">In the tree, expand 'Intrastat\Data: Sequence'.</span></span>
43. <span data-ttu-id="d2662-173">Na árvore, selecione 'Intrastat\Dados: Sequência\Entradas?'.</span><span class="sxs-lookup"><span data-stu-id="d2662-173">In the tree, select 'Intrastat\Data: Sequence\Arrivals?'.</span></span>
44. <span data-ttu-id="d2662-174">Clique no botão Editar do campo 'Nome da chave de dados coletada',</span><span class="sxs-lookup"><span data-stu-id="d2662-174">Click Edit button for the ‘Collected data key name’ field.</span></span>
    * <span data-ttu-id="d2662-175">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="d2662-175">Count the lines of this sequence.</span></span> <span data-ttu-id="d2662-176">Os resultados serão memorizados usando o nome "registro".</span><span class="sxs-lookup"><span data-stu-id="d2662-176">The results will be memorized using the name “record”.</span></span>  
45. <span data-ttu-id="d2662-177">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-177">In the tree, select '$RecName'.</span></span>
46. <span data-ttu-id="d2662-178">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d2662-178">Click Add data source.</span></span>
47. <span data-ttu-id="d2662-179">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-179">Click Save.</span></span>
48. <span data-ttu-id="d2662-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-180">Close the page.</span></span>
49. <span data-ttu-id="d2662-181">Clique no botão Editar do campo 'Valor da chave de dados coletada'.</span><span class="sxs-lookup"><span data-stu-id="d2662-181">Click Edit button for the ‘Collected data key value’ field</span></span>
50. <span data-ttu-id="d2662-182">No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="d2662-182">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
51. <span data-ttu-id="d2662-183">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-183">Click Save.</span></span>
52. <span data-ttu-id="d2662-184">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-184">Close the page.</span></span>
    * <span data-ttu-id="d2662-185">Conte as linhas da sequência.</span><span class="sxs-lookup"><span data-stu-id="d2662-185">Count the lines of this sequence.</span></span> <span data-ttu-id="d2662-186">Os resultados serão usados com o nome "registro" separadamente para os diferentes códigos de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="d2662-186">The results will be used with the name “record” separately for different commodity codes.</span></span> <span data-ttu-id="d2662-187">Considere isso como uma planilha de Excel virtual.</span><span class="sxs-lookup"><span data-stu-id="d2662-187">Consider this to be a virtual Excel spreadsheet.</span></span> <span data-ttu-id="d2662-188">Para cada transação, uma linha na primeira coluna "bloco" será preenchida com valores "Importar" e "Exportar" consequentemente e o segundo bloco "registro" será preenchido com o valor do código de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="d2662-188">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly and the second block “record” is filled with the commodity code value.</span></span>  
53. <span data-ttu-id="d2662-189">Na árvore, selecione 'Intrastat\Dados: Sequência\Expedições?'.</span><span class="sxs-lookup"><span data-stu-id="d2662-189">In the tree, select 'Intrastat\Data: Sequence\Dispatches?'.</span></span>
54. <span data-ttu-id="d2662-190">Clique no botão Editar do campo 'Nome da chave de dados coletada'</span><span class="sxs-lookup"><span data-stu-id="d2662-190">Click Edit button for the ‘Collected data key name’ field</span></span>
55. <span data-ttu-id="d2662-191">Na árvore, selecione '$RecName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-191">In the tree, select '$RecName'.</span></span>
56. <span data-ttu-id="d2662-192">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d2662-192">Click Add data source.</span></span>
57. <span data-ttu-id="d2662-193">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-193">Click Save.</span></span>
58. <span data-ttu-id="d2662-194">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-194">Close the page.</span></span>
59. <span data-ttu-id="d2662-195">Clique no botão Editar do campo 'Valor da chave de dados coletada'.</span><span class="sxs-lookup"><span data-stu-id="d2662-195">Click the Edit button for the ‘Collected data key value’ field.</span></span>
60. <span data-ttu-id="d2662-196">No campo Fórmula, insira 'Intrastat.CommodityRecord.CommodityCode'.</span><span class="sxs-lookup"><span data-stu-id="d2662-196">In the Formula field, enter 'Intrastat.CommodityRecord.CommodityCode'.</span></span>
61. <span data-ttu-id="d2662-197">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-197">Click Save.</span></span>
62. <span data-ttu-id="d2662-198">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-198">Close the page.</span></span>
63. <span data-ttu-id="d2662-199">Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?'.</span><span class="sxs-lookup"><span data-stu-id="d2662-199">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?'.</span></span>
64. <span data-ttu-id="d2662-200">Na árvore, expanda 'Intrastat\Dados: Sequência\Expedições: Sequência?\Registro =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="d2662-200">In the tree, expand 'Intrastat\Data: Sequence\Dispatches: Sequence?\Record =  Intrastat.CommodityRecord'.</span></span>
65. <span data-ttu-id="d2662-201">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="d2662-201">Click the Format tab.</span></span>
66. <span data-ttu-id="d2662-202">Na árvore, selecione 'Intrastat\Dados\Expedições\Registro\Valor da fatura em EUR'.</span><span class="sxs-lookup"><span data-stu-id="d2662-202">In the tree, select 'Intrastat\Data\Dispatches\Record\Invoice amount EUR'.</span></span>
67. <span data-ttu-id="d2662-203">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d2662-203">Click the Mapping tab.</span></span>
68. <span data-ttu-id="d2662-204">Clique no botão Editar do campo 'Nome da chave de dados coletada',</span><span class="sxs-lookup"><span data-stu-id="d2662-204">Click the Edit button for the ‘Collected data key name’ field.</span></span>
69. <span data-ttu-id="d2662-205">Na árvore, selecione '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-205">In the tree, select '$InvName'.</span></span>
70. <span data-ttu-id="d2662-206">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d2662-206">Click Add data source.</span></span>
71. <span data-ttu-id="d2662-207">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-207">Click Save.</span></span>
72. <span data-ttu-id="d2662-208">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-208">Close the page.</span></span>
    * <span data-ttu-id="d2662-209">Resuma os valores do valor faturado das linhas desta sequência.</span><span class="sxs-lookup"><span data-stu-id="d2662-209">Summarize the invoiced amount values for lines of this sequence.</span></span> <span data-ttu-id="d2662-210">Os resultados serão usados com o nome "InvoicedAmountEUR" separadamente para as diferentes direções intrastat e os códigos de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="d2662-210">The results will be used with the name “InvoicedAmountEUR” separately for different Intrastat directions and commodity codes.</span></span> <span data-ttu-id="d2662-211">Considere isso como uma criação virtual em planilha de Excel.</span><span class="sxs-lookup"><span data-stu-id="d2662-211">Consider this to be a virtual creation in Excel spreadsheet.</span></span> <span data-ttu-id="d2662-212">Para cada transação, uma linha em que a primeira coluna "bloco" será preenchida com os valores "Importar" e "Exportar" consequentemente.</span><span class="sxs-lookup"><span data-stu-id="d2662-212">For each transaction a row where the first column “block” is filled with the values “Import” and “Export” accordingly.</span></span> <span data-ttu-id="d2662-213">O segundo bloco "registro" será preenchido com o valor do código de mercadoria e a terceira coluna "InvoicedAmountEUR" será preenchida com o valor da fatura.</span><span class="sxs-lookup"><span data-stu-id="d2662-213">The second block “record” is filled with the commodity code value, and the third column “InvoicedAmountEUR” is filled with the invoice amount value.</span></span>  
73. <span data-ttu-id="d2662-214">Na árvore, expanda 'Intrastat\Dados\Entradas?'.</span><span class="sxs-lookup"><span data-stu-id="d2662-214">In the tree, expand 'Intrastat\Data\Arrivals?'.</span></span>
74. <span data-ttu-id="d2662-215">Na árvore, expanda 'Intrastat\Dados\Entradas?\Registro =  Intrastat.CommodityRecord'.</span><span class="sxs-lookup"><span data-stu-id="d2662-215">In the tree, expand 'Intrastat\Data\Arrivals?\Record =  Intrastat.CommodityRecord'.</span></span>
75. <span data-ttu-id="d2662-216">Clique na guia Formato.</span><span class="sxs-lookup"><span data-stu-id="d2662-216">Click the Format tab.</span></span>
76. <span data-ttu-id="d2662-217">Na árvore, selecione 'Intrastat\Dados\Entradas\Registro\Valor da fatura em EUR'.</span><span class="sxs-lookup"><span data-stu-id="d2662-217">In the tree, select 'Intrastat\Data\Arrivals\Record\Invoice amount EUR'.</span></span>
77. <span data-ttu-id="d2662-218">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d2662-218">Click the Mapping tab.</span></span>
78. <span data-ttu-id="d2662-219">Clique no botão Editar do campo 'Nome da chave de dados coletada',</span><span class="sxs-lookup"><span data-stu-id="d2662-219">Click the Edit button for the ‘Collected data key name’ field.</span></span>
79. <span data-ttu-id="d2662-220">Na árvore, selecione '$InvName'.</span><span class="sxs-lookup"><span data-stu-id="d2662-220">In the tree, select '$InvName'.</span></span>
80. <span data-ttu-id="d2662-221">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d2662-221">Click Add data source.</span></span>
81. <span data-ttu-id="d2662-222">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-222">Click Save.</span></span>
82. <span data-ttu-id="d2662-223">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-223">Close the page.</span></span>
83. <span data-ttu-id="d2662-224">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2662-224">Click Save.</span></span>
84. <span data-ttu-id="d2662-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2662-225">Close the page.</span></span>

