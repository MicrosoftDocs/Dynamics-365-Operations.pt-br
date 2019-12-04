---
title: Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego
description: Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 2 – Gerar documentos)".
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5df6128228b9ff620c606c550c5eb7a6039b915
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182292"
---
# <a name="modify-models-and-mappings-to-generate-documents-that-have-application-data"></a><span data-ttu-id="86902-103">Modificar modelos e mapeamentos para gerar documentos com dados da solicitação de emprego</span><span class="sxs-lookup"><span data-stu-id="86902-103">Modify models and mappings to generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="86902-104">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 2: Gerar documentos)".</span><span class="sxs-lookup"><span data-stu-id="86902-104">To complete the steps in this procedure, you must first complete the procedure, “ER Generate documents with application data update (Part 2: Generate documents)”.</span></span> 

<span data-ttu-id="86902-105">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="86902-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="86902-106">Nesse procedimento, você modificará as configurações de ER para começar a usá-las para gerar documentos eletrônicos e dados de aplicativo de atualização.</span><span class="sxs-lookup"><span data-stu-id="86902-106">In this procedure, you will modify the ER configurations to start using them to generate electronic documents and update application data.</span></span> <span data-ttu-id="86902-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="86902-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="86902-108">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="86902-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-data-model"></a><span data-ttu-id="86902-109">Modifique o modelo de dados</span><span class="sxs-lookup"><span data-stu-id="86902-109">Modify data model</span></span>
1. <span data-ttu-id="86902-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="86902-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="86902-111">Na árvore, selecione 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="86902-111">In the tree, select 'Intrastat (model)'.</span></span>
    * <span data-ttu-id="86902-112">Você estenderá como usa o modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="86902-112">You will extend how you use the data model.</span></span> <span data-ttu-id="86902-113">Além de usá-lo como a fonte de dados para gerar o relatório Intrastat, o modelo de dados será usado para obter detalhes sobre o processo de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="86902-113">Besides using it as data source to generate the Intrastat report, the data model will be used to collect details about the Intrastat reporting process.</span></span> <span data-ttu-id="86902-114">Os detalhes serão usados para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="86902-114">The details will then be used to update application data.</span></span>   
3. <span data-ttu-id="86902-115">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="86902-115">Click Designer.</span></span>
4. <span data-ttu-id="86902-116">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-116">Click New to open the drop dialog.</span></span>
5. <span data-ttu-id="86902-117">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="86902-117">In the New node as a field, enter 'Model root'.</span></span>
6. <span data-ttu-id="86902-118">No campo Nome, digite 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="86902-118">In the Name field, type 'For application data update'.</span></span>
    * <span data-ttu-id="86902-119">Para atualização de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="86902-119">For application data update</span></span>  
7. <span data-ttu-id="86902-120">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-120">Click Add.</span></span>
8. <span data-ttu-id="86902-121">Na árvore, selecione 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="86902-121">In the tree, select 'For application data update'.</span></span>
    * <span data-ttu-id="86902-122">Este novo item raiz foi adicionado para especificar o fluxo de dados para mover dados do relatório Intrastat (usado como uma fonte de dados) para as tabelas de aplicativo (o destino de atualização).</span><span class="sxs-lookup"><span data-stu-id="86902-122">This new root item is added to specify the data flow for moving data from the Intrastat report (used as a data source) to the application tables (the update destination).</span></span> <span data-ttu-id="86902-123">Observe que diferentes itens raiz devem ser usados para receber dados que são lançados no documento de saída e receber dados do documento usado para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="86902-123">Note that different root items must be used for getting data that is posted to the outgoing document and for getting data from the document that is used to update application data.</span></span>   
9. <span data-ttu-id="86902-124">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="86902-125">No campo Nome, digite 'Cabeçalho do arquivo-morto'.</span><span class="sxs-lookup"><span data-stu-id="86902-125">In the Name field, type 'Archive header'.</span></span>
    * <span data-ttu-id="86902-126">Cabeçalho do arquivo-morto</span><span class="sxs-lookup"><span data-stu-id="86902-126">Archive header</span></span>  
11. <span data-ttu-id="86902-127">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="86902-127">In the Item type field, select 'Record list'.</span></span>
12. <span data-ttu-id="86902-128">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-128">Click Add.</span></span>
    * <span data-ttu-id="86902-129">Conforme você cria um registro para cada relatório Intrastat que é gerado, você deve criar um novo item para tal.</span><span class="sxs-lookup"><span data-stu-id="86902-129">Because you will create a record for each Intrastat report that is generated, you must create a new item for that.</span></span>  
13. <span data-ttu-id="86902-130">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-130">Click New to open the drop dialog.</span></span>
14. <span data-ttu-id="86902-131">No campo Nome, digite 'Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="86902-131">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="86902-132">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="86902-132">File name</span></span>  
15. <span data-ttu-id="86902-133">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="86902-133">In the Item type field, select 'String'.</span></span>
16. <span data-ttu-id="86902-134">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-134">Click Add.</span></span>
17. <span data-ttu-id="86902-135">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-135">Click New to open the drop dialog.</span></span>
18. <span data-ttu-id="86902-136">No campo Nome, digite 'Número de linhas'.</span><span class="sxs-lookup"><span data-stu-id="86902-136">In the Name field, type 'Number of lines'.</span></span>
    * <span data-ttu-id="86902-137">Número de linhas</span><span class="sxs-lookup"><span data-stu-id="86902-137">Number of lines</span></span>  
19. <span data-ttu-id="86902-138">No campo Tipo de item, selecione 'Inteiro'.</span><span class="sxs-lookup"><span data-stu-id="86902-138">In the Item type field, select 'Integer'.</span></span>
20. <span data-ttu-id="86902-139">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-139">Click Add.</span></span>
    * <span data-ttu-id="86902-140">Adicione este item para representar o número das transações Intrastat que são informadas durante o processo de relatório atual.</span><span class="sxs-lookup"><span data-stu-id="86902-140">Add this item to represent the number of Intrastat transactions that are reported during the current reporting process.</span></span>  
21. <span data-ttu-id="86902-141">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-141">Click New to open the drop dialog.</span></span>
22. <span data-ttu-id="86902-142">No campo Nome, digite 'Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="86902-142">In the Name field, type 'Archive lines'.</span></span>
    * <span data-ttu-id="86902-143">Arquivar linhas</span><span class="sxs-lookup"><span data-stu-id="86902-143">Archive lines</span></span>  
23. <span data-ttu-id="86902-144">No campo Tipo de item, selecione 'Lista de Registro'.</span><span class="sxs-lookup"><span data-stu-id="86902-144">In the Item type field, select 'Record list'.</span></span>
24. <span data-ttu-id="86902-145">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-145">Click Add.</span></span>
    * <span data-ttu-id="86902-146">Adicione este item para representar a lita de das transações Intrastat que são informadas durante o processo de relatório atual.</span><span class="sxs-lookup"><span data-stu-id="86902-146">Add this item to represent the list of Intrastat transactions that are reported during the current reporting process.</span></span>  
25. <span data-ttu-id="86902-147">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-147">Click New to open the drop dialog.</span></span>
26. <span data-ttu-id="86902-148">No campo Nome, digite 'Valor'.</span><span class="sxs-lookup"><span data-stu-id="86902-148">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="86902-149">Valor</span><span class="sxs-lookup"><span data-stu-id="86902-149">Amount</span></span>  
27. <span data-ttu-id="86902-150">No campo Tipo de item, selecione 'Real'.</span><span class="sxs-lookup"><span data-stu-id="86902-150">In the Item type field, select 'Real'.</span></span>
28. <span data-ttu-id="86902-151">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-151">Click Add.</span></span>
29. <span data-ttu-id="86902-152">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-152">Click New to open the drop dialog.</span></span>
30. <span data-ttu-id="86902-153">No campo Nome, digite 'Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="86902-153">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="86902-154">Id reg de mercadoria</span><span class="sxs-lookup"><span data-stu-id="86902-154">Commodity rec id</span></span>  
31. <span data-ttu-id="86902-155">No campo Tipo de item, selecione 'Int64'.</span><span class="sxs-lookup"><span data-stu-id="86902-155">In the Item type field, select 'Int64'.</span></span>
32. <span data-ttu-id="86902-156">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-156">Click Add.</span></span>
33. <span data-ttu-id="86902-157">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="86902-157">Click New to open the drop dialog.</span></span>
34. <span data-ttu-id="86902-158">No campo Nome, digite 'Número do item'.</span><span class="sxs-lookup"><span data-stu-id="86902-158">In the Name field, type 'Item number'.</span></span>
    * <span data-ttu-id="86902-159">Nº de itens</span><span class="sxs-lookup"><span data-stu-id="86902-159">Item number</span></span>  
35. <span data-ttu-id="86902-160">No campo Tipo de item, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="86902-160">In the Item type field, select 'String'.</span></span>
36. <span data-ttu-id="86902-161">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-161">Click Add.</span></span>
37. <span data-ttu-id="86902-162">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86902-162">Click Save.</span></span>
38. <span data-ttu-id="86902-163">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="86902-163">Close the page.</span></span>

## <a name="modify-model-mapping"></a><span data-ttu-id="86902-164">Modifique o mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="86902-164">Modify model mapping</span></span>
1. <span data-ttu-id="86902-165">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="86902-165">In the tree, expand 'Intrastat (model)'.</span></span>
2. <span data-ttu-id="86902-166">Na árvore, selecione 'Intrastat (modelo)\Intrastat (mapeamento)'.</span><span class="sxs-lookup"><span data-stu-id="86902-166">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
    * <span data-ttu-id="86902-167">Modifique o mapeamento de modelo existente para começar a usá-lo para a atualização de dados do aplicativo e para arquivar detalhes de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="86902-167">Modify the existing model mapping to start using it for  the application data update and to archive Intrastat reporting details.</span></span>  
3. <span data-ttu-id="86902-168">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="86902-168">Click Designer.</span></span>
4. <span data-ttu-id="86902-169">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="86902-169">Click New.</span></span>
5. <span data-ttu-id="86902-170">No campo Nome, digite 'Atualizar arquivo-morto'.</span><span class="sxs-lookup"><span data-stu-id="86902-170">In the Name field, type 'Update archive'.</span></span>
    * <span data-ttu-id="86902-171">Atualizar arquivo-morto</span><span class="sxs-lookup"><span data-stu-id="86902-171">Update archive</span></span>  
6. <span data-ttu-id="86902-172">No campo Direção, selecione 'Para destino'.</span><span class="sxs-lookup"><span data-stu-id="86902-172">In the Direction field, select 'To destination'.</span></span>
7. <span data-ttu-id="86902-173">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86902-173">Click Save.</span></span>
    * <span data-ttu-id="86902-174">Este novo mapeamento especifica o fluxo de dados para mover dados (detalhes do relatório Intrastat) do modelo de dados para as tabelas do aplicativo (o destino da atualização).</span><span class="sxs-lookup"><span data-stu-id="86902-174">This new mapping specifies the data flow for moving data (Intrastat reporting details) from the data model to the application tables (the update destination).</span></span> <span data-ttu-id="86902-175">Observe que diferentes itens raiz do modelo devem ser usados para obter os dados do aplicativo para o processo de relatório e depois use os dados do modelo para atualização de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="86902-175">Note that different model’s root items must be used to get data from the application for the reporting process and then use the data from data model for the application data update.</span></span>   
8. <span data-ttu-id="86902-176">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="86902-176">Click Designer.</span></span>
9. <span data-ttu-id="86902-177">Na árvore, selecione 'Modelo de dados\Modelo de dados'.</span><span class="sxs-lookup"><span data-stu-id="86902-177">In the tree, select 'Data model\Data model'.</span></span>
    * <span data-ttu-id="86902-178">Adicione a fonte de dados obrigatória.</span><span class="sxs-lookup"><span data-stu-id="86902-178">Add the required data source.</span></span> <span data-ttu-id="86902-179">Este é o modelo de dados que contém detalhes das transações Intrastat informadas que devem ser preenchidas.</span><span class="sxs-lookup"><span data-stu-id="86902-179">This is the data model that contains details of the reported Intrastat transactions that must be archived.</span></span>  
10. <span data-ttu-id="86902-180">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="86902-180">Click Add root.</span></span>
11. <span data-ttu-id="86902-181">No campo Nome, digite 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="86902-181">In the Name field, type 'model'.</span></span>
    * <span data-ttu-id="86902-182">modelo</span><span class="sxs-lookup"><span data-stu-id="86902-182">model</span></span>  
12. <span data-ttu-id="86902-183">No campo Definição, insira ou selecione o valor 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="86902-183">In the Definition field, enter or select the value ‘For application data update’.</span></span>
    * <span data-ttu-id="86902-184">Para atualização de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="86902-184">For application data update</span></span>  
13. <span data-ttu-id="86902-185">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86902-185">Click OK.</span></span>
14. <span data-ttu-id="86902-186">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="86902-186">In the tree, expand 'model'.</span></span>
15. <span data-ttu-id="86902-187">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="86902-187">In the tree, select 'Functions\Calculated field'.</span></span>
16. <span data-ttu-id="86902-188">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="86902-188">In the tree, select 'model\Archive header'.</span></span>
17. <span data-ttu-id="86902-189">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="86902-189">Click Add.</span></span>
    * <span data-ttu-id="86902-190">Como você deseja enumerar transações Intrastat informadas para arquivar, a fonte de dados apropriada deverá ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="86902-190">Because you want to enumerate reported Intrastat transactions for archiving, the appropriate data source must be added.</span></span>  
18. <span data-ttu-id="86902-191">No campo Nome, digite 'Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="86902-191">In the Name field, type 'Enumerated lines'.</span></span>
    * <span data-ttu-id="86902-192">Linhas enumeradas</span><span class="sxs-lookup"><span data-stu-id="86902-192">Enumerated lines</span></span>  
19. <span data-ttu-id="86902-193">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="86902-193">Click Edit formula.</span></span>
20. <span data-ttu-id="86902-194">Na árvore, selecione 'Lista\ENUMERAR'.</span><span class="sxs-lookup"><span data-stu-id="86902-194">In the tree, select 'List\ENUMERATE'.</span></span>
21. <span data-ttu-id="86902-195">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="86902-195">Click Add function.</span></span>
22. <span data-ttu-id="86902-196">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="86902-196">In the tree, expand 'model'.</span></span>
23. <span data-ttu-id="86902-197">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="86902-197">In the tree, expand 'model\Archive header'.</span></span>
24. <span data-ttu-id="86902-198">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="86902-198">In the tree, select 'model\Archive header\Archive lines'.</span></span>
25. <span data-ttu-id="86902-199">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="86902-199">Click Add data source.</span></span>
26. <span data-ttu-id="86902-200">No campo Fórmula, insira “ENUMERAM (modelo."Cabeçalho do arquivo morto.""Arquivar linhas").</span><span class="sxs-lookup"><span data-stu-id="86902-200">In the Formula field, enter 'ENUMERATE(model.'Archive header'.'Archive lines')'.</span></span>
    * <span data-ttu-id="86902-201">ENUMERATE(model.'Cabeçalho do arquivo morto'.'Arquivar linhas')</span><span class="sxs-lookup"><span data-stu-id="86902-201">ENUMERATE(model.'Archive header'.'Archive lines')</span></span>  
27. <span data-ttu-id="86902-202">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86902-202">Click Save.</span></span>
28. <span data-ttu-id="86902-203">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="86902-203">Close the page.</span></span>
29. <span data-ttu-id="86902-204">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86902-204">Click OK.</span></span>
30. <span data-ttu-id="86902-205">Clique em Adicionar destino.</span><span class="sxs-lookup"><span data-stu-id="86902-205">Click Add destination.</span></span>
    * <span data-ttu-id="86902-206">Adicione as tabelas do aplicativo como destinos obrigatórios que exigem atualizações para arquivar detalhes de transações Intrastat reportadas.</span><span class="sxs-lookup"><span data-stu-id="86902-206">Add application tables as required destinations that require updates to archive details of reported Intrastat transactions.</span></span>  
31. <span data-ttu-id="86902-207">No campo Nome, digite "Arquivar".</span><span class="sxs-lookup"><span data-stu-id="86902-207">In the Name field, type 'Archive'.</span></span>
    * <span data-ttu-id="86902-208">Arquivar</span><span class="sxs-lookup"><span data-stu-id="86902-208">Archive</span></span>  
32. <span data-ttu-id="86902-209">No campo Nome de tabela, digite “IntrastatArchiveGeneral”.</span><span class="sxs-lookup"><span data-stu-id="86902-209">In the Table name field, type 'IntrastatArchiveGeneral'.</span></span>
    * <span data-ttu-id="86902-210">IntrastatArchiveGeneral</span><span class="sxs-lookup"><span data-stu-id="86902-210">IntrastatArchiveGeneral</span></span>  
    * <span data-ttu-id="86902-211">Mantenha a ação de registro 'Inserir' para poder adicionar registros durante o arquivamento de detalhes de cada processo do relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="86902-211">Keep the record action ‘Insert’ so you can add records during the detail archiving of each Intrastat reporting process.</span></span>  
33. <span data-ttu-id="86902-212">Selecione Sim no campo Log de informações sobre registro.</span><span class="sxs-lookup"><span data-stu-id="86902-212">Select Yes in the Record infolog field.</span></span>
    * <span data-ttu-id="86902-213">Selecione Sim para obter informações sobre problemas com a atualização de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="86902-213">Select Yes to get information about issues with the application data update.</span></span>  
34. <span data-ttu-id="86902-214">Selecione Sim no campo Ignorar validação da ação de registro.</span><span class="sxs-lookup"><span data-stu-id="86902-214">Select Yes in the Skip record action validation field.</span></span>
    * <span data-ttu-id="86902-215">Selecione Sim para suprimir erros de validação sobre o campo "ID de arquivo morto Intrastat".</span><span class="sxs-lookup"><span data-stu-id="86902-215">Select Yes to suppress validation errors about the empty ‘Intrastat archive ID’ field.</span></span> <span data-ttu-id="86902-216">Isso será feito depois que os registros forem adicionados, com base nas configurações do número de sequência configuradas para a tabela no formulário parâmetros Comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="86902-216">This will be done after records are added, based on the sequence number settings that are configured for this table in the Foreign trade parameters form.</span></span>  
35. <span data-ttu-id="86902-217">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="86902-217">Click OK.</span></span>
    * <span data-ttu-id="86902-218">Associe os elementos da fonte de dados adicional (o modelo filtrado baseado no item raiz selecionado) com elementos de destino adicionado.</span><span class="sxs-lookup"><span data-stu-id="86902-218">Bind elements of the added data source (the filtered model based on the selected root item) with elements from the added destination.</span></span>  
36. <span data-ttu-id="86902-219">Na árvore, expanda 'Arquivar'.</span><span class="sxs-lookup"><span data-stu-id="86902-219">In the tree, expand 'Archive'.</span></span>
37. <span data-ttu-id="86902-220">Na árvore, expanda 'Arquivar\<Relações'.</span><span class="sxs-lookup"><span data-stu-id="86902-220">In the tree, expand 'Archive\<Relations'.</span></span>
38. <span data-ttu-id="86902-221">Na árvore, expanda 'Arquivar\<Relações\IntrastatArchiveDetail'.</span><span class="sxs-lookup"><span data-stu-id="86902-221">In the tree, expand 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
39. <span data-ttu-id="86902-222">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Valor(AmountMST)'.</span><span class="sxs-lookup"><span data-stu-id="86902-222">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Amount(AmountMST)'.</span></span>
40. <span data-ttu-id="86902-223">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="86902-223">In the tree, expand 'model\Archive header\Enumerated lines'.</span></span>
41. <span data-ttu-id="86902-224">Na árvore, expanda 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor'.</span><span class="sxs-lookup"><span data-stu-id="86902-224">In the tree, expand 'model\Archive header\Enumerated lines\Value'.</span></span>
42. <span data-ttu-id="86902-225">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Valor'.</span><span class="sxs-lookup"><span data-stu-id="86902-225">In the tree, select 'model\Archive header\Enumerated lines\Value\Amount'.</span></span>
43. <span data-ttu-id="86902-226">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-226">Click Bind.</span></span>
44. <span data-ttu-id="86902-227">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Mercadoria(IntrastatCommodity)'.</span><span class="sxs-lookup"><span data-stu-id="86902-227">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Commodity(IntrastatCommodity)'.</span></span>
45. <span data-ttu-id="86902-228">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="86902-228">In the tree, select 'model\Archive header\Enumerated lines\Value\Commodity rec id'.</span></span>
46. <span data-ttu-id="86902-229">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-229">Click Bind.</span></span>
47. <span data-ttu-id="86902-230">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número do item(ItemId)'.</span><span class="sxs-lookup"><span data-stu-id="86902-230">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Item number(ItemId)'.</span></span>
48. <span data-ttu-id="86902-231">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Valor\Número do item'.</span><span class="sxs-lookup"><span data-stu-id="86902-231">In the tree, select 'model\Archive header\Enumerated lines\Value\Item number'.</span></span>
49. <span data-ttu-id="86902-232">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-232">Click Bind.</span></span>
50. <span data-ttu-id="86902-233">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail\Número da linha(LineNumber)'.</span><span class="sxs-lookup"><span data-stu-id="86902-233">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail\Line number(LineNumber)'.</span></span>
51. <span data-ttu-id="86902-234">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas\Número'.</span><span class="sxs-lookup"><span data-stu-id="86902-234">In the tree, select 'model\Archive header\Enumerated lines\Number'.</span></span>
52. <span data-ttu-id="86902-235">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-235">Click Bind.</span></span>
53. <span data-ttu-id="86902-236">Na árvore, selecione 'Arquivar\<Relações\IntrastatArchiveDetail'.</span><span class="sxs-lookup"><span data-stu-id="86902-236">In the tree, select 'Archive\<Relations\IntrastatArchiveDetail'.</span></span>
54. <span data-ttu-id="86902-237">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Linhas enumeradas'.</span><span class="sxs-lookup"><span data-stu-id="86902-237">In the tree, select 'model\Archive header\Enumerated lines'.</span></span>
55. <span data-ttu-id="86902-238">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-238">Click Bind.</span></span>
56. <span data-ttu-id="86902-239">Na árvore, selecione 'Arquivar\Nome do arquivo(FileName)'.</span><span class="sxs-lookup"><span data-stu-id="86902-239">In the tree, select 'Archive\File name(FileName)'.</span></span>
57. <span data-ttu-id="86902-240">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="86902-240">In the tree, select 'model\Archive header\File name'.</span></span>
58. <span data-ttu-id="86902-241">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-241">Click Bind.</span></span>
59. <span data-ttu-id="86902-242">Na árvore, selecione 'Arquivar\Número de linhas(NumberOfLines)'.</span><span class="sxs-lookup"><span data-stu-id="86902-242">In the tree, select 'Archive\Number of lines(NumberOfLines)'.</span></span>
60. <span data-ttu-id="86902-243">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto\Número de linhas'.</span><span class="sxs-lookup"><span data-stu-id="86902-243">In the tree, select 'model\Archive header\Number of lines'.</span></span>
61. <span data-ttu-id="86902-244">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-244">Click Bind.</span></span>
62. <span data-ttu-id="86902-245">Na árvore, selecione 'Arquivar'.</span><span class="sxs-lookup"><span data-stu-id="86902-245">In the tree, select 'Archive'.</span></span>
63. <span data-ttu-id="86902-246">Na árvore, selecione 'modelo\Cabeçalho do arquivo morto'.</span><span class="sxs-lookup"><span data-stu-id="86902-246">In the tree, select 'model\Archive header'.</span></span>
64. <span data-ttu-id="86902-247">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="86902-247">Click Bind.</span></span>
65. <span data-ttu-id="86902-248">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="86902-248">Click Save.</span></span>
66. <span data-ttu-id="86902-249">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="86902-249">Close the page.</span></span>
67. <span data-ttu-id="86902-250">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="86902-250">Close the page.</span></span>
