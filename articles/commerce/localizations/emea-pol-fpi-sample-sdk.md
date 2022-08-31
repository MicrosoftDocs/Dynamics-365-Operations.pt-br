---
title: Diretrizes de implantação para o exemplo de integração da impressora fiscal para a Polônia (herdado)
description: Este artigo fornece diretrizes para a implantação do exemplo de integração da impressora fiscal para a Polônia do kit de desenvolvimento de software do Microsoft Dynamics 365 Commerce Retail (SDK).
author: EvgenyPopovMBS
ms.date: 08/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-03-01
ms.openlocfilehash: 178301e6d8e5f87376ed893e4bf5f966260cad62
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9336633"
---
# <a name="deployment-guidelines-for-the-fiscal-printer-integration-sample-for-poland-legacy"></a>Diretrizes de implantação para o exemplo de integração da impressora fiscal para a Polônia (herdado)

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

> [!IMPORTANT]
> Siga as diretrizes deste artigo somente se estiver usando o Microsoft Dynamics 365 Commerce versão 10.0.28 ou anterior. A partir do Commerce versão 10.0.29, o exemplo de integração da impressora fiscal para a Polônia está disponível no kit de desenvolvimento de software (SDK) do Commerce. Para obter mais informações, consulte [Configurar componentes de canal](./emea-pol-fpi-sample.md#configure-channel-components).

Este artigo fornece diretrizes para a implantação do exemplo de integração da impressora fiscal para a Polônia do SDK do Retail do Dynamics 365 Commerce em uma máquina virtual do desenvolvedor (VM) no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre este exemplo de integração fiscal, consulte [Exemplo de integração da impressora fiscal para a Polônia](emea-pol-fpi-sample.md). 

O exemplo de integração fiscal para a Polônia faz parte do SDK do Retail. Para obter informações sobre como instalar e usar o SDK, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Este exemplo consiste em extensões para o Commerce Runtime (CRT) e a estação de hardware. Para executar este exemplo, você deve modificar e criar os projetos do CRT e estação de hardware. É recomendável usar um SDK não modificado do Retail para fazer as alterações descritas neste artigo. Também é recomendável usar um sistema de controle do código-fonte, como o Azure DevOps, onde nenhum arquivo foi alterado ainda.

## <a name="development-environment"></a>Ambiente de desenvolvimento

Siga estas etapas e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

### <a name="commerce-runtime-extension-components"></a>Componentes de extensão do Commerce Runtime

Os componentes de extensão do CRT são incluídos no SDK do Retail. Para concluir os procedimentos a seguir, abra a solução **CommerceRuntimeSamples.sln** em **RetailSdk\\SampleExtensions\\CommerceRuntime**.

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.PosnetSample** e crie-o.
2. Na pasta **Extensions.DocumentProvider.PosnetSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll**.
3. Copie o arquivo assembly para a pasta da extensão do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do Serviços de Informações da Internet da Microsoft (IIS).
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
    ```

6. Reinicie o Commerce Service:

    - **Commerce Scale Unit:** reinicie o site do Commerce Service do Gerenciador do IIS.
    - **Agente do cliente:** encerre o processo **dllhost.exe** no Gerenciador de tarefas e reinicie o PDV moderno.

### <a name="hardware-station-extension-components"></a>Componentes de extensão da estação de hardware

Os componentes de extensão da estação de hardware são incluídos no SDK do Retail. Para concluir os procedimentos a seguir, abra a solução **HardwareStationSamples.sln** em **RetailSdk\\SampleExtensions\\HardwareStation**.

1. Encontre o projeto **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample** e crie-o.
2. Na pasta **Extension.Posnet.ThermalFVFiscalPrinterSample\\bin\\Debug**, encontre o arquivo assembly **Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll**.
3. Copie o arquivo de montagem para uma máquina da estação de hardware implantada:

    - **Estação de hardware remota:** copie o arquivo para a pasta **bin** no local do site da estação de hardware do IIS. Copie as bibliotecas de drivers da impressora (**libposcmbth.dll**, **libcmbth\_serial.dll**, and **cmbth\_pl.lng**).

4. Localize o arquivo de configuração das extensões da estação de hardware. O arquivo é chamado **HardwareStation.Extension.config**:

    - **Estação de hardware remota:** o arquivo está no local da estação de hardware do IIS.

5. Adicione a linha a seguir à seção **composição** do arquivo de configuração.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
    ```

6. Reinicie o serviço da estação de hardware:

    - **Estação de hardware remota:** reinicie o site da estação de hardware do Gerenciador do IIS.

## <a name="production-environment"></a>Ambiente de produção

No procedimento anterior, você habilitou as extensões que são componentes do exemplo de integração do serviço de registro fiscal. Além disso, você deve seguir estas etapas para criar pacotes implantáveis que contenham componentes do Commerce e para aplicar esses pacotes em um ambiente de produção.

1. Faça as alterações a seguir nos arquivos de configuração do pacote na pasta **RetailSdk\\Assets**:

    - Nos arquivos de configuração **commerceruntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config**, adicione a seguinte linha à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample" />
        ```

    - No arquivo de configuração **HardwareStation.Extension.config**, adicione a seguinte linha à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample" />
        ```

1. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings** na pasta **BuildTools**:

    - Adicione a seguintes linha para incluir a extensão do CRT nos pacotes implantáveis.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.Extensions.DocumentProvider.PosnetSample.dll"/>
        ```

    - Adicione a seguinte linha para incluir a extensão de estação de hardware nos pacotes implantáveis.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.PosnetThermalFVFiscalPrinterSample.dll"/>
        ```

1. Inicie o prompt de comando do MSBuild para o utilitário do Visual Studio e execute **msbuild** na pasta do SDK do Retail para criar pacotes implantáveis.
1. Aplique os pacotes via LCS ou manualmente. Para obter mais informações, consulte [Criar pacotes implantáveis](../dev-itpro/retail-sdk/retail-sdk-packaging.md).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração da impressora fiscal para a Polônia se baseia na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md). Para obter mais informações sobre o design da solução de integração fiscal, consulte a [visão geral de um design de exemplo de integração fiscal](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos da impressora e manipular respostas da impressora fiscal.

A extensão do CRT é **Runtime.Extensions.DocumentProvider.PosnetSample**. Essa extensão gera um conjunto de comandos específicos da impressora no formato JSON (JavaScript Object Notation) definido pela especificação POSNET 19-3678.

Para obter mais informações sobre o design da solução de integração fiscal, consulte [Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais e serviços](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **DocumentProviderPosnetProtocol** é o ponto de entrada para a solicitação gerar documentos da impressora fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico da impressora que deve ser registrado na impressora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, imprimir relatório X e imprimir relatório Z.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações para que o provedor de documentos seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- Mapeamento das alíquotas do IVA
- Mapeamento do tipo de meio de pagamento
- Tipo de pagamento de depósito

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a impressora fiscal.

A extensão da estação de hardware é **HardwareStation.Extension.PosnetThermalFVFiscalPrinterSample**. Essa extensão chama as funções do driver POSNET para enviar comandos que a extensão do CRT gera para a impressora fiscal. Ela também manipula erros de dispositivo.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **FiscalPrinterHandler** é o ponto de entrada para o manuseio da solicitação ao dispositivo periférico fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para impressoras e retorna a resposta da impressora fiscal.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade do dispositivo.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para a inicialização da impressora.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizados na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações para que o conector seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- **Cadeia de conexão** – Uma cadeia de caracteres que descreve os detalhes da conexão com o dispositivo em um formato compatível com o driver. Para obter mais informações, consulte a documentação do driver POSNET.
- **Sincronização de data e hora** – Um valor que especifica se a data e a hora da impressora devem ser sincronizadas com a estação de hardware conectada.
- **Tempo limite do dispositivo** – O período, em milissegundos, que o driver aguardará por uma resposta do dispositivo. Para obter mais informações, consulte a documentação do driver POSNET.
