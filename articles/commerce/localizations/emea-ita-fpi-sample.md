---
title: Exemplo de integração da impressora fiscal para a Itália
description: Este tópico fornece uma visão geral do exemplo de integração fiscal da Itália no Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 12/20/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2018-11-1
ms.openlocfilehash: 592cecff5b6179e7afd1bacb25beda277dfb8fa3
ms.sourcegitcommit: 0d2de52e12fdb9928556d37a4813a67b303695dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2021
ms.locfileid: "7944625"
---
# <a name="fiscal-printer-integration-sample-for-italy"></a>Exemplo de integração da impressora fiscal para a Itália

[!include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral do exemplo de integração fiscal da Itália no Microsoft Dynamics 365 Commerce.

A funcionalidade do Commerce da Itália inclui um exemplo de integração do ponto de venda (PDV) a uma impressora fiscal. O exemplo amplia a [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) para que funcione com [Epson Epson FP-90III Series](https://www.epson.it/products/sd/pos-printer/epson-fp-90iii-series) e permite a comunicação com uma impressora fiscal no modo de servidor Web por meio do serviço Web EpsonFPMate usando a API Fiscal ePOS-Print. O exemplo oferece suporte apenas ao modo Registratore Telematico (RT). O exemplo é fornecido na forma de código-fonte e faz parte do kit de desenvolvimento de software (SDK) do Retail.

A Microsoft não disponibiliza nenhum hardware, software ou documentação da Epson. Para obter informações sobre como obter a impressora fiscal e operá-la, entre em contato com a [Epson Italia S.p.A](https://www.epson.it).

## <a name="scenarios"></a>Cenários

Os cenários a seguir são abordados pelo exemplo de integração de impressora fiscal da Itália:

- Cenários de vendas:

    - Imprima um recibo fiscal para vendas e devoluções de cash-and-carry.
    - Capture uma resposta da impressora fiscal e armazene-a no banco de dados do canal.
    - Impostos:

        - Mapeie para os códigos de imposto da impressora fiscal (departamentos).
        - Transfira dados de imposto mapeados para a impressora fiscal.
        - Imprimir impostos em um recibo fiscal.

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
        - Imprimir um recibo fiscal para linhas de execução de uma ordem híbrida de cliente.
        - Imprima um recibo fiscal para a operação de retirada do pedido de um cliente.
        - Imprima um recibo fiscal de um pedido de devolução.

    - Imprimir um código de barras para o número do recibo em um recibo fiscal.
    - Imprimir as [informações do cliente](emea-ita-customer-information.md) especificadas para uma transação de venda em um recibo fiscal. Um exemplo dessas informações é o código da loteria do cliente. 

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
- Os relatórios diários (fiscal X e fiscal Z) são impressos usando o formato inseridos no firmware da impressora fiscal.
- A impressora fiscal não oferece suporte a transações mistas. A opção **Proibir a mistura de vendas e devoluções em um único recibo** deve ser definida como **Sim** nos perfis de funcionalidade de PDV.
- O exemplo oferece suporte à integração somente a uma impressora fiscal que esteja funcionando no modo Registratore Telematico (RT)).

## <a name="set-up-fiscal-integration-for-italy"></a>Configurar integração fiscal da Itália

O exemplo de integração da impressora fiscal da Itália é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\EpsonFP90IIISample** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) em um provedor de documentos fiscais, que é uma extensão do Commerce Runtime (CRT) e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma máquina virtual (VM) do desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal da Itália (herdado)](emea-ita-fpi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

Conclua as etapas de integração fiscal conforme descritas em [Configurar a integração da fiscal para os canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md).

1. [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Além disso, anote as configurações do processo de registro fiscal [específicas a este exemplo de integração da impressora fiscal](#set-up-the-registration-process).
1. [Configurar textos fiscais para descontos](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-texts-for-discounts).
1. [Definir configurações de tratamento de erros](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Configurar relatórios fiscais X/Z a partir do PDV](setting-up-fiscal-integration-for-retail-channel.md#set-up-fiscal-xz-reports-from-the-pos).
1. [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar a funcionalidade para gerenciamento de informações do cliente no PDV](emea-ita-customer-information.md#setup).
1. [Configurar os componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurar o processo de registro fiscal

Para habilitar o processo de registro, siga estas etapas para configurar a sede do Commerce. Para obter mais informações, consulte [Configurar a integração fiscal dos canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Baixe arquivos de configuração para o provedor de documentos fiscais e o conector fiscal:

    1. Abra o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo (por exemplo, **[versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> EpsonFP90IIISample**.
    1. Baixe o arquivo de configuração do provedor de documentos fiscais em **CommerceRuntime \> DocumentProvider.EpsonFP90IIISample \> Configuration \> DocumentProviderEpsonFP90IIISample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/CommerceRuntime/DocumentProvider.EpsonFP90IIISample/Configuration/DocumentProviderEpsonFP90IIISample.xml)).
    1. Baixe o arquivo de configuração do conector fiscal em **HardwareStation \> EpsonFP90IIIFiscalDeviceSample \> Configuration \> ConnectorEpsonFP90IIISample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/EpsonFP90IIISample/HardwareStation/EpsonFP90IIIFiscalDeviceSample/Configuration/ConnectorEpsonFP90IIISample.xml).

    > [!WARNING]
    > Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Os arquivos de configuração deste exemplo de integração fiscal estão localizados nas seguintes pastas do SDK do Retail em uma VM do desenvolvedor no LCS:
    >
    > - **Arquivo de configuração do provedor de documentos fiscais:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extension.DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml
    > - **Arquivo de configuração do conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml
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

- **Mapeamento de tipos de meio de pagamento** – O mapeamento das formas de pagamento configuradas para a loja para tipos de pagamento compatíveis com a impressora fiscal. O exemplo a seguir mostra o mapeamento padrão.

    ```JSON
    {"PaymentMethods": [
        {"StorePaymentMethod":"1", "PrinterPaymentType":"0", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"3", "PrinterPaymentType":"2", "PrinterPaymentIndex":"00"},
        {"StorePaymentMethod":"4", "PrinterPaymentType":"2", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"6", "PrinterPaymentType":"0", "PrinterPaymentIndex":"01"},
        {"StorePaymentMethod":"8", "PrinterPaymentType":"6", "PrinterPaymentIndex":"01"}
        ],
        "DepositPaymentMethod": {"PrinterPaymentType":"2", "PrinterPaymentIndex":"00"}}
    ```

    Aqui está uma explicação dos atributos neste mapeamento:

    - **StorePaymentMethod** é uma forma de pagamento configurada para a loja em **Retail e Commerce \> Configuração de canal \> Formas de pagamento \> Formas de pagamento**.
    - **PrinterPaymentType** e **PrinterPaymentIndex** são o índice e os tipos de pagamento correspondentes definidos na documentação da impressora fiscal Epson.
    - **DepositPaymentMethod** é usado para especificar o tipo de pagamento e o índice de uma impressora para a parte do valor de retirada da ordem do cliente que é liquidado com o depósito da ordem do cliente.

    A tabela a seguir mostra como o mapeamento de exemplo das formas de pagamento corresponde às formas de pagamento da loja configuradas nos dados de demonstração padrão.

    | Forma de pagamento | Nome do método de pagamento |
    |----------------|---------------------|
    | 1              | Pagamento à vista                |
    | 3              | Cartão                |
    | 4              | Conta do cliente    |
    | 6              | Moeda            |
    | 8              | Cartão-presente           |

    Você deve modificar o mapeamento de exemplo de acordo com as formas de pagamento que são configuradas no seu aplicativo.

- **Tipo de código de barra para número do recibo** – O tipo de código de barras usado para mostrar um número de recibo em um recibo fiscal. O mapeamento padrão é **CODE128**.
- **Imprimir dados fiscais no cabeçalho do recibo** – Se este parâmetro estiver ativado, as informações da loja serão impressas no recibo fiscal. Essas informações incluem o nome da loja, o endereço e o número de identificação do imposto e o nome do caixa.
- **Mapeamento de departamentos da impressora fiscal** – O mapeamento de departamentos da impressora fiscal para imposto sobre valor agregado (IVA), natureza de isenção de IVA e tipos de produtos. O exemplo a seguir mostra o mapeamento padrão.

    ```JSON
    {"Departments": [
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"01"},
        {"VATRate":"2200", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"02"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"03"},
        {"VATRate":"1000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"04"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"05"},
        {"VATRate":"0500", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"06"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"07"},
        {"VATRate":"0400", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"08"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"0", "DepartmentNumber":"09"},
        {"VATRate":"0000", "VATExemptNature":"", "ProductType":"1", "DepartmentNumber":"10"},
        {"VATRate":"0000", "VATExemptNature":"NS", "ProductType":"0", "DepartmentNumber":"99"}]}
    ```

    Aqui está uma explicação dos atributos neste mapeamento:

    - **VATRate** é uma taxa de IVA com suporte configurada como um código de imposto. O valor no mapeamento tem duas casas decimais, mas nenhum separador decimal. Por exemplo, **2200** representa 22%, e **1000** representa 10%.
    - **VATExemptNature** é aplicável somente nos casos em que a taxa de IVA é 0 (zero), incluindo casos em que não há imposto. No momento, **VATExemptNature** só tem suporte para cartões-presente, e o valor no mapeamento deve corresponder ao valor da propriedade **VATExemptNatureForGiftCard** no arquivo de configuração XML.
    - **ProductType** é o tipo de produto. Um valor igual a **0** representa mercadorias, e um valor igual a **1** representa serviços.
    - **DepartmentNumber** é o número do departamento que é configurado na impressora e que corresponde aos três atributos anteriores.

    Você deve modificar o mapeamento de exemplo de acordo com as taxas de IVA configuradas no seu aplicativo e os departamentos correspondentes configurados na impressora fiscal.

- **Natureza de isenção de IVA para cartão-presente** – A natureza de isenção de IVA que deve ser aplicada quando um cartão-presente é emitido ou recarregado. O valor deve corresponder a alguma entrada no mapeamento de departamentos da impressora fiscal. O mapeamento padrão é **NS**.
- **Habilitar itens gratuitos** – Se este parâmetro for ativado, o tipo de ajuste de desconto especial *omaggio* para itens com desconto de 100% será habilitado.
- **Código informativo para origem de devolução** – O código informativo usado para capturar a origem de uma transação de devolução se nenhum recibo de venda original for fornecido. Esse parâmetro é usado juntamente com os parâmetros **Código informativo para data de venda original** e **Mapeamento de origens de devolução** para gerar uma mensagem correta no recibo fiscal sobre a origem de uma transação de devolução se nenhuma transação de venda original existir. 

    Esse código informativo deve ser configurado para permitir que o usuário selecione ou insira uma das possíveis origens de devoluções em suas lojas. Por exemplo, ele pode ser configurado como uma lista de subcódigos (como **Devolução do site** ou **Devolução do quiosque**). O parâmetro **Mapeamento de origens de devolução** é usado para converter o valor do código informativo em um comando da impressora fiscal.

    O código informativo selecionado para **Código informativo para origem de devolução** deve ser configurado como um código informativo obrigatório que é acionado uma vez por transação de venda. Ele deve ser atribuído como o código informativo **Devolver produto** no perfil de funcionalidade de PDV, de forma que ele seja acionado quando a operação **Devolver produto** for executada.

    Nenhum valor padrão é especificado para esse mapeamento. Você deve selecionar um código informativo configurado no seu aplicativo.

- **Código informativo para data de venda original** – O código informativo usado para capturar a data de venda original de uma transação de devolução se nenhum recibo de venda original for fornecido. Esse parâmetro é usado juntamente com os parâmetros **Código informativo para origem de devolução** e **Mapeamento de origens de devolução** para gerar uma mensagem correta no recibo fiscal sobre a origem de uma transação de devolução se nenhuma transação de venda original existir.

    O código informativo deve ser configurado para que o campo **Tipo de entrada** seja definido como **Data**. Ele deve ser configurado como um código informativo obrigatório que é acionado uma vez por transação de venda. Ele também deve ser atribuído como o **Código informativo vinculado** para o código informativo selecionado para o parâmetro **Informações para origem de devolução**, para que os dois códigos informativos sejam acionados um após o outro.

    Nenhum valor padrão é especificado para esse mapeamento. Você deve selecionar um código informativo configurado no seu aplicativo.

- **Mapeamento de origens de devolução** – O mapeamento de origens de devolução usado para imprimir a origem de uma transação de devolução se nenhum recibo de venda original for fornecido. Esse parâmetro é usado juntamente com os parâmetros **Código informativo para origem de devolução** e **Código informativo para data de venda original** para gerar uma mensagem correta no recibo fiscal sobre a origem de uma transação de devolução se nenhuma transação de venda original existir. O exemplo a seguir mostra o mapeamento padrão.

    ```JSON
    {"ReturnOrigins": [
        {"ReturnOrigin":"1", "PrinterReturnOrigin":"POS"},
        {"ReturnOrigin":"2", "PrinterReturnOrigin":"ND"}
        ],
        "PrinterReturnOriginWithoutFiscalData":"POS"}
    ```

    Aqui está uma explicação dos atributos neste mapeamento:

    - **ReturnOrigin** é uma das possíveis origens de devoluções em suas lojas. O valor deve corresponder a um valor do parâmetro **Código informativo para origem de devolução**.
    - **PrinterReturnOrigin** é uma das origens de devolução aceitas pela impressora fiscal (**PDV**, **VR** ou **ND**).
    - **PrinterReturnOriginWithoutFiscalData** é a origem de devolução que a impressora fiscal aceita e que corresponde a uma transação de devolução vinculada a uma transação de venda original que não tem dados fiscais vinculados, pois não foi registrada por meio de uma impressora fiscal. Nesse caso, a data de venda original é identificada como a data da transação de venda original.

Os seguintes mapeamentos de dados padrão são obsoletos e são mantidos somente para compatibilidade com versões anteriores:

- Mapeamento de códigos de imposto sobre valor agregado (IVA)
- Tipo de pagamento de depósito

#### <a name="fiscal-connector-settings"></a>Configurações do conector fiscal

As configurações a seguir são incluídas na configuração do conector fiscal fornecida como parte do exemplo de integração fiscal:

- **Endereço do ponto de extremidade** – A URL da impressora.
- **Sincronização de data e hora** – Um valor que especifica se a data e a hora da impressora devem ser sincronizadas com a estação de hardware conectada.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal da Itália (herdado)](emea-ita-fpi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar o ambiente de desenvolvimento

Para configurar um ambiente de desenvolvimento para testar e ampliar o exemplo, siga estas etapas.

1. Clone ou baixe o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo. Para obter mais informações, consulte [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra a solução de integração da impressora fiscal em **Dynamics365Commerce.Solutions\\FiscalIntegration\\EpsonFP90IIISample\\EpsonFP90IIISample.sln** e crie-a.
1. Instale as extensões do CRT:

    1. Localize o instalador de extensão do CRT:

        - **Commerce Scale Unit:** na pasta **EpsonFP90IIISample\\ScaleUnit\\ScaleUnit.EpsonFP90III.Installer\\bin\\Debug\\net461**, encontre o instalador **ScaleUnit.EpsonFP90III.Installer**.
        - **CRT local no PDV moderno:** na pasta **EpsonFP90IIISample\\ModernPOS\\ModernPOS.EpsonFP90III.Installer\\bin\\Debug\\net461**, encontre o instalador **ModernPOS.EpsonFP90III.Installer**.

    1. Inicie o instalador de extensão do CRT na linha de comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EpsonFP90III.Installer.exe install --verbosity 0
            ```

        - **CRT local no PDV moderno:**

            ```Console
            ModernPOS.EpsonFP90III.Installer.exe install --verbosity 0
            ```

1. Instale as extensões da extensão de hardware:

    1. Na pasta **EpsonFP90IIISample\\HardwareStation\\HardwareStation.EpsonFP90III.Installer\\bin\\Debug\\net461**, encontre o instalador **HardwareStation.EpsonFP90III.Installer**.
    1. Inicie o instalador de extensão na linha de comando:

        ```Console
        HardwareStation.EpsonFP90III.Installer.exe install --verbosity 0
        ```

#### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **EpsonFP90III build-pipeline.yml.yml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração da impressora fiscal da Itália é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\EpsonFP90IIISample** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/EpsonFP90IIISample)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices) em um provedor de documentos fiscais, que é uma extensão do CRT e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração da impressora fiscal da Itália (herdado)](emea-ita-fpi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos da impressora e manipular respostas da impressora fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **DocumentProviderEpsonFP90III** é o ponto de entrada para a solicitação gerar documentos da impressora fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico da impressora que deve ser registrado na impressora fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, imprimir relatório X e imprimir relatório Z.

#### <a name="configuration"></a>Configuração

O arquivo de configuração para o provedor de documentos fiscais está em **src\\FiscalIntegration\\EpsonFP90IIISample\\CommerceRuntime\\DocumentProvider.EpsonFP90IIISample\\Configuration\\DocumentProviderEpsonFP90IIISample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações para que o provedor de documentos seja configurado na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com a impressora fiscal. Essa extensão usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para a impressora fiscal. Ele também manipula as respostas recebidas da impressora fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **EpsonFP90IIISample** é o ponto de entrada para o manuseio da solicitação ao dispositivo periférico fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para impressoras e retorna a resposta da impressora fiscal.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação de integridade do dispositivo.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para a inicialização da impressora.

#### <a name="configuration"></a>Configuração

O arquivo de configuração para o conector fiscal está em **src\\FiscalIntegration\\EpsonFP90IIISample\\HardwareStation\\EpsonFP90IIIFiscalDeviceSample\\Configuration\\ConnectorEpsonFP90IIISample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações para que o conector seja configurado na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
