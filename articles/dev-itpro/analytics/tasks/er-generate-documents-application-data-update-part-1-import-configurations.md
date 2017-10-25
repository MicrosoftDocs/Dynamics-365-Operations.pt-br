--- 
title: "Importar configurações para gerar documentos com atualização de dados de aplicativo para relatório eletrônico (ER)"
description: "Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, \"ER Criar um provedor de configuração e marcá-lo como ativo\"."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
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
ms.sourcegitcommit: b49cfe39732a450e4723419c50d8bcc3d64b7ec9
ms.openlocfilehash: 7f2fe7228856ff6377be7d527b32d3ddee252981
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="import-configurations-to-generate-documents-with-application-data-update-for-electronic-reporting-er"></a><span data-ttu-id="38d59-103">Importar configurações para gerar documentos com atualização de dados de aplicativo para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="38d59-103">Import configurations to generate documents with application data update for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38d59-104">Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, "ER Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="38d59-104">To complete the steps in this procedure, you must first complete the procedure, “ER Create a configuration provider and mark it as active”.</span></span>

<span data-ttu-id="38d59-105">As etapas desse procedimento explicam como criar configurações de Relatório eletrônico (ER) para gerar um documento eletrônico.</span><span class="sxs-lookup"><span data-stu-id="38d59-105">The steps in this procedure explain how to design Electronic reporting (ER) configurations to generate an electronic document.</span></span> <span data-ttu-id="38d59-106">Nesse procedimento, você importará as configurações de ER necessárias que foram criadas para a empresa exemplo, Litware, Inc., e usá-las para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="38d59-106">In this procedure, you will import the required ER configurations that have been created for the sample company, Litware, Inc. and use them to generate electronic documents.</span></span> <span data-ttu-id="38d59-107">Este procedimento é criado para usuários com a função atribuída de administrador do sistema ou desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="38d59-107">This procedure is created for users with the assigned role of system administrator or electronic reporting developer.</span></span> <span data-ttu-id="38d59-108">Estas etapas podem ser concluídas usando o conjunto de dados de DEMF.</span><span class="sxs-lookup"><span data-stu-id="38d59-108">These steps can be completed using the DEMF dataset.</span></span> <span data-ttu-id="38d59-109">Antes de começar, baixe e salve os arquivos listados no tópico da Ajuda, "Gerar documentos eletrônicos e atualizar dados do aplicativo com a ferramenta de Relatórios eletrônico" (generate-electronic-documents-update-application-data/).</span><span class="sxs-lookup"><span data-stu-id="38d59-109">Before you begin, download and save the files listed in the Help topic, “Generate electronic documents and update application data with ER tool” (generate-electronic-documents-update-application-data/).</span></span> <span data-ttu-id="38d59-110">Os arquivos são Intrastat (model).xml, Intrastat (mapping).xml e Intrastat (format).xml.</span><span class="sxs-lookup"><span data-stu-id="38d59-110">The files are Intrastat (model).xml, Intrastat (mapping).xml, and Intrastat (format).xml.</span></span>

1. <span data-ttu-id="38d59-111">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="38d59-111">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="38d59-112">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="38d59-112">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="38d59-113">Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="38d59-113">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
    * <span data-ttu-id="38d59-114">As etapas deste procedimento mostram como usar recursos de ER para concluir uma atualização de dados do aplicativo e como gerar um relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-114">The steps in this procedure show how to use ER capabilities to complete an application data update and how to generate a Intrastat report.</span></span> <span data-ttu-id="38d59-115">Os detalhes do processo de relatório são arquivados em tabelas do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38d59-115">The details of the reporting process are archived in the application tables.</span></span> <span data-ttu-id="38d59-116">Atualmente, quando o processo de relatório Intrastat é ativado no formulário Intrastat, o arquivamento é feito com base na lógica programada do código-fonte existente.</span><span class="sxs-lookup"><span data-stu-id="38d59-116">Currently, when the Intrastat reporting process is activated from the Intrastat form, archiving is done based on the logic programmed in the existing source code.</span></span> <span data-ttu-id="38d59-117">Nesse procedimento, você configurará uma lógica semelhante simplificada de dados de aplicativo usando somente a estrutura de ER.</span><span class="sxs-lookup"><span data-stu-id="38d59-117">In this procedure, you will configure a similar yet simplified logic of application data using only the ER framework.</span></span> <span data-ttu-id="38d59-118">Nenhuma alteração será feita ao código-fonte.</span><span class="sxs-lookup"><span data-stu-id="38d59-118">No changes will be made to the source code.</span></span>   

## <a name="import-er-configurations"></a><span data-ttu-id="38d59-119">Importar configurações de ER</span><span class="sxs-lookup"><span data-stu-id="38d59-119">Import ER configurations</span></span>
1. <span data-ttu-id="38d59-120">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="38d59-120">Click Reporting configurations.</span></span>
2. <span data-ttu-id="38d59-121">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="38d59-121">Click Exchange.</span></span>
3. <span data-ttu-id="38d59-122">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="38d59-122">Click Load from XML file.</span></span>
    * <span data-ttu-id="38d59-123">Importe a configuração do modelo de ER que contém o modelo de dados criado para ser usado como a fonte de dados para gerar o relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-123">Import the ER model configuration that contains the data model that is designed to be used as the data source for generating the Intrastat report.</span></span> <span data-ttu-id="38d59-124">Posteriormente, você estenderá esta definição do modelo de dados para usá-las para uma atualização de dados do aplicativo para arquivar detalhes do processo do relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-124">Later, you will extend this data model definition to use it for an application data update to archive details of the Intrastat reporting process.</span></span>   
    * <span data-ttu-id="38d59-125">Clique em Procurar e selecione o arquivo Intrastat (model).xml.</span><span class="sxs-lookup"><span data-stu-id="38d59-125">Click Browse and select the Intrastat (model).xml file.</span></span>  
4. <span data-ttu-id="38d59-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="38d59-126">Click OK.</span></span>
5. <span data-ttu-id="38d59-127">Na árvore, selecione 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="38d59-127">In the tree, select 'Intrastat (model)'.</span></span>
6. <span data-ttu-id="38d59-128">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="38d59-128">Click Designer.</span></span>
7. <span data-ttu-id="38d59-129">Na árvore, expanda 'Para documento de saída'.</span><span class="sxs-lookup"><span data-stu-id="38d59-129">In the tree, expand 'For outgoing document'.</span></span>
8. <span data-ttu-id="38d59-130">Na árvore, expanda 'Para documento de saída\Transações'.</span><span class="sxs-lookup"><span data-stu-id="38d59-130">In the tree, expand 'For outgoing document\Transactions'.</span></span>
    * <span data-ttu-id="38d59-131">Revise a estrutura do modelo de dados importado.</span><span class="sxs-lookup"><span data-stu-id="38d59-131">Review the structure of the imported data model.</span></span> <span data-ttu-id="38d59-132">Observe que o item raiz "Para documento de saída" é definido para especificar o fluxo de dados para obter dados do aplicativo e usá-lo como origem de dados para gerar o relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-132">Note that the root item ‘For outgoing document’ is defined to specify the data flow for getting data from the application and using it as data source to generate the Intrastat report.</span></span> <span data-ttu-id="38d59-133">As "Transações (lista de registros)" são usadas para representar a lista de transações Intrastat que devem ser reportadas.</span><span class="sxs-lookup"><span data-stu-id="38d59-133">The ‘Transactions (Record list)’ is used to represent the list of Intrastat transactions that must be reported.</span></span> <span data-ttu-id="38d59-134">Como você arquivará códigos de mercadoria reportados, o identificador exclusive de um código de mercadoria único "Id rec mercadoria (Int64)" é necessário neste fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="38d59-134">Because you will archive reported commodity codes, the unique identifier of a single commodity code ‘Commodity rec id (Int64)’ is needed in this data flow.</span></span>   
9. <span data-ttu-id="38d59-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38d59-135">Close the page.</span></span>
10. <span data-ttu-id="38d59-136">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="38d59-136">Click Exchange.</span></span>
11. <span data-ttu-id="38d59-137">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="38d59-137">Click Load from XML file.</span></span>
    * <span data-ttu-id="38d59-138">Importe a configuração de mapeamento de ER que especifica o fluxo de dados para obter dados do aplicativo e usá-los para gerar o relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-138">Import the ER mapping configuration that specifies the data flow for getting data from the application and then using it to generate the Intrastat report.</span></span> <span data-ttu-id="38d59-139">Posteriormente, você estenderá esta definição de mapeamento de modelo para obter dados do relatório Intrastat e usá-lo para atualização de dados do aplicativo para arquivar detalhes do processo do relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-139">Later, you will extend this model mapping definition to get data from the Intrastat report and use it for the application data update to archive details of Intrastat reporting process.</span></span>   
    * <span data-ttu-id="38d59-140">Clique em Procurar e selecione o arquivo Intrastat (mapping).xml.</span><span class="sxs-lookup"><span data-stu-id="38d59-140">Click Browse and select the Intrastat (mapping).xml file.</span></span>  
12. <span data-ttu-id="38d59-141">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="38d59-141">Click OK.</span></span>
13. <span data-ttu-id="38d59-142">Na árvore, expanda 'Intrastat (model)'.</span><span class="sxs-lookup"><span data-stu-id="38d59-142">In the tree, expand 'Intrastat (model)'.</span></span>
14. <span data-ttu-id="38d59-143">Na árvore, selecione 'Intrastat (modelo)\Intrastat (mapeamento)'.</span><span class="sxs-lookup"><span data-stu-id="38d59-143">In the tree, select 'Intrastat (model)\Intrastat (mapping)'.</span></span>
15. <span data-ttu-id="38d59-144">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="38d59-144">Click Designer.</span></span>
    * <span data-ttu-id="38d59-145">Observe que o mapeamento de modelo atual contém o valor "Para modelo" no campo Direção.</span><span class="sxs-lookup"><span data-stu-id="38d59-145">Note that the current model mapping contains the value ‘To model’ in the Direction field.</span></span> <span data-ttu-id="38d59-146">Isso significa que esse mapeamento modelo foi criado obtendo dados de aplicativo e armazenando-os no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="38d59-146">This means that this model mapping has been designed for getting data from the application and storing it in the data model.</span></span>  
16. <span data-ttu-id="38d59-147">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="38d59-147">Click Designer.</span></span>
17. <span data-ttu-id="38d59-148">Na árvore, expanda 'Lista'.</span><span class="sxs-lookup"><span data-stu-id="38d59-148">In the tree, expand 'List'.</span></span>
18. <span data-ttu-id="38d59-149">Na árvore, expanda 'Transações= Lista'.</span><span class="sxs-lookup"><span data-stu-id="38d59-149">In the tree, expand 'Transactions= List'.</span></span>
    * <span data-ttu-id="38d59-150">Reveja a estrutura de mapeamento do modelo que usa o modelo de dados que é filtrado com base no item raiz 'Para documento de saída'.</span><span class="sxs-lookup"><span data-stu-id="38d59-150">Review the structure of the model mapping that uses the data model that is filtered based on the root item, ‘For outgoing document.’</span></span> <span data-ttu-id="38d59-151">Observe que a fonte de dados adicionada, ‘Lista’, fornece acesso a dados de aplicativo necessários, que é a lista de registros de tabela intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-151">Note that the added data source, ‘List’ provides access to the required application data, which is the list of records from the Intrastat table.</span></span>  
19. <span data-ttu-id="38d59-152">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38d59-152">Close the page.</span></span>
20. <span data-ttu-id="38d59-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38d59-153">Close the page.</span></span>
21. <span data-ttu-id="38d59-154">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="38d59-154">Click Exchange.</span></span>
22. <span data-ttu-id="38d59-155">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="38d59-155">Click Load from XML file.</span></span>
    * <span data-ttu-id="38d59-156">Importe a configuração de formato de ER que especifica o layout do relatório Intrastat e o processo de preenchimento de dados para o relatório.</span><span class="sxs-lookup"><span data-stu-id="38d59-156">Import the ER format configuration that specifies the layout of the Intrastat report and the process of populating data to the report.</span></span> <span data-ttu-id="38d59-157">Posteriormente, você estenderá esta definição de formato para colocar dados do relatório Intrastat no modelo de dados e depois usá-lo para atualização de dados do aplicativo para arquivar os detalhes do processo do relatório Intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-157">Later, you will extend this format definition to put data from the Intrastat report in to the data model and then use it to update application data to archive the details of Intrastat reporting process.</span></span>   
    * <span data-ttu-id="38d59-158">Clique em Procurar e selecione o arquivo Intrastat (format).xml.</span><span class="sxs-lookup"><span data-stu-id="38d59-158">Click Browse and select the Intrastat (format).xml file.</span></span>  
23. <span data-ttu-id="38d59-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="38d59-159">Click OK.</span></span>
24. <span data-ttu-id="38d59-160">Na árvore, selecione 'Intrastat (modelo)\Intrastat (formato)'.</span><span class="sxs-lookup"><span data-stu-id="38d59-160">In the tree, select 'Intrastat (model)\Intrastat (format)'.</span></span>
25. <span data-ttu-id="38d59-161">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="38d59-161">Click Designer.</span></span>
26. <span data-ttu-id="38d59-162">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="38d59-162">Click Expand/collapse.</span></span>
27. <span data-ttu-id="38d59-163">Na árvore, selecione 'Arquivo\Declaração'.</span><span class="sxs-lookup"><span data-stu-id="38d59-163">In the tree, select 'File\Declaration'.</span></span>
28. <span data-ttu-id="38d59-164">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="38d59-164">Click the Mapping tab.</span></span>
29. <span data-ttu-id="38d59-165">Na árvore, selecione 'Arquivo'.</span><span class="sxs-lookup"><span data-stu-id="38d59-165">In the tree, select 'File'.</span></span>
    * <span data-ttu-id="38d59-166">Examine a estrutura do formato usado para gerar o relatório intrastat.</span><span class="sxs-lookup"><span data-stu-id="38d59-166">Review the structure of the format used to generate the Intrastat report.</span></span> <span data-ttu-id="38d59-167">Observe que ele foi criado para gerar um arquivo XML preenchendo dados do modelo de dados, que está baseado no item raiz 'Para documento de saída'.</span><span class="sxs-lookup"><span data-stu-id="38d59-167">Note that it is designed to generate an XML file by populating data from the data model, which is based on the root item ‘For outgoing document’.</span></span> <span data-ttu-id="38d59-168">Verifique se o nome do arquivo gerado está definido no formulário da caixa de diálogo (a fonte de dados 'fn' é usada para isso.)</span><span class="sxs-lookup"><span data-stu-id="38d59-168">Verify that the name for generated file is defined on the user dialog form (‘fn’ data source is used for that).</span></span>   
30. <span data-ttu-id="38d59-169">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="38d59-169">Close the page.</span></span>

