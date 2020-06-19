---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)'
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cef61787e50561eaac4fd52741ab5f90d9c4171d
ms.sourcegitcommit: d9125c20b21459076e4fd92fd9ebfe2e53a0431b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "3406488"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="e2222-103">ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="e2222-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e2222-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="e2222-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="e2222-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="e2222-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="e2222-106">Para completar essas etapas, primeiro você deve concluir as etapas "Dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo)".</span><span class="sxs-lookup"><span data-stu-id="e2222-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="e2222-107">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="e2222-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="e2222-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="e2222-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="e2222-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="e2222-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="e2222-110">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="e2222-111">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="e2222-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="e2222-112">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="e2222-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="e2222-113">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="e2222-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="e2222-114">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="e2222-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="e2222-115">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="e2222-115">Click Create configuration.</span></span>
8. <span data-ttu-id="e2222-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="e2222-116">Click Designer.</span></span>
9. <span data-ttu-id="e2222-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="e2222-118">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="e2222-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="e2222-119">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="e2222-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="e2222-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-120">Click OK.</span></span>
13. <span data-ttu-id="e2222-121">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="e2222-122">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="e2222-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="e2222-123">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="e2222-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="e2222-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-124">Click OK.</span></span>
17. <span data-ttu-id="e2222-125">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="e2222-126">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="e2222-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="e2222-127">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="e2222-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="e2222-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-128">Click OK.</span></span>
21. <span data-ttu-id="e2222-129">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="e2222-130">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="e2222-131">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="e2222-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="e2222-132">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="e2222-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="e2222-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-133">Click OK.</span></span>
26. <span data-ttu-id="e2222-134">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="e2222-135">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="e2222-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="e2222-136">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="e2222-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="e2222-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-137">Click OK.</span></span>
30. <span data-ttu-id="e2222-138">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="e2222-139">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="e2222-140">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="e2222-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="e2222-141">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="e2222-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="e2222-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-142">Click OK.</span></span>
35. <span data-ttu-id="e2222-143">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="e2222-144">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="e2222-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="e2222-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-145">Click OK.</span></span>
38. <span data-ttu-id="e2222-146">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="e2222-147">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="e2222-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="e2222-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-148">Click OK.</span></span>
41. <span data-ttu-id="e2222-149">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="e2222-150">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="e2222-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="e2222-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-151">Click OK.</span></span>
44. <span data-ttu-id="e2222-152">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="e2222-153">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="e2222-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="e2222-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-154">Click OK.</span></span>
47. <span data-ttu-id="e2222-155">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="e2222-156">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="e2222-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="e2222-157">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="e2222-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="e2222-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-158">Click OK.</span></span>
51. <span data-ttu-id="e2222-159">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="e2222-160">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="e2222-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="e2222-161">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="e2222-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="e2222-162">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="e2222-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="e2222-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-163">Click OK.</span></span>
56. <span data-ttu-id="e2222-164">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="e2222-165">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="e2222-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="e2222-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-166">Click OK.</span></span>
59. <span data-ttu-id="e2222-167">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="e2222-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="e2222-168">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="e2222-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="e2222-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="e2222-169">Click OK.</span></span>
<span data-ttu-id="e2222-170">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="e2222-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="e2222-171">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="e2222-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="e2222-172">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="e2222-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="e2222-173">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="e2222-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="e2222-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="e2222-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="e2222-176">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="e2222-177">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="e2222-178">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="e2222-179">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-179">Click Bind.</span></span>
9. <span data-ttu-id="e2222-180">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="e2222-181">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="e2222-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-182">Click Bind.</span></span>
12. <span data-ttu-id="e2222-183">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="e2222-184">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="e2222-185">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-185">Click Bind.</span></span>
15. <span data-ttu-id="e2222-186">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="e2222-187">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="e2222-188">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-188">Click Bind.</span></span>
18. <span data-ttu-id="e2222-189">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="e2222-190">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="e2222-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="e2222-191">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-191">Click Bind.</span></span>
21. <span data-ttu-id="e2222-192">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="e2222-193">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="e2222-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="e2222-194">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-194">Click Bind.</span></span>
24. <span data-ttu-id="e2222-195">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="e2222-196">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="e2222-197">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-197">Click Bind.</span></span>
27. <span data-ttu-id="e2222-198">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="e2222-199">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="e2222-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="e2222-200">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-200">Click Bind.</span></span>
30. <span data-ttu-id="e2222-201">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="e2222-202">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="e2222-203">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-203">Click Bind.</span></span>
33. <span data-ttu-id="e2222-204">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="e2222-205">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="e2222-206">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-206">Click Bind.</span></span>
36. <span data-ttu-id="e2222-207">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="e2222-208">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="e2222-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="e2222-209">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-209">Click Bind.</span></span>
39. <span data-ttu-id="e2222-210">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="e2222-211">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="e2222-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="e2222-212">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-212">Click Bind.</span></span>
42. <span data-ttu-id="e2222-213">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="e2222-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="e2222-214">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="e2222-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="e2222-215">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="e2222-215">Click Bind.</span></span>
45. <span data-ttu-id="e2222-216">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="e2222-216">Click Save.</span></span>
46. <span data-ttu-id="e2222-217">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e2222-217">Close the page.</span></span>
<span data-ttu-id="e2222-218">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="e2222-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

