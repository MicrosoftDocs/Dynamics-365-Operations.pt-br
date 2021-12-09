---
title: Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil
description: Este tópico fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para a funcionalidade de Adyen no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.
author: akviklis
ms.date: 09/09/2021
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
ms.openlocfilehash: 22b3f5577db937e2528599d206445022103aa3bb
ms.sourcegitcommit: f9fca3d55b47e615e5ef64669dab184e057ec234
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2021
ms.locfileid: "7862760"
---
# <a name="dynamics-365-payment-connector-for-adyen-in-commerce-pos-for-brazil"></a>Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil

[!Include[banner](../includes/banner.md)]

Este tópico fornece uma visão geral do Microsoft Dynamics 365 Payment Connector para a funcionalidade de Adyen no ponto de venda (PDV) do Microsoft Dynamics 365 Commerce para o Brasil.

O Dynamics 365 Payment Connector para Adyen é um conector de pagamento pronto para uso que oferece suporte a vários instrumentos de pagamento globalmente.

Os seguintes recursos específicos do Brasil do Dynamics 365 Payment Connector para Adyen são habilitados depois que você configura e implanta a localização do Commerce para o Brasil:

- Suporte para vendas feitas com cartões de uso duplo. Uma placa de uso duplo é um cartão de débito e um cartão de crédito.
- Salvamento de dados relacionados ao pagamento em transações de venda. Esses dados incluem o tipo de cartão, o código de transação (Número Sequencial Único \[NSU\]) e o número de Cadastro Nacional da Pessoa Jurídica (CNPJ) do comprador. Em seguida, os dados são relatados nas seguintes notas fiscais eletrônicas:

    - Nota Fiscal de Consumidor Eletrônica (NFC-e)
    - Nota Fiscal Eletrônica (NF-e)
    - Cupom Fiscal Eletrônico (CF-e)

## <a name="dual-purpose-cards"></a>Cartões de uso duplo

Os cartões de uso duplo (em outras palavras, cartões que são cartões de débito e cartões de crédito) são comuns no varejo brasileiro. Quando os clientes pagam por cartão em uma loja, eles selecionam se preferem pagar em débito ou crédito. A preferência de pagamento em cartão é registrada com Adyen.

## <a name="saving-of-payment-related-data"></a>Salvamento de dados relacionados ao pagamento

Quando uma venda de varejo é paga em cartão, as seguintes informações de pagamento são armazenadas no bloco de dados do pagamento com cartão do documento fiscal eletrônico. Ele também é transmitido para a Secretaria de Estado de Fazenda (SEFAZ).

- **Credenciamento** – o número do CNPJ da empresa que compra a transferência de pagamento.
- **Banner do cartão** – o tipo de cartão (por exemplo, Visa ou MasterCard).
- **Código da transação (NSU)** – o número de identificação da transação de venda que usa cartões.

## <a name="configure-the-dynamics-365-payment-connector-for-adyen-in-commerce-pos-for-brazil"></a>Configurar o Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil

Para configurar o Dynamics 365 Payment Connector para Adyen no PDV do Commerce para o Brasil, siga estas etapas.

1. Conclua as etapas de configuração descritas em [Configurar o Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector-setup.md).
1. No Commerce Headquarters, acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Processadores de cartão**.
1. Crie um registro e insira o número do CNPJ da empresa que compra o processador de cartão.
1. Acesse **Retail e Commerce \> Configuração do canal \> Métodos de pagamento \> Tipos de cartão**.
1. Especifique o número do CNPJ do processador do cartão inserido anteriormente para os tipos de pagamento eletrônico obrigatórios. Você deve selecionar um sistema de pagamento.
1. Selecione **Configuração de pagamento eletrônico** para adicionar os tipos de pagamento eletrônico criados antes dos métodos de pagamento da loja.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector.md)

[Configurar o Dynamics 365 Payment Connector para Adyen](../dev-itpro/adyen-connector-setup.md)

[Conector de pagamento Adyen para Dynamics 365](https://docs.adyen.com/plugins/microsoft-dynamics)
