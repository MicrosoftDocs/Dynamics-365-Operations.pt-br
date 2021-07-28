---
title: Configuração do Finance Insights - Antes da versão 10.0.19
description: Este tópico explica as etapas de configuração que habilitarão seu sistema a usar as funcionalidades que estão disponíveis no Finance Insights para versões anteriores à 10.0.19.
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
ms.openlocfilehash: 6b578962839a34a1e2ce0311f7d8e7ee57a10927
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357429"
---
# <a name="configuration-for-finance-insights-for-private-preview-preview---before-version-10019"></a>Configuração para o Finance Insights para versão prévia privada - Antes da versão 10.0.19

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> Os seguintes procedimentos para configurar o Finance Insights são válidos para as versões do Microsoft Dynamics 365 Finance antes da versão 10.0.19. Para configurar o Finance Insights na versão do 10.0.20 e posterior, consulte [Configuração para o Finance Insights (versão preliminar) - versões 10.0.20 e além](configure-for-fin-insites-PubPrvw.md).

Os insights do Finance combinam a funcionalidade do Microsoft Dynamics 365 Finance com o Microsoft Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização. Este tópico explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis nos insights do Finance.

## <a name="deploy-dynamics-365-finance"></a>Implantar Dynamics 365 Finance

Implante os ambientes seguindo estas etapas.

1. No Microsoft Dynamics Lifecycle Services (LCS), crie ou atualize um ambiente do Dynamics 365 Finance. O ambiente exige uma versão do aplicativo 10.0.11/Platform update 35 ou posterior.
2. O ambiente deve ser de alta disponibilidade na Área restrita. (Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Se você estiver configurando o Finance Insights em um ambiente de área restrita, talvez você precise copiar os dados de produção nesse ambiente para que as previsões funcionem. O modelo de previsão usa vários anos de dados para criar previsões. Os dados de demonstração da Contoso não contêm dados históricos suficientes para treinar o modelo de previsão corretamente. 

## <a name="configure-dataverse"></a>Configurar o Dataverse

Use as etapas a seguir para configurar o Dataverse para Finance insights.

1. Abra a página do ambiente no LCS e verifique se a seção **Power Platform** já está configurada.
    1. Se já estiver configurada, o nome do ambiente do Dataverse vinculado ao Ambiente do Dynamics 365 Finance deverá ser listado. Copie o nome do ambiente do Dataverse.
    2. Se não estiver configurada, siga estas etapas:
        1. Selecione o botão **Configurar** na seção de integração do Power Platform. A configuração do ambiente pode demorar até uma hora.
        2. Se o ambiente do Dataverse for configurado com sucesso, o nome do ambiente do Dataverse vinculado ao Ambiente do Dynamics 365 Finance deve ser listado. Copie o nome do ambiente do Dataverse.
> [!NOTE]
> Após concluir a configuração do ambiente, **NÃO** selecione o botão **Link para o CDS para aplicativos**. Isso não é necessário para Finance Insights e desabilitará a capacidade de concluir os Suplementos de Ambiente necessários no LCS.

2. Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/) e siga estas etapas para criar um ambiente do Dataverse no mesmo locatário do Active Directory:

    1. Abra a página **Ambientes**.

        [![Página de ambientes.](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)

    2. Selecione o ambiente do Dataverse criado acime e, em seguida, selecione **Configurações**.
    3. Selecione **Recursos \> Todas as Configurações Herdadas**.
    4. Na barra de navegação superior, selecione **Configurações** e depois **Personalizações**.
    5. Selecione **Recursos do Desenvolvedor**.
    6. Copie o valor da **ID da organização do Dataverse**.
    7. Na barra de endereços do navegador, anote a URL da organização do Dataverse. Por exemplo, a URL pode ser `https://org42b2b3d3.crm.dynamics.com`.

3. Se você planeja usar o recurso Previsões de fluxo de caixa ou Previsões de orçamento, siga estas etapas para atualizar o limite de anotação da sua organização para pelo menos 50 megabytes (MB):

    1. Abra o [portal do Power Apps](https://make.powerapps.com).
    2. Selecione o ambiente recém-criado e depois selecione **Configurações avançadas**.
    3. Selecione **Configurações \> Configuração de Email**.
    4. Altere o valor do campo **Tamanho máximo do arquivo** para **51.200**. (O valor é expresso em quilobytes \[KB\].)
    5. Selecione **OK** para salvar as alterações.

## <a name="configure-the-azure-setup"></a>Configurar a definição do Azure

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a>Insira a ID do diretório do Dataverse e a ID do objeto do Azure AD do usuário

1. Insira a ID do diretório do Dataverse:

    1. Abra o [portal do Azure](https://portal.azure.com).
    2. Entre com a ID de usuário usada para criar o ambiente do Dataverse.
    3. Acesse **Azure Active Directory**.
    4. Copie o valor da **ID de locatário**.

2. Insira a ID de objeto do Azure Active Directory (Azure AD) do usuário:

    1. No [portal do Azure](https://portal.azure.com), acesse **Usuários** e pesquise o usuário pelo endereço de email.
    2. Selecione o nome do usuário.
    3. Copie o valor da **ID do objeto**.

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Use o Azure Cloud Shell para configurar os recursos de Data Lake dos insights do Finance

# <a name="use-a-windows-powershell-script"></a>[Use um script do Windows PowerShell](#tab/use-a-powershell-script)

Um script do Windows PowerShell foi fornecido para que você possa facilmente configurar os recursos do Azure descritos em [Configurar exportação para o Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Se preferir fazer a configuração manual, ignore este procedimento e continue com o procedimento na seção [Configuração manual](#manual-setup).

> [!NOTE]
> Siga as etapas abaixo para executar o script do PowerShell. A opção "Experimente" da CLI do Azure ou a execução do script no PC pode não funcionar.

Siga estas etapas para configurar o Azure usando o script do Windows PowerShell. É necessário ter os direitos para criar um grupo de recursos do Azure, recursos do Azure e um aplicativo do Azure AD. Para obter informações sobre as permissões necessárias, consulte [Verificar permissões do Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. No [portal do Azure](https://portal.azure.com), vá para a assinatura do Azure de destino. Selecione o botão **Cloud Shell** à direita do campo **Pesquisar**.
2. Selecione **PowerShell**.
3. Crie o armazenamento, caso seja solicitado.
4. Vá para a guia **CLI do Azure** e selecione **Copiar**.  
5. Abra o Bloco de notas e cole o script do PowerShell. Salve o arquivo como ConfigureDataLake.ps1.
6. Carregue o script do Windows PowerShell na sessão usando a opção de menu para carregar no Cloud Shell.
7. Execute o script .\ConfigureDataLake.ps1.
8. Siga as instruções para executar o script.
9. Use as informações de saída do script para instalar o suplemento **Exportar para Data Lake** no LCS.
10. Use as informações de saída do script para habilitar o armazenamento da entidade na página **Conexões de dados** no Finance (**Administração do sistema \> Parâmetros do sistema \> Conexões de dados**).

### <a name="manual-setup"></a>Configuração manual

#### <a name="add-applications-to-the-azure-ad-tenant"></a>Adicionar aplicativos ao locatário do Azure AD

1. No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory**.
2. Selecione **Gerenciar \> Aplicativos empresariais**.
3. Procure os seguintes aplicativos por ID do aplicativo.

    | Solicitação de Emprego                              | ID do Aplicativo                               |
    |------------------------------------------|--------------------------------------|
    | Microsserviços de ERP do Microsoft Dynamics     | 0cdb527f-a8d1-4bf8-9436-b352c68682b2 |
    | CDS de Microsserviços de ERP do Microsoft Dynamics | 703e2651-d3fc-48f5-942c-74274233dba8 |
    | Serviço de Autorização do AI Builder         | ad40333e-9910-4b61-b281-e3aeeb8c3ef3 |

Caso não encontre nenhum dos aplicativos anteriores, tente executar as seguintes etapas.

1. No computador local, selecione o menu **Iniciar** e pesquise **powershell**.
2. Selecione e mantenha pressionado (ou clique com o botão direito) **Windows PowerShell** e depois selecione **Executar como administrador**.
3. Execute o seguinte comando para instalar o módulo **AzureAD**.

    `Install-Module -Name AzureAD`

4. Se um provedor de NuGet for necessário para continuar, selecione **Y** para instalá-lo.
5. Se uma mensagem "Repositório não confiável" for exibida, selecione **Y** para continuar.
6. Para cada aplicativo que deve ser adicionado, execute os seguintes comandos para adicionar o aplicativo ao Azure AD. Quando solicitado, entre como administrador do Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Criar recursos do Azure

> [!NOTE]
> Certifique-se de criar os seguintes recursos na mesma instância do Azure AD como ambiente do Dataverse. Não é possível usar recursos de outra instância do Azure AD.

1. Crie uma conta de armazenamento:

    1. No [portal do Azure](https://portal.azure.com), crie uma conta de armazenamento.
    2. Na caixa de diálogo **Criar conta de armazenamento**, defina os seguintes campos:

        - **Local** – Selecione o data center em que o ambiente está localizado.
        - **Desempenho** – Recomendamos selecionar **Padrão**.
        - **Tipo de conta** – É necessário selecionar **StorageV2**.

    3. Na caixa de diálogo **Opções avançadas**, na opção **Data Lake Storage Gen2**, selecione **Habilitar** no recurso **Namespaces hierárquicos**. Se você desabilitar esse recurso, não poderá consumir dados que os aplicativos do Finance and Operations gravam usando serviços como fluxos de dados do Power BI.
    4. Selecione **Revisar e criar**. Quando a implantação for concluída, o novo recurso será mostrado no portal do Azure.
    5. Acesse a conta de armazenamento que você criou.
    6. No menu esquerdo, selecione **Chaves de acesso**.
    7. Copie e salve a cadeia de conexão para **Chave1** ou **Chave2**.
    8. Copie e salve o nome da conta de armazenamento.

2. Crie um cofre de chaves:

    1. No [portal do Azure](https://portal.azure.com), crie um cofre de chaves.
    2. Na caixa de diálogo **Criar cofre de chaves**, no campo **Local**, selecione o data center no qual o ambiente está localizado.
    3. Após criar o cofre de chaves, selecione-o na lista e depois selecione **Segredos**.
    4. Selecione **Gerar/Importar**.
    5. Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
    6. Digite um nome para o segredo. Anote o nome, pois ele será solicitado depois.
    7. No campo **Valor**, insira a cadeia de conexão obtida da conta de armazenamento no procedimento anterior.
    8. Selecione **Habilitado** e depois selecione **Criar**. O segredo é criado e adicionado ao Cofre de Chaves.
    9. Vá para a **Visão Geral do Cofre de Chaves** e anote o nome DNS.

3. Criar e registrar um aplicativo do Azure AD:

    1. No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e selecione **Registros de aplicativo**.
    2. Selecione **Novo registro de aplicativo** e defina os campos a seguir:

        - **Nome** – Insira o nome do aplicativo.
        - **Tipo de aplicativo** – Selecione **API Web**.
        - **Redirecionar configuração de URI** – Insira a URL da instância do Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Vá para o aplicativo recém-criado e copie e salve o valor da **ID (do cliente) do aplicativo**. Você terá que fornecer esse valor mais tarde, ao configurar o cofre de chaves.
    4. Vá para **Permissões de API** e siga estas etapas:

        1. Selecione **Adicionar uma permissão**.
        2. Selecione **Azure Key Vault**.
        3. Depois de selecionar permissões delegadas, selecione **user\_impersonation**.
        4. Selecione **Adicionar permissões**.

    5. No menu do aplicativo, selecione **Certificados \& segredos** e siga as etapas para criar segredos do Key Vault:

        1. Selecione **Novo segredo do cliente**.
        2. No campo **Descrição da Chave**, insira um nome.
        3. Selecione uma duração e, em seguida, selecione **Adicionar**. Um segredo é gerado no campo **Valor**.
        4. Copie e salve o valor do segredo.

4. Crie segredos do Key Vault:

    1. Vá para o cofre de chaves criado anteriormente e selecione **Segredos**.
    2. Para cada nome de segredo na seguinte tabela, siga estas etapas:

        1. Selecione **Gerar/Importar**.
        2. Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
        3. Crie o nome e o valor do segredo da seguinte tabela.
        4. Selecione **Habilitado** e depois selecione **Criar**. O segredo é criado e adicionado ao Cofre de Chaves.

        | Nome secreto                       | Valor do segredo                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | app-id                            | A ID do aplicativo criado anteriormente                                      |
        | app-secret                        | O segredo do cliente salvo anteriormente                                                    |
        | storage-account-name              | O nome da conta de armazenamento criada anteriormente, como **storageaccount1**       |
        | storage-account-connection-string | A cadeia de conexão copiada da página **Chaves de acesso** para a conta de armazenamento |

5. Autorize o acesso do aplicativo ao cofre de chaves:

    1. No [portal do Azure](https://portal.azure.com), abra o cofre de chaves criado anteriormente.
    2. Selecione as políticas de acesso.
    3. Para cada aplicativo na seguinte tabela, siga estas etapas:

        1. Selecione **Adicionar Política de Acesso** para criar uma política de acesso.
        2. No campo **Permissões do segredo**, selecione as permissões da seguinte tabela.
        3. No campo **Selecionar entidade de segurança**, pesquise o nome de exibição do aplicativo na seguinte tabela.
        4. Escolha **Selecionar**.
        5. Selecione **Adicionar**.
        6. Selecione **Salvar**.

        | Solicitação de Emprego                                              | Permissões |
        |----------------------------------------------------------|-------------|
        | O nome de exibição do aplicativo que você criou | Get, List   |
        | **Microsserviços de ERP do Microsoft Dynamics**                 | Get, List   |

6. Atribuir funções para acessar a conta de armazenamento:

    1. No [portal do Azure](https://portal.azure.com), abra a conta de armazenamento criada anteriormente.
    2. Selecione **Controle de Acesso (IAM)** e, em seguida, selecione **Atribuições de Função**.
    3. Selecione **Adicionar, Adicionar Atribuição de Função**.
    4. Para cada aplicativo na seguinte tabela, siga estas etapas:

        1. Selecione a função da seguinte tabela.
        2. Deixe o campo **Atribuir acesso a** como **Usuário, grupo ou entidade de serviço do Azure AD**.
        3. No campo **Selecionar**, insira o aplicativo da seguinte tabela.
        4. Selecione **Salvar**.

        | Solicitação de Emprego                                              | Função                        |
        |----------------------------------------------------------|-----------------------------|
        | O nome de exibição do aplicativo que você criou | Proprietário                       |
        | O nome de exibição do aplicativo que você criou | Colaborador                 |
        | O nome de exibição do aplicativo que você criou | Colaborador da Conta de Armazenamento |
        | O nome de exibição do aplicativo que você criou | Proprietário de Dados Blob de Armazenamento     |
        | **Serviço de Autorização do AI Builder**                     | Leitor de Dados Blob de Armazenamento    |

# <a name="azure-cli"></a>[Azure CLI](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a>Configurar o data lake

Siga estas etapas para usar o LCS para adicionar o suplemento do Azure Data Lake ao ambiente.

1. Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.
2. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.
3. Selecione o suplemento **Exportar para o Data Lake**.
4. Insira os seguintes valores.

    | Alíquota                                                              | descrição |
    |--------------------------------------------------------------------|-------------|
    | ID de Locatário da Assinatura do Azure em que o Key Vault está localizado | A ID de locatário onde a conta de armazenamento, os aplicativos e os cofres de chaves estão localizados. Para encontrar esse valor, abra o [portal do Azure](https://portal.azure.com), vá para o **Azure Active Directory** e copie o valor da **ID de Locatário**. |
    | Forneça o nome DNS de seu Key Vault                             | O nome DNS do cofre de chaves, como `https://customkeyvault.vault.azure.net/`. (Esse valor corresponde ao nome DNS usado no repositório de entidades.) |
    | Forneça o segredo que contém o nome da conta de armazenamento   | **storage-account-name** |
    | Nome do Segredo da ID do Aplicativo que será usada para acessar o Data Lake          | **app-id** |
    | Nome do segredo que será usado com a ID do Aplicativo                                 | **app-secret** |

5. Concorde com os termos e selecione **Instalar**.

O suplemento será instalado em alguns minutos.

## <a name="configure-ai-builder"></a>Configurar o AI Builder

1. Entre no LCS e abra a página **Detalhes do ambiente**.
2. Role até a seção **Suplementos de ambiente**. Você verá os suplementos que já estão instalados nesse ambiente. Se o suplemento **Exportar para Data Lake** não estiver entre eles, configure-o.
3. Selecione o suplemento **Obter insights**.
4. Na página de detalhes do suplemento **Obter insights**, insira os seguintes valores.

    | Alíquota                                                    | descrição |
    |----------------------------------------------------------|-------------|
    | URL da Organização CDS                                     | O URL da organização do Dataverse copiado de cima. |
    | ID da Organização CDS                                               | A ID da organização do Dataverse copiada de cima. |
5. Ative **Este é o ambiente padrão do seu Locatário?**.

O suplemento pode demorar vários minutos para ser instalado.
    
## <a name="configure-the-entity-store"></a>Configure o armazenamento da entidade

Siga estas etapas para configurar o repositório de entidades no ambiente do Finance.

1. Vá para **Administração do sistema \> Configuração \> Parâmetros do sistema \> Conexões de dados**.
2. Defina os seguintes campos do Key Vault:

    - **ID (do cliente) do aplicativo** – Insira o ID do cliente do aplicativo criado anteriormente.
    - **Segredo do Aplicativo** – Insira o segredo salvo para o aplicativo criado anteriormente.
    - **Nome DNS** – Você pode encontrar o nome do Sistema de Nome de Domínio (DNS) na página de detalhes do aplicativo criado anteriormente.
    - **Nome do segredo** – Insira **storage-account-connection-string**.
3. Ativa **Habilitar a integração do Data Lake**.
4. Selecione **Testar Azure Key Vault** e verifique se não há erros.
5. Selecione **Testar Armazenamento do Azure** e verifique se não há erros.

## <a name="feedback-and-support"></a>Comentários e suporte

Envie um email para [insights de pagamento do cliente (versão prévia)](mailto:fiap@microsoft.com) se tiver interesse em fornecer comentários ou precisar de suporte.

## <a name="privacy-notice"></a>Aviso de privacidade

As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
