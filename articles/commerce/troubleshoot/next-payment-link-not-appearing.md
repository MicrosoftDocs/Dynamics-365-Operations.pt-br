---
title: A opção Salvar para o próximo pagamento não aparece
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção Salvar para o próximo pagamento não aparecer no método de pagamento na página de finalização de compra de um site de comércio eletrônico.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4887cde3e4243ae7a4da6402782e69e780ae20331ed80df63ba1239ef5187e41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6769262"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>A opção "Salvar para o próximo pagamento" não aparece

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção **Salvar para o próximo pagamento** não aparecer no **Método de pagamento** na página de finalização de compra de um site de comércio eletrônico.

## <a name="description"></a>descrição

A caixa de seleção **Salvar para o próximo pagamento** não aparece na seção **Método de pagamento** em uma página de finalização de compra de um site de comércio eletrônico.

A ilustração a seguir mostra um exemplo de uma página de finalização de compra que inclui a caixa de seleção **Salvar para meu próximo pagamento**.

![Caixa de seleção Salvar para meu próximo pagamento no módulo de Pagamento.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Resolução

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Verifique se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente na matriz do Commerce

Para verificar se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente na matriz do Commerce, siga estas etapas.

1. Acesse **Varejo e Comércio \> Canais \> Lojas Online**.
1. Selecione a loja online.
1. Na guia rápida **Contas de pagamento**, verifique se o campo **Permitir salvar informações de pagamento no comércio eletrônico** está definido como **Verdadeiro**.

![Campo Permitir salvar informações de pagamento no comércio eletrônico na matriz do Commerce.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de pagamento](../payment-module.md)

[Salvando meios de pagamento online com o conector para Adyen](../dev-itpro/adyen-connector-listPI.md)
