---
title: Acessar metadados do aplicativo usando aplicativos conectados
description: As etapas deste tópico explicam como um usuário do Regulatory Configuration Service (RCS) pode criar um novo mapeamento de modelo de relatório eletrônico (ER) usando os metadados.
author: NickSelin
manager: AnnBe
ms.date: 06/29/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e0a769bdc86d36f8c5373c0301ed55f26757b405
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562895"
---
# <a name="access-application-metadata-by-using-connected-applications"></a><span data-ttu-id="2bb98-103">Acessar metadados do aplicativo usando aplicativos conectados</span><span class="sxs-lookup"><span data-stu-id="2bb98-103">Access application metadata by using connected applications</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="2bb98-104">As etapas a seguir explicam como um usuário do Regulatory Configuration Service (RCS) na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode criar um novo mapeamento de modelo de relatório eletrônico (ER) por meio de metadados do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2bb98-104">The following steps explain how a Regulatory configuration service (RCS) user in the System Administrator or Electronic Reporting Developer role can design a new Electronic reporting (ER) model mapping by using metadata in Finance and Operations.</span></span> <span data-ttu-id="2bb98-105">Os metadados do aplicativo serão acessados online usando o aplicativo conectado de RCS.</span><span class="sxs-lookup"><span data-stu-id="2bb98-105">Application metadata will be accessed online by using the RCS connected application.</span></span> <span data-ttu-id="2bb98-106">O mapeamento de modelo ER de exemplo será configurado para acessar transações de comércio exterior.</span><span class="sxs-lookup"><span data-stu-id="2bb98-106">Sample ER model mapping will be configured to access foreign trade transactions.</span></span> <span data-ttu-id="2bb98-107">Para concluir estas etapas, no RCS, primeiro conclua as etapas do tópico [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2bb98-107">To complete these steps, in RCS you must first complete the steps in the topic, [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="2bb98-108">Se você não concluiu as etapas do tópico [Acessar metadados do aplicativo usando a configuração ER](access-application-metadata-er-configuration.md), vá para a [página Exemplos de relatórios eletrônicos](https://go.microsoft.com/fwlink/?linkid=862266) para baixar e salvar as seguintes configurações de ER: Metadados de comércio exterior.xml; Modelo de comércio exterior.xml; Mapeamento de comércio exterior.xml e conclua as etapas no procedimento.</span><span class="sxs-lookup"><span data-stu-id="2bb98-108">If you have not completed the steps in the topic, [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md), go to the [Electronic reporting examples page](https://go.microsoft.com/fwlink/?linkid=862266) to download and save the following ER configurations: Foreign trade metadata.xml; Foreign trade model.xml; Foreign trade mapping.xml, and then complete the steps in the procedure.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2bb98-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2bb98-109">Prerequisites</span></span>
1. <span data-ttu-id="2bb98-110">Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-110">Go to **All workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="2bb98-111">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-111">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="2bb98-112">Se você não visualizar este provedor de configuração, conclua as etapas no procedimento [Criar provedores de configuração e marcá-los como ativos](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="2bb98-112">If you don't see this configuration provider, complete the steps in the procedure [Create configuration providers and mark them as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 

## <a name="get-required-er-configurations"></a><span data-ttu-id="2bb98-113">Obtenha configurações de ER necessárias</span><span class="sxs-lookup"><span data-stu-id="2bb98-113">Get required ER configurations</span></span>
1. <span data-ttu-id="2bb98-114">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-114">Click **Reporting configurations**.</span></span> 
2. <span data-ttu-id="2bb98-115">Se você já tiver concluído as etapas no procedimento [Acessar metadados do aplicativo usando a configuração ER](access-application-metadata-er-configuration.md), já terá todas as configurações ER necessárias (metadados de comércio exterior, configurações de modelo e mapeamento) na instância do RCS atual.</span><span class="sxs-lookup"><span data-stu-id="2bb98-115">If you already completed the steps in the [Access application metadata by using ER configuration](access-application-metadata-er-configuration.md) procedure, you already have all necessary ER configurations (foreign trade metadata, model and mapping configurations) in the current RCS instance.</span></span> <span data-ttu-id="2bb98-116">Você pode ignorar todas as etapas restantes desta subtarefa.</span><span class="sxs-lookup"><span data-stu-id="2bb98-116">You can skip all the remaining steps of this sub-task.</span></span> 
3. <span data-ttu-id="2bb98-117">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-117">Click **Exchange**.</span></span> 
4. <span data-ttu-id="2bb98-118">Clique em **Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-118">Click **Load from XML file**.</span></span> 
5. <span data-ttu-id="2bb98-119">Clique em **Procurar** e selecione o arquivo **Metadados de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-119">Click **Browse** and select the **Foreign trade metadata.xml** file.</span></span> 
6. <span data-ttu-id="2bb98-120">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-120">Click **OK**.</span></span> 
7. <span data-ttu-id="2bb98-121">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-121">Click **Exchange**.</span></span> 
8. <span data-ttu-id="2bb98-122">Clique em **Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-122">Click **Load from XML file**.</span></span> 
9. <span data-ttu-id="2bb98-123">Clique em **Procurar** e selecione o arquivo **Modelo de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-123">Click **Browse** and select the **Foreign trade model.xml** file.</span></span> 
10. <span data-ttu-id="2bb98-124">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-124">Click **OK**.</span></span> 
11. <span data-ttu-id="2bb98-125">Clique em **Taxa de câmbio**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-125">Click **Exchange**.</span></span> 
12. <span data-ttu-id="2bb98-126">Clique em **Carregar de um arquivo XML**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-126">Click **Load from XML file**.</span></span> 
13. <span data-ttu-id="2bb98-127">Clique em **Procurar** e selecione o arquivo **Mapeamento de comércio exterior.xml**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-127">Click **Browse** and select the **Foreign trade mapping.xml** file.</span></span> 
14. <span data-ttu-id="2bb98-128">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-128">Click **OK**.</span></span> 

## <a name="register-a-connected-application"></a><span data-ttu-id="2bb98-129">Registre um aplicativo conectado</span><span class="sxs-lookup"><span data-stu-id="2bb98-129">Register a connected application</span></span>
1. <span data-ttu-id="2bb98-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-130">Close the page.</span></span> 
2. <span data-ttu-id="2bb98-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-131">Close the page.</span></span> 
3. <span data-ttu-id="2bb98-132">Vá para **Todos os espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-132">Go to **All workspaces** > **Electronic reporting**.</span></span> 
4. <span data-ttu-id="2bb98-133">Clique em **Aplicativos conectados**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-133">Click **Connected applications**.</span></span> 
5. <span data-ttu-id="2bb98-134">Verifique se o aplicativo configurado é baseado em Azure e está disponível para o usuário do RCS atual.</span><span class="sxs-lookup"><span data-stu-id="2bb98-134">Make sure that the configured application is Azure based and accessible for the current RCS user.</span></span> <span data-ttu-id="2bb98-135">Também é necessário que o usuário do RCS atual tenha acesso ao aplicativo selecionado e esteja registrado como um usuário desse aplicativo com uma função que lhes concede privilégios para acessar metadados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bb98-135">It is also required that the current RCS user has access to the selected application and has been registered as a user of this application playing a role giving them privileges to access application's metadata.</span></span> 
6. <span data-ttu-id="2bb98-136">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-136">Click **New**.</span></span> 
7. <span data-ttu-id="2bb98-137">No campo **Nome**, digite 'MyConnectedApp'.</span><span class="sxs-lookup"><span data-stu-id="2bb98-137">In the **Name** field, type 'MyConnectedApp'.</span></span> 
8. <span data-ttu-id="2bb98-138">No campo **Aplicativo**, digite 'https:// mycompany.operations.dynamics.com'.</span><span class="sxs-lookup"><span data-stu-id="2bb98-138">In the **Application** field, type 'https:// mycompany.operations.dynamics.com'.</span></span> 
9. <span data-ttu-id="2bb98-139">No campo **Locatário**, digite "mycompany.onmicrosoft.com".</span><span class="sxs-lookup"><span data-stu-id="2bb98-139">In the **Tenant** field, type 'mycompany.onmicrosoft.com'.</span></span> 
10. <span data-ttu-id="2bb98-140">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-140">Click **Save**.</span></span> 
11. <span data-ttu-id="2bb98-141">Quando você verificar a conexão com o aplicativo, na página **Conectar-se ao aplicativo remoto**, clique no link **Clique aqui para conectar-se ao aplicativo remoto selecionado**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-141">When you check connection to configured application, on the **Connect to remote application** page click **Click here to connect to selected remote application** link.</span></span> 
12. <span data-ttu-id="2bb98-142">Clique em **Verifique a conexão**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-142">Click **Check connection**.</span></span> 
13. <span data-ttu-id="2bb98-143">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-143">Click **Close**.</span></span> 
14. <span data-ttu-id="2bb98-144">Quando a validação da conexão for bem-sucedida, os detalhes da versão e do locatário serão atualizados para o aplicativo configurado na grade atual.</span><span class="sxs-lookup"><span data-stu-id="2bb98-144">When the connection validation succeeded, version and tenant details will be updated for the configured application in the current grid.</span></span> 

## <a name="review-existing-model-mapping-configuration"></a><span data-ttu-id="2bb98-145">Reveja a configuração de mapeamento do modelo existente</span><span class="sxs-lookup"><span data-stu-id="2bb98-145">Review existing model mapping configuration</span></span>
1. <span data-ttu-id="2bb98-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-146">Close the page.</span></span> 
2. <span data-ttu-id="2bb98-147">Clique em **Configurações de relatórios**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-147">Click **Reporting configurations**.</span></span> 
3. <span data-ttu-id="2bb98-148">Na árvore, expanda **Modelo de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-148">In the tree, expand **Foreign trade model**.</span></span> 
4. <span data-ttu-id="2bb98-149">Na árvore, selecione **Modelo de comércio exterior\Mapeamento de comércio exterior**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-149">In the tree, select **Foreign trade model\Foreign trade mapping**.</span></span> 
5. <span data-ttu-id="2bb98-150">Expanda a seção **Pré-requisitos**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-150">Expand the **Prerequisites** section.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2bb98-151">Atualmente, o mapeamento se refere à configuração dos metadados.</span><span class="sxs-lookup"><span data-stu-id="2bb98-151">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2bb98-152">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="2bb98-152">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

6. <span data-ttu-id="2bb98-153">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-153">Click **Designer**.</span></span> 
7. <span data-ttu-id="2bb98-154">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-154">Click **Designer**.</span></span> 
8. <span data-ttu-id="2bb98-155">Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-155">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
9. <span data-ttu-id="2bb98-156">Clique em **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-156">Click **Add root**.</span></span> 
10. <span data-ttu-id="2bb98-157">No campo **Tabela**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2bb98-157">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2bb98-158">Atualmente, o mapeamento se refere à configuração dos metadados.</span><span class="sxs-lookup"><span data-stu-id="2bb98-158">Currently, this mapping refers to the metadata configuration.</span></span> <span data-ttu-id="2bb98-159">Os metadados de aplicativos dessa configuração serão oferecidos durante a criação desse mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="2bb98-159">Application metadata from this configuration will be offered while this model mapping will be designed.</span></span> 

11. <span data-ttu-id="2bb98-160">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-160">Click **Cancel**.</span></span> 
12. <span data-ttu-id="2bb98-161">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-161">Close the page.</span></span> 
13. <span data-ttu-id="2bb98-162">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-162">Close the page.</span></span> 

## <a name="assign-connected-application-to-model-mapping"></a><span data-ttu-id="2bb98-163">Atribua um aplicativo conectado ao mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="2bb98-163">Assign connected application to model mapping</span></span> 
1. <span data-ttu-id="2bb98-164">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-164">Click **Edit**.</span></span> 
2. <span data-ttu-id="2bb98-165">Selecione o aplicativo **MyConnectedApp**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-165">Select **MyConnectedApp** application.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2bb98-166">Atualmente, este mapeamento refere-se aos metadados do aplicativo conectado selecionado.</span><span class="sxs-lookup"><span data-stu-id="2bb98-166">Currently, this mapping refers to the metadata of the selected connected application.</span></span> <span data-ttu-id="2bb98-167">Quando o mesmo mapeamento referir-se à configuração de metadados e ao aplicativo associado simultaneamente, os metadados do aplicativo conectado serão usados.</span><span class="sxs-lookup"><span data-stu-id="2bb98-167">When the same mapping refers to metadata configuration and connected application at the same time, metadata of the connected application will be used.</span></span> 

3. <span data-ttu-id="2bb98-168">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-168">Click **Designer**.</span></span> 
4. <span data-ttu-id="2bb98-169">Clique em **Designer**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-169">Click **Designer**.</span></span> 
5. <span data-ttu-id="2bb98-170">Na árvore, selecione **Dynamics 365 for Operations\Registros da tabela**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-170">In the tree, select **Dynamics 365 for Operations\Table records**.</span></span> 
6. <span data-ttu-id="2bb98-171">Clique em **Adicionar raiz**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-171">Click **Add root**.</span></span> 
7. <span data-ttu-id="2bb98-172">No campo **Tabela**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="2bb98-172">In the **Table** field, enter or select a value.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2bb98-173">Mais de duas tabelas do aplicativo foram oferecidas agora pois esse mapeamento utiliza todos os metadados do aplicativo conectado que foram atribuídos a ele.</span><span class="sxs-lookup"><span data-stu-id="2bb98-173">More than two application tables were offered now as this mapping uses all the metadata of the connected application that has been assigned for it.</span></span> 

8. <span data-ttu-id="2bb98-174">Clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-174">Click **Cancel**.</span></span> 
9. <span data-ttu-id="2bb98-175">Clique em **Validar**.</span><span class="sxs-lookup"><span data-stu-id="2bb98-175">Click **Validate**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="2bb98-176">Associamos com êxito elementos de modelo de dados com itens de fontes de dados que serão descritos usando detalhes de metadados do aplicativo conectado que foram atribuídos a este mapeamento.</span><span class="sxs-lookup"><span data-stu-id="2bb98-176">We successfully bound elements of data model with items of data sources that are described by using details of metadata of the connected application that has been assigned for this mapping.</span></span> 

10. <span data-ttu-id="2bb98-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-177">Close the page.</span></span> 
11. <span data-ttu-id="2bb98-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2bb98-178">Close the page.</span></span> 

<span data-ttu-id="2bb98-179">Quando você precisar avaliar esse mapeamento de modelo usando metadados de um aplicativo de versão diferente, registre outro aplicativo conectado, atribua-o a este mapeamento de modelo e valide-o em relação aos novos metadados.</span><span class="sxs-lookup"><span data-stu-id="2bb98-179">When you need to evaluate this model mapping by using metadata of a different version application, register another connected application, assign it to this model mapping and validate it against new metadata.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]