---
title: Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de cancelamento e devolução para documentos NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: akviklis
manager: annbe
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c7b863d5400b264d8d73787b30b9c26155b10bb9
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891400"
---
# <a name="cancellation-and-return-of-nfc-e-documents-in-commerce-pos-for-brazil"></a>Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil

[!include[banner](../includes/banner.md)]

Este tópico dá uma visão geral da funcionalidade de cancelamento e devolução para documentos NFC-e (Nota Fiscal do Consumidor eletrônica) no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.

A funcionalidade do Commerce para o Brasil permite o cancelamento e a devolução das vendas que foram emitidas por meio de documentos NFC-e. Os formatos de documentos NFC-e baseiam-se nas normas técnicas nacionais para documentos fiscais eletrônicos. Essas normas também incluem um formato para eventos de cancelamento e NF-e (Nota Fiscal eletrônica) modelo 55 para devoluções.

Uma NF-e é um documento fiscal eletrônico gerado e impressa para registrar a devolução de mercadorias que foram vendidas para um cliente. Ela permite o controle fiscal e fiscal por parte das autoridades fiscais. Ela também permite que os clientes verifiquem a validade e autenticidade dos documentos fiscais que recebem. Para obter mais informações sobre o processo de NF-e, consulte [Visão geral do processo de NF-e do Brasil](../../finance/localizations/latam-bra-nf-e-process.md).

Um documento NFC-e só pode ser cancelado se já tiver sido autorizado pela autoridade fiscal, e se a mercadoria e o cliente ainda estiverem no estabelecimento. O prazo para o cancelamento de um documento NFC-e é de 30 minutos após a autorização de uso ser concedida. Após o término deste prazo de cancelamento, um documento de devolução da NF-e deve ser emitido para cancelar uma venda.

## <a name="limitations"></a>Limitações

As seguintes limitações aplicam-se à funcionalidade de cancelamento e devolução para documentos NFC-e:

- Cancelamentos e devoluções são permitidos apenas para vendas que são feitas dentro do mesmo estado. As operações interestaduais são proibidas.
- O cancelamento de documentos NFC-e autorizados por terminais de PDV em outras lojas não é compatível. Somente documentos NFC-e autorizados que são emitidos por terminais do PDV na mesma loja podem ser cancelados.
- Os cancelamentos e devoluções que são emitidos no modo de contingência offline não são compatíveis. Em outras palavras, os cancelamentos e devoluções não podem ser emitidos por terminais de PDV que não tenham acesso à internet, ou quando o serviço de autorização da autoridade fiscal está disponível.
- O DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) simplificado para o formato modelo 55 é o único layout compatível para devoluções.
- As vendas e devoluções de serviços não são compatíveis.

## <a name="supported-scenarios"></a>Cenários com suporte

Os cenários de exemplo a seguir mostram como iniciar cancelamentos e devoluções no PDV do Commerce para o Brasil.

### <a name="scenario-1-initiate-a-cancellation-of-sold-goods"></a>Cenário 1: iniciar o cancelamento de mercadorias vendidas

Para iniciar o cancelamento de mercadorias vendidas, siga estas etapas.

1. Entre no POS.
1. Abra a página **Exibir diário**.
1. Encontre a venda que deve ser cancelada.
1. Selecione **Cancelar transação**.
1. Digite uma justificativa para o cancelamento e selecione **OK**.
1. Adicione um cliente nomeado ou insira manualmente informações do cliente. Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).
1. Registre os reembolsos de pagamento da transação e, em seguida, finalize a transação.

### <a name="scenario-2-initiate-a-return-of-sold-goods"></a>Cenário 2: iniciar a devolução de mercadorias vendidas

Para iniciar a devolução de mercadorias vendidas, siga estas etapas.

1. Entre no POS.
1. Abra a página **Exibir diário**.
1. Encontre a venda que deve ser devolvida total ou parcialmente.
1. Selecione **Devolução**, selecione os produtos que podem ser devolvidos conforme necessário e selecione **Devolver**.
1. Adicione um cliente nomeado ou insira manualmente informações do cliente. Para obter mais informações, consulte [Gerenciar informações de clientes no PDV para o Brasil](latam-bra-customer-information.md).
1. Registre os pagamentos da transação.
1. Verifique se as informações (incluindo o código de barras) no recibo DANFE simplificado impresso para o documento fiscal modelo 55 correspondem à venda.

## <a name="simplified-danfe-for-model-55-fiscal-receipt"></a>DANFE simplificado para o recibo fiscal modelo 55

Além da [lista comum de campos personalizados para DANFE](latam-bra-nfce.md#custom-fields-for-danfe-fiscal-receipts), um DANFE simplificado para o recibo fiscal modelo 55 pode incluir os campos personalizados descritos nesta seção.

### <a name="configure-custom-fields-so-that-they-can-be-used-in-receipt-formats-for-sales-receipts"></a>Configurar campos personalizados para que possam ser usados em formatos de recibos de vendas

Adicione os seguintes rótulos de PDV à seção **PDV** da página **Texto do idioma**.

| ID do Idioma | ID do texto | Texto                                      |
|-------------|---------|-------------------------------------------|
| pt-BR       | 900101  | Código de barras                                   |
| pt-BR       | 900102  | Bloco 1 do código de barras (22 dígitos)               | 
| pt-BR       | 900103  | Bloco 2 do código de barras (22 dígitos)               | 

Na página **Campos personalizados**, adicione os seguintes registros para os campos personalizados nos layouts de recibo. Os valores de **ID do texto da legenda** devem corresponder aos valores de **ID do texto** especificados na página **Texto do idioma**.

| Nome                            | Tipo    | ID do texto da legenda |
|---------------------------------|---------|-----------------|
| BARCODE\_BR                     | Recebimento | 900101          |
| FISCALDOCUMENTBARCODEFIRST\_BR  | Recebimento | 900102          |
| FISCALDOCUMENTBARCODESECOND\_BR | Recebimento | 900103          |

### <a name="configure-receipt-formats"></a>Configurar formatos de recibo

Para cada formato de recibo necessário, altere o valor do campo **Comportamento de impressão** para **Sempre imprimir**.

No designer de formato de recibo, adicione os seguintes campos personalizados às seções de recibo apropriadas. Os nomes de campo correspondem aos valores de texto do idioma que você definiu na seção anterior.

- **Cabeçalho:** Adicione os seguintes campos:

    - **Código de barras** – Você pode adicionar um campo de código de barras ao DANFE simplificado para recibos fiscais do modelo 55 para devoluções.
    - **Bloco 1 do código de barras**, **Bloco 2 do código de barras** – Você pode adicionar campos de código de barras de 22 dígitos ao DANFE simplificado para recibos fiscais modelo 55 no caso de devoluções que são impressas em papel de recibo. O código de barras é uma representação gráfica do valor da **Chave de acesso** que é dividida em duas partes, cada uma com 22 dígitos.

Para mais informações sobre como trabalhar com formatos de recibo, consulte [Configurar e criar formatos de recibo](../receipt-templates-printing.md).

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil](latam-bra-nfce.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Registro adiado de documentos NFC-e emitidos no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)

[Configurar e criar formatos de recibo](../receipt-templates-printing.md).
