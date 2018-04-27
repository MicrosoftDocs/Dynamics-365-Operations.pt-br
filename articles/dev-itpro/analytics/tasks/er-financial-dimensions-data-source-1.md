--- 
title: "Criar modelo de dados para usar dimensões financeiras como uma fonte de dados"
description: "As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 3e55eedba1955ae79733afee1a0b3c7072147bb5
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="design-data-model-to-use-financial-dimensions-as-a-data-source"></a><span data-ttu-id="465c7-103">Criar modelo de dados para usar dimensões financeiras como uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="465c7-103">Design data model to use financial dimensions as a data source</span></span> 

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="465c7-104">As etapas a seguir explicam como um administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="465c7-104">The following steps explain how either a system administrator or electronic reporting developer can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="465c7-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="465c7-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="465c7-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="465c7-106">To complete these steps, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>


## <a name="create-a-new-data-model"></a><span data-ttu-id="465c7-107">Criar um novo modelo de dados</span><span class="sxs-lookup"><span data-stu-id="465c7-107">Create a new data model</span></span>
1. <span data-ttu-id="465c7-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="465c7-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="465c7-109">Verifique se o provedor "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="465c7-109">Make sure that the “Litware, Inc.”</span></span> <span data-ttu-id="465c7-110">está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="465c7-110">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="465c7-111">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="465c7-111">Click Reporting configurations.</span></span>
3. <span data-ttu-id="465c7-112">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-112">Click Create configuration to open the drop dialog.</span></span>
4. <span data-ttu-id="465c7-113">No campo Nome, digite "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="465c7-113">In the Name field, type 'Financial dimensions sample model'.</span></span>
5. <span data-ttu-id="465c7-114">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="465c7-114">Click Create configuration.</span></span>
6. <span data-ttu-id="465c7-115">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="465c7-115">Click Designer.</span></span>
7. <span data-ttu-id="465c7-116">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-116">Click New to open the drop dialog.</span></span>
8. <span data-ttu-id="465c7-117">No campo Nome, digite "Entrada".</span><span class="sxs-lookup"><span data-stu-id="465c7-117">In the Name field, type 'Entry'.</span></span>
9. <span data-ttu-id="465c7-118">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-118">Click Add.</span></span>
10. <span data-ttu-id="465c7-119">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-119">Click New to open the drop dialog.</span></span>
11. <span data-ttu-id="465c7-120">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="465c7-120">In the Name field, type 'Company'.</span></span>
12. <span data-ttu-id="465c7-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-121">Click Add.</span></span>
    * <span data-ttu-id="465c7-122">Nós adicionaremos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="465c7-122">We will add to our model a new record list.</span></span> <span data-ttu-id="465c7-123">Esta lista exporá (para qualquer relatórios ER usando este modelo como a fonte de dados) as configurações de dimensões financeiras selecionadas.</span><span class="sxs-lookup"><span data-stu-id="465c7-123">This list will expose (for any ER reports using this model as data source) the settings of selected financial dimensions.</span></span> <span data-ttu-id="465c7-124">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam a configuração de dimensão.</span><span class="sxs-lookup"><span data-stu-id="465c7-124">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s setting.</span></span>  
13. <span data-ttu-id="465c7-125">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-125">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="465c7-126">No campo Nome, digite "Configurações de dimensão".</span><span class="sxs-lookup"><span data-stu-id="465c7-126">In the Name field, type 'Dimensions setting'.</span></span>
15. <span data-ttu-id="465c7-127">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="465c7-127">In the Item type field, select 'Record list'.</span></span>
16. <span data-ttu-id="465c7-128">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-128">Click Add.</span></span>
17. <span data-ttu-id="465c7-129">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-129">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="465c7-130">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="465c7-130">In the Name field, type 'Code'.</span></span>
19. <span data-ttu-id="465c7-131">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="465c7-131">In the Item type field, select 'String'.</span></span>
20. <span data-ttu-id="465c7-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-132">Click Add.</span></span>
21. <span data-ttu-id="465c7-133">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-133">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="465c7-134">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="465c7-134">In the Name field, type 'Name'.</span></span>
23. <span data-ttu-id="465c7-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-135">Click Add.</span></span>
24. <span data-ttu-id="465c7-136">Na árvore, selecione 'Entrada'.</span><span class="sxs-lookup"><span data-stu-id="465c7-136">In the tree, select 'Entry'.</span></span>
25. <span data-ttu-id="465c7-137">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-137">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="465c7-138">No campo Nome, digite "Diário".</span><span class="sxs-lookup"><span data-stu-id="465c7-138">In the Name field, type 'Journal'.</span></span>
27. <span data-ttu-id="465c7-139">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="465c7-139">In the Item type field, select 'Record list'.</span></span>
28. <span data-ttu-id="465c7-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-140">Click Add.</span></span>
29. <span data-ttu-id="465c7-141">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-141">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="465c7-142">No campo Nome, digite "Lote".</span><span class="sxs-lookup"><span data-stu-id="465c7-142">In the Name field, type 'Batch'.</span></span>
31. <span data-ttu-id="465c7-143">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="465c7-143">In the Item type field, select 'String'.</span></span>
32. <span data-ttu-id="465c7-144">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-144">Click Add.</span></span>
33. <span data-ttu-id="465c7-145">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-145">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="465c7-146">No campo Nome, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="465c7-146">In the Name field, type 'Transaction'.</span></span>
35. <span data-ttu-id="465c7-147">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="465c7-147">In the Item type field, select 'Record list'.</span></span>
36. <span data-ttu-id="465c7-148">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-148">Click Add.</span></span>
37. <span data-ttu-id="465c7-149">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-149">Click New to open the drop dialog.</span></span>
38. <span data-ttu-id="465c7-150">No campo Nome, digite "Data".</span><span class="sxs-lookup"><span data-stu-id="465c7-150">In the Name field, type 'Date'.</span></span>
39. <span data-ttu-id="465c7-151">No campo Tipo de item, selecione 'Data'.</span><span class="sxs-lookup"><span data-stu-id="465c7-151">In the Item type field, select 'Date'.</span></span>
40. <span data-ttu-id="465c7-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-152">Click Add.</span></span>
41. <span data-ttu-id="465c7-153">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-153">Click New to open the drop dialog.</span></span>
42. <span data-ttu-id="465c7-154">No campo Nome, digite "Débito".</span><span class="sxs-lookup"><span data-stu-id="465c7-154">In the Name field, type 'Debit'.</span></span>
43. <span data-ttu-id="465c7-155">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="465c7-155">In the Item type field, select 'Real'.</span></span>
44. <span data-ttu-id="465c7-156">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-156">Click Add.</span></span>
45. <span data-ttu-id="465c7-157">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-157">Click New to open the drop dialog.</span></span>
46. <span data-ttu-id="465c7-158">No campo Nome, digite 'Crédito'.</span><span class="sxs-lookup"><span data-stu-id="465c7-158">In the Name field, type 'Credit'.</span></span>
47. <span data-ttu-id="465c7-159">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-159">Click Add.</span></span>
48. <span data-ttu-id="465c7-160">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-160">Click New to open the drop dialog.</span></span>
49. <span data-ttu-id="465c7-161">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="465c7-161">In the Name field, type 'Currency'.</span></span>
50. <span data-ttu-id="465c7-162">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="465c7-162">In the Item type field, select 'String'.</span></span>
51. <span data-ttu-id="465c7-163">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-163">Click Add.</span></span>
52. <span data-ttu-id="465c7-164">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-164">Click New to open the drop dialog.</span></span>
53. <span data-ttu-id="465c7-165">No campo Nome, digite "Comprovante".</span><span class="sxs-lookup"><span data-stu-id="465c7-165">In the Name field, type 'Voucher'.</span></span>
54. <span data-ttu-id="465c7-166">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-166">Click Add.</span></span>
55. <span data-ttu-id="465c7-167">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-167">Click New to open the drop dialog.</span></span>
56. <span data-ttu-id="465c7-168">No campo Nome, digite "Dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="465c7-168">In the Name field, type 'Dimensions data'.</span></span>
57. <span data-ttu-id="465c7-169">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="465c7-169">In the Item type field, select 'Record list'.</span></span>
58. <span data-ttu-id="465c7-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-170">Click Add.</span></span>
    * <span data-ttu-id="465c7-171">Nós adicionamos nosso modelo a uma lista do novo registro.</span><span class="sxs-lookup"><span data-stu-id="465c7-171">We added to our model a new record list.</span></span> <span data-ttu-id="465c7-172">Esta lista exporá (para qualquer ER relatórios usando este modelo como a fonte de dados) os valores de dimensões financeiras selecionados.</span><span class="sxs-lookup"><span data-stu-id="465c7-172">This list will expose (for any ER reports using this model as data source) the values of selected financial dimensions.</span></span> <span data-ttu-id="465c7-173">Cada dimensão financeira será exibida nesta lista como um registro com os campos apropriados que representam os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="465c7-173">Each financial dimension will be presented in this list as a record with appropriate fields representing dimension’s values.</span></span> <span data-ttu-id="465c7-174">O nome de dimensões será apresentado também neste registro pois um campo a ser usado, se necessário, para fins de seleção.</span><span class="sxs-lookup"><span data-stu-id="465c7-174">Dimension name will be also presented in this record as a field to be used, if needed, for selection purposes.</span></span>  
59. <span data-ttu-id="465c7-175">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-175">Click New to open the drop dialog.</span></span>
60. <span data-ttu-id="465c7-176">No campo Nome, digite "Código".</span><span class="sxs-lookup"><span data-stu-id="465c7-176">In the Name field, type 'Code'.</span></span>
61. <span data-ttu-id="465c7-177">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="465c7-177">In the Item type field, select 'String'.</span></span>
62. <span data-ttu-id="465c7-178">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-178">Click Add.</span></span>
63. <span data-ttu-id="465c7-179">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-179">Click New to open the drop dialog.</span></span>
64. <span data-ttu-id="465c7-180">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="465c7-180">In the Name field, type 'Description'.</span></span>
65. <span data-ttu-id="465c7-181">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-181">Click Add.</span></span>
66. <span data-ttu-id="465c7-182">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="465c7-182">Click New to open the drop dialog.</span></span>
67. <span data-ttu-id="465c7-183">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="465c7-183">In the Name field, type 'Name'.</span></span>
68. <span data-ttu-id="465c7-184">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="465c7-184">Click Add.</span></span>
69. <span data-ttu-id="465c7-185">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="465c7-185">Click Save.</span></span>
70. <span data-ttu-id="465c7-186">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="465c7-186">Close the page.</span></span>


