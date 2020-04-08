---
title: 'ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)'
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 7bbbc81eaf8c13e8d13e30a0276e38453e07ead9
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142515"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-3---design-the-report"></a><span data-ttu-id="84747-103">ER Usar dimensões financeiras como uma fonte de dados (Parte 3: Criar o relatório)</span><span class="sxs-lookup"><span data-stu-id="84747-103">ER Use financial dimensions as a data source (Part 3 - Design the report)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="84747-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="84747-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="84747-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="84747-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="84747-106">Para completar essas etapas, primeiro você deve concluir as etapas "Dimensões financeiras de uso ER como uma fonte de dados do procedimento (parte 2: mapeamento de modelo)".</span><span class="sxs-lookup"><span data-stu-id="84747-106">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 2: Model mapping)" procedure.</span></span>


## <a name="design-a-report-to-present-financial-dimensions"></a><span data-ttu-id="84747-107">Criar um relatório para apresentar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="84747-107">Design a report to present financial dimensions</span></span>
1. <span data-ttu-id="84747-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="84747-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="84747-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="84747-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="84747-110">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-110">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="84747-111">No campo Novo, insira 'Formato baseado no modelo de dados modelo de amostra de dimensões financeiras'.</span><span class="sxs-lookup"><span data-stu-id="84747-111">In the New field, enter 'Format based on data model Financial dimensions sample model'.</span></span>
    * <span data-ttu-id="84747-112">Use o modelo criado antecipado como a fonte de dados de seu novo relatório.</span><span class="sxs-lookup"><span data-stu-id="84747-112">Use the model that was created in advance as the data source for your new report.</span></span>  
5. <span data-ttu-id="84747-113">No campo Nome, digite "Relatório de jornal razão".</span><span class="sxs-lookup"><span data-stu-id="84747-113">In the Name field, type 'Ledger journal report'.</span></span>
6. <span data-ttu-id="84747-114">No campo Definição de modelo de dados, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="84747-114">In the Data model definition field, select Entry.</span></span>
7. <span data-ttu-id="84747-115">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="84747-115">Click Create configuration.</span></span>
8. <span data-ttu-id="84747-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="84747-116">Click Designer.</span></span>
9. <span data-ttu-id="84747-117">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-117">Click Add root to open the drop dialog.</span></span>
10. <span data-ttu-id="84747-118">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="84747-118">In the tree, select 'XML\Element'.</span></span>
11. <span data-ttu-id="84747-119">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="84747-119">In the Name field, type 'Root'.</span></span>
12. <span data-ttu-id="84747-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-120">Click OK.</span></span>
13. <span data-ttu-id="84747-121">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-121">Click Add to open the drop dialog.</span></span>
14. <span data-ttu-id="84747-122">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="84747-122">In the tree, select 'XML\Attribute'.</span></span>
15. <span data-ttu-id="84747-123">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="84747-123">In the Name field, type 'Company'.</span></span>
16. <span data-ttu-id="84747-124">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-124">Click OK.</span></span>
17. <span data-ttu-id="84747-125">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-125">Click Add to open the drop dialog.</span></span>
18. <span data-ttu-id="84747-126">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="84747-126">In the tree, select 'XML\Element'.</span></span>
19. <span data-ttu-id="84747-127">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="84747-127">In the Name field, type 'Journal'.</span></span>
20. <span data-ttu-id="84747-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-128">Click OK.</span></span>
21. <span data-ttu-id="84747-129">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-129">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
22. <span data-ttu-id="84747-130">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-130">Click Add to open the drop dialog.</span></span>
23. <span data-ttu-id="84747-131">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="84747-131">In the tree, select 'XML\Attribute'.</span></span>
24. <span data-ttu-id="84747-132">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="84747-132">In the Name field, type 'Batch'.</span></span>
25. <span data-ttu-id="84747-133">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-133">Click OK.</span></span>
26. <span data-ttu-id="84747-134">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-134">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="84747-135">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="84747-135">In the tree, select 'XML\Element'.</span></span>
28. <span data-ttu-id="84747-136">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="84747-136">In the Name field, type 'Transaction'.</span></span>
29. <span data-ttu-id="84747-137">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-137">Click OK.</span></span>
30. <span data-ttu-id="84747-138">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-138">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
31. <span data-ttu-id="84747-139">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-139">Click Add to open the drop dialog.</span></span>
32. <span data-ttu-id="84747-140">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="84747-140">In the tree, select 'XML\Attribute'.</span></span>
33. <span data-ttu-id="84747-141">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="84747-141">In the Name field, type 'Voucher'.</span></span>
34. <span data-ttu-id="84747-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-142">Click OK.</span></span>
35. <span data-ttu-id="84747-143">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-143">Click Add Attribute.</span></span>
36. <span data-ttu-id="84747-144">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="84747-144">In the Name field, type 'Date'.</span></span>
37. <span data-ttu-id="84747-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-145">Click OK.</span></span>
38. <span data-ttu-id="84747-146">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-146">Click Add Attribute.</span></span>
39. <span data-ttu-id="84747-147">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="84747-147">In the Name field, type 'Currency'.</span></span>
40. <span data-ttu-id="84747-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-148">Click OK.</span></span>
41. <span data-ttu-id="84747-149">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-149">Click Add Attribute.</span></span>
42. <span data-ttu-id="84747-150">No campo Nome, digite "Dt".</span><span class="sxs-lookup"><span data-stu-id="84747-150">In the Name field, type 'Dt'.</span></span>
43. <span data-ttu-id="84747-151">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-151">Click OK.</span></span>
44. <span data-ttu-id="84747-152">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-152">Click Add Attribute.</span></span>
45. <span data-ttu-id="84747-153">No campo Nome, digite "Ct".</span><span class="sxs-lookup"><span data-stu-id="84747-153">In the Name field, type 'Ct'.</span></span>
46. <span data-ttu-id="84747-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-154">Click OK.</span></span>
47. <span data-ttu-id="84747-155">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-155">Click Add to open the drop dialog.</span></span>
48. <span data-ttu-id="84747-156">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="84747-156">In the tree, select 'XML\Element'.</span></span>
49. <span data-ttu-id="84747-157">No campo Nome, digite "Dimensões".</span><span class="sxs-lookup"><span data-stu-id="84747-157">In the Name field, type 'Dimensions'.</span></span>
50. <span data-ttu-id="84747-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-158">Click OK.</span></span>
51. <span data-ttu-id="84747-159">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-159">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
52. <span data-ttu-id="84747-160">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="84747-160">Click Add to open the drop dialog.</span></span>
53. <span data-ttu-id="84747-161">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="84747-161">In the tree, select 'XML\Attribute'.</span></span>
54. <span data-ttu-id="84747-162">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="84747-162">In the Name field, type 'Code'.</span></span>
55. <span data-ttu-id="84747-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-163">Click OK.</span></span>
56. <span data-ttu-id="84747-164">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-164">Click Add Attribute.</span></span>
57. <span data-ttu-id="84747-165">No campo Nome, digite "Valor".</span><span class="sxs-lookup"><span data-stu-id="84747-165">In the Name field, type 'Value'.</span></span>
58. <span data-ttu-id="84747-166">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-166">Click OK.</span></span>
59. <span data-ttu-id="84747-167">Clique em Adicionar atributo.</span><span class="sxs-lookup"><span data-stu-id="84747-167">Click Add Attribute.</span></span>
60. <span data-ttu-id="84747-168">No campo Nome, digite "Desc".</span><span class="sxs-lookup"><span data-stu-id="84747-168">In the Name field, type 'Desc'.</span></span>
61. <span data-ttu-id="84747-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="84747-169">Click OK.</span></span>

## <a name="map-report-elements-to-data-sources"></a><span data-ttu-id="84747-170">Mapear elementos de relatório para fontes de dados</span><span class="sxs-lookup"><span data-stu-id="84747-170">Map report elements to data sources</span></span>
1. <span data-ttu-id="84747-171">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="84747-171">Click the Mapping tab.</span></span>
2. <span data-ttu-id="84747-172">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="84747-172">In the tree, expand 'model: Data model Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="84747-173">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-173">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
4. <span data-ttu-id="84747-174">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-174">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
5. <span data-ttu-id="84747-175">Na árvore, expanda "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-175">In the tree, expand 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
6. <span data-ttu-id="84747-176">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Desc: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-176">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Desc: XML Attribute'.</span></span>
7. <span data-ttu-id="84747-177">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Descrição: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-177">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Description: String'.</span></span>
8. <span data-ttu-id="84747-178">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-178">Click Bind.</span></span>
9. <span data-ttu-id="84747-179">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Valor: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-179">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Value: XML Attribute'.</span></span>
10. <span data-ttu-id="84747-180">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Código: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-180">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Code: String'.</span></span>
11. <span data-ttu-id="84747-181">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-181">Click Bind.</span></span>
12. <span data-ttu-id="84747-182">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML\Código: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-182">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element\Code: XML Attribute'.</span></span>
13. <span data-ttu-id="84747-183">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros\Nome: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-183">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list\Name: String'.</span></span>
14. <span data-ttu-id="84747-184">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-184">Click Bind.</span></span>
15. <span data-ttu-id="84747-185">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Dados de dimensões: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-185">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Dimensions data: Record list'.</span></span>
16. <span data-ttu-id="84747-186">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dimensões: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-186">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dimensions: XML Element'.</span></span>
17. <span data-ttu-id="84747-187">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-187">Click Bind.</span></span>
18. <span data-ttu-id="84747-188">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Ct: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-188">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Ct: XML Attribute'.</span></span>
19. <span data-ttu-id="84747-189">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Crédito: Real".</span><span class="sxs-lookup"><span data-stu-id="84747-189">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Credit: Real'.</span></span>
20. <span data-ttu-id="84747-190">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-190">Click Bind.</span></span>
21. <span data-ttu-id="84747-191">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Dt: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-191">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Dt: XML Attribute'.</span></span>
22. <span data-ttu-id="84747-192">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Débito: Real".</span><span class="sxs-lookup"><span data-stu-id="84747-192">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Debit: Real'.</span></span>
23. <span data-ttu-id="84747-193">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-193">Click Bind.</span></span>
24. <span data-ttu-id="84747-194">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Moeda: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-194">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Currency: XML Attribute'.</span></span>
25. <span data-ttu-id="84747-195">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Moeda: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-195">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Currency: String'.</span></span>
26. <span data-ttu-id="84747-196">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-196">Click Bind.</span></span>
27. <span data-ttu-id="84747-197">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Data: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-197">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Date: XML Attribute'.</span></span>
28. <span data-ttu-id="84747-198">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Data: Data".</span><span class="sxs-lookup"><span data-stu-id="84747-198">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Date: Date'.</span></span>
29. <span data-ttu-id="84747-199">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-199">Click Bind.</span></span>
30. <span data-ttu-id="84747-200">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML\Comprovante: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-200">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element\Voucher: XML Attribute'.</span></span>
31. <span data-ttu-id="84747-201">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros\Comprovante: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-201">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list\Voucher: String'.</span></span>
32. <span data-ttu-id="84747-202">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-202">Click Bind.</span></span>
33. <span data-ttu-id="84747-203">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Transação: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-203">In the tree, select 'Root: XML Element\Journal: XML Element\Transaction: XML Element'.</span></span>
34. <span data-ttu-id="84747-204">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Transação: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-204">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Transaction: Record list'.</span></span>
35. <span data-ttu-id="84747-205">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-205">Click Bind.</span></span>
36. <span data-ttu-id="84747-206">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML\Lote: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-206">In the tree, select 'Root: XML Element\Journal: XML Element\Batch: XML Attribute'.</span></span>
37. <span data-ttu-id="84747-207">Na árvore, selecione 'modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros\Lote: Sequência de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="84747-207">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list\Batch: String'.</span></span>
38. <span data-ttu-id="84747-208">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-208">Click Bind.</span></span>
39. <span data-ttu-id="84747-209">Na árvore, selecione "Raiz: Elemento XML\Diário: Elemento XML".</span><span class="sxs-lookup"><span data-stu-id="84747-209">In the tree, select 'Root: XML Element\Journal: XML Element'.</span></span>
40. <span data-ttu-id="84747-210">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Diário: Lista de registros".</span><span class="sxs-lookup"><span data-stu-id="84747-210">In the tree, select 'model: Data model Financial dimensions sample model\Journal: Record list'.</span></span>
41. <span data-ttu-id="84747-211">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-211">Click Bind.</span></span>
42. <span data-ttu-id="84747-212">Na árvore, selecione "Raiz: Elemento XML\Empresa: Atributo XML".</span><span class="sxs-lookup"><span data-stu-id="84747-212">In the tree, select 'Root: XML Element\Company: XML Attribute'.</span></span>
43. <span data-ttu-id="84747-213">Na árvore, selecione "modelo: Modelo de exemplo de dimensões financeiras do modelo de dados\Empresa: Cadeia de caracteres".</span><span class="sxs-lookup"><span data-stu-id="84747-213">In the tree, select 'model: Data model Financial dimensions sample model\Company: String'.</span></span>
44. <span data-ttu-id="84747-214">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="84747-214">Click Bind.</span></span>
45. <span data-ttu-id="84747-215">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="84747-215">Click Save.</span></span>
46. <span data-ttu-id="84747-216">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="84747-216">Close the page.</span></span>

