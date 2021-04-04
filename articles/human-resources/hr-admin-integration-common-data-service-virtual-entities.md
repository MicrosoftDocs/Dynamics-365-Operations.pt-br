---
title: Configurar tabelas virtuais do Dataverse
description: Este tópico mostra como configurar tabelas virtuais para o Dynamics 365 Human Resources. Gere e atualize tabelas virtuais existentes e analise as tabelas geradas e disponíveis.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d8780be777c9a204fcb95950f5679a5711aee298
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465813"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="1f29d-104">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="1f29d-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="1f29d-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="1f29d-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Dataverse e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="1f29d-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="1f29d-107">Os dados de tabelas virtuais não são armazenados no Dataverse, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1f29d-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="1f29d-108">Para habilitar operações CRUD em entidades do Human Resources do Dataverse, você deverá disponibilizar as entidades como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="1f29d-109">Isso permite executar operações CRUD do Dataverse e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="1f29d-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="1f29d-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="1f29d-111">Entidades do Human Resources correspondem a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="1f29d-112">Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="1f29d-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="1f29d-113">Tabelas virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="1f29d-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="1f29d-114">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="1f29d-115">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="1f29d-115">They're also available in Power Platform.</span></span> <span data-ttu-id="1f29d-116">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="1f29d-117">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="1f29d-118">Você pode exibir a lista de tabelas virtuais habilitada no ambiente e começar a trabalhar com as tabelas no [Power Apps](https://make.powerapps.com), na solução **Tabelas virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tabelas virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="1f29d-120">Tabelas virtuais x tabelas nativas</span><span class="sxs-lookup"><span data-stu-id="1f29d-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="1f29d-121">As tabelas virtuais para Human Resources não são iguais às tabelas nativas do Dataverse criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="1f29d-122">As tabelas nativas do Human Resources são geradas separadamente e mantidas na solução HCM Common no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="1f29d-123">Com tabelas nativas, os dados são armazenados no Dataverse e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="1f29d-124">Para obter uma lista das tabelas nativas do Dataverse para Human Resources, consulte [Tabelas do Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="1f29d-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="1f29d-125">Configurar</span><span class="sxs-lookup"><span data-stu-id="1f29d-125">Setup</span></span>

<span data-ttu-id="1f29d-126">Siga estas etapas de configuração para habilitar tabelas virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="1f29d-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="1f29d-127">Habilitar tabelas virtuais no Human Resources</span><span class="sxs-lookup"><span data-stu-id="1f29d-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="1f29d-128">Primeiro, você deve habilitar tabelas virtuais no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="1f29d-129">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="1f29d-130">Selecione o bloco **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="1f29d-131">Selecione **Suporte da tabela virtual para HR no Dataverse** e selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="1f29d-132">Para obter mais informações sobre como habilitar e desabilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="1f29d-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="1f29d-133">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1f29d-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="1f29d-134">Você precisa registrar sua instância do Human Resources no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="1f29d-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="1f29d-135">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="1f29d-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="1f29d-136">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="1f29d-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="1f29d-137">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="1f29d-138">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-138">Select **New registration**.</span></span>

4. <span data-ttu-id="1f29d-139">No campo **Nome**, insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1f29d-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="1f29d-140">Por exemplo, **Tabelas virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="1f29d-141">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="1f29d-142">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-142">Select **Register**.</span></span>

7. <span data-ttu-id="1f29d-143">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="1f29d-144">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="1f29d-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="1f29d-145">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="1f29d-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="1f29d-146">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="1f29d-147">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="1f29d-148">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="1f29d-149">Registre o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="1f29d-149">Record the secret's value.</span></span> <span data-ttu-id="1f29d-150">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="1f29d-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1f29d-151">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="1f29d-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="1f29d-152">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="1f29d-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="1f29d-153">Instalar o aplicativo Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="1f29d-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="1f29d-154">Instale o aplicativo Dynamics 365 HR Virtual Table no ambiente do Power Apps para implantar o pacote da solução da tabela virtual no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="1f29d-155">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1f29d-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="1f29d-156">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="1f29d-157">Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="1f29d-158">Selecione a ação **Instalar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="1f29d-159">Selecione **Dynamics 365 HR Virtual Table** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="1f29d-160">Analisar e marcar para concordar com os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="1f29d-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="1f29d-161">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-161">Select **Install**.</span></span>

<span data-ttu-id="1f29d-162">A instalação demora alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="1f29d-162">The install takes a few minutes.</span></span> <span data-ttu-id="1f29d-163">Ao concluir, prossiga para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="1f29d-163">When it completes, continue to the next steps.</span></span>

![Instalar o aplicativo Dynamics 365 HR Virtual Table do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="1f29d-165">Configurar a fonte de dados da tabela virtual</span><span class="sxs-lookup"><span data-stu-id="1f29d-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="1f29d-166">A próxima etapa é configurar a fonte de dados de tabela virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1f29d-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="1f29d-167">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="1f29d-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="1f29d-168">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="1f29d-169">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="1f29d-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="1f29d-170">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="1f29d-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="1f29d-171">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="1f29d-172">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-172">Select **Results**.</span></span>

7. <span data-ttu-id="1f29d-173">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="1f29d-174">Insira as informações necessárias para a configuração da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="1f29d-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="1f29d-175">**URL de Destino**: a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="1f29d-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="1f29d-176">O formato da URL de destino é:</span><span class="sxs-lookup"><span data-stu-id="1f29d-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="1f29d-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="1f29d-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="1f29d-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1f29d-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="1f29d-179">Inclua o caractere "**/**" no final da URL para evitar o recebimento de um erro.</span><span class="sxs-lookup"><span data-stu-id="1f29d-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="1f29d-180">**ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="1f29d-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="1f29d-181">**ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1f29d-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="1f29d-182">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="1f29d-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="1f29d-183">**Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1f29d-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="1f29d-184">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="1f29d-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="1f29d-186">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="1f29d-187">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="1f29d-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="1f29d-188">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="1f29d-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="1f29d-189">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="1f29d-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="1f29d-190">O aplicativo Dynamics 365 HR Virtual Table instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="1f29d-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="1f29d-191">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="1f29d-192">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="1f29d-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="1f29d-193">No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1f29d-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="1f29d-194">No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="1f29d-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="1f29d-195">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1f29d-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="1f29d-196">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="1f29d-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="1f29d-197">**ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="1f29d-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="1f29d-198">**Nome**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="1f29d-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="1f29d-199">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="1f29d-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="1f29d-200">Gerar tabelas virtuais</span><span class="sxs-lookup"><span data-stu-id="1f29d-200">Generate virtual tables</span></span>

<span data-ttu-id="1f29d-201">Quando a configuração for concluída, você poderá selecionar as tabelas virtuais que deseja gerar e habilitar na instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="1f29d-202">No Human Resources, abra a página **Integração do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="1f29d-203">Selecione a guia **Tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="1f29d-204">A alternância **Habilitar tabelas virtuais** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="1f29d-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="1f29d-205">Se a alternância estiver definida como **Não**, revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.</span><span class="sxs-lookup"><span data-stu-id="1f29d-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="1f29d-206">Selecione uma ou mais tabelas a serem geradas no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="1f29d-207">Selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-207">Select **Generate/refresh**.</span></span>

![Integração do Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="1f29d-209">Verificar status de geração de tabela</span><span class="sxs-lookup"><span data-stu-id="1f29d-209">Check table generation status</span></span>

<span data-ttu-id="1f29d-210">As tabelas virtuais são geradas no Dataverse por meio de um processo assíncrono em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="1f29d-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="1f29d-211">Atualizações na exibição do processo na central de ações.</span><span class="sxs-lookup"><span data-stu-id="1f29d-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="1f29d-212">Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="1f29d-213">No Human Resources, abra a página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="1f29d-214">Selecione a guia **Processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="1f29d-215">Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="1f29d-216">Selecione **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="1f29d-216">Select **View most recent results**.</span></span>

<span data-ttu-id="1f29d-217">O painel deslizante exibe os resultados da execução mais recente para o processo.</span><span class="sxs-lookup"><span data-stu-id="1f29d-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="1f29d-218">Você pode exibir o log do processo, incluindo todos os erros retornados do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="1f29d-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f29d-219">Consulte também</span><span class="sxs-lookup"><span data-stu-id="1f29d-219">See also</span></span>

[<span data-ttu-id="1f29d-220">O que é o Dataverse?</span><span class="sxs-lookup"><span data-stu-id="1f29d-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="1f29d-221">Tabelas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="1f29d-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="1f29d-222">Visão geral de relacionamentos entre tabelas</span><span class="sxs-lookup"><span data-stu-id="1f29d-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="1f29d-223">Criar e editar tabelas virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="1f29d-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="1f29d-224">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="1f29d-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="1f29d-225">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="1f29d-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]