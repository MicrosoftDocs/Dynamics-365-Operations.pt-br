---
title: Dynamics 365 Payment Connector para Adyen no Commerce POS para o Brasil
description: Este artigo fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para a funcionalidade de Adyen no PDV (ponto de venda) do Microsoft Dynamics 365 Commerce para o Brasil.
author: akviklis
ms.date: 03/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2021-08-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: a7400d2f81650abcb66ef2b44eb6480adb37173c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881750"
---
# <a name="dynamics-365-payment-connector-for-adyen-in-commerce-pos-for-brazil"></a>Dynamics 365 Payment Connector para Adyen no Commerce POS para o Brasil

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para a funcionalidade de Adyen no PDV (ponto de venda) do Microsoft Dynamics 365 Commerce para o Brasil.

O Dynamics 365 Payment Connector para Adyen é um conector de pagamento pronto para uso que oferece suporte a vários instrumentos de pagamento globalmente.

Os seguintes recursos específicos do Brasil do Dynamics 365 Payment Connector para Adyen são habilitados depois que você configura e implanta a localização do Commerce para o Brasil:

- Suporte para vendas feitas com cartões de uso duplo. Uma placa de uso duplo é um cartão de débito e um cartão de crédito.
- Salvamento de dados relacionados ao pagamento em transações de venda. Esses dados incluem o tipo de cartão, o código de transação (Número Sequencial Único \[NSU\]) e o número de Cadastro Nacional da Pessoa Jurídica (CNPJ) do comprador. Em seguida, os dados são relatados nas seguintes notas fiscais eletrônicas:

    - Nota Fiscal de Consumidor Eletrônica (NFC-e)
    - Nota Fiscal Eletrônica (NF-e)
    - Cupom Fiscal Eletrônico (CF-e)

- Suporte para pagamento em prestações. Essa opção de pagamento é popular no Brasil, pois os compradores podem receber bens ou serviços imediatamente, mas distribuir o custo por vários meses.

## <a name="dual-purpose-cards"></a>Cartões de uso duplo

Os cartões de uso duplo (em outras palavras, cartões que são cartões de débito e cartões de crédito) são comuns no varejo brasileiro. Quando os clientes pagam por cartão em uma loja, eles selecionam se preferem pagar em débito ou crédito. A preferência de pagamento em cartão é registrada com Adyen.

## <a name="saving-of-payment-related-data"></a>Salvamento de dados relacionados ao pagamento

Quando uma venda de varejo é paga em cartão, as seguintes informações de pagamento são armazenadas no bloco de dados do pagamento com cartão do documento fiscal eletrônico. Ele também é transmitido para a Secretaria de Estado de Fazenda (SEFAZ).

- **Credenciamento** – o número do CNPJ da empresa que compra a transferência de pagamento.
- **Banner do cartão** – o tipo de cartão (por exemplo, Visa ou MasterCard).
- **Código da transação (NSU)** – o número de identificação da transação de venda que usa cartões.

## <a name="payment-in-installments"></a>Pagamento em prestações

Este recurso aproveita o recurso interno de [parcelas em cartão de crédito](https://docs.adyen.com/payment-methods/cards/credit-card-installments) do conector. Ele estende o conector de pagamento para que dê suporte ao pagamento em prestações em lojas localizadas no Brasil.

Um cliente de varejo que paga por cartão pode optar por pagar em prestações. O caixa pode selecionar **Prestações** como o tipo de preferência de pagamento e especificar o número de pagamentos que o cliente solicita. As informações de preferência de pagamento são passadas para Adyen, junto com outros dados de pagamento de cartão de crédito. O processamento de prestação adicional é realizado por Adyen e pelo banco do cliente. O valor de compra é dividido no número especificado de pagamentos mensais iguais. Esses pagamentos são cobrados do cartão de crédito do cliente a cada 30 dias até que a compra seja paga inteira.

## <a name="configure-the-dynamics-365-payment-connector-for-adyen-in-commerce-pos-for-brazil"></a>Configurar o Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil

Para configurar o Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil, siga estas etapas.

1. Conclua as etapas de configuração descritas em [Configurar o Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector-setup.md).
1. No Commerce Headquarters, acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Processadores de cartão**.
1. Crie um registro e insira o número do CNPJ da empresa que compra o processador de cartão.
1. Acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Tipos de cartão**.
1. Especifique o número do CNPJ do processador do cartão inserido anteriormente para os tipos de pagamento eletrônico obrigatórios. Você deve selecionar um sistema de pagamento.
1. Selecione **Configuração de pagamento eletrônico** para adicionar os tipos de pagamento eletrônico criados antes dos métodos de pagamento da loja.
1. Configure o componente de extensão de estação de hardware para o conector de pagamento para Adyen em PDV do Brasil. Para obter mais informações sobre como configurar essa extensão, consulte o [componente Payments.Connector.Adyen.Device.Brazil](latam-bra-deployment.md#paymentsconnectoradyendevicebrazil-component).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector.md)

[Configurar o Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector-setup.md)

[Conector de pagamento Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)

[Documentação do Adyen: parcelas em cartão de crédito](https://docs.adyen.com/payment-methods/cards/credit-card-installments)
