---
title: Erro O tipo de pagamento deve ser cartão de crédito na página ordem de venda
description: Este artigo fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 71c5cbaf574866c74e222f4d67132004327db8fe
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285623"
---
# <a name="payment-type-must-be-credit-card-error-on-the-sales-order-page"></a>O erro "O tipo de pagamento deve ser cartão de crédito" na página ordem de venda

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientação de solução de problemas que pode ser útil quando uma mensagem de erro é mostrada na página ordem de venda após a sincronização de uma ordem.

## <a name="description"></a>descrição

Ao abrir a página ordem de venda após a sincronização de uma ordem, você recebe a seguinte mensagem de erro: "O tipo de pagamento deve ser cartão de crédito, pois o número do cartão de crédito foi especificado".

![Erro O tipo de pagamento deve ser cartão de crédito.](media/payment-type-must-be-credit-card.jpg)

## <a name="resolution"></a>Resolução

### <a name="set-the-payment-type-in-commerce-headquarters"></a>Definir o tipo de pagamento no Commerce headquarters

1. Acesse **Contas a receber \> Configuração de pagamento \> Termos de pagamento**.
1. Na navegação à esquerda, selecione as condições de pagamento.
1. No campo **Tipo de pagamento**, verifique se **Cartão de crédito** está selecionado.

## <a name="additional-resources"></a>Recursos adicionais

[Lançamento de vendas e pagamentos online](../tasks/posting-online-sales-payments.md)
