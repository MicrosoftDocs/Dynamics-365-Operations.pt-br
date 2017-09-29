--- 
title: "Criar uma configuração de formato para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 04817d1f1851e43679995641e8b0ff99edaa83ad
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="fade3-103">Criar uma configuração de formato para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="fade3-103">Create a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fade3-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar uma configuração de formato para Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="fade3-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can create a format configuration for Electronic reporting (ER).</span></span> <span data-ttu-id="fade3-105">Esta configuração de formato irá definir o formato de documentos eletrônicos que são usados para processar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="fade3-105">This format configuration will define the format of electronic documents that are used for processing payments.</span></span> <span data-ttu-id="fade3-106">Neste exemplo, você criará uma configuração de formato para a empresa de exemplo, Litware, Inc. Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento "mapear modelo para as fontes de dados selecionadas".</span><span class="sxs-lookup"><span data-stu-id="fade3-106">In this example, you will create a format configuration for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Map model to selected datasources” procedure.</span></span>


## <a name="create-a-new-format-configuration"></a><span data-ttu-id="fade3-107">Criar uma nova configuração de formato</span><span class="sxs-lookup"><span data-stu-id="fade3-107">Create a new format configuration</span></span>
1. <span data-ttu-id="fade3-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fade3-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="fade3-109">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="fade3-109">Click Reporting configurations.</span></span>
3. <span data-ttu-id="fade3-110">Na árvore, selecione 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="fade3-110">In the tree, select 'Payments (simplified model)'.</span></span>
4. <span data-ttu-id="fade3-111">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-111">Click Create configuration to open the drop dialog.</span></span>
5. <span data-ttu-id="fade3-112">No campo Novo, insira 'Formato baseado no modelo de dados PaymentModel'.</span><span class="sxs-lookup"><span data-stu-id="fade3-112">In the New field, enter 'Format based on data model PaymentModel'.</span></span>
6. <span data-ttu-id="fade3-113">No campo Nome, digite 'BACS (Reino Unido fictício)'.</span><span class="sxs-lookup"><span data-stu-id="fade3-113">In the Name field, type 'BACS (UK fictitious)'.</span></span>
    * <span data-ttu-id="fade3-114">BACS (Reino Unido fictício)</span><span class="sxs-lookup"><span data-stu-id="fade3-114">BACS (UK fictitious)</span></span>  
7. <span data-ttu-id="fade3-115">No campo Descrição, digite 'Formato de pagamento de fornecedor BACS (Reino Unido fictício)'.</span><span class="sxs-lookup"><span data-stu-id="fade3-115">In the Description field, type 'BACS vendor payment format (UK fictitious)'.</span></span>
    * <span data-ttu-id="fade3-116">Formato de pagamento de fornecedor BACS (Reino Unido fictício)</span><span class="sxs-lookup"><span data-stu-id="fade3-116">BACS vendor payment format (UK fictitious)</span></span>  
    * <span data-ttu-id="fade3-117">O provedor de configuração ativo é automaticamente inserido aqui.</span><span class="sxs-lookup"><span data-stu-id="fade3-117">The active configuration provider is automatically entered here.</span></span> <span data-ttu-id="fade3-118">Este provedor será capaz de manter essa configuração.</span><span class="sxs-lookup"><span data-stu-id="fade3-118">This provider will be able to maintain this configuration.</span></span> <span data-ttu-id="fade3-119">Outros provedores podem usar esta configuração, mas não poderão mantê-la.</span><span class="sxs-lookup"><span data-stu-id="fade3-119">Other providers can use this configuration, but will not be able to maintain it.</span></span>  
    * <span data-ttu-id="fade3-120">Um formato específico de documento eletrônico pode ser definido.</span><span class="sxs-lookup"><span data-stu-id="fade3-120">A particular format of electronic document can be defined.</span></span> <span data-ttu-id="fade3-121">Deixe este campo em branco se desejar selecionar um formato durante a execução.</span><span class="sxs-lookup"><span data-stu-id="fade3-121">Leave this field blank if you want to select a format at run-time.</span></span>  
8. <span data-ttu-id="fade3-122">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="fade3-122">In the Data model definition field, enter or select a value.</span></span>
9. <span data-ttu-id="fade3-123">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="fade3-123">Click Create configuration.</span></span>
    * <span data-ttu-id="fade3-124">Uma nova configuração foi criada.</span><span class="sxs-lookup"><span data-stu-id="fade3-124">A new configuration has been created.</span></span> <span data-ttu-id="fade3-125">A versão de rascunho pode ser usada para armazenar o formato de design para gerenciar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="fade3-125">The draft version can be used to store the design format for managing electronic documents.</span></span>  

## <a name="design-format-of-electronic-document"></a><span data-ttu-id="fade3-126">Projetar formato de documento eletrônico</span><span class="sxs-lookup"><span data-stu-id="fade3-126">Design format of electronic document</span></span>
1. <span data-ttu-id="fade3-127">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="fade3-127">Click Designer.</span></span>
2. <span data-ttu-id="fade3-128">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-128">Click Add root to open the drop dialog.</span></span>
3. <span data-ttu-id="fade3-129">Na árvore, selecione 'Comum\Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="fade3-129">In the tree, select 'Common\File'.</span></span>
4. <span data-ttu-id="fade3-130">No campo Nome, digite 'Xml'.</span><span class="sxs-lookup"><span data-stu-id="fade3-130">In the Name field, type 'Xml'.</span></span>
    * <span data-ttu-id="fade3-131">Xml</span><span class="sxs-lookup"><span data-stu-id="fade3-131">Xml</span></span>  
5. <span data-ttu-id="fade3-132">No campo Codificação, digite 'UTF-8'.</span><span class="sxs-lookup"><span data-stu-id="fade3-132">In the Encoding field, type 'UTF-8'.</span></span>
    * <span data-ttu-id="fade3-133">UTF-8</span><span class="sxs-lookup"><span data-stu-id="fade3-133">UTF-8</span></span>  
6. <span data-ttu-id="fade3-134">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-134">Click OK.</span></span>
7. <span data-ttu-id="fade3-135">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-135">Click Add to open the drop dialog.</span></span>
8. <span data-ttu-id="fade3-136">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="fade3-136">In the tree, select 'XML\Element'.</span></span>
9. <span data-ttu-id="fade3-137">No campo Nome, digite 'Mensagem'.</span><span class="sxs-lookup"><span data-stu-id="fade3-137">In the Name field, type 'Message'.</span></span>
    * <span data-ttu-id="fade3-138">Mensagem</span><span class="sxs-lookup"><span data-stu-id="fade3-138">Message</span></span>  
10. <span data-ttu-id="fade3-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-139">Click OK.</span></span>
11. <span data-ttu-id="fade3-140">Na árvore, selecione "Xml\Mensagem".</span><span class="sxs-lookup"><span data-stu-id="fade3-140">In the tree, select 'Xml\Message'.</span></span>
12. <span data-ttu-id="fade3-141">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-141">Click Add Element.</span></span>
13. <span data-ttu-id="fade3-142">No campo Nome, digite 'ProcessingDate'.</span><span class="sxs-lookup"><span data-stu-id="fade3-142">In the Name field, type 'ProcessingDate'.</span></span>
    * <span data-ttu-id="fade3-143">ProcessingDate</span><span class="sxs-lookup"><span data-stu-id="fade3-143">ProcessingDate</span></span>  
14. <span data-ttu-id="fade3-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-144">Click OK.</span></span>
15. <span data-ttu-id="fade3-145">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-145">Click Add Element.</span></span>
16. <span data-ttu-id="fade3-146">No campo Nome, digite 'MessageId'.</span><span class="sxs-lookup"><span data-stu-id="fade3-146">In the Name field, type 'MessageId'.</span></span>
    * <span data-ttu-id="fade3-147">MessageId</span><span class="sxs-lookup"><span data-stu-id="fade3-147">MessageId</span></span>  
17. <span data-ttu-id="fade3-148">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-148">Click OK.</span></span>
18. <span data-ttu-id="fade3-149">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-149">Click Add Element.</span></span>
19. <span data-ttu-id="fade3-150">No campo Nome, digite 'Pagamentos'.</span><span class="sxs-lookup"><span data-stu-id="fade3-150">In the Name field, type 'Payments'.</span></span>
    * <span data-ttu-id="fade3-151">Pagamentos</span><span class="sxs-lookup"><span data-stu-id="fade3-151">Payments</span></span>  
20. <span data-ttu-id="fade3-152">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-152">Click OK.</span></span>
21. <span data-ttu-id="fade3-153">Na árvore, selecione "Xml\Mensagem\Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="fade3-153">In the tree, select 'Xml\Message\Payments'.</span></span>
22. <span data-ttu-id="fade3-154">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-154">Click Add Element.</span></span>
23. <span data-ttu-id="fade3-155">No campo Nome, digite 'Item'.</span><span class="sxs-lookup"><span data-stu-id="fade3-155">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="fade3-156">Item</span><span class="sxs-lookup"><span data-stu-id="fade3-156">Item</span></span>  
24. <span data-ttu-id="fade3-157">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-157">Click OK.</span></span>
25. <span data-ttu-id="fade3-158">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="fade3-158">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
26. <span data-ttu-id="fade3-159">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-159">Click Add to open the drop dialog.</span></span>
27. <span data-ttu-id="fade3-160">Na árvore, selecione 'XML\Atributo'.</span><span class="sxs-lookup"><span data-stu-id="fade3-160">In the tree, select 'XML\Attribute'.</span></span>
28. <span data-ttu-id="fade3-161">No campo Nome, digite 'Id'.</span><span class="sxs-lookup"><span data-stu-id="fade3-161">In the Name field, type 'Id'.</span></span>
    * <span data-ttu-id="fade3-162">ID</span><span class="sxs-lookup"><span data-stu-id="fade3-162">Id</span></span>  
29. <span data-ttu-id="fade3-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-163">Click OK.</span></span>
30. <span data-ttu-id="fade3-164">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-164">Click Add to open the drop dialog.</span></span>
31. <span data-ttu-id="fade3-165">Na árvore, selecione 'XML\Elemento'.</span><span class="sxs-lookup"><span data-stu-id="fade3-165">In the tree, select 'XML\Element'.</span></span>
32. <span data-ttu-id="fade3-166">No campo Nome, digite 'Fornecedor'.</span><span class="sxs-lookup"><span data-stu-id="fade3-166">In the Name field, type 'Vendor'.</span></span>
    * <span data-ttu-id="fade3-167">Fornecedor</span><span class="sxs-lookup"><span data-stu-id="fade3-167">Vendor</span></span>  
33. <span data-ttu-id="fade3-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-168">Click OK.</span></span>
34. <span data-ttu-id="fade3-169">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".</span><span class="sxs-lookup"><span data-stu-id="fade3-169">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
35. <span data-ttu-id="fade3-170">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-170">Click Add Element.</span></span>
36. <span data-ttu-id="fade3-171">No campo Nome, digite 'Nome'.</span><span class="sxs-lookup"><span data-stu-id="fade3-171">In the Name field, type 'Name'.</span></span>
    * <span data-ttu-id="fade3-172">Nome</span><span class="sxs-lookup"><span data-stu-id="fade3-172">Name</span></span>  
37. <span data-ttu-id="fade3-173">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-173">Click OK.</span></span>
38. <span data-ttu-id="fade3-174">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-174">Click Add Element.</span></span>
39. <span data-ttu-id="fade3-175">No campo Nome, digite 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="fade3-175">In the Name field, type 'Bank'.</span></span>
    * <span data-ttu-id="fade3-176">Banco</span><span class="sxs-lookup"><span data-stu-id="fade3-176">Bank</span></span>  
40. <span data-ttu-id="fade3-177">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-177">Click OK.</span></span>
41. <span data-ttu-id="fade3-178">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco".</span><span class="sxs-lookup"><span data-stu-id="fade3-178">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank'.</span></span>
42. <span data-ttu-id="fade3-179">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-179">Click Add Element.</span></span>
43. <span data-ttu-id="fade3-180">No campo Nome, digite 'Número Identificador do banco'.</span><span class="sxs-lookup"><span data-stu-id="fade3-180">In the Name field, type 'RoutingNumber'.</span></span>
    * <span data-ttu-id="fade3-181">Número identificador do banco</span><span class="sxs-lookup"><span data-stu-id="fade3-181">RoutingNumber</span></span>  
44. <span data-ttu-id="fade3-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-182">Click OK.</span></span>
45. <span data-ttu-id="fade3-183">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-183">Click Add Element.</span></span>
46. <span data-ttu-id="fade3-184">No campo Nome, digite 'NúmeroConta'.</span><span class="sxs-lookup"><span data-stu-id="fade3-184">In the Name field, type 'AccountNumber'.</span></span>
    * <span data-ttu-id="fade3-185">AccountNumber</span><span class="sxs-lookup"><span data-stu-id="fade3-185">AccountNumber</span></span>  
47. <span data-ttu-id="fade3-186">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-186">Click OK.</span></span>
48. <span data-ttu-id="fade3-187">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor".</span><span class="sxs-lookup"><span data-stu-id="fade3-187">In the tree, select 'Xml\Message\Payments\Item\Vendor'.</span></span>
49. <span data-ttu-id="fade3-188">Clique em Copiar.</span><span class="sxs-lookup"><span data-stu-id="fade3-188">Click Copy.</span></span>
50. <span data-ttu-id="fade3-189">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="fade3-189">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
51. <span data-ttu-id="fade3-190">Clique em Colar.</span><span class="sxs-lookup"><span data-stu-id="fade3-190">Click Paste.</span></span>
52. <span data-ttu-id="fade3-191">No campo Nome, digite 'Pagador'.</span><span class="sxs-lookup"><span data-stu-id="fade3-191">In the Name field, type 'Payer'.</span></span>
    * <span data-ttu-id="fade3-192">Pagador</span><span class="sxs-lookup"><span data-stu-id="fade3-192">Payer</span></span>  
53. <span data-ttu-id="fade3-193">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item".</span><span class="sxs-lookup"><span data-stu-id="fade3-193">In the tree, select 'Xml\Message\Payments\Item'.</span></span>
54. <span data-ttu-id="fade3-194">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-194">Click Add Element.</span></span>
55. <span data-ttu-id="fade3-195">No campo Nome, digite 'Moeda'.</span><span class="sxs-lookup"><span data-stu-id="fade3-195">In the Name field, type 'Currency'.</span></span>
    * <span data-ttu-id="fade3-196">Moeda</span><span class="sxs-lookup"><span data-stu-id="fade3-196">Currency</span></span>  
56. <span data-ttu-id="fade3-197">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-197">Click OK.</span></span>
57. <span data-ttu-id="fade3-198">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-198">Click Add Element.</span></span>
58. <span data-ttu-id="fade3-199">No campo Nome, digite 'Descrição'.</span><span class="sxs-lookup"><span data-stu-id="fade3-199">In the Name field, type 'Description'.</span></span>
    * <span data-ttu-id="fade3-200">descrição</span><span class="sxs-lookup"><span data-stu-id="fade3-200">Description</span></span>  
59. <span data-ttu-id="fade3-201">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-201">Click OK.</span></span>
60. <span data-ttu-id="fade3-202">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-202">Click Add Element.</span></span>
61. <span data-ttu-id="fade3-203">No campo Nome, digite 'TransDate'.</span><span class="sxs-lookup"><span data-stu-id="fade3-203">In the Name field, type 'TransDate'.</span></span>
    * <span data-ttu-id="fade3-204">TransDate</span><span class="sxs-lookup"><span data-stu-id="fade3-204">TransDate</span></span>  
62. <span data-ttu-id="fade3-205">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-205">Click OK.</span></span>
63. <span data-ttu-id="fade3-206">Clique em Adicionar elemento.</span><span class="sxs-lookup"><span data-stu-id="fade3-206">Click Add Element.</span></span>
64. <span data-ttu-id="fade3-207">No campo Nome, digite 'Valor'.</span><span class="sxs-lookup"><span data-stu-id="fade3-207">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="fade3-208">Valor</span><span class="sxs-lookup"><span data-stu-id="fade3-208">Amount</span></span>  
65. <span data-ttu-id="fade3-209">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-209">Click OK.</span></span>

## <a name="prepare-format-components-for-mapping-to-data-model-elements"></a><span data-ttu-id="fade3-210">Preparar os componentes do formato para mapeamento aos elementos do modelo de dados</span><span class="sxs-lookup"><span data-stu-id="fade3-210">Prepare format components for mapping to data model elements</span></span>
1. <span data-ttu-id="fade3-211">Na árvore, selecione "Xml\Mensagem\ProcessingDate".</span><span class="sxs-lookup"><span data-stu-id="fade3-211">In the tree, select 'Xml\Message\ProcessingDate'.</span></span>
2. <span data-ttu-id="fade3-212">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-212">Click Add to open the drop dialog.</span></span>
3. <span data-ttu-id="fade3-213">Na árvore, selecione "Texto\DateTime"</span><span class="sxs-lookup"><span data-stu-id="fade3-213">In the tree, select 'Text\DateTime'.</span></span>
4. <span data-ttu-id="fade3-214">No campo Formato, digite 'aaaa-MM-dd'.</span><span class="sxs-lookup"><span data-stu-id="fade3-214">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="fade3-215">dd-MM-aa</span><span class="sxs-lookup"><span data-stu-id="fade3-215">yyyy-MM-dd</span></span>  
5. <span data-ttu-id="fade3-216">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-216">Click OK.</span></span>
6. <span data-ttu-id="fade3-217">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\TransDate".</span><span class="sxs-lookup"><span data-stu-id="fade3-217">In the tree, select 'Xml\Message\Payments\Item\TransDate'.</span></span>
7. <span data-ttu-id="fade3-218">Clique em Adicionar DateTime.</span><span class="sxs-lookup"><span data-stu-id="fade3-218">Click Add DateTime.</span></span>
8. <span data-ttu-id="fade3-219">No campo Formato, digite 'aaaa-MM-dd'.</span><span class="sxs-lookup"><span data-stu-id="fade3-219">In the Format field, type 'yyyy-MM-dd'.</span></span>
    * <span data-ttu-id="fade3-220">dd-MM-aa</span><span class="sxs-lookup"><span data-stu-id="fade3-220">yyyy-MM-dd</span></span>  
9. <span data-ttu-id="fade3-221">No campo DateTime, selecione "Data".</span><span class="sxs-lookup"><span data-stu-id="fade3-221">In the DateTime type field, select 'Date'.</span></span>
10. <span data-ttu-id="fade3-222">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-222">Click OK.</span></span>
11. <span data-ttu-id="fade3-223">Na árvore, selecione "Xml\Mensagem\MessageId".</span><span class="sxs-lookup"><span data-stu-id="fade3-223">In the tree, select 'Xml\Message\MessageId'.</span></span>
12. <span data-ttu-id="fade3-224">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fade3-224">Click Add to open the drop dialog.</span></span>
13. <span data-ttu-id="fade3-225">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="fade3-225">In the tree, select 'Text\String'.</span></span>
14. <span data-ttu-id="fade3-226">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-226">Click OK.</span></span>
15. <span data-ttu-id="fade3-227">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Nome".</span><span class="sxs-lookup"><span data-stu-id="fade3-227">In the tree, select 'Xml\Message\Payments\Item\Vendor\Name'.</span></span>
16. <span data-ttu-id="fade3-228">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-228">Click Add String.</span></span>
17. <span data-ttu-id="fade3-229">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-229">Click OK.</span></span>
18. <span data-ttu-id="fade3-230">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="fade3-230">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\RoutingNumber'.</span></span>
19. <span data-ttu-id="fade3-231">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-231">Click Add String.</span></span>
20. <span data-ttu-id="fade3-232">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-232">Click OK.</span></span>
21. <span data-ttu-id="fade3-233">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Fornecedor\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="fade3-233">In the tree, select 'Xml\Message\Payments\Item\Vendor\Bank\AccountNumber'.</span></span>
22. <span data-ttu-id="fade3-234">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-234">Click Add String.</span></span>
23. <span data-ttu-id="fade3-235">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-235">Click OK.</span></span>
24. <span data-ttu-id="fade3-236">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Nome".</span><span class="sxs-lookup"><span data-stu-id="fade3-236">In the tree, select 'Xml\Message\Payments\Item\Payer\Name'.</span></span>
25. <span data-ttu-id="fade3-237">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-237">Click Add String.</span></span>
26. <span data-ttu-id="fade3-238">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-238">Click OK.</span></span>
27. <span data-ttu-id="fade3-239">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\RoutingNumber".</span><span class="sxs-lookup"><span data-stu-id="fade3-239">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\RoutingNumber'.</span></span>
28. <span data-ttu-id="fade3-240">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-240">Click Add String.</span></span>
29. <span data-ttu-id="fade3-241">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-241">Click OK.</span></span>
30. <span data-ttu-id="fade3-242">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Pagador\Banco\AccountNumber".</span><span class="sxs-lookup"><span data-stu-id="fade3-242">In the tree, select 'Xml\Message\Payments\Item\Payer\Bank\AccountNumber'.</span></span>
31. <span data-ttu-id="fade3-243">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-243">Click Add String.</span></span>
32. <span data-ttu-id="fade3-244">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-244">Click OK.</span></span>
33. <span data-ttu-id="fade3-245">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Moeda".</span><span class="sxs-lookup"><span data-stu-id="fade3-245">In the tree, select 'Xml\Message\Payments\Item\Currency'.</span></span>
34. <span data-ttu-id="fade3-246">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-246">Click Add String.</span></span>
35. <span data-ttu-id="fade3-247">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-247">Click OK.</span></span>
36. <span data-ttu-id="fade3-248">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Descrição".</span><span class="sxs-lookup"><span data-stu-id="fade3-248">In the tree, select 'Xml\Message\Payments\Item\Description'.</span></span>
37. <span data-ttu-id="fade3-249">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-249">Click Add String.</span></span>
38. <span data-ttu-id="fade3-250">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-250">Click OK.</span></span>
39. <span data-ttu-id="fade3-251">Na árvore, selecione "Xml\Mensagem\Pagamentos\Item\Valor".</span><span class="sxs-lookup"><span data-stu-id="fade3-251">In the tree, select 'Xml\Message\Payments\Item\Amount'.</span></span>
40. <span data-ttu-id="fade3-252">Clique em Adicionar cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="fade3-252">Click Add String.</span></span>
41. <span data-ttu-id="fade3-253">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fade3-253">Click OK.</span></span>
42. <span data-ttu-id="fade3-254">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fade3-254">Click Save.</span></span>
43. <span data-ttu-id="fade3-255">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fade3-255">Close the page.</span></span>


