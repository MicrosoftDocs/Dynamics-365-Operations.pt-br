---
title: Solucionar problemas de sincronização ao vivo
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d45b19c1e88e6a27bde4335d4a356f2173bdfcd3
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275408"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="2daad-103">Solucionar problemas de sincronização ao vivo</span><span class="sxs-lookup"><span data-stu-id="2daad-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="2daad-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2daad-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="2daad-105">Especificamente, ele fornece informações que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.</span><span class="sxs-lookup"><span data-stu-id="2daad-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2daad-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="2daad-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="2daad-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="2daad-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="2daad-108">A sincronização dinâmica lança um erro 403 Proibido ao criar um registro em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2daad-108">Live synchronization throws a 403 Forbidden error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="2daad-109">Você pode receber a seguinte mensagem de erro ao criar um registro em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="2daad-109">You might receive the following error message when you create a record in a Finance and Operations app:</span></span>

<span data-ttu-id="2daad-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"O usuário não é um membro da organização.\\"}}\], O servidor remoto retornou um erro: (403) Proibido."}}".*</span><span class="sxs-lookup"><span data-stu-id="2daad-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="2daad-111">Para corrigir o problema, siga as etapas dos [pré-requisitos e requisitos do sistema](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="2daad-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="2daad-112">Para concluir essas etapas, os usuários do aplicativo de gravação dupla que são criados em Common Data Service devem ter a função de administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="2daad-112">To complete those steps, the dual-write application users who are created in Common Data Service must have the system admin role.</span></span> <span data-ttu-id="2daad-113">A equipe de propriedade padrão também deve ter a função de administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="2daad-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a><span data-ttu-id="2daad-114">A sincronização ao vivo de uma entidade lança, de forma consistente, um erro semelhando ao criar um registro em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2daad-114">Live synchronization for any entity consistently throws a similar error when you create a record in a Finance and Operations app</span></span>

<span data-ttu-id="2daad-115">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="2daad-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="2daad-116">Você pode receber uma mensagem de erro como a seguinte toda vez que tentar salvar dados da entidade em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="2daad-116">You might receive an error message like the following every time that you try to save entity data in a Finance and Operations app:</span></span>

<span data-ttu-id="2daad-117">*Não é possível salvar as alterações no banco de dados. A unidade de trabalho não pode confirmar a transação. Não é possível gravar dados no uoms da entidade. As gravações no UnitOfMeasureEntity falharam com a mensagem de erro. Não é possível sincronizar com a entidade uoms.*</span><span class="sxs-lookup"><span data-stu-id="2daad-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="2daad-118">Para corrigir o problema, você deve verificar se os dados de referência de pré-requisito existem no aplicativo Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2daad-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Common Data Service.</span></span> <span data-ttu-id="2daad-119">Por exemplo, se o cliente que você está no aplicativo Finance and Operations pertencer a um grupo de clientes específico, verifique se o grupo de clientes existe em Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2daad-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Common Data Service.</span></span>

<span data-ttu-id="2daad-120">Se houver dados em ambos os lados e você tiver confirmado que o problema não é relacionado a dados, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2daad-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="2daad-121">Interrompa a entidade relacionada.</span><span class="sxs-lookup"><span data-stu-id="2daad-121">Stop the related entity.</span></span>
2. <span data-ttu-id="2daad-122">Faça login no aplicativo Finance and Operations e verifique se os registros da entidade com falha existem nas tabelas DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="2daad-122">Sign in to the Finance and Operations app, and make sure that records for the failing entity exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="2daad-123">Por exemplo, aqui está a aparência da consulta se a entidade **Clientes** está falhando.</span><span class="sxs-lookup"><span data-stu-id="2daad-123">For example, here is what the query looks like if the **Customers** entity is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="2daad-124">Se houver registros para a entidade com falha mesmo depois que você interromper o mapeamento de entidade, exclua os registros relacionados à entidade com falha.</span><span class="sxs-lookup"><span data-stu-id="2daad-124">If there are records for the failing entity even after you stop the entity mapping, delete the records that are related to the failing entity.</span></span> <span data-ttu-id="2daad-125">Anote a coluna **projectname** na tabela DualWriteProjectConfiguration, e busque o registro na tabela DualWriteProjectFieldConfiguration usando o nome do projeto para excluir o registro.</span><span class="sxs-lookup"><span data-stu-id="2daad-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the record in the DualWriteProjectFieldConfiguration table by using the project name to delete the record.</span></span>
4. <span data-ttu-id="2daad-126">Inicie o mapeamento de entidade.</span><span class="sxs-lookup"><span data-stu-id="2daad-126">Start the entity mapping.</span></span> <span data-ttu-id="2daad-127">Validar se os dados são sincronizados sem problemas.</span><span class="sxs-lookup"><span data-stu-id="2daad-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="2daad-128">Manipular erros de privilégio de leitura ou gravação ao criar dados em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="2daad-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="2daad-129">Você pode receber uma mensagem de erro de "solicitação incorreta" que se assemelha ao exemplo a seguir ao criar dados em um aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2daad-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exemplo da mensagem inválida de erro de solicitação](media/error_record_id_source.png)

<span data-ttu-id="2daad-131">Para corrigir o problema, você deve atribuir o direito de acesso correto à equipe da unidade de negócios do Dynamics 365 Sales ou do Dynamics 365 Customer Service mapeada para habilitar o privilégio ausente.</span><span class="sxs-lookup"><span data-stu-id="2daad-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="2daad-132">No aplicativo Finance and Operations, localize a unidade de negócios mapeada no conjunto de conexões de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="2daad-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Mapeamento da organização](media/mapped_business_unit.png)

2. <span data-ttu-id="2daad-134">Faça login no ambiente no aplicativo controlado por modelo no Dynamics 365, navegue até **Definir segurança do \>**, e encontre a equipe da unidade de negócios mapeada.</span><span class="sxs-lookup"><span data-stu-id="2daad-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Equipe da unidade de negócios mapeada](media/setting_security_page.png)

3. <span data-ttu-id="2daad-136">Abra a página da equipe para edição, e depois selecione **Gerenciar funções** para abrir a caixa de diálogo **Gerenciar funções de equipe**.</span><span class="sxs-lookup"><span data-stu-id="2daad-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Gerenciar botão de funções](media/manage_team_roles.png)

4. <span data-ttu-id="2daad-138">Atribua a função que tem o privilégio de leitura/gravação para as entidades relevantes e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2daad-138">Assign the role that has the read/write privilege for the relevant entities, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a><span data-ttu-id="2daad-139">Corrigir problemas de sincronização em um ambiente que tem um ambiente Common Data Service alterado recentemente</span><span class="sxs-lookup"><span data-stu-id="2daad-139">Fix synchronization issues in an environment that has a recently changed Common Data Service environment</span></span>

<span data-ttu-id="2daad-140">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="2daad-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="2daad-141">Você pode receber a seguinte mensagem de erro ao criar dados em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="2daad-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="2daad-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable para gerar carga de trabalho para a entidade CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Criação de carga de trabalho falhada com erro de URI inválido: O URI está vazio."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="2daad-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="2daad-143">Esta é a aparência do erro no aplicativo baseado em modelo no Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="2daad-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="2daad-144">*Ocorreu um erro inesperado no código do ISV. (ErrorType = ClientError) Exceção inesperada do plug-in (Executar): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: falha ao processar conta da entidade — (Houve falha em uma tentativa de conexão porque a parte conectada não respondeu adequadamente após um período de tempo ou houve falha na conexão estabelecida porque o host não respondeu*</span><span class="sxs-lookup"><span data-stu-id="2daad-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="2daad-145">Este erro ocorre quando o ambiente Common Data Service é redefinido incorretamente ao mesmo tempo que você tenta criar dados no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="2daad-145">This error occurs when the Common Data Service environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="2daad-146">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="2daad-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="2daad-147">Entre na máquina virtual Finance and Operations (VM), abra SQL Server Management Studio (SSMS), e procure por registros na tabela DUALWRITEPROJECTCONFIGURATIONENTITY onde **internalentityname** é igual a **Clientes V3** e **externalentityname** é igual a **contas**.</span><span class="sxs-lookup"><span data-stu-id="2daad-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for records in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="2daad-148">Esta é a aparência da consulta.</span><span class="sxs-lookup"><span data-stu-id="2daad-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="2daad-149">Use o nome do projeto dos resultados da consulta anterior para executar a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="2daad-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="2daad-150">Verifique se a coluna **externalenvironmentURL** tem o Common Data Service correto ou URL de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2daad-150">Make sure that the **externalenvironmentURL** column has the correct Common Data Service or app URL.</span></span> <span data-ttu-id="2daad-151">Exclua os registros duplicados que apontam para a URL de Common Data Service errada.</span><span class="sxs-lookup"><span data-stu-id="2daad-151">Delete any duplicate records that point to the wrong Common Data Service URL.</span></span> <span data-ttu-id="2daad-152">Exclua os registros correspondentes nas tabelas DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="2daad-152">Delete the corresponding records in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="2daad-153">Interrompa o mapeamento da entidade e reinicie-o</span><span class="sxs-lookup"><span data-stu-id="2daad-153">Stop the entity mapping, and then restart it</span></span>
