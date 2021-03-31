---
title: Configuração de Insights do Finance (versão preliminar)
description: Este tópico explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis nos insights do Finance.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: cf29e3c05f9fdcc685017a4c640ef32c40989c73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208548"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="59320-103">Configuração de Insights do Finance (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="59320-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="59320-104">Os insights do Finance combinam a funcionalidade do Microsoft Dynamics 365 Finance com o Microsoft Dataverse, o Azure e o AI Builder para fornecer ferramentas de previsão importantes para sua organização.</span><span class="sxs-lookup"><span data-stu-id="59320-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="59320-105">Este tópico explica as etapas de configuração que permitirão que o sistema use os recursos disponíveis nos insights do Finance.</span><span class="sxs-lookup"><span data-stu-id="59320-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="59320-106">Implantar Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="59320-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="59320-107">Implante os ambientes seguindo estas etapas.</span><span class="sxs-lookup"><span data-stu-id="59320-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="59320-108">No Microsoft Dynamics Lifecycle Services (LCS), crie ou atualize um ambiente do Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="59320-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="59320-109">O ambiente exige uma versão do aplicativo 10.0.11/Platform update 35 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="59320-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="59320-110">O ambiente deve ser de alta disponibilidade na Área restrita.</span><span class="sxs-lookup"><span data-stu-id="59320-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="59320-111">(Esse tipo de ambiente também é conhecido como um ambiente de Camada 2). Para obter mais informações, consulte [Planejamento de ambiente](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="59320-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="59320-112">Se você estiver usando os dados de demonstração da Contoso, dados de amostra adicionais serão necessários para usar os recursos de previsões de pagamento do cliente, previsões de fluxo de caixa, e previsão de orçamento.</span><span class="sxs-lookup"><span data-stu-id="59320-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="59320-113">Configurar o Dataverse</span><span class="sxs-lookup"><span data-stu-id="59320-113">Configure Dataverse</span></span>

<span data-ttu-id="59320-114">Você pode concluir as seguintes etapas de configuração manual ou acelerar o processo de configuração usando o script do Windows PowerShell fornecido.</span><span class="sxs-lookup"><span data-stu-id="59320-114">You can complete the manual configuration steps that follow, or you can speed up the configuration process by using the Windows PowerShell script that is provided.</span></span> <span data-ttu-id="59320-115">Quando o script do PowerShell concluir a execução, ele fornecerá os valores que serão usados para configurar os insights do Finance.</span><span class="sxs-lookup"><span data-stu-id="59320-115">When the PowerShell script has finished running, it will give you values to use to configure Finance insights.</span></span> 

> [!NOTE]
> <span data-ttu-id="59320-116">Abra o PowerShell no PC para executar o script.</span><span class="sxs-lookup"><span data-stu-id="59320-116">Open PowerShell on your PC to run the script.</span></span> <span data-ttu-id="59320-117">Talvez você precise do PowerShell versão 5.</span><span class="sxs-lookup"><span data-stu-id="59320-117">You may need PowerShell version 5.</span></span> <span data-ttu-id="59320-118">A opção "Experimente" da CLI do Microsoft Azure pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="59320-118">The Microsoft Azure CLI "Try it" option may not work.</span></span>

# <a name="manual-configuration-steps"></a>[<span data-ttu-id="59320-119">Etapas da configuração manual</span><span class="sxs-lookup"><span data-stu-id="59320-119">Manual configuration steps</span></span>](#tab/configuration-steps)

1. <span data-ttu-id="59320-120">Abra o [centro de administração do Power Platform](https://admin.powerplatform.microsoft.com/) e siga estas etapas para criar um ambiente do Dataverse no mesmo locatário do Active Directory:</span><span class="sxs-lookup"><span data-stu-id="59320-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="59320-121">Abra a página **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="59320-121">Open the **Environments** page.</span></span>

        <span data-ttu-id="59320-122">[![Página de ambientes](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="59320-122">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="59320-123">Selecione **Novo ambiente**.</span><span class="sxs-lookup"><span data-stu-id="59320-123">Select **New environment**.</span></span>
    3. <span data-ttu-id="59320-124">No campo **Tipo**, selecione **Área restrita**.</span><span class="sxs-lookup"><span data-stu-id="59320-124">In the **Type** field, select **Sandbox**.</span></span>
    4. <span data-ttu-id="59320-125">Defina a opção **Criar Banco de Dados** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="59320-125">Set the **Create Database** option to **Yes**.</span></span>
    5. <span data-ttu-id="59320-126">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="59320-126">Select **Next**.</span></span>
    6. <span data-ttu-id="59320-127">Selecione o idioma e a moeda da organização.</span><span class="sxs-lookup"><span data-stu-id="59320-127">Select the language and currency for your organization.</span></span>
    7. <span data-ttu-id="59320-128">Aceite os valores padrão para os demais campos.</span><span class="sxs-lookup"><span data-stu-id="59320-128">Accept the default values for the other fields.</span></span>
    8. <span data-ttu-id="59320-129">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="59320-129">Select **Save**.</span></span>
    9. <span data-ttu-id="59320-130">Atualize a página **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="59320-130">Refresh the **Environments** page.</span></span>
    10. <span data-ttu-id="59320-131">Aguarde até que o valor do campo **Estado** seja atualizado para **Pronto**.</span><span class="sxs-lookup"><span data-stu-id="59320-131">Wait until the value of the **State** field is updated to **Ready**.</span></span>
    11. <span data-ttu-id="59320-132">Anote a ID da organização do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-132">Make a note of the Dataverse organization ID.</span></span>
    12. <span data-ttu-id="59320-133">Selecione o ambiente e depois **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="59320-133">Select the environment, and then select **Settings**.</span></span>
    13. <span data-ttu-id="59320-134">Selecione **Recursos \> Todas as Configurações Herdadas**.</span><span class="sxs-lookup"><span data-stu-id="59320-134">Select **Resources \> All Legacy Settings**.</span></span>
    14. <span data-ttu-id="59320-135">Na barra de navegação superior, selecione **Configurações** e depois **Personalizações**.</span><span class="sxs-lookup"><span data-stu-id="59320-135">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    15. <span data-ttu-id="59320-136">Selecione **Recursos do Desenvolvedor**.</span><span class="sxs-lookup"><span data-stu-id="59320-136">Select **Developer Resources**.</span></span>
    16. <span data-ttu-id="59320-137">Defina o campo **ID de Informações de Referência da Instância** como o valor da ID da organização do Dataverse anotado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-137">Set the **Instance Reference Information ID** field to the Dataverse organization ID value that you made a note of earlier.</span></span>
    17. <span data-ttu-id="59320-138">Na barra de endereços do navegador, anote a URL da organização do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-138">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="59320-139">Por exemplo, a URL pode ser `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="59320-139">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

2. <span data-ttu-id="59320-140">Se você planeja usar o recurso Previsões de fluxo de caixa ou Previsões de orçamento, siga estas etapas para atualizar o limite de anotação da sua organização para pelo menos 50 megabytes (MB):</span><span class="sxs-lookup"><span data-stu-id="59320-140">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="59320-141">Abra o [portal do Power Apps](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="59320-141">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="59320-142">Selecione o ambiente recém-criado e depois selecione **Configurações avançadas**.</span><span class="sxs-lookup"><span data-stu-id="59320-142">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="59320-143">Selecione **Configurações \> Configuração de Email**.</span><span class="sxs-lookup"><span data-stu-id="59320-143">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="59320-144">Altere o valor do campo **Tamanho máximo do arquivo** para **51.200**.</span><span class="sxs-lookup"><span data-stu-id="59320-144">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="59320-145">(O valor é expresso em quilobytes \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="59320-145">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="59320-146">Selecione **OK** para salvar as alterações.</span><span class="sxs-lookup"><span data-stu-id="59320-146">Select **OK** to save your changes.</span></span>

# <a name="windows-powershell-configuration-script"></a>[<span data-ttu-id="59320-147">Script de configuração do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59320-147">Windows PowerShell configuration script</span></span>](#tab/powershell-configuration-script)

```azurecli-interactive
Write-Output 'The following modules need to be present for execution of this script:'
Write-Output '  Microsoft.PowerApps.Administration.PowerShell'
Write-Output '  Microsoft.PowerApps.PowerShell'
Write-Output '  Microsoft.Xrm.Tooling.CrmConnector.PowerShell'

try {
    $moduleConsent = Read-Host 'Is it ok to install or update these modules as needed? (yes/no)'
    if ($moduleConsent -ne 'yes' -and $moduleConsent -ne 'y') {
        Write-Warning 'User declined to install required modules.'
        return
    }

    $module = 'Microsoft.PowerApps.Administration.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '2.0.61' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '2.0.61' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.PowerApps.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '1.0.9' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '1.0.9' -AllowClobber -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    $module = 'Microsoft.Xrm.Tooling.CrmConnector.PowerShell'
    if (-not (Get-InstalledModule -Name $module -MinimumVersion '3.3.0.892' -ErrorAction SilentlyContinue)) {
        Install-Module -Name $module -MinimumVersion '3.3.0.892' -Force
        Write-Output ('Installed {0} module.' -f $module)
    }
    else {
        Write-Output ('{0} module found.' -f $module)
    }

    Write-Output '================================================================================='

    $useMfa = $false
    $useMfaPrompt = Read-Host "Does your organization require the use of multi-factor authentication? (yes/no)"
    if ($useMfaPrompt -eq 'yes' -or $useMfaPrompt -eq 'y') {
        $useMfa = $true
    }
    if(-not $useMfa) {
        $credential = Get-Credential -Message 'Power Apps Credential'
    }

    $orgFriendlyName = Read-Host "Enter the name of the CDS Organization to use or create: (blank for 'FinanceInsightsOrg')"
    if ($orgFriendlyName.Trim() -eq '') {
        $orgFriendlyName = 'FinanceInsightsOrg'
    }

    $isDefaultOrgPrompt = Read-Host ("Is '" + $orgFriendlyName + "' the default organization for your tenant? (yes/no)")
    if ($isDefaultOrgPrompt -eq 'yes' -or $isDefaultOrgPrompt -eq 'y') {
        $isDefaultOrg = $true
    }

    if ($credential) {
        Add-PowerAppsAccount -Username $credential.UserName -Password $credential.Password
    }
    else {
        Add-PowerAppsAccount
    }

    if ($isDefaultOrg) {
        $orgMatch = ('(default)')
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { $_.IsDefault -eq $true })
    }
    else {
        $orgMatch = ('{0} (*)' -f $orgFriendlyName)
        $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.IsDefault -eq $false -and ($_.DisplayName -eq $orgFriendlyName -or $_.DisplayName -like $orgMatch)) })
    }

    $getCrmOrgParams = @{ 'OnlineType' = 'Office365' }
    if ($credential) {
        $getCrmOrgParams.Credential = $credential
    }

    if ($null -eq $environment) {
        Write-Output '================================================================================='
        Write-Output 'PowerApps environment not found. A new one will be provisioned.'

        $invalid = 'invalid'

        $location = $invalid
        $cdsLocations = (Get-AdminPowerAppEnvironmentLocations | Select-Object LocationName).LocationName
        while (-not ($location -in $cdsLocations)) {
            $location = (Read-Host -Prompt "Enter the location in which to create the new PowerApps environment: ('help' to see values)")
            if ($location -eq 'help') {
                $cdsLocations
            }
        }

        $currency = $invalid
        $cdsCurrencies = (Get-AdminPowerAppCdsDatabaseCurrencies -Location $location | Select-Object CurrencyName).CurrencyName
        while ($currency -ne '' -and -not ($currency -in $cdsCurrencies)) {
            $currency = (Read-Host -Prompt "Enter the currency to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($currency -eq 'help') {
                $cdsCurrencies
            }
        }

        $language = $invalid
        $cdsLanguages = (Get-AdminPowerAppCdsDatabaseLanguages -Location $location | Select-Object LanguageName, LanguageDisplayName)
        while ($language -ne '' -and -not ($language -in $cdsLanguages.LanguageName)) {
            $language = (Read-Host -Prompt "Enter the language name to use for the new PowerApps environment: ('help' to see values, blank for default)")
            if ($language -eq 'help') {
                $cdsLanguages | Format-Table -Property LanguageName, LanguageDisplayName
            }
        }

        Write-Output 'Provisioning PowerApps environment. This may take several minutes.'

        $sleep = 15

        $envParams = @{ 'DisplayName' = $orgFriendlyName; 'EnvironmentSku' = 'Sandbox'; 'ProvisionDatabase' = $true; 'Location' = $location; 'WaitUntilFinished' = $true }
        if ($language.Trim() -ne '') {
            $envParams.LanguageName = $language
        }
        if ($currency.Trim() -ne '') {
            $envParams.CurrencyName = $currency
        }
        $newEnvResult = New-AdminPowerAppEnvironment @envParams
        if (($null -eq $newEnvResult) -or ($newEnvResult.CommonDataServiceDatabaseProvisioningState -ne 'Succeeded')) {
            Write-Warning 'Failed to create to PowerApps environment'
            if ($null -ne $newEnvResult) {
                $newEnvResult
            }
        }
        else {
            $environment = $null
            $retryCount = 0
            while (($null -eq $environment) -and ($retryCount -lt 5)) {
                Start-Sleep -Seconds $sleep
                $environment = (Get-AdminPowerAppEnvironment | Where-Object { ($_.DisplayName -like $orgMatch) })
            }
            Write-Output ("Provisioned PowerApps environment with name: '" + $environment.DisplayName + "'")
        }

        Write-Output 'Waiting for CDS organization provisioning. This may take several minutes.'
        if (-not $credential) {
            $sleep = 120
            Write-Output 'You may be prompted for credentials multiple times while checking the status of the provisioning.'
        }

        while ($null -eq $crmOrg) {
            Start-Sleep -Seconds $sleep
            $crmOrg = (Get-CrmOrganizations @getCrmOrgParams) | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }
    else {
        $crmOrgs = Get-CrmOrganizations @getCrmOrgParams
        if ($UseDefaultOrganization -eq $true) {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -match $orgMatch }
        }
        else {
            $crmOrg = $crmOrgs | Where-Object { $_.FriendlyName -eq $orgFriendlyName }
        }
    }

    Write-Output '================================================================================='
    Write-Output 'Values for PowerAI LCS Add-In:'
    Write-Output ("  CDS organization url:             " + $crmOrg.WebApplicationUrl)
    Write-Output ("  CDS organization ID:              " + $crmOrg.OrganizationId)
}
catch {
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $_.Exception.InnerException
    while ($null -ne $inner) {
        Write-Output 'Inner Exception:'
        Write-Error $_.Exception.Message
        Write-Warning $_.Exception.StackTrace
        $inner = $inner.InnerException
    }
}
```
---

## <a name="configure-the-azure-setup"></a><span data-ttu-id="59320-148">Configurar a definição do Azure</span><span class="sxs-lookup"><span data-stu-id="59320-148">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="59320-149">Insira a ID do diretório do Dataverse e a ID do objeto do Azure AD do usuário</span><span class="sxs-lookup"><span data-stu-id="59320-149">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="59320-150">Insira a ID do diretório do Dataverse:</span><span class="sxs-lookup"><span data-stu-id="59320-150">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="59320-151">Abra o [portal do Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="59320-151">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="59320-152">Entre com a ID de usuário usada para criar o ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-152">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="59320-153">Acesse **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="59320-153">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="59320-154">Copie o valor da **ID de locatário**.</span><span class="sxs-lookup"><span data-stu-id="59320-154">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="59320-155">Insira a ID de objeto do Azure Active Directory (Azure AD) do usuário:</span><span class="sxs-lookup"><span data-stu-id="59320-155">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="59320-156">No [portal do Azure](https://portal.azure.com), acesse **Usuários** e pesquise o usuário pelo endereço de email.</span><span class="sxs-lookup"><span data-stu-id="59320-156">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="59320-157">Selecione o nome do usuário.</span><span class="sxs-lookup"><span data-stu-id="59320-157">Select the user's name.</span></span>
    3. <span data-ttu-id="59320-158">Copie o valor da **ID do objeto**.</span><span class="sxs-lookup"><span data-stu-id="59320-158">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="59320-159">Use o Azure Cloud Shell para configurar os recursos de Data Lake dos insights do Finance</span><span class="sxs-lookup"><span data-stu-id="59320-159">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="59320-160">Use um script do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="59320-160">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="59320-161">Um script do Windows PowerShell foi fornecido para que você possa facilmente configurar os recursos do Azure descritos em [Configurar exportação para o Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span><span class="sxs-lookup"><span data-stu-id="59320-161">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/configure-export-data-lake).</span></span> <span data-ttu-id="59320-162">Se preferir fazer a configuração manual, ignore este procedimento e continue com o procedimento na seção [Configuração manual](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="59320-162">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="59320-163">Siga as etapas abaixo para executar o script do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59320-163">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="59320-164">A opção "Experimente" da CLI do Azure ou a execução do script no PC pode não funcionar.</span><span class="sxs-lookup"><span data-stu-id="59320-164">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="59320-165">Siga estas etapas para configurar o Azure usando o script do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59320-165">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="59320-166">É necessário ter os direitos para criar um grupo de recursos do Azure, recursos do Azure e um aplicativo do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59320-166">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="59320-167">Para obter informações sobre as permissões necessárias, consulte [Verificar permissões do Azure AD](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="59320-167">For information about the required permissions, see [Check Azure AD permissions](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="59320-168">No [portal do Azure](https://portal.azure.com), vá para a assinatura do Azure de destino.</span><span class="sxs-lookup"><span data-stu-id="59320-168">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="59320-169">Selecione o botão **Cloud Shell** à direita do campo **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="59320-169">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="59320-170">Selecione **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="59320-170">Select **PowerShell**.</span></span>
3. <span data-ttu-id="59320-171">Crie o armazenamento, caso seja solicitado.</span><span class="sxs-lookup"><span data-stu-id="59320-171">Create storage, if you're prompted to do so.</span></span> <span data-ttu-id="59320-172">Em seguida, carregue o script do Windows PowerShell na sessão.</span><span class="sxs-lookup"><span data-stu-id="59320-172">Then upload the Windows PowerShell script to the session.</span></span>
4. <span data-ttu-id="59320-173">Executar o script.</span><span class="sxs-lookup"><span data-stu-id="59320-173">Run the script.</span></span>
5. <span data-ttu-id="59320-174">Siga as instruções para executar o script.</span><span class="sxs-lookup"><span data-stu-id="59320-174">Follow the prompts to run the script.</span></span>
6. <span data-ttu-id="59320-175">Use as informações de saída do script para instalar o suplemento **Exportar para Data Lake** no LCS.</span><span class="sxs-lookup"><span data-stu-id="59320-175">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
7. <span data-ttu-id="59320-176">Use as informações de saída do script para habilitar o armazenamento da entidade na página **Conexões de dados** no Finance (**Administração do sistema \> Parâmetros do sistema \> Conexões de dados**).</span><span class="sxs-lookup"><span data-stu-id="59320-176">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="59320-177">Configuração manual</span><span class="sxs-lookup"><span data-stu-id="59320-177">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="59320-178">Adicionar aplicativos ao locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="59320-178">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="59320-179">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="59320-179">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="59320-180">Selecione **Gerenciar \> Aplicativos empresariais**.</span><span class="sxs-lookup"><span data-stu-id="59320-180">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="59320-181">Procure os seguintes aplicativos por ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59320-181">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="59320-182">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="59320-182">Application</span></span>                              | <span data-ttu-id="59320-183">ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="59320-183">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="59320-184">Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="59320-184">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="59320-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="59320-185">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="59320-186">CDS de Microsserviços de ERP do Microsoft Dynamics</span><span class="sxs-lookup"><span data-stu-id="59320-186">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="59320-187">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="59320-187">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="59320-188">Serviço de Autorização do AI Builder</span><span class="sxs-lookup"><span data-stu-id="59320-188">AI Builder Authorization Service</span></span>         | <span data-ttu-id="59320-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="59320-189">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="59320-190">Caso não encontre nenhum dos aplicativos anteriores, tente executar as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="59320-190">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="59320-191">No computador local, selecione o menu **Iniciar** e pesquise **powershell**.</span><span class="sxs-lookup"><span data-stu-id="59320-191">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="59320-192">Selecione e mantenha pressionado (ou clique com o botão direito) **Windows PowerShell** e depois selecione **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="59320-192">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="59320-193">Execute o seguinte comando para instalar o módulo **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="59320-193">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="59320-194">Se um provedor de NuGet for necessário para continuar, selecione **Y** para instalá-lo.</span><span class="sxs-lookup"><span data-stu-id="59320-194">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="59320-195">Se uma mensagem "Repositório não confiável" for exibida, selecione **Y** para continuar.</span><span class="sxs-lookup"><span data-stu-id="59320-195">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="59320-196">Para cada aplicativo que deve ser adicionado, execute os seguintes comandos para adicionar o aplicativo ao Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59320-196">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="59320-197">Quando solicitado, entre como administrador do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59320-197">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="59320-198">Criar recursos do Azure</span><span class="sxs-lookup"><span data-stu-id="59320-198">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="59320-199">Certifique-se de criar os seguintes recursos na mesma instância do Azure AD como ambiente do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-199">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="59320-200">Não é possível usar recursos de outra instância do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="59320-200">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="59320-201">Crie uma conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="59320-201">Create a new storage account:</span></span>

    1. <span data-ttu-id="59320-202">No [portal do Azure](https://portal.azure.com), crie uma conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="59320-202">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="59320-203">Na caixa de diálogo **Criar conta de armazenamento**, defina os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="59320-203">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="59320-204">**Local** – Selecione o data center em que o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="59320-204">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="59320-205">**Desempenho** – Recomendamos selecionar **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="59320-205">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="59320-206">**Tipo de conta** – É necessário selecionar **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="59320-206">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="59320-207">Na caixa de diálogo **Opções avançadas**, na opção **Data Lake Storage Gen2**, selecione **Habilitar** no recurso **Namespaces hierárquicos**.</span><span class="sxs-lookup"><span data-stu-id="59320-207">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="59320-208">Se você desabilitar esse recurso, não poderá consumir dados que os aplicativos do Finance and Operations gravam usando serviços como fluxos de dados do Power BI.</span><span class="sxs-lookup"><span data-stu-id="59320-208">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="59320-209">Selecione **Revisar e criar**.</span><span class="sxs-lookup"><span data-stu-id="59320-209">Select **Review and create**.</span></span> <span data-ttu-id="59320-210">Quando a implantação for concluída, o novo recurso será mostrado no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="59320-210">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="59320-211">Acesse a conta de armazenamento que você criou.</span><span class="sxs-lookup"><span data-stu-id="59320-211">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="59320-212">No menu esquerdo, selecione **Chaves de acesso**.</span><span class="sxs-lookup"><span data-stu-id="59320-212">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="59320-213">Copie e salve a cadeia de conexão para **Chave1** ou **Chave2**.</span><span class="sxs-lookup"><span data-stu-id="59320-213">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="59320-214">Copie e salve o nome da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="59320-214">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="59320-215">Crie um cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="59320-215">Create a new key vault:</span></span>

    1. <span data-ttu-id="59320-216">No [portal do Azure](https://portal.azure.com), crie um cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="59320-216">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="59320-217">Na caixa de diálogo **Criar cofre de chaves**, no campo **Local**, selecione o data center no qual o ambiente está localizado.</span><span class="sxs-lookup"><span data-stu-id="59320-217">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="59320-218">Após criar o cofre de chaves, selecione-o na lista e depois selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="59320-218">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="59320-219">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="59320-219">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="59320-220">Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="59320-220">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="59320-221">Digite um nome para o segredo.</span><span class="sxs-lookup"><span data-stu-id="59320-221">Enter a name for the secret.</span></span> <span data-ttu-id="59320-222">Anote o nome, pois ele será solicitado depois.</span><span class="sxs-lookup"><span data-stu-id="59320-222">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="59320-223">No campo **Valor**, insira a cadeia de conexão obtida da conta de armazenamento no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="59320-223">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="59320-224">Selecione **Habilitado** e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="59320-224">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="59320-225">O segredo é criado e adicionado ao Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="59320-225">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="59320-226">Vá para a **Visão Geral do Cofre de Chaves** e anote o nome DNS.</span><span class="sxs-lookup"><span data-stu-id="59320-226">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="59320-227">Criar e registrar um aplicativo do Azure AD:</span><span class="sxs-lookup"><span data-stu-id="59320-227">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="59320-228">No [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory** e selecione **Registros de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="59320-228">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="59320-229">Selecione **Novo registro de aplicativo** e defina os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="59320-229">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="59320-230">**Nome** – Insira o nome do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="59320-230">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="59320-231">**Tipo de aplicativo** – Selecione **API Web**.</span><span class="sxs-lookup"><span data-stu-id="59320-231">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="59320-232">**Redirecionar configuração de URI** – Insira a URL da instância do Dynamics 365, como `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="59320-232">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="59320-233">Vá para o aplicativo recém-criado e copie e salve o valor da **ID (do cliente) do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="59320-233">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="59320-234">Você terá que fornecer esse valor mais tarde, ao configurar o cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="59320-234">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="59320-235">Vá para **Permissões de API** e siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="59320-235">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="59320-236">Selecione **Adicionar uma permissão**.</span><span class="sxs-lookup"><span data-stu-id="59320-236">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="59320-237">Selecione **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="59320-237">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="59320-238">Depois de selecionar permissões delegadas, selecione **user\_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="59320-238">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="59320-239">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="59320-239">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="59320-240">No menu do aplicativo, selecione **Certificados \& segredos** e siga as etapas para criar segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="59320-240">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="59320-241">Selecione **Novo segredo do cliente**.</span><span class="sxs-lookup"><span data-stu-id="59320-241">Select **New client secret**.</span></span>
        2. <span data-ttu-id="59320-242">No campo **Descrição da Chave**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="59320-242">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="59320-243">Selecione uma duração e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59320-243">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="59320-244">Um segredo é gerado no campo **Valor**.</span><span class="sxs-lookup"><span data-stu-id="59320-244">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="59320-245">Copie e salve o valor do segredo.</span><span class="sxs-lookup"><span data-stu-id="59320-245">Copy and save the secret value.</span></span>

4. <span data-ttu-id="59320-246">Crie segredos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="59320-246">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="59320-247">Vá para o cofre de chaves criado anteriormente e selecione **Segredos**.</span><span class="sxs-lookup"><span data-stu-id="59320-247">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="59320-248">Para cada nome de segredo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="59320-248">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="59320-249">Selecione **Gerar/Importar**.</span><span class="sxs-lookup"><span data-stu-id="59320-249">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="59320-250">Na caixa de diálogo **Criar um segredo**, no campo **Opções de carregamento**, selecione **Manual**.</span><span class="sxs-lookup"><span data-stu-id="59320-250">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="59320-251">Crie o nome e o valor do segredo da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="59320-251">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="59320-252">Selecione **Habilitado** e depois selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="59320-252">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="59320-253">O segredo é criado e adicionado ao Cofre de Chaves.</span><span class="sxs-lookup"><span data-stu-id="59320-253">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="59320-254">Nome secreto</span><span class="sxs-lookup"><span data-stu-id="59320-254">Secret name</span></span>                       | <span data-ttu-id="59320-255">Valor do segredo</span><span class="sxs-lookup"><span data-stu-id="59320-255">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="59320-256">app-id</span><span class="sxs-lookup"><span data-stu-id="59320-256">app-id</span></span>                            | <span data-ttu-id="59320-257">A ID do aplicativo criado anteriormente</span><span class="sxs-lookup"><span data-stu-id="59320-257">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="59320-258">app-secret</span><span class="sxs-lookup"><span data-stu-id="59320-258">app-secret</span></span>                        | <span data-ttu-id="59320-259">O segredo do cliente salvo anteriormente</span><span class="sxs-lookup"><span data-stu-id="59320-259">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="59320-260">storage-account-name</span><span class="sxs-lookup"><span data-stu-id="59320-260">storage-account-name</span></span>              | <span data-ttu-id="59320-261">O nome da conta de armazenamento criada anteriormente, como **storageaccount1**</span><span class="sxs-lookup"><span data-stu-id="59320-261">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="59320-262">storage-account-connection-string</span><span class="sxs-lookup"><span data-stu-id="59320-262">storage-account-connection-string</span></span> | <span data-ttu-id="59320-263">A cadeia de conexão copiada da página **Chaves de acesso** para a conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="59320-263">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="59320-264">Autorize o acesso do aplicativo ao cofre de chaves:</span><span class="sxs-lookup"><span data-stu-id="59320-264">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="59320-265">No [portal do Azure](https://portal.azure.com), abra o cofre de chaves criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-265">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="59320-266">Selecione as políticas de acesso.</span><span class="sxs-lookup"><span data-stu-id="59320-266">Select the access policies.</span></span>
    3. <span data-ttu-id="59320-267">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="59320-267">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="59320-268">Selecione **Adicionar Política de Acesso** para criar uma política de acesso.</span><span class="sxs-lookup"><span data-stu-id="59320-268">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="59320-269">No campo **Permissões do segredo**, selecione as permissões da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="59320-269">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="59320-270">No campo **Selecionar entidade de segurança**, pesquise o nome de exibição do aplicativo na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="59320-270">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="59320-271">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="59320-271">Select **Select**.</span></span>
        5. <span data-ttu-id="59320-272">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="59320-272">Select **Add**.</span></span>
        6. <span data-ttu-id="59320-273">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="59320-273">Select **Save**.</span></span>

        | <span data-ttu-id="59320-274">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="59320-274">Application</span></span>                                              | <span data-ttu-id="59320-275">Permissões</span><span class="sxs-lookup"><span data-stu-id="59320-275">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="59320-276">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="59320-276">The display name of the new application that you created</span></span> | <span data-ttu-id="59320-277">Get, List</span><span class="sxs-lookup"><span data-stu-id="59320-277">Get, List</span></span>   |
        | <span data-ttu-id="59320-278">**Microsserviços de ERP do Microsoft Dynamics**</span><span class="sxs-lookup"><span data-stu-id="59320-278">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="59320-279">Get, List</span><span class="sxs-lookup"><span data-stu-id="59320-279">Get, List</span></span>   |

6. <span data-ttu-id="59320-280">Atribuir funções para acessar a conta de armazenamento:</span><span class="sxs-lookup"><span data-stu-id="59320-280">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="59320-281">No [portal do Azure](https://portal.azure.com), abra a conta de armazenamento criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-281">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="59320-282">Selecione **Controle de Acesso (IAM)** e, em seguida, selecione **Atribuições de Função**.</span><span class="sxs-lookup"><span data-stu-id="59320-282">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="59320-283">Selecione **Adicionar, Adicionar Atribuição de Função**.</span><span class="sxs-lookup"><span data-stu-id="59320-283">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="59320-284">Para cada aplicativo na seguinte tabela, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="59320-284">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="59320-285">Selecione a função da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="59320-285">Select the role from the following table.</span></span>
        2. <span data-ttu-id="59320-286">Deixe o campo **Atribuir acesso a** como **Usuário, grupo ou entidade de serviço do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="59320-286">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="59320-287">No campo **Selecionar**, insira o aplicativo da seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="59320-287">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="59320-288">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="59320-288">Select **Save**.</span></span>

        | <span data-ttu-id="59320-289">Solicitação de Emprego</span><span class="sxs-lookup"><span data-stu-id="59320-289">Application</span></span>                                              | <span data-ttu-id="59320-290">Função</span><span class="sxs-lookup"><span data-stu-id="59320-290">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="59320-291">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="59320-291">The display name of the new application that you created</span></span> | <span data-ttu-id="59320-292">Proprietário</span><span class="sxs-lookup"><span data-stu-id="59320-292">Owner</span></span>                       |
        | <span data-ttu-id="59320-293">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="59320-293">The display name of the new application that you created</span></span> | <span data-ttu-id="59320-294">Colaborador</span><span class="sxs-lookup"><span data-stu-id="59320-294">Contributor</span></span>                 |
        | <span data-ttu-id="59320-295">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="59320-295">The display name of the new application that you created</span></span> | <span data-ttu-id="59320-296">Colaborador da Conta de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="59320-296">Storage Account Contributor</span></span> |
        | <span data-ttu-id="59320-297">O nome de exibição do aplicativo que você criou</span><span class="sxs-lookup"><span data-stu-id="59320-297">The display name of the new application that you created</span></span> | <span data-ttu-id="59320-298">Proprietário de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="59320-298">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="59320-299">**Serviço de Autorização do AI Builder**</span><span class="sxs-lookup"><span data-stu-id="59320-299">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="59320-300">Leitor de Dados Blob de Armazenamento</span><span class="sxs-lookup"><span data-stu-id="59320-300">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="59320-301">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="59320-301">Azure CLI</span></span>](#tab/azure-azure-cli)

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

## <a name="configure-the-entity-store"></a><span data-ttu-id="59320-302">Configure o armazenamento da entidade</span><span class="sxs-lookup"><span data-stu-id="59320-302">Configure the entity store</span></span>

<span data-ttu-id="59320-303">Siga estas etapas para configurar o repositório de entidades no ambiente do Finance.</span><span class="sxs-lookup"><span data-stu-id="59320-303">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="59320-304">Vá para **Administração do sistema \> Configuração \> Parâmetros do sistema \> Conexões de dados**.</span><span class="sxs-lookup"><span data-stu-id="59320-304">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="59320-305">Defina a opção **Habilitar a integração do Data Lake** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="59320-305">Set the **Enable Data Lake integration** option to **Yes**.</span></span>
3. <span data-ttu-id="59320-306">Defina os seguintes campos do Key Vault:</span><span class="sxs-lookup"><span data-stu-id="59320-306">Set the following Key Vault fields:</span></span>

    - <span data-ttu-id="59320-307">**ID (do cliente) do aplicativo** – Insira o ID do cliente do aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-307">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="59320-308">**Segredo do Aplicativo** – Insira o segredo salvo para o aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-308">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="59320-309">**Nome DNS** – Você pode encontrar o nome do Sistema de Nome de Domínio (DNS) na página de detalhes do aplicativo criado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="59320-309">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="59320-310">**Nome do segredo** – Insira **storage-account-connection-string**.</span><span class="sxs-lookup"><span data-stu-id="59320-310">**Secret name** – Enter **storage-account-connection-string**.</span></span>

## <a name="configure-the-data-lake"></a><span data-ttu-id="59320-311">Configurar o data lake</span><span class="sxs-lookup"><span data-stu-id="59320-311">Configure the data lake</span></span>

<span data-ttu-id="59320-312">Siga estas etapas para usar o LCS para adicionar o suplemento do Azure Data Lake ao ambiente.</span><span class="sxs-lookup"><span data-stu-id="59320-312">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="59320-313">Entre no LCS e, no nome do ambiente do lado direito da página, selecione **Detalhes Completos**.</span><span class="sxs-lookup"><span data-stu-id="59320-313">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="59320-314">Na seção **Suplementos de ambiente**, selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="59320-314">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="59320-315">Selecione o suplemento **Exportar para o Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="59320-315">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="59320-316">Insira os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="59320-316">Enter the following values.</span></span>

    | <span data-ttu-id="59320-317">Alíquota</span><span class="sxs-lookup"><span data-stu-id="59320-317">Value</span></span>                                                              | <span data-ttu-id="59320-318">descrição</span><span class="sxs-lookup"><span data-stu-id="59320-318">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="59320-319">ID de Locatário da Assinatura do Azure em que o Key Vault está localizado</span><span class="sxs-lookup"><span data-stu-id="59320-319">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="59320-320">A ID de locatário onde a conta de armazenamento, os aplicativos e os cofres de chaves estão localizados.</span><span class="sxs-lookup"><span data-stu-id="59320-320">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="59320-321">Para encontrar esse valor, abra o [portal do Azure](https://portal.azure.com), vá para o **Azure Active Directory** e copie o valor da **ID de Locatário**.</span><span class="sxs-lookup"><span data-stu-id="59320-321">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="59320-322">Forneça o nome DNS de seu Key Vault</span><span class="sxs-lookup"><span data-stu-id="59320-322">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="59320-323">O nome DNS do cofre de chaves, como `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="59320-323">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="59320-324">(Esse valor corresponde ao nome DNS usado no repositório de entidades.)</span><span class="sxs-lookup"><span data-stu-id="59320-324">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="59320-325">Forneça o segredo que contém o nome da conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="59320-325">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="59320-326">**storage-account-name**</span><span class="sxs-lookup"><span data-stu-id="59320-326">**storage-account-name**</span></span> |
    | <span data-ttu-id="59320-327">Nome do Segredo da ID do Aplicativo que será usada para acessar o Data Lake</span><span class="sxs-lookup"><span data-stu-id="59320-327">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="59320-328">**app-id**</span><span class="sxs-lookup"><span data-stu-id="59320-328">**app-id**</span></span> |
    | <span data-ttu-id="59320-329">Nome do segredo que será usado com a ID do Aplicativo</span><span class="sxs-lookup"><span data-stu-id="59320-329">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="59320-330">**app-secret**</span><span class="sxs-lookup"><span data-stu-id="59320-330">**app-secret**</span></span> |

5. <span data-ttu-id="59320-331">Concorde com os termos e selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="59320-331">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="59320-332">O suplemento será instalado em alguns minutos.</span><span class="sxs-lookup"><span data-stu-id="59320-332">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="59320-333">Configurar o AI Builder</span><span class="sxs-lookup"><span data-stu-id="59320-333">Configure AI Builder</span></span>

1. <span data-ttu-id="59320-334">Entre no LCS e abra a página **Detalhes do ambiente**.</span><span class="sxs-lookup"><span data-stu-id="59320-334">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="59320-335">Role até a seção **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="59320-335">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="59320-336">Você verá os suplementos que já estão instalados nesse ambiente.</span><span class="sxs-lookup"><span data-stu-id="59320-336">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="59320-337">Se o suplemento **Exportar para Data Lake** não estiver entre eles, configure-o.</span><span class="sxs-lookup"><span data-stu-id="59320-337">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="59320-338">Selecione o suplemento **Obter insights**.</span><span class="sxs-lookup"><span data-stu-id="59320-338">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="59320-339">Na página de detalhes do suplemento **Obter insights**, insira os seguintes valores.</span><span class="sxs-lookup"><span data-stu-id="59320-339">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="59320-340">Alíquota</span><span class="sxs-lookup"><span data-stu-id="59320-340">Value</span></span>                                                    | <span data-ttu-id="59320-341">descrição</span><span class="sxs-lookup"><span data-stu-id="59320-341">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="59320-342">URL da Organização CDS</span><span class="sxs-lookup"><span data-stu-id="59320-342">CDS Organization URL</span></span>                                     | <span data-ttu-id="59320-343">Uma URL da organização do Dataverse da instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-343">The Dataverse organization URL of the Dataverse instance.</span></span> <span data-ttu-id="59320-344">Para localizar esse valor, abra o [portal do Power Apps](https://make.powerapps.com), selecione o botão **Configurações** (símbolo de engrenagem) no canto superior direito, selecione **Configurações avançadas** e copie a URL.</span><span class="sxs-lookup"><span data-stu-id="59320-344">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Advanced settings**, and copy the URL.</span></span> <span data-ttu-id="59320-345">(A URL termina com "dynamics.com".)</span><span class="sxs-lookup"><span data-stu-id="59320-345">(The URL ends with "dynamics.com.")</span></span> |
    | <span data-ttu-id="59320-346">ID da Organização CDS</span><span class="sxs-lookup"><span data-stu-id="59320-346">CDS Org ID</span></span>                                               | <span data-ttu-id="59320-347">A ID do ambiente da instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-347">The environment ID of the Dataverse instance.</span></span> <span data-ttu-id="59320-348">Para localizar esse valor, abra o [portal do Power Apps](https://make.powerapps.com), selecione o botão **Configurações** (símbolo de engrenagem) no canto superior direito, selecione **Personalizações \> Recursos do desenvolvedor \> Informações de Referência da Instância** e copie o valor da **ID**.</span><span class="sxs-lookup"><span data-stu-id="59320-348">To find this value, open the [Power Apps portal](https://make.powerapps.com), select the **Settings** button (gear symbol) in the upper-right upper corner, select **Customizations \> Developer resources \> Instance Reference Information**, and copy the **ID** value.</span></span> |
    | <span data-ttu-id="59320-349">ID de Locatário CDS (ID do Diretório do AAD)</span><span class="sxs-lookup"><span data-stu-id="59320-349">CDS Tenant ID (Directory ID from AAD)</span></span>               | <span data-ttu-id="59320-350">A ID do locatário da instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-350">The tenant ID of the Dataverse instance.</span></span> <span data-ttu-id="59320-351">Para encontrar esse valor, abra o [portal do Azure](https://portal.azure.com), vá para o **Azure Active Directory** e copie o valor da **ID de Locatário**.</span><span class="sxs-lookup"><span data-stu-id="59320-351">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="59320-352">Forneça a ID do objeto do usuário que tem a função de administrador do sistema</span><span class="sxs-lookup"><span data-stu-id="59320-352">Provide user object ID who has system administrator role</span></span> | <span data-ttu-id="59320-353">A ID do objeto do usuário do Azure AD do usuário no Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-353">The Azure AD user object ID of the user in Dataverse.</span></span> <span data-ttu-id="59320-354">Esse usuário deve ser um administrador do sistema da instância do Dataverse.</span><span class="sxs-lookup"><span data-stu-id="59320-354">This user must be a system administrator of the Dataverse instance.</span></span> <span data-ttu-id="59320-355">Para localizar esse valor, abra o [portal do Azure](https://portal.azure.com), vá para **Azure Active Directory \> Usuários**, selecione o usuário e, na seção **Identificar**, copie o valor de **ID de Objeto**.</span><span class="sxs-lookup"><span data-stu-id="59320-355">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory \> Users**, select the user, and then, in the **Identity** section, copy the **Object ID** value.</span></span> |
    | <span data-ttu-id="59320-356">Este é o ambiente CDS padrão do locatário?</span><span class="sxs-lookup"><span data-stu-id="59320-356">Is this the default CDS environment for the tenant?</span></span>      | <span data-ttu-id="59320-357">Se a instância do Dataverse foi a primeira instância de produção criada, marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="59320-357">If the Dataverse instance was the first production instance that was created, select this check box.</span></span> <span data-ttu-id="59320-358">Se a instância do Dataverse foi criada manualmente, desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="59320-358">If the Dataverse instance was manually created, clear this check box.</span></span> |

## <a name="feedback-and-support"></a><span data-ttu-id="59320-359">Comentários e suporte</span><span class="sxs-lookup"><span data-stu-id="59320-359">Feedback and support</span></span>

<span data-ttu-id="59320-360">Envie um email para [insights de pagamento do cliente (versão prévia)](mailto:fiap@microsoft.com) se tiver interesse em fornecer comentários ou precisar de suporte.</span><span class="sxs-lookup"><span data-stu-id="59320-360">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="59320-361">Aviso de privacidade</span><span class="sxs-lookup"><span data-stu-id="59320-361">Privacy notice</span></span>

<span data-ttu-id="59320-362">As versões prévias (1) podem utilizar menos medidas de privacidade e segurança que o serviço do Dynamics 365 Finance and Operations, (2) não estão incluídas no contrato de nível de serviço (SLA) desse serviço, (3) não devem ser usadas para processar dados pessoais ou outros dados sujeitos a requisitos de conformidade legais ou regulatórios e (4) têm suporte limitado.</span><span class="sxs-lookup"><span data-stu-id="59320-362">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]