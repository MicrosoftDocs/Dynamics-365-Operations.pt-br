---
title: ER Usar dimensões financeiras como uma fonte de dados (Parte 1 - Criar modelo de dados)
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 1)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5ecae444d80698c03ac050b49894daa1b090f74
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570183"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1---design-data-model"></a><span data-ttu-id="1e48d-104">ER Usar dimensões financeiras como uma fonte de dados (Parte 1 - Criar modelo de dados)</span><span class="sxs-lookup"><span data-stu-id="1e48d-104">ER Use financial dimensions as a data source (Part 1 - Design data model)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e48d-105">As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="1e48d-105">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="1e48d-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="1e48d-107">Para completar essas etapas, você deve primeiro completar as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="1e48d-107">To complete these steps, you must first complete the steps in the procedure, "Create a configuration provider and mark it as active".</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="1e48d-108">Criar um novo modelo de dados</span><span class="sxs-lookup"><span data-stu-id="1e48d-108">Create a new data model</span></span>
1. <span data-ttu-id="1e48d-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="1e48d-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="1e48d-110">Verifique se o provedor "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="1e48d-110">Make sure that the "Litware, Inc."</span></span> <span data-ttu-id="1e48d-111">está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="1e48d-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="1e48d-112">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="1e48d-112">Click Reporting configurations.</span></span>
3. <span data-ttu-id="1e48d-113">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-113">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="1e48d-114">No campo Nome, digite "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="1e48d-114">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="1e48d-115">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="1e48d-115">Click Create configuration.</span></span>
6. <span data-ttu-id="1e48d-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="1e48d-116">Click Designer.</span></span>
7. <span data-ttu-id="1e48d-117">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-117">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="1e48d-118">No campo Nome, digite "Entrada".</span><span class="sxs-lookup"><span data-stu-id="1e48d-118">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="1e48d-119">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-119">Click Add.</span></span>
10. <span data-ttu-id="1e48d-120">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-120">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="1e48d-121">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-121">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="1e48d-122">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-122">Click Add.</span></span>
    * <span data-ttu-id="1e48d-123">Nós adicionaremos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="1e48d-123">We will add to our model a new record list.</span></span> <span data-ttu-id="1e48d-124">Esta lista exporá (para qualquer relatórios ER usando este modelo como a fonte de dados) as configurações de dimensões financeiras selecionadas.</span><span class="sxs-lookup"><span data-stu-id="1e48d-124">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="1e48d-125">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam a configuração de dimensão.</span><span class="sxs-lookup"><span data-stu-id="1e48d-125">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's setting.</span></span>  
13. <span data-ttu-id="1e48d-126">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-126">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="1e48d-127">No campo Nome, digite "Configurações de dimensão".</span><span class="sxs-lookup"><span data-stu-id="1e48d-127">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="1e48d-128">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-128">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="1e48d-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-129">Click Add.</span></span>
17. <span data-ttu-id="1e48d-130">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-130">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="1e48d-131">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="1e48d-131">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="1e48d-132">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-132">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="1e48d-133">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-133">Click Add.</span></span>
21. <span data-ttu-id="1e48d-134">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-134">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="1e48d-135">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-135">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="1e48d-136">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-136">Click Add.</span></span>
24. <span data-ttu-id="1e48d-137">Na árvore, selecione 'Entrada'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-137">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="1e48d-138">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-138">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="1e48d-139">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="1e48d-139">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="1e48d-140">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-140">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="1e48d-141">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-141">Click Add.</span></span>
29. <span data-ttu-id="1e48d-142">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-142">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="1e48d-143">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="1e48d-143">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="1e48d-144">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-144">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="1e48d-145">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-145">Click Add.</span></span>
33. <span data-ttu-id="1e48d-146">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-146">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="1e48d-147">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-147">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="1e48d-148">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-148">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="1e48d-149">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-149">Click Add.</span></span>
37. <span data-ttu-id="1e48d-150">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-150">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="1e48d-151">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="1e48d-151">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="1e48d-152">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-152">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="1e48d-153">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-153">Click Add.</span></span>
41. <span data-ttu-id="1e48d-154">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-154">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="1e48d-155">No campo Nome, digite "Débito".</span><span class="sxs-lookup"><span data-stu-id="1e48d-155">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="1e48d-156">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-156">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="1e48d-157">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-157">Click Add.</span></span>
45. <span data-ttu-id="1e48d-158">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-158">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="1e48d-159">No campo Nome, digite 'Crédito'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-159">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="1e48d-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-160">Click Add.</span></span>
48. <span data-ttu-id="1e48d-161">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-161">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="1e48d-162">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-162">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="1e48d-163">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-163">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="1e48d-164">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-164">Click Add.</span></span>
52. <span data-ttu-id="1e48d-165">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-165">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="1e48d-166">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="1e48d-166">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="1e48d-167">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-167">Click Add.</span></span>
55. <span data-ttu-id="1e48d-168">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-168">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="1e48d-169">No campo Nome, digite "Dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="1e48d-169">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="1e48d-170">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-170">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="1e48d-171">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-171">Click Add.</span></span>
    * <span data-ttu-id="1e48d-172">Nós adicionamos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="1e48d-172">We added to our model a new record list.</span></span> <span data-ttu-id="1e48d-173">Esta lista exporá (para qualquer ER relatórios usando este modelo como a fonte de dados) os valores de dimensões financeiras selecionados.</span><span class="sxs-lookup"><span data-stu-id="1e48d-173">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="1e48d-174">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="1e48d-174">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension's values.</span></span> <span data-ttu-id="1e48d-175">O nome de dimensões será apresentado também neste registro pois um campo a ser usado, se necessário, para fins de seleção.</span><span class="sxs-lookup"><span data-stu-id="1e48d-175">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="1e48d-176">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-176">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="1e48d-177">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="1e48d-177">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="1e48d-178">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-178">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="1e48d-179">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-179">Click Add.</span></span>
63. <span data-ttu-id="1e48d-180">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-180">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="1e48d-181">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-181">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="1e48d-182">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-182">Click Add.</span></span>
66. <span data-ttu-id="1e48d-183">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e48d-183">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="1e48d-184">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="1e48d-184">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="1e48d-185">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-185">Click Add.</span></span>
69. <span data-ttu-id="1e48d-186">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1e48d-186">Click Save.</span></span>
70. <span data-ttu-id="1e48d-187">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e48d-187">Close the page.</span></span>

![Página do designer de modelo de dados de ER](../media/er-financial-dimensions-guides-data-model.png)



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]