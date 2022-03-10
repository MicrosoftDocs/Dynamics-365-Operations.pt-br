---
title: Exemplo de integração da unidade de controle para a Suécia
description: Este tópico fornece uma visão geral do exemplo de integração fiscal da Suécia no Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-10-08
ms.openlocfilehash: ace1bd5b1a06317b6753a34779ecfa96e519a63e
ms.sourcegitcommit: 5cefe7d2a71c6f220190afc3293e33e2b9119685
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2022
ms.locfileid: "8077004"
---
# <a name="control-unit-integration-sample-for-sweden"></a>Exemplo de integração da unidade de controle para a Suécia

[!include [banner](../includes/banner.md)]

Este tópico fornece uma visão geral do exemplo de integração fiscal da Suécia no Microsoft Dynamics 365 Commerce.

> [!NOTE]
> Este exemplo de funcionalidade de integração fiscal substitui o [exemplo anterior de integração do PDV com unidades de controle da Suécia ](retail-sdk-control-unit-sample.md). O exemplo anterior não se beneficia da [estrutura de integração fiscal](./fiscal-integration-for-retail-channel.md) e ficará obsoleto em atualizações posteriores. Para obter informações sobre como migrar do exemplo anterior para o que corresponde ao Dynamics 365 Commerce versão **10.0.22 e anterior**, consulte [Migrar do exemplo de integração anterior](emea-swe-fi-sample-sdk.md#migrating-from-the-earlier-integration-sample).

A funcionalidade do Commerce da Suécia inclui um exemplo de integração do ponto de venda (PDV) com dispositivos fiscais específicos da Suécia conhecidos como *unidades de controle*. Este exemplo amplia a [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md). Supõe-se que uma unidade de controle está fisicamente conectada a uma estação de hardware com a qual o PDV está emparelhado. Este exemplo usa a interface de programação de aplicativo (API) da unidade de controle [CleanCash Type A](https://www.retailinnovation.se/produkter) do Retail Innovation HTT AB. A versão 1.1.4 da API CleanCash é usada.

O exemplo é fornecido na forma de código-fonte e faz parte do kit de desenvolvimento de software (SDK) do Retail.

A Microsoft não disponibiliza nenhum hardware, software ou documentação do Retail Innovation HTT AB. Para obter informações sobre como obter a unidade de controle e operá-la, entre em contato com o [Retail Innovation HTT AB](https://www.retailinnovation.se/).

## <a name="scenarios"></a>Cenários

O exemplo de integração da unidade de controle da Suécia inclui os seguintes recursos:

- As cópias de vendas, devoluções e recibos são automaticamente registradas em uma unidade de controle conectada à estação de hardware emparelhada com o PDV.
- O código de controle e o número de fabricação da unidade de controle de uma transação registrada são capturados a partir da unidade de controle e salvos na transação. Esses dados também são chamados de *resposta fiscal*. A resposta fiscal pode ser exibida na página **Transações de armazenamento**.
- Os campos personalizados do código de controle e o número de fabricação da unidade de controle podem ser adicionados a um layout de recibo. Desse modo, você pode imprimir a resposta fiscal de uma transação em um recibo.
- A resposta fiscal de uma transação é mostrada no relatório do canal **Diário eletrônico (Suécia)**.
- Há várias opções de manipulação de erros disponíveis. Veja alguns exemplos:

    - Repita o registro fiscal, caso seja possível tentar novamente. Você pode repetir o registro fiscal se, por exemplo, a unidade de controle não estiver conectada, não estiver pronta ou não estiver respondendo.
    - Adiar o registro fiscal.
    - Ignore o registro fiscal ou marque a transação como registrada e inclua códigos informativos para capturar o motivo da falha e informações adicionais.
    - Verifique a disponibilidade da unidade de controle antes que uma nova transação de venda seja aberta ou que uma transação de venda seja finalizada.

### <a name="limitations-of-the-sample"></a>Limitações do exemplo

No momento, o exemplo de integração da unidade de controle para a Suécia não oferece suporte a cenários de pedidos de clientes.

## <a name="setting-up-the-integration-with-control-units"></a>Configurar a integração com unidades de controle

Para obter mais informações sobre a configuração necessária para a Suécia, consulte [Configurar o Commerce para a Suécia](./emea-swe-cash-registers.md#setting-up-commerce-for-sweden).

### <a name="configuring-swedenspecific-receipts"></a>Configurar recibos específicos da Suécia

#### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Você pode configurar o texto do idioma e os campos personalizados usados nos formatos de recibo do PDV. A empresa padrão do usuário que cria a configuração de recibo deve ser a mesma entidade legal na qual a configuração de texto do idioma foi criada. Como alternativa, os textos do mesmo idioma devem ser criados na empresa padrão do usuário e na entidade legal da loja para a qual a configuração foi criada.

Na página **Texto do idioma**, adicione os seguintes registros para os rótulos dos campos personalizados nos layouts de recibo. Os valores **ID de idioma**, **ID do texto** e **Texto** mostrados na tabela são apenas exemplos. Você pode alterá-los para atender aos seus requisitos. No entanto, os valores de **ID do texto** usados devem ser exclusivos e iguais ou maiores que 900001.

Adicione os seguintes rótulos de PDV à seção **PDV** da página **Texto do idioma**.

| ID do Idioma | ID do texto | Texto                  |
|-------------|---------|-----------------------|
| pt-BR       | 900001  | Código de controle do registro |
| pt-BR       | 900002  | Registrar dispositivo       |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**.

| Nome                         | Tipo    | ID do texto da legenda |
|------------------------------|---------|-----------------|
| SE_FISCALREGISTERCONTROLCODE | Recebimento | 900001          |
| SE_FISCALREGISTERID          | Recebimento | 900002          |

> [!NOTE]
> É importante que você especifique os nomes de campos personalizados corretos, conforme listados na tabela acima. Um nome de campo personalizado incorreto causará a falta de dados em recibos.

#### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No designer de formato de recibo, adicione os seguintes campos personalizados à seção **Rodapé**. Os nomes de campo correspondem aos textos do idioma que você definiu na seção anterior deste tópico.

- **Código de controle do registro** – Este campo imprime o código de controle.
- **Registrar dispositivo** – Este campo imprime o número de fabricação da unidade de controle.

Para obter mais informações sobre como trabalhar com formatos de recibo, consulte [Modelos de recibo e impressão](../receipt-templates-printing.md).

### <a name="set-up-fiscal-integration-for-sweden"></a>Configurar integração fiscal para a Suécia

O exemplo de integração da unidade de controle da Suécia se baseia na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\CleanCash** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do Commerce Runtime (CRT) e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma máquina virtual (VM) do desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação do exemplo de integração da unidade de controle da Suécia (herdado)](emea-swe-fi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

Conclua as etapas de integração fiscal conforme descritas em [Configurar a integração da fiscal para os canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Além disso, anote as configurações do processo de registro fiscal [específicas a este exemplo de integração da unidade de controle](#set-up-the-registration-process).
1. [Definir configurações de tratamento de erros](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar os componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurar o processo de registro fiscal

Para habilitar o processo de registro, siga estas etapas para configurar a sede do Commerce. Para obter mais informações, consulte [Configurar a integração fiscal dos canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Baixe arquivos de configuração para o provedor de documentos fiscais e o conector fiscal:

    1. Abra o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo (por exemplo, **[versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> CleanCash**.
    1. Faça download do arquivo de configuração do provedor de documentos fiscais em **CommerceRuntime \> DocumentProvider.CleanCashSample \> Configuration \> DocumentProviderFiscalCleanCashSample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/CommerceRuntime/DocumentProvider.CleanCashSample/Configuration/DocumentProviderFiscalCleanCashSample.xml)).
    1. Faça download do arquivo de configuração do conector fiscal em **HardwareStation \> Connector.CleanCashSample \> Configuration \> ConnectorCleanCashSample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/CleanCash/HardwareStation/Connector.CleanCashSample/Configuration/ConnectorCleanCashSample.xml)).

    > [!WARNING]
    > Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Os arquivos de configuração deste exemplo de integração fiscal estão localizados nas seguintes pastas do SDK do Retail em uma VM do desenvolvedor no LCS:
    >
    > - **Arquivo de configuração do provedor de documentos fiscais:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml
    > - **Arquivo de configuração do conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml
    > 
    > O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados com o comércio**. Na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Provedores de documentos fiscais** e carregue o arquivo do provedor de documentos fiscais baixado anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Conectores fiscais** e carregue o arquivo de configuração do conector fiscal baixado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis funcionais do conector**. Crie um novo perfil funcional do conector. Selecione o provedor de documentos e o conector carregados anteriormente. Atualize as [configurações de mapeamento de dados](#default-data-mapping) conforme necessário.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**. Crie um novo perfil técnico do conector e selecione o conector fiscal carregado anteriormente. Atualize as [configurações do conector](#fiscal-connector-settings) conforme necessário.
6. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Grupos de conectores fiscais**. Crie um novo grupo do conector fiscal para o perfil funcional do conector criado anteriormente.
7. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**. Crie um novo processo de registro fiscal e uma etapa do processo de registro fiscal e selecione o grupo do conector fiscal criado anteriormente.
8. Acesse **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. Selecione um perfil de funcionalidade vinculado à loja em que o processo de registro deve ser ativado. Na guia rápida **Processo de registro fiscal**, selecione o processo de registro fiscal criado anteriormente.
9. Acesse **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de hardware**. Selecione um perfil de hardware vinculado à estação de hardware à qual a impressora fiscal será conectada. Na guia rápida **Periféricos fiscais**, selecione o perfil técnico do conector criado anteriormente.
10. Abra a agenda de distribuição (**Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**), e selecione os trabalhos **1070** e **1090** para transferir dados ao banco de dados de canal.

#### <a name="default-data-mapping"></a>Mapeamento de dados padrão

O mapeamento de dados padrão a seguir é incluído na configuração do provedor de documentos fiscais fornecida como parte do exemplo de integração fiscal:

- **Mapeamento de código de imposto sobre valor agregado (IVA)** – Este mapeamento define os códigos de imposto sobre valor agregado específicos de dispositivos para os códigos de imposto sobre vendas correspondentes. O mapeamento de código de IVA deve ter o seguinte formato:

    ```
    1 : code1 ; 2 : code2
    ```

    Aqui está uma explicação deste formato:

    - *1* e *2* são códigos de IVA específicos de dispositivos.
    - Ponto e vírgula (;) será usado como separador.
    - *code1* e *code2* são códigos de impostos sobre vendas configurados no Commerce Headquarters. Você deve modificar o mapeamento de exemplo de acordo com os códigos de imposto que são configurados no seu aplicativo.

    As unidades de controle dão suporte a até quatro códigos de IVA diferentes. Portanto, o mapeamento de código de IVA pode ser configurado da seguinte maneira:

    ```
    1 : code1 ; 2 : code2 ; 3 : code3 ; 4 : code4
    ```

    > [!NOTE]
    > Vários códigos de impostos sobre vendas podem ser mapeados para o mesmo código de IVA específico de dispositivos.

#### <a name="fiscal-connector-settings"></a>Configurações do conector fiscal

As configurações a seguir são incluídas na configuração do conector fiscal fornecida como parte do exemplo de integração fiscal:

- **Cadeia de conexões** – As configurações de conexão da unidade de controle.
- **Tempo limite** – O período, em milissegundos, que o driver aguardará por uma resposta da unidade de controle.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação do exemplo de integração da unidade de controle da Suécia (herdado)](emea-swe-fi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar o ambiente de desenvolvimento

Para configurar um ambiente de desenvolvimento para testar e ampliar o exemplo, siga estas etapas.

1. Clone ou baixe o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo. Para obter mais informações, consulte [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra a solução de integração da unidade de controle em **Dynamics365Commerce.Solutions\\FiscalIntegration\\CleanCash\\CleanCash.sln** e crie-a.
1. Instale as extensões do CRT:

    1. Localize o instalador de extensão do CRT:

        - **Commerce Scale Unit:** Na pasta **CleanCash\\ScaleUnit\\ScaleUnit.CleanCash.Installer\\bin\\Debug\\net461**, encontre o instalador **ScaleUnit.CleanCash.Installer**.
        - **CRT local no PDV Moderno:** Na pasta **CleanCash\\ModernPOS\\ModernPOS.CleanCash.Installer\\bin\\Debug\\net461**, encontre o instalador **ModernPOS.CleanCash.Installer**.

    2. Inicie o instalador de extensão do CRT na linha de comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.CleanCash.Installer.exe install --verbosity 0
            ```

        - **CRT local no PDV moderno:**

            ```Console
            ModernPOS.CleanCash.Installer.exe install --verbosity 0
            ```

1. Instale as extensões da extensão de hardware:

    1. Na pasta **CleanCash\\HardwareStation\\HardwareStation.CleanCash.Installer\\bin\\Debug\\net461**, encontre o instalador **HardwareStation.CleanCash.Installer**.
    1. Inicie o instalador de extensão na linha de comando:

        ```Console
        HardwareStation.CleanCash.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **CleanCash build-pipeline.yml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-the-extensions"></a>Design das extensões

O exemplo de integração da unidade de controle da Suécia se baseia na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\CleanCash** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/CleanCash)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do CRT e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação do exemplo de integração da unidade de controle da Suécia (herdado)](emea-swe-fi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

### <a name="crt-extension-design"></a>Design de extensão do CRT

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos do serviço e manipular respostas da unidade de controle.

#### <a name="request-handler"></a>Manipulador de solicitações

Há um único manipulador de solicitações **DocumentProviderCleanCash** para o provedor de documentos. Esse manipulador é usado para gerar documentos fiscais para a unidade de controle.

Esse manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado na unidade de controle.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte a eventos de vendas e de auditoria.

#### <a name="configuration"></a>Configuração

O arquivo de configuração do provedor de documentos fiscais está em **src\\FiscalIntegration\\CleanCash\\CommerceRuntime\\DocumentProvider.CleanCashSample\\Configuration\\DocumentProviderFiscalCleanCashSample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade deste arquivo é habilitar as configurações para que o provedor de documentos seja configurado na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a unidade de controle. Ela usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para a unidade de controle. Ela também manipula as respostas recebidas da unidade de controle.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **CleanCashHandler** é o ponto de entrada para o manuseio de solicitações à unidade de controle.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para a unidade de controle e retorna uma resposta dela.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade da unidade de controle.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para inicializar a unidade de controle.

#### <a name="configuration"></a>Configuração

O arquivo de configuração para o conector fiscal está em **src\\FiscalIntegration\\CleanCash\\HardwareStation\\Connector.CleanCashSample\\Configuration\\ConnectorCleanCashSample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
