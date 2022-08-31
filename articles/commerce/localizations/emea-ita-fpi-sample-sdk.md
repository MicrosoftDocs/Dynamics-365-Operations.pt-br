---
title: Diretrizes de implantação para o exemplo de integração da impressora fiscal da Itália (herdado)
description: Este artigo fornece diretrizes para a implantação do exemplo de integração da impressora fiscal da Itália do kit de desenvolvimento de software (SDK) do Retail do Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 46d42a2c2a5f8f40fc8b9693f26a182c8f2e6352
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336630"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-italy-legacy"></a>Diretrizes de implantação para o exemplo de integração da impressora fiscal da Itália (herdado)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Siga as diretrizes deste artigo somente se estiver usando o Microsoft Dynamics 365 Commerce versão 10.0.28 ou anterior. A partir do Commerce versão 10.0.29, o exemplo de integração da impressora fiscal para a Itália está disponível no kit de desenvolvimento de software (SDK) do Commerce. Para obter mais informações, consulte [Configurar componentes de canal](./emea-ita-fpi-sample.md#configure-channel-components).

Este artigo fornece diretrizes para a implantação do exemplo de integração da impressora fiscal para a Itália do SDK do Retail do Dynamics 365 Commerce em uma máquina virtual do desenvolvedor (VM) no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre este exemplo de integração fiscal, consulte [Exemplo de integração da impressora fiscal da Itália](emea-ita-fpi-sample.md). 

O exemplo de integração fiscal da Itália faz parte do SDK do Retail. Para obter informações sobre como instalar e usar o SDK, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Este exemplo consiste em extensões para o Commerce Runtime (CRT) e a estação de hardware. Para executar este exemplo, você deve modificar e criar os projetos do CRT e estação de hardware. É recomendável usar um SDK não modificado do Retail para fazer as alterações descritas neste artigo. Também é recomendável usar um sistema de controle do código-fonte, como o Azure DevOps, onde nenhum arquivo foi alterado ainda.

## <a name="development-environment"></a>Ambiente de desenvolvimento

Siga estas etapas e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

### <a name="commerce-runtime-extension-components"></a>Componentes de extensão do Commerce Runtime

Os componentes de extensão do CRT são incluídos no SDK do Retail. Para concluir os procedimentos a seguir, abra a solução **CommerceRuntimeSamples.sln** em **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample** e crie-o.
2. Na pasta **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do Serviços de Informações da Internet da Microsoft (IIS).
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
    ```

6. Reinicie o Commerce Scale Unit:

    - **Commerce Scale Unit:** reinicie o site do Commerce Scale Unit do Gerenciador do IIS.
    - **Agente do cliente:** encerre o processo **dllhost.exe** no Gerenciador de tarefas e reinicie o PDV moderno.

### <a name="hardware-station-extension-components"></a>Componentes de extensão da estação de hardware

Os componentes de extensão da estação de hardware são incluídos no SDK do Retail. Para concluir os procedimentos a seguir, abra a solução **HardwareStationSamples.sln** em **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Encontre o projeto **HardwareStation.Extensions.EpsonFP90IIIFiscalDeviceSample** e crie-o.
2. Na pasta **Extensions.EpsonFP90IIIFiscalDeviceSample\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll**.
3. Copie o arquivo de montagem para uma máquina da estação de hardware implantada:

    - **Estação de hardware remota:** copie o arquivo para a pasta **bin** no local do site da estação de hardware do IIS.
    - **Estação de hardware local:** copie o arquivo para o local do agente do cliente de PDV moderno.

4. Localize o arquivo de configuração das extensões da estação de hardware. O arquivo é chamado **HardwareStation.Extension.config**:

    - **Estação de hardware remota:** o arquivo está no local da estação de hardware do IIS.
    - **Estação de hardware local:** o arquivo está no local do agente do cliente de PDV moderno.

5. Adicione a seção a seguir à seção **composição** do arquivo de configuração.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
    ```

6. Reinicie o serviço da estação de hardware:

    - **Estação de hardware remota:** reinicie o site da estação de hardware do Gerenciador do IIS.
    - **Estação de hardware local:** encerre o processo **dllhost.exe** no Gerenciador de tarefas e reinicie o PDV moderno.

## <a name="production-environment"></a>Ambiente de produção

Para criar pacotes implantáveis que contenham componentes do Commerce e aplicar esses pacotes em um ambiente de produção, siga estas etapas.

1. Conclua as etapas descritas na seção [Ambiente de desenvolvimento](#development-environment) anteriormente neste artigo.
2. Faça as alterações a seguir nos arquivos de configuração do pacote na pasta **RetailSdk\\Assets**:

    1. Nos arquivos de configuração **commerceruntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config**, adicione a seguinte linha à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample" />
        ```

    1. No arquivo de configuração **HardwareStation.Extension.config**, adicione a seguinte linha à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample" />
        ```

3. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings** na pasta **BuildTools**:

    1. Adicione a seguintes linha para incluir a extensão do CRT nos pacotes implantáveis.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.dll"/>
        ```

    1. Adicione a seguinte linha para incluir a extensão de estação de hardware nos pacotes implantáveis.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EpsonFP90IIIFiscalDeviceSample.dll"/>
        ```

4. Faça as seguintes alterações no arquivo **Sdk.ModernPos.Shared.csproj** na pasta **Packages\_SharedPackagingProjectComponents** para incluir os arquivos de recursos para Itália em pacotes implantáveis:

    1. Adicione uma seção **ItemGroup** que contém nós que apontam para os arquivos de recursos das traduções desejadas. Especifique os namespaces e nomes de exemplo corretos. O exemplo a seguir adiciona nós de recursos aos locais **it** e **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. Na seção **Target Name="CopyPackageFiles"**, adicione uma linha para cada local, conforme mostrado no exemplo a seguir.

        ```xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\CustomizedFiles\ClientBroker\ext\it-CH" SkipUnchangedFiles="true" />
        ```

5. Faça as seguintes alterações no arquivo **Sdk.RetailServerSetup.proj** na pasta **Packages\_SharedPackagingProjectComponents** para incluir os arquivos de recursos para Itália em pacotes implantáveis:

    1. Adicione uma seção **ItemGroup** que contém nós que apontam para os arquivos de recursos das traduções desejadas. Especifique os namespaces e nomes de exemplo corretos. O exemplo a seguir adiciona nós de recursos aos locais **it** e **it-CH**.

        ```xml
        <ItemGroup>
            <ResourcesIt Include="$(SdkReferencesPath)\it\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
            <ResourcesItCh Include="$(SdkReferencesPath)\it-CH\Contoso.Commerce.Runtime.DocumentProvider.EpsonFP90IIISample.resources.dll"/>
        </ItemGroup>
        ```

    1. Na seção **Target Name="CopyPackageFiles"**, adicione uma linha para cada local, conforme mostrado no exemplo a seguir.

        ``` xml
        <Copy SourceFiles="@(ResourcesIt)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it" SkipUnchangedFiles="true" />
        <Copy SourceFiles="@(ResourcesItCh)" DestinationFolder="$(OutputPath)content.folder\RetailServer\Code\bin\ext\it-CH" SkipUnchangedFiles="true" />
        ```

6. Inicie o prompt de comando do MSBuild para o utilitário do Visual Studio e execute **msbuild** na pasta do SDK do Retail para criar pacotes implantáveis.
7. Aplique os pacotes via LCS ou manualmente. Para obter mais informações, consulte [Criar pacotes implantáveis](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Design de extensões

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos da impressora e manipular respostas da impressora fiscal.

A extensão do CRT é **Runtime.Extensions.DocumentProvider.EpsonFP90IIISample**.

Para obter mais informações sobre o design da solução de integração fiscal, consulte [Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais e serviços](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **DocumentProviderEpsonFP90III** é o ponto de entrada para a solicitação gerar documentos da impressora fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico da impressora que deve ser registrado na impressora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, imprimir relatório X e imprimir relatório Z.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizados na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações para que o provedor de documentos seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- Mapeamento dos códigos IVA
- Mapeamento das alíquotas do IVA
- Mapeamento do tipo de meio de pagamento
- Tipo de código de barras do número do recibo
- Tipo de pagamento de depósito

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a impressora fiscal.

A extensão da estação de hardware é **HardwareStation.Extension.EpsonFP90IIIFiscalDeviceSample**. Essa extensão usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para a impressora fiscal. Ele também manipula as respostas recebidas da impressora fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **EpsonFP90IIISample** é o ponto de entrada para o manuseio de solicitações ao dispositivo periférico fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para impressoras e retorna a resposta da impressora fiscal.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade do dispositivo.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para a inicialização da impressora.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizados na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações para que o conector seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- **Endereço do ponto de extremidade** – A URL da impressora.
- **Sincronização de data e hora** – Um valor que especifica se a data e a hora da impressora devem ser sincronizadas com a estação de hardware conectada.
