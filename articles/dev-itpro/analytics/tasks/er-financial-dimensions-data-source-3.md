--- 
title: "ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)"
description: "As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 45096a728ad6f9e331b53b4e12ca0ff9317a3939
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3-design-the-report"></a><span data-ttu-id="783de-103">O ER usa dimensões financeiras como uma fonte de dados (parte 3: criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="783de-103">ER Use financial dimensions as a data source (Part 3: Design the report)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="783de-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="783de-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="783de-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="783de-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="783de-106">Para completar essas etapas, primeiro você deve concluir as etapas “dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo).”</span><span class="sxs-lookup"><span data-stu-id="783de-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 2: Model mapping)” procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="783de-107">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="783de-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="783de-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="783de-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="783de-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="783de-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="783de-110">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="783de-111">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="783de-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="783de-112">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="783de-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="783de-113">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="783de-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="783de-114">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="783de-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="783de-115">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="783de-115">Click Create configuration.</span></span>
8. <span data-ttu-id="783de-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="783de-116">Click Designer.</span></span>
9. <span data-ttu-id="783de-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="783de-118">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="783de-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="783de-119">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="783de-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="783de-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-120">Click OK.</span></span>
13. <span data-ttu-id="783de-121">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="783de-122">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="783de-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="783de-123">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="783de-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="783de-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-124">Click OK.</span></span>
17. <span data-ttu-id="783de-125">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="783de-126">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="783de-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="783de-127">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="783de-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="783de-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-128">Click OK.</span></span>
21. <span data-ttu-id="783de-129">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="783de-130">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="783de-131">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="783de-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="783de-132">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="783de-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="783de-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-133">Click OK.</span></span>
26. <span data-ttu-id="783de-134">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="783de-135">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="783de-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="783de-136">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="783de-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="783de-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-137">Click OK.</span></span>
30. <span data-ttu-id="783de-138">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="783de-139">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="783de-140">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="783de-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="783de-141">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="783de-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="783de-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-142">Click OK.</span></span>
35. <span data-ttu-id="783de-143">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="783de-144">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="783de-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="783de-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-145">Click OK.</span></span>
38. <span data-ttu-id="783de-146">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="783de-147">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="783de-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="783de-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-148">Click OK.</span></span>
41. <span data-ttu-id="783de-149">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="783de-150">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="783de-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="783de-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-151">Click OK.</span></span>
44. <span data-ttu-id="783de-152">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="783de-153">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="783de-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="783de-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-154">Click OK.</span></span>
47. <span data-ttu-id="783de-155">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="783de-156">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="783de-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="783de-157">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="783de-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="783de-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-158">Click OK.</span></span>
51. <span data-ttu-id="783de-159">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="783de-160">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="783de-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="783de-161">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="783de-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="783de-162">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="783de-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="783de-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-163">Click OK.</span></span>
56. <span data-ttu-id="783de-164">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="783de-165">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="783de-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="783de-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-166">Click OK.</span></span>
59. <span data-ttu-id="783de-167">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="783de-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="783de-168">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="783de-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="783de-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="783de-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="783de-170">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="783de-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="783de-171">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="783de-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="783de-172">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="783de-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="783de-173">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="783de-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="783de-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="783de-176">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="783de-177">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="783de-178">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-178">Click Bind.</span></span>
9. <span data-ttu-id="783de-179">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="783de-180">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="783de-181">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-181">Click Bind.</span></span>
12. <span data-ttu-id="783de-182">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="783de-183">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="783de-184">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-184">Click Bind.</span></span>
15. <span data-ttu-id="783de-185">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="783de-186">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="783de-187">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-187">Click Bind.</span></span>
18. <span data-ttu-id="783de-188">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="783de-189">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="783de-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="783de-190">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-190">Click Bind.</span></span>
21. <span data-ttu-id="783de-191">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="783de-192">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="783de-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="783de-193">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-193">Click Bind.</span></span>
24. <span data-ttu-id="783de-194">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="783de-195">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="783de-196">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-196">Click Bind.</span></span>
27. <span data-ttu-id="783de-197">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="783de-198">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="783de-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="783de-199">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-199">Click Bind.</span></span>
30. <span data-ttu-id="783de-200">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="783de-201">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="783de-202">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-202">Click Bind.</span></span>
33. <span data-ttu-id="783de-203">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="783de-204">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="783de-205">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-205">Click Bind.</span></span>
36. <span data-ttu-id="783de-206">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="783de-207">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="783de-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="783de-208">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-208">Click Bind.</span></span>
39. <span data-ttu-id="783de-209">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="783de-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="783de-210">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="783de-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="783de-211">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-211">Click Bind.</span></span>
42. <span data-ttu-id="783de-212">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="783de-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="783de-213">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="783de-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="783de-214">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="783de-214">Click Bind.</span></span>
45. <span data-ttu-id="783de-215">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="783de-215">Click Save.</span></span>
46. <span data-ttu-id="783de-216">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="783de-216">Close the page.</span></span>


