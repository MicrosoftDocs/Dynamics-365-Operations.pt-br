---
title: Configuração do Finance Insights - versões até a 10.0.19
description: Este tópico explica as etapas de configuração que habilitarão seu sistema a usar as funcionalidades que estão disponíveis no Finance Insights para versões até o 10.0.19.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ad06bb6d041fc060b3a99538f6d4d0af333180f
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186411"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="3ddc3-103">Configuração de Insights do Finance (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="3ddc3-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="3ddc3-104">Os seguintes procedimentos para configurar o Finance Insights são válidos para as versões do Microsoft Dynamics 365 Finance até a 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-104">The following procedures for setting up Finance insights are valid for Microsoft Dynamics 365 Finance versions up to 10.0.19.</span></span> <span data-ttu-id="3ddc3-105">Para configurar o Finance Insights na versão do 10.0.20 e posterior, consulte [Configuração para o Finance Insights (versão preliminar) - versões 10.0.20 e além](configure-for-fin-insites-PubPrvw.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-105">To set up Finance insights on version 10.0.20 and later, see [Configuration for Finance Insights (preview) - versions 10.0.20 and beyond](configure-for-fin-insites-PubPrvw.md).</span></span>

<span data-ttu-id="3ddc3-106">Os insights do Finance combinam a funcionalidade do Microsoft Dynamics 365 Finance com o Microsoft Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-106">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="3ddc3-107">Este tópico explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis nos insights do Finance.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-107">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="3ddc3-108">Implantar Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="3ddc3-108">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="3ddc3-109">Implante os ambientes seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-109">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="3ddc3-110">No Microsoft Dynamics Lifecycle Services (LCS), crie ou atualize um ambiente do Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="3ddc3-111">O ambiente exige uma versão do aplicativo 10.0.11/Platform update 35 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-111">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="3ddc3-112">O ambiente deve ser de alta disponibilidade na Área restrita.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="3ddc3-113">(Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="3ddc3-114">Se você estiver configurando o Finance Insights em um ambiente de área restrita, talvez você precise copiar os dados de produção nesse ambiente para que as previsões funcionem.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="3ddc3-115">O modelo de previsão usa vários anos de dados para criar previsões.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="3ddc3-116">Os dados de demonstração da Contoso não contêm dados históricos suficientes para treinar o modelo de previsão corretamente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="3ddc3-117">Configurar o Dataverse</span><span class="sxs-lookup"><span data-stu-id="3ddc3-117">Configure Dataverse</span></span>

<span data-ttu-id="3ddc3-118">Use as etapas a seguir para configurar o Dataverse para Finance insights.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-118">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="3ddc3-119">Abra a página do ambiente no LCS e verifique se a seção **Power Platform** já está configurada.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-119">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="3ddc3-120">Se já estiver configurada, o nome do ambiente do Dataverse vinculado ao Ambiente do Dynamics 365 Finance deverá ser listado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-120">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="3ddc3-121">Copie o nome do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-121">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="3ddc3-122">Se não estiver configurada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-122">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="3ddc3-123">Selecione o botão **Configurar** na seção de integração do Power Platform.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-123">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="3ddc3-124">A configuração do ambiente pode demorar até uma hora.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-124">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="3ddc3-125">Se o ambiente do Dataverse for configurado com sucesso, o nome do ambiente do Dataverse vinculado ao Ambiente do Dynamics 365 Finance deve ser listado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-125">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="3ddc3-126">Copie o nome do ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-126">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="3ddc3-127">Após concluir a configuração do ambiente, **NÃO** selecione o botão **Link para o CDS para aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-127">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="3ddc3-128">Isso não é necessário para Finance Insights e desabilitará a capacidade de concluir os Suplementos de Ambiente necessários no LCS.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-128">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="3ddc3-129">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/) e siga estas etapas para criar um ambiente do Dataverse no mesmo locatário do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-129">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="3ddc3-130">Abra a página **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-130">Open the **Environments** page.</span></span>

        <span data-ttu-id="3ddc3-131">[![Página de ambientes](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="3ddc3-131">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="3ddc3-132">Selecione o ambiente do Dataverse criado acime e, em seguida, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-132">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="3ddc3-133">Selecione **Recursos \> Todas as Configurações Herdadas**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-133">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="3ddc3-134">Na barra de navegação superior, selecione **Configurações** e depois **Personalizações**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-134">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="3ddc3-135">Selecione **Recursos do Desenvolvedor**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-135">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="3ddc3-136">Copie o valor da **ID da organização do Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-136">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="3ddc3-137">Na barra de endereços do navegador, anote a URL da organização do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-137">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="3ddc3-138">Por exemplo, a URL pode ser `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-138">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="3ddc3-139">Se você planeja usar o recurso Previsões de fluxo de caixa ou Previsões de orçamento, siga estas etapas para atualizar o limite de anotação da sua organização para pelo menos 50 megabytes (MB):</span><span class="sxs-lookup"><span data-stu-id="3ddc3-139">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="3ddc3-140">Abra o [portal do Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-140">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="3ddc3-141">Selecione o ambiente recém-criado e depois selecione **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-141">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="3ddc3-142">Selecione **Configurações \> Configuração de Email**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-142">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="3ddc3-143">Altere o valor do campo **Tamanho máximo do arquivo** para **51.200**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-143">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="3ddc3-144">(O valor é expresso em quilobytes \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="3ddc3-144">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="3ddc3-145">Selecione **OK** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-145">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="3ddc3-146">Configurar a definição do Azure</span><span class="sxs-lookup"><span data-stu-id="3ddc3-146">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="3ddc3-147">Insira a ID do diretório do Dataverse e a ID do objeto do Azure AD do usuário</span><span class="sxs-lookup"><span data-stu-id="3ddc3-147">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="3ddc3-148">Insira a ID do diretório do Dataverse:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-148">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="3ddc3-149">Abra o [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-149">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="3ddc3-150">Entre com a ID de usuário usada para criar o ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-150">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="3ddc3-151">Acesse **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-151">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="3ddc3-152">Copie o valor da **ID de locatário**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-152">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="3ddc3-153">Insira a ID de objeto do Azure Active Directory (Azure AD) do usuário:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-153">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="3ddc3-154">No [portal do Azure](https://portal.azure.com), acesse **Usuários** e pesquise o usuário pelo endereço de email.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-154">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="3ddc3-155">Selecione o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-155">Select the user's name.</span></span>
    3. <span data-ttu-id="3ddc3-156">Copie o valor da **ID do objeto**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-156">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="3ddc3-157">Use o Azure Cloud Shell para configurar os recursos de Data Lake dos insights do Finance</span><span class="sxs-lookup"><span data-stu-id="3ddc3-157">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="3ddc3-158">Use um script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ddc3-158">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="3ddc3-159">Um script do Windows PowerShell foi fornecido para que você possa facilmente configurar os recursos do Azure descritos em [Configurar exportação para o Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-159">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="3ddc3-160">Se preferir fazer a configuração manual, ignore este procedimento e continue com o procedimento na seção [Configuração manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-160">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="3ddc3-161">Siga as etapas abaixo para executar o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-161">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="3ddc3-162">A opção "Experimente" da CLI do Azure ou a execução do script no PC pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-162">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="3ddc3-163">Siga estas etapas para configurar o Azure usando o script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-163">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="3ddc3-164">É necessário ter os direitos para criar um grupo de recursos do Azure, recursos do Azure e um aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-164">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="3ddc3-165">Para obter informações sobre as permissões necessárias, consulte [Verificar permissões do Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-165">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="3ddc3-166">No [portal do Azure](https://portal.azure.com), vá para a assinatura do Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-166">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="3ddc3-167">Selecione o botão **Cloud Shell** à direita do campo **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-167">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="3ddc3-168">Selecione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-168">Select **PowerShell**.</span></span>
3. <span data-ttu-id="3ddc3-169">Crie o armazenamento, caso seja solicitado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-169">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="3ddc3-170">Vá para a guia **CLI do Azure** e selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-170">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="3ddc3-171">Abra o Bloco de notas e cole o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-171">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="3ddc3-172">Salve o arquivo como ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-172">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="3ddc3-173">Carregue o script do Windows PowerShell na sessão usando a opção de menu para carregar no Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-173">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="3ddc3-174">Execute o script .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-174">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="3ddc3-175">Siga as instruções para executar o script.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-175">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="3ddc3-176">Use as informações de saída do script para instalar o suplemento **Exportar para Data Lake** no LCS.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-176">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="3ddc3-177">Use as informações de saída do script para habilitar o armazenamento da entidade na página **Conexões de dados** no Finance (**Administração do sistema \> Parâmetros do sistema \> Conexões de dados**).</span><span class="sxs-lookup"><span data-stu-id="3ddc3-177">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="3ddc3-178">Configuração manual</span><span class="sxs-lookup"><span data-stu-id="3ddc3-178">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="3ddc3-179">Adicionar aplicativos ao locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="3ddc3-179">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="3ddc3-180">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-180">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="3ddc3-181">Selecione **Gerenciar \> Aplicativos empresariais**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-181">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="3ddc3-182">Procure os seguintes aplicativos por ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-182">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="3ddc3-183">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="3ddc3-183">Application</span></span>                              | <span data-ttu-id="3ddc3-184">ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3ddc3-184">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="3ddc3-185">Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="3ddc3-185">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="3ddc3-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="3ddc3-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="3ddc3-187">CDS de Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="3ddc3-187">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="3ddc3-188">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="3ddc3-188">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="3ddc3-189">Serviço de Autorização do AI Builder</span><span class="sxs-lookup"><span data-stu-id="3ddc3-189">AI Builder Authorization Service</span></span>         | <span data-ttu-id="3ddc3-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="3ddc3-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="3ddc3-191">Caso não encontre nenhum dos aplicativos anteriores, tente executar as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-191">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="3ddc3-192">No computador local, selecione o menu **Iniciar** e pesquise **powershell**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-192">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="3ddc3-193">Selecione e mantenha pressionado (ou clique com o botão direito) **Windows PowerShell** e depois selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-193">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="3ddc3-194">Execute o seguinte comando para instalar o módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-194">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="3ddc3-195">Se um provedor de NuGet for necessário para continuar, selecione **Y** para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-195">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="3ddc3-196">Se uma mensagem "Repositório não confiável" for exibida, selecione **Y** para continuar.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-196">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="3ddc3-197">Para cada aplicativo que deve ser adicionado, execute os seguintes comandos para adicionar o aplicativo ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-197">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="3ddc3-198">Quando solicitado, entre como administrador do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-198">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="3ddc3-199">Criar recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="3ddc3-199">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="3ddc3-200">Certifique-se de criar os seguintes recursos na mesma instância do Azure AD como ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-200">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="3ddc3-201">Não é possível usar recursos de outra instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-201">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="3ddc3-202">Crie uma conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-202">Create a new storage account:</span></span>

    1. <span data-ttu-id="3ddc3-203">No [portal do Azure](https://portal.azure.com), crie uma conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-203">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="3ddc3-204">Na caixa de diálogo **Criar conta de armazenamento**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-204">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="3ddc3-205">**Local** – Selecione o data center em que o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-205">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="3ddc3-206">**Desempenho** – Recomendamos selecionar **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-206">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="3ddc3-207">**Tipo de conta** – É necessário selecionar **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-207">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="3ddc3-208">Na caixa de diálogo **Opções avançadas**, na opção **Data Lake Storage Gen2**, selecione **Habilitar** no recurso **Namespaces hierárquicos**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-208">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="3ddc3-209">Se você desabilitar esse recurso, não poderá consumir dados que os aplicativos do Finance and Operations gravam usando serviços como fluxos de dados do Power BI.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-209">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="3ddc3-210">Selecione **Revisar e criar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-210">Select **Review and create**.</span></span> <span data-ttu-id="3ddc3-211">Quando a implantação for concluída, o novo recurso será mostrado no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-211">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="3ddc3-212">Acesse a conta de armazenamento que você criou.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-212">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="3ddc3-213">No menu esquerdo, selecione **Chaves de acesso**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-213">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="3ddc3-214">Copie e salve a cadeia de conexão para **Chave1** ou **Chave2**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-214">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="3ddc3-215">Copie e salve o nome da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-215">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="3ddc3-216">Crie um cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-216">Create a new key vault:</span></span>

    1. <span data-ttu-id="3ddc3-217">No [portal do Azure](https://portal.azure.com), crie um cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-217">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="3ddc3-218">Na caixa de diálogo **Criar cofre de chaves**, no campo **Local**, selecione o data center no qual o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-218">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="3ddc3-219">Após criar o cofre de chaves, selecione-o na lista e depois selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-219">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="3ddc3-220">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-220">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="3ddc3-221">Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-221">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="3ddc3-222">Digite um nome para o segredo.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-222">Enter a name for the secret.</span></span> <span data-ttu-id="3ddc3-223">Anote o nome, pois ele será solicitado depois.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-223">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="3ddc3-224">No campo **Valor**, insira a cadeia de conexão obtida da conta de armazenamento no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-224">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="3ddc3-225">Selecione **Habilitado** e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-225">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="3ddc3-226">O segredo é criado e adicionado ao Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-226">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="3ddc3-227">Vá para a **Visão Geral do Cofre de Chaves** e anote o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-227">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="3ddc3-228">Criar e registrar um aplicativo do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-228">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="3ddc3-229">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e selecione **Registros de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-229">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="3ddc3-230">Selecione **Novo registro de aplicativo** e defina os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-230">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="3ddc3-231">**Nome** – Insira o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-231">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="3ddc3-232">**Tipo de aplicativo** – Selecione **API Web**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-232">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="3ddc3-233">**Redirecionar configuração de URI** – Insira a URL da instância do Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-233">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="3ddc3-234">Vá para o aplicativo recém-criado e copie e salve o valor da **ID (do cliente) do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-234">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="3ddc3-235">Você terá que fornecer esse valor mais tarde, ao configurar o cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-235">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="3ddc3-236">Vá para **Permissões de API** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-236">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="3ddc3-237">Selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-237">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="3ddc3-238">Selecione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-238">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="3ddc3-239">Depois de selecionar permissões delegadas, selecione **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-239">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="3ddc3-240">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-240">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="3ddc3-241">No menu do aplicativo, selecione **Certificados \& segredos** e siga as etapas para criar segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-241">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="3ddc3-242">Selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-242">Select **New client secret**.</span></span>
        2. <span data-ttu-id="3ddc3-243">No campo **Descrição da Chave**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-243">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="3ddc3-244">Selecione uma duração e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-244">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="3ddc3-245">Um segredo é gerado no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-245">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="3ddc3-246">Copie e salve o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-246">Copy and save the secret value.</span></span>

4. <span data-ttu-id="3ddc3-247">Crie segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-247">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="3ddc3-248">Vá para o cofre de chaves criado anteriormente e selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-248">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="3ddc3-249">Para cada nome de segredo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-249">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="3ddc3-250">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-250">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="3ddc3-251">Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-251">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="3ddc3-252">Crie o nome e o valor do segredo da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-252">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="3ddc3-253">Selecione **Habilitado** e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-253">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="3ddc3-254">O segredo é criado e adicionado ao Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-254">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="3ddc3-255">Nome secreto</span><span class="sxs-lookup"><span data-stu-id="3ddc3-255">Secret name</span></span>                       | <span data-ttu-id="3ddc3-256">Valor do segredo</span><span class="sxs-lookup"><span data-stu-id="3ddc3-256">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="3ddc3-257">app-id</span><span class="sxs-lookup"><span data-stu-id="3ddc3-257">app-id</span></span>                            | <span data-ttu-id="3ddc3-258">A ID do aplicativo criado anteriormente</span><span class="sxs-lookup"><span data-stu-id="3ddc3-258">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="3ddc3-259">app-secret</span><span class="sxs-lookup"><span data-stu-id="3ddc3-259">app-secret</span></span>                        | <span data-ttu-id="3ddc3-260">O segredo do cliente salvo anteriormente</span><span class="sxs-lookup"><span data-stu-id="3ddc3-260">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="3ddc3-261">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="3ddc3-261">storage-account-name</span></span>              | <span data-ttu-id="3ddc3-262">O nome da conta de armazenamento criada anteriormente, como **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-262">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="3ddc3-263">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="3ddc3-263">storage-account-connection-string</span></span> | <span data-ttu-id="3ddc3-264">A cadeia de conexão copiada da página **Chaves de acesso** para a conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="3ddc3-264">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="3ddc3-265">Autorize o acesso do aplicativo ao cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-265">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="3ddc3-266">No [portal do Azure](https://portal.azure.com), abra o cofre de chaves criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-266">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="3ddc3-267">Selecione as políticas de acesso.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-267">Select the access policies.</span></span>
    3. <span data-ttu-id="3ddc3-268">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-268">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="3ddc3-269">Selecione **Adicionar Política de Acesso** para criar uma política de acesso.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-269">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="3ddc3-270">No campo **Permissões do segredo**, selecione as permissões da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-270">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="3ddc3-271">No campo **Selecionar entidade de segurança**, pesquise o nome de exibição do aplicativo na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-271">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="3ddc3-272">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-272">Select **Select**.</span></span>
        5. <span data-ttu-id="3ddc3-273">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-273">Select **Add**.</span></span>
        6. <span data-ttu-id="3ddc3-274">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-274">Select **Save**.</span></span>

        | <span data-ttu-id="3ddc3-275">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="3ddc3-275">Application</span></span>                                              | <span data-ttu-id="3ddc3-276">Permissões</span><span class="sxs-lookup"><span data-stu-id="3ddc3-276">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="3ddc3-277">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="3ddc3-277">The display name of the new application that you created</span></span> | <span data-ttu-id="3ddc3-278">Get, List</span><span class="sxs-lookup"><span data-stu-id="3ddc3-278">Get, List</span></span>   |
        | <span data-ttu-id="3ddc3-279">**Microsserviços de ERP do Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-279">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="3ddc3-280">Get, List</span><span class="sxs-lookup"><span data-stu-id="3ddc3-280">Get, List</span></span>   |

6. <span data-ttu-id="3ddc3-281">Atribuir funções para acessar a conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-281">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="3ddc3-282">No [portal do Azure](https://portal.azure.com), abra a conta de armazenamento criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-282">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="3ddc3-283">Selecione **Controle de Acesso (IAM)** e, em seguida, selecione **Atribuições de Função**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-283">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="3ddc3-284">Selecione **Adicionar, Adicionar Atribuição de Função**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-284">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="3ddc3-285">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-285">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="3ddc3-286">Selecione a função da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-286">Select the role from the following table.</span></span>
        2. <span data-ttu-id="3ddc3-287">Deixe o campo **Atribuir acesso a** como **Usuário, grupo ou entidade de serviço do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-287">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="3ddc3-288">No campo **Selecionar**, insira o aplicativo da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-288">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="3ddc3-289">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-289">Select **Save**.</span></span>

        | <span data-ttu-id="3ddc3-290">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="3ddc3-290">Application</span></span>                                              | <span data-ttu-id="3ddc3-291">Função</span><span class="sxs-lookup"><span data-stu-id="3ddc3-291">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="3ddc3-292">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="3ddc3-292">The display name of the new application that you created</span></span> | <span data-ttu-id="3ddc3-293">Proprietário</span><span class="sxs-lookup"><span data-stu-id="3ddc3-293">Owner</span></span>                       |
        | <span data-ttu-id="3ddc3-294">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="3ddc3-294">The display name of the new application that you created</span></span> | <span data-ttu-id="3ddc3-295">Colaborador</span><span class="sxs-lookup"><span data-stu-id="3ddc3-295">Contributor</span></span>                 |
        | <span data-ttu-id="3ddc3-296">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="3ddc3-296">The display name of the new application that you created</span></span> | <span data-ttu-id="3ddc3-297">Colaborador da Conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="3ddc3-297">Storage Account Contributor</span></span> |
        | <span data-ttu-id="3ddc3-298">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="3ddc3-298">The display name of the new application that you created</span></span> | <span data-ttu-id="3ddc3-299">Proprietário de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="3ddc3-299">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="3ddc3-300">**Serviço de Autorização do AI Builder**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-300">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="3ddc3-301">Leitor de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="3ddc3-301">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="3ddc3-302">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="3ddc3-302">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}

```
---



## <a name="configure-the-data-lake"></a><span data-ttu-id="3ddc3-303">Configurar o data lake</span><span class="sxs-lookup"><span data-stu-id="3ddc3-303">Configure the data lake</span></span>

<span data-ttu-id="3ddc3-304">Siga estas etapas para usar o LCS para adicionar o suplemento do Azure Data Lake ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-304">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="3ddc3-305">Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-305">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="3ddc3-306">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-306">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="3ddc3-307">Selecione o suplemento **Exportar para o Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-307">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="3ddc3-308">Insira os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-308">Enter the following values.</span></span>

    | <span data-ttu-id="3ddc3-309">Alíquota</span><span class="sxs-lookup"><span data-stu-id="3ddc3-309">Value</span></span>                                                              | <span data-ttu-id="3ddc3-310">descrição</span><span class="sxs-lookup"><span data-stu-id="3ddc3-310">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="3ddc3-311">ID de Locatário da Assinatura do Azure em que o Key Vault está localizado</span><span class="sxs-lookup"><span data-stu-id="3ddc3-311">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="3ddc3-312">A ID de locatário onde a conta de armazenamento, os aplicativos e os cofres de chaves estão localizados.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-312">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="3ddc3-313">Para encontrar esse valor, abra o [portal do Azure](https://portal.azure.com), vá para o **Azure Active Directory** e copie o valor da **ID de Locatário**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-313">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="3ddc3-314">Forneça o nome DNS de seu Key Vault</span><span class="sxs-lookup"><span data-stu-id="3ddc3-314">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="3ddc3-315">O nome DNS do cofre de chaves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-315">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="3ddc3-316">(Esse valor corresponde ao nome DNS usado no repositório de entidades.)</span><span class="sxs-lookup"><span data-stu-id="3ddc3-316">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="3ddc3-317">Forneça o segredo que contém o nome da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="3ddc3-317">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="3ddc3-318">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-318">**storage-account-name**</span></span> |
    | <span data-ttu-id="3ddc3-319">Nome do Segredo da ID do Aplicativo que será usada para acessar o Data Lake</span><span class="sxs-lookup"><span data-stu-id="3ddc3-319">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="3ddc3-320">**app-id**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-320">**app-id**</span></span> |
    | <span data-ttu-id="3ddc3-321">Nome do segredo que será usado com a ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="3ddc3-321">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="3ddc3-322">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="3ddc3-322">**app-secret**</span></span> |

5. <span data-ttu-id="3ddc3-323">Concorde com os termos e selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-323">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="3ddc3-324">O suplemento será instalado em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-324">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="3ddc3-325">Configurar o AI Builder</span><span class="sxs-lookup"><span data-stu-id="3ddc3-325">Configure AI Builder</span></span>

1. <span data-ttu-id="3ddc3-326">Entre no LCS e abra a página **Detalhes do ambiente**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-326">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="3ddc3-327">Role até a seção **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-327">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="3ddc3-328">Você verá os suplementos que já estão instalados nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-328">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="3ddc3-329">Se o suplemento **Exportar para Data Lake** não estiver entre eles, configure-o.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-329">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="3ddc3-330">Selecione o suplemento **Obter insights**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-330">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="3ddc3-331">Na página de detalhes do suplemento **Obter insights**, insira os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-331">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="3ddc3-332">Alíquota</span><span class="sxs-lookup"><span data-stu-id="3ddc3-332">Value</span></span>                                                    | <span data-ttu-id="3ddc3-333">descrição</span><span class="sxs-lookup"><span data-stu-id="3ddc3-333">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="3ddc3-334">URL da Organização CDS</span><span class="sxs-lookup"><span data-stu-id="3ddc3-334">CDS Organization URL</span></span>                                     | <span data-ttu-id="3ddc3-335">O URL da organização do Dataverse copiado de cima.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-335">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="3ddc3-336">ID da Organização CDS</span><span class="sxs-lookup"><span data-stu-id="3ddc3-336">CDS Org ID</span></span>                                               | <span data-ttu-id="3ddc3-337">A ID da organização do Dataverse copiada de cima.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-337">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="3ddc3-338">Ative **Este é o ambiente padrão do seu Locatário?**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-338">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="3ddc3-339">Configure o armazenamento da entidade</span><span class="sxs-lookup"><span data-stu-id="3ddc3-339">Configure the entity store</span></span>

<span data-ttu-id="3ddc3-340">Siga estas etapas para configurar o repositório de entidades no ambiente do Finance.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-340">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="3ddc3-341">Vá para **Administração do sistema \> Configuração \> Parâmetros do sistema \> Conexões de dados**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-341">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="3ddc3-342">Defina os seguintes campos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="3ddc3-342">Set the following key vault fields:</span></span>

    - <span data-ttu-id="3ddc3-343">**ID (do cliente) do aplicativo** – Insira o ID do cliente do aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-343">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="3ddc3-344">**Segredo do Aplicativo** – Insira o segredo salvo para o aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-344">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="3ddc3-345">**Nome DNS** – Você pode encontrar o nome do Sistema de Nome de Domínio (DNS) na página de detalhes do aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-345">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="3ddc3-346">**Nome do segredo** – Insira **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-346">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="3ddc3-347">Ativa **Habilitar a integração do Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-347">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="3ddc3-348">Selecione **Testar Azure Key Vault** e verifique se não há erros.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-348">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="3ddc3-349">Selecione **Testar Armazenamento do Azure** e verifique se não há erros.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-349">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="3ddc3-350">Comentários e suporte</span><span class="sxs-lookup"><span data-stu-id="3ddc3-350">Feedback and support</span></span>

<span data-ttu-id="3ddc3-351">Envie um email para [insights de pagamento do cliente (versão prévia)](mailto:fiap@microsoft.com) se tiver interesse em fornecer comentários ou precisar de suporte.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-351">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="3ddc3-352">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="3ddc3-352">Privacy notice</span></span>

<span data-ttu-id="3ddc3-353">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="3ddc3-353">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
