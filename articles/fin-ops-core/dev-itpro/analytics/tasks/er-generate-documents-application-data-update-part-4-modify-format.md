---
title: Modificar formatos para gerar documentos com dados de aplicativo
description: Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 3 – Modificar modelo e mapeamento)".
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
ms.openlocfilehash: bbed62c80c14e7cfe96d38d43a5db39b0469d939
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184913"
---
# <a name="modify-formats-to-generate-documents-that-have-application-data"></a><span data-ttu-id="562c6-103">Modificar formatos para gerar documentos com dados de aplicativo</span><span class="sxs-lookup"><span data-stu-id="562c6-103">Modify formats to generate documents that have application data</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="562c6-104">Para concluir as etapas desse procedimento, você deve primeiramente concluir o procedimento, "ER Gerar documentos com atualização de dados de aplicativo (Parte 3: Modificar modelo e mapeamento)".</span><span class="sxs-lookup"><span data-stu-id="562c6-104">To complete the steps in this procedure, you must first complete the procedure, "ER Generate documents with application data update (Part 3: Modify model and mapping)".</span></span>

<span data-ttu-id="562c6-105">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico e atualizar os dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="562c6-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document and update application data.</span></span> <span data-ttu-id="562c6-106">Nesse procedimento, você modificará as configurações de ER não apenas para usá-las para gerar documentos eletrônicos, mas também para atualizar dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="562c6-106">In this procedure, you will modify the ER configurations to not just use them to generate electronic documents, but also to update application data.</span></span> <span data-ttu-id="562c6-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="562c6-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="562c6-108">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="562c6-108">These steps can be completed using the DEMF dataset.</span></span>


## <a name="modify-format-to-collect-details-of-reporting"></a><span data-ttu-id="562c6-109">Modificar o formato para obter detalhes de relatório</span><span class="sxs-lookup"><span data-stu-id="562c6-109">Modify format to collect details of reporting</span></span>
1. <span data-ttu-id="562c6-110">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="562c6-110">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="562c6-111">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-111">In the tree, expand 'Intrastat (model)'.</span></span>
3. <span data-ttu-id="562c6-112">Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-112">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
4. <span data-ttu-id="562c6-113">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="562c6-113">Click Designer.</span></span>
5. <span data-ttu-id="562c6-114">Na árvore, expanda 'Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-114">In the tree, expand 'File'.</span></span>
6. <span data-ttu-id="562c6-115">Na árvore, expanda 'Arquivo\Declaração'.</span><span class="sxs-lookup"><span data-stu-id="562c6-115">In the tree, expand 'File\Declaration'.</span></span>
7. <span data-ttu-id="562c6-116">Na árvore, selecione 'Arquivo\Declaração\Dados'.</span><span class="sxs-lookup"><span data-stu-id="562c6-116">In the tree, select 'File\Declaration\Data'.</span></span>
8. <span data-ttu-id="562c6-117">No campo Multiplicidade, selecione 'Um muitos'.</span><span class="sxs-lookup"><span data-stu-id="562c6-117">In the Multiplicity field, select 'One many'.</span></span>
    * <span data-ttu-id="562c6-118">Configure esse elemento de formato para arquivar detalhes do processo de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="562c6-118">Configure this format element to archive details of the Intrastat reporting process.</span></span> <span data-ttu-id="562c6-119">Esse item representa o registro de cabeçalho de arquivo morto.</span><span class="sxs-lookup"><span data-stu-id="562c6-119">This item represents the archive’s header record.</span></span>  
9. <span data-ttu-id="562c6-120">Na árvore, expanda 'Arquivo\Declaração\Dados'.</span><span class="sxs-lookup"><span data-stu-id="562c6-120">In the tree, expand 'File\Declaration\Data'.</span></span>
10. <span data-ttu-id="562c6-121">Na árvore, selecione 'Arquivo\Declaração\Dados\Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-121">In the tree, select 'File\Declaration\Data\Item'.</span></span>
11. <span data-ttu-id="562c6-122">No campo Multiplicidade, selecione 'Zero muitos'.</span><span class="sxs-lookup"><span data-stu-id="562c6-122">In the Multiplicity field, select 'Zero many'.</span></span>
    * <span data-ttu-id="562c6-123">Configure esse elemento de formato para arquivar detalhes do processo de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="562c6-123">Configure this format element to archive details of the Intrastat reporting process.</span></span> <span data-ttu-id="562c6-124">Esse item representará a lista de linhas arquivadas.</span><span class="sxs-lookup"><span data-stu-id="562c6-124">This item will represent the list of archived lines.</span></span>  
12. <span data-ttu-id="562c6-125">Na árvore, expanda 'Arquivo\Declaração\Dados\Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-125">In the tree, expand 'File\Declaration\Data\Item'.</span></span>
13. <span data-ttu-id="562c6-126">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1'.</span><span class="sxs-lookup"><span data-stu-id="562c6-126">In the tree, select 'File\Declaration\Data\Item\Dim1'.</span></span>
14. <span data-ttu-id="562c6-127">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-127">Select Yes in the Excluded field.</span></span>
    * <span data-ttu-id="562c6-128">Você não arquivará esses dados, dessa forma você poderá excluir esse elemento de formato dos dados de origem dos detalhes de relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="562c6-128">You will not archive this data, so you can exclude this format element from the data source of Intrastat reporting details.</span></span>  
15. <span data-ttu-id="562c6-129">Na árvore, expanda 'Arquivo\Declaração\Dados\Item\Dim1'.</span><span class="sxs-lookup"><span data-stu-id="562c6-129">In the tree, expand 'File\Declaration\Data\Item\Dim1'.</span></span>
16. <span data-ttu-id="562c6-130">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1\propriedade'.</span><span class="sxs-lookup"><span data-stu-id="562c6-130">In the tree, select 'File\Declaration\Data\Item\Dim1\property'.</span></span>
17. <span data-ttu-id="562c6-131">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-131">Select Yes in the Excluded field.</span></span>
18. <span data-ttu-id="562c6-132">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim1\data'.</span><span class="sxs-lookup"><span data-stu-id="562c6-132">In the tree, select 'File\Declaration\Data\Item\Dim1\date'.</span></span>
19. <span data-ttu-id="562c6-133">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-133">Select Yes in the Excluded field.</span></span>
20. <span data-ttu-id="562c6-134">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2'.</span><span class="sxs-lookup"><span data-stu-id="562c6-134">In the tree, select 'File\Declaration\Data\Item\Dim2'.</span></span>
21. <span data-ttu-id="562c6-135">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-135">Select Yes in the Excluded field.</span></span>
22. <span data-ttu-id="562c6-136">Na árvore, expanda 'Arquivo\Declaração\Dados\Item\Dim2'.</span><span class="sxs-lookup"><span data-stu-id="562c6-136">In the tree, expand 'File\Declaration\Data\Item\Dim2'.</span></span>
23. <span data-ttu-id="562c6-137">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2\propriedade'.</span><span class="sxs-lookup"><span data-stu-id="562c6-137">In the tree, select 'File\Declaration\Data\Item\Dim2\property'.</span></span>
24. <span data-ttu-id="562c6-138">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-138">Select Yes in the Excluded field.</span></span>
25. <span data-ttu-id="562c6-139">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim2\código'.</span><span class="sxs-lookup"><span data-stu-id="562c6-139">In the tree, select 'File\Declaration\Data\Item\Dim2\code'.</span></span>
26. <span data-ttu-id="562c6-140">Selecione Sim no campo Excluído.</span><span class="sxs-lookup"><span data-stu-id="562c6-140">Select Yes in the Excluded field.</span></span>
27. <span data-ttu-id="562c6-141">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim3'.</span><span class="sxs-lookup"><span data-stu-id="562c6-141">In the tree, select 'File\Declaration\Data\Item\Dim3'.</span></span>
    * <span data-ttu-id="562c6-142">Vários elementos de formato podem ter o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="562c6-142">Several format elements can have the same name.</span></span> <span data-ttu-id="562c6-143">Por exemplo, Dim. Você não pode reconhecê-los explicitamente quando usar este formato como uma fonte de dados para arquivar detalhes de relatório Intrastat, dessa forma você precisa definir os nomes alternativos para esses elementos de formato.</span><span class="sxs-lookup"><span data-stu-id="562c6-143">For example, Dim. You cannot explicitly recognize them when you use this format as a data source for archiving Intrastat reporting details, so you need to define the alternative names for these format elements.</span></span>   
28. <span data-ttu-id="562c6-144">No campo Nome, digite 'Valor'.</span><span class="sxs-lookup"><span data-stu-id="562c6-144">In the Name field, type 'Amount'.</span></span>
    * <span data-ttu-id="562c6-145">Valor</span><span class="sxs-lookup"><span data-stu-id="562c6-145">Amount</span></span>  
29. <span data-ttu-id="562c6-146">No campo Multiplicidade, selecione 'Exatamente um'.</span><span class="sxs-lookup"><span data-stu-id="562c6-146">In the Multiplicity field, select 'Exactly one'.</span></span>
30. <span data-ttu-id="562c6-147">Na árvore, selecione 'Arquivo\Declaração\Dados\Item\Dim4'.</span><span class="sxs-lookup"><span data-stu-id="562c6-147">In the tree, select 'File\Declaration\Data\Item\Dim4'.</span></span>
31. <span data-ttu-id="562c6-148">No campo Nome, digite 'Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-148">In the Name field, type 'Item'.</span></span>
    * <span data-ttu-id="562c6-149">Item</span><span class="sxs-lookup"><span data-stu-id="562c6-149">Item</span></span>  
32. <span data-ttu-id="562c6-150">No campo Multiplicidade, selecione 'Exatamente um'.</span><span class="sxs-lookup"><span data-stu-id="562c6-150">In the Multiplicity field, select 'Exactly one'.</span></span>
    * <span data-ttu-id="562c6-151">Além dos elementos de formato de design, os detalhes do relatório Intrastat devem ser arquivados: identificação de registro exclusivo de cada item de mercadorias relatado e nome de arquivo gerado.</span><span class="sxs-lookup"><span data-stu-id="562c6-151">In addition to the design format elements, the following Intrastat reporting details must be archived: unique record identification of each reported commodity item and name of the generated file.</span></span> <span data-ttu-id="562c6-152">Como os dados não serão preenchidos no relatório Intrastat, você precisará adicionar o formato relacionado a esses elementos de detalhe como itens de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="562c6-152">Because this data will not be populated in the Intrastat report, you need to add the format that is related to these detail elements as data source items.</span></span>  
33. <span data-ttu-id="562c6-153">Na árvore, selecione 'Arquivo\Declaração\Dados'.</span><span class="sxs-lookup"><span data-stu-id="562c6-153">In the tree, select 'File\Declaration\Data'.</span></span>
34. <span data-ttu-id="562c6-154">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="562c6-154">Click Add to open the drop dialog.</span></span>
35. <span data-ttu-id="562c6-155">Na árvore, selecione 'Origem de dados\Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-155">In the tree, select 'Data source\Item'.</span></span>
36. <span data-ttu-id="562c6-156">No campo Nome, digite 'Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-156">In the Name field, type 'File name'.</span></span>
    * <span data-ttu-id="562c6-157">Nome do arquivo</span><span class="sxs-lookup"><span data-stu-id="562c6-157">File name</span></span>  
37. <span data-ttu-id="562c6-158">No campo Tipo de dados, selecione 'String'.</span><span class="sxs-lookup"><span data-stu-id="562c6-158">In the Data type field, select 'String'.</span></span>
38. <span data-ttu-id="562c6-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="562c6-159">Click OK.</span></span>
39. <span data-ttu-id="562c6-160">Na árvore, selecione 'Arquivo\Declaração\Dados\Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-160">In the tree, select 'File\Declaration\Data\Item'.</span></span>
40. <span data-ttu-id="562c6-161">Clique em Adicionar Item.</span><span class="sxs-lookup"><span data-stu-id="562c6-161">Click Add Item.</span></span>
41. <span data-ttu-id="562c6-162">No campo Nome, digite 'Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="562c6-162">In the Name field, type 'Commodity rec id'.</span></span>
    * <span data-ttu-id="562c6-163">Id reg de mercadoria</span><span class="sxs-lookup"><span data-stu-id="562c6-163">Commodity rec id</span></span>  
42. <span data-ttu-id="562c6-164">No campo Tipo de dados, selecione 'Int64'.</span><span class="sxs-lookup"><span data-stu-id="562c6-164">In the Data type field, select 'Int64'.</span></span>
43. <span data-ttu-id="562c6-165">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="562c6-165">Click OK.</span></span>
44. <span data-ttu-id="562c6-166">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="562c6-166">Click the Mapping tab.</span></span>
45. <span data-ttu-id="562c6-167">Na árvore, selecione 'Arquivo\Declaração\Dados\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-167">In the tree, select 'File\Declaration\Data\File name'.</span></span>
46. <span data-ttu-id="562c6-168">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-168">Click Bind.</span></span>
47. <span data-ttu-id="562c6-169">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-169">In the tree, expand 'model'.</span></span>
48. <span data-ttu-id="562c6-170">Na árvore, expanda 'modelo\Transações'.</span><span class="sxs-lookup"><span data-stu-id="562c6-170">In the tree, expand 'model\Transactions'.</span></span>
49. <span data-ttu-id="562c6-171">Na árvore, selecione 'Arquivo\Declaração\Dados\Item = model.Transactions\Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="562c6-171">In the tree, select 'File\Declaration\Data\Item =  model.Transactions\Commodity rec id'.</span></span>
50. <span data-ttu-id="562c6-172">Na árvore, selecione 'modelo\Transações\Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="562c6-172">In the tree, select 'model\Transactions\Commodity rec id'.</span></span>
51. <span data-ttu-id="562c6-173">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-173">Click Bind.</span></span>
52. <span data-ttu-id="562c6-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="562c6-174">Click Save.</span></span>

## <a name="modify-format-to-memorize-details-of-reporting"></a><span data-ttu-id="562c6-175">Modificar o formato para memorizar detalhes de relatório</span><span class="sxs-lookup"><span data-stu-id="562c6-175">Modify format to memorize details of reporting</span></span>
1. <span data-ttu-id="562c6-176">Clique em Mapear formato para modelo.</span><span class="sxs-lookup"><span data-stu-id="562c6-176">Click Map format to model.</span></span>
2. <span data-ttu-id="562c6-177">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="562c6-177">Click New.</span></span>
3. <span data-ttu-id="562c6-178">No campo Definição, insira ou selecione o item raiz 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-178">In the Definition field, enter or select the ‘For application data update’ root item.</span></span>
    * <span data-ttu-id="562c6-179">Para atualização de dados do aplicativo</span><span class="sxs-lookup"><span data-stu-id="562c6-179">For application data update</span></span>  
4. <span data-ttu-id="562c6-180">No campo Nome, digite "Mapeamento de dados de atualização".</span><span class="sxs-lookup"><span data-stu-id="562c6-180">In the Name field, type 'Mapping to update data'.</span></span>
    * <span data-ttu-id="562c6-181">Mapeamento para atualizar dados</span><span class="sxs-lookup"><span data-stu-id="562c6-181">Mapping to update data</span></span>  
5. <span data-ttu-id="562c6-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="562c6-182">Click Save.</span></span>
    * <span data-ttu-id="562c6-183">Este mapeamento define como os detalhes do relatório Intrastat são reunidos no modelo de dados, a estrutura especificada pelo item raiz selecionado 'Para atualização de dados do aplicativo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-183">This mapping defines how the details of the Intrastat report are collected in the data model, the structure of which is specified by the selected root item ‘For application data update’.</span></span> <span data-ttu-id="562c6-184">Esses detalhes, o mapeamento de modelo com o mesmo item raiz “Para atualização de dados do aplicativo”, e a direção e “Para destino” serão usados para a atualização de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="562c6-184">These details, the model mapping with same root item ‘For application data update’, and the direction ‘To destination’ will be used for the application data update.</span></span> <span data-ttu-id="562c6-185">A atualização de dados do aplicativo é iniciada imediatamente após o relatório Intrastat de saída ser gerado.</span><span class="sxs-lookup"><span data-stu-id="562c6-185">The application data update starts immediately after the outgoing Intrastat report is generated.</span></span> <span data-ttu-id="562c6-186">Observe que a atualização de dados do aplicativo pode ser ignorada no tempo de execução, mas o modelo de dados deve estar vazio (contendo a lista de registros vazia).</span><span class="sxs-lookup"><span data-stu-id="562c6-186">Note that the application data update can be skipped at run-time, but the data model must be empty (containing empty record list).</span></span>   
6. <span data-ttu-id="562c6-187">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="562c6-187">Click Designer.</span></span>
    * <span data-ttu-id="562c6-188">Observe que o formato de relatório Intrastat de saída será adicionada, por padrão, como uma origem de dados para este mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="562c6-188">Note that the outgoing Intrastat report format is added by default as a data source for this model mapping.</span></span>  
    * <span data-ttu-id="562c6-189">Associe os elementos do relatório criado (apresentado como a fonte de dados) aos elementos do modelo de dados, que é filtrado com base no item raiz do modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="562c6-189">Bind elements of the designed report (presented as data source) to elements of the data model, which is filtered based on the selected model’s root item.</span></span>  
7. <span data-ttu-id="562c6-190">Na árvore, expanda 'Archive header'.</span><span class="sxs-lookup"><span data-stu-id="562c6-190">In the tree, expand 'Archive header'.</span></span>
8. <span data-ttu-id="562c6-191">Na árvore, expanda 'Cabeçalho do arquivo morto\Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="562c6-191">In the tree, expand 'Archive header\Archive lines'.</span></span>
9. <span data-ttu-id="562c6-192">Na árvore, expanda 'format'.</span><span class="sxs-lookup"><span data-stu-id="562c6-192">In the tree, expand 'format'.</span></span>
10. <span data-ttu-id="562c6-193">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-193">In the tree, expand 'format\Declaration: XML Element(Declaration)'.</span></span>
11. <span data-ttu-id="562c6-194">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-194">In the tree, expand 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)'.</span></span>
12. <span data-ttu-id="562c6-195">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-195">In the tree, expand 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)'.</span></span>
13. <span data-ttu-id="562c6-196">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)\Dim3: Elemento XML 1..1 (Valor)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-196">In the tree, expand 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)\Dim3: XML Element 1..1 (Amount)'.</span></span>
14. <span data-ttu-id="562c6-197">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\*(Item)\Dim4: Elemento XML 1..1 (Item)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-197">In the tree, expand 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)\Dim4: XML Element 1..1 (Item)'.</span></span>
15. <span data-ttu-id="562c6-198">Na árvore, selecione 'Cabeçalho do arquivo morto\Número de linhas'.</span><span class="sxs-lookup"><span data-stu-id="562c6-198">In the tree, select 'Archive header\Number of lines'.</span></span>
16. <span data-ttu-id="562c6-199">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="562c6-199">Click Edit.</span></span>
17. <span data-ttu-id="562c6-200">Na árvore, selecione 'Lista\CONTAGEM'.</span><span class="sxs-lookup"><span data-stu-id="562c6-200">In the tree, select 'List\COUNT'.</span></span>
18. <span data-ttu-id="562c6-201">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="562c6-201">Click Add function.</span></span>
19. <span data-ttu-id="562c6-202">Na árvore, expanda 'format'.</span><span class="sxs-lookup"><span data-stu-id="562c6-202">In the tree, expand 'format'.</span></span>
20. <span data-ttu-id="562c6-203">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-203">In the tree, expand 'format\Declaration: XML Element(Declaration)'.</span></span>
21. <span data-ttu-id="562c6-204">Na árvore, expanda 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-204">In the tree, expand 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)'.</span></span>
22. <span data-ttu-id="562c6-205">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-205">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)'.</span></span>
23. <span data-ttu-id="562c6-206">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="562c6-206">Click Add data source.</span></span>
24. <span data-ttu-id="562c6-207">No campo Fórmula, insira 'COUNT(format.Declaration.Data.Item)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-207">In the Formula field, enter 'COUNT(format.Declaration.Data.Item)'.</span></span>
    * <span data-ttu-id="562c6-208">CONTAGEM (formato.Declaração.Dados.Item)</span><span class="sxs-lookup"><span data-stu-id="562c6-208">COUNT(format.Declaration.Data.Item)</span></span>  
25. <span data-ttu-id="562c6-209">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="562c6-209">Click Save.</span></span>
26. <span data-ttu-id="562c6-210">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="562c6-210">Close the page.</span></span>
27. <span data-ttu-id="562c6-211">Na árvore, selecione 'Cabeçalho do arquivo morto\Nome do arquivo'.</span><span class="sxs-lookup"><span data-stu-id="562c6-211">In the tree, select 'Archive header\File name'.</span></span>
28. <span data-ttu-id="562c6-212">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Nome do arquivo: Cadeia de caracteres do item (Nome do arquivo)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-212">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\File name: Item String(File name)'.</span></span>
29. <span data-ttu-id="562c6-213">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-213">Click Bind.</span></span>
30. <span data-ttu-id="562c6-214">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)\Dim4: Elemento XML 1..1 (Item)\número: Cadeia de caracteres(número)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-214">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)\Dim4: XML Element 1..1 (Item)\number: String(number)'.</span></span>
31. <span data-ttu-id="562c6-215">Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas\Número do Item'.</span><span class="sxs-lookup"><span data-stu-id="562c6-215">In the tree, select 'Archive header\Archive lines\Item number'.</span></span>
32. <span data-ttu-id="562c6-216">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-216">Click Bind.</span></span>
33. <span data-ttu-id="562c6-217">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Data: Elemento XML 1..\* (Data)\Item: Elemento XML 0..\* (Item)\Dim3: Elemento XML 1..1 (Valor)\valor: Numérico Real(valor)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-217">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)\Dim3: XML Element 1..1 (Amount)\value: Numeric Real(value)'.</span></span>
34. <span data-ttu-id="562c6-218">Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas\Valor'.</span><span class="sxs-lookup"><span data-stu-id="562c6-218">In the tree, select 'Archive header\Archive lines\Amount'.</span></span>
35. <span data-ttu-id="562c6-219">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-219">Click Bind.</span></span>
36. <span data-ttu-id="562c6-220">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)\Id reg de mercadoria: Item Int64(Id reg. mercadoria)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-220">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)\Commodity rec id: Item Int64(Commodity rec id)'.</span></span>
37. <span data-ttu-id="562c6-221">Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas\Id reg. mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="562c6-221">In the tree, select 'Archive header\Archive lines\Commodity rec id'.</span></span>
38. <span data-ttu-id="562c6-222">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-222">Click Bind.</span></span>
39. <span data-ttu-id="562c6-223">Na árvore, selecione 'Cabeçalho do arquivo morto\Arquivar linhas'.</span><span class="sxs-lookup"><span data-stu-id="562c6-223">In the tree, select 'Archive header\Archive lines'.</span></span>
40. <span data-ttu-id="562c6-224">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)\Item: Elemento XML 0..\* (Item)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-224">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)\Item: XML Element 0..\* (Item)'.</span></span>
41. <span data-ttu-id="562c6-225">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-225">Click Bind.</span></span>
42. <span data-ttu-id="562c6-226">Na árvore, selecione 'Cabeçalho do arquivo-morto'.</span><span class="sxs-lookup"><span data-stu-id="562c6-226">In the tree, select 'Archive header'.</span></span>
43. <span data-ttu-id="562c6-227">Na árvore, selecione 'formato\Declaração: Elemento XML(Declaração)\Dados: Elemento XML 1..\* (Dados)'.</span><span class="sxs-lookup"><span data-stu-id="562c6-227">In the tree, select 'format\Declaration: XML Element(Declaration)\Data: XML Element 1..\* (Data)'.</span></span>
44. <span data-ttu-id="562c6-228">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="562c6-228">Click Bind.</span></span>
45. <span data-ttu-id="562c6-229">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="562c6-229">Click Save.</span></span>
46. <span data-ttu-id="562c6-230">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="562c6-230">Close the page.</span></span>
47. <span data-ttu-id="562c6-231">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="562c6-231">Close the page.</span></span>
48. <span data-ttu-id="562c6-232">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="562c6-232">Close the page.</span></span>
