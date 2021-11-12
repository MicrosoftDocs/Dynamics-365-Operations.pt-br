---
title: Implantar unidades de escala de borda em hardware personalizado usando LBD (Versão preliminar)
description: Este tópico explica como provisionar unidades de escala de borda local usando o hardware e a implantação personalizados que se baseiam em dados comerciais locais (LBD).
author: cabeln
ms.date: 04/22/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ebbdaab9d6f040497d3158db2712e102b6e9aa8
ms.sourcegitcommit: 1e5a46271bf7fae2f958d2b1b666a8d2583e04a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/25/2021
ms.locfileid: "7678972"
---
# <a name="deploy-edge-scale-units-on-custom-hardware-using-lbd-preview"></a>Implantar unidades de escala de borda em hardware personalizado usando LBD (Versão preliminar)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)] <!--KFM: Until 11/1/2021 -->

As unidades de escala de borda desempenham uma função importante na topologia híbrida distribuída para o gerenciamento da cadeia de fornecedores. Na topologia híbrida, você pode distribuir cargas de trabalho entre o seu hub de nuvem do Supply Chain Management e unidades de escala adicionais na nuvem ou na borda.

As unidades de escala de borda podem ser implantadas criando-se um [ambiente local](../../fin-ops-core/dev-itpro/deployment/on-premises-deployment-landing-page.md) de dados comerciais locais (LBD) e, em seguida, configurando-o para funcionar como uma unidade de escala na sua topologia híbrida distribuída para o gerenciamento da cadeia de fornecedores. Isso é obtido associando o ambiente LBD local a um ambiente do Supply Chain Management nuvem, que foi configurado para funcionar como um hub.  

No momento, as unidades de escala de borda estão na versão preliminar. Portanto, você pode usar um ambiente desse tipo somente de acordo com os [termos da versão preliminar](https://aka.ms/scmcnepreviewterms).

Este tópico descreve como configurar um ambiente LBD local como uma unidade de escala de borda e depois associá-lo a um hub.

## <a name="deployment-overview"></a>Visão geral da implantação

Aqui está uma visão geral das etapas de implantação.

1. **Habilite um slot LBD no seu projeto LBD no Microsoft Dynamics Lifecycle Services (LCS).**

    Durante a versão preliminar, as unidades de escala de borda LBD destinam-se a clientes LBD existentes. Um slot de área restrita LBD limitada de 60 dias só será fornecido em situações de cliente específicas.

1. **Configure e implante um ambiente LBD com um banco de dados *vazio*.**

    Use o LCS para implantar o ambiente LBD com a topologia mais recente e um banco de dados vazio. Para obter mais informações, consulte a seção [Configurar e implantar um ambiente LBD com um banco de dados vazio](#set-up-deploy) posteriormente neste tópico. Você deve usar o Supply Chain Management versão 10.0.19 com a Platform Update 43 ou posterior em ambientes de unidade de escala e hub.

1. **Carregue pacotes de destino em ativos de projeto LBD no LCS.**

    Prepare aplicativos, plataformas e pacotes de personalização usados no hub e na unidade de escala de borda. Para obter mais informações, consulte a seção [Carregar pacotes de destino em ativos de projeto LBD no LCS](#upload-packages) posteriormente neste tópico.

1. **Faça a manutenção do ambiente LBD com os pacotes de destino.**

    Essa etapa garante que os mesmos builds e personalizações sejam implantados no hub e no spoke. Para obter mais informações, consulte a seção [Fazer a manutenção do ambiente LBD com os pacotes de destino](#service-target-packages) posteriormente neste tópico.

1. **Conclua a configuração da unidade de escala e a atribuição de carga de trabalho.**

    Para obter mais informações, consulte a seção [Atribuir sua unidade de escala de borda LBD a um hub](#assign-edge-to-hub) posteriormente neste tópico.

As seções restantes deste tópico fornecem mais detalhes sobre como concluir essas etapas.

## <a name="set-up-and-deploy-an-lbd-environment-with-an-empty-database"></a><a name="set-up-deploy"></a>Configurar e implantar um ambiente LBD com um banco de dados vazio

Esta etapa cria um ambiente LBD funcional. No entanto, o ambiente não tem necessariamente as mesmas versões de aplicativo e plataforma que o ambiente de hub. Além disso, ainda está faltando as personalizações, e ele ainda não foi habilitado para trabalhar como uma unidade de escala.

1. Siga as instruções em [Configurar e implantar ambientes locais (Platform update 41 e posterior)](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md). Você deve usar o Supply Chain Management versão 10.0.19 com a Platform Update 43 ou posterior em ambientes de unidade de escala e hub

    > [!IMPORTANT]
    > Leia o restante desta seção **antes** de concluir as etapas deste tópico.

1. Antes de descrever a configuração no arquivo infrastructure\\ConfigTemplate.xml, execute o seguinte script:

    ```powershell
    .\Configure-ScriptsForEdgeScaleUnits.ps1 -ConfigurationFilePath .\ConfigTemplate.xml
    ```

    > [!NOTE]
    > Esse script removerá qualquer configuração que não seja necessária para implantar unidades de escala de borda.

1. Configure um banco de dados que contenha dados vazios, conforme descrito em [Configurar bancos de dados](../../fin-ops-core/dev-itpro/deployment/setup-deploy-on-premises-pu41.md#configuredb). Use o arquivo data.bak vazio para essa etapa.
1. Configure o script de pré-implantação. Para obter mais informações, consulte [Scripts de pré-implantação e pós-implantação de agente local](../../fin-ops-core/dev-itpro/lifecycle-services/pre-post-scripts.md).

    1. Copie o conteúdo da pasta **ScaleUnit** em **Scripts de Infra-estrutura** para a pasta **Scripts** no compartilhamento de armazenamento de arquivo do agente que foi configurado no ambiente. Um caminho típico é \\\\lbdiscsi01\\agente\\Scripts.
    2. Crie o script **PreDeployment.ps1** que chamará os scripts usando os parâmetros necessários. O script de pré-implantação deve ser colocado na pasta **Scripts** no compartilhamento de armazenamento de arquivo do agente. Caso contrário, ele não poderá ser executado. Um caminho típico é \\\\lbdiscsi01\\agente\\Scripts\\PreDeployment.ps1.

        O conteúdo do script PreDeployment.ps1 será semelhante ao exemplo a seguir.

        ```powershell
        $agentShare = '\\lbdiscsi01\agent'
        
        Write-Output "AgentShare is set to $agentShare" 
        & $agentShare\Scripts\Configure-CloudandEdge.ps1 -AgentShare $agentShare -InstanceId '@A' -DatabaseServer 'lbdsqla01.contoso.com' -DatabaseName 'AXDB'
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

## <a name="upload-target-packages-into-lbd-project-assets-in-lcs"></a><a name="upload-packages"></a>Carregar pacotes de destino em ativos de projeto LBD no LCS

Esta etapa prepara a versão do aplicativo, a versão da plataforma e as personalizações que farão a transição em seu ambiente de unidade de escala LBD.

1. Carregue o mesmo pacote de aplicativo/plataforma combinado que foi aplicado ao ambiente de hub na biblioteca de ativos do projeto no local do LCS.
1. Obtenha uma cópia do pacote implantável personalizado que foi aplicado ao ambiente de hub e carregue-o na biblioteca de ativos do projeto no local do LCS.

## <a name="service-the-lbd-environment-with-target-packages"></a><a name="service-target-packages"></a>Fazer a manutenção do ambiente LBD com os pacotes de destino

Esta etapa alinha a versão do aplicativo, a versão da plataforma e as personalizações em seu ambiente de unidade de escala LBD com o hub.

1. Faça a manutenção do ambiente LBD com o pacote de aplicativo/plataforma combinado que você carregou na etapa anterior.
1. Faça a manutenção do ambiente LBD com o pacote implantável personalizado que você carregou na etapa anterior.

    ![Selecionando Manter > Aplicar atualizações no LCS.](media/cloud_edge-LBD-LCS-ServiceLBDEnv1.png "Selecionando Manter > Aplicar atualizações no LCS")

    ![Selecionando o pacote de personalização.](media/cloud_edge-LBD-LCS-ServiceLBDEnv2.png "Selecionando o pacote de personalização")

## <a name="assign-your-lbd-edge-scale-unit-to-a-hub"></a><a name="assign-edge-to-hub"></a>Atribuir sua unidade de escala de borda LBD a um hub

Embora as unidades de escala de borda ainda estejam na versão preliminar, você deve usar as [ferramentas de configuração e implantação da unidade de escala](https://github.com/microsoft/SCMScaleUnitDevTools) disponíveis no GitHub para atribuir sua unidade de escala de borda LBD a um hub. O processo permite que uma configuração LBD funcione como uma unidade de escala de borda e a associa ao hub. O processo é semelhante à configuração de um ambiente de desenvolvimento de uma caixa.

1. Baixe a versão mais recente do [SCMScaleUnitDevTools](https://github.com/microsoft/SCMScaleUnitDevTools/releases) e descompacte o conteúdo do arquivo.
1. Crie uma cópia do arquivo `UserConfig.sample.xml` e dê-lhe o nome de `UserConfig.xml`.
1. Crie um aplicativo Microsoft Azure Active Directory (Azure AD) no seu locatário do Azure AD, conforme mencionado no [Guia de implantação para unidades de escala e cargas de trabalho](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#aad-application-registrations).
    1. Depois de criado, navegue até o formulários dos aplicativos Azure AD (SysAADClientTable) no seu hub.
    1. Crie uma nova entrada e defina a **ID do Cliente** como a ID do aplicativo criado. Defina o **Nome** como *ScaleUnits* e a **ID de Usuário** como *Admin*.

1. Crie um aplicativo AD FS (serviço de Federação do Active Directory) conforme mencionado no [Guia de implantação para unidades de escala e cargas de trabalho](https://github.com/microsoft/SCMScaleUnitDevTools/wiki/Step-by-step-usage-guide#adfs-application-registrations).
    1. Depois de criado, navegue até o formulários dos aplicativos Azure AD (SysAADClientTable) na unidade de escala de borda.
    1. Crie uma nova entrada e defina a **ID do Cliente** como a ID do aplicativo criado. Defina a **ID de Usuário** como *Admin*.

1. Modifique o arquivo `UserConfig.xml`.
    1. Na seção `InterAOSAADConfiguration`, insira as informações do aplicativo Azure AD criado anteriormente.
        - No elemento `AppId`, insira a ID de aplicativo do aplicativo Azure.
        - No elemento `AppSecret`, insira o segredo de aplicativo do aplicativo Azure.
        - O elemento `Authority` deve conter a URL especificando a autoridade de segurança para o seu locatário.

        ```xml
        <InterAOSAADConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopty56TGUedDTVhtER-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </InterAOSAADConfiguration>
        ```

    1. Na seção `ScaleUnitConfiguration`, para o primeiro `ScaleUnitInstance`, modifique a seção `AuthConfiguration`.
        - No elemento `AppId`, insira a ID de aplicativo do aplicativo Azure.
        - No elemento `AppSecret`, insira o segredo de aplicativo do aplicativo Azure.
        - O elemento `Authority` deve conter a URL especificando a autoridade de segurança para o seu locatário.

        ```xml
        <AuthConfiguration>
            <AppId>8dab14f6-97b1-48e3-b51b-350b45f6ede5</AppId>
            <AppSecret>k6em-_7.lopdz.6d3DTVOtf9Lo-j_6anY1</AppSecret>
            <Authority>https://login.windows.net/contoso.onmicrosoft.com</Authority>
        </AuthConfiguration>
        ```

    1. Além disso, para o mesmo `ScaleUnitInstance`, defina os seguintes valores:
        - No elemento `Domain`, especifique a URL do seu hub. Por exemplo: `https://cloudhub.sandbox.operations.dynamics.com/`
        - No elemento `EnvironmentType`, verifique se o valor `LCSHosted` está definido.

    1. Na seção `ScaleUnitConfiguration`, para o segundo `ScaleUnitInstance`, modifique a seção `AuthConfiguration`.
        - No elemento `AppId`, insira a ID de aplicativo do aplicativo AD FS.
        - No elemento `AppSecret`, insira o segredo de aplicativo do aplicativo ADFS.
        - O elemento `Authority` deve conter a URL da sua instância do AD FS.

        ```xml
        <AuthConfiguration>
            <AppId>26b16f25-21d8-4d36-987b-62df292895aa</AppId>
            <AppSecret>iZFfObgI6lLtY9kEbBjEFV98NqI5_YZ0e5SBcWER</AppSecret>
            <Authority>https://adfs.contoso.com/adfs</Authority>
        </AuthConfiguration>
        ```

    1. Além disso, para o mesmo `ScaleUnitInstance`, defina os seguintes valores:
        - No elemento `Domain`, especifique a URL da sua unidade de escala de borda. Por exemplo: https://ax.contoso.com/
        - No elemento `EnvironmentType`, verifique se o valor LBD está definido.
        - No elemento `ScaleUnitId`, insira o mesmo valor que você especificou para `InstanceId` ao configurar o script de pré-implantação `Configure-CloudandEdge.ps1`.

        > [!NOTE]
        > Se você não usar a ID padrão (@A), certifique-se de atualizar ScaleUnitId para cada ConfiguredWorkload na seção Cargas de Trabalho.

1. Abra o PowerShell e navegue até a pasta que contém o arquivo `UserConfig.xml`.

1. Execute a ferramenta com este comando.

    ```powershell
    .\CLI.exe
    ```

    > [!NOTE]
    > Após cada ação, você terá que iniciar a ferramenta novamente.

1. Na ferramenta, selecione **2. Preparar ambientes para a instalação das cargas de trabalho**. Em seguida, execute as seguintes etapas:
    1. Selecione **1. Preparar o Hub**.
    1. Selecione **2. Preparar a Unidade de Escala**.

    > [!NOTE]
    > Se você não estiver executando este comando a partir de uma instalação limpa e ele falhar, execute as seguintes ações:
    >
    > - Remova todas as pastas da pasta `aos-storage` (exceto para `GACAssemblies`).
    > - Execute o seguinte comando SQL no banco de dados comercial (AXDB):
    >
    > ```sql 
    > delete from storagefoler
    > ```

1. Execute os seguintes comandos SQL no banco de dados comercial (AXDB):

    ```sql
    delete from FEATUREMANAGEMENTMETADATA
    delete from FEATUREMANAGEMENTSTATE
    delete from NUMBERSEQUENCESCOPE
    ```

1. Verificar se o controle de alterações foi habilitado no banco de dados comercial (AXDB)
    1. Inicie o SQL Server Management Studio (SSMS).
    1. Clique com o botão direito do mouse no banco de dados comercial (AXDB) e selecione Propriedades.
    1. Na janela que é aberta, selecione **Controle de Alterações** e faça as seguintes configurações:

        - **Controle de Alterações:** *Verdadeiro*
        - **Período de Retenção:** *7*
        - **Unidades de Retenção:** *Dias*
        - **Limpeza Automática:** *Verdadeiro*

1. Na ferramenta, selecione **3. Instalar cargas de trabalho**. Em seguida, execute as seguintes etapas:
    1. Selecione **1. Instalar no Hub**.
    1. Selecione **2. Instalar na Unidade de Escala**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
