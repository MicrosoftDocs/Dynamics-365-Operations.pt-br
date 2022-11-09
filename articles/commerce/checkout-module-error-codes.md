---
title: Códigos de referência de erro do módulo de finalização da compra
description: Este artigo descreve os códigos de referência de erro do módulo de finalização da compra exibidos nas mensagens de erro do usuário no Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 10/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2022-09-20
ms.openlocfilehash: 952cb932522b4e0bb91be985e4f8974cb6cd8bc0
ms.sourcegitcommit: 435e69160dbd7f9c61b37ac4440285a5df144622
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728236"
---
# <a name="checkout-module-error-reference-codes"></a>Códigos de referência de erro do módulo de finalização da compra

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este artigo descreve os códigos de erro do módulo de finalização da compra exibidos nas mensagens de erro do usuário no Microsoft Dynamics 365 Commerce.

O Dynamics 365 Commerce introduziu referências de erro padronizadas que podem ser incluídas nos erros de finalização da compra no canal on-line que os clientes recebem. No Commerce versão 10.0.31 e posteriores, as mensagens de erro no módulo de finalização da compra incluem códigos de erro e não mostram informações desnecessárias para os clientes on-line. Os códigos se referem a erros que são detalhados no artigo.

Dependendo do erro encontrado, a tabela no artigo inclui os seguintes detalhes:

- Uma descrição da condição que causou o erro ou outros detalhes
- Informações a serem consideradas no ambiente ou nas configurações do conector de pagamento
- Informações que poderão ser referenciadas em um caso de suporte se ele exigir mais ajuda

## <a name="prerequisites"></a>Pré-requisitos

Para habilitar os códigos de referência de erro do módulo de check-out listado abaixo, no construtor de sites do seu site, vá para **Configurações de site \> Extensões** e na seção **Carrinho e de finalização da compra**, selecione **Ativar Mensagem de Exibição de Erro do Canal On-line Avançado**. 

## <a name="checkout-module-error-reference-codes"></a>Códigos de referência de erro do módulo de finalização da compra

Use a seguinte tabela para ver mais detalhes sobre as referências de códigos de erro fornecidas pelos clientes ou que acontecem na loja on-line. Role para a direita para exibir a coluna **Descrição do Erro**.

| Código de erro | Código de erro relacionado ao Dynamics | Descrição do erro |
| ---------- | ------------------------------ | ----------------- |
| CCR001     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardTypeMissingOrNotSupported | O pagamento não foi autorizado. O ID do tipo de cartão no **TokenizedPaymentCard** está faltando ou não é suportado. |
| CCR002     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePayment | Recusado. O pagamento não foi autorizado. |
| CCR003     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToAuthorizePaymentCardAdditionalContextRequired | O pagamento não foi autorizado. É necessário que o cliente insira informações adicionais. |
| CCR004     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToRetrieveCardPaymentAcceptResult | Infelizmente, ocorreu um problema. Não foi possível obter o resultado de aprovação do pagamento do cartão. Tente novamente ou entre em contato com o administrador do sistema. |
| CCR005     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentRequiresMerchantProperties | Não foi possível processar o pagamento porque há propriedades do comerciante faltando. Entre em contato com o administrador do sistema. |
| CCR006     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidPaymentRequest | Não foi possível recuperar o serviço para a operação. Analise a configuração da forma de pagamento do tipo de serviço selecionado. |
| CCR007     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | Um pagamento da conta do cliente já foi aplicado e apenas um deles pode ser realizado na transação. |
| CCR008     | Microsoft\_Dynamics\_Commerce\_Runtime\_MultipleCustomerAccountPaymentsNotAllowed | O limite da conta do cliente difere do valor devido. Tente usar outra forma de pagamento ou fale com o suporte ao cliente para obter ajuda. |
| CCR009     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsTotalAmountForCarryOutAndReturnItems | O pagamento da conta do cliente excede o valor total devido para os itens listados. Tente novamente mais tarde ou fale com o suporte para obter ajuda. |
| CCR010     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentUsingUnauthorizedAccount | O pagamento da conta do cliente exige uma conta própria ou uma conta de fatura correspondente em uma linha de forma de pagamento. |
| CCR011     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentExceedsCustomerAccountFloorLimit | Não é possível processar o pagamento de conta de um cliente no momento. Valor de limite de piso excedido. |
| CCR012     | Microsoft\_Dynamics\_Commerce\_Runtime\_CustomerAccountPaymentForCustomerWithoutAllowOnAccount | Este cliente não tem permissão para fazer pagamentos na conta. |
| CCR013     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToCancelPayment | Infelizmente, ocorreu um problema. Não foi possível cancelar o pagamento. Tente novamente. |
| CCR014     | Microsoft\_Dynamics\_Commerce\_Runtime\_UnableToReadCardTokenInfo | Ocorreu um erro ao processar o pagamento. Tente novamente mais tarde. |
| CCR015     | Microsoft\_Dynamics\_Commerce\_Runtime\_NotEnoughRewardPoints | O valor do pagamento do programa de fidelidade excede o limite permitido para o cartão de fidelidade usado nesta transação. |
| CCR016     | Microsoft\_Dynamics\_Commerce\_Runtime\_RefundAmountMoreThanAllowed | O valor do reembolso do programa de fidelidade excede o limite permitido para o cartão de fidelidade usado nesta transação. |
| CCR017     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidLoyaltyCardNumber | O número do cartão-fidelidade não foi encontrado. Ative o número do cartão de fidelidade ou insira o número de outro cartão e tente novamente. |
| CCR018     | Microsoft\_Dynamics\_Commerce\_Runtime\_BlockedLoyaltyCard | O número do cartão de fidelidade não está disponível. Insira o número de outro cartão e tente novamente. |
| CCR019     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoTenderLoyaltyCard | Este cartão de fidelidade não pode ser usado para resgate de pontos nesta transação. |
| CCR020     | Microsoft\_Dynamics\_Commerce\_Runtime\_GiftCardCurrencyMismatch | Ocorreu um erro no número do vale-presente. Tente usar outro vale-presente ou fale com o suporte ao cliente para obter ajuda. |
| CCR021     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAmountExceedsGiftBalance | O valor excede o saldo do vale-presente. Insira outro valor e tente novamente. |
| CCR022     | Microsoft\_Dynamics\_Commerce\_Runtime\_NoMoreThanOneLoyaltyTender | A transação não pode conter mais de uma linha de pagamento do programa de fidelidade. |
| CCR023     | Microsoft\_Dynamics\_Commerce\_Runtime\_PaymentAlreadyVoided | As informações de pagamento estão ausentes ou incorretas. Verifique as informações de pagamento e tente novamente. |
| CCR024     | Microsoft\_Dynamics\_Commerce\_Runtime\_FraudRisk | Não é possível processar a ordem no momento. Tente novamente mais tarde. |
| CCR025     | Expiração do front-end da API de finalização da compra | A operação de front-end expirou. Verifique se a ordem foi processada no Dynamics 365 Commerce headquarters. |
| CCR026     | O valor original autorizado mudou | O valor da ordem mudou em relação ao valor da autorização original que foi processada com o gateway do pagamento. Isso pode ter acontecido porque o cupom, a promoção ou oferta expirou. |
| CCR027     | Microsoft\_Dynamics\_Commerce\_Runtime\_InvalidCartVersion | Ocorreu um erro ao processar um pagamento. A referência fornecida à API do Carrinho não corresponde ao que era esperado (possível inconsistência durante o processo de finalização da compra). |
| CCR028     | Microsoft\_Dynamics\_Commerce\_Runtime\_MissingRequiredCartTenderLines | Ocorreu um erro na forma de pagamento. Fale com o suporte para analisar as configurações da sua conta ou tente novamente usando outra forma de pagamento. |

## <a name="additional-resources"></a>Recursos adicionais

[Perguntas frequentes sobre pagamentos](dev-itpro/payments-retail.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)
