---
title: Solucionar problemas de sincronização ao vivo
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b40b71eb45ae5a95a732c9554356afcddecb750e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566804"
---
# <a name="troubleshoot-live-synchronization-issues"></a><span data-ttu-id="e7d4e-103">Solucionar problemas de sincronização ao vivo</span><span class="sxs-lookup"><span data-stu-id="e7d4e-103">Troubleshoot live synchronization issues</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="e7d4e-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="e7d4e-105">Especificamente, ele fornece informações que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-105">Specifically, it provides information that can help you fix issues with live synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e7d4e-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e7d4e-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="e7d4e-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="e7d4e-108">A sincronização dinâmica lança um erro 403 Proibido ao criar uma linha em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e7d4e-108">Live synchronization throws a 403 Forbidden error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="e7d4e-109">Você pode receber a seguinte mensagem de erro ao criar uma linha em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e7d4e-109">You might receive the following error message when you create a row in a Finance and Operations app:</span></span>

<span data-ttu-id="e7d4e-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"O usuário não é um membro da organização.\\"}}\], O servidor remoto retornou um erro: (403) Proibido."}}".*</span><span class="sxs-lookup"><span data-stu-id="e7d4e-110">*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"The user is not a member of the organization.\\"}}\], The remote server returned an error: (403) Forbidden."}}".*</span></span>

<span data-ttu-id="e7d4e-111">Para corrigir o problema, siga as etapas dos [pré-requisitos e requisitos do sistema](requirements-and-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="e7d4e-111">To fix the issue, follow the steps in [System requirements and prerequisites](requirements-and-prerequisites.md).</span></span> <span data-ttu-id="e7d4e-112">Para concluir essas etapas, os usuários do aplicativo de gravação dupla que são criados em Dataverse devem ter a função de administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-112">To complete those steps, the dual-write application users who are created in Dataverse must have the system admin role.</span></span> <span data-ttu-id="e7d4e-113">A equipe de propriedade padrão também deve ter a função de administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-113">The default owning team must also have the system admin role.</span></span>

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a><span data-ttu-id="e7d4e-114">A sincronização ao vivo de uma tabela lança, de forma consistente, um erro semelhante ao criar uma linha em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e7d4e-114">Live synchronization for any table consistently throws a similar error when you create a row in a Finance and Operations app</span></span>

<span data-ttu-id="e7d4e-115">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="e7d4e-115">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="e7d4e-116">Você pode receber uma mensagem de erro como a seguinte toda vez que tentar salvar dados da tabela em um aplicativo do Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e7d4e-116">You might receive an error message like the following every time that you try to save table data in a Finance and Operations app:</span></span>

<span data-ttu-id="e7d4e-117">*Não é possível salvar as alterações no banco de dados. A unidade de trabalho não pode confirmar a transação. Não é possível gravar dados no uoms da entidade. As gravações no UnitOfMeasureEntity falharam com a mensagem de erro. Não é possível sincronizar com a entidade uoms.*</span><span class="sxs-lookup"><span data-stu-id="e7d4e-117">*Cannot save the changes to the database. Unit of Work can not commit transaction. Unable to write data to entity uoms. Writes to UnitOfMeasureEntity failed with error message Unable to sync with entity uoms.*</span></span>

<span data-ttu-id="e7d4e-118">Para corrigir o problema, você deve verificar se os dados de referência de pré-requisito existem no aplicativo Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-118">To fix the issue, you must make sure that the prerequisite reference data exists in both the Finance and Operations app and Dataverse.</span></span> <span data-ttu-id="e7d4e-119">Por exemplo, se o cliente que você está no aplicativo Finance and Operations pertencer a um grupo de clientes específico, verifique se o grupo de clientes existe em Dataverse.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-119">For example, if the customer that you're in the Finance and Operations app belongs to a specific customer group, make sure that the customer group exists in Dataverse.</span></span>

<span data-ttu-id="e7d4e-120">Se houver dados em ambos os lados e você tiver confirmado que o problema não é relacionado a dados, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-120">If data exists on both sides, and you've confirmed that the issue isn't data-related, follow these steps.</span></span>

1. <span data-ttu-id="e7d4e-121">Interrompa a tabela relacionada.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-121">Stop the related table.</span></span>
2. <span data-ttu-id="e7d4e-122">Faça login no aplicativo do Finance and Operations e verifique se as linhas da tabela com falha existem nas tabelas DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-122">Sign in to the Finance and Operations app, and make sure that rows for the failing table exist in the DualWriteProjectConfiguration and DualWriteProjectFieldConfiguration tables.</span></span> <span data-ttu-id="e7d4e-123">Por exemplo, está será a aparência da consulta se a tabela **Clientes** estiver falhando.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-123">For example, here is what the query looks like if the **Customers** table is failing.</span></span>

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. <span data-ttu-id="e7d4e-124">Se houver linhas para a tabela com falha mesmo depois que você interromper o mapeamento de tabela, exclua as linhas relacionados à tabela com falha.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-124">If there are rows for the failing table even after you stop the table mapping, delete the rows that are related to the failing table.</span></span> <span data-ttu-id="e7d4e-125">Anote a coluna **projectname** na tabela DualWriteProjectConfiguration e busque o registro na linha DualWriteProjectFieldConfiguration usando o nome do projeto para excluir a linha.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-125">Make a note of the **projectname** column in the DualWriteProjectConfiguration table, and fetch the row in the DualWriteProjectFieldConfiguration table by using the project name to delete the row.</span></span>
4. <span data-ttu-id="e7d4e-126">Inicie o mapeamento de tabela.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-126">Start the table mapping.</span></span> <span data-ttu-id="e7d4e-127">Validar se os dados são sincronizados sem problemas.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-127">Validate whether the data is synced without any issues.</span></span>

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a><span data-ttu-id="e7d4e-128">Manipular erros de privilégio de leitura ou gravação ao criar dados em um aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e7d4e-128">Handle read or write privilege errors when you create data in a Finance and Operations app</span></span>

<span data-ttu-id="e7d4e-129">Você pode receber uma mensagem de erro de "solicitação incorreta" que se assemelha ao exemplo a seguir ao criar dados em um aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-129">You might receive a "Bad Request" error message that resembles the following example when you create data in a Finance and Operations app.</span></span>

![Exemplo da mensagem inválida de erro de solicitação](media/error_record_id_source.png)

<span data-ttu-id="e7d4e-131">Para corrigir o problema, você deve atribuir o direito de acesso correto à equipe da unidade de negócios do Dynamics 365 Sales ou do Dynamics 365 Customer Service mapeada para habilitar o privilégio ausente.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-131">To fix the issue, you must assign the correct security role to the team of the mapped Dynamics 365 Sales or Dynamics 365 Customer Service business unit to enable the missing privilege.</span></span>

1. <span data-ttu-id="e7d4e-132">No aplicativo Finance and Operations, localize a unidade de negócios mapeada no conjunto de conexões de integração de dados.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-132">In the Finance and Operations app, find the business unit that is mapped in the Data Integration connection set.</span></span>

    ![Mapeamento da organização](media/mapped_business_unit.png)

2. <span data-ttu-id="e7d4e-134">Faça login no ambiente no aplicativo controlado por modelo no Dynamics 365, navegue até **Definir segurança do \>**, e encontre a equipe da unidade de negócios mapeada.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-134">Sign in to the environment in the model-driven app in Dynamics 365, navigate to **Setting \> Security**, and find the team of the mapped business unit.</span></span>

    ![Equipe da unidade de negócios mapeada](media/setting_security_page.png)

3. <span data-ttu-id="e7d4e-136">Abra a página da equipe para edição, e depois selecione **Gerenciar funções** para abrir a caixa de diálogo **Gerenciar funções de equipe**.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-136">Open the page for the team for editing, and then select **Manage roles** to open the **Manage Team Roles** dialog box.</span></span>

    ![Gerenciar botão de funções](media/manage_team_roles.png)

4. <span data-ttu-id="e7d4e-138">Atribua a função que tem o privilégio de leitura/gravação para as tabelas relevantes e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-138">Assign the role that has the read/write privilege for the relevant tables, and then select **OK**.</span></span>

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a><span data-ttu-id="e7d4e-139">Corrigir problemas de sincronização em um ambiente que tem um ambiente Dataverse alterado recentemente</span><span class="sxs-lookup"><span data-stu-id="e7d4e-139">Fix synchronization issues in an environment that has a recently changed Dataverse environment</span></span>

<span data-ttu-id="e7d4e-140">**Função necessária para corrigir o problema:** administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="e7d4e-140">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="e7d4e-141">Você pode receber a seguinte mensagem de erro ao criar dados em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="e7d4e-141">You might receive the following error message when you create data in a Finance and Operations app:</span></span>

<span data-ttu-id="e7d4e-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable para gerar carga de trabalho para a entidade CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Criação de carga de trabalho falhada com erro de URI inválido: O URI está vazio."}\],"isErrorCountUpdated":true}*</span><span class="sxs-lookup"><span data-stu-id="e7d4e-142">*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable to generate payload for entity CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Payload creation failed with error Invalid URI: The URI is empty."}\],"isErrorCountUpdated":true}*</span></span>

<span data-ttu-id="e7d4e-143">Esta é a aparência do erro no aplicativo baseado em modelo no Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="e7d4e-143">Here is what the error looks like in the model-driven app in Dynamics 365:</span></span>

<span data-ttu-id="e7d4e-144">*Ocorreu um erro inesperado no código do ISV. (ErrorType = ClientError) Exceção inesperada do plug-in (Executar): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: falha ao processar conta da entidade — (Houve falha em uma tentativa de conexão porque a parte conectada não respondeu adequadamente após um período de tempo ou houve falha na conexão estabelecida porque o host não respondeu*</span><span class="sxs-lookup"><span data-stu-id="e7d4e-144">*An unexpected error occurred from ISV code. (ErrorType = ClientError) Unexpected exception from plug-in (Execute): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: failed to process entity account - (A connection attempt failed because the connected party did not properly respond after a period of time, or established connection failed because connected host has failed to respond*</span></span>

<span data-ttu-id="e7d4e-145">Este erro ocorre quando o ambiente Dataverse é redefinido incorretamente ao mesmo tempo que você tenta criar dados no aplicativo Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-145">This error occurs when the Dataverse environment is incorrectly reset at the same time that you try to create data in the Finance and Operations app.</span></span>

<span data-ttu-id="e7d4e-146">Para corrigir o problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-146">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="e7d4e-147">Entre na máquina virtual Finance and Operations (VM), abra SQL Server Management Studio (SSMS), e procure por linhas na tabela DUALWRITEPROJECTCONFIGURATIONENTITY onde **internalentityname** é igual a **Clientes V3** e **externalentityname** é igual a **contas**.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-147">Sign in to the Finance and Operations virtual machine (VM), open SQL Server Management Studio (SSMS), and look for rows in the DUALWRITEPROJECTCONFIGURATIONENTITY table where **internalentityname** equals **Customers V3** and **externalentityname** equals **accounts**.</span></span> <span data-ttu-id="e7d4e-148">Esta é a aparência da consulta.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-148">Here is what the query looks like.</span></span>

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. <span data-ttu-id="e7d4e-149">Use o nome do projeto dos resultados da consulta anterior para executar a consulta a seguir.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-149">Use the project name from the results of the previous query to run the following query.</span></span>

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. <span data-ttu-id="e7d4e-150">Verifique se a coluna **externalenvironmentURL** tem o Dataverse correto ou URL de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-150">Make sure that the **externalenvironmentURL** column has the correct Dataverse or app URL.</span></span> <span data-ttu-id="e7d4e-151">Exclua as linhas duplicadas que apontam para a URL de Dataverse errada.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-151">Delete any duplicate rows that point to the wrong Dataverse URL.</span></span> <span data-ttu-id="e7d4e-152">Exclua as linhas correspondentes nas tabelas DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.</span><span class="sxs-lookup"><span data-stu-id="e7d4e-152">Delete the corresponding rows in the DUALWRITEPROJECTFIELDCONFIGURATION and DUALWRITEPROJECTCONFIGURATION tables.</span></span>
4. <span data-ttu-id="e7d4e-153">Interrompa o mapeamento de tabela e reinicie-o</span><span class="sxs-lookup"><span data-stu-id="e7d4e-153">Stop the table mapping, and then restart it</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]