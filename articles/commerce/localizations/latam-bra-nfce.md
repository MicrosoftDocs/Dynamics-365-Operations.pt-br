---
title: Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de documento fiscal NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: josaw1
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-06-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: cf98586194364506724631761fc953f00685a286
ms.sourcegitcommit: de0f50e9e24e74b4d3bb84f67908cdd23e75104b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2021
ms.locfileid: "7818506"
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

Os recibos fiscais DANFE podem implementar e usar os seguintes campos personalizados para incluir informações adicionais:

- **Chave de acesso** – A chave de acesso que consiste em 11 blocos, cada um com quatro dígitos.
- **Protocolo de Autorização** – Número que é obtido da SEFAZ quando são emitidos documentos fiscais NFC-e ou NF-e.
- **Dados fiscais do emissor (Emitente)**:

    - **Nome** – O nome corporativo do estabelecimento fiscal.
    - **CNPJ** – O número CNPJ do estabelecimento fiscal.
    - **IE** – O ID de registro do estado do estabelecimento fiscal.
    - **Endereço** – O endereço do estabelecimento fiscal.

- **Data de emissão (Emissão / Dados de recebimento)** – A data e hora em que o recibo é emitido.
- **Número NFC-e / NF-e (Número)** – O número do documento fiscal eletrônico.
- **Série** – A série do documento fiscal eletrônico.
- **Tipo de operação (Saída / Entrada )** – O tipo de entrada ou saída da operação.
- **Dados fiscais do cliente (Destinatário)**:

    - **Nome** – O nome do destinatário ou da corporação.
    - **CPF/CNPJ/ID de estrangeiro** – O número do CPF/CNPJ ou ID de estrangeiro do destinatário.
    - **Endereço** - O endereço de email do destinatário.

- **Quantidade (Qtd.)** – A quantidade de itens.
- **Valor total do item (Valor total)** – O valor por item.
- **Quantidade total (Qtd. total de itens)** – A quantidade total de itens no recibo.
- **Valor total** – O valor total do recibo.
- **Código QR** – Um recibo pode incluir um código QR para DANFE modelo 65 para vendas.
- **Mensagem de Interesse do Contribuinte** – Um detalhamento aproximado da carga tributária nos documentos fiscais da NFC-e.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Registro adiado de notas NFC-e emitidas no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)
