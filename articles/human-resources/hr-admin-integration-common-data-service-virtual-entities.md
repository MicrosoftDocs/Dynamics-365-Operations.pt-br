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
ms.openlocfilehash: cd299b51e38cc30c3e18f3ef9de1f43fa817b840
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111531"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="54e39-104">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="54e39-104">Configure Dataverse virtual tables</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="54e39-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="54e39-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Dataverse e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="54e39-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="54e39-107">Os dados de tabelas virtuais não são armazenados no Dataverse, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54e39-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="54e39-108">Para habilitar operações CRUD em entidades do Human Resources do Dataverse, você deverá disponibilizar as entidades como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="54e39-109">Isso permite executar operações CRUD do Dataverse e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="54e39-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="54e39-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="54e39-111">Entidades do Human Resources correspondem a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="54e39-112">Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="54e39-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="54e39-113">Tabelas virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="54e39-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="54e39-114">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="54e39-115">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="54e39-115">They're also available in Power Platform.</span></span> <span data-ttu-id="54e39-116">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="54e39-117">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="54e39-118">Você pode exibir a lista de tabelas virtuais habilitada no ambiente e começar a trabalhar com as tabelas no [Power Apps](https://make.powerapps.com), na solução **Tabelas virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="54e39-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tabelas virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="54e39-120">Tabelas virtuais x tabelas nativas</span><span class="sxs-lookup"><span data-stu-id="54e39-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="54e39-121">As tabelas virtuais para Human Resources não são iguais às tabelas nativas do Dataverse criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="54e39-122">As tabelas nativas do Human Resources são geradas separadamente e mantidas na solução HCM Common no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="54e39-123">Com tabelas nativas, os dados são armazenados no Dataverse e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="54e39-124">Para obter uma lista das tabelas nativas do Dataverse para Human Resources, consulte [Tabelas do Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="54e39-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="54e39-125">Configurar</span><span class="sxs-lookup"><span data-stu-id="54e39-125">Setup</span></span>

<span data-ttu-id="54e39-126">Siga estas etapas de configuração para habilitar tabelas virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="54e39-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="54e39-127">Habilitar tabelas virtuais no Human Resources</span><span class="sxs-lookup"><span data-stu-id="54e39-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="54e39-128">Primeiro, você deve habilitar tabelas virtuais no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="54e39-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="54e39-129">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="54e39-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="54e39-130">Selecione o bloco **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="54e39-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="54e39-131">Selecione **Suporte da tabela virtual para HR no Dataverse** e selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="54e39-132">Para obter mais informações sobre como habilitar e desabilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="54e39-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="54e39-133">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="54e39-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="54e39-134">Você precisa registrar sua instância do Human Resources no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="54e39-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="54e39-135">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="54e39-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="54e39-136">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="54e39-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="54e39-137">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="54e39-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="54e39-138">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="54e39-138">Select **New registration**.</span></span>

4. <span data-ttu-id="54e39-139">No campo **Nome**, insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54e39-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="54e39-140">Por exemplo, **Tabelas virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="54e39-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="54e39-141">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="54e39-142">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-142">Select **Register**.</span></span>

7. <span data-ttu-id="54e39-143">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="54e39-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="54e39-144">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="54e39-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="54e39-145">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="54e39-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="54e39-146">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="54e39-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="54e39-147">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="54e39-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="54e39-148">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="54e39-149">Registre o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="54e39-149">Record the secret's value.</span></span> <span data-ttu-id="54e39-150">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="54e39-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="54e39-151">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="54e39-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="54e39-152">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="54e39-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="54e39-153">Instalar o aplicativo Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="54e39-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="54e39-154">Instale o aplicativo Dynamics 365 HR Virtual Table no ambiente do Power Apps para implantar o pacote da solução da tabela virtual no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="54e39-155">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="54e39-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="54e39-156">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="54e39-157">Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="54e39-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="54e39-158">Selecione a ação **Instalar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="54e39-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="54e39-159">Selecione **Dynamics 365 HR Virtual Table** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="54e39-160">Analisar e marcar para concordar com os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="54e39-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="54e39-161">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-161">Select **Install**.</span></span>

<span data-ttu-id="54e39-162">A instalação demora alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="54e39-162">The install takes a few minutes.</span></span> <span data-ttu-id="54e39-163">Ao concluir, prossiga para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="54e39-163">When it completes, continue to the next steps.</span></span>

![Instalar o aplicativo Dynamics 365 HR Virtual Table do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="54e39-165">Configurar a fonte de dados da tabela virtual</span><span class="sxs-lookup"><span data-stu-id="54e39-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="54e39-166">A próxima etapa é configurar a fonte de dados de tabela virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="54e39-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="54e39-167">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="54e39-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="54e39-168">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="54e39-169">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="54e39-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="54e39-170">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="54e39-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="54e39-171">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="54e39-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="54e39-172">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="54e39-172">Select **Results**.</span></span>

7. <span data-ttu-id="54e39-173">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="54e39-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="54e39-174">Insira as informações necessárias para a configuração da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="54e39-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="54e39-175">**URL de Destino**: a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="54e39-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="54e39-176">O formato da URL de destino é:</span><span class="sxs-lookup"><span data-stu-id="54e39-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="54e39-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="54e39-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="54e39-178">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="54e39-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="54e39-179">Inclua o caractere "**/**" no final da URL para evitar o recebimento de um erro.</span><span class="sxs-lookup"><span data-stu-id="54e39-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="54e39-180">**ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="54e39-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="54e39-181">**ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="54e39-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="54e39-182">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="54e39-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="54e39-183">**Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="54e39-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="54e39-184">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="54e39-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="54e39-186">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="54e39-187">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="54e39-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="54e39-188">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="54e39-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="54e39-189">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="54e39-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="54e39-190">O aplicativo Dynamics 365 HR Virtual Table instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="54e39-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="54e39-191">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="54e39-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="54e39-192">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="54e39-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="54e39-193">No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="54e39-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="54e39-194">No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="54e39-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="54e39-195">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="54e39-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="54e39-196">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="54e39-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="54e39-197">**ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="54e39-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="54e39-198">**Nome**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="54e39-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="54e39-199">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="54e39-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="54e39-200">Gerar tabelas virtuais</span><span class="sxs-lookup"><span data-stu-id="54e39-200">Generate virtual tables</span></span>

<span data-ttu-id="54e39-201">Quando a configuração for concluída, você poderá selecionar as tabelas virtuais que deseja gerar e habilitar na instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="54e39-202">No Human Resources, abra a página **Integração do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="54e39-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="54e39-203">Selecione a guia **Tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="54e39-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="54e39-204">A alternância **Habilitar tabelas virtuais** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="54e39-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="54e39-205">Se a alternância estiver definida como **Não**, revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.</span><span class="sxs-lookup"><span data-stu-id="54e39-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="54e39-206">Selecione uma ou mais tabelas a serem geradas no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="54e39-207">Selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="54e39-207">Select **Generate/refresh**.</span></span>

![Integração do Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="54e39-209">Verificar status de geração de tabela</span><span class="sxs-lookup"><span data-stu-id="54e39-209">Check table generation status</span></span>

<span data-ttu-id="54e39-210">As tabelas virtuais são geradas no Dataverse por meio de um processo assíncrono em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="54e39-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="54e39-211">Atualizações na exibição do processo na central de ações.</span><span class="sxs-lookup"><span data-stu-id="54e39-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="54e39-212">Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="54e39-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="54e39-213">No Human Resources, abra a página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="54e39-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="54e39-214">Selecione a guia **Processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="54e39-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="54e39-215">Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="54e39-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="54e39-216">Selecione **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="54e39-216">Select **View most recent results**.</span></span>

<span data-ttu-id="54e39-217">O painel deslizante exibe os resultados da execução mais recente para o processo.</span><span class="sxs-lookup"><span data-stu-id="54e39-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="54e39-218">Você pode exibir o log do processo, incluindo todos os erros retornados do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="54e39-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="54e39-219">Consulte também</span><span class="sxs-lookup"><span data-stu-id="54e39-219">See also</span></span>

[<span data-ttu-id="54e39-220">O que é o Dataverse?</span><span class="sxs-lookup"><span data-stu-id="54e39-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="54e39-221">Tabelas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="54e39-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="54e39-222">Visão geral de relacionamentos entre tabelas</span><span class="sxs-lookup"><span data-stu-id="54e39-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="54e39-223">Criar e editar tabelas virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="54e39-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="54e39-224">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="54e39-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="54e39-225">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="54e39-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
