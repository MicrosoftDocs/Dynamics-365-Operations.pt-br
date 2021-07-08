---
title: Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil
description: Este tópico dá uma visão geral da funcionalidade de cancelamento e devolução para documentos NFC-e no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: v-ankvik
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
ms.author: v-ankvik
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 5b2ea57de34c22b1cc95318d2e73a376744a82b1
ms.sourcegitcommit: cee7887282d372c756c5c11f76684315f249bba5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6303527"
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

Além da [lista comum de campos personalizados para DANFE](latam-bra-nfce.md), um DANFE simplificado para o recibo fiscal modelo 55 pode incluir o seguinte campo personalizado:

- **Código de barras** – Você pode adicionar um campo de código de barras ao DANFE simplificado para recibos fiscais do modelo 55 para devoluções.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil](latam-bra-nfce.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Registro adiado de documentos NFC-e emitidos no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)
