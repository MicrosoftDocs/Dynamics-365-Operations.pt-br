---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)'
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 3)
author: NickSelin
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a3b9a8b5775d2001f3384480e2f9593f2dfa8b1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752403"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="86c18-104">ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="86c18-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="86c18-105">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="86c18-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="86c18-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="86c18-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="86c18-107">Para completar essas etapas, primeiro você deve concluir as etapas "Dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo)".</span><span class="sxs-lookup"><span data-stu-id="86c18-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="86c18-108">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="86c18-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="86c18-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="86c18-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="86c18-110">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="86c18-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="86c18-111">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="86c18-112">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="86c18-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="86c18-113">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="86c18-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="86c18-114">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="86c18-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="86c18-115">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="86c18-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="86c18-116">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="86c18-116">Click Create configuration.</span></span>
8. <span data-ttu-id="86c18-117">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="86c18-117">Click Designer.</span></span>
9. <span data-ttu-id="86c18-118">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="86c18-119">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="86c18-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="86c18-120">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="86c18-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="86c18-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-121">Click OK.</span></span>
13. <span data-ttu-id="86c18-122">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="86c18-123">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="86c18-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="86c18-124">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="86c18-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="86c18-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-125">Click OK.</span></span>
17. <span data-ttu-id="86c18-126">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="86c18-127">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="86c18-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="86c18-128">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="86c18-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="86c18-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-129">Click OK.</span></span>
21. <span data-ttu-id="86c18-130">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="86c18-131">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="86c18-132">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="86c18-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="86c18-133">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="86c18-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="86c18-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-134">Click OK.</span></span>
26. <span data-ttu-id="86c18-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="86c18-136">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="86c18-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="86c18-137">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="86c18-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="86c18-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-138">Click OK.</span></span>
30. <span data-ttu-id="86c18-139">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="86c18-140">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="86c18-141">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="86c18-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="86c18-142">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="86c18-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="86c18-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-143">Click OK.</span></span>
35. <span data-ttu-id="86c18-144">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="86c18-145">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="86c18-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="86c18-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-146">Click OK.</span></span>
38. <span data-ttu-id="86c18-147">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="86c18-148">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="86c18-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="86c18-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-149">Click OK.</span></span>
41. <span data-ttu-id="86c18-150">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="86c18-151">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="86c18-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="86c18-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-152">Click OK.</span></span>
44. <span data-ttu-id="86c18-153">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="86c18-154">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="86c18-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="86c18-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-155">Click OK.</span></span>
47. <span data-ttu-id="86c18-156">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="86c18-157">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="86c18-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="86c18-158">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="86c18-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="86c18-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-159">Click OK.</span></span>
51. <span data-ttu-id="86c18-160">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="86c18-161">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86c18-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="86c18-162">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="86c18-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="86c18-163">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="86c18-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="86c18-164">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-164">Click OK.</span></span>
56. <span data-ttu-id="86c18-165">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="86c18-166">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="86c18-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="86c18-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-167">Click OK.</span></span>
59. <span data-ttu-id="86c18-168">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="86c18-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="86c18-169">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="86c18-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="86c18-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86c18-170">Click OK.</span></span>
<span data-ttu-id="86c18-171">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="86c18-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="86c18-172">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="86c18-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="86c18-173">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="86c18-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="86c18-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="86c18-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="86c18-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="86c18-176">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="86c18-177">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="86c18-178">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="86c18-179">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="86c18-180">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-180">Click Bind.</span></span>
9. <span data-ttu-id="86c18-181">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="86c18-182">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="86c18-183">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-183">Click Bind.</span></span>
12. <span data-ttu-id="86c18-184">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="86c18-185">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="86c18-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-186">Click Bind.</span></span>
15. <span data-ttu-id="86c18-187">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="86c18-188">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="86c18-189">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-189">Click Bind.</span></span>
18. <span data-ttu-id="86c18-190">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="86c18-191">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="86c18-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="86c18-192">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-192">Click Bind.</span></span>
21. <span data-ttu-id="86c18-193">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="86c18-194">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="86c18-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="86c18-195">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-195">Click Bind.</span></span>
24. <span data-ttu-id="86c18-196">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="86c18-197">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="86c18-198">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-198">Click Bind.</span></span>
27. <span data-ttu-id="86c18-199">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="86c18-200">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="86c18-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="86c18-201">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-201">Click Bind.</span></span>
30. <span data-ttu-id="86c18-202">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="86c18-203">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="86c18-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-204">Click Bind.</span></span>
33. <span data-ttu-id="86c18-205">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="86c18-206">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="86c18-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-207">Click Bind.</span></span>
36. <span data-ttu-id="86c18-208">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="86c18-209">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="86c18-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="86c18-210">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-210">Click Bind.</span></span>
39. <span data-ttu-id="86c18-211">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="86c18-212">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="86c18-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="86c18-213">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-213">Click Bind.</span></span>
42. <span data-ttu-id="86c18-214">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="86c18-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="86c18-215">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="86c18-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="86c18-216">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86c18-216">Click Bind.</span></span>
45. <span data-ttu-id="86c18-217">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86c18-217">Click Save.</span></span>
46. <span data-ttu-id="86c18-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="86c18-218">Close the page.</span></span>
<span data-ttu-id="86c18-219">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="86c18-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]