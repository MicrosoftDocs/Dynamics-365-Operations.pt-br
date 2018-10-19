--- 
title: "ER Criar uma configuração de formato (Novembro de 2016)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 803ed4a1018d344f1b40fa1f2338fc066e784c3c
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="er-create-a-format-configuration-november-2016"></a><span data-ttu-id="f5bc2-103">ER Criar uma configuração de formato (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="f5bc2-103">ER Create a format configuration (November 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f5bc2-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="f5bc2-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="f5bc2-105">Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="f5bc2-106">Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "mapear modelo para as fontes de dados selecionadas".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="f5bc2-107">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="f5bc2-107">Create a new format configuration</span></span>
1. <span data-ttu-id="f5bc2-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f5bc2-109">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="f5bc2-110">Na árvore, selecione 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="f5bc2-111">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="f5bc2-112">No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="f5bc2-113">No campo Nome, digite 'BACS (Reino Unido fictício)'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="f5bc2-114">BACS (Reino Unido fictício)</span><span class="sxs-lookup"><span data-stu-id="f5bc2-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="f5bc2-115">No campo Descrição, digite 'Formato de pagamento de fornecedor BACS (Reino Unido fictício)'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="f5bc2-116">Formato de pagamento de fornecedor BACS (Reino Unido fictício)</span><span class="sxs-lookup"><span data-stu-id="f5bc2-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="f5bc2-117">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="f5bc2-118">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="f5bc2-119">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="f5bc2-120">Um formato específico de documento eletrônico pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="f5bc2-121">Deixe este campo em branco se desejar selecionar um formato durante a execução.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="f5bc2-122">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="f5bc2-123">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-123">Click Create configuration.</span></span>
    * <span data-ttu-id="f5bc2-124">Uma nova configuração foi criada.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-124">A new configuration has been created.</span></span> <span data-ttu-id="f5bc2-125">A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="f5bc2-126">Projetar formato de documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="f5bc2-126">Design format of electronic document</span></span>
1. <span data-ttu-id="f5bc2-127">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-127">Click Designer.</span></span>
2. <span data-ttu-id="f5bc2-128">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="f5bc2-129">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="f5bc2-130">No campo Nome, digite 'Xml'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="f5bc2-131">Xml</span><span class="sxs-lookup"><span data-stu-id="f5bc2-131">Xml</span></span>  
5. <span data-ttu-id="f5bc2-132">No campo Codificação, digite 'UTF-8'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="f5bc2-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="f5bc2-133">UTF-8</span></span>  
6. <span data-ttu-id="f5bc2-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-134">Click OK.</span></span>
7. <span data-ttu-id="f5bc2-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="f5bc2-136">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="f5bc2-137">No campo Nome, digite 'Mensagem'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="f5bc2-138">Mensagem</span><span class="sxs-lookup"><span data-stu-id="f5bc2-138">Message</span></span>  
10. <span data-ttu-id="f5bc2-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-139">Click OK.</span></span>
11. <span data-ttu-id="f5bc2-140">Na árvore, selecione "Xml\Mensagem".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="f5bc2-141">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-141">Click Add Element.</span></span>
13. <span data-ttu-id="f5bc2-142">No campo Nome, digite 'ProcessingDate'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="f5bc2-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="f5bc2-143">ProcessingDate</span></span>  
14. <span data-ttu-id="f5bc2-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-144">Click OK.</span></span>
15. <span data-ttu-id="f5bc2-145">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-145">Click Add Element.</span></span>
16. <span data-ttu-id="f5bc2-146">No campo Nome, digite 'MessageId'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="f5bc2-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="f5bc2-147">MessageId</span></span>  
17. <span data-ttu-id="f5bc2-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-148">Click OK.</span></span>
18. <span data-ttu-id="f5bc2-149">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-149">Click Add Element.</span></span>
19. <span data-ttu-id="f5bc2-150">No campo Nome, digite 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="f5bc2-151">Pagamentos</span><span class="sxs-lookup"><span data-stu-id="f5bc2-151">Payments</span></span>  
20. <span data-ttu-id="f5bc2-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-152">Click OK.</span></span>
21. <span data-ttu-id="f5bc2-153">Na árvore, selecione "Xml\Mensagem\Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="f5bc2-154">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-154">Click Add Element.</span></span>
23. <span data-ttu-id="f5bc2-155">No campo Nome, digite 'Item'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="f5bc2-156">Item</span><span class="sxs-lookup"><span data-stu-id="f5bc2-156">Item</span></span>  
24. <span data-ttu-id="f5bc2-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-157">Click OK.</span></span>
25. <span data-ttu-id="f5bc2-158">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="f5bc2-159">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="f5bc2-160">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="f5bc2-161">No campo Nome, digite 'Id'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="f5bc2-162">ID</span><span class="sxs-lookup"><span data-stu-id="f5bc2-162">Id</span></span>  
29. <span data-ttu-id="f5bc2-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-163">Click OK.</span></span>
30. <span data-ttu-id="f5bc2-164">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="f5bc2-165">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="f5bc2-166">No campo Nome, digite 'Fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="f5bc2-167">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="f5bc2-167">Vendor</span></span>  
33. <span data-ttu-id="f5bc2-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-168">Click OK.</span></span>
34. <span data-ttu-id="f5bc2-169">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="f5bc2-170">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-170">Click Add Element.</span></span>
36. <span data-ttu-id="f5bc2-171">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="f5bc2-172">Nome</span><span class="sxs-lookup"><span data-stu-id="f5bc2-172">Name</span></span>  
37. <span data-ttu-id="f5bc2-173">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-173">Click OK.</span></span>
38. <span data-ttu-id="f5bc2-174">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-174">Click Add Element.</span></span>
39. <span data-ttu-id="f5bc2-175">No campo Nome, digite 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="f5bc2-176">Banco</span><span class="sxs-lookup"><span data-stu-id="f5bc2-176">Bank</span></span>  
40. <span data-ttu-id="f5bc2-177">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-177">Click OK.</span></span>
41. <span data-ttu-id="f5bc2-178">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="f5bc2-179">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-179">Click Add Element.</span></span>
43. <span data-ttu-id="f5bc2-180">No campo Nome, digite 'Número Identificador do banco'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="f5bc2-181">Número identificador do banco</span><span class="sxs-lookup"><span data-stu-id="f5bc2-181">RoutingNumber</span></span>  
44. <span data-ttu-id="f5bc2-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-182">Click OK.</span></span>
45. <span data-ttu-id="f5bc2-183">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-183">Click Add Element.</span></span>
46. <span data-ttu-id="f5bc2-184">No campo Nome, digite 'NúmeroConta'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="f5bc2-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="f5bc2-185">AccountNumber</span></span>  
47. <span data-ttu-id="f5bc2-186">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-186">Click OK.</span></span>
48. <span data-ttu-id="f5bc2-187">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="f5bc2-188">Clique em Copiar.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-188">Click Copy.</span></span>
50. <span data-ttu-id="f5bc2-189">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="f5bc2-190">Clique em Colar.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-190">Click Paste.</span></span>
52. <span data-ttu-id="f5bc2-191">No campo Nome, digite 'Pagador'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="f5bc2-192">Pagador</span><span class="sxs-lookup"><span data-stu-id="f5bc2-192">Payer</span></span>  
53. <span data-ttu-id="f5bc2-193">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="f5bc2-194">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-194">Click Add Element.</span></span>
55. <span data-ttu-id="f5bc2-195">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="f5bc2-196">Moeda</span><span class="sxs-lookup"><span data-stu-id="f5bc2-196">Currency</span></span>  
56. <span data-ttu-id="f5bc2-197">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-197">Click OK.</span></span>
57. <span data-ttu-id="f5bc2-198">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-198">Click Add Element.</span></span>
58. <span data-ttu-id="f5bc2-199">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="f5bc2-200">descrição</span><span class="sxs-lookup"><span data-stu-id="f5bc2-200">Description</span></span>  
59. <span data-ttu-id="f5bc2-201">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-201">Click OK.</span></span>
60. <span data-ttu-id="f5bc2-202">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-202">Click Add Element.</span></span>
61. <span data-ttu-id="f5bc2-203">No campo Nome, digite 'TransDate'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="f5bc2-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="f5bc2-204">TransDate</span></span>  
62. <span data-ttu-id="f5bc2-205">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-205">Click OK.</span></span>
63. <span data-ttu-id="f5bc2-206">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-206">Click Add Element.</span></span>
64. <span data-ttu-id="f5bc2-207">No campo Nome, digite 'Valor'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="f5bc2-208">Valor</span><span class="sxs-lookup"><span data-stu-id="f5bc2-208">Amount</span></span>  
65. <span data-ttu-id="f5bc2-209">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="f5bc2-210">Preparar os componentes do formato para mapeamento aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="f5bc2-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="f5bc2-211">Na árvore, selecione "Xml\Mensagem\ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="f5bc2-212">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="f5bc2-213">Na árvore, selecione "Texto\DateTime"</span><span class="sxs-lookup"><span data-stu-id="f5bc2-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="f5bc2-214">No campo Formato, digite 'aaaa-MM-dd'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f5bc2-215">dd-MM-aa</span><span class="sxs-lookup"><span data-stu-id="f5bc2-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="f5bc2-216">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-216">Click OK.</span></span>
6. <span data-ttu-id="f5bc2-217">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\TransDate".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="f5bc2-218">Clique em Adicionar DateTime.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="f5bc2-219">No campo Formato, digite 'aaaa-MM-dd'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="f5bc2-220">dd-MM-aa</span><span class="sxs-lookup"><span data-stu-id="f5bc2-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="f5bc2-221">No campo DateTime, selecione "Data".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="f5bc2-222">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-222">Click OK.</span></span>
11. <span data-ttu-id="f5bc2-223">Na árvore, selecione "Xml\Mensagem\MessageId".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="f5bc2-224">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="f5bc2-225">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="f5bc2-226">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-226">Click OK.</span></span>
15. <span data-ttu-id="f5bc2-227">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="f5bc2-228">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-228">Click Add String.</span></span>
17. <span data-ttu-id="f5bc2-229">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-229">Click OK.</span></span>
18. <span data-ttu-id="f5bc2-230">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="f5bc2-231">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-231">Click Add String.</span></span>
20. <span data-ttu-id="f5bc2-232">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-232">Click OK.</span></span>
21. <span data-ttu-id="f5bc2-233">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="f5bc2-234">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-234">Click Add String.</span></span>
23. <span data-ttu-id="f5bc2-235">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-235">Click OK.</span></span>
24. <span data-ttu-id="f5bc2-236">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Nome".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="f5bc2-237">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-237">Click Add String.</span></span>
26. <span data-ttu-id="f5bc2-238">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-238">Click OK.</span></span>
27. <span data-ttu-id="f5bc2-239">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="f5bc2-240">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-240">Click Add String.</span></span>
29. <span data-ttu-id="f5bc2-241">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-241">Click OK.</span></span>
30. <span data-ttu-id="f5bc2-242">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="f5bc2-243">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-243">Click Add String.</span></span>
32. <span data-ttu-id="f5bc2-244">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-244">Click OK.</span></span>
33. <span data-ttu-id="f5bc2-245">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Moeda".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="f5bc2-246">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-246">Click Add String.</span></span>
35. <span data-ttu-id="f5bc2-247">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-247">Click OK.</span></span>
36. <span data-ttu-id="f5bc2-248">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Descrição".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="f5bc2-249">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-249">Click Add String.</span></span>
38. <span data-ttu-id="f5bc2-250">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-250">Click OK.</span></span>
39. <span data-ttu-id="f5bc2-251">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Valor".</span><span class="sxs-lookup"><span data-stu-id="f5bc2-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="f5bc2-252">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="f5bc2-252">Click Add String.</span></span>
41. <span data-ttu-id="f5bc2-253">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-253">Click OK.</span></span>
42. <span data-ttu-id="f5bc2-254">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-254">Click Save.</span></span>
43. <span data-ttu-id="f5bc2-255">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f5bc2-255">Close the page.</span></span>


