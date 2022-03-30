---
title: Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de documento fiscal NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: akviklis
manager: annbe
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2019-06-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f9600f6807f214131f836ddc9104280ed56706f1
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407970"
---
# <a name="nfc-e-fiscal-document-functionality-in-commerce-pos-for-brazil"></a>Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil

[!include[banner](../includes/banner.md)]

Este tópico dá uma visão geral da funcionalidade de documento fiscal NFCe (Nota Fiscal do Consumidor eletrônica) no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil. Ele também explica como emitir documentos NFC-e e imprimir recibos fiscais DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) quando as vendas de mercadorias no varejo são concluídas no PDV do Commerce para o Brasil.

Uma NFC-e é um documento fiscal eletrônico gerado para registrar a venda de mercadorias para um cliente. Ela permite o controle fiscal e fiscal por parte das autoridades fiscais. Ela também permite que os clientes verifiquem a validade e autenticidade dos documentos fiscais que recebem. As vendas de serviços não são compatíveis.

A funcionalidade do Commerce para o Brasil permite o formato NFC-e modelo 65 para varejistas brasileiros. O formato de NFC-e modelo 65 é um padrão nacional para documentos fiscais eletrônicos. Ele foi projetado para o varejo e é baseado nas mesmas normas técnicas do formato do modelo 55 da NF-e (Nota Fiscal eletrônica). Para obter mais informações sobre o formato e o processo da NF-e, consulte [Visão geral do processo de NF-e do Brasil](../../finance/localizations/latam-bra-nf-e-process.md).

## <a name="supported-scenarios"></a>Cenários com suporte

Os cenários de exemplo a seguir mostram as ações do Commerce frequentemente realizadas que estão associadas a documentos NFC-e.

### <a name="scenario-1-make-a-cash-and-carry-sale-of-goods-and-print-a-danfe-receipt"></a>Cenário 1: fazer uma venda de mercadorias cash-and-carry e imprimir um recibo DANFE

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Registre os pagamentos da transação.
1. Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código QR) no recibo DANFE impresso correspondem à venda.

### <a name="scenario-2-make-a-cash-and-carry-sale-of-goods-to-an-identified-customer"></a>Cenário 2: fazer uma venda de mercadorias cash-and-carry para um cliente identificado

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Adicione um cliente nomeado ou insira manualmente informações do cliente. Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).
1. Registre os pagamentos da transação.
1. Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se as informações (incluindo o código QR) no recibo DANFE impresso correspondem à venda.

### <a name="scenario-3-make-a-cash-and-carry-sale-of-goods-in-offline-contingency-mode"></a>Cenário 3: fazer uma venda de mercadorias por cash-and-carry no modo de contingência offline

O modo de contingência offline NFC-e deve ser usado quando a conexão à Internet de uma loja não estiver disponível, ou quando o serviço de autorização da SEFAZ (Secretaria de Estado de Fazenda) estiver desativado. No modo de contingência offline, o PDV gera documentos NFC-e localmente. Esses documentos são encaminhados à SEFAZ posteriormente.

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Registre os pagamentos da transação. Você receberá um erro quando o PDV tentar se comunicar com a SEFAZ.
1. Selecione **Adiar**, digite uma justificativa para o adiamento e, em seguida, finalize a transação.
1. Verifique se são impressas duas cópias do DANFE detalhado: uma para o consumidor (via consumidor) e outra para o estabelecimento (via estabelecimento).
1. Verifique se as informações (incluindo o código QR) nos recibos DANFE impressos correspondem à venda.
1. Verifique se os recibos DANFE contêm o seguinte texto: "EMITIDA EM CONTINGÊNCIA Pendente de autorização".

> [!NOTE]
> Se NFC-e for escolhido como o modo principal de um estabelecimento no estado de São Paulo, o PDV deverá gerar documentos CF-e (Cupom Fiscal Eletrônico) por meio de um dispositivo SAT (Sistema Autenticador e Transmissor de Cupons Fiscais Eletrônicos) quando a conexão com a Internet da loja não estiver disponível ou quando o serviço de autorização da SEFAZ estiver inoperante. Esse uso de SAT é considerado um modo de contingência. Para mais informações, consulte o cenário [Fazer uma venda de mercadorias por cash-and-carry usando SAT como modo de contingência](latam-bra-cf-e-sat.md#scenario-4-make-a-cash-and-carry-sale-of-goods-by-using-sat-as-contingency-mode) para a integração de documentos fiscais CF-e com a funcionalidade de SAT.

### <a name="scenario-4-make-a-mixed-sale-that-contains-gift-cards-and-other-goods-in-the-same-transaction"></a>Cenário 4: fazer uma venda mista que contenha vales-presente e outras mercadorias na mesma transação

As operações de emissão de vales-presente e agregação de valor aos vales-presente não estão sujeitas a tributações no Brasil. Portanto, elas não são inseridas no recibo fiscal.

1. Entre no POS.
1. Adicione produtos ao carrinho.
1. Emita vales-presente na mesma transação.
1. Registre os pagamentos da transação.
1. Selecione o formato do DANFE (**Simplificado** ou **Detalhado**) e, em seguida, finalize a transação.
1. Verifique se o recibo DANFE impresso não inclui os vales-presente junto com os outras mercadorias que foram vendidas.
1. Verifique se os recibos separados são impressos para cada vale-presente que foi vendido.

## <a name="custom-fields-for-danfe-fiscal-receipts"></a>Campos personalizados para recibos fiscais DANFE

Os recibos fiscais DANFE podem implementar e usar campos personalizados para incluir informações adicionais.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Você pode configurar o texto do idioma e os campos personalizados usados nos formatos de recibo do PDV. A empresa padrão do usuário que cria a configuração de recibo deve ser a mesma entidade legal na qual a configuração de texto do idioma foi criada. Como alternativa, os textos do mesmo idioma devem ser criados na empresa padrão do usuário e na entidade legal da loja para a qual a configuração foi criada.

Na página **Texto do idioma**, adicione os seguintes registros para os rótulos dos campos personalizados nos layouts de recibo. Os valores **ID de idioma**, **ID do texto** e **Texto** mostrados na tabela são apenas exemplos. Você pode alterá-los para atender aos seus requisitos. No entanto, os valores de **ID do texto** usados devem ser exclusivos e iguais ou maiores que 900001.

Adicione os seguintes rótulos de PDV à seção **PDV** da página **Texto do idioma**.

| ID do Idioma | ID do texto | Texto |
|---|---|---|
| pt-BR | 900001 | Chave de acesso |
| pt-BR | 900002 | Protocolo de autorização |
| pt-BR | 900003 | Data do Protocolo de Autorização |
| pt-BR | 900004 | Nome do estabelecimento do emissor |
| pt-BR | 900005 | Endereço do estabelecimento do emissor |
| pt-BR | 900006 | Número de registro da IE (estado) do estabelecimento do emissor |
| pt-BR | 900007 | Número de registro do CCM (cidade) do estabelecimento do emissor |
| pt-BR | 900008 | Número de registro do CNPJ do estabelecimento do emissor |
| pt-BR | 900009 | Data e hora da emissão |
| pt-BR | 900010 | Tipo de operação (entrada ou saída) |
| pt-BR | 900011 | Número da NFC-e / NF-e |
| pt-BR | 900012 | Série da NFC-e / NF-e |
| pt-BR | 900013 | Mensagem de cliente não identificado |
| pt-BR | 900014 | Nome do cliente |
| pt-BR | 900015 | Endereço do cliente |
| pt-BR | 900016 | Número de registro da IE (estado) do cliente |
| pt-BR | 900017 | Número de registro do CCM (cidade) do cliente |
| pt-BR | 900018 | Número de registro do CPF / CNPJ / ID de estrangeiro do cliente |
| pt-BR | 900019 | Quantidade de item |
| pt-BR | 900020 | Valor total do item |
| pt-BR | 900021 | Quantidade total |
| pt-BR | 900022 | Valor total |
| pt-BR | 900023 | Desconto do item |
| pt-BR | 900024 | Desconto do valor subtotal |
| pt-BR | 900025 | Desconto total |
| pt-BR | 900026 | Mensagem de desconto total |
| pt-BR | 900027 | Código QR |
| pt-BR | 900028 | Mensagem de juros do contribuinte |

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Observe que os valores de **ID de texto da legenda** devem corresponder aos valores de **ID de texto** especificados na página **Texto do idioma**.

| Nome | Tipo | ID do texto da legenda |
|---|---|---|
| EFDOCACCESSKEY\_BR | Recebimento | 900001 |
| EFDAUTHORIZATIONPROTOCOL\_BR | Recebimento | 900002 |
| EFDAUTHORIZATIONPROTOCOLDATE\_BR | Recebimento | 900003 |
| FISCALDOCUMENTESTABLISHMENTNAME\_BR | Recebimento | 900004 |
| FISCALDOCUMENTESTABILISHMENTADDRESS\_BR | Recebimento | 900005 |
| IENUMBER\_BR | Recebimento | 900006 |
| CCMNUM\_BR | Recebimento | 900007 |
| CNPJCPFNUM\_BR | Recebimento | 900008 |
| FISCALDOCUMENTDATE\_BR | Recebimento | 900009 |
| TYPEOFOPERATION\_BR | Recebimento | 900010 |
| FISCALDOCUMENTNUMBER\_BR | Recebimento | 900011 |
| FISCALDOCUMENTSERIES\_BR | Recebimento | 900012 |
| EFDNOTIDENTIFIEDCUSTOMERMESSAGE\_BR | Recebimento | 900013 |
| FISCALDOCUMENTCUSTOMERNAME\_BR | Recebimento | 900014 |
| FISCALDOCUMENTCUSTOMERADDRESS\_BR | Recebimento | 900015 |
| IETAXIDENTIFIER\_BR | Recebimento | 900016 |
| CCMTAXIDENTIFIER_BR | Recebimento | 900017 |
| CPFCNPJTAXIDENTIFIER_BR | Recebimento | 900018 |
| QTY\_BR | Recebimento | 900019 |
| TOTALAMOUNT\_BR | Recebimento | 900020 |
| EFDTOTALITEMQUANTITY\_BR | Recebimento | 900021 |
| TOTALAMOUNTWITHTAX\_BR | Recebimento |900022 |
| FISCALDOCUMENTTOTALITEMSDISCOUNT\_BR | Recebimento |900023 |
| FISCALDOCUMENTSUBTOTALDISCOUNT\_BR | Recebimento |900024 |
| FISCALDOCUMENTDISCOUNTTOTAL\_BR | Recebimento |900025 |
| FISCALDOCUMENTDISCOUNTTOTALMESSAGE\_BR | Recebimento |900026 |
| EFDQRCODE\_BR | Recebimento | 900027 |
| FISCALDOCUMENTCONSUMEROBSERVATION\_BR | Recebimento | 900028 |

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Os nomes de campo correspondem aos textos do idioma que você definiu na seção anterior.

- **Cabeçalho:** Adicione os seguintes campos:

    - **Chave de acesso** – A chave de acesso que consiste em 11 blocos, cada um com quatro dígitos.
    - **Protocolo de Autorização** – Número que é obtido da SEFAZ quando a NFC-e ou NF-e é emitida.
    - **Data do Protocolo de Autorização (Data de Autorização)** – A data e a hora em que a NFC-e ou NF-e é registrada na SEFAZ.
    - **Dados fiscais do emissor (Emitente)**:

        - **Nome** – O nome corporativo do estabelecimento fiscal.
        - **CNPJ** – O número CNPJ do estabelecimento fiscal.
        - **IE** – O ID de registro do estado do estabelecimento fiscal.
        - **CCM** – O ID de registro da cidade do estabelecimento fiscal.
        - **Endereço** – O endereço do estabelecimento fiscal.

    - **Data de emissão (Emissão / Dados de recebimento)** – A data e hora em que o recibo é emitido.
    - **Número NFC-e / NF-e (Número)** – O número do documento fiscal eletrônico.
    - **Série** – A série do documento fiscal eletrônico.
    - **Tipo de operação (Saída / Entrada )** – O tipo de entrada ou saída da operação.
    - **Dados fiscais do cliente (Destinatário)**:

        - **Nome** – O nome comum ou corporativo do cliente.
        - **CPF/CNPJ/ID de estrangeiro** – O número do CPF/CNPJ ou ID de estrangeiro do cliente.
        - **IE** – O ID de registro do estado do cliente.
        - **CCM** – O ID de registro da cidade do cliente.
        - **Endereço** – O endereço do cliente.

        Como alternativa, pode haver uma mensagem de cliente não identificado.

- **Linhas:** Adicione os seguintes campos:

    - **Nome do item** – O nome do item.
    - **Quantidade de itens (Qtd.)** – A quantidade de itens.
    - **Valor total do item (Valor total)** – O valor por item.
    - **Quantidade total (Qtd. total de itens)** – A quantidade total de itens no recibo.
    - **Valor total** – O valor total do recibo.
    - **Desconto do item** – O desconto por item.
    - **Desconto do valor subtotal** – O desconto a ser aplicado sobre o subtotal.
    - **Desconto total** – O desconto total do recibo.
    - **Mensagem de desconto total** – A mensagem de desconto total. 

- **Rodapé:** Adicione os seguintes campos:

    - **Código QR** – Um recibo pode incluir um código QR para DANFE modelo 65 para vendas.
    - **Mensagem de Interesse do Contribuinte** – Um detalhamento aproximado da carga tributária nos documentos fiscais da NFC-e.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Registro adiado de notas NFC-e emitidas no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)

[Configurar e criar formatos de recibo](../receipt-templates-printing.md).
