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
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959566"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="c0798-104">Configurar entidades virtuais do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="c0798-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="c0798-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="c0798-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Common Data Service e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="c0798-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="c0798-107">Os dados para entidades virtuais não são armazenados no Common Data Service, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0798-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="c0798-108">Para habilitar as operações CRUD em entidades do Human Resources do Common Data Service, você deverá disponibilizar as entidades como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="c0798-109">Isso permite executar operações CRUD do Common Data Service e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="c0798-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="c0798-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="c0798-111">Entidades virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="c0798-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="c0798-112">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="c0798-113">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="c0798-113">They're also available in Power Platform.</span></span> <span data-ttu-id="c0798-114">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="c0798-115">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="c0798-116">Você pode exibir a lista de entidades virtuais habilitada no ambiente e começar a trabalhar com as entidades no [Power Apps](https://make.powerapps.com), na solução **Entidades Virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="c0798-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades Virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="c0798-118">Entidades virtuais versus entidades naturais</span><span class="sxs-lookup"><span data-stu-id="c0798-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="c0798-119">As entidades virtuais para Human Resources não são iguais das entidades naturais do Common Data Service criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="c0798-120">As entidades naturais para o Human Resources são geradas separadamente e mantidas na solução HCM Common no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="c0798-121">Com as entidades naturais, os dados são armazenados no Common Data Service e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="c0798-122">Para obter uma lista das entidades naturais do Common Data Service para Human Resources, consulte [Entidades do Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="c0798-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="c0798-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="c0798-123">Setup</span></span>

<span data-ttu-id="c0798-124">Siga estas etapas de configuração para habilitar as entidades virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c0798-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="c0798-125">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c0798-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="c0798-126">Primeiro, você precisa registrar o aplicativo no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="c0798-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="c0798-127">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="c0798-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="c0798-128">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="c0798-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="c0798-129">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="c0798-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="c0798-130">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="c0798-130">Select **New registration**.</span></span>

4. <span data-ttu-id="c0798-131">No campo **Nome**, insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0798-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="c0798-132">Por exemplo, **Entidades virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="c0798-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="c0798-133">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="c0798-134">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="c0798-134">Select **Register**.</span></span>

7. <span data-ttu-id="c0798-135">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="c0798-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="c0798-136">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="c0798-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="c0798-137">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="c0798-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="c0798-138">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="c0798-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="c0798-139">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="c0798-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="c0798-140">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="c0798-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="c0798-141">Registre o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="c0798-141">Record the secret's value.</span></span> <span data-ttu-id="c0798-142">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="c0798-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c0798-143">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="c0798-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="c0798-144">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="c0798-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="c0798-145">Instalar o aplicativo Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="c0798-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="c0798-146">Instale o aplicativo Dynamics 365 HR Virtual Entity no seu ambiente do Power Apps para implantar o pacote da solução da entidade virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="c0798-147">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0798-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="c0798-148">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="c0798-149">Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c0798-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="c0798-150">Selecione a ação **Instalar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="c0798-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="c0798-151">Selecione **Dynamics 365 HR Virtual Entity** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c0798-151">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="c0798-152">Analisar e marcar para concordar com os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="c0798-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="c0798-153">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="c0798-153">Select **Install**.</span></span>

<span data-ttu-id="c0798-154">A instalação demora alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="c0798-154">The install takes a few minutes.</span></span> <span data-ttu-id="c0798-155">Ao concluir, prossiga para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="c0798-155">When it completes, continue to the next steps.</span></span>

![Instalar o aplicativo Dynamics 365 HR Virtual Entity do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="c0798-157">Configurar a fonte de dados da entidade virtual</span><span class="sxs-lookup"><span data-stu-id="c0798-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="c0798-158">A próxima etapa é configurar a fonte de dados de entidade virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c0798-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="c0798-159">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0798-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="c0798-160">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="c0798-161">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="c0798-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="c0798-162">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c0798-162">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="c0798-163">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="c0798-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="c0798-164">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="c0798-164">Select **Results**.</span></span>

7. <span data-ttu-id="c0798-165">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="c0798-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="c0798-166">Insira as informações necessárias para a configuração da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c0798-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="c0798-167">**URL de Destino**: a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-167">**Target URL**: The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="c0798-168">**ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c0798-168">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="c0798-169">**ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="c0798-169">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="c0798-170">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="c0798-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="c0798-171">**Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="c0798-171">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="c0798-172">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="c0798-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="c0798-173">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c0798-173">Select **Save & Close**.</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="c0798-175">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="c0798-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="c0798-176">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="c0798-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="c0798-177">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="c0798-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="c0798-178">O aplicativo Dynamics 365 HR Virtual Entity instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="c0798-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="c0798-179">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c0798-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="c0798-180">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c0798-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="c0798-181">No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="c0798-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="c0798-182">No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="c0798-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="c0798-183">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c0798-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="c0798-184">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="c0798-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="c0798-185">**ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="c0798-185">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="c0798-186">**Nome**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="c0798-186">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="c0798-187">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c0798-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="c0798-188">Gerar entidades virtuais</span><span class="sxs-lookup"><span data-stu-id="c0798-188">Generate virtual entities</span></span>

<span data-ttu-id="c0798-189">Quando a configuração for concluída, você poderá selecionar as entidades virtuais que deseja gerar e habilitar na instância do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0798-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="c0798-190">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c0798-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="c0798-191">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="c0798-192">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="c0798-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="c0798-193">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página.</span><span class="sxs-lookup"><span data-stu-id="c0798-193">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="c0798-194">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Entidades do HR Disponíveis**.</span><span class="sxs-lookup"><span data-stu-id="c0798-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities**.</span></span>

6. <span data-ttu-id="c0798-195">Use as opções de filtro para localizar a entidade ou entidades que deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="c0798-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="c0798-196">Selecione uma entidade na lista.</span><span class="sxs-lookup"><span data-stu-id="c0798-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="c0798-197">Na página da entidade, altere a propriedade **Foi Gerada** para **Sim** para a entidade.</span><span class="sxs-lookup"><span data-stu-id="c0798-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="c0798-198">Salve e feche a página da entidade.</span><span class="sxs-lookup"><span data-stu-id="c0798-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="c0798-199">Você pode gerar várias entidades virtuais de uma só vez usando a página **Alterar Vários Registros**.</span><span class="sxs-lookup"><span data-stu-id="c0798-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="c0798-200">Selecione vários registros na página e selecione **Editar** na faixa de opções.</span><span class="sxs-lookup"><span data-stu-id="c0798-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="c0798-201">Em seguida, você poderá alterar a propriedade **Foi Gerada** para todos os registros selecionados.</span><span class="sxs-lookup"><span data-stu-id="c0798-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Entidades do HR Disponíveis](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="c0798-203">Para simplificar o processo de geração de entidades virtuais em versões futuras, o processo ocorrerá em uma página no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c0798-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0798-204">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c0798-204">See also</span></span>

[<span data-ttu-id="c0798-205">O que é o Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="c0798-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="c0798-206">Visão geral de entidades</span><span class="sxs-lookup"><span data-stu-id="c0798-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="c0798-207">Visão geral de relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="c0798-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="c0798-208">Criar e editar entidades virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="c0798-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="c0798-209">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="c0798-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="c0798-210">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="c0798-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
