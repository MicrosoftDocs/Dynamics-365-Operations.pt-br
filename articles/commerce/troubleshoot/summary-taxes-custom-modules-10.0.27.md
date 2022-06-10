---
title: O subtotal do resumo do pedido não inclui impostos sobre cobranças ao usar módulos personalizados de resumo do pedido
description: Este tópico fornece orientação de solução de problemas que podem ajudar quando você usa módulos de resumo de pedidos personalizados e o subtotal de resumo de pedidos não inclui impostos sobre cobranças no cenário "o preço inclui imposto sobre vendas".
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-04-22
ms.openlocfilehash: 1a47561a3ac984bc554b5b93546592237c16cf18
ms.sourcegitcommit: 48d094d083c1bd45c3d72f8b666926b48ec7ae35
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2022
ms.locfileid: "8767942"
---
# <a name="order-summary-subtotal-doesnt-include-taxes-on-charges-when-using-customized-order-summary-modules"></a>O subtotal do resumo do pedido não inclui impostos sobre cobranças ao usar módulos personalizados de resumo do pedido

Este tópico fornece orientação de solução de problemas que podem ajudar quando você usa módulos de resumo de pedidos personalizados e o subtotal de resumo de pedidos não inclui impostos sobre cobranças no cenário "o preço inclui imposto sobre vendas".

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

1. No Commerce Headquarters, abra a página de parâmetros do Commerce (**Varejo e Comércio \> Configuração do Headquarters \> Parâmetros \> Parâmetros do Commerce**).
1. No painel de navegação esquerdo, selecione **Parâmetros de configuração**.
1. Adicione os seguintes parâmetros de configuração e defina o valor de cada um como **true**:

    - IsLegacyTaxOnChargeInSubtotalAmountIncludedInTaxIncusiveEnabled
    - IsLegacyOrderSummaryHydrationEnabled

> [!NOTE]
> Se você já usou o parâmetro de configuração **IsUpdatedPriceIncludesTaxSubtotalCalculationEnabled** e deseja manter o mesmo comportamento para a propriedade **order.NetAmountWithoutTax**, adicione também o parâmetro de configuração **IsLegacyPriceIncludesTaxNetAmountWithoutTaxCalculationEnabled** e defina seu valor como **true**.

## <a name="additional-resources"></a>Recursos adicionais

[Ocultar informações de divisão de imposto em resumos de ordens](../hide-taxes-breakup.md)
