---
title: Implantar unidades de escala de borda em hardware personalizado usando LBD
description: Este tópico explica como provisionar unidades de escala de borda local usando o hardware e a implantação personalizados que se baseiam em dados comerciais locais (LBD).
author: Mirzaab
ms.date: 01/24/2022
ms.topic: article
ms.prod: dynamics-365
ms.service: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 540ac1f6d69d869256f49b8501e18966575903fa
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674076"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd"></a>Implantar unidades de escala de borda em hardware personalizado usando LBD

[!include [banner](../includes/banner.md)]

As unidades de escala de borda desempenham uma função importante na topologia híbrida distribuída para o gerenciamento da cadeia de fornecedores. Na topologia híbrida, você pode distribuir cargas de trabalho entre o seu hub de nuvem do Supply Chain Management e unidades de escala adicionais na nuvem ou na borda.

As unidades de escala de borda podem ser implantadas criando-se um [ambiente local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) de dados comerciais locais (LBD) e, em seguida, configurando-o para funcionar como uma unidade de escala na sua topologia híbrida distribuída para o gerenciamento da cadeia de fornecedores. Isso é obtido associando o ambiente LBD local a um ambiente do Supply Chain Management nuvem, que foi configurado para funcionar como um hub.  

Este tópico descreve como configurar um ambiente LBD local como uma unidade de escala de borda e depois associá-lo a um hub.

## <a name="infrastructure-considerations"></a>Considerações sobre infraestrutura

As unidades de escala de borda são executadas em ambientes locais; portanto, os requisitos de infraestrutura são muito semelhantes. No entanto, há certas diferenças que devem ser observadas:

- As unidades de escala de borda não usam o Financial Reporting; então, elas não exigem nós do Financial Reporting.
- As cargas de trabalho de fabricação e de depósito não fazem uso intensivo de computação; portanto, considere o dimensionamento da potência computacional para nós do AOS.

## <a name="deployment-overview"></a>Visão geral da implantação

Aqui está uma visão geral das etapas de implantação.

1. **Habilite um slot LBD no seu projeto LBD no Microsoft Dynamics Lifecycle Services (LCS).**

1. **Configure e implante um ambiente LBD com um banco de dados *vazio*.**

    Use o LCS para implantar o ambiente LBD com a topologia mais recente e um banco de dados vazio. Para obter mais informações, consulte a seção [Configurar e implantar um ambiente LBD com um banco de dados vazio](#set-up-deploy) posteriormente neste tópico. Você deve usar a versão 10.0.21 ou posterior do Supply Chain Management em ambientes de hub e da unidade de escala.

1. **Carregue pacotes de destino em ativos de projeto LBD no LCS.**

    Prepare aplicativos, plataformas e pacotes de personalização usados no hub e na unidade de escala de borda. Para obter mais informações, consulte a seção [Carregar pacotes de destino em ativos de projeto LBD no LCS](#upload-packages) posteriormente neste tópico.

1. **Faça a manutenção do ambiente LBD com os pacotes de destino.**

    Essa etapa garante que os mesmos builds e personalizações sejam implantados no hub e no spoke. Para obter mais informações, consulte a seção [Fazer a manutenção do ambiente LBD com os pacotes de destino](#service-target-packages) posteriormente neste tópico.

1. **Conclua a configuração da unidade de escala e a atribuição de carga de trabalho.**

    Para obter mais informações, consulte a seção [Atribuir sua unidade de escala de borda LBD a um hub](#assign-edge-to-hub) posteriormente neste tópico.

As seções restantes deste tópico fornecem mais detalhes sobre como concluir essas etapas.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configurar e implantar um ambiente LBD com um banco de dados vazio

Esta etapa cria um ambiente LBD funcional. No entanto, o ambiente não tem necessariamente as mesmas versões de aplicativo e plataforma que o ambiente de hub. Além disso, ainda está faltando as personalizações, e ele ainda não foi habilitado para trabalhar como uma unidade de escala.

1. Siga as instruções em [Configurar e implantar ambientes locais (Platform update 41 e posterior)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Você deve usar a versão 10.0.21 ou posterior do Supply Chain Management em ambientes de hub e da unidade de escala. Além disso, você deve usar a versão 2.12.0 ou posterior dos scripts de infraestrutura. 

    > [!IMPORTANT]
    > Leia o restante desta seção **antes** de concluir as etapas deste tópico.

1. Antes de descrever a configuração no arquivo infrastructure\\ConfigTemplate.xml, execute o seguinte script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Esse script removerá qualquer configuração que não seja necessária para implantar unidades de escala de borda.

1. Configure um banco de dados que contenha dados vazios, conforme descrito em [Configurar bancos de dados](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Use o arquivo data.bak vazio para essa etapa.
1. Depois de concluir a etapa [Configurar bancos de dados](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), execute o seguinte script para configurar o banco de dados do Orquestrador de ALM da Unidade de Escala.

    > [!NOTE]
    > Não configure o banco de dados do Financial Reporting durante a etapa [Configurar bancos de dados](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb).

    ```powershell
    .\Initialize-Database.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -ComponentName EdgeScaleUnit
    ```

    O script Initialize-Database. ps1 executa as seguintes ações:

    1. Criar um banco de dados vazio chamado **ScaleUnitAlmDb**.
    2. Mapear os usuários para as funções de banco de dados, com base na tabela a seguir.

        | Usuário            | Tipo | Função do banco de dados |
        |-----------------|------|---------------|
        | svc-LocalAgent$ | gMSA | db\_owner     |

1. Siga as instruções em [Configurar e implantar ambientes locais (Atualização da plataforma 41 e posterior)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md).
1. Depois de concluir a etapa [Configurar AD FS](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb), siga estas etapas:

    1. Crie um novo aplicativo Serviços de Federação do Active Directory (AD FS) que permitirá que o serviço de orquestração do Alm se comunique com seu Servidor de Objetos de Aplicativo (AOS).

        ```powershell
        # Host URL is your DNS record\host name for accessing the AOS
        .\Create-ADFSServerApplicationForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml -HostUrl 'https://ax.d365ffo.onprem.contoso.com'
        ```

    1. Crie um novo aplicativo Azure Active Directory (Azure AD) que permitirá que o serviço de orquestração do Alm se comunique com o serviço de Gerenciamento da Unidade de Escala.

        ```powershell
        # Example .\Create-SumAADApplication.ps1 -ConfigurationFilePath ..\ConfigTemplate.xml -TenantId '6240a19e-86f1-41af-91ab-dbe29dbcfb95' -ApplicationDisplayName 'EdgeAgent-SUMCommunication-EN01'
        .\Create-SumAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                       -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                       -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
        ```

1. Siga as instruções em [Configurar e implantar ambientes locais (Atualização da plataforma 41 e posterior)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Quando for necessário inserir a configuração para o agente local, certifique-se de habilitar os Recursos da Unidade da Escala de Borda e fornecer todos os parâmetros necessários.

    ![Habilitar Recursos da Unidade de Escala de Borda.](media/EnableEdgeScaleUnitFeatures.png "Habilitando Recursos da Unidade de Escala de Borda.")

1. Antes de implantar seu ambiente do LCS, configure o script de pré-implantação. Para obter mais informações, consulte [Scripts de pré-implantação e pós-implantação de agente local](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copie o script Configure-CloudAndEdge.ps1 da pasta **ScaleUnit** nos **Scripts de Infraestrutura** para a pasta **Scripts** no compartilhamento de armazenamento de arquivo do agente que foi configurado no ambiente. Um caminho típico é \\\\lbdiscsi01\\agente\\Scripts.
    2. Crie o script **PreDeployment.ps1** que chamará os scripts usando os parâmetros necessários. O script de pré-implantação deve ser colocado na pasta **Scripts** no compartilhamento de armazenamento de arquivo do agente. Caso contrário, ele não poderá ser executado. Um caminho típico é \\\\lbdiscsi01\\agente\\Scripts\\PreDeployment.ps1.

        O conteúdo do script PreDeployment.ps1 será semelhante ao exemplo a seguir.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        . $PSScriptRoot\Configure-CloudAndEdge.ps1 -AgentShare $agentShare -InstanceId '@A'
        ```

        > [!NOTE]
        > O parâmetro InstanceId deve ter apenas dois caracteres. O primeiro caractere é @ e o segundo pode ser qualquer letra maiúscula no alfabeto inglês.
        >
        > - Valores válidos:
        >   - @D
        >   - @X
        > - Valores não válidos:
        >   - @a
        >   - @4
        >   - @#

1. Implante o ambiente usando a topologia de base mais recente que estiver disponível.
1. Depois que seu ambiente for implantado, siga estas etapas:

    1. Execute os seguintes comandos SQL no banco de dados comercial (AXDB).

        ```sql
        ALTER TABLE dbo.NUMBERSEQUENCETABLE ENABLE CHANGE_TRACKING WITH (TRACK_COLUMNS_UPDATED = ON)
        delete from NumberSequenceTable
        delete from NumberSequenceReference
        delete from NumberSequenceScope
        delete from FeatureManagementMetadata
        delete from FeatureManagementState
        delete from SysFeatureStateV0
        ```

    1. Aumente a sessão de lote máxima simultânea para um valor maior do que 4.

        ```sql
        Update batchserverconfig set maxbatchsessions = '<Replace with number of concurrent batch tasks you want>'
        ```

    1. Verifique se o controle de alterações foi habilitado no banco de dados comercial (AXDB).

        1. Abra o SQL Server Management Studio (SSMS).
        1. Selecione e segure (ou clique com o botão direito do mouse) em seu banco de dados comercial (AXDB) e selecione **Propriedades**.
        1. Na janela que aparecer, selecione **Controle de Alterações** e defina os seguintes valores:

            - **Controle de Alterações:** *Verdadeiro*
            - **Período de Retenção:** *7*
            - **Unidades de Retenção:** *Dias*
            - **Limpeza Automática:** *Verdadeiro*

    1. Adicione a ID do aplicativo do AD FS criada anteriormente (usando o script Create-ADFSServerApplicationForEdgeScaleUnits.ps1) à tabela de aplicativos Azure AD na unidade de escala. Você pode concluir manualmente essa etapa por meio da interface do usuário (IU). Como alternativa, você pode completá-la por meio do banco de dados usando o seguinte script.

        ```sql
        DECLARE @ALMOrchestratorId NVARCHAR(76) = '<Replace with the ADFS Application ID created in a previous step>';

        IF NOT EXISTS (SELECT TOP 1 1 FROM SysAADClientTable WHERE AADClientId = @ALMOrchestratorId)
        BEGIN
            INSERT INTO SysAADClientTable (AADClientId, UserId, Name, ModifiedBy, CreatedBy)
            VALUES (@ALMOrchestratorId, 'ScaleUnitManagement', 'Scale Unit Management', 'Admin', 'Admin');
        END
        ```

## <a name="set-up-an-azure-key-vault-and-an-azure-ad-application-to-enable-communication-between-scale-units"></a><a name="set-up-keyvault"></a>Configurar um Azure Key Vault e um aplicativo Azure AD para habilitar a comunicação entre as unidades de escala

1. Depois que seu ambiente for implantado, crie um aplicativo Azure AD adicional para habilitar a comunicação confiável entre a unidade de escala e o hub.

    ```powershell
    .\Create-SpokeToHubAADApplication.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                          -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                          -ApplicationDisplayName '<Whichever name you want the Azure AD app to have>'
    ```

1. Depois de criar o aplicativo, você deve criar um segredo de cliente e salvar as informações em um Azure Key Vault. Além disso, você deve conceder acesso ao aplicativo Azure AD que foi criado, de forma que possa recuperar os segredos armazenados no cofre de chaves. Para sua conveniência, o script a seguir executará automaticamente todas as ações necessárias.

    ```powershell
    .\Create-SpokeToHubAADAppSecrets.ps1 -ConfigurationFilePath '<Path of the ConfigTemplate.xml file>' `
                                         -TenantId '<ID of the tenant where your cloud hub is deployed>' `
                                         -SubscriptionName '<Any subscription within your tenant>' `
                                         -ResourceGroupName '<Any resource group within your subscription>' `
                                         -KeyVaultName '<Any key vault within your resource group>' `
                                         -Location '<Any Azure location where Azure Key Vault is available>' `
                                         -LCSEnvironmentId '<The LCS environment ID of your deployed scale unit>' `
    ```

    > [!NOTE]
    > Se não houver cofre de chaves que tem o valor **KeyVaultName** especificado, o script criará automaticamente um.

1. Adicione a ID do aplicativo Azure AD que você acabou de criar (ao usar o script Create-SpokeToHubAADApplication.ps1) à tabela de aplicativos Azure AD no seu hub. Você pode concluir manualmente essa etapa por meio da interface do usuário.

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Carregar pacotes de destino em ativos de projeto LBD no LCS

Esta etapa prepara a versão do aplicativo, a versão da plataforma e as personalizações que farão a transição em seu ambiente de unidade de escala LBD.

1. Carregue o mesmo pacote de aplicativo/plataforma combinado que foi aplicado ao ambiente de hub na biblioteca de ativos do projeto no local do LCS.
1. Obtenha uma cópia do pacote implantável personalizado que foi aplicado ao ambiente de hub e carregue-o na biblioteca de ativos do projeto no local do LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Fazer a manutenção do ambiente LBD com os pacotes de destino

Esta etapa alinha a versão do aplicativo, a versão da plataforma e as personalizações em seu ambiente de unidade de escala LBD com o hub.

1. Faça a manutenção do ambiente LBD com o pacote de aplicativo/plataforma combinado que você carregou na etapa anterior.
1. Faça a manutenção do ambiente LBD com o pacote implantável personalizado que você carregou na etapa anterior.

    ![Aplicando atualizações ao LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Aplicando atualizações ao LCS")

    ![Selecionando o pacote de personalização.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Selecionando o pacote de personalização")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Atribuir sua unidade de escala de borda LBD a um hub

Você configura e gerencia a unidade de escala de borda por meio do Portal de Gerenciamento da Unidade de Escala. Para obter mais informações, consulte [Gerenciar unidades de escala e cargas de trabalho usando o portal de Gerente de Unidade de Escala](./cloud-edge-landing-page.md#scale-unit-manager-portal).

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
