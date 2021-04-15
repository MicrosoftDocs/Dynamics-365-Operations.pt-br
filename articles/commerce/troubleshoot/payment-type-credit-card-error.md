---
title: Erro O tipo de pagamento deve ser cartão de crédito na página ordem de venda
description: Este tópico fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: eabc64acc74645c7e6c7c4ab5794ed9fdb9dc997
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801666"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>O erro "O tipo de pagamento deve ser cartão de crédito" na página ordem de venda

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.

## <a name="description"></a>descrição

Ao abrir a página ordem de venda após a sincronização de uma ordem, você recebe a seguinte mensagem de erro: "O tipo de pagamento deve ser cartão de crédito, pois o número do cartão de crédito foi especificado".

![Erro O tipo de pagamento deve ser cartão de crédito](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Resolução

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Definir o tipo de pagamento no Commerce Headquarters

1. Vá para **Contas a receber \> Configuração de pagamento \> Termos de pagamento**.
1. Na navegação à esquerda, selecione as condições de pagamento.
1. No campo **Tipo de pagamento**, verifique se **Cartão de crédito** está selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Lançamento de vendas e pagamentos online](../tasks/posting-online-sales-payments.md)
