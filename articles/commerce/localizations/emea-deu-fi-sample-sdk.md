---
title: Diretrizes de implantação para o exemplo de integração do serviço de registro fiscal da Alemanha (herdado)
description: Este artigo fornece diretrizes para a implantação do exemplo de integração fiscal da Alemanha do kit de desenvolvimento de software (SDK) do Retail do Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 08/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 7315b6bb145ccdc5631a558af88de55660ebf877
ms.sourcegitcommit: 0feb5d0b06e04f99903069ff2801577be86b8555
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2022
ms.locfileid: "9313846"
---
# <a name="deployment-guidelines-for-the-fiscal-registration-service-integration-sample-for-germany-legacy"></a>Diretrizes de implantação para o exemplo de integração do serviço de registro fiscal da Alemanha (herdado)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Siga as diretrizes deste artigo somente se estiver usando o Microsoft Dynamics 365 Commerce versão 10.0.28 ou anterior. A partir do Commerce versão 10.0.29, o exemplo de integração do serviço de registro para a Alemanha está disponível no kit de desenvolvimento de software (SDK) do Commerce. Para obter mais informações, consulte [Configurar componentes de canal](./emea-deu-fi-sample.md#configure-channel-components).

Este artigo fornece diretrizes para a implantação do exemplo de integração do serviço de registro fiscal da Alemanha do SDK do Retail do Dynamics 365 Commerce em uma máquina virtual de desenvolvedor (VM) no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre este exemplo de integração fiscal, consulte [Exemplo de integração fiscal da Alemanha](emea-deu-fi-sample.md). 

O exemplo de integração fiscal da Alemanha faz parte do SDK do Retail. Para obter informações sobre como instalar e usar o SDK, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Este exemplo consiste em extensões para o Commerce Runtime (CRT) e a estação de hardware. Para executar este exemplo, você deve modificar e criar os projetos do CRT e estação de hardware. É recomendável usar um SDK não modificado do Retail para fazer as alterações descritas neste artigo. Também é recomendável usar um sistema de controle do código-fonte, como o Azure DevOps, onde nenhum arquivo foi alterado ainda.

## <a name="development-environment"></a>Ambiente de desenvolvimento

Siga estas etapas e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

### <a name="enable-commerce-runtime-extensions"></a>Habilitar extensões do Commerce Runtime

Os componentes de extensão do CRT são incluídos nos exemplos de CRT. Para concluir os procedimentos a seguir, abra a solução **CommerceRuntimeSamples.sln** em **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentproviderefrsample-component"></a>Componente DocumentProvider.EFRSample

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.EFRSample** e crie-o.
2. Na pasta **Runtime.Extensions.DocumentProvider.EFRSample\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do Serviços de Informações da Internet da Microsoft (IIS).
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
    ```

#### <a name="documentproviderdatamodelefr-component"></a>Componente DocumentProvider.DataModelEFR

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.DataModelEFR** e crie-o.
2. Na pasta **Runtime.Extensions.DocumentProvider.DataModelEFR\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do IIS.
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
    ```

#### <a name="extension-configuration-file"></a>Extensão de configuração da extensão

1. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

2. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
    ```

### <a name="enable-fiscal-connector-extensions"></a>Habilitar extensões do conector fiscal

Você pode habilitar extensões do conector fiscal na [estação de hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) ou no [terminal de PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

#### <a name="enable-hardware-station-extensions"></a>Habilitar extensões da estação de hardware

Os componentes de extensão da estação de hardware são incluídos nos exemplos da estação de hardware. Para concluir os procedimentos a seguir, abra a solução **HardwareStationSamples.sln** em **RetailSdk\\SampleExtensions\\HardwareStation**.

##### <a name="efrsample-component"></a>Componente EFRSample

1. Encontre o projeto **HardwareStation.Extension.EFRSample** e crie-o.
2. Na pasta **Extension.EFRSample\\bin\\Debug**, encontre os seguintes arquivos de montagem:

    - Contoso.Commerce.HardwareStation.EFRSample.dll
    - Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll

3. Copie os arquivos assembly para a pasta de extensões da estação de hardware:

    - **Estação compartilhada de hardware:** copie os arquivos para a pasta **bin** no local do site da estação de hardware do IIS.
    - **Estação de hardware dedicada no PDV Moderno:** copie os arquivos para o local do agente do cliente de PDV Moderno.

4. Localize o arquivo de configuração da extensão da estação de hardware. O nome do arquivo é **HardwareStation.Extension.config**.

    - **Estação de hardware compartilhada:** o arquivo está no local da estação de hardware do IIS.
    - **Estação de hardware dedicada no PDV moderno:** o arquivo está no local do agente do cliente de PDV moderno.

5. Adicione a linha a seguir à seção **composição** do arquivo de configuração.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample.dll" />
    ```

#### <a name="enable-pos-extensions"></a>Habilitar extensões do PDV

O exemplo de extensão de PDV está localizado na pasta **src\\FiscalIntegration\\PosFiscalConnectorSample** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).

Para usar o exemplo de extensão PDV no SDK herdado, siga estas etapas.

1. Copie a pasta **Pos.Extension** na pasta **Extensões** de PDV do SDK herdado (por exemplo, `C:\RetailSDK\src\POS\Extensions`).
1. Renomeie a cópia da pasta **Pos.Extension** como **PosFiscalConnector**.
1. Remova as seguintes pastas e arquivos da pasta **PosFiscalConnector**:

    - compartimento
    - DataService
    - devDependencies
    - Bibliotecas
    - obj
    - Contoso.PosFiscalConnectorSample.Pos.csproj
    - RetailServerEdmxModel.g.xml
    - tsconfig.json

1. Abra a solução **CloudPos.sln** ou **ModernPos.sln**.
1. No projeto **Pos.Extensions**, inclua a pasta **PosFiscalConnector**.
1. Abra o arquivo **extensions.json** e adicione a extensão **PosFiscalConnector**.
1. Crie o SDK.

### <a name="production-environment"></a>Ambiente de produção

No procedimento anterior, você habilitou as extensões que são componentes do exemplo de integração do serviço de registro fiscal. Além disso, você deve seguir estas etapas para criar pacotes implantáveis que contenham componentes do Commerce e para aplicar esses pacotes em um ambiente de produção.

1. Faça as alterações a seguir nos arquivos de configuração do pacote na pasta **RetailSdk\\Assets**:

    - Nos arquivos de configuração **commerceruntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config**, adicione as seguintes linhas à seção **composição**.

        ``` xml
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsGermany" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

    - No arquivo de configuração **HardwareStation.Extension.config**, adicione as seguintes linhas à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.EFRSample" />
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR" />
        ```

2. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings** na pasta **BuildTools**:

    - Adicione as seguintes linhas para incluir as extensões do CRT nos pacotes implantáveis.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.EFRSample.dll" />
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

    - Adicione as seguintes linhas para incluir as extensões de estação de hardware nos pacotes implantáveis.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.EFRSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.DataModelEFR.dll" />
        ```

3. Inicie o prompt de comando do MSBuild para o utilitário do Visual Studio e execute **msbuild** na pasta do SDK do Retail para criar pacotes implantáveis.
4. Aplique os pacotes via LCS ou manualmente. Para obter mais informações, consulte [Criar pacotes implantáveis](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
5. Conclua todas as tarefas de configuração necessárias descritas em [Configurar o Commerce para a Alemanha](emea-deu-fi-sample.md#set-up-commerce-for-germany).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração do serviço de registro fiscal da Alemanha é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md). Para obter mais informações sobre o design da solução de integração fiscal, consulte a [visão geral de um design de exemplo de integração fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos do serviço e manipular respostas do serviço de registro fiscal.

A extensão do CRT é **Runtime.Extensions.DocumentProvider.EFRSample**. Para obter mais informações sobre o design da solução de integração fiscal, consulte [Visão geral da integração fiscal dos canais do Commerce](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manipulador de solicitações

Existe um manipulador de solicitações para o provedor de documentos, **DocumentProviderEFRFiscalDEU**. Esse manipulador é usado para gerar documentos fiscais para o serviço de registro fiscal. Ele é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado no serviço de registro fiscal.
- **GetFiscalTransactionExtendedDataDocumentProviderRequest** – Esta solicitação retorna a resposta em conjunto com os dados estendidos.

#### <a name="configuration"></a>Configuração

O arquivo de configuração **DocumentProviderFiscalEFRSampleGermany** está localizado na pasta **Configuração** do projeto de extensão. A finalidade deste arquivo é habilitar as configurações para que o provedor de documentos seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

As seguintes configurações são adicionadas:

- **Mapeamento de alíquotas de IVA** – O mapeamento de valores de porcentagem de imposto que são configurados para os códigos de imposto como valores do atributo **TaxG** (grupo de imposto) em solicitações que são enviadas para o serviço fiscal.
- **Grupo de impostos para cartões-presente e depósitos** – O valor do atributo **TaxG** em solicitações enviadas ao serviço fiscal, com base nas operações que envolvem cartões-presente ou depósitos.
- **Mapeamento de tipo de meio de pagamento** – O mapeamento de formas de pagamento para valores do atributo **PAYG** (grupo de pagamento) em solicitações enviadas ao serviço fiscal.
- **Grupo de impostos para isenção de IVA** – O valor do atributo **TaxG** em solicitações enviadas ao serviço fiscal, com base nas operações isentas de obrigações fiscais.
- **Incluir dados do cliente** – Se este parâmetro estiver ativado, as solicitações ao serviço fiscal conterão informações do cliente, como nomes e endereços, em casos que um cliente for adicionado a uma transação.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com o serviço de registro fiscal.

A extensão da estação de hardware é **HardwareStation.Extension.EFRSample**. Ela usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para o serviço de registro fiscal. Ele também manipula as respostas recebidas do serviço de registro fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **EFRHandler** é o ponto de entrada para o manuseio de solicitações ao serviço de registro fiscal. Esse manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para o serviço de registro fiscal e retorna uma resposta dele.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação do serviço de registro fiscal.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para inicializar o serviço de registro fiscal.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizados na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

As seguintes configurações são adicionadas:

- **Endereço do ponto de extremidade** – A URL do serviço de registro fiscal.
- **Tempo limite** – O período, em milissegundos (ms), que o driver aguardará por uma resposta do serviço de registro fiscal.
- **Mostrar notificações do registro fiscal** – Se este parâmetro for ativado, as notificações do serviço fiscal serão mostradas como mensagens do usuário no PDV.

### <a name="pos-fiscal-connector-extension-design"></a>Design de extensão do conector fiscal PDV

A finalidade da extensão do conector fiscal PDV é comunicar-se com o serviço de registro fiscal do PDV. Ele usa o protocolo HTTPS para comunicação.

#### <a name="fiscal-connector-factory"></a>Fábrica do conector fiscal

A fábrica do conector fiscal mapeia o nome do conector para a implementação do conector fiscal e está localizada no arquivo **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. O nome do conector deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

#### <a name="efr-fiscal-connector"></a>Conector fiscal EFR

O conector fiscal EFR está localizado no arquivo **Pos.Extension\\Connectors\\Efr \\EfrFiscalConnector.ts**. Ele implementa a interface **IFiscalConnector** que dá suporte às seguintes solicitações:

- **FiscalRegisterSubmitDocumentClientRequest** – Esta solicitação envia documentos para o serviço de registro fiscal e retorna uma resposta dele.
- **FiscalRegisterIsReadyClientRequest** – Esta solicitação é usada para uma verificação do serviço de registro fiscal.
- **FiscalRegisterInitializeClientRequest** – Esta solicitação é usada para inicializar o serviço de registro fiscal.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizado na pasta **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- **Endereço do ponto de extremidade** – A URL do serviço de registro fiscal.
- **Tempo limite** – O período, em milissegundos, que o conector aguardará por uma resposta do serviço de registro fiscal.
