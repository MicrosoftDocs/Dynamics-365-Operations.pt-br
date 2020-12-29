---
title: Configurar entidades virtuais do Common Data Service
description: Este tópico mostra como configurar entidades virtuais para o Dynamics 365 Human Resources. Gerar e atualizar entidades virtuais existentes e analisar as entidades geradas e disponíveis.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645592"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="b754e-104">Configurar entidades virtuais do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b754e-104">Configure Common Data Service virtual entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="b754e-105">O Dynamics 365 Human Resources é uma fonte de dados virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="b754e-106">Ele fornece as operações CRUD (criar, ler, atualizar e excluir) completas do Common Data Service e do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b754e-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="b754e-107">Os dados para entidades virtuais não são armazenados no Common Data Service, mas no banco de dado do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b754e-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="b754e-108">Para habilitar as operações CRUD em entidades do Human Resources do Common Data Service, você deverá disponibilizar as entidades como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="b754e-109">Isso permite executar operações CRUD do Common Data Service e do Microsoft Power Platform em dados que estão no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="b754e-110">As operações também dão suporte a validações de lógica comercial completa do Human Resources para garantir a integridade dos dados ao gravar dados nas entidades.</span><span class="sxs-lookup"><span data-stu-id="b754e-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="b754e-111">Entidades virtuais disponíveis para Human Resources</span><span class="sxs-lookup"><span data-stu-id="b754e-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="b754e-112">Todas as entidades Open Data Protocol (OData) no Human Resources estão disponíveis como entidades virtuais no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="b754e-113">Elas também estão disponíveis no Power Platform.</span><span class="sxs-lookup"><span data-stu-id="b754e-113">They're also available in Power Platform.</span></span> <span data-ttu-id="b754e-114">Agora você pode criar aplicativos e experiências com dados diretamente do Human Resources com o recurso CRUD completo, sem copiar ou sincronizar dados para o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="b754e-115">Você pode usar portais do Power Apps para criar sites destinados a externos que permitem cenários de colaboração para processos comerciais no Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="b754e-116">Você pode exibir a lista de entidades virtuais habilitada no ambiente e começar a trabalhar com as entidades no [Power Apps](https://make.powerapps.com), na solução **Entidades Virtuais do Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="b754e-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades Virtuais do Dynamics 365 HR no Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="b754e-118">Entidades virtuais versus entidades naturais</span><span class="sxs-lookup"><span data-stu-id="b754e-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="b754e-119">As entidades virtuais para Human Resources não são iguais das entidades naturais do Common Data Service criadas para o Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="b754e-120">As entidades naturais para o Human Resources são geradas separadamente e mantidas na solução HCM Common no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="b754e-121">Com as entidades naturais, os dados são armazenados no Common Data Service e exigem a sincronização com o banco da dados do aplicativo Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="b754e-122">Para obter uma lista das entidades naturais do Common Data Service para Human Resources, consulte [Entidades do Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="b754e-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="b754e-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="b754e-123">Setup</span></span>

<span data-ttu-id="b754e-124">Siga estas etapas de configuração para habilitar as entidades virtuais no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b754e-124">Follow these setup steps to enable virtual entities in your environment.</span></span>

### <a name="enable-virtual-entities-in-human-resources"></a><span data-ttu-id="b754e-125">Habilitar entidades virtuais em Human Resources</span><span class="sxs-lookup"><span data-stu-id="b754e-125">Enable virtual entities in Human Resources</span></span>

<span data-ttu-id="b754e-126">Primeiro, você deve habilitar entidades virtuais no espaço de trabalho **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="b754e-126">First, you must enable virtual entities in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="b754e-127">No Human Resources, selecione **Administração do sistema**.</span><span class="sxs-lookup"><span data-stu-id="b754e-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="b754e-128">Selecione o bloco **Gerenciamento de recursos**.</span><span class="sxs-lookup"><span data-stu-id="b754e-128">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="b754e-129">Selecione **Suporte da Entidade Virtual em HR/CDs** e selecione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-129">Select **Virtual Entity support in HR/CDS**, and then select **Enable**.</span></span>

<span data-ttu-id="b754e-130">Para obter mais informações sobre como habilitar e desabilitar recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="b754e-130">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="b754e-131">Registrar o aplicativo no Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b754e-131">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="b754e-132">Você precisa registrar sua instância do Human Resources no portal do Azure para que a plataforma de identidade da Microsoft possa fornecer serviços de autenticação e autorização para o aplicativo e os usuários.</span><span class="sxs-lookup"><span data-stu-id="b754e-132">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="b754e-133">Para obter mais informações sobre como registrar aplicativos no Azure, consulte [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="b754e-133">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="b754e-134">Abra o [portal do Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="b754e-134">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="b754e-135">Na lista Serviços do Azure, selecione **Registros de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="b754e-135">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="b754e-136">Selecione **Novo registro**.</span><span class="sxs-lookup"><span data-stu-id="b754e-136">Select **New registration**.</span></span>

4. <span data-ttu-id="b754e-137">No campo **Nome**, insira um nome descritivo para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b754e-137">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="b754e-138">Por exemplo, **Entidades virtuais do Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="b754e-138">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="b754e-139">No campo **URI de Redirecionamento** , insira a URL do namespace da sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-139">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="b754e-140">Selecione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-140">Select **Register**.</span></span>

7. <span data-ttu-id="b754e-141">Quando o registro for concluído, o portal do Azure exibirá o painel **Visão geral** do registro do aplicativo, que inclui sua **ID de Aplicativo (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="b754e-141">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="b754e-142">Anote a **ID do Aplicativo (cliente)** nesse momento.</span><span class="sxs-lookup"><span data-stu-id="b754e-142">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="b754e-143">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="b754e-143">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="b754e-144">No painel de navegação esquerdo, selecione **Certificados e segredos**.</span><span class="sxs-lookup"><span data-stu-id="b754e-144">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="b754e-145">Na seção **Segredos do cliente** da página, selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="b754e-145">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="b754e-146">Forneça uma descrição, selecione uma duração e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-146">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="b754e-147">Registre o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="b754e-147">Record the secret's value.</span></span> <span data-ttu-id="b754e-148">Você inserirá essas informações ao [Configurar a fonte de dados de entidade virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="b754e-148">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b754e-149">Anote o valor do segredo nesse momento.</span><span class="sxs-lookup"><span data-stu-id="b754e-149">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="b754e-150">O segredo nunca será exibido novamente depois que você sair desta página.</span><span class="sxs-lookup"><span data-stu-id="b754e-150">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="b754e-151">Instalar o aplicativo Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="b754e-151">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="b754e-152">Instale o aplicativo Dynamics 365 HR Virtual Entity no seu ambiente do Power Apps para implantar o pacote da solução da entidade virtual no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-152">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="b754e-153">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b754e-153">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="b754e-154">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-154">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="b754e-155">Na seção **Recursos** da página, selecione **Aplicativos do Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="b754e-155">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="b754e-156">Selecione a ação **Instalar aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="b754e-156">Select the **Install app** action.</span></span>

5. <span data-ttu-id="b754e-157">Selecione **Dynamics 365 HR Virtual Entity** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-157">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="b754e-158">Analisar e marcar para concordar com os termos de serviço.</span><span class="sxs-lookup"><span data-stu-id="b754e-158">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="b754e-159">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-159">Select **Install**.</span></span>

<span data-ttu-id="b754e-160">A instalação demora alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="b754e-160">The install takes a few minutes.</span></span> <span data-ttu-id="b754e-161">Ao concluir, prossiga para as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="b754e-161">When it completes, continue to the next steps.</span></span>

![Instalar o aplicativo Dynamics 365 HR Virtual Entity do centro de administração do Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="b754e-163">Configurar a fonte de dados da entidade virtual</span><span class="sxs-lookup"><span data-stu-id="b754e-163">Configure the virtual entity data source</span></span> 

<span data-ttu-id="b754e-164">A próxima etapa é configurar a fonte de dados de entidade virtual no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b754e-164">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="b754e-165">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b754e-165">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="b754e-166">Na lista **Ambientes**, selecione o ambiente do Power Apps associado à sua instância do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-166">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="b754e-167">Selecione a **URL de Ambiente** na seção **Detalhes** da página.</span><span class="sxs-lookup"><span data-stu-id="b754e-167">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="b754e-168">No **Hub de Integridade da Solução** , selecione o ícone **Localização Avançada** no canto superior direito da página do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="b754e-168">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="b754e-169">Na página **Localização Avançada**, na lista suspensa **Procurar**, selecione **Configurações de Fonte de Dados Virtual do Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="b754e-169">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="b754e-170">Selecione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="b754e-170">Select **Results**.</span></span>

7. <span data-ttu-id="b754e-171">Selecione o registro **Fonte de Dados do Microsoft HR**.</span><span class="sxs-lookup"><span data-stu-id="b754e-171">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="b754e-172">Insira as informações necessárias para a configuração da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="b754e-172">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="b754e-173">**URL de Destino**: a URL do namespace do Human Resources.</span><span class="sxs-lookup"><span data-stu-id="b754e-173">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="b754e-174">O formato da URL de destino é:</span><span class="sxs-lookup"><span data-stu-id="b754e-174">The format of the target URL is:</span></span>
     
     <span data-ttu-id="b754e-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="b754e-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="b754e-176">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="b754e-176">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="b754e-177">Inclua o caractere "**/**" no final da URL para evitar o recebimento de um erro.</span><span class="sxs-lookup"><span data-stu-id="b754e-177">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="b754e-178">**ID do Locatário**: a ID do locatário do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b754e-178">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="b754e-179">**ID do Aplicativo AAD**: a ID do aplicativo (cliente) criada para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b754e-179">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="b754e-180">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="b754e-180">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="b754e-181">**Segredo do Aplicativo AAD**: o segredo do cliente criado para o aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b754e-181">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="b754e-182">Você recebeu essas informações antes durante a etapa [Registrar o aplicativo no Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="b754e-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fonte de Dados do Microsoft HR](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="b754e-184">Selecione **Salvar e Fechar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-184">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="b754e-185">Conceder permissões de aplicativo no Human Resources</span><span class="sxs-lookup"><span data-stu-id="b754e-185">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="b754e-186">Conceda permissões para os dois aplicativos do Azure AD no Human Resources:</span><span class="sxs-lookup"><span data-stu-id="b754e-186">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="b754e-187">O aplicativo criado para o seu locatário no portal do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b754e-187">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="b754e-188">O aplicativo Dynamics 365 HR Virtual Entity instalado no ambiente do Power Apps</span><span class="sxs-lookup"><span data-stu-id="b754e-188">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="b754e-189">No Human Resources, abra a página **Aplicativos do Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b754e-189">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="b754e-190">Selecione **Novo** para criar um novo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="b754e-190">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="b754e-191">No campo **ID do Cliente**, insira a ID do cliente do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b754e-191">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="b754e-192">No campo **Nome**, insira o nome do aplicativo registrado no portal do Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="b754e-192">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="b754e-193">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b754e-193">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="b754e-194">Selecione **Novo** para criar um segundo registro de aplicativo:</span><span class="sxs-lookup"><span data-stu-id="b754e-194">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="b754e-195">**ID do Cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="b754e-195">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="b754e-196">**Nome**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="b754e-196">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="b754e-197">No campo **ID do Usuário**, selecione a ID de usuário com permissões de administrador no Human Resources e no ambiente do Power Apps.</span><span class="sxs-lookup"><span data-stu-id="b754e-197">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="b754e-198">Gerar entidades virtuais</span><span class="sxs-lookup"><span data-stu-id="b754e-198">Generate virtual entities</span></span>

<span data-ttu-id="b754e-199">Quando a configuração for concluída, você poderá selecionar as entidades virtuais que deseja gerar e habilitar na instância do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-199">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="b754e-200">No Human Resources, abra a página **Integração do Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="b754e-200">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="b754e-201">Selecione a guia **Entidades virtuais**.</span><span class="sxs-lookup"><span data-stu-id="b754e-201">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="b754e-202">A alternância **Habilitar a entidade virtual** será definida como **Sim** automaticamente quando todas as configurações necessárias forem concluídas.</span><span class="sxs-lookup"><span data-stu-id="b754e-202">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="b754e-203">Se a alternância estiver definida como **Não**, revise as etapas nas seções anteriores deste documento para verificar se toda a configuração de pré-requisitos foi concluída.</span><span class="sxs-lookup"><span data-stu-id="b754e-203">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="b754e-204">Selecione a entidade ou entidades que deseja gerar no Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-204">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="b754e-205">Selecione **Gerar/atualizar**.</span><span class="sxs-lookup"><span data-stu-id="b754e-205">Select **Generate/refresh**.</span></span>

![Integração do Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="b754e-207">Verificar status de geração de entidade</span><span class="sxs-lookup"><span data-stu-id="b754e-207">Check entity generation status</span></span>

<span data-ttu-id="b754e-208">As entidades virtuais são geradas no Common Data Service por meio de um processo assíncrono em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b754e-208">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="b754e-209">Atualizações na exibição do processo na central de ações.</span><span class="sxs-lookup"><span data-stu-id="b754e-209">Updates on the process display in the action center.</span></span> <span data-ttu-id="b754e-210">Os detalhes sobre o processo, incluindo logs de erros, são exibidos na página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="b754e-210">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="b754e-211">No Human Resources, abra a página **Automações de processo**.</span><span class="sxs-lookup"><span data-stu-id="b754e-211">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="b754e-212">Selecione a guia **Processos em segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="b754e-212">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="b754e-213">Selecione o **Processo em segundo plano de operação assíncrona de pesquisa de entidades virtuais**.</span><span class="sxs-lookup"><span data-stu-id="b754e-213">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="b754e-214">Selecione **Exibir resultados mais recentes**.</span><span class="sxs-lookup"><span data-stu-id="b754e-214">Select **View most recent results**.</span></span>

<span data-ttu-id="b754e-215">O painel deslizante exibe os resultados da execução mais recente para o processo.</span><span class="sxs-lookup"><span data-stu-id="b754e-215">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="b754e-216">Você pode exibir o log do processo, incluindo todos os erros retornados do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b754e-216">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="b754e-217">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b754e-217">See also</span></span>

[<span data-ttu-id="b754e-218">O que é o Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="b754e-218">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="b754e-219">Visão geral de entidades</span><span class="sxs-lookup"><span data-stu-id="b754e-219">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="b754e-220">Visão geral de relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="b754e-220">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="b754e-221">Criar e editar entidades virtuais que contenham dados de uma fonte de dados externa</span><span class="sxs-lookup"><span data-stu-id="b754e-221">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="b754e-222">O que são os portais do Power Apps?</span><span class="sxs-lookup"><span data-stu-id="b754e-222">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="b754e-223">Visão geral da criação de aplicativos no Power Apps</span><span class="sxs-lookup"><span data-stu-id="b754e-223">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
