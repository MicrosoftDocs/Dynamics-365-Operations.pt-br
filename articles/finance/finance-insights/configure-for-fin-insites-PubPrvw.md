---
title: Configuração para o Finance Insights para versão preliminar pública - versão 10.0.20 e posterior
description: Este tópico explica como configurar seu sistema para usar os recursos disponíveis no Finance Insights para a versão preliminar pública 10.0.20 e posterior.
author: ShivamPandey-msft
ms.date: 06/16/2021
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
ms.openlocfilehash: 859385f8feb240d3860ae37d3500029b818a5458
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638695"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a>Configuração para o Finance Insights para versão preliminar pública - versão 10.0.20 e posterior

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Os insights do Finance combinam a funcionalidade do Microsoft Dynamics 365 Finance com o Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização. Este tópico explica como configurar o Dynamics 365 Finance versão 10.0.20 para que o seu sistema possa usar os recursos disponíveis na versão preliminar pública do Finance Insights.

> [!NOTE]
> As etapas de configuração que são descritas neste tópico aplicam-se somente ao Finance versão 10.0.20 e posterior. 'Para configurar o Finance Insights nas versões 10.0.19 e anteriores, consulte [Configuração para o Finance Insights - versões até 10.0.19](configure-for-fin-insites.md).

## <a name="deploy-finance"></a>Implantação no Finance

Para implantar os ambientes, siga estas etapas.

1. No Microsoft Dynamics Lifecycle Services (LCS), crie ou atualize o ambiente do Finance. Um ambiente com a versão 10.0.20 ou posterior de aplicativos do Finance and Operations.
2. O ambiente deve ser de alta disponibilidade na Área restrita. (Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).
3. Se você estiver configurando o Finance Insights em um ambiente de área restrita, talvez você precise copiar os dados de produção nesse ambiente para que as previsões funcionem. O modelo de previsão usa vários anos de dados para criar previsões. Os dados de demonstração da Contoso não contêm dados históricos suficientes para treinar o modelo de previsão corretamente. 

## <a name="configure-dataverse"></a>Configurar o Dataverse

Para configurar o Dataverse para Finance Insights, siga estas etapas:

1. No LCS, abra a página do ambiente e verifique se a seção **Integração do Power Platform** já está configurado.

    - Se ela já estiver configurada, o nome do ambiente do Dataverse que está vinculado ao ambiente deve do Finance deve aparecer na lista.
    - Se ela não estiver configurada, siga estas etapas:

        1. Na seção **Integração do Power Platform**, selecione **Configurar**. A configuração do ambiente pode levar até uma hora.
        2. Se o ambiente do Dataverse for configurado com êxito, o nome do ambiente do Dataverse que está vinculado ao ambiente deve do Finance deve aparecer na lista.

        > [!NOTE]
        > Ao usar o link para abrir o ambiente, **não** selecione **Vincular ao CDS para Aplicativos**. Este botão não é necessário para o Finance Insights. Se você o selecionar, não será possível configurar os suplementos necessários do ambiente no LCS.

## <a name="configure-azure"></a>Configurar o Azure

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a>Use o Azure Cloud Shell para configurar os recursos de Data Lake dos insights do Finance

# <a name="use-a-windows-powershell-script"></a>[Use um script do Windows PowerShell](#tab/use-a-powershell-script)

O script do Windows PowerShell foi fornecido para que você possa configurar facilmente os recursos do Azure que são descritos em [Configurar exportação para Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md). Se você preferir fazer a configuração manualmente, pule este procedimento e, em vez disso, conclua o procedimento da seção [Configuração Manual](#manual-setup).

> [!NOTE]
> Use os seguintes procedimentos para executar o script do Windows PowerShell. A configuração pode não funcionar se você usar a opção **Experimentar** no CLI do Azure ou se você executar o script no seu computador.

Siga as seguintes etapas para usar o script do Windows PowerShell para configurar o Azure. É necessário ter os direitos para criar um grupo de recursos do Azure, recursos do Azure e um aplicativo do Azure AD. Para obter informações sobre as permissões necessárias, consulte [Verificar permissões do Azure AD](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).

1. No [portal do Azure](https://portal.azure.com), vá para a assinatura do Azure de destino.
2. Selecione **Cloud Shell** à direita do campo **Pesquisar**.
3. Selecione **PowerShell**.
4. Crie o armazenamento se isso for solicitado a você.
5. Na guia **CLI do Azure**, selecione **Copiar**.
6. No Bloco de notas, abra um novo arquivo e copie o script do Windows PowerShell.
7. Salve o arquivo localmente como **ConfigureDataLake.ps1**.
8. Faça upload do script do Windows PowerShell à sessão usando a opção de menu para upload no Cloud Shell.
9. Execute o script **.\ConfigureDataLake.ps1**.
10. Siga as instruções para executar o script.
11. Use as informações de saída do script para instalar o suplemento Exportar para Data Lake no LCS.

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

1. No computador local, no menu **Iniciar**, pesquise **powershell**.
2. Selecione e mantenha pressionado (ou clique com o botão direito) **Windows PowerShell** e depois selecione **Executar como administrador**.
3. Execute o seguinte comando para instalar o módulo **AzureAD**.

    `Install-Module -Name AzureAD`

4. Se um provedor de NuGet for necessário para continuar, selecione **Y** para instalá-lo.
5. Se você receber a mensagem "Repositório não confiável", selecione **Y** para continuar.
6. Para cada aplicativo que deve ser adicionado, execute os seguintes comandos para adicionar o aplicativo ao Azure AD. Quando solicitado, entre como administrador do Azure AD.

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a>Criar recursos do Azure

> [!NOTE]
> Certifique-se de criar os seguintes recursos na mesma instância do Azure AD em que o ambiente do Dataverse está. Não é possível usar recursos de outra instância do Azure AD.

1. Criar uma conta de armazenamento:

    1. No [portal do Azure](https://portal.azure.com), crie uma conta de armazenamento.
    2. Na caixa de diálogo **Criar conta de armazenamento**, defina os seguintes campos:

        - **Local** – Selecione o data center em que o ambiente está localizado.
        - **Desempenho** – Recomendamos selecionar **Padrão**.
        - **Tipo de conta** – É necessário selecionar **StorageV2**.

    3. Na caixa de diálogo **Opções avançadas**, na opção **Data Lake Storage Gen2**, selecione **Habilitar** no recurso **Namespaces hierárquicos**. Se você não habilitar este recurso, você não poderá consumir os dados que os aplicativos do Finance and Operations gravarem usando serviços, como os fluxos de dados do Power BI.
    4. Selecione **Revisar e criar**. Quando a implantação for concluída, o novo recurso será mostrado no portal do Azure.
    5. Acesse a conta de armazenamento que você criou.
    6. No menu esquerdo, selecione **Chaves de acesso**.
    7. Copie e salve o nome da conta de armazenamento. Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.

2. Criar um cofre de chaves:

    1. No [portal do Azure](https://portal.azure.com), crie um cofre de chaves.
    2. Na caixa de diálogo **Criar cofre de chaves**, no campo **Local**, selecione o data center no qual o ambiente está localizado.
    3. Quando um cofre de chaves for criado, vá para **Visão geral do cofre de chaves** e copie e salve o nome do DNS. Você precisará fornecer este valor mais tarde, ao configurar o suplemento do Data Lake.

3. Criar e registrar um aplicativo do Azure AD:

    1. No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e selecione **Registros de aplicativo**.
    2. Selecione **Novo registro de aplicativo** e defina os campos a seguir:

        - **Nome** – Insira o nome do aplicativo.
        - **Tipo de aplicativo** – Selecione **API Web**.
        - **Redirecionar a configuração de URI** - Digite o URL da sua instância do Dynamics 365, tal como `https://yourdynamicsinstance.dynamics.com/auth`.

    3. Vá para o aplicativo recém-criado e copie e salve o valor da **ID (do cliente) do aplicativo**. Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.
    4. Vá para **Permissões de API** e siga estas etapas:

        1. Selecione **Adicionar uma permissão**.
        2. Selecione **Azure Key Vault**.
        3. Depois de selecionar permissões delegadas, selecione **user\_impersonation**.
        4. Selecione **Adicionar permissões**.

    5. No menu do aplicativo, selecione **Certificados \& segredos** e siga as etapas para criar segredos do Key Vault:

        1. Selecione **Novo segredo do cliente**.
        2. No campo **Descrição da Chave**, insira um nome.
        3. Selecione uma duração e, em seguida, selecione **Adicionar**. Um segredo é gerado no campo **Valor**.
        4. Copie e salve o valor do segredo do cliente. Você precisará fornecer este valor mais tarde, ao configurar os segredos do cofre de chaves.

4. Crie segredos do Key Vault:

    1. Vá para o cofre de chaves criado anteriormente e selecione **Segredos**.
    2. Para cada nome de segredo na seguinte tabela, siga estas etapas:

        1. Selecione **Gerar/Importar**.
        2. Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.
        3. Crie o nome e o valor do segredo com base na tabela.
        4. Selecione **Habilitado** e depois selecione **Criar**. O segredo é criado e adicionado ao Cofre de Chaves.

        | Nome secreto                       | Valor do segredo                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | app-id                            | O ID do aplicativo que você criou antes.                                      |
        | app-secret                        | O segredo do cliente que você salvou antes.                                                    |
        | storage-account-name              | O nome da conta de armazenamento que você criou antes, como **storageaccount1**.       |

5. Autorize o acesso do aplicativo ao cofre de chaves:

    1. No [portal do Azure](https://portal.azure.com), abra o cofre de chaves criado anteriormente.
    2. Selecione as políticas de acesso.
    3. Para cada aplicativo na seguinte tabela, siga estas etapas:

        1. Selecione **Adicionar Política de Acesso** para criar uma política de acesso.
        2. No campo **Permissões do segredo**, selecione as permissões na tabela.
        3. No campo **Selecionar principal**, pesquise o nome de exibição do aplicativo na tabela.
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

        1. Selecione a função na tabela.
        2. Deixe o campo **Atribuir acesso a** como **Usuário, grupo ou entidade de serviço do Azure AD**.
        3. No campo **Selecionar**, insira o aplicativo da tabela.
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

## <a name="configure-the-export-to-data-lake-add-in"></a>Configurar o suplemento Exportar para o Data Lake

Siga estas etapas para usar o LCS para adicionar o suplemento Exportar para o Data Lake no ambiente.

1. Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.
2. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.
3. Selecione o suplemento **Exportar para o Data Lake**.
4. Insira os seguintes valores.

    | Alíquota                                                              | descrição |
    |--------------------------------------------------------------------|-------------|
    | ID de Locatário da Assinatura do Azure em que o Key Vault está localizado | A ID de locatário onde a conta de armazenamento, os aplicativos e os cofres de chaves estão localizados. Para obter este valor, abra o [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e copie o valor **ID do locatário**. |
    | Forneça o nome DNS de seu Key Vault                             | O nome DNS do cofre de chaves, como `https://customkeyvault.vault.azure.net/`. |
    | Forneça o segredo que contém o nome da conta de armazenamento   | **storage-account-name** |
    | Nome do Segredo da ID do Aplicativo que será usada para acessar o Data Lake          | **app-id** |
    | O nome do segredo para o segredo do cliente do aplicativo                                  | **app-secret** |

5. Aceite os termos e selecione **Instalar**.

O suplemento será instalado em alguns minutos.

## <a name="configure-the-finance-insights-add-in"></a>Configurar o suplemento do Finance Insights

> [!NOTE]
> Se você instalou o suplemento Obter insights anteriormente, desinstale-o antes de concluir o seguinte procedimento.

Para instalar o suplemento do Finance Insights, siga estas etapas.

1. Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.
2. Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.
3. Selecione o suplemento do **Finance Insights**.
4. Aceite os termos e selecione **Instalar**.

O suplemento pode demorar vários minutos para ser instalado.

## <a name="feedback-and-support"></a>Comentários e suporte

Se você quiser fornecer feedback ou precisar de suporte, envie um email para [Finance Insights (versão preliminar)](mailto:fiap@microsoft.com).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
