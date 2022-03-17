---
title: Exemplo de integração de serviços de registro fiscal da República Tcheca
description: Este tópico fornece uma visão geral do exemplo de integração fiscal da República Tcheca no Microsoft Dynamics 365 Commerce.
author: EvgenyPopovMBS
ms.date: 03/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: epopov
ms.search.validFrom: 2019-4-1
ms.dyn365.ops.version: 10.0.2
ms.openlocfilehash: cb9679bd02c5400fc015c6807407b01e9bf55343
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388227"
---
# <a name="fiscal-registration-service-integration-sample-for-the-czech-republic"></a>Exemplo de integração de serviços de registro fiscal da República Tcheca

[!include[banner](../includes/banner.md)]
[!include[banner](../includes/preview-banner.md)]

Este tópico fornece uma visão geral do exemplo de integração fiscal da República Tcheca no Microsoft Dynamics 365 Commerce.

Para atender aos requisitos fiscais locais para caixas registradoras na República Tcheca, a funcionalidade do Dynamics 365 Commerce da República Tcheca inclui um exemplo de integração do ponto de venda (PDV) com um serviço de registro fiscal externo. O exemplo amplia a [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md). Ele é baseado na solução [EFR (Registro fiscal eletrônico)](https://efsta.org/sicherheitsloesungen/) do [EFSTA](https://efsta.org/) e permite a comunicação com o serviço de EFR por meio do protocolo HTTPS. O serviço de EFR garante o registro eletrônico de vendas (EET - lektronická evidence tržeb), ou seja, a transmissão online dos dados de vendas para um serviço Web fiscal de autoridades de imposto.

O serviço de EFR deve ser hospedado na estação de hardware do Commerce ou em uma máquina separada que pode ser conectada da estação de hardware. O exemplo é fornecido na forma de código-fonte e faz parte do kit de desenvolvimento de software (SDK) do Retail.

A Microsoft não disponibiliza nenhum hardware, software ou documentação da EFSTA. Para obter informações sobre como obter a solução de EFR e operá-la, entre em contato com a [EFSTA](https://efsta.org/kontakt/).

## <a name="scenarios"></a>Cenários

Os cenários a seguir são abordados pelo exemplo de integração do serviço de registro fiscal da República Tcheca:

- Registro de transações de pagamento à vista no serviço de registro fiscal.

    - Enviar os dados de transação detalhados para o serviço de registro fiscal. Esses dados incluem informações da linha de venda e informações sobre descontos, pagamentos e impostos. O serviço de registro fiscal envia os dados para o serviço Web de autoridades de imposto e recebe uma confirmação dele que inclui o código de identificação fiscal da transação.
    - Capturar uma resposta do serviço de registro fiscal. Essa resposta inclui dados fiscais, como o código de identificação fiscal e o código de segurança da transação, etc.
    - Imprimir os dados discais para uma transação registrada no recibo.

- Registro de operações de cartões-presente e depósitos de clientes no serviço de registro fiscal.

    - Emitir ou adicionar dinheiro a um cartão-presente.
    - Registrar um depósito da conta de cliente.
    - Criar uma ordem de cliente e registrar um depósito para a ordem.
    - Editar uma ordem de cliente e substituir o depósito para a ordem.
    - Cancelar uma ordem de cliente e reembolsar o depósito para a ordem.

- Manipulação de erros, como as seguintes opções.

    - Repita o registro fiscal se houver uma nova tentativa, como se o serviço de registro fiscal não estiver disponível, não estiver pronto ou não estiver respondendo.
    - Adiar o registro fiscal.
    - Ignore o registro fiscal ou marque a transação como registrada e inclua códigos informativos para capturar o motivo da falha e informações adicionais.
    - Verifique a disponibilidade do serviço de registro fiscal antes que uma nova transação de venda seja aberta ou que uma transação de venda seja finalizada.

### <a name="gift-cards"></a>Cartões-presente

O exemplo de integração do serviço de registro fiscal implementa as seguintes regras relacionadas a cartões-presente.

- As linhas de venda relacionadas às operações *Emitir cartão-presente* ou *Adicionar cartão-presente* em uma transação de venda são marcadas com um atributo especial quando a transação é registrada no serviço de registro fiscal.
- Um pagamento por cartão-presente é considerado um pagamento regular e marcado com um atributo especial quando a transação é registrada no serviço de registro fiscal.

### <a name="customer-account-deposits-and-customer-order-deposits"></a>Depósitos de conta de cliente e de ordem de cliente

O exemplo de integração do serviço de registro fiscal implementa as seguintes regras relacionadas a depósitos de conta de cliente e de ordem de cliente.

- Uma transação relacionada a um depósito de conta de cliente ou de ordem de cliente é registrada no serviço de registro fiscal como uma transação de uma única linha e é marcada com um atributo especial. O grupo de IVA de depósito é especificado nessa linha.
- Quando uma ordem híbrida de cliente é criada, ou seja, uma ordem de cliente que contém produtos que podem ser retirados da loja pelo cliente, bem como produtos que serão retirados ou remetidos posteriormente, a transação registrada no serviço de registro fiscal contém linhas para os produtos executados, bem como uma linha para o depósito de ordem.
- Um pagamento de uma conta de cliente é considerado um pagamento regular e marcado com um atributo especial quando a transação é registrada no serviço de registro fiscal.
- O valor do depósito de ordem de cliente que é aplicado a uma operação de retirada da ordem de cliente é considerado um pagamento regular e marcado com um atributo especial quando a transação é registrada no serviço de registro fiscal.

### <a name="offline-registration"></a>Registro offline

Se o serviço de registro fiscal não transmitir dados de transação para o serviço da Web fiscal de autoridades de imposto (por exemplo, devido ao tempo limite da resposta) e receber uma confirmação do serviço Web (ou seja, o código de identificação fiscal da transação), ele gerará uma assinatura local para a transação e a incluirá e um código de erro especial na resposta. O serviço de registro fiscal reenvia as transações na ordem original em segundo plano assim que a conexão de rede é restaurada.

### <a name="limitations-of-the-sample"></a>Limitações do exemplo

O serviço de registro fiscal oferece suporte somente a cenários nos quais o imposto está incluído no preço. Portanto, a opção **Preço inclui imposto** deve estar definida como **Sim** para lojas e clientes.

## <a name="set-up-commerce-for-the-czech-republic"></a>Configurar o Commerce para a República Tcheca

Esta seção descreve as configurações do Commerce específicas e recomendadas para a República Tcheca. Para obter mais informações, consulte [Home page do Commerce](../index.md).

Para usar a funcionalidade específica da República Tcheca, você deve especificar as seguintes configurações.

- No endereço principal da entidade legal, defina o campo **País/região** como **CZE** (República Tcheca).
- No perfil da funcionalidade de PDV de todas as lojas localizadas na República Tcheca, defina o campo **Código ISO** como **CZ** (República Tcheca).

Você também deve especificar as seguintes configurações para a República Tcheca. Observe que você deve executar os trabalhos de distribuição apropriados depois de concluir a configuração.

### <a name="set-up-vat-per-czech-republic-requirements"></a>Configurar IVA de acordo com requisitos da República Tcheca


Você deve criar códigos de impostos, grupos de impostos e grupos de impostos de item. Você também deve configurar informações de impostos para produtos e serviços. Para obter mais informações sobre como configurar e usar recursos de impostos, consulte [Visão geral de imposto](../../finance/general-ledger/indirect-taxes-overview.md).

### <a name="set-up-stores"></a>Configurar lojas

Na página **Todas as lojas**, atualize os detalhes da loja. Especificamente, defina os seguintes parâmetros.

- No campo **Grupo de impostos**, especifique o grupo de impostos que deve ser usado para vendas ao cliente padrão.
- Defina a opção **Preço inclui imposto** como **Sim**.
- Defina o campo **Nome** como o nome da empresa. Essa alteração ajuda a garantir que o nome da empresa seja exibido em um recibo de vendas. Como alternativa, você pode adicionar o nome da empresa ao layout do recibo de vendas como texto livre.
- Defina o campo **Número de Identificação de Imposto (TIN)** como o número de identificação da empresa. Essa alteração ajuda a garantir que o número de identificação da empresa seja exibido em um recibo de vendas. Como alternativa, você pode adicionar o número de identificação da empresa ao layout do recibo de vendas como texto livre.

### <a name="set-up-functionality-profiles"></a>Configurar perfis de funcionalidade

Configurar perfis de funcionalidade de PDV.

- Na guia rápida **Numeração de recibo**, configure a numeração de recibo criando ou atualizando registros para os tipos de transação de recibo de **Vendas**, **Ordem de vendas** e **Devolução**.

### <a name="set-up-registration-numbers"></a>Configurar números de registro

1. Vá para **Administração da organização \> Catálogo de endereços global \> Tipos de registro \> Tipos de registro**. Criar um novo tipo de registro. Especifique o campo **País/região** como **CZE** (República Tcheca) e torne-o restrito à organização.
2. Vá para **Administração da organização \> Catálogo de endereços global \> Tipos de registro \> Categorias de registro**. Criar uma nova categoria de registro. Selecione o tipo de registro da etapa anterior e defina a **Categoria de registro** como **ID de local comercial**.
3. Acesse **Administração da organização \> Organizações \> Unidades operacionais**. Para cada loja localizada na República Tcheca, selecione a unidade relacionada à loja. Na guia rápida **Endereço**, expanda a lista suspensa **Mais opções** e selecione **Avançado**. 
4. Na página aberta **Gerenciar endereços**, você deve especificar a configuração a seguir.

    - Na guia rápida **Endereço** defina o campo **País/região** como **CZE**.
    - Na guia rápida **ID de registro**, crie um novo registro. Selecione o tipo de registro criado anteriormente e defina o número de registro.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Você pode configurar o texto do idioma e os campos personalizados usados nos formatos de recibo do PDV. A empresa padrão do usuário que cria a configuração de recibo deve ser a mesma entidade legal na qual a configuração de texto do idioma foi criada. Como alternativa, os textos do mesmo idioma devem ser criados na empresa padrão do usuário e na entidade legal da loja para a qual a configuração foi criada.

Na página **Texto do idioma**, adicione os seguintes registros para os rótulos dos campos personalizados nos layouts de recibo. Os valores **ID de idioma**, **ID do texto** e **Texto** mostrados na tabela são apenas exemplos. Você pode alterá-los para atender aos seus requisitos. No entanto, os valores de **ID do texto** usados devem ser exclusivos e iguais ou maiores que 900001.

Adicione os seguintes rótulos de PDV à seção **PDV** de **Texto do idioma** na tabela:

| ID do Idioma | ID do texto | Texto                   |
|-------------|---------|------------------------|
| pt-BR       | 900001  | ID provozovny/pokladny |
| pt-BR       | 900002  | BKP                    |
| pt-BR       | 900003  | PKP                    |
| pt-BR       | 900004  | FIK                    |
| pt-BR       | 900005  | Informações                   |
| pt-BR       | 900006  | Número de sequência        |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**:

| Nome                 | Tipo    | ID do texto da legenda |
|----------------------|---------|-----------------|
| TLT                  | Recebimento | 900001          |
| SEC                  | Recebimento | 900002          |
| SIGN                 | Recebimento | 900003          |
| FISCAL               | Recebimento | 900004          |
| INFO                 | Recebimento | 900005          |
| CONTINUOUSNUMBER     | Recebimento | 900006          |

> [!NOTE]
> É importante que você especifique os nomes de campos personalizados corretos, conforme listados na tabela anterior. Um nome de campo personalizado incorreto causará a falta de dados em recibos.

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No Designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Os nomes de campo correspondem aos textos do idioma que você definiu na seção anterior.

- **Cabeçalho:** Adicione os seguintes campos.

    - **Nomes da loja** e **Número de Identificação de Imposto**: Campos usados para imprimir o nome da empresa e o número da identidade nos recibos. Como alternativa, você pode adicionar o número de identidade e o nome da empresa ao layout do recibo de vendas como texto livre.
    - **Endereço da loja**, **Data**, **Hora 24H**, **Número de recibo** e **Número de registro**.
    - **Número de sequência**: Este campo identifica o número da transação de pagamento à vista no serviço de registro fiscal.

- **Linhas:** Adicione os seguintes campos.

    - **Nome do item**
    - **Qtd.**
    - **Preço total com imposto**

- **Rodapé:** Adicione os seguintes campos.

    - Campos de pagamento para que os valores de pagamento de cada forma de pagamento sejam impressos. Por exemplo, adicione os campos **Nome do meio de pagamento** e **Valor do meio de pagamento** a uma linha do layout.
    - **ID provozovny/pokladny**: Este campo imprime os identificadores do local comercial e da caixa registradora.
    - **BKP**: Este campo imprime o código de segurança do contribuinte atribuído pelo serviço de registro fiscal.
    - **FIK**: Este campo imprime o código de identificação fiscal da transação atribuída pelo serviço Web de autoridades de imposto no caso de um registro online bem-sucedido.
    - **PKP**: Este campo imprime o código de assinatura do contribuinte gerado pelo serviço de registro fiscal no caso de registro offline.
    - **Informações**: Este campo imprime as informações adicionais do serviço de registro fiscal.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

## <a name="set-up-fiscal-integration-for-the-czech-republic"></a>Configurar a integração fiscal da República Tcheca

O exemplo de integração do serviço de registro fiscal da República Tcheca é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Efr** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do Commerce Runtime (CRT) e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma máquina virtual (VM) do desenvolvedor no Microsoft Dynamics Lifecycle Services (LCS). Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da República Tcheca (herdado)](emea-cze-fi-sample-sdk.md).
>
> O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

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
    1. Baixe o arquivo de configuração do provedor de documentos fiscais em **Configurações \> DocumentProviders \> DocumentProviderFiscalEFRSampleCzech.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/DocumentProviders/DocumentProviderFiscalEFRSampleCzech.xml)).
    1. Baixe o arquivo de configuração do conector fiscal em **Configurações \> Conectores \> ConnectorEFRSample.xml** (por exemplo, [o arquivo para a versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/blob/release/9.33/src/FiscalIntegration/Efr/Configurations/Connectors/ConnectorEFRSample.xml)).

    > [!WARNING]
    > Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Os arquivos de configuração deste exemplo de integração fiscal estão localizados nas seguintes pastas do SDK do Retail em uma VM do desenvolvedor no LCS:
    >
    > - **Arquivo de configuração do provedor de documentos fiscais:** RetailSdk\\SampleExtensions\\CommerceRuntime\\Extensions.DocumentProvider.EFRSample\\Configuration\\DocumentProviderFiscalEFRSampleCzech.xml
    > - **Arquivo de configuração do conector fiscal:** RetailSdk\\SampleExtensions\\HardwareStation\\Extension.EFRSample\\Configuration\\ConnectorEFRSample.xml
    > 
    > O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros \> Parâmetros compartilhados com o comércio**. Na guia **Geral**, defina a opção **Habilitar integração fiscal** como **Sim**.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Provedores de documentos fiscais** e carregue o arquivo do provedor de documentos fiscais baixado anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Integração fiscal \> Conectores fiscais** e carregue o arquivo de configuração do conector fiscal baixado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis funcionais do conector**. Crie um novo perfil funcional do conector. Selecione o provedor de documentos e o conector carregados anteriormente. Atualize as [configurações de mapeamento de dados](#default-data-mapping) conforme necessário.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Perfis técnicos do conector**. Crie um novo perfil técnico do conector e selecione o conector fiscal carregado anteriormente. Atualize as [configurações do conector](#fiscal-connector-settings) conforme necessário.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Grupos de conectores fiscais**. Crie um novo grupo do conector fiscal para o perfil funcional do conector criado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Integração fiscal \> Processos de registro fiscal**. Crie um novo processo de registro fiscal e uma etapa do processo de registro fiscal e selecione o grupo do conector fiscal criado anteriormente.
1. Acesse **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de funcionalidade**. Selecione um perfil de funcionalidade vinculado à loja em que o processo de registro deve ser ativado. Na guia rápida **Processo de registro fiscal**, selecione o processo de registro fiscal criado anteriormente.
1. Acesse **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> Perfis de PDV \> Perfis de hardware**. Selecione um perfil de hardware vinculado à estação de hardware à qual a impressora fiscal será conectada. Na guia rápida **Periféricos fiscais**, selecione o perfil técnico do conector criado anteriormente.
1. Abra a agenda de distribuição (**Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**), e selecione os trabalhos **1070** e **1090** para transferir dados ao banco de dados de canal.

#### <a name="default-data-mapping"></a>Mapeamento de dados padrão

O mapeamento de dados padrão a seguir é incluído na configuração do provedor de documentos fiscais fornecida como parte do exemplo de integração fiscal:

- **Mapeamento de alíquotas de imposto sobre valor agregado (IVA)** – O mapeamento de valores de porcentagem de imposto que são configurados para os códigos de imposto como valores do atributo **TaxG** (grupo de imposto) em solicitações que são enviadas para o serviço fiscal. Veja a seguir o mapeamento padrão:

    ```
    A: 21.00; B: 15.00; C: 10.00; Z: 0.00
    ```

    O primeiro componente em cada par representa um grupo de impostos IVA ao qual o serviço de registro fiscal de EFR oferece suporte. O segundo componente representa a alíquota de IVA correspondente. Para obter mais informações sobre os grupos de impostos IVA aos quais o EFR oferece suporte para a República Tcheca, consulte a [referência de EFR](https://public.efsta.net/efr/).

- **Mapeamento de grupo de IVA padrão** – Os valores de IVA que não podem ser mapeados para um dos grupos de IVA predeterminados serão atribuídos ao grupo de IVA padrão (básico). Veja a seguir o mapeamento padrão:

    ```
    A
    ```

- **Mapeamento de grupo de IVA de depósito** – Valores de depósito de cliente e de ordem de cliente serão atribuídos ao grupo de IVA de depósito. Veja a seguir o mapeamento padrão:

    ```
    Z
    ```

#### <a name="fiscal-connector-settings"></a>Configurações do conector fiscal

As configurações a seguir são incluídas na configuração do conector fiscal fornecida como parte do exemplo de integração fiscal:

- **Endereço do ponto de extremidade** – A URL do serviço de registro fiscal.
- **Tempo limite** – O período, em milissegundos, que o conector fiscal aguardará por uma resposta do serviço de registro fiscal.

### <a name="configure-channel-components"></a>Configurar os componentes de canal

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da República Tcheca (herdado)](emea-cze-fi-sample-sdk.md).
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
        1. Inicie o instalador de extensão na linha de comando, executando o comando a seguir.

            ```Console
            Contoso.PosFiscalConnectorSample.StoreCommerce.Installer.exe install --verbosity 0
            ```

#### <a name="production-environment"></a>Ambiente de produção

Siga as etapas em [Configurar um pipeline de build para um exemplo de integração fiscal](fiscal-integration-sample-build-pipeline.md) a fim de gerar e lançar os pacotes implantáveis de autoatendimento e do Cloud Scale Unit para o exemplo de integração fiscal. O arquivo YAML do modelo **EFR build-pipeline.yml** pode ser encontrado na pasta **Pipeline\\YAML_Files** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions).

## <a name="design-of-extensions"></a>Design de extensões

O exemplo de integração do serviço de registro fiscal da República Tcheca é baseado na [funcionalidade de integração fiscal](fiscal-integration-for-retail-channel.md) e faz parte do SDK do Retail. O exemplo está localizado na pasta **src\\FiscalIntegration\\Efr** do repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/) (por exemplo, [o exemplo na versão/9.33](https://github.com/microsoft/Dynamics365Commerce.Solutions/tree/release/9.33/src/FiscalIntegration/Efr)). O exemplo [consiste](fiscal-integration-for-retail-channel.md#fiscal-registration-process-and-fiscal-integration-samples-for-fiscal-devices-and-services) em um provedor de documentos fiscais, que é uma extensão do CRT e um conector fiscal, que é uma extensão da estação de hardware do Commerce. Para obter mais informações sobre como usar o SDK do Retail, consulte [arquitetura de SDK do Retail](../dev-itpro/retail-sdk/retail-sdk-overview.md) e [Configurar um pipeline de build para o SDK de compactação independente](../dev-itpro/build-pipeline.md).

> [!WARNING]
> Devido às limitações do [novo empacotamento independente e modelo de extensão](../dev-itpro/build-pipeline.md), ele não pode ser usado no momento para esse exemplo de integração fiscal. Você deve usar a versão anterior do SDK do Retail em uma VM do desenvolvedor no LCS. Para obter mais informações, consulte [Diretrizes de implantação para o exemplo de integração fiscal da República Tcheca (herdado)](emea-cze-fi-sample-sdk.md). O suporte para o novo pacote independente e o modelo de extensão para os exemplo de integração fiscal está planejado para versões posteriores.

### <a name="commerce-runtime-extension-design"></a>Design de extensão do Commerce Runtime

A finalidade da extensão que é um provedor de documentos fiscais é gerar documentos específicos do serviço e manipular respostas do serviço de registro fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

Há um único manipulador de solicitações **DocumentProviderEFRFiscalCZE** para o provedor de documentos, que é usado para gerar documentos fiscais para o serviço de registro fiscal.

Esse manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do provedor do documento do conector especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações.

- **GetFiscalDocumentDocumentProviderRequest** – Esta solicitação contém informações sobre qual documento deve ser gerado. Ele retorna um documento específico do serviço que deve ser registrado no serviço de registro fiscal.
- **GetSupportedRegistrableEventsDocumentProviderRequest** – Esta solicitação retorna a lista de eventos a serem assinados. No momento, há suporte para os seguintes eventos: vendas, depósitos de conta de cliente e de ordem de clientes.
- **GetFiscalRegisterResponseToSaveDocumentProviderRequest** – Esta solicitação retorna a resposta do serviço de registro fiscal. Esta resposta é serializada para formar uma sequência de caracteres, de modo que esteja pronta para ser salva.

#### <a name="configuration"></a>Configuração

O arquivo de configuração para o provedor de documentos fiscais está em **src\\FiscalIntegration\\Efr\\Configurations\\DocumentProviders\\DocumentProviderFiscalEFRSampleCzech.xml** no repositório [Soluções do Dynamics 365 Commerce](https://github.com/microsoft/Dynamics365Commerce.Solutions/). A finalidade do arquivo é habilitar as configurações do provedor de documentos fiscais a ser configurado na sede do Commerce. O formato de arquivo é alinhado com os requisitos para a configuração de integração fiscal.

### <a name="hardware-station-extension-design"></a>Design de extensão de estação de hardware

A finalidade da extensão que é um conector fiscal é comunicar-se com o serviço de registro fiscal. A extensão da estação de hardware usa o protocolo HTTP para enviar documentos que a extensão do CRT gera para o serviço de registro fiscal. Ele também manipula as respostas recebidas do serviço de registro fiscal.

#### <a name="request-handler"></a>Manipulador de solicitações

O manipulador de solicitações **EFRHandler** é o ponto de entrada para o manuseio de solicitações ao serviço de registro fiscal.

O manipulador é herdado da interface **INamedRequestHandler**. O método **HandlerName** é responsável por retornar o nome do manipulador. O nome do manipulador deve corresponder ao nome do conector fiscal especificado no Commerce Headquarters.

O conector oferece suporte às seguintes solicitações.

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
