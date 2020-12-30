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
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a12f88f1e8b5e451bc8a5c5486d820da61bf3ad0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684778"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="6af94-103">ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="6af94-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6af94-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="6af94-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="6af94-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="6af94-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="6af94-106">Para completar essas etapas, primeiro você deve concluir as etapas "Dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo)".</span><span class="sxs-lookup"><span data-stu-id="6af94-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="6af94-107">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="6af94-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="6af94-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="6af94-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="6af94-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="6af94-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6af94-110">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="6af94-111">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="6af94-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="6af94-112">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="6af94-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="6af94-113">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="6af94-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="6af94-114">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="6af94-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="6af94-115">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="6af94-115">Click Create configuration.</span></span>
8. <span data-ttu-id="6af94-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="6af94-116">Click Designer.</span></span>
9. <span data-ttu-id="6af94-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="6af94-118">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6af94-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="6af94-119">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="6af94-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="6af94-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-120">Click OK.</span></span>
13. <span data-ttu-id="6af94-121">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="6af94-122">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6af94-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="6af94-123">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="6af94-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="6af94-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-124">Click OK.</span></span>
17. <span data-ttu-id="6af94-125">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="6af94-126">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6af94-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="6af94-127">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="6af94-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="6af94-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-128">Click OK.</span></span>
21. <span data-ttu-id="6af94-129">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="6af94-130">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="6af94-131">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6af94-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="6af94-132">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="6af94-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="6af94-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-133">Click OK.</span></span>
26. <span data-ttu-id="6af94-134">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="6af94-135">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6af94-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="6af94-136">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="6af94-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="6af94-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-137">Click OK.</span></span>
30. <span data-ttu-id="6af94-138">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="6af94-139">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="6af94-140">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6af94-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="6af94-141">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="6af94-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="6af94-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-142">Click OK.</span></span>
35. <span data-ttu-id="6af94-143">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="6af94-144">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="6af94-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="6af94-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-145">Click OK.</span></span>
38. <span data-ttu-id="6af94-146">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="6af94-147">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="6af94-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="6af94-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-148">Click OK.</span></span>
41. <span data-ttu-id="6af94-149">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="6af94-150">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="6af94-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="6af94-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-151">Click OK.</span></span>
44. <span data-ttu-id="6af94-152">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="6af94-153">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="6af94-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="6af94-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-154">Click OK.</span></span>
47. <span data-ttu-id="6af94-155">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="6af94-156">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="6af94-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="6af94-157">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="6af94-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="6af94-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-158">Click OK.</span></span>
51. <span data-ttu-id="6af94-159">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="6af94-160">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6af94-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="6af94-161">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="6af94-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="6af94-162">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="6af94-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="6af94-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-163">Click OK.</span></span>
56. <span data-ttu-id="6af94-164">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="6af94-165">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="6af94-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="6af94-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-166">Click OK.</span></span>
59. <span data-ttu-id="6af94-167">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="6af94-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="6af94-168">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="6af94-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="6af94-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6af94-169">Click OK.</span></span>
<span data-ttu-id="6af94-170">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format1.png)</span><span class="sxs-lookup"><span data-stu-id="6af94-170">![ER Operations designer page](../media/er-financial-dimensions-guides-format1.png)</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="6af94-171">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="6af94-171">Map report elements to data sources</span></span>
1. <span data-ttu-id="6af94-172">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="6af94-172">Click the Mapping tab.</span></span>
2. <span data-ttu-id="6af94-173">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="6af94-173">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="6af94-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="6af94-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="6af94-176">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-176">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="6af94-177">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-177">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="6af94-178">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-178">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="6af94-179">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-179">Click Bind.</span></span>
9. <span data-ttu-id="6af94-180">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-180">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="6af94-181">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-181">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="6af94-182">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-182">Click Bind.</span></span>
12. <span data-ttu-id="6af94-183">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-183">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="6af94-184">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-184">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="6af94-185">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-185">Click Bind.</span></span>
15. <span data-ttu-id="6af94-186">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-186">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="6af94-187">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-187">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="6af94-188">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-188">Click Bind.</span></span>
18. <span data-ttu-id="6af94-189">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-189">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="6af94-190">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="6af94-190">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="6af94-191">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-191">Click Bind.</span></span>
21. <span data-ttu-id="6af94-192">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-192">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="6af94-193">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="6af94-193">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="6af94-194">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-194">Click Bind.</span></span>
24. <span data-ttu-id="6af94-195">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-195">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="6af94-196">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-196">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="6af94-197">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-197">Click Bind.</span></span>
27. <span data-ttu-id="6af94-198">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-198">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="6af94-199">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="6af94-199">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="6af94-200">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-200">Click Bind.</span></span>
30. <span data-ttu-id="6af94-201">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-201">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="6af94-202">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-202">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="6af94-203">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-203">Click Bind.</span></span>
33. <span data-ttu-id="6af94-204">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-204">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="6af94-205">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-205">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="6af94-206">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-206">Click Bind.</span></span>
36. <span data-ttu-id="6af94-207">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-207">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="6af94-208">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="6af94-208">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="6af94-209">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-209">Click Bind.</span></span>
39. <span data-ttu-id="6af94-210">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-210">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="6af94-211">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="6af94-211">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="6af94-212">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-212">Click Bind.</span></span>
42. <span data-ttu-id="6af94-213">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="6af94-213">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="6af94-214">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="6af94-214">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="6af94-215">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="6af94-215">Click Bind.</span></span>
45. <span data-ttu-id="6af94-216">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="6af94-216">Click Save.</span></span>
46. <span data-ttu-id="6af94-217">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6af94-217">Close the page.</span></span>
<span data-ttu-id="6af94-218">![Página do designer de operações de ER](../media/er-financial-dimensions-guides-format2.png)</span><span class="sxs-lookup"><span data-stu-id="6af94-218">![ER Operations designer page](../media/er-financial-dimensions-guides-format2.png)</span></span>

