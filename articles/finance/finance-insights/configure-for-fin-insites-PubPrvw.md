---
title: Configuração para o Finance Insights para versão preliminar pública - versão 10.0.20 e posterior
description: Este tópico explica como configurar seu sistema para usar os recursos disponíveis no Finance Insights para a versão preliminar pública 10.0.20 e posterior.
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
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222603"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="588b4-103">Configuração para o Finance Insights para versão preliminar pública - versão 10.0.20 e posterior</span><span class="sxs-lookup"><span data-stu-id="588b4-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="588b4-104">Os insights do Finance combinam a funcionalidade do Microsoft Dynamics 365 Finance com o Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="588b4-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="588b4-105">Este tópico explica como configurar o Dynamics 365 Finance versão 10.0.20 para que o seu sistema possa usar os recursos disponíveis na versão preliminar pública do Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="588b4-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="588b4-106">As etapas de configuração que são descritas neste tópico aplicam-se somente ao Finance versão 10.0.20 e posterior.</span><span class="sxs-lookup"><span data-stu-id="588b4-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="588b4-107">'Para configurar o Finance Insights nas versões 10.0.19 e anteriores, consulte [Configuração para o Finance Insights - versões até 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="588b4-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="588b4-108">Implantação no Finance</span><span class="sxs-lookup"><span data-stu-id="588b4-108">Deploy Finance</span></span>

<span data-ttu-id="588b4-109">Para implantar os ambientes, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="588b4-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="588b4-110">No Microsoft Dynamics Lifecycle Services (LCS), crie ou atualize o ambiente do Finance.</span><span class="sxs-lookup"><span data-stu-id="588b4-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="588b4-111">Um ambiente com a versão 10.0.20 ou posterior de aplicativos do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="588b4-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="588b4-112">O ambiente deve ser de alta disponibilidade na Área restrita.</span><span class="sxs-lookup"><span data-stu-id="588b4-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="588b4-113">(Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="588b4-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="588b4-114">Se você estiver configurando o Finance Insights em um ambiente de área restrita, talvez você precise copiar os dados de produção nesse ambiente para que as previsões funcionem.</span><span class="sxs-lookup"><span data-stu-id="588b4-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="588b4-115">O modelo de previsão usa vários anos de dados para criar previsões.</span><span class="sxs-lookup"><span data-stu-id="588b4-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="588b4-116">Os dados de demonstração da Contoso não contêm dados históricos suficientes para treinar o modelo de previsão corretamente.</span><span class="sxs-lookup"><span data-stu-id="588b4-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="588b4-117">Configurar o Dataverse</span><span class="sxs-lookup"><span data-stu-id="588b4-117">Configure Dataverse</span></span>

<span data-ttu-id="588b4-118">Para configurar o Dataverse para Finance Insights, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="588b4-119">No LCS, abra a página do ambiente e verifique se a seção **Integração do Power Platform** já está configurado.</span><span class="sxs-lookup"><span data-stu-id="588b4-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="588b4-120">Se ela já estiver configurada, o nome do ambiente do Dataverse que está vinculado ao ambiente deve do Finance deve aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="588b4-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="588b4-121">Se ela não estiver configurada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="588b4-122">Na seção **Integração do Power Platform**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="588b4-123">A configuração do ambiente pode levar até uma hora.</span><span class="sxs-lookup"><span data-stu-id="588b4-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="588b4-124">Se o ambiente do Dataverse for configurado com êxito, o nome do ambiente do Dataverse que está vinculado ao ambiente deve do Finance deve aparecer na lista.</span><span class="sxs-lookup"><span data-stu-id="588b4-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="588b4-125">Ao usar o link para abrir o ambiente, **não** selecione **Vincular ao CDS para Aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="588b4-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="588b4-126">Este botão não é necessário para o Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="588b4-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="588b4-127">Se você o selecionar, não será possível configurar os suplementos necessários do ambiente no LCS.</span><span class="sxs-lookup"><span data-stu-id="588b4-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="588b4-128">Configurar o Azure</span><span class="sxs-lookup"><span data-stu-id="588b4-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="588b4-129">Use o Azure Cloud Shell para configurar os recursos de Data Lake dos insights do Finance</span><span class="sxs-lookup"><span data-stu-id="588b4-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="588b4-130">Use um script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="588b4-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="588b4-131">O script do Windows PowerShell foi fornecido para que você possa configurar facilmente os recursos do Azure que são descritos em [Configurar exportação para Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="588b4-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="588b4-132">Se você preferir fazer a configuração manualmente, pule este procedimento e, em vez disso, conclua o procedimento da seção [Configuração Manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="588b4-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="588b4-133">Use os seguintes procedimentos para executar o script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="588b4-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="588b4-134">A configuração pode não funcionar se você usar a opção **Experimentar** no CLI do Azure ou se você executar o script no seu computador.</span><span class="sxs-lookup"><span data-stu-id="588b4-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="588b4-135">Siga as seguintes etapas para usar o script do Windows PowerShell para configurar o Azure.</span><span class="sxs-lookup"><span data-stu-id="588b4-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="588b4-136">É necessário ter os direitos para criar um grupo de recursos do Azure, recursos do Azure e um aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="588b4-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="588b4-137">Para obter informações sobre as permissões necessárias, consulte [Verificar permissões do Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="588b4-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="588b4-138">No [portal do Azure](https://portal.azure.com), vá para a assinatura do Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="588b4-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="588b4-139">Selecione **Cloud Shell** à direita do campo **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="588b4-140">Selecione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="588b4-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="588b4-141">Crie o armazenamento se isso for solicitado a você.</span><span class="sxs-lookup"><span data-stu-id="588b4-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="588b4-142">Na guia **CLI do Azure**, selecione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="588b4-143">No Bloco de notas, abra um novo arquivo e copie o script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="588b4-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="588b4-144">Salve o arquivo localmente como **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="588b4-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="588b4-145">Faça upload do script do Windows PowerShell à sessão usando a opção de menu para upload no Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="588b4-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="588b4-146">Execute o script **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="588b4-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="588b4-147">Siga as instruções para executar o script.</span><span class="sxs-lookup"><span data-stu-id="588b4-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="588b4-148">Use as informações de saída do script para instalar o suplemento Exportar para Data Lake no LCS.</span><span class="sxs-lookup"><span data-stu-id="588b4-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="588b4-149">Configuração manual</span><span class="sxs-lookup"><span data-stu-id="588b4-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="588b4-150">Adicionar aplicativos ao locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="588b4-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="588b4-151">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="588b4-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="588b4-152">Selecione **Gerenciar \> Aplicativos empresariais**.</span><span class="sxs-lookup"><span data-stu-id="588b4-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="588b4-153">Procure os seguintes aplicativos por ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="588b4-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="588b4-154">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="588b4-154">Application</span></span>                              | <span data-ttu-id="588b4-155">ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="588b4-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="588b4-156">Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="588b4-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="588b4-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="588b4-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="588b4-158">CDS de Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="588b4-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="588b4-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="588b4-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="588b4-160">Serviço de Autorização do AI Builder</span><span class="sxs-lookup"><span data-stu-id="588b4-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="588b4-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="588b4-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="588b4-162">Caso não encontre nenhum dos aplicativos anteriores, tente executar as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="588b4-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="588b4-163">No computador local, no menu **Iniciar**, pesquise **powershell**.</span><span class="sxs-lookup"><span data-stu-id="588b4-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="588b4-164">Selecione e mantenha pressionado (ou clique com o botão direito) **Windows PowerShell** e depois selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="588b4-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="588b4-165">Execute o seguinte comando para instalar o módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="588b4-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="588b4-166">Se um provedor de NuGet for necessário para continuar, selecione **Y** para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="588b4-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="588b4-167">Se você receber a mensagem "Repositório não confiável", selecione **Y** para continuar.</span><span class="sxs-lookup"><span data-stu-id="588b4-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="588b4-168">Para cada aplicativo que deve ser adicionado, execute os seguintes comandos para adicionar o aplicativo ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="588b4-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="588b4-169">Quando solicitado, entre como administrador do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="588b4-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="588b4-170">Criar recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="588b4-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="588b4-171">Certifique-se de criar os seguintes recursos na mesma instância do Azure AD em que o ambiente do Dataverse está.</span><span class="sxs-lookup"><span data-stu-id="588b4-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="588b4-172">Não é possível usar recursos de outra instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="588b4-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="588b4-173">Criar uma conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="588b4-173">Create a storage account:</span></span>

    1. <span data-ttu-id="588b4-174">No [portal do Azure](https://portal.azure.com), crie uma conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="588b4-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="588b4-175">Na caixa de diálogo **Criar conta de armazenamento**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="588b4-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="588b4-176">**Local** – Selecione o data center em que o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="588b4-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="588b4-177">**Desempenho** – Recomendamos selecionar **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="588b4-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="588b4-178">**Tipo de conta** – É necessário selecionar **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="588b4-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="588b4-179">Na caixa de diálogo **Opções avançadas**, na opção **Data Lake Storage Gen2**, selecione **Habilitar** no recurso **Namespaces hierárquicos**.</span><span class="sxs-lookup"><span data-stu-id="588b4-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="588b4-180">Se você não habilitar este recurso, você não poderá consumir os dados que os aplicativos do Finance and Operations gravarem usando serviços, como os fluxos de dados do Power BI.</span><span class="sxs-lookup"><span data-stu-id="588b4-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="588b4-181">Selecione **Revisar e criar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-181">Select **Review and create**.</span></span> <span data-ttu-id="588b4-182">Quando a implantação for concluída, o novo recurso será mostrado no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="588b4-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="588b4-183">Acesse a conta de armazenamento que você criou.</span><span class="sxs-lookup"><span data-stu-id="588b4-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="588b4-184">No menu esquerdo, selecione **Chaves de acesso**.</span><span class="sxs-lookup"><span data-stu-id="588b4-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="588b4-185">Copie e salve o nome da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="588b4-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="588b4-186">Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="588b4-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="588b4-187">Criar um cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="588b4-187">Create a key vault:</span></span>

    1. <span data-ttu-id="588b4-188">No [portal do Azure](https://portal.azure.com), crie um cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="588b4-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="588b4-189">Na caixa de diálogo **Criar cofre de chaves**, no campo **Local**, selecione o data center no qual o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="588b4-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="588b4-190">Quando um cofre de chaves for criado, vá para **Visão geral do cofre de chaves** e copie e salve o nome do DNS.</span><span class="sxs-lookup"><span data-stu-id="588b4-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="588b4-191">Você precisará fornecer este valor mais tarde, ao configurar o suplemento do Data Lake.</span><span class="sxs-lookup"><span data-stu-id="588b4-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="588b4-192">Criar e registrar um aplicativo do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="588b4-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="588b4-193">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e selecione **Registros de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="588b4-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="588b4-194">Selecione **Novo registro de aplicativo** e defina os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="588b4-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="588b4-195">**Nome** – Insira o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="588b4-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="588b4-196">**Tipo de aplicativo** – Selecione **API Web**.</span><span class="sxs-lookup"><span data-stu-id="588b4-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="588b4-197">**Redirecionar a configuração de URI** - Digite o URL da sua instância do Dynamics 365, tal como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="588b4-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="588b4-198">Vá para o aplicativo recém-criado e copie e salve o valor da **ID (do cliente) do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="588b4-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="588b4-199">Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="588b4-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="588b4-200">Vá para **Permissões de API** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="588b4-201">Selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="588b4-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="588b4-202">Selecione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="588b4-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="588b4-203">Depois de selecionar permissões delegadas, selecione **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="588b4-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="588b4-204">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="588b4-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="588b4-205">No menu do aplicativo, selecione **Certificados \& segredos** e siga as etapas para criar segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="588b4-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="588b4-206">Selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="588b4-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="588b4-207">No campo **Descrição da Chave**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="588b4-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="588b4-208">Selecione uma duração e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="588b4-209">Um segredo é gerado no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="588b4-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="588b4-210">Copie e salve o valor do segredo do cliente.</span><span class="sxs-lookup"><span data-stu-id="588b4-210">Copy and save the client secret value.</span></span> <span data-ttu-id="588b4-211">Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="588b4-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="588b4-212">Crie segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="588b4-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="588b4-213">Vá para o cofre de chaves criado anteriormente e selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="588b4-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="588b4-214">Para cada nome de segredo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="588b4-215">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="588b4-216">Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="588b4-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="588b4-217">Crie o nome e o valor do segredo com base na tabela.</span><span class="sxs-lookup"><span data-stu-id="588b4-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="588b4-218">Selecione **Habilitado** e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="588b4-219">O segredo é criado e adicionado ao Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="588b4-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="588b4-220">Nome secreto</span><span class="sxs-lookup"><span data-stu-id="588b4-220">Secret name</span></span>                       | <span data-ttu-id="588b4-221">Valor do segredo</span><span class="sxs-lookup"><span data-stu-id="588b4-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="588b4-222">app-id</span><span class="sxs-lookup"><span data-stu-id="588b4-222">app-id</span></span>                            | <span data-ttu-id="588b4-223">O ID do aplicativo que você criou antes.</span><span class="sxs-lookup"><span data-stu-id="588b4-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="588b4-224">app-secret</span><span class="sxs-lookup"><span data-stu-id="588b4-224">app-secret</span></span>                        | <span data-ttu-id="588b4-225">O segredo do cliente que você salvou antes.</span><span class="sxs-lookup"><span data-stu-id="588b4-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="588b4-226">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="588b4-226">storage-account-name</span></span>              | <span data-ttu-id="588b4-227">O nome da conta de armazenamento que você criou antes, como **storageaccount1**.</span><span class="sxs-lookup"><span data-stu-id="588b4-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="588b4-228">Autorize o acesso do aplicativo ao cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="588b4-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="588b4-229">No [portal do Azure](https://portal.azure.com), abra o cofre de chaves criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="588b4-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="588b4-230">Selecione as políticas de acesso.</span><span class="sxs-lookup"><span data-stu-id="588b4-230">Select the access policies.</span></span>
    3. <span data-ttu-id="588b4-231">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="588b4-232">Selecione **Adicionar Política de Acesso** para criar uma política de acesso.</span><span class="sxs-lookup"><span data-stu-id="588b4-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="588b4-233">No campo **Permissões do segredo**, selecione as permissões na tabela.</span><span class="sxs-lookup"><span data-stu-id="588b4-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="588b4-234">No campo **Selecionar principal**, pesquise o nome de exibição do aplicativo na tabela.</span><span class="sxs-lookup"><span data-stu-id="588b4-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="588b4-235">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-235">Select **Select**.</span></span>
        5. <span data-ttu-id="588b4-236">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-236">Select **Add**.</span></span>
        6. <span data-ttu-id="588b4-237">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-237">Select **Save**.</span></span>

        | <span data-ttu-id="588b4-238">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="588b4-238">Application</span></span>                                              | <span data-ttu-id="588b4-239">Permissões</span><span class="sxs-lookup"><span data-stu-id="588b4-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="588b4-240">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="588b4-240">The display name of the new application that you created</span></span> | <span data-ttu-id="588b4-241">Get, List</span><span class="sxs-lookup"><span data-stu-id="588b4-241">Get, List</span></span>   |
        | <span data-ttu-id="588b4-242">**Microsserviços de ERP do Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="588b4-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="588b4-243">Get, List</span><span class="sxs-lookup"><span data-stu-id="588b4-243">Get, List</span></span>   |

6. <span data-ttu-id="588b4-244">Atribuir funções para acessar a conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="588b4-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="588b4-245">No [portal do Azure](https://portal.azure.com), abra a conta de armazenamento criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="588b4-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="588b4-246">Selecione **Controle de Acesso (IAM)** e, em seguida, selecione **Atribuições de Função**.</span><span class="sxs-lookup"><span data-stu-id="588b4-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="588b4-247">Selecione **Adicionar, Adicionar Atribuição de Função**.</span><span class="sxs-lookup"><span data-stu-id="588b4-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="588b4-248">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="588b4-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="588b4-249">Selecione a função na tabela.</span><span class="sxs-lookup"><span data-stu-id="588b4-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="588b4-250">Deixe o campo **Atribuir acesso a** como **Usuário, grupo ou entidade de serviço do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="588b4-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="588b4-251">No campo **Selecionar**, insira o aplicativo da tabela.</span><span class="sxs-lookup"><span data-stu-id="588b4-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="588b4-252">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-252">Select **Save**.</span></span>

        | <span data-ttu-id="588b4-253">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="588b4-253">Application</span></span>                                              | <span data-ttu-id="588b4-254">Função</span><span class="sxs-lookup"><span data-stu-id="588b4-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="588b4-255">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="588b4-255">The display name of the new application that you created</span></span> | <span data-ttu-id="588b4-256">Proprietário</span><span class="sxs-lookup"><span data-stu-id="588b4-256">Owner</span></span>                       |
        | <span data-ttu-id="588b4-257">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="588b4-257">The display name of the new application that you created</span></span> | <span data-ttu-id="588b4-258">Colaborador</span><span class="sxs-lookup"><span data-stu-id="588b4-258">Contributor</span></span>                 |
        | <span data-ttu-id="588b4-259">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="588b4-259">The display name of the new application that you created</span></span> | <span data-ttu-id="588b4-260">Colaborador da Conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="588b4-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="588b4-261">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="588b4-261">The display name of the new application that you created</span></span> | <span data-ttu-id="588b4-262">Proprietário de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="588b4-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="588b4-263">**Serviço de Autorização do AI Builder**</span><span class="sxs-lookup"><span data-stu-id="588b4-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="588b4-264">Leitor de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="588b4-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="588b4-265">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="588b4-265">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="588b4-266">Configurar o suplemento Exportar para o Data Lake</span><span class="sxs-lookup"><span data-stu-id="588b4-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="588b4-267">Siga estas etapas para usar o LCS para adicionar o suplemento Exportar para o Data Lake no ambiente.</span><span class="sxs-lookup"><span data-stu-id="588b4-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="588b4-268">Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.</span><span class="sxs-lookup"><span data-stu-id="588b4-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="588b4-269">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="588b4-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="588b4-270">Selecione o suplemento **Exportar para o Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="588b4-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="588b4-271">Insira os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="588b4-271">Enter the following values.</span></span>

    | <span data-ttu-id="588b4-272">Alíquota</span><span class="sxs-lookup"><span data-stu-id="588b4-272">Value</span></span>                                                              | <span data-ttu-id="588b4-273">descrição</span><span class="sxs-lookup"><span data-stu-id="588b4-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="588b4-274">ID de Locatário da Assinatura do Azure em que o Key Vault está localizado</span><span class="sxs-lookup"><span data-stu-id="588b4-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="588b4-275">A ID de locatário onde a conta de armazenamento, os aplicativos e os cofres de chaves estão localizados.</span><span class="sxs-lookup"><span data-stu-id="588b4-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="588b4-276">Para obter este valor, abra o [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e copie o valor **ID do locatário**.</span><span class="sxs-lookup"><span data-stu-id="588b4-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="588b4-277">Forneça o nome DNS de seu Key Vault</span><span class="sxs-lookup"><span data-stu-id="588b4-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="588b4-278">O nome DNS do cofre de chaves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="588b4-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="588b4-279">Forneça o segredo que contém o nome da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="588b4-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="588b4-280">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="588b4-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="588b4-281">Nome do Segredo da ID do Aplicativo que será usada para acessar o Data Lake</span><span class="sxs-lookup"><span data-stu-id="588b4-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="588b4-282">**app-id**</span><span class="sxs-lookup"><span data-stu-id="588b4-282">**app-id**</span></span> |
    | <span data-ttu-id="588b4-283">O nome do segredo para o segredo do cliente do aplicativo</span><span class="sxs-lookup"><span data-stu-id="588b4-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="588b4-284">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="588b4-284">**app-secret**</span></span> |

5. <span data-ttu-id="588b4-285">Aceite os termos e selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="588b4-286">O suplemento será instalado em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="588b4-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="588b4-287">Configurar o suplemento do Finance Insights</span><span class="sxs-lookup"><span data-stu-id="588b4-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="588b4-288">Se você instalou o suplemento Obter insights anteriormente, desinstale-o antes de concluir o seguinte procedimento.</span><span class="sxs-lookup"><span data-stu-id="588b4-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="588b4-289">Para instalar o suplemento do Finance Insights, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="588b4-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="588b4-290">Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.</span><span class="sxs-lookup"><span data-stu-id="588b4-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="588b4-291">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="588b4-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="588b4-292">Selecione o suplemento do **Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="588b4-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="588b4-293">Aceite os termos e selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="588b4-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="588b4-294">Comentários e suporte</span><span class="sxs-lookup"><span data-stu-id="588b4-294">Feedback and support</span></span>

<span data-ttu-id="588b4-295">Se você quiser fornecer feedback ou precisar de suporte, envie um email para [Finance Insights (versão preliminar)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="588b4-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
