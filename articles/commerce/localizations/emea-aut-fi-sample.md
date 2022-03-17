---
title: Exemplo de integração de serviços de registro fiscal para a Áustria
description: Este tópico fornece uma visão geral do exemplo de integração fiscal da Áustria no Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-3-1
ms.openlocfilehash: b41ff8a112f801cd9bf5ebad3aed588ccb40e1f8
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388354"
---
# <a name="fiscal-registration-service-integration-sample-for-austria"></a>Exemplo de integração de serviços de registro fiscal para a Áustria

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Este tópico fornece uma visão geral do exemplo de integração fiscal da Áustria no Microsoft Dynamics 365 Commerce.

Para atender aos requisitos fiscais locais para caixas registradoras na Áustria, a funcionalidade do Dynamics 365 Retail da Áustria inclui um exemplo de integração do ponto de venda (PDV) com um serviço de registro fiscal externo. O exemplo amplia a [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md). Ele é baseado na solução [EFR (Registro fiscal eletrônico)](https://www.efsta.eu/at/fiskalloesungen/oesterreich) da [EFSTA](https://www.efsta.eu/at/) e permite a comunicação com o serviço de EFR por meio do protocolo HTTPS. O serviço de EFR deve ser hospedado na estação de hardware do Retail ou em uma máquina separada que pode ser conectada da estação de hardware. O exemplo é fornecido na forma de código-fonte e faz parte do kit de desenvolvimento de software (SDK) do Retail.

A Microsoft não disponibiliza nenhum hardware, software ou documentação da EFSTA. Para obter informações sobre como obter a solução de EFR e operá-la, entre em contato com a [EFSTA](https://www.efsta.eu/at/kontakt).

## <a name="scenarios"></a>Cenários

Os cenários a seguir são abordados pelo exemplo de integração do serviço de registro fiscal da Áustria:

- Registro de transações de pagamento à vista no serviço de registro fiscal:

    - Enviar os dados de transação detalhados para o serviço de registro fiscal. Esses dados incluem informações da linha de venda e informações sobre descontos, pagamentos e impostos.
    - Capturar uma resposta do serviço de registro fiscal. Essa resposta inclui uma assinatura digital e um link para a transação registrada.
    - Registrar os impostos e mapeá-los para os códigos de imposto do serviço de registro fiscal.
    - Imprimir o código QR para uma transação registrada no recibo.

- Registro de operações de cartões-presente e depósitos de clientes como transações não relacionadas a pagamentos à vista no serviço de registro fiscal:

    - Emitir ou adicionar dinheiro a um cartão-presente.
    - Registrar um depósito da conta de cliente.
    - Registrar um depósito de ordem de cliente.

- Registro de eventos e transações relacionadas a vendas como transações não relacionadas a pagamentos à vista no serviço de registro fiscal:

    - Abrir turno e Fechar turno
    - Valor inicial, Entrada variável e Remoção de forma de pagamento
    - Definição de preço manual
    - Substituição do imposto
    - Imprimir cópia do recibo
    - Abrir gaveta
    - Imprimir leitura X
    - Imprimir redução Z

- Imprimir demonstrativos de fechamento do dia (relatórios X/Z) que têm campos específicos da Áustria:

    - Número total de produtos ou serviços entregues aos clientes
    - Detalhamento de vendas por taxa de imposto
    - Detalhamento de pagamentos por caixa/operador de caixa registradora
    - Descontos e devoluções que reduzem as vendas diárias
    - Venda zero (brindes)

- Manipulação de erros, como as seguintes opções:

    - Repita o registro fiscal se houver uma nova tentativa, como se o serviço de registro fiscal não estiver disponível, não estiver pronto ou não estiver respondendo.
    - Adiar o registro fiscal.
    - Ignore o registro fiscal ou marque a transação como registrada e inclua códigos informativos para capturar o motivo da falha e informações adicionais.
    - Verifique a disponibilidade do serviço de registro fiscal antes que uma nova transação de venda seja aberta ou que uma transação de venda seja finalizada.

### <a name="gift-cards"></a>Cartões-presente

O exemplo de integração do serviço de registro fiscal implementa as seguintes regras relacionadas a cartões-presente:

- Exclua as linhas de venda relacionadas às operações *Emitir cartão-presente* e *Adicionar ao cartão-presente* de uma transação de pagamento à vista. Em vez de registrar essas linhas como parte de uma transação de pagamento à vista, registre-as como uma transação separada não relacionada a pagamentos à vista no serviço de registro fiscal.
- Não imprime um detalhamento de grupo de impostos e um código QR em um recibo se ele consistir somente em linhas de cartão-presente.
- Imprima o valor total de cartões-presente que são emitidos ou recarregados em uma transação separadamente do valor da transação de pagamento à vista no recebo.
- Salve os ajustes calculados das linhas de pagamento no banco de dados de canal com uma referência a uma transação fiscal correspondente.
- O pagamento por cartão-presente é considerado um pagamento regular.

### <a name="customer-deposits-and-customer-order-deposits"></a>Depósitos de cliente e de ordem de cliente

O exemplo de integração do serviço de registro fiscal implementa as seguintes regras relacionadas a depósitos de cliente e de ordem de cliente:

- Registre uma transação de não pagamento à vista se uma transação for um depósito de cliente.
- Registre uma transação de não pagamento à vista se uma transação tiver somente um depósito de ordem de cliente ou um reembolso de depósito de ordem de cliente.
- Deduzir o valor do depósito de ordem de cliente das linhas de pagamento quando uma ordem híbrida de cliente for criada.
- Salve os ajustes calculados das linhas de pagamento no banco de dados de canal com uma referência a uma transação fiscal para uma ordem híbrida de cliente.

### <a name="limitations-of-the-sample"></a>Limitações do exemplo

O serviço de registro fiscal oferece suporte somente a cenários nos quais o imposto está incluído no preço. Portanto, a opção **Preço inclui imposto** deve estar definida como **Sim** para lojas e clientes.

## <a name="set-up-commerce-for-austria"></a>Configurar o Commerce para a Áustria

Esta seção descreve as configurações do Commerce específicas e recomendadas para a Áustria. Para obter mais informações sobre configuração, consulte [Home page do Commerce](../index.md).

Para usar a funcionalidade específica da Áustria, você deve especificar as seguintes configurações:

- No endereço principal da entidade legal, defina o campo **País/região** como **AUT** (Áustria).
- No perfil da funcionalidade de PDV de todas as lojas localizadas na Áustria, defina o campo **Código ISO** como **AT** (Áustria).

Você também deve especificar as seguintes configurações para a Áustria. Observe que você deve executar os trabalhos de distribuição apropriados depois de concluir a configuração.

### <a name="set-up-vat-per-austrian-requirements"></a>Configurar IVA de acordo com requisitos da Áustria

Você deve criar códigos de impostos, grupos de impostos e grupos de impostos de item. Você também deve configurar informações de impostos para produtos e serviços. Para obter mais informações sobre como configurar e usar recursos de impostos, consulte [Visão geral de imposto](../../finance/general-ledger/indirect-taxes-overview.md).

Em recibos de venda, você pode imprimir um código abreviado para um código de imposto (por exemplo, "A" ou "B"). Para disponibilizar esta funcionalidade, defina o campo **Imprimir código** na página **Códigos de imposto**.

### <a name="set-up-stores"></a>Configurar lojas

Na página **Todas as lojas**, atualize os detalhes da loja. Especificamente, defina os seguintes parâmetros:

- No campo **Grupo de impostos**, especifique o grupo de impostos que deve ser usado para vendas ao cliente padrão.
- Defina a opção **Preço inclui imposto** como **Sim**.
- Defina o campo **Nome** como o nome da empresa. Essa alteração ajuda a garantir que o nome da empresa seja exibido em um recibo de vendas. Como alternativa, você pode adicionar o nome da empresa ao layout do recibo de vendas como texto livre.
- Defina o campo **Número de Identificação de Imposto (TIN)** como o número de identificação da empresa. Essa alteração ajuda a garantir que o número de identificação da empresa seja exibido em um recibo de vendas. Como alternativa, você pode adicionar o número de identificação da empresa ao layout do recibo de vendas como texto livre.

### <a name="set-up-functionality-profiles"></a>Configurar perfis de funcionalidade

Configurar perfis de funcionalidade de PDV:

- Na guia rápida **Numeração de recibo**, configure a numeração de recibo criando ou atualizando registros para os tipos de transação de recibo de **Vendas**, **Ordem de vendas** e **Devolução**.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Você pode configurar o texto do idioma e os campos personalizados usados nos formatos de recibo do PDV. A empresa padrão do usuário que cria a configuração de recibo deve ser a mesma entidade legal na qual a configuração de texto do idioma foi criada. Como alternativa, os textos do mesmo idioma devem ser criados na empresa padrão do usuário e na entidade legal da loja para a qual a configuração foi criada.

Na página **Texto do idioma**, adicione os seguintes registros para os rótulos dos campos personalizados nos layouts de recibo. Os valores **ID de idioma**, **ID do texto** e **Texto** mostrados na tabela são apenas exemplos. Você pode alterá-los para atender aos seus requisitos. No entanto, os valores de **ID do texto** usados devem ser exclusivos e iguais ou maiores que 900001.

Adicione os seguintes rótulos de PDV à seção **PDV** de **Texto do idioma** na tabela:

| ID do Idioma | ID do texto | Texto                      |
|-------------|---------|---------------------------|
| pt-BR       | 900001  | Código QR                   |
| pt-BR       | 900002  | Número contínuo         |
| pt-BR       | 900003  | Código de impressão de varejo de imposto     |
| pt-BR       | 900004  | Total (vendas)             |
| pt-BR       | 900005  | Total de impostos (vendas)         |
| pt-BR       | 900006  | Total incluindo imposto (vendas) |
| pt-BR       | 900007  | Valor do imposto (vendas)        |
| pt-BR       | 900008  | Base do imposto (vendas)         |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**:

| Nome                 | Tipo    | ID do texto da legenda |
|----------------------|---------|-----------------|
| QRCODE               | Recebimento | 900001          |
| CONTINUOUSNUMBER     | Recebimento | 900002          |
| RETAILPRINTCODE      | Recebimento | 900003          |
| SALESTOTAL           | Recebimento | 900004          |
| SALESTOTALTAX        | Recebimento | 900005          |
| SALESTOTALINCLUDETAX | Recebimento | 900006          |
| SALESTAXAMOUNT       | Recebimento | 900007          |
| SALESTAXBASIS        | Recebimento | 900008          |

> [!NOTE]
> É importante que você especifique os nomes de campos personalizados corretos, conforme listados na tabela anterior. Um nome de campo personalizado incorreto causará a falta de dados em recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No Designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Os nomes de campo correspondem aos textos do idioma que você definiu na seção anterior.

- **Cabeçalho:** Adicione os seguintes campos:

    - Os campos **Nomes da loja** e **Número de Identificação de Imposto** usados para imprimir o nome da empresa e o número da identidade nos recibos. Como alternativa, você pode adicionar o número de identidade e o nome da empresa ao layout do recibo de vendas como texto livre.
    - Campos **Endereço da loja**, **Data**, **Hora 24H**, **Número de recibo** e **Número de registro**.
    - Campos **Número contínuo**, para identificar o número da transação de pagamento à vista no serviço de registro fiscal.

- **Linhas:** Adicione os seguintes campos:

    - **Nome do item**.
    - **Quantidade**.
    - **Preço total com imposto**.
    - **Código de impressão de varejo de imposto**, usado para imprimir o código abreviado que corresponde ao código do imposto que se aplica ao item.

- **Rodapé:** Adicione os seguintes campos:

    - Campos de pagamento para que os valores de pagamento de cada forma de pagamento sejam impressos. Por exemplo, adicione os campos **Nome do meio de pagamento** e **Valor do meio de pagamento** a uma linha do layout.
    - Grupo de campos **Total de vendas**:

        - Campo **Total (vendas)**, usado para imprimir o valor total de vendas de à vista do recibo. O valor não inclui imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.
        - Campo **Total incluindo imposto (vendas)**, usado para imprimir o valor total de vendas de à vista do recibo. O valor inclui imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.
        - Campo **Total de impostos (vendas)**, usado para imprimir o valor total de impostos para vendas à vista. Pagamentos antecipados e operações de cartão-presente não são incluídos.

    - Grupo de campos **Detalhamento de imposto**. Todos os campos deste grupo de campos devem ser impressos em uma linha separada.

        - **ID de imposto**, que é um campo padrão que permite que um resumo de impostos seja impresso para cada código de imposto. O campo deve ser adicionado a uma nova linha.
        - **Porcentagem do imposto**, que é um campo padrão usado para imprimir a taxa de imposto efetiva para o código do imposto.
        - **Base do imposto (vendas)**, usado para imprimir o valor total de vendas à vista para o código de imposto. Pagamentos antecipados e operações de cartão-presente não são incluídos.
        - **Valor do imposto (vendas)**, usado para imprimir o valor do imposto do recibo para vendas à vista para o código de imposto.
        - Campo **Código de impressão de varejo de imposto**, usado para imprimir o código abreviado que corresponde ao código do imposto,

    - Campo **Código QR**, usado para imprimir a referência à transação de caixa registradora na forma de código QR.

        > [!NOTE]
        > O valor do **Código QR** é recuperado da resposta do registro fiscal. O EFR retorna um código QR em sua resposta somente se o valor do campo **Atributos** na configuração do EFR for descrito na documentação da EFSTA. O formato de código QR no campo **Atributos** da configuração do EFR deve ser definido como **BMP**.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-austria"></a>Configurar integração fiscal da Áustria

O exemplo de integração do serviço de registro fiscal da Áustria é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Efr** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do Commerce Runtime (CRT) e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma máquina virtual (VM) do desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da Áustria (herdado)](emea-aut-fi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

Conclua as etapas de integração fiscal conforme descritas em [Configurar a integração da fiscal para os canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md):

1. [Configurar um processo de registro fiscal](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process). Além disso, anote as configurações do processo de registro fiscal [específicas a este exemplo de integração do serviço de registro fiscal](#set-up-the-registration-process).
1. [Definir configurações de tratamento de erros](setting-up-fiscal-integration-for-retail-channel.md#set-error-handling-settings).
1. [Habilitar a execução manual do registro fiscal adiado](setting-up-fiscal-integration-for-retail-channel.md#enable-manual-execution-of-postponed-fiscal-registration).
1. [Configurar os componentes de canal](#configure-channel-components).

### <a name="set-up-the-registration-process"></a>Configurar o processo de registro fiscal

Para habilitar o processo de registro, siga estas etapas para configurar a sede do Commerce. Para obter mais informações, consulte [Configurar a integração fiscal dos canais do Commerce](setting-up-fiscal-integration-for-retail-channel.md#set-up-a-fiscal-registration-process).

1. Baixe arquivos de configuração para o provedor de documentos fiscais e o conector fiscal:

    1. Abra o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/).
    1. Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo (por exemplo, **[versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33)**).
    1. Abra **src \> FiscalIntegration \> Efr**.
    1. Abra **Configurações \> DocumentProviders** e baixe os arquivos de configuração do provedor de documentos fiscais: **DocumentProviderFiscalEFRSampleAustria.xml** e **DocumentProviderNonFiscalEFRSampleAustria.xml** (por exemplo, [o local dos arquivos para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders)).
    1. Baixe o arquivo de configuração do conector fiscal em **Configurações \> Conectores \> ConnectorEFRSample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Os arquivos de configuração deste exemplo de integração fiscal estão localizados nas seguintes pastas do SDK do Retail em uma VM do desenvolvedor no LCS:
    >
    > - **Arquivos de configuração do provedor de documentos fiscais:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration
    > - **Arquivo de configuração do conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration
    > 
    > O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados com o comércio**. Na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Provedores de documentos fiscais** e carregue os arquivos do provedor de documentos fiscais baixados anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Conectores fiscais** e carregue o arquivo de configuração do conector fiscal baixado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis funcionais do conector**. Crie dois novos perfis funcionais do conector, um para cada provedor de documentos fiscais carregado anteriormente, e selecione o conector fiscal carregado anteriormente. Atualize as [configurações de mapeamento de dados](#default-data-mapping) conforme necessário.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**. Crie um novo perfil técnico do conector e selecione o conector fiscal carregado anteriormente. Atualize as [configurações do conector](#fiscal-connector-settings) conforme necessário.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Grupos de conectores fiscais**. Crie dois novos grupos de conectores fiscais, um para cada perfil funcional de conector criado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**. Crie um novo processo de registro fiscal e duas etapas do processo de registro fiscal e selecione os grupos de conectores fiscais criados anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. Selecione um perfil de funcionalidade vinculado à loja em que o processo de registro deve ser ativado. Na guia rápida **Processo de registro fiscal**, selecione o processo de registro fiscal criado anteriormente. Para habilitar o registro de eventos não fiscais no PDV, na guia rápida **Funções**, em **PDV**, defina a opção **Auditoria** como **Sim**.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de hardware**. Selecione um perfil de hardware vinculado à estação de hardware à qual a impressora fiscal será conectada. Na guia rápida **Periféricos fiscais**, selecione o perfil técnico do conector criado anteriormente.
1. Abra a agenda de distribuição (**Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**), e selecione os trabalhos **1070** e **1090** para transferir dados ao banco de dados de canal.

#### <a name="default-data-mapping"></a>Mapeamento de dados padrão

O mapeamento de dados padrão a seguir é incluído na configuração do provedor de documentos fiscais fornecida como parte do exemplo de integração fiscal:

- **Mapeamento de alíquotas de imposto sobre valor agregado (IVA)** – O mapeamento de valores de porcentagem de imposto que são configurados para os códigos de imposto como valores do atributo **TaxG** (grupo de imposto) em solicitações que são enviadas para o serviço fiscal. Veja a seguir o mapeamento padrão:

    ```
    A: 20.00; B: 10.00; C: 13.00; D: 0.00; E: 19.00; F: 7.00
    ```

    O primeiro componente em cada par representa um grupo de impostos IVA ao qual o serviço de registro fiscal de EFR oferece suporte. O segundo componente representa a alíquota de IVA correspondente. Para obter mais informações sobre os grupos de impostos IVA aos quais o EFR oferece suporte para a Áustria, consulte a [referência de EFR](https://public.efsta.net/efr/).

#### <a name="fiscal-connector-settings"></a>Configurações do conector fiscal

As configurações a seguir são incluídas na configuração do conector fiscal fornecida como parte do exemplo de integração fiscal:

- **Endereço do ponto de extremidade** – A URL do serviço de registro fiscal.
- **Tempo limite de dispositivo** – O período, em milissegundos, que o conector fiscal aguardará por uma resposta do serviço de registro fiscal.
- **Mostrar notificações de registro fiscal** – Este sinalizador controla se as notificações retornadas pelo serviço de registro fiscal devem ser mostradas ao operador.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da Áustria (herdado)](emea-aut-fi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

#### <a name="set-up-the-development-environment"></a>Configurar o ambiente de desenvolvimento

Para configurar um ambiente de desenvolvimento para testar e ampliar o exemplo, siga estas etapas.

1. Clone ou baixe o repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions). Selecione uma versão correta da ramificação de lançamento de acordo com a sua versão do SDK/aplicativo. Para obter mais informações, consulte [Baixar exemplos de SDK do Retail e pacotes de referência do GitHub e NuGet](../dev-itpro/retail-sdk/sdk-github.md).
1. Abra a solução de EFR em **Dynamics365Commerce.Solutions\\FiscalIntegration\\Efr\\EFR.sln** e crie-a.
1. Instale as extensões do CRT:

    1. Localize o instalador de extensão do CRT:

        - **Commerce Scale Unit:** Na pasta **Efr\\ScaleUnit\\ScaleUnit.EFR.Installer\\bin\\Debug\\net461**, encontre o instalador **ScaleUnit.EFR.Installer**.
        - **CRT local no PDV moderno:** Na pasta **Efr\\ModernPOS\\ModernPOS.EFR.Installer\\bin\\Debug\\net461**, encontre o instalador **ModernPOS.EFR.Installer**.

    1. Inicie o instalador de extensão do CRT na linha de comando:

        - **Commerce Scale Unit:**

            ```Console
            ScaleUnit.EFR.Installer.exe install --verbosity 0
            ```

        - **CRT local no PDV moderno:**

            ```Console
            ModernPOS.EFR.Installer.exe install --verbosity 0
            ```

1. Instalar extensões do conector fiscal:

    Você pode instalar extensões do conector fiscal na [estação de hardware](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-connected-to-the-hardware-station) ou no [terminal de PDV](fiscal-integration-for-retail-channel.md#fiscal-registration-is-done-via-a-device-or-service-in-the-local-network).

    1. Instale as extensões da extensão de hardware:

        1. Na pasta **Efr\\HardwareStation\\HardwareStation.EFR.Installer\\bin\\Debug\\net461**, encontre o instalador **HardwareStation.EFR.Installer**.
        1. Inicie o instalador de extensão na linha de comando, executando o comando a seguir.

            ```Console
            HardwareStation.EFR.Installer.exe install --verbosity 0
            ```

    1. Instale extensões do PDV:

        1. Abra a solução de exemplo do conector fiscal PDV em **Dynamics365Commerce.Solutions\\FiscalIntegration\\PosFiscalConnectorSample\\Contoso.PosFiscalConnectorSample.sln** e compile-a.
        1. Na pasta **PosFiscalConnectorSample\\StoreCommerce.Installer\\bin\\Debug\\net461**, localize o instalador **Contoso.PosFiscalConnectorSample.StoreCommerce.Installer**.
        1. Inicie o instalador de extensão na linha de comando executando o comando a seguir.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **EFR build-pipeline.yml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração do serviço de registro fiscal da Áustria é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Efr** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do CRT e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da Áustria (herdado)](emea-aut-fi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime 

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos do serviço e manipular respostas do serviço de registro fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

Há dois manipuladores de solicitações para provedores de documentos:

- **DocumentProviderEFRFiscalAUT** – Este manipulador é usado para gerar documentos fiscais para o serviço de registro fiscal.
- **DocumentProviderEFRNonFiscalAUT** – Este manipulador é usado para gerar documentos não fiscais para o serviço de registro fiscal.

Esses manipuladores são herdados da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações:

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado no serviço de registro fiscal.
- **GetNonFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre o documento não fiscal que deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado no serviço de registro fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, imprimir relatório X, imprimir relatório Z, depósitos de conta de cliente, depósitos de ordem de cliente, eventos de auditoria e transações não relacionadas a vendas.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Esta solicitação retorna a resposta do serviço de registro fiscal. Esta resposta é serializada para formar uma sequência de caracteres, de modo que esteja pronta para ser salva.

#### <a name="configuration"></a>Configuração

Os arquivos de configuração do provedor de documentos fiscais estão localizados na pasta **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/):

- **DocumentProviderFiscalEFRSampleAustria** – O arquivo de configuração do provedor de documentos fiscais.
- **DocumentProviderNonFiscalEFRSampleAustria** – O arquivo de configuração do provedor de documentos não fiscais.

A finalidade desses arquivos é habilitar as configurações do provedor de documentos fiscais a ser configurado na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão do conector fiscal é comunicar-se com o serviço de registro fiscal. A extensão da estação de hardware usa o protocolos HTTP e HTTPS para enviar documentos que a extensão do CRT gera para o serviço de registro fiscal. Ele também manipula as respostas recebidas do serviço de registro fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **EFRHandler** é o ponto de entrada para o manuseio de solicitações ao serviço de registro fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado na sede do Commerce.

O conector fiscal oferece suporte às seguintes solicitações:

- **SubmitDocumentFiscalDeviceRequest** – Esta solicitação envia documentos para o serviço de registro fiscal e retorna uma resposta dele.
- **IsReadyFiscalDeviceRequest** – Esta solicitação é usada para uma verificação do serviço de registro fiscal.
- **InitializeFiscalDeviceRequest** – Esta solicitação é usada para inicializar o serviço de registro fiscal.

#### <a name="configuration"></a>Configuração

O arquivo de configuração para o conector fiscal está em **src\\FiscalIntegration\\Efr\\Configurations\\Connectors\\ConnectorEFRSample.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="pos-fiscal-connector-extension-design"></a>Design de extensão do conector fiscal PDV

A finalidade da extensão do conector fiscal PDV é comunicar-se com o serviço de registro fiscal do PDV. Ele usa o protocolo HTTPS para comunicação.

#### <a name="fiscal-connector-factory"></a>Fábrica do conector fiscal

A fábrica do conector fiscal mapeia o nome do conector para a implementação do conector fiscal e está localizada no arquivo **Pos.Extension\\Connectors\\FiscalConnectorFactory.ts**. O nome do conector deve corresponder ao nome do conector fiscal especificado na sede do Commerce.

#### <a name="efr-fiscal-connector"></a>Conector fiscal EFR

O conector fiscal EFR está localizado no arquivo **Pos.Extension\\Connectors\\Efr \\EfrFiscalConnector.ts**. Ele implementa a interface **IFiscalConnector** que dá suporte às seguintes solicitações:

- **FiscalRegisterSubmitDocumentClientRequest** – Esta solicitação envia documentos para o serviço de registro fiscal e retorna uma resposta dele.
- **FiscalRegisterIsReadyClientRequest** – Esta solicitação é usada para uma verificação do serviço de registro fiscal.
- **FiscalRegisterInitializeClientRequest** – Esta solicitação é usada para inicializar o serviço de registro fiscal.

#### <a name="configuration"></a>Configuração

O arquivo de configuração está localizado na pasta **src\\FiscalIntegration\\Efr\\Configurations\\Connectors** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do conector fiscal para que sejam definidas na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal. As seguintes configurações são adicionadas:

- **Endereço do ponto de extremidade** – A URL do serviço de registro fiscal.
- **Tempo limite** – O período, em milissegundos, que o conector aguardará por uma resposta do serviço de registro fiscal.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
