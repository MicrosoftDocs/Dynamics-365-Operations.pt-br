---
title: Diretrizes de implantação do exemplo de integração da unidade de controle da Suécia (herdado)
description: Este artigo fornece diretrizes para a implantação do exemplo de integração da unidade de controle da Suécia do (SDK) do Retail
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: fcc35a2203641b24fe4edd2ab34f2e4d5db9bb53
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324288"
---
# <a name="deployment-guidelines-for-the-control-unit-integration-sample-for-sweden-legacy"></a>Diretrizes de implantação do exemplo de integração da unidade de controle da Suécia (herdado)

[!include [banner](../includes/banner.md)]

Este artigo fornece diretrizes para a implantação do exemplo de integração da unidade de controle da Suécia do kit de desenvolvimento de software (SDK) do Retail em uma máquina virtual de desenvolvedor (VM) no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações sobre este exemplo de integração fiscal, consulte [Exemplo de integração da unidade de controle da Suécia](emea-swe-fi-sample.md). 

O exemplo de integração fiscal para a Suécia faz parte do SDK do Retail. Para obter informações sobre como instalar e usar o SDK, consulte [Arquitetura do SDK (software development kit) do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md). Este exemplo consiste em extensões para o Commerce Runtime (CRT), estação de hardware e ponto de venda (PDV). Para executar este exemplo, você deve modificar e criar os projetos do CRT, estação de hardware e PDV. É recomendável usar um SDK não modificado do Retail para fazer as alterações descritas neste artigo. Também é recomendável usar um sistema de controle do código-fonte, como o Azure DevOps, onde nenhum arquivo foi alterado ainda.

## <a name="development-environment"></a>Ambiente de desenvolvimento

Siga estas etapas e configure um ambiente de desenvolvimento para poder testar e estender a amostra.

### <a name="enable-crt-extensions"></a>Habilitar extensões do CRT

Os componentes de extensão do CRT são incluídos nos exemplos de CRT. Para concluir os procedimentos a seguir, abra a solução **CommerceRuntimeSamples.sln** em **RetailSdk\\SampleExtensions\\CommerceRuntime**.

#### <a name="documentprovidercleancashsample-component"></a>Componente DocumentProvider.CleanCashSample

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.CleanCashSample** e crie-o.
2. Na pasta **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do Serviços de Informações da Internet da Microsoft (IIS).
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

5. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    ```

#### <a name="extension-configuration-file"></a>Extensão de configuração da extensão

1. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **commerceruntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está no local do agente do cliente CRT local.

2. Registre a alteração do CRT no arquivo de configuração da extensão.

    ``` xml
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

### <a name="enable-hardware-station-extensions"></a>Habilitar extensões da estação de hardware

Os componentes de extensão da estação de hardware são incluídos nos exemplos da estação de hardware. Para concluir os procedimentos a seguir, abra a solução **HardwareStationSamples.sln** em **RetailSdk\\SampleExtensions\\HardwareStation**.

#### <a name="cleancash-component"></a>Componente CleanCash

1. Encontre o projeto **HardwareStation.Extension.CleanCashSample** e crie-o.
2. Na pasta **Extension.CleanCashSample\\bin\\Debug**, encontre os arquivos assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** e **Interop.CleanCash\_1\_1.dll**.
3. Copie os arquivos assembly para a pasta de extensões da estação de hardware:

    - **Estação compartilhada de hardware:** copie os arquivos para a pasta **bin** no local do site da estação de hardware do IIS.
    - **Estação de hardware dedicada no PDV Moderno:** copie os arquivos para o local do agente do cliente de PDV Moderno.

4. Localize o arquivo de configuração da extensão da estação de hardware. O nome do arquivo é **HardwareStation.Extension.config**.

    - **Estação de hardware compartilhada:** o arquivo está no local da estação de hardware do IIS.
    - **Estação de hardware dedicada no PDV Moderno:** o arquivo está no local do agente do cliente de PDV Moderno.

5. Adicione a linha a seguir à seção **composição** do arquivo de configuração.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

### <a name="enable-modern-pos-extension-components"></a>Habilitar os componentes da extensão do PDV Moderno

1. Abra a solução **ModernPOS.sln** em **RetailSdk\\POS** e verifique se ela pode ser compilada sem erros. Além disso, verifique se você pode executar o Modern PDV do Visual Studio usando o comando **Run**.

    > [!NOTE]
    > O PDV Moderno não deve ser personalizado. Você deve habilitar o UAC (Controle de Conta de Usuário) e desinstalar instâncias instaladas anteriormente do PDV Moderno, conforme necessário.

2. Habilite as extensões que precisam ser carregadas adicionando as seguintes linhas ao arquivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Para obter mais informações e para exemplos que mostram como incluir pastas de código-fonte e permitir que as extensões sejam carregadas, consulte as instruções no arquivo readme.md no projeto **Pos.Extensions**.

3. Recrie a solução.
4. Execute o PDV Moderno no depurador e teste a funcionalidade.

### <a name="enable-cloud-pos-extension-components"></a>Habilitar componentes da extensão do PDV em Nuvem

1. Abra a solução **CloudPOS.sln** em **RetailSdk\\POS** e verifique se ela pode ser compilada sem erros.
2. Habilite as extensões que precisam ser carregadas adicionando as seguintes linhas ao arquivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

    > [!NOTE]
    > Para obter mais informações e para exemplos que mostram como incluir pastas de código-fonte e permitir que as extensões sejam carregadas, consulte as instruções no arquivo readme.md no projeto **Pos.Extensions**.

3. Recrie a solução.
4. Execute a solução usando o comando **Run** e seguindo as etapas no manual do SDK do Retail.

## <a name="production-environment"></a>Ambiente de produção

O procedimento anterior habilita as extensões que são componentes do exemplo de integração da unidade de controle. Além disso, você deve seguir estas etapas para criar pacotes implantáveis que contenham componentes do Commerce e para aplicar esses pacotes em um ambiente de produção.

1. Faça as alterações a seguir nos arquivos de configuração do pacote na pasta **RetailSdk\\Assets**:

    - Nos arquivos de configuração **commerceruntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config**, adicione as seguintes linhas à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
        <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
        ```

    - No arquivo de configuração **HardwareStation.Extension.config**, adicione a seguinte linha à seção **composição**.

        ``` xml
        <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
        ```

2. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings** na pasta **BuildTools**:

    - Adicione a seguinte linha para incluir as extensões do CRT nos pacotes implantáveis.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
        ```

    - Adicione as seguintes linhas para incluir a extensão de estação de hardware nos pacotes implantáveis.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

3. Habilite a extensão de PDV adicionando as seguintes linhas ao arquivo **extensions.json** na pasta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
            "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

4. Inicie o prompt de comando do MSBuild para o utilitário do Visual Studio e execute **msbuild** na pasta do SDK do Retail para criar pacotes implantáveis.
5. Aplique os pacotes via LCS ou manualmente. Para obter mais informações, consulte [Criar pacotes implantáveis](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
6. Conclua todas as tarefas de configuração necessárias descritas em [Configurar a integração com unidades de controle](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).

## <a name="design-of-the-extensions"></a>Design das extensões

### <a name="crt-extension-design"></a>Design de extensão do CRT

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos do serviço e manipular respostas da unidade de controle.

A extensão do CRT é **Runtime.Extensions.DocumentProvider.CleanCashSample**.

Para obter mais informações sobre o design da solução de integração fiscal, consulte [Processo de registro fiscal e exemplos de integração fiscal para dispositivos fiscais e serviços](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services).

#### <a name="request-handler"></a>Manipulador de solicitações

Há um único manipulador de solicitações **DocumentProviderCleanCash** para o provedor de documentos. Esse manipulador é usado para gerar documentos fiscais para a unidade de controle.

Esse manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado na unidade de controle.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte a eventos de vendas e de auditoria.

#### <a name="configuration"></a>Configuração

O arquivo de configuração **DocumentProviderFiscalCleanCashSample** está na pasta **Configuração** do projeto de extensão. A finalidade deste arquivo é habilitar as configurações para que o provedor de documentos seja configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- Mapeamento dos códigos IVA

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a unidade de controle.

A extensão da estação de hardware é **HardwareStation.Extension.CleanCashSample**. Ela usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para a unidade de controle. Ela também manipula as respostas recebidas da unidade de controle.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **CleanCashHandler** é o ponto de entrada para o manuseio de solicitações à unidade de controle.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para a unidade de controle e retorna uma resposta dela.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade da unidade de controle.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para inicializar a unidade de controle.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está na pasta **Configuração** do projeto de extensão. A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- **Cadeia de conexões** – As configurações de conexão da unidade de controle.
- **Tempo limite** – O período, em milissegundos, que o driver aguardará por uma resposta da unidade de controle.

## <a name="migrating-from-the-earlier-integration-sample"></a>Migrar do exemplo de integração anterior

Se você estiver usando o [exemplo anterior de integração do PDV com unidades de controle da Suécia](retail-sdk-control-unit-sample.md), talvez seja necessário migrar dele para o exemplo de integração atual. Para ativar a alteração e receber atualizações oportunas para os recursos da Suécia no futuro, talvez seja necessário atualizar, fazer ajustes de código e de configuração secundários nas extensões que você criou e recriar suas soluções. Nenhuma alteração importante é necessária na lógica de extensão que você criou. O exemplo de integração anterior e suas personalizações continuarão a funcionar se nenhuma alteração for feita por você. Portanto, você pode planejar, preparar-se e realizar a tomada no seu ambiente.

### <a name="migration-process"></a>Processo de migração

A migração do exemplo de integração anterior para o da unidade de controle atual deve se basear no conceito de atualização gradual. Em outras palavras, todos os componentes do Commerce Scale Unit e do Commerce headquarters já devem estar atualizados antes de você começar a atualizar os componentes do PDV e da estação de hardware.

Para ajudar a evitar uma situação em que um evento ou uma transação é assinada duas vezes (ou seja, ela é assinada pela extensão anterior e pela extensão atual) ou em que um evento ou uma transação não pode ser assinada por causa da configuração ausente, recomendamos que você desative todos os dispositivos de PDV e da estação de hardware que usam o exemplo anterior e, depois, atualizá-los simultaneamente. Essa atualização simultânea pode ser feita, por exemplo, a cada armazenamento atualizando o perfil de funcionalidade do armazenamento e do perfil de hardware da estação de hardware.

O processo de migração deve consistir nas etapas a seguir.

1. Atualize os componentes do Commerce headquarters.
1. Atualize os componentes do Commerce Scale Unit e habilite as extensões do exemplo atual.
1. Verifique se todas as transações offline foram sincronizadas a partir de dispositivos MPOS habilitados para offline.
1. Desative todos os dispositivos que usam os componentes do exemplo anterior.
1. Conclua todas as tarefas de configuração necessárias descritas em [Configurar a integração com unidades de controle](emea-swe-fi-sample.md#setting-up-the-integration-with-control-units).
1. Atualize os componentes do PDV e da estação de hardware, desabilite as extensões que fazem parte do exemplo anterior e habilite as extensões do exemplo atual.

    > [!NOTE]
    > Dependendo do tipo de ambiente, você pode encontrar mais detalhes técnicos sobre o processo de migração nas seções [Migração em um ambiente de desenvolvimento](#migration-in-a-development-environment) ou [Migração em um ambiente de produção](#migration-in-a-production-environment) deste artigo.

### <a name="migration-in-a-development-environment"></a>Migração em um ambiente de desenvolvimento

#### <a name="update-crt"></a>Atualizar CRT

1. Encontre o projeto **Runtime.Extensions.DocumentProvider.CleanCashSample** e crie-o.
2. Na pasta **Runtime.Extensions.DocumentProvider.CleanCashSample\\bin\\Debug**, encontre o arquivo de montagem **Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll**.
3. Copie o arquivo assembly para a pasta de extensões do CRT:

    - **Commerce Scale Unit:** Copie o arquivo para a pasta **\\bin\\ext** no local do site do Commerce Scale Unit do IIS.
    - **CRT local no POS moderno:** Copie o arquivo para a pasta **\\ext** no local do agente do cliente CRT local.

4. Localize o arquivo de configuração da extensão do CRT:

    - **Commerce Scale Unit:** o nome do arquivo é **CommerceRuntime.ext.config**, e ele está na pasta **bin\\ext**, no local do site do Commerce Scale Unit do IIS.
    - **CRT local no PDV Moderno:** o nome do arquivo é **CommerceRuntime.MPOSOffline.Ext.config**, e ele está na pasta **bin\\ext** no local do agente do cliente CRT local.

    > [!WARNING]
    > **Não** edite os arquivos CommerceRuntime.config e CommerceRuntime.MPOSOffline.config. Esses arquivos não são destinados a personalizações.

5. Localize e remova a extensão do CRT anterior do arquivo de configuração de extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Não conclua esta etapa até atualizar todos os dispositivos PDV que funcionam com essa instância do CRT.

6. Registre as extensões de exemplo atuais do CRT no arquivo de configuração de extensão adicionando as linhas a seguir.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

#### <a name="update-hardware-station"></a>Atualizar estação de hardware

1. Encontre o projeto **HardwareStation.Extension.CleanCashSample** e crie-o.
2. Na pasta **Extension.CleanCashSample\\bin\\Debug**, encontre os arquivos assembly **Contoso.Commerce.HardwareStation.CleanCashSample.dll** e **Interop.CleanCash\_1\_1.dll**.
3. Copie os arquivos assembly para a pasta de extensões da estação de hardware:

    - **Estação compartilhada de hardware:** copie os arquivos para a pasta **bin** no local do site da estação de hardware do IIS.
    - **Estação de hardware dedicada no PDV Moderno:** copie os arquivos para o local do agente do cliente de PDV Moderno.

4. Localize o arquivo de configuração da extensão **HardwareStation.Extension.config**:

    - **Estação de hardware remota:** o arquivo está no local da estação de hardware do IIS.
    - **Estação de hardware local no PDV Moderno:** o arquivo está no local do agente do cliente de PDV Moderno.

    > [!WARNING]
    > **Não** edite os arquivos CommerceRuntime.config e CommerceRuntime.MPOSOffline.config. Esses arquivos não são destinados a personalizações.

5. Localize e remova a extensão da estação de hardware anterior do arquivo de configuração de extensão.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 e anterior](#tab/retail-7-3)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 e posterior](#tab/retail-7-3-1)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 e posterior](#tab/retail-10-0)

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

6. Adicione a linha a seguir à seção **composição** do arquivo de configuração de extensão.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

#### <a name="update-modern-pos"></a>Atualizar PDV Moderno

1. Abra a solução **CloudPOS.sln** em **RetailSdk\\POS**.
2. Desabilite a extensão de PDV anterior removendo as seguintes linhas do arquivo **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Habilite o exemplo de extensão de PDV atual adicionando as seguintes linhas ao arquivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Atualizar PDV em Nuvem

1. Abra a solução **ModernPOS.sln** em **RetailSdk\\POS**.
2. Desabilite a extensão de PDV anterior removendo as seguintes linhas do arquivo **extensions.json**.

    ``` json
    {
        "baseUrl": "FiscalRegisterSample"
    }
    ```

2. Habilite o exemplo de extensão de PDV atual adicionando as seguintes linhas ao arquivo **extensions.json**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

### <a name="migration-in-a-production-environment"></a>Migração em um ambiente de produção

#### <a name="update-crt"></a>Atualizar CRT

1. Remova a extensão de CRT anterior dos arquivos de configuração **CommerceRuntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** na pasta **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.FiscalRegisterReceiptSample" />
    ```

    > [!WARNING]
    > Não conclua esta etapa até atualizar todos os dispositivos PDV que funcionam com essa instância do CRT.

2. Habilite o exemplo atual de extensões de CRT fazendo as seguintes alterações nos arquivos de configuração **CommerceRuntime.ext.config** e **CommerceRuntime.MPOSOffline.Ext.config** na pasta **RetailSdk\\Assets**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample" />
    <add source="assembly" value="Microsoft.Dynamics.Commerce.Runtime.ReceiptsSweden" />
    ```

3. No arquivo de configuração de personalização de pacotes **Customization.settings** na pasta **BuildTools**, adicione a seguinte linha para incluir a extensão de exemplo atual de CRT em pacotes implantáveis.

    ``` xml
    <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.Runtime.DocumentProvider.CleanCashSample.dll" />
    ```

#### <a name="update-hardware-station"></a>Atualizar estação de hardware

1. Remova a extensão da estação de hardware anterior modificando o arquivo de configuração **HardwareStation.Extension.config**.

    # <a name="retail-73-and-earlier"></a>[Retail 7.3 e anterior](#tab/retail-7-3)

    Remova a seção a seguir dos arquivos de configuração **HardwareStation.Shared.config** e **HardwareStation.Dedicated.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-731-and-later"></a>[Retail 7.3.1 e posterior](#tab/retail-7-3-1)

    Remova a seção a seguir do arquivo de configuração **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample" />
    ```

    # <a name="retail-100-and-later"></a>[Retail 10.0 e posterior](#tab/retail-10-0)

    Remova a seção a seguir do arquivo de configuração **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.FiscalRegisterSample" />
    ```
    ---

2. Habilite e exemplo de extensão atual de estação de hardware adicionando a seguinte linha à seção **composição** no arquivo de configuração **HardwareStation.Extension.config**.

    ``` xml
    <add source="assembly" value="Contoso.Commerce.HardwareStation.CleanCashSample" />
    ```

3. Faça as alterações a seguir no arquivo de configuração de personalização de pacote **Customization.settings** na pasta **BuildTools**:

    - Remova a seguinte linha para excluir a extensão de estação de hardware anterior dos pacotes implantáveis.

        ``` xml
        <ISV_CommerceRuntime_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.Extension.FiscalRegisterSample.dll" />
        ```

    - Adicione as seguintes linhas para incluir o exemplo de extensão da estação de hardware atual nos pacotes implantáveis.

        ``` xml
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Contoso.Commerce.HardwareStation.CleanCashSample.dll" />
        <ISV_HardwareStation_CustomizableFile Include="$(SdkReferencesPath)\Interop.CleanCash_1_1.dll" />
        ```

#### <a name="update-modern-pos"></a>Atualizar PDV Moderno

1. Abra a solução **CloudPOS.sln** em **RetailSdk\\POS**.
2. Desabilitar a extensão de PDV anterior:

    - No arquivo **tsconfig.json**, adicione a pasta **FiscalRegisterSample** à lista de exclusões.
    - Remova as seguintes linhas do arquivo **extensions.json** na pasta **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Habilite o exemplo de extensão de PDV atual adicionando as seguintes linhas ao arquivo **extensions.json** na pasta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="update-cloud-pos"></a>Atualizar PDV em Nuvem

1. Abra a solução **ModernPOS.sln** em **RetailSdk\\POS**.
2. Desabilitar a extensão de PDV anterior:

    - No arquivo **tsconfig.json**, adicione a pasta **FiscalRegisterSample** à lista de exclusões.
    - Remova as seguintes linhas do arquivo **extensions.json** na pasta **RetailSDK\\POS\\Extensions**.

        ``` json
        {
            "baseUrl": "FiscalRegisterSample"
        }
        ```

3. Habilite o exemplo de extensão de PDV atual adicionando as seguintes linhas ao arquivo **extensions.json** na pasta **RetailSDK\\POS\\Extensions**.

    ``` json
    {
        "extensionPackages": [
            {
                "baseUrl": "Microsoft/AuditEvent.SE"
            }
        ]
    }
    ```

#### <a name="create-deployable-packages"></a>Criar pacotes implantáveis

Execute **msbuild** para o SDK do Retail completo para criar pacotes implantáveis. Aplique os pacotes via LCS ou manualmente. Para obter mais informações, consulte [Empacotamento do SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-packaging.md).
