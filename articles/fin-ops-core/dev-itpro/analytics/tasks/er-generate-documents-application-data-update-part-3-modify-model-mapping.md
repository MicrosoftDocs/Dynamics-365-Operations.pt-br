---
title: Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego
description: Este tópico descreve como criar configurações de relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo. (Parte 2 - Gerar documentos).
author: NickSelin
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 78b1771d0e01702162192ff20c03facbba4f3513
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751597"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="7477e-104">Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="7477e-104">Modify models and mappings to generate documents that have application data</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7477e-105">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 2: Gerar documentos)".</span><span class="sxs-lookup"><span data-stu-id="7477e-105">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 2: Generate documents)".</span></span> 

<span data-ttu-id="7477e-106">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7477e-106">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="7477e-107">Nesse procedimento, você modificará as configurações de ER para começar a usá-las para gerar documentos eletrônicos e dados de aplicativo de atualização.</span><span class="sxs-lookup"><span data-stu-id="7477e-107">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="7477e-108">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="7477e-108">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="7477e-109">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="7477e-109">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="7477e-110">Modifique o modelo de dados</span><span class="sxs-lookup"><span data-stu-id="7477e-110">Modify data model</span></span>
1. <span data-ttu-id="7477e-111">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="7477e-111">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="7477e-112">Na árvore, selecione 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-112">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="7477e-113">Você estenderá como usa o modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="7477e-113">You will extend how you use the data model.</span></span> <span data-ttu-id="7477e-114">Além de usá-lo como a fonte de dados para gerar o relatório Intrastat, o modelo de dados será usado para obter detalhes sobre o processo de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7477e-114">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="7477e-115">Os detalhes serão usados para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7477e-115">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="7477e-116">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="7477e-116">Click Designer.</span></span>
4. <span data-ttu-id="7477e-117">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-117">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="7477e-118">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="7477e-118">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="7477e-119">No campo Nome, digite 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-119">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="7477e-120">Para atualização de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7477e-120">For application data update</span></span>  
7. <span data-ttu-id="7477e-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-121">Click Add.</span></span>
8. <span data-ttu-id="7477e-122">Na árvore, selecione 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-122">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="7477e-123">Este novo item raiz foi adicionado para especificar o fluxo de dados para mover dados do relatório Intrastat (usado como uma fonte de dados) para as tabelas de aplicativo (o destino de atualização).</span><span class="sxs-lookup"><span data-stu-id="7477e-123">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="7477e-124">Observe que diferentes itens raiz devem ser usados para receber dados que são lançados no documento de saída e receber dados do documento usado para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7477e-124">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="7477e-125">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-125">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="7477e-126">No campo Nome, digite 'Cabeçalho do arquivo-morto'.</span><span class="sxs-lookup"><span data-stu-id="7477e-126">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="7477e-127">Cabeçalho do arquivo-morto</span><span class="sxs-lookup"><span data-stu-id="7477e-127">Archive header</span></span>  
11. <span data-ttu-id="7477e-128">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="7477e-128">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="7477e-129">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-129">Click Add.</span></span>
    * <span data-ttu-id="7477e-130">Conforme você cria um registro para cada relatório Intrastat que é gerado, você deve criar um novo item para tal.</span><span class="sxs-lookup"><span data-stu-id="7477e-130">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="7477e-131">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-131">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="7477e-132">No campo Nome, digite 'Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-132">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="7477e-133">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="7477e-133">File name</span></span>  
15. <span data-ttu-id="7477e-134">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="7477e-134">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="7477e-135">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-135">Click Add.</span></span>
17. <span data-ttu-id="7477e-136">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-136">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="7477e-137">No campo Nome, digite 'Número de linhas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-137">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="7477e-138">Número de linhas</span><span class="sxs-lookup"><span data-stu-id="7477e-138">Number of lines</span></span>  
19. <span data-ttu-id="7477e-139">No campo Tipo de item, selecione 'Inteiro'.</span><span class="sxs-lookup"><span data-stu-id="7477e-139">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="7477e-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-140">Click Add.</span></span>
    * <span data-ttu-id="7477e-141">Adicione este item para representar o número das transações Intrastat que são informadas durante o processo de relatório atual.</span><span class="sxs-lookup"><span data-stu-id="7477e-141">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="7477e-142">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-142">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="7477e-143">No campo Nome, digite 'Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-143">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="7477e-144">Arquivar linhas</span><span class="sxs-lookup"><span data-stu-id="7477e-144">Archive lines</span></span>  
23. <span data-ttu-id="7477e-145">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="7477e-145">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="7477e-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-146">Click Add.</span></span>
    * <span data-ttu-id="7477e-147">Adicione este item para representar a lita de das transações Intrastat que são informadas durante o processo de relatório atual.</span><span class="sxs-lookup"><span data-stu-id="7477e-147">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="7477e-148">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-148">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="7477e-149">No campo Nome, digite 'Valor'.</span><span class="sxs-lookup"><span data-stu-id="7477e-149">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="7477e-150">Valor</span><span class="sxs-lookup"><span data-stu-id="7477e-150">Amount</span></span>  
27. <span data-ttu-id="7477e-151">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="7477e-151">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="7477e-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-152">Click Add.</span></span>
29. <span data-ttu-id="7477e-153">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-153">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="7477e-154">No campo Nome, digite 'Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="7477e-154">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="7477e-155">Id reg de mercadoria</span><span class="sxs-lookup"><span data-stu-id="7477e-155">Commodity rec id</span></span>  
31. <span data-ttu-id="7477e-156">No campo Tipo de item, selecione 'Int64'.</span><span class="sxs-lookup"><span data-stu-id="7477e-156">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="7477e-157">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-157">Click Add.</span></span>
33. <span data-ttu-id="7477e-158">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="7477e-158">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="7477e-159">No campo Nome, digite 'Número do item'.</span><span class="sxs-lookup"><span data-stu-id="7477e-159">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="7477e-160">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="7477e-160">Item number</span></span>  
35. <span data-ttu-id="7477e-161">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="7477e-161">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="7477e-162">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-162">Click Add.</span></span>
37. <span data-ttu-id="7477e-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7477e-163">Click Save.</span></span>
38. <span data-ttu-id="7477e-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7477e-164">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="7477e-165">Modifique o mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="7477e-165">Modify model mapping</span></span>
1. <span data-ttu-id="7477e-166">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-166">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="7477e-167">Na árvore, selecione 'Intrastat (modelo)\Intrastat (mapeamento)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-167">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="7477e-168">Modifique o mapeamento de modelo existente para começar a usá-lo para a atualização de dados do aplicativo e para arquivar detalhes de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7477e-168">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="7477e-169">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="7477e-169">Click Designer.</span></span>
4. <span data-ttu-id="7477e-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7477e-170">Click New.</span></span>
5. <span data-ttu-id="7477e-171">No campo Nome, digite 'Atualizar arquivo-morto'.</span><span class="sxs-lookup"><span data-stu-id="7477e-171">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="7477e-172">Atualizar arquivo-morto</span><span class="sxs-lookup"><span data-stu-id="7477e-172">Update archive</span></span>  
6. <span data-ttu-id="7477e-173">No campo Direção, selecione 'Para destino'.</span><span class="sxs-lookup"><span data-stu-id="7477e-173">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="7477e-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7477e-174">Click Save.</span></span>
    * <span data-ttu-id="7477e-175">Este novo mapeamento especifica o fluxo de dados para mover dados (detalhes do relatório Intrastat) do modelo de dados para as tabelas do aplicativo (o destino da atualização).</span><span class="sxs-lookup"><span data-stu-id="7477e-175">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="7477e-176">Observe que diferentes itens raiz do modelo devem ser usados para obter os dados do aplicativo para o processo de relatório e depois use os dados do modelo para atualização de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7477e-176">Note that different model's root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="7477e-177">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="7477e-177">Click Designer.</span></span>
9. <span data-ttu-id="7477e-178">Na árvore, selecione 'Modelo de dados\Modelo de dados'.</span><span class="sxs-lookup"><span data-stu-id="7477e-178">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="7477e-179">Adicione a fonte de dados obrigatória.</span><span class="sxs-lookup"><span data-stu-id="7477e-179">Add the required data source.</span></span> <span data-ttu-id="7477e-180">Este é o modelo de dados que contém detalhes das transações Intrastat informadas que devem ser preenchidas.</span><span class="sxs-lookup"><span data-stu-id="7477e-180">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="7477e-181">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="7477e-181">Click Add root.</span></span>
11. <span data-ttu-id="7477e-182">No campo Nome, digite 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-182">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="7477e-183">modelo</span><span class="sxs-lookup"><span data-stu-id="7477e-183">model</span></span>  
12. <span data-ttu-id="7477e-184">No campo Definição, insira ou selecione o valor "Para atualização de dados do aplicativo".</span><span class="sxs-lookup"><span data-stu-id="7477e-184">In the Definition field, enter or select the value 'For application data update'.</span></span>
    * <span data-ttu-id="7477e-185">Para atualização de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="7477e-185">For application data update</span></span>  
13. <span data-ttu-id="7477e-186">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7477e-186">Click OK.</span></span>
14. <span data-ttu-id="7477e-187">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-187">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="7477e-188">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="7477e-188">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="7477e-189">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="7477e-189">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="7477e-190">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="7477e-190">Click Add.</span></span>
    * <span data-ttu-id="7477e-191">Como você deseja enumerar transações Intrastat informadas para arquivar, a fonte de dados apropriada deverá ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="7477e-191">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="7477e-192">No campo Nome, digite 'Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-192">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="7477e-193">Linhas enumeradas</span><span class="sxs-lookup"><span data-stu-id="7477e-193">Enumerated lines</span></span>  
19. <span data-ttu-id="7477e-194">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="7477e-194">Click Edit formula.</span></span>
20. <span data-ttu-id="7477e-195">Na árvore, selecione 'Lista\ENUMERAR'.</span><span class="sxs-lookup"><span data-stu-id="7477e-195">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="7477e-196">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="7477e-196">Click Add function.</span></span>
22. <span data-ttu-id="7477e-197">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-197">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="7477e-198">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="7477e-198">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="7477e-199">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-199">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="7477e-200">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7477e-200">Click Add data source.</span></span>
26. <span data-ttu-id="7477e-201">No campo Fórmula, insira “ENUMERAM (modelo."Cabeçalho do arquivo morto.""Arquivar linhas").</span><span class="sxs-lookup"><span data-stu-id="7477e-201">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="7477e-202">ENUMERATE(model.'Cabeçalho do arquivo morto'.'Arquivar linhas')</span><span class="sxs-lookup"><span data-stu-id="7477e-202">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="7477e-203">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7477e-203">Click Save.</span></span>
28. <span data-ttu-id="7477e-204">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7477e-204">Close the page.</span></span>
29. <span data-ttu-id="7477e-205">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7477e-205">Click OK.</span></span>
30. <span data-ttu-id="7477e-206">Clique em Adicionar destino.</span><span class="sxs-lookup"><span data-stu-id="7477e-206">Click Add destination.</span></span>
    * <span data-ttu-id="7477e-207">Adicione as tabelas do aplicativo como destinos obrigatórios que exigem atualizações para arquivar detalhes de transações Intrastat reportadas.</span><span class="sxs-lookup"><span data-stu-id="7477e-207">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="7477e-208">No campo Nome, digite "Arquivar".</span><span class="sxs-lookup"><span data-stu-id="7477e-208">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="7477e-209">Arquivar</span><span class="sxs-lookup"><span data-stu-id="7477e-209">Archive</span></span>  
32. <span data-ttu-id="7477e-210">No campo Nome de tabela, digite “IntrastatArchiveGeneral”.</span><span class="sxs-lookup"><span data-stu-id="7477e-210">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="7477e-211">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="7477e-211">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="7477e-212">Mantenha a ação de registro "Inserir" para poder adicionar registros durante o arquivamento de detalhes de cada processo do relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="7477e-212">Keep the record action 'Insert' so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="7477e-213">Selecione Sim no campo Log de informações sobre registro.</span><span class="sxs-lookup"><span data-stu-id="7477e-213">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="7477e-214">Selecione Sim para obter informações sobre problemas com a atualização de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="7477e-214">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="7477e-215">Selecione Sim no campo Ignorar validação da ação de registro.</span><span class="sxs-lookup"><span data-stu-id="7477e-215">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="7477e-216">Selecione Sim para suprimir erros de validação sobre o campo "ID de arquivo morto Intrastat".</span><span class="sxs-lookup"><span data-stu-id="7477e-216">Select Yes to suppress validation errors about the empty 'Intrastat archive ID' field.</span></span> <span data-ttu-id="7477e-217">Isso será feito depois que os registros forem adicionados, com base nas configurações do número de sequência configuradas para a tabela no formulário parâmetros Comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="7477e-217">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="7477e-218">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7477e-218">Click OK.</span></span>
    * <span data-ttu-id="7477e-219">Associe os elementos da fonte de dados adicional (o modelo filtrado baseado no item raiz selecionado) com elementos de destino adicionado.</span><span class="sxs-lookup"><span data-stu-id="7477e-219">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="7477e-220">Na árvore, expanda 'Arquivar'.</span><span class="sxs-lookup"><span data-stu-id="7477e-220">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="7477e-221">Na árvore, expanda 'Arquivar\<Relações'.</span><span class="sxs-lookup"><span data-stu-id="7477e-221">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="7477e-222">Na árvore, expanda 'Arquivar\<Relações\IntrastatArchiveDetail'.</span><span class="sxs-lookup"><span data-stu-id="7477e-222">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="7477e-223">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Valor(AmountMST)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-223">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="7477e-224">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-224">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="7477e-225">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor'.</span><span class="sxs-lookup"><span data-stu-id="7477e-225">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="7477e-226">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Valor'.</span><span class="sxs-lookup"><span data-stu-id="7477e-226">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="7477e-227">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-227">Click Bind.</span></span>
44. <span data-ttu-id="7477e-228">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Mercadoria(IntrastatCommodity)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-228">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="7477e-229">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="7477e-229">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="7477e-230">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-230">Click Bind.</span></span>
47. <span data-ttu-id="7477e-231">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número do item(ItemId)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-231">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="7477e-232">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Número do item'.</span><span class="sxs-lookup"><span data-stu-id="7477e-232">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="7477e-233">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-233">Click Bind.</span></span>
50. <span data-ttu-id="7477e-234">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número da linha(LineNumber)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-234">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="7477e-235">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Número'.</span><span class="sxs-lookup"><span data-stu-id="7477e-235">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="7477e-236">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-236">Click Bind.</span></span>
53. <span data-ttu-id="7477e-237">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail'.</span><span class="sxs-lookup"><span data-stu-id="7477e-237">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="7477e-238">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-238">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="7477e-239">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-239">Click Bind.</span></span>
56. <span data-ttu-id="7477e-240">Na árvore, selecione 'Arquivar\Nome do arquivo(FileName)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-240">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="7477e-241">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="7477e-241">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="7477e-242">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-242">Click Bind.</span></span>
59. <span data-ttu-id="7477e-243">Na árvore, selecione 'Arquivar\Número de linhas(NumberOfLines)'.</span><span class="sxs-lookup"><span data-stu-id="7477e-243">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="7477e-244">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Número de linhas'.</span><span class="sxs-lookup"><span data-stu-id="7477e-244">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="7477e-245">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-245">Click Bind.</span></span>
62. <span data-ttu-id="7477e-246">Na árvore, selecione 'Arquivar'.</span><span class="sxs-lookup"><span data-stu-id="7477e-246">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="7477e-247">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="7477e-247">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="7477e-248">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="7477e-248">Click Bind.</span></span>
65. <span data-ttu-id="7477e-249">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="7477e-249">Click Save.</span></span>
66. <span data-ttu-id="7477e-250">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7477e-250">Close the page.</span></span>
67. <span data-ttu-id="7477e-251">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7477e-251">Close the page.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]