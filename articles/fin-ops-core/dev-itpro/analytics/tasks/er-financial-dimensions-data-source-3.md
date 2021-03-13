---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)'
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 3)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b0d6da96850e04d5e975b3febbfae2737c8a86af
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092291"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="f3038-104">ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="f3038-104">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3038-105">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="f3038-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="f3038-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="f3038-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="f3038-107">Para completar essas etapas, primeiro você deve concluir as etapas "Dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo)".</span><span class="sxs-lookup"><span data-stu-id="f3038-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="f3038-108">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="f3038-108">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="f3038-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="f3038-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="f3038-110">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="f3038-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f3038-111">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-111">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="f3038-112">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="f3038-112">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="f3038-113">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="f3038-113">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="f3038-114">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="f3038-114">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="f3038-115">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="f3038-115">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="f3038-116">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f3038-116">Click Create configuration.</span></span>
8. <span data-ttu-id="f3038-117">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f3038-117">Click Designer.</span></span>
9. <span data-ttu-id="f3038-118">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-118">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="f3038-119">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f3038-119">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="f3038-120">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="f3038-120">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="f3038-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-121">Click OK.</span></span>
13. <span data-ttu-id="f3038-122">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-122">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="f3038-123">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="f3038-123">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="f3038-124">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f3038-124">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="f3038-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-125">Click OK.</span></span>
17. <span data-ttu-id="f3038-126">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-126">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="f3038-127">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f3038-127">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="f3038-128">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="f3038-128">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="f3038-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-129">Click OK.</span></span>
21. <span data-ttu-id="f3038-130">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-130">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="f3038-131">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-131">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="f3038-132">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="f3038-132">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="f3038-133">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="f3038-133">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="f3038-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-134">Click OK.</span></span>
26. <span data-ttu-id="f3038-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-135">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f3038-136">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f3038-136">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="f3038-137">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="f3038-137">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="f3038-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-138">Click OK.</span></span>
30. <span data-ttu-id="f3038-139">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-139">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="f3038-140">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-140">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="f3038-141">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="f3038-141">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="f3038-142">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="f3038-142">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="f3038-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-143">Click OK.</span></span>
35. <span data-ttu-id="f3038-144">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-144">Click Add Attribute.</span></span>
36. <span data-ttu-id="f3038-145">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="f3038-145">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="f3038-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-146">Click OK.</span></span>
38. <span data-ttu-id="f3038-147">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-147">Click Add Attribute.</span></span>
39. <span data-ttu-id="f3038-148">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="f3038-148">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="f3038-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-149">Click OK.</span></span>
41. <span data-ttu-id="f3038-150">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-150">Click Add Attribute.</span></span>
42. <span data-ttu-id="f3038-151">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="f3038-151">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="f3038-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-152">Click OK.</span></span>
44. <span data-ttu-id="f3038-153">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-153">Click Add Attribute.</span></span>
45. <span data-ttu-id="f3038-154">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="f3038-154">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="f3038-155">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-155">Click OK.</span></span>
47. <span data-ttu-id="f3038-156">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-156">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="f3038-157">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f3038-157">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="f3038-158">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="f3038-158">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="f3038-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-159">Click OK.</span></span>
51. <span data-ttu-id="f3038-160">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-160">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="f3038-161">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f3038-161">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="f3038-162">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="f3038-162">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="f3038-163">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="f3038-163">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="f3038-164">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-164">Click OK.</span></span>
56. <span data-ttu-id="f3038-165">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-165">Click Add Attribute.</span></span>
57. <span data-ttu-id="f3038-166">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="f3038-166">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="f3038-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-167">Click OK.</span></span>
59. <span data-ttu-id="f3038-168">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="f3038-168">Click Add Attribute.</span></span>
60. <span data-ttu-id="f3038-169">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="f3038-169">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="f3038-170">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f3038-170">Click OK.</span></span>
<span data-ttu-id="f3038-171">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="f3038-171">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="f3038-172">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="f3038-172">Map report elements to data sources</span></span>
1. <span data-ttu-id="f3038-173">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="f3038-173">Click the Mapping tab.</span></span>
2. <span data-ttu-id="f3038-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="f3038-174">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="f3038-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="f3038-176">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="f3038-177">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-177">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="f3038-178">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-178">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="f3038-179">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-179">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="f3038-180">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-180">Click Bind.</span></span>
9. <span data-ttu-id="f3038-181">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-181">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="f3038-182">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-182">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="f3038-183">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-183">Click Bind.</span></span>
12. <span data-ttu-id="f3038-184">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-184">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="f3038-185">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="f3038-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-186">Click Bind.</span></span>
15. <span data-ttu-id="f3038-187">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-187">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="f3038-188">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="f3038-189">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-189">Click Bind.</span></span>
18. <span data-ttu-id="f3038-190">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-190">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="f3038-191">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="f3038-191">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="f3038-192">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-192">Click Bind.</span></span>
21. <span data-ttu-id="f3038-193">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-193">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="f3038-194">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="f3038-194">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="f3038-195">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-195">Click Bind.</span></span>
24. <span data-ttu-id="f3038-196">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-196">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="f3038-197">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-197">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="f3038-198">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-198">Click Bind.</span></span>
27. <span data-ttu-id="f3038-199">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-199">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="f3038-200">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="f3038-200">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="f3038-201">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-201">Click Bind.</span></span>
30. <span data-ttu-id="f3038-202">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-202">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="f3038-203">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-203">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="f3038-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-204">Click Bind.</span></span>
33. <span data-ttu-id="f3038-205">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-205">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="f3038-206">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-206">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="f3038-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-207">Click Bind.</span></span>
36. <span data-ttu-id="f3038-208">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-208">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="f3038-209">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="f3038-209">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="f3038-210">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-210">Click Bind.</span></span>
39. <span data-ttu-id="f3038-211">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-211">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="f3038-212">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="f3038-212">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="f3038-213">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-213">Click Bind.</span></span>
42. <span data-ttu-id="f3038-214">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="f3038-214">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="f3038-215">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="f3038-215">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="f3038-216">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f3038-216">Click Bind.</span></span>
45. <span data-ttu-id="f3038-217">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f3038-217">Click Save.</span></span>
46. <span data-ttu-id="f3038-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f3038-218">Close the page.</span></span>
<span data-ttu-id="f3038-219">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="f3038-219">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

