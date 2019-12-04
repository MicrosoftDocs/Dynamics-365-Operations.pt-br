---
title: Acesse metadados de aplicativos usando a configuração de ER
description: As etapas deste tópico explicam como um usuário do Regulatory configuration Service (RCS) pode criar um novo mapeamento modelo de relatório eletrônico (ER) por meio dos metadados no Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa8444b081650e3d375e6f28f47866c8d4853721
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772454"
---
# <a name="access-application-metadata-by-using-er-configuration"></a><span data-ttu-id="73255-103">Acesse metadados de aplicativos usando a configuração de ER</span><span class="sxs-lookup"><span data-stu-id="73255-103">Access application metadata by using ER configuration</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="73255-104">As etapas a seguir explicam como um usuário do Regulatory Configuration Service (RCS) na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um novo mapeamento de modelos de relatório eletrônico (ER) por meio dos metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="73255-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using the application metadata.</span></span> <span data-ttu-id="73255-105">Os metadados do aplicativo serão acessados por meio de uma configuração de metadados de ER contendo um conjunto de exemplo de metadados para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="73255-105">Application metadata will be accessed by using an ER metadata configuration that contains a sample set of metadata to access foreign trade transactions.</span></span> <span data-ttu-id="73255-106">Para concluir estas etapas no RCS, primeiro é necessário concluir as etapas no procedimento do tópico, [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="73255-106">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md) procedure.</span></span> <span data-ttu-id="73255-107">Em seguida, conclua as etapas no tópico [Preparar metadados do aplicativo a serem usados no RCS](prepare-application-metadata-rcs.md).</span><span class="sxs-lookup"><span data-stu-id="73255-107">Then complete the steps in the topic, [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73255-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="73255-108">Prerequisites</span></span>
1. <span data-ttu-id="73255-109">Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="73255-109">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="73255-110">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="73255-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="73255-111">Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="73255-111">If you don’t see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="import-metadata-configuration"></a><span data-ttu-id="73255-112">Importar configuração de metadados</span><span class="sxs-lookup"><span data-stu-id="73255-112">Import metadata configuration</span></span> 
1. <span data-ttu-id="73255-113">Clique em **Configurações de metadados**.</span><span class="sxs-lookup"><span data-stu-id="73255-113">Click **Metadata configurations**.</span></span> 
2. <span data-ttu-id="73255-114">Importe a configuração de metadados de ER que contém metadados que foram configurados para gerar documentos eletrônicos para negócios de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="73255-114">Import the ER metadata configuration that contains metadata that has been configured to generate electronic documents for foreign trade business.</span></span> <span data-ttu-id="73255-115">Essa configuração de metadados de ER foi exportada como arquivo XML enquanto as etapas no procedimento [Preparar metadados do aplicativo a serem usados no RCS](prepare-application-metadata-rcs.md) foram concluídas.</span><span class="sxs-lookup"><span data-stu-id="73255-115">This ER metadata configuration has been exported as XML file while the steps in the [Prepare application metadata to be used in RCS](prepare-application-metadata-rcs.md) procedure have been completed.</span></span> 
3. <span data-ttu-id="73255-116">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="73255-116">Click **Exchange**.</span></span> 
4. <span data-ttu-id="73255-117">Clique em **Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="73255-117">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="73255-118">Clique em **Procurar** e selecione o arquivo ‘Foreign trade metadata.xml’.</span><span class="sxs-lookup"><span data-stu-id="73255-118">Click **Browse** and select the ‘Foreign trade metadata.xml’ file.</span></span> 
6. <span data-ttu-id="73255-119">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73255-119">Click **OK**.</span></span> 
7. <span data-ttu-id="73255-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73255-120">Close the page.</span></span> 

## <a name="create-data-model-configuration"></a><span data-ttu-id="73255-121">Crie a configuração de modelo de dados</span><span class="sxs-lookup"><span data-stu-id="73255-121">Create data model configuration</span></span>
1. <span data-ttu-id="73255-122">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="73255-122">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="73255-123">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-123">Click **Create configuration** to open the drop dialog.</span></span> 
3. <span data-ttu-id="73255-124">No campo **Nome**, digite 'Modelo de comércio exterior'.</span><span class="sxs-lookup"><span data-stu-id="73255-124">In the **Name** field, type 'Foreign trade model'.</span></span> 
4. <span data-ttu-id="73255-125">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="73255-125">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="73255-126">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="73255-126">Click **Designer**.</span></span> 
6. <span data-ttu-id="73255-127">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-127">Click **New** to open the drop dialog.</span></span> 
7. <span data-ttu-id="73255-128">No campo **Nome**, digite 'Raiz'.</span><span class="sxs-lookup"><span data-stu-id="73255-128">In the **Name** field, type 'Root'.</span></span> 
8. <span data-ttu-id="73255-129">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73255-129">Click **Add**.</span></span> 
9. <span data-ttu-id="73255-130">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-130">Click **New** to open the drop dialog.</span></span> 
10. <span data-ttu-id="73255-131">No campo **Nome**, digite 'Transação'.</span><span class="sxs-lookup"><span data-stu-id="73255-131">In the **Name** field, type 'Transaction'.</span></span> 
11. <span data-ttu-id="73255-132">No campo **Tipo de item**, selecione **Lista de registros**.</span><span class="sxs-lookup"><span data-stu-id="73255-132">In the **Item type** field, select **Record list**.</span></span> 
12. <span data-ttu-id="73255-133">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73255-133">Click **Add**.</span></span> 
13. <span data-ttu-id="73255-134">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-134">Click **New** to open the drop dialog.</span></span> 
14. <span data-ttu-id="73255-135">No campo **Nome**, digite 'Código de mercadoria'.</span><span class="sxs-lookup"><span data-stu-id="73255-135">In the **Name** field, type 'Commodity code'.</span></span> 
15. <span data-ttu-id="73255-136">No campo **Tipo de item**, selecione **String**.</span><span class="sxs-lookup"><span data-stu-id="73255-136">In the **Item type** field, select **String**.</span></span> 
16. <span data-ttu-id="73255-137">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73255-137">Click **Add**.</span></span> 
17. <span data-ttu-id="73255-138">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-138">Click **New** to open the drop dialog.</span></span> 
18. <span data-ttu-id="73255-139">No campo **Nome**, digite 'Valor faturado'.</span><span class="sxs-lookup"><span data-stu-id="73255-139">In the **Name** field, type 'Invoiced amount'.</span></span> 
19. <span data-ttu-id="73255-140">No campo **Tipo de item**, selecione **Real**.</span><span class="sxs-lookup"><span data-stu-id="73255-140">In the **Item type** field, select **Real**.</span></span> 
20. <span data-ttu-id="73255-141">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73255-141">Click **Add**.</span></span> 
21. <span data-ttu-id="73255-142">Clique em **Novo** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-142">Click **New** to open the drop dialog.</span></span> 
22. <span data-ttu-id="73255-143">No campo **Nome**, digite 'Data'.</span><span class="sxs-lookup"><span data-stu-id="73255-143">In the **Name** field, type 'Date'.</span></span> 
23. <span data-ttu-id="73255-144">No campo **Tipo de item**, selecione **Data**.</span><span class="sxs-lookup"><span data-stu-id="73255-144">In the **Item type** field, select **Date**.</span></span> 
24. <span data-ttu-id="73255-145">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="73255-145">Click **Add**.</span></span> 
25. <span data-ttu-id="73255-146">Clique em **Referência raiz**.</span><span class="sxs-lookup"><span data-stu-id="73255-146">Click **Root reference**.</span></span> 
26. <span data-ttu-id="73255-147">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73255-147">Click **OK**.</span></span> 
27. <span data-ttu-id="73255-148">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73255-148">Click **Save**.</span></span> 
28. <span data-ttu-id="73255-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73255-149">Close the page.</span></span> 
29. <span data-ttu-id="73255-150">Clique em **Alterar status**.</span><span class="sxs-lookup"><span data-stu-id="73255-150">Click **Change status**.</span></span> 
30. <span data-ttu-id="73255-151">Clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="73255-151">Click **Complete**.</span></span> 
31. <span data-ttu-id="73255-152">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73255-152">Click **OK**.</span></span> 

## <a name="create-model-mapping-configuration"></a><span data-ttu-id="73255-153">Crie uma configuração de mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="73255-153">Create model mapping configuration</span></span> 
1. <span data-ttu-id="73255-154">Clique em **Criar configuração** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="73255-154">Click **Create configuration** to open the drop dialog.</span></span> 
2. <span data-ttu-id="73255-155">No campo **Novo**, insira 'Mapeamento de modelo baseado no modelo de comércio exterior de modelo de dados'.</span><span class="sxs-lookup"><span data-stu-id="73255-155">In the **New** field, enter 'Model Mapping based on data model Foreign trade model'.</span></span> 
3. <span data-ttu-id="73255-156">No campo **Nome**, digite 'Mapeamento de comércio exterior'.</span><span class="sxs-lookup"><span data-stu-id="73255-156">In the **Name** field, type 'Foreign trade mapping'.</span></span> 
4. <span data-ttu-id="73255-157">Clique em **Criar configuração**.</span><span class="sxs-lookup"><span data-stu-id="73255-157">Click **Create configuration**.</span></span> 
5. <span data-ttu-id="73255-158">Expanda a seção **Pré-requisitos**.</span><span class="sxs-lookup"><span data-stu-id="73255-158">Expand the **Prerequisites** section.</span></span> 
6. <span data-ttu-id="73255-159">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="73255-159">Click **Edit**.</span></span> 
7. <span data-ttu-id="73255-160">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="73255-160">Click **New**.</span></span> 
8. <span data-ttu-id="73255-161">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="73255-161">In the list, mark the selected row.</span></span> 
9. <span data-ttu-id="73255-162">No campo **Tipo de componente de pré-requisito**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="73255-162">In the **Prerequisite component type** field, select **Configuration**.</span></span> 
10. <span data-ttu-id="73255-163">Selecione a configuração de **Metadados de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="73255-163">Select **Foreign trade metadata** configuration.</span></span> 
11. <span data-ttu-id="73255-164">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73255-164">Click **Save**.</span></span> 
12. <span data-ttu-id="73255-165">Adicionamos a referência à versão 1 da configuração de 'Metadados de comércio exterior'.</span><span class="sxs-lookup"><span data-stu-id="73255-165">We added the reference to the version 1 of the ‘Foreign trade metadata’ configuration.</span></span> <span data-ttu-id="73255-166">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="73255-166">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 
13. <span data-ttu-id="73255-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73255-167">Close the page.</span></span> 
14. <span data-ttu-id="73255-168">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="73255-168">Click **Designer**.</span></span> 
15. <span data-ttu-id="73255-169">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="73255-169">Click **Designer**.</span></span> 
16. <span data-ttu-id="73255-170">Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**.</span><span class="sxs-lookup"><span data-stu-id="73255-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
17. <span data-ttu-id="73255-171">Clique em **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="73255-171">Click **Add root**.</span></span> 
18. <span data-ttu-id="73255-172">No campo **Nome**, digite 'Intrastat'.</span><span class="sxs-lookup"><span data-stu-id="73255-172">In the **Name** field, type 'Intrastat'.</span></span> 
19. <span data-ttu-id="73255-173">Selecione registros de tabela **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="73255-173">Select **Intrastat** table records.</span></span> 
20. <span data-ttu-id="73255-174">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="73255-174">Click **OK**.</span></span> 

> [!NOTE]
> <span data-ttu-id="73255-175">As 2 únicas tabelas foram oferecidas porque as 2 únicas tabelas foram adicionadas no conjunto de metadados em uso no momento.</span><span class="sxs-lookup"><span data-stu-id="73255-175">The only 2 tables were offered as the only 2 tables were added into the set of metadata which is currently in use.</span></span> 

21. <span data-ttu-id="73255-176">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="73255-176">Click **Bind**.</span></span> 
22. <span data-ttu-id="73255-177">Na árvore, expanda **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="73255-177">In the tree, expand **Intrastat**.</span></span> 
23. <span data-ttu-id="73255-178">Na árvore, selecione **Intrastat\AmountMST**.</span><span class="sxs-lookup"><span data-stu-id="73255-178">In the tree, select **Intrastat\AmountMST**.</span></span> 
24. <span data-ttu-id="73255-179">Na árvore, expanda **Transação = Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="73255-179">In the tree, expand **Transaction = Intrastat**.</span></span> 
25. <span data-ttu-id="73255-180">Na árvore, selecione **Transação = Intrastat\Valor faturado**.</span><span class="sxs-lookup"><span data-stu-id="73255-180">In the tree, select **Transaction = Intrastat\Invoiced amount**.</span></span> 
26. <span data-ttu-id="73255-181">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="73255-181">Click **Bind**.</span></span> 
27. <span data-ttu-id="73255-182">Na árvore, selecione **Intrastat\TransDate**.</span><span class="sxs-lookup"><span data-stu-id="73255-182">In the tree, select **Intrastat\TransDate**.</span></span> 
28. <span data-ttu-id="73255-183">Na árvore, selecione **Transação = Intrastat\Data**.</span><span class="sxs-lookup"><span data-stu-id="73255-183">In the tree, select **Transaction = Intrastat\Date**.</span></span> 
29. <span data-ttu-id="73255-184">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="73255-184">Click **Bind**.</span></span> 
30. <span data-ttu-id="73255-185">Na árvore, expanda **Intrastat\>Relações**.</span><span class="sxs-lookup"><span data-stu-id="73255-185">In the tree, expand **Intrastat\>Relations**.</span></span> 
31. <span data-ttu-id="73255-186">Na árvore, expanda **Intrastat\>Relações\IntrastatCommodity**.</span><span class="sxs-lookup"><span data-stu-id="73255-186">In the tree, expand **Intrastat\>Relations\IntrastatCommodity**.</span></span> 
32. <span data-ttu-id="73255-187">Na árvore, selecione **Intrastat\>Relações\IntrastatCommodity\Código**.</span><span class="sxs-lookup"><span data-stu-id="73255-187">In the tree, select **Intrastat\>Relations\IntrastatCommodity\Code**.</span></span> 
33. <span data-ttu-id="73255-188">Na árvore, selecione **Transação = Intrastat\Código de mercadoria**.</span><span class="sxs-lookup"><span data-stu-id="73255-188">In the tree, select **Transaction = Intrastat\Commodity code**.</span></span> 
34. <span data-ttu-id="73255-189">Clique em **Associar**.</span><span class="sxs-lookup"><span data-stu-id="73255-189">Click **Bind**.</span></span> 
35. <span data-ttu-id="73255-190">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="73255-190">Click **Validate**.</span></span> 

> [!NOTE]
> <span data-ttu-id="73255-191">Associamos com êxito elementos de modelo de dados com itens de fontes de dados que serão descritos usando detalhes de metadados de aplicativo da configuração de metadados de ER referenciada.</span><span class="sxs-lookup"><span data-stu-id="73255-191">We have successfully bound elements of data model with items of data sources that are described by using details of application metadata from the referred ER metadata configuration.</span></span> 
36. <span data-ttu-id="73255-192">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="73255-192">Click **Save**.</span></span> 
37. <span data-ttu-id="73255-193">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73255-193">Close the page.</span></span> 
38. <span data-ttu-id="73255-194">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="73255-194">Close the page.</span></span> 
39. <span data-ttu-id="73255-195">Se necessário, você pode estender o conjunto de metadados existente e exportar a nova versão concluída da configuração de metadados de ER.</span><span class="sxs-lookup"><span data-stu-id="73255-195">When needed, you can extend the existing set of metadata and then export the new completed version of ER metadata configuration.</span></span> <span data-ttu-id="73255-196">Em seguida, é possível importá-la para o RCS e atualizar os pré-requisitos da configuração de mapeamento de modelos configurado que se refere a uma nova versão da configuração de metadados importada.</span><span class="sxs-lookup"><span data-stu-id="73255-196">You can then import it to RCS, and update the prerequisites of the configured model mapping configuration referring to a new version of imported metadata configuration.</span></span> 

> [!NOTE]
> <span data-ttu-id="73255-197">Essa forma de obter informações sobre os metadados de aplicativos é a única disponível para aplicativos implantados localmente (quando dados corporativos locais (LBD) ou o modelo de implantação local são usados).</span><span class="sxs-lookup"><span data-stu-id="73255-197">This way of getting information about application metadata is the only one available for locally deployed applications (when local business data (LBD), or on-premises, deployment model is used).</span></span>
        
