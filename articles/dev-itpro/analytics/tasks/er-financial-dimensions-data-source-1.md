--- 
title: "ER Usar dimensões financeiras como uma fonte de dados (Parte 1 - Criar modelo de dados)"
description: "As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 84f546b73eefe3ead78c6ab3fdbbc05d0db5fef5
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="er-use-financial-dimensions-as-a-data-source-part-1-design-data-model"></a><span data-ttu-id="a6534-103">O ER usa dimensões financeiras como uma fonte de dados (parte 1: Modelo de dados de design)</span><span class="sxs-lookup"><span data-stu-id="a6534-103">ER Use financial dimensions as a data source (Part 1: Design data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6534-104">As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="a6534-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="a6534-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="a6534-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="a6534-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="a6534-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="a6534-107">Criar um novo modelo de dados</span><span class="sxs-lookup"><span data-stu-id="a6534-107">Create a new data model</span></span>
1. <span data-ttu-id="a6534-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="a6534-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="a6534-109">Verifique se o provedor "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="a6534-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="a6534-110">está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="a6534-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="a6534-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="a6534-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="a6534-112">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="a6534-113">No campo Nome, digite "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="a6534-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="a6534-114">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="a6534-114">Click Create configuration.</span></span>
6. <span data-ttu-id="a6534-115">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="a6534-115">Click Designer.</span></span>
7. <span data-ttu-id="a6534-116">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="a6534-117">No campo Nome, digite "Entrada".</span><span class="sxs-lookup"><span data-stu-id="a6534-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="a6534-118">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-118">Click Add.</span></span>
10. <span data-ttu-id="a6534-119">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="a6534-120">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="a6534-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="a6534-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-121">Click Add.</span></span>
    * <span data-ttu-id="a6534-122">Nós adicionaremos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="a6534-122">We will add to our model a new record list.</span></span> <span data-ttu-id="a6534-123">Esta lista exporá (para qualquer relatórios ER usando este modelo como a fonte de dados) as configurações de dimensões financeiras selecionadas.</span><span class="sxs-lookup"><span data-stu-id="a6534-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="a6534-124">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam a configuração de dimensão.</span><span class="sxs-lookup"><span data-stu-id="a6534-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="a6534-125">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="a6534-126">No campo Nome, digite "Configurações de dimensão".</span><span class="sxs-lookup"><span data-stu-id="a6534-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="a6534-127">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="a6534-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="a6534-128">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-128">Click Add.</span></span>
17. <span data-ttu-id="a6534-129">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="a6534-130">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="a6534-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="a6534-131">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="a6534-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="a6534-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-132">Click Add.</span></span>
21. <span data-ttu-id="a6534-133">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="a6534-134">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="a6534-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="a6534-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-135">Click Add.</span></span>
24. <span data-ttu-id="a6534-136">Na árvore, selecione 'Entrada'.</span><span class="sxs-lookup"><span data-stu-id="a6534-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="a6534-137">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="a6534-138">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="a6534-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="a6534-139">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="a6534-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="a6534-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-140">Click Add.</span></span>
29. <span data-ttu-id="a6534-141">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="a6534-142">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="a6534-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="a6534-143">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="a6534-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="a6534-144">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-144">Click Add.</span></span>
33. <span data-ttu-id="a6534-145">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="a6534-146">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="a6534-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="a6534-147">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="a6534-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="a6534-148">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-148">Click Add.</span></span>
37. <span data-ttu-id="a6534-149">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="a6534-150">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="a6534-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="a6534-151">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="a6534-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="a6534-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-152">Click Add.</span></span>
41. <span data-ttu-id="a6534-153">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="a6534-154">No campo Nome, digite "Débito".</span><span class="sxs-lookup"><span data-stu-id="a6534-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="a6534-155">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="a6534-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="a6534-156">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-156">Click Add.</span></span>
45. <span data-ttu-id="a6534-157">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="a6534-158">No campo Nome, digite 'Crédito'.</span><span class="sxs-lookup"><span data-stu-id="a6534-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="a6534-159">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-159">Click Add.</span></span>
48. <span data-ttu-id="a6534-160">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="a6534-161">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="a6534-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="a6534-162">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="a6534-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="a6534-163">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-163">Click Add.</span></span>
52. <span data-ttu-id="a6534-164">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="a6534-165">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="a6534-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="a6534-166">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-166">Click Add.</span></span>
55. <span data-ttu-id="a6534-167">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="a6534-168">No campo Nome, digite "Dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="a6534-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="a6534-169">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="a6534-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="a6534-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-170">Click Add.</span></span>
    * <span data-ttu-id="a6534-171">Nós adicionamos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="a6534-171">We added to our model a new record list.</span></span> <span data-ttu-id="a6534-172">Esta lista exporá (para qualquer ER relatórios usando este modelo como a fonte de dados) os valores de dimensões financeiras selecionados.</span><span class="sxs-lookup"><span data-stu-id="a6534-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="a6534-173">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="a6534-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="a6534-174">O nome de dimensões será apresentado também neste registro pois um campo a ser usado, se necessário, para fins de seleção.</span><span class="sxs-lookup"><span data-stu-id="a6534-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="a6534-175">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="a6534-176">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="a6534-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="a6534-177">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="a6534-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="a6534-178">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-178">Click Add.</span></span>
63. <span data-ttu-id="a6534-179">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="a6534-180">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="a6534-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="a6534-181">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-181">Click Add.</span></span>
66. <span data-ttu-id="a6534-182">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a6534-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="a6534-183">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="a6534-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="a6534-184">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="a6534-184">Click Add.</span></span>
69. <span data-ttu-id="a6534-185">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="a6534-185">Click Save.</span></span>
70. <span data-ttu-id="a6534-186">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a6534-186">Close the page.</span></span>


