---
title: Configurar tabelas virtuais do Dataverse
description: Este tópico mostra como configurar tabelas virtuais para o Dynamics 365 Human Resources. Gere e atualize tabelas virtuais existentes e analise as tabelas geradas e disponíveis.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8c2e207efe0eeec6fc7e679a6ae12edcb21b291f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058575"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="49faa-104">Configurar tabelas virtuais do Dataverse</span><span class="sxs-lookup"><span data-stu-id="49faa-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="49faa-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="49faa-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Dataverse e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="49faa-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="49faa-107">Os dados de tabelas virtuais não são armazenados no Dataverse, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="49faa-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="49faa-108">Para habilitar operações CRUD em entidades do Human Resources do Dataverse, você deverá disponibilizar as entidades como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="49faa-109">Isso permite executar operações CRUD do Dataverse e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="49faa-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="49faa-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="49faa-111">Entidades do Human Resources correspondem a tabelas do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="49faa-112">Para obter mais informações sobre o Dataverse (antes conhecido como Common Data Service) e atualizações de terminologia, consulte [O que é o Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="49faa-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="49faa-113">Tabelas virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="49faa-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="49faa-114">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como tabelas virtuais no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="49faa-115">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="49faa-115">They're also available in Power Platform.</span></span> <span data-ttu-id="49faa-116">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="49faa-117">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="49faa-118">Você pode exibir a lista de tabelas virtuais habilitada no ambiente e começar a trabalhar com as tabelas no [Power Apps](https://make.powerapps.com), na solução **Tabelas virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="49faa-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tabelas virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="49faa-120">Tabelas virtuais x tabelas nativas</span><span class="sxs-lookup"><span data-stu-id="49faa-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="49faa-121">As tabelas virtuais para Human Resources não são iguais às tabelas nativas do Dataverse criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="49faa-122">As tabelas nativas do Human Resources são geradas separadamente e mantidas na solução HCM Common no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="49faa-123">Com tabelas nativas, os dados são armazenados no Dataverse e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="49faa-124">Para obter uma lista das tabelas nativas do Dataverse para Human Resources, consulte [Tabelas do Dataverse](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="49faa-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="49faa-125">Configurar</span><span class="sxs-lookup"><span data-stu-id="49faa-125">Setup</span></span>

<span data-ttu-id="49faa-126">Siga estas etapas de configuração para habilitar tabelas virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="49faa-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="49faa-127">Habilitar tabelas virtuais no Human Resources</span><span class="sxs-lookup"><span data-stu-id="49faa-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="49faa-128">Primeiro, você deve habilitar tabelas virtuais no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="49faa-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="49faa-129">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="49faa-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="49faa-130">Selecione o bloco **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="49faa-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="49faa-131">Selecione **Suporte da tabela virtual para HR no Dataverse** e selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="49faa-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="49faa-132">Para obter mais informações sobre como habilitar e desabilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="49faa-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="49faa-133">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="49faa-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="49faa-134">Você precisa registrar sua instância do Human Resources no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="49faa-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="49faa-135">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="49faa-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="49faa-136">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="49faa-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="49faa-137">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="49faa-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="49faa-138">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="49faa-138">Select **New registration**.</span></span>

4. <span data-ttu-id="49faa-139">No campo **Nome**, insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="49faa-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="49faa-140">Por exemplo, **Tabelas virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="49faa-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="49faa-141">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="49faa-142">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="49faa-142">Select **Register**.</span></span>

7. <span data-ttu-id="49faa-143">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="49faa-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="49faa-144">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="49faa-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="49faa-145">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="49faa-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="49faa-146">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="49faa-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="49faa-147">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="49faa-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="49faa-148">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="49faa-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="49faa-149">Registre o valor do segredo a partir a propriedade **Valor** da tabela.</span><span class="sxs-lookup"><span data-stu-id="49faa-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="49faa-150">Você inserirá essas informações ao [Configurar a fonte de dados de tabela virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="49faa-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="49faa-151">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="49faa-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="49faa-152">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="49faa-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="49faa-153">Instalar o aplicativo Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="49faa-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="49faa-154">Instale o aplicativo Dynamics 365 HR Virtual Table no ambiente do Power Apps para implantar o pacote da solução da tabela virtual no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="49faa-155">No Human Resources, abra a página **Integração do Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="49faa-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="49faa-156">Selecione a guia **Tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="49faa-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="49faa-157">Selecione **Instalar aplicativo de tabela virtual**.</span><span class="sxs-lookup"><span data-stu-id="49faa-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="49faa-158">Configurar a fonte de dados da tabela virtual</span><span class="sxs-lookup"><span data-stu-id="49faa-158">Configure the virtual table data source</span></span>

<span data-ttu-id="49faa-159">A próxima etapa é configurar a fonte de dados de tabela virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="49faa-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="49faa-160">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="49faa-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="49faa-161">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="49faa-162">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="49faa-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="49faa-163">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="49faa-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="49faa-164">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="49faa-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49faa-165">A instalação do aplicativo de tabela virtual da etapa de configuração anterior pode levar alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="49faa-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="49faa-166">Se **Configurações de Fonte de Dados Virtual do Finance and Operations** não estiver disponível na lista, aguarde um minuto e atualize a lista.</span><span class="sxs-lookup"><span data-stu-id="49faa-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="49faa-167">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="49faa-167">Select **Results**.</span></span>

7. <span data-ttu-id="49faa-168">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="49faa-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="49faa-169">Insira as informações necessárias para a configuração da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="49faa-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="49faa-170">**URL de Destino**: a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="49faa-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="49faa-171">O formato da URL de destino é:</span><span class="sxs-lookup"><span data-stu-id="49faa-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="49faa-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="49faa-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="49faa-173">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="49faa-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="49faa-174">Inclua o caractere "**/**" no final da URL para evitar o recebimento de um erro.</span><span class="sxs-lookup"><span data-stu-id="49faa-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="49faa-175">**ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="49faa-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="49faa-176">**ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="49faa-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="49faa-177">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="49faa-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="49faa-178">**Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="49faa-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="49faa-179">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="49faa-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="49faa-181">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="49faa-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="49faa-182">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="49faa-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="49faa-183">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="49faa-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="49faa-184">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="49faa-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="49faa-185">O aplicativo Dynamics 365 HR Virtual Table instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="49faa-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="49faa-186">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="49faa-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="49faa-187">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="49faa-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="49faa-188">No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="49faa-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="49faa-189">No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="49faa-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="49faa-190">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="49faa-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="49faa-191">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="49faa-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="49faa-192">**ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="49faa-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="49faa-193">**Nome**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="49faa-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="49faa-194">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="49faa-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="49faa-195">Gerar tabelas virtuais</span><span class="sxs-lookup"><span data-stu-id="49faa-195">Generate virtual tables</span></span>

<span data-ttu-id="49faa-196">Quando a configuração for concluída, você poderá selecionar as tabelas virtuais que deseja gerar e habilitar na instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="49faa-197">No Human Resources, abra a página **Integração do Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="49faa-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="49faa-198">Selecione a guia **Tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="49faa-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="49faa-199">A alternância **Habilitar tabelas virtuais** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="49faa-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="49faa-200">Se a alternância estiver definida como **Não**, revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.</span><span class="sxs-lookup"><span data-stu-id="49faa-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="49faa-201">Selecione uma ou mais tabelas a serem geradas no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="49faa-202">Selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="49faa-202">Select **Generate/refresh**.</span></span>

![Integração do Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="49faa-204">Verificar status de geração de tabela</span><span class="sxs-lookup"><span data-stu-id="49faa-204">Check table generation status</span></span>

<span data-ttu-id="49faa-205">As tabelas virtuais são geradas no Dataverse por meio de um processo assíncrono em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="49faa-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="49faa-206">Atualizações na exibição do processo na central de ações.</span><span class="sxs-lookup"><span data-stu-id="49faa-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="49faa-207">Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="49faa-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="49faa-208">No Human Resources, abra a página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="49faa-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="49faa-209">Selecione a guia **Processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="49faa-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="49faa-210">Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de tabelas virtuais**.</span><span class="sxs-lookup"><span data-stu-id="49faa-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="49faa-211">Selecione **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="49faa-211">Select **View most recent results**.</span></span>

<span data-ttu-id="49faa-212">O painel deslizante exibe os resultados da execução mais recente para o processo.</span><span class="sxs-lookup"><span data-stu-id="49faa-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="49faa-213">Você pode exibir o log do processo, incluindo todos os erros retornados do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="49faa-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="49faa-214">Consulte também</span><span class="sxs-lookup"><span data-stu-id="49faa-214">See also</span></span>

[<span data-ttu-id="49faa-215">O que é o Dataverse?</span><span class="sxs-lookup"><span data-stu-id="49faa-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="49faa-216">Tabelas no Dataverse</span><span class="sxs-lookup"><span data-stu-id="49faa-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="49faa-217">Visão geral de relacionamentos entre tabelas</span><span class="sxs-lookup"><span data-stu-id="49faa-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="49faa-218">Criar e editar tabelas virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="49faa-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="49faa-219">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="49faa-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="49faa-220">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="49faa-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
