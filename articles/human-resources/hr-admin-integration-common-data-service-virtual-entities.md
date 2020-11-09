---
title: Configurar entidades virtuais do Common Data Service
description: Este tópico mostra como configurar entidades virtuais para o Dynamics 365 Human Resources. Gerar e atualizar entidades virtuais existentes e analisar as entidades geradas e disponíveis.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
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
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058145"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="72a30-104">Configurar entidades virtuais do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="72a30-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="72a30-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="72a30-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Common Data Service e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="72a30-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="72a30-107">Os dados para entidades virtuais não são armazenados no Common Data Service, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72a30-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="72a30-108">Para habilitar as operações CRUD em entidades do Human Resources do Common Data Service, você deverá disponibilizar as entidades como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="72a30-109">Isso permite executar operações CRUD do Common Data Service e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="72a30-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="72a30-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="72a30-111">Entidades virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="72a30-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="72a30-112">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="72a30-113">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="72a30-113">They're also available in Power Platform.</span></span> <span data-ttu-id="72a30-114">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="72a30-115">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="72a30-116">Você pode exibir a lista de entidades virtuais habilitada no ambiente e começar a trabalhar com as entidades no [Power Apps](https://make.powerapps.com), na solução **Entidades Virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="72a30-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades Virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="72a30-118">Entidades virtuais versus entidades naturais</span><span class="sxs-lookup"><span data-stu-id="72a30-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="72a30-119">As entidades virtuais para Human Resources não são iguais das entidades naturais do Common Data Service criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="72a30-120">As entidades naturais para o Human Resources são geradas separadamente e mantidas na solução HCM Common no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="72a30-121">Com as entidades naturais, os dados são armazenados no Common Data Service e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="72a30-122">Para obter uma lista das entidades naturais do Common Data Service para Human Resources, consulte [Entidades do Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="72a30-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="72a30-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="72a30-123">Setup</span></span>

<span data-ttu-id="72a30-124">Siga estas etapas de configuração para habilitar as entidades virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="72a30-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="72a30-125">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="72a30-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="72a30-126">Primeiro, você precisa registrar o aplicativo no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="72a30-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="72a30-127">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="72a30-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="72a30-128">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="72a30-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="72a30-129">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="72a30-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="72a30-130">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="72a30-130">Select **New registration**.</span></span>

4. <span data-ttu-id="72a30-131">No campo **Nome** , insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72a30-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="72a30-132">Por exemplo, **Entidades virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="72a30-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="72a30-133">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="72a30-134">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-134">Select **Register**.</span></span>

7. <span data-ttu-id="72a30-135">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="72a30-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="72a30-136">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="72a30-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="72a30-137">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="72a30-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="72a30-138">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="72a30-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="72a30-139">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="72a30-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="72a30-140">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="72a30-141">Registre o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="72a30-141">Record the secret's value.</span></span> <span data-ttu-id="72a30-142">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="72a30-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="72a30-143">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="72a30-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="72a30-144">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="72a30-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="72a30-145">Instalar o aplicativo Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="72a30-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="72a30-146">Instale o aplicativo Dynamics 365 HR Virtual Entity no seu ambiente do Power Apps para implantar o pacote da solução da entidade virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="72a30-147">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="72a30-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="72a30-148">Na lista **Ambientes** , selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="72a30-149">Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="72a30-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="72a30-150">Selecione a ação **Instalar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="72a30-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="72a30-151">Selecione **Dynamics 365 HR Virtual Entity** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next**.</span></span>

6. <span data-ttu-id="72a30-152">Analisar e marcar para concordar com os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="72a30-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="72a30-153">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-153">Select **Install**.</span></span>

<span data-ttu-id="72a30-154">A instalação demora alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="72a30-154">The install takes a few minutes.</span></span> <span data-ttu-id="72a30-155">Ao concluir, prossiga para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="72a30-155">When it completes, continue to the next steps.</span></span>

![Instalar o aplicativo Dynamics 365 HR Virtual Entity do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="72a30-157">Configurar a fonte de dados da entidade virtual</span><span class="sxs-lookup"><span data-stu-id="72a30-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="72a30-158">A próxima etapa é configurar a fonte de dados de entidade virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="72a30-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="72a30-159">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="72a30-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="72a30-160">Na lista **Ambientes** , selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="72a30-161">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="72a30-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="72a30-162">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="72a30-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="72a30-163">Na página **Localização Avançada** , na lista suspensa **Procurar** , selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="72a30-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="72a30-164">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="72a30-164">Select **Results**.</span></span>

7. <span data-ttu-id="72a30-165">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="72a30-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="72a30-166">Insira as informações necessárias para a configuração da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="72a30-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="72a30-167">**URL de Destino** : a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="72a30-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="72a30-168">**ID do Locatário** : a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="72a30-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="72a30-169">**ID do Aplicativo AAD** : a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="72a30-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="72a30-170">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="72a30-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="72a30-171">**Segredo do Aplicativo AAD** : o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="72a30-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="72a30-172">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="72a30-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="72a30-173">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-173">Select **Save & Close**.</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="72a30-175">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="72a30-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="72a30-176">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="72a30-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="72a30-177">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="72a30-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="72a30-178">O aplicativo Dynamics 365 HR Virtual Entity instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="72a30-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="72a30-179">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="72a30-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="72a30-180">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="72a30-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="72a30-181">No campo **ID do Cliente** , insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="72a30-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="72a30-182">No campo **Nome** , insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="72a30-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="72a30-183">No campo **ID do Usuário** , selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="72a30-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="72a30-184">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="72a30-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="72a30-185">**ID do Cliente** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="72a30-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="72a30-186">**Nome** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="72a30-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="72a30-187">No campo **ID do Usuário** , selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="72a30-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="72a30-188">Gerar entidades virtuais</span><span class="sxs-lookup"><span data-stu-id="72a30-188">Generate virtual entities</span></span>

<span data-ttu-id="72a30-189">Quando a configuração for concluída, você poderá selecionar as entidades virtuais que deseja gerar e habilitar na instância do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="72a30-190">No Human Resources, abra a página **Integração do Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="72a30-190">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="72a30-191">Selecione a guia **Entidades virtuais**.</span><span class="sxs-lookup"><span data-stu-id="72a30-191">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="72a30-192">A alternância **Habilitar a entidade virtual** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="72a30-192">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="72a30-193">Se a alternância estiver definida como **Não** , revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.</span><span class="sxs-lookup"><span data-stu-id="72a30-193">If the toggle is set to **No** , review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="72a30-194">Selecione a entidade ou entidades que deseja gerar no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-194">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="72a30-195">Selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="72a30-195">Select **Generate/refresh**.</span></span>

![Integração do Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="72a30-197">Verificar status de geração de entidade</span><span class="sxs-lookup"><span data-stu-id="72a30-197">Check entity generation status</span></span>

<span data-ttu-id="72a30-198">As entidades virtuais são geradas no Common Data Service por meio de um processo assíncrono em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="72a30-198">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="72a30-199">Atualizações na exibição do processo na central de ações.</span><span class="sxs-lookup"><span data-stu-id="72a30-199">Updates on the process display in the action center.</span></span> <span data-ttu-id="72a30-200">Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="72a30-200">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="72a30-201">No Human Resources, abra a página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="72a30-201">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="72a30-202">Selecione a guia **Processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="72a30-202">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="72a30-203">Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de entidades virtuais**.</span><span class="sxs-lookup"><span data-stu-id="72a30-203">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="72a30-204">Selecione **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="72a30-204">Select **View most recent results**.</span></span>

<span data-ttu-id="72a30-205">O painel deslizante exibe os resultados da execução mais recente para o processo.</span><span class="sxs-lookup"><span data-stu-id="72a30-205">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="72a30-206">Você pode exibir o log do processo, incluindo todos os erros retornados do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="72a30-206">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="72a30-207">Consulte também</span><span class="sxs-lookup"><span data-stu-id="72a30-207">See also</span></span>

[<span data-ttu-id="72a30-208">O que é o Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="72a30-208">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="72a30-209">Visão geral de entidades</span><span class="sxs-lookup"><span data-stu-id="72a30-209">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="72a30-210">Visão geral de relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="72a30-210">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="72a30-211">Criar e editar entidades virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="72a30-211">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="72a30-212">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="72a30-212">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="72a30-213">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="72a30-213">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
