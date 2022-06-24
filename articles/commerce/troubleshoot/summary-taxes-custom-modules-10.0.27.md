---
title: Subtotal do resumo da ordem não inclui impostos sobre encargos durante o uso de módulos de resumo de ordem personalizados
description: Este artigo fornece orientação de solução de problemas que podem ajudar quando você usa módulos de resumo de ordens personalizados e o subtotal de resumo de ordens não inclui impostos sobre cobranças no cenário "o preço inclui imposto sobre vendas".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 260dcb6bc1585615195e32adfcd1da6bfbca294e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848828"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>Subtotal do resumo da ordem não inclui impostos sobre encargos durante o uso de módulos de resumo de ordem personalizados

Este artigo fornece orientação de solução de problemas que podem ajudar quando você usa módulos de resumo de ordens personalizados e o subtotal de resumo de ordens não inclui impostos sobre cobranças no cenário "o preço inclui imposto sobre vendas".

## <a name="description"></a>Descrição

A partir do lançamento do Microsoft Dynamics 365 Commerce versão 10.0.27, as seguintes alterações foram feitas no cenário "o preço inclui impostos sobre vendas" para fornecer uma experiência consistente em módulos de resumo de pedidos nas páginas do site de comércio eletrônico.

- Dois novos campos foram adicionados: **TaxOnShippingCharge** e **TaxOnNonShippingCharges**.
- As interfaces de programação de aplicativos (APIs) **GetSalesOrderBySalesId** e **GetSalesOrderByTransactionId** têm valores precisos para os campos a seguir no cenário "o preço inclui imposto sobre vendas":

    - SubtotalSalesAmount
    - SubtotalAmountWithoutTax
    - SubtotalAmount
    - ShippingChargeAmount
    - OtherChargeAmount

Contudo, se você estiver usando módulos de resumo de pedidos personalizados, essas alterações podem afetar os valores do subtotal do resumo do pedido ao não incluir impostos sobre cobranças.

## <a name="resolution"></a>Resolução

Se você estiver usando módulos de resumo de pedidos personalizados e não quiser herdar as alterações feitas no cenário "o preço inclui imposto sobre vendas" no Commerce versão 10.0.27 ou posterior, siga as instruções nesta seção.

Ao reverter para o comportamento de resumo do pedido anterior (antes da versão 10.0.27) dos campos **salesTransaction.SubtotalAmount** e **salesTransaction.SubtotalAmountWithoutTax**, você restaura a inclusão do valor total do imposto de cobrança (**TaxOnShippingCharge** e **TaxOnNonShippingCharges**) nos valores do subtotal (**SubtotalAmount** e **SubtotalAmountWithoutTax**).

Para reverter para o comportamento de resumo do pedido anterior, siga estas etapas.

1. No Commerce headquarters, abra a página de parâmetros do Commerce (**Varejo e Comércio \> Configuração do headquarters \> Parâmetros \> Parâmetros do Commerce**).
1. No painel de navegação esquerdo, selecione **Parâmetros de configuração**.
1. Adicione os seguintes parâmetros de configuração e defina o valor de cada um como **true**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Se você já usou o parâmetro de configuração **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** e deseja manter o mesmo comportamento para a propriedade **order.NetAmountWithoutTax**, adicione também o parâmetro de configuração **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** e defina seu valor como **true**.

## <a name="additional-resources"></a>Recursos adicionais

[Ocultar informações de divisão de imposto em resumos de ordens](../hide-taxes-breakup.md)
