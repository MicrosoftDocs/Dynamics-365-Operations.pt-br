---
title: Exemplo de integração da impressora fiscal para a Polônia
description: Este artigo fornece uma visão geral do exemplo de integração fiscal da Polônia no Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-2-1
ms.openlocfilehash: e71d7b342789e4cf2e7644a46bc847087063fc78
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8876940"
---
# <a name="fiscal-printer-integration-sample-for-poland"></a>Exemplo de integração da impressora fiscal para a Polônia

[!include[banner](../includes/banner.md)]

Este artigo fornece uma visão geral do exemplo de integração fiscal da Polônia no Microsoft Dynamics 365 Commerce.

A funcionalidade do Dynamics 365 Commerce para a Polônia inclui um exemplo de integração do ponto de venda (PDV) a uma impressora fiscal. O exemplo estende a [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e oferece suporte ao protocolo POSNET THERMAL HD 2.02 para impressoras fiscais da [Posnet Polska S.A.](https://www.posnet.com.pl) O exemplo permite a comunicação com uma impressora fiscal conectada por meio de uma porta COM usando um driver de software nativo. Ele foi implementado e testado usando um emulador de software que a Posnet forneceu para a impressora fiscal Posnet Thermal HD FV EJ. O exemplo é fornecido na forma de código-fonte e faz parte do kit de desenvolvimento de software (SDK) do Retail.

A Microsoft não disponibiliza nenhum hardware, software ou documentação da Posnet. Para obter informações sobre como obter a impressora fiscal e operá-la, entre em contato com a [Posnet Polska S.A.](https://www.posnet.com.pl)

## <a name="scenarios"></a>Cenários

Os cenários a seguir são abordados pelo exemplo de integração de impressora fiscal para a Polônia:

- Cenários de vendas:

    - Imprima um recibo fiscal para vendas e devoluções de cash-and-carry.
    - Capture uma resposta da impressora fiscal e armazene-a no banco de dados do canal.
    - Impostos:

        - Mapeie para os códigos de imposto da impressora fiscal (departamentos).
        - Transfira dados de imposto mapeados para a impressora fiscal.

    - Pagamentos:

        - Mapeie para os métodos de pagamento da impressora fiscal.
        - Imprima pagamentos em um recibo fiscal.
        - Imprimir informações de alterações.

    - Imprimir descontos de linha.
    - Cartões-presente:

        - Exclua uma linha de cartão-presente emitida/recarregada de um recibo fiscal para uma venda.
        - Imprima um pagamento que usa um cartão-presente como um método de pagamento regular.

    - Imprima recibos fiscais para operações de pedidos de clientes:

        - Um recibo fiscal não é impresso para o depósito do pedido de um cliente.
        - Imprima um recibo fiscal para linhas de execução do pedido híbrido de um cliente.
        - Imprima um recibo fiscal para a operação de retirada do pedido de um cliente.
        - Imprima um recibo fiscal de um pedido de devolução.

    - Imprimir as [informações do cliente](emea-pol-customer-information.md) especificadas para uma transação de venda em um recibo fiscal. Um exemplo dessas informações é o número do IVA.

- Demonstrativos de fechamento de dia (relatórios fiscais X e Z).
- Manipulação de erros, como as seguintes opções:

    - Repita o registro fiscal se houver uma nova tentativa, como se a impressora fiscal não está conectada, não está pronta ou não está respondendo, a impressora está sem papel ou há uma obstrução de papel.
    - Adie o registro fiscal.
    - Ignore o registro fiscal ou marque a transação como registrada e inclua códigos informativos para capturar o motivo da falha e informações adicionais.
    - Verifique a disponibilidade da impressora fiscal antes que uma nova transação de venda seja aberta ou que uma transação de venda seja finalizada.

### <a name="gift-cards"></a>Cartões-presente

O exemplo de integração da impressora fiscal implementa as seguintes regras relacionadas a cartões-presente:

- Exclua as linhas de venda relacionadas às operações *Emitir cartão-presente* e *Adicionar ao cartão-presente* do recibo fiscal.
- Não imprima um recibo fiscal se ele consistir somente em linhas de cartão-presente.
- Deduza o valor total de cartões-presente que são emitidos ou recarregados em uma transação das linhas de pagamento do recibo fiscal.
- Salve os ajustes calculados das linhas de pagamento no banco de dados de canal com uma referência a uma transação fiscal correspondente.
- O pagamento por cartão-presente é considerado um pagamento regular.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depósitos de cliente e de ordem de cliente

O exemplo de integração da impressora fiscal implementa as seguintes regras relacionadas a depósitos de cliente e depósitos de ordem de cliente:

- Não imprima um recibo fiscal se uma transação for um depósito de cliente.
- Não imprima um recibo fiscal se uma transação tiver somente um depósito de ordem de cliente ou um reembolso de depósito de ordem de cliente.
- Imprima o valor do depósito pago anteriormente em um recibo fiscal para uma operação de retirada do pedido do cliente.
- Deduzir o valor do depósito de ordem de cliente das linhas de pagamento quando uma ordem híbrida de cliente for criada.
- Salve os ajustes calculados das linhas de pagamento no banco de dados de canal com uma referência a uma transação fiscal para uma ordem híbrida de cliente.

### <a name="limitations-of-the-sample"></a>Limitações do exemplo

- A impressora fiscal oferece suporte somente a cenários nos quais o imposto está incluído no preço. Portanto, a opção **Preço inclui imposto** deve estar definida como **Sim** para lojas e clientes.
- Os relatórios diários (fiscal X e fiscal Z) são impressos usando o formato de *Relatório de turno* incorporado.
- A impressão de um código de barras em recibos fiscais é considerada uma personalização potencial, porque não há suporte para esse recurso nos formatos incorporados e só pode ser implementado usando o relatório **Superformato** personalizável.
- A impressora fiscal não oferece suporte a transações mistas. A opção **Proibir a mistura de vendas e devoluções em um único recibo** deve ser definida como **Sim** nos perfis de funcionalidade de PDV.

## <a name="set-up-fiscal-integration-for-poland"></a>Configurar integração fiscal para a Polônia

O exemplo de integração da impressora fiscal da Polônia é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Posnet** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do Commerce Runtime (CRT) e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma máquina virtual (VM) do desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal para a Polônia (herdado)](emea-pol-fpi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

Conclua as etapas de integração fiscal conforme descritas em [Configurar a integração da fiscal para os canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Além disso, anote as configurações do processo de registro fiscal [específicas a este exemplo de integração da impressora fiscal](#set-up-the-registration-process).
1. [Definir configurações de tratamento de erros](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configurar relatórios fiscais X/Z a partir do PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar os componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurar o processo de registro fiscal

Para habilitar o processo de registro, siga estas etapas para configurar o Commerce headquarters. Para obter mais informações, consulte [Configurar a integração fiscal dos canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Baixe arquivos de configuração para o provedor de documentos fiscais e o conector fiscal:

    1. Abra o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo (por exemplo, **[versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> Posnet**.
    1. Faça download do arquivo de configuração do provedor de documentos fiscais em **CommerceRuntime \> DocumentProvider.PosnetSample \> Configuration \> DocumentProviderPosnetSample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/CommerceRuntime/DocumentProvider.PosnetSample/Configuration/DocumentProviderPosnetSample.xml)).
    1. Faça download do arquivo de configuração do conector fiscal em **HardwareStation \> ThermalDeviceSample \> Configuration \> ConnectorPosnetThermalFVEJ.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Posnet/HardwareStation/ThermalDeviceSample/Configuration/ConnectorPosnetThermalFVEJ.xml)).

    > [!WARNING]
    > Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Os arquivos de configuração deste exemplo de integração fiscal estão localizados nas seguintes pastas do SDK do Retail em uma VM do desenvolvedor no LCS:
    >
    > - **Arquivo de configuração do provedor de documentos fiscais:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml
    > - **Arquivo de configuração do conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.Posnet.ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml
    > 
    > O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

1. Vá para **Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Parâmetros compartilhados com o comércio**. Na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
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

- **Mapeamento de taxas de imposto sobre valor agregado (IVA)** – O mapeamento de valores de porcentagem de imposto que são configurados para os códigos de impostos sobre vendas para a impressora fiscal-taxas de IVA específicas. Veja a seguir o mapeamento padrão:

    ```
    0 : 23.00 ; 1 : 8.00 ; 2 : 5.00 ; 3 : 0.00
    ```

    O primeiro componente em cada par representa um número de taxa de IVA configurado na impressora fiscal. O segundo componente representa a alíquota de IVA correspondente. Para obter mais informações sobre a configuração de taxa de IVA da impressora fiscal, consulte a documentação do driver POSNET.

- **Mapeamento de tipos de meio de pagamento** – O mapeamento das formas de pagamento configuradas para a loja para formas de pagamento compatíveis com a impressora fiscal. Veja a seguir o mapeamento padrão:

    ```
    0 : 0 ; 1 : 0 ; 2 : 2 ; 3 : 2 ; 4 : 0 ; 5 : 0 ; 6 : 0 ; 7 : 2 ; 8 : 0
    ```

    O primeiro componente em cada par representa uma forma de pagamento configurada para a loja. O segundo componente representa a forma de pagamento correspondente à qual a impressora fiscal oferece suporte. Para obter mais informações sobre as formas de pagamento compatíveis com a impressora fiscal, consulte a documentação do driver POSNET. Você deve modificar o mapeamento de exemplo de acordo com as formas de pagamento que são configuradas no seu aplicativo.

#### <a name="fiscal-connector-settings"></a>Configurações do conector fiscal

As configurações a seguir são incluídas na configuração do conector fiscal fornecida como parte do exemplo de integração fiscal:

- **Cadeia de conexão** – Uma cadeia de caracteres que descreve os detalhes da conexão com o dispositivo em um formato compatível com o driver. Para obter mais informações, consulte a documentação do driver POSNET.
- **Sincronização de data e hora** – Um valor que especifica se a data e a hora da impressora devem ser sincronizadas com a estação de hardware conectada.
- **Tempo limite do dispositivo** – O período, em milissegundos, que o driver aguardará por uma resposta do dispositivo. Para obter mais informações, consulte a documentação do driver POSNET.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal para a Polônia (herdado)](emea-pol-fpi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar o ambiente de desenvolvimento

Para configurar um ambiente de desenvolvimento para testar e ampliar o exemplo, siga estas etapas.

1. Clone ou baixe o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo. Para obter mais informações, consulte [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra a solução de integração da impressora fiscal em **Dynamics365Commerce.Solutions\\FiscalIntegration\\Posnet\\Posnet.sln** e crie-a.
1. Instale as extensões do CRT:

    1. Localize o instalador de extensão do CRT:

        - **Commerce Scale Unit:** Na pasta **Posnet\\ScaleUnit\\ScaleUnit.Posnet.Installer\\bin\\Debug\\net461**, encontre o instalador **ScaleUnit.Posnet.Installer**.
        - **CRT local no PDV Moderno:** Na pasta **Posnet\\ModernPOS\\ModernPOS.Posnet.Installer\\bin\\Debug\\net461**, encontre o instalador **ModernPOS.Posnet.Installer**.

    1. Inicie o instalador de extensão do CRT na linha de comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.Posnet.Installer.exe install --verbosity 0
            ```

        - **CRT local no PDV moderno:**

            ```Console
            ModernPOS.Posnet.Installer.exe install --verbosity 0
            ```

1. Instale as extensões da extensão de hardware:

    1. Na pasta **Posnet\\HardwareStation\\HardwareStation.PosnetThermalFVFiscalPrinter.Installer\\bin\\Debug\\net461**, encontre o instalador **HardwareStation.PosnetThermalFVFiscalPrinter.Installer**.
    1. Inicie o instalador de extensão na linha de comando:

        ```Console
        HardwareStation.PosnetThermalFVFiscalPrinter.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **Posnet build-pipeline.yml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração da impressora fiscal da Polônia é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Posnet** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Posnet)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do CRT e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal para a Polônia (herdado)](emea-pol-fpi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos da impressora e manipular respostas da impressora fiscal. Essa extensão gera um conjunto de comandos específicos da impressora no formato JSON (JavaScript Object Notation) definido pela especificação POSNET 19-3678.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **DocumentProviderPosnetProtocol** é o ponto de entrada para a solicitação gerar documentos da impressora fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico da impressora que deve ser registrado na impressora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, imprimir relatório X e imprimir relatório Z.

#### <a name="configuration"></a>Configuração

O arquivo de configuração do provedor de documentos fiscais está em **src\\FiscalIntegration\\Posnet\\CommerceRuntime\\DocumentProvider.PosnetSample\\Configuration\\DocumentProviderPosnetSample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do provedor de documentos fiscais a ser configurado no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a impressora fiscal. Essa extensão chama as funções do driver POSNET para enviar comandos que a extensão do CRT gera para a impressora fiscal. Ela também manipula erros de dispositivo.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **FiscalPrinterHandler** é o ponto de entrada para o manuseio da solicitação ao dispositivo periférico fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para impressoras e retorna a resposta da impressora fiscal.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade do dispositivo.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para a inicialização da impressora.

#### <a name="configuration"></a>Configuração

O arquivo de configuração do conector fiscal está em **src\\FiscalIntegration\\Posnet\\HardwareStation\\ThermalDeviceSample\\Configuration\\ConnectorPosnetThermalFVEJ.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas no Commerce headquarters. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
