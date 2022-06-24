---
title: A opção Salvar para o próximo pagamento não aparece
description: Este artigo fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção Salvar para o próximo pagamento não aparecer no método de pagamento na página de finalização de compra de um site de comércio eletrônico.
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
ms.openlocfilehash: efa04c87f78c376fd00da1b26aedb9e8b428dfa5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871546"
---
# <a name="save-for-my-next-payment-option-doesnt-appear"></a>A opção "Salvar para o próximo pagamento" não aparece

[!include [banner](../../includes/banner.md)]

Este artigo fornece orientação de solução de problemas que pode ser útil quando a caixa de seleção **Salvar para o próximo pagamento** não aparecer no **Método de pagamento** na página de finalização de compra de um site de comércio eletrônico.

## <a name="description"></a>descrição

A caixa de seleção **Salvar para o próximo pagamento** não aparece na seção **Método de pagamento** em uma página de finalização de compra de um site de comércio eletrônico.

A ilustração a seguir mostra um exemplo de uma página de finalização de compra que inclui a caixa de seleção **Salvar para meu próximo pagamento**.

![Caixa de seleção Salvar para meu próximo pagamento no módulo de Pagamento.](media/payment-module-save-payment.jpg)

## <a name="resolution"></a>Resolução

### <a name="verify-that-the-dynamics-365-payment-connector-for-adyen-is-correctly-configured-in-commerce-headquarters"></a>Verifique se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente no Commerce headquarters

Para verificar se o Conector de Pagamento do Dynamics 365 para Adyen está configurado corretamente no Commerce headquarters, siga estas etapas.

1. Acesse **Varejo e Comércio \> Canais \> Lojas Online**.
1. Selecione a loja online.
1. Na guia rápida **Contas de pagamento**, verifique se o campo **Permitir salvar informações de pagamento no comércio eletrônico** está definido como **Verdadeiro**.

![Campo Permitir salvar informações de pagamento no comércio eletrônico no Commerce headquarters.](media/payment-connector-save-payment.jpg)

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de pagamento](../payment-module.md)

[Salvando meios de pagamento online com o conector para Adyen](../dev-itpro/adyen-connector-listPI.md)
