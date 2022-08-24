---
title: APIs de preços do Commerce
description: TEste artigo descreve várias APIs de preços fornecidas pelo mecanismo de preços do Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 08/10/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: boycez
ms.search.validFrom: 2022-07-15
ms.openlocfilehash: d694c44f6987fbf2a360869d2fb2a2fbaf0d2e4d
ms.sourcegitcommit: 924dbcdc6b03f6a7ae3a07378ec405fd15c7e359
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2022
ms.locfileid: "9294104"
---
# <a name="commerce-pricing-apis"></a>APIs de preços do Commerce

[!include [banner](../includes/banner.md)]

TEste artigo descreve várias APIs de preços fornecidas pelo mecanismo de preços do Microsoft Dynamics 365 Commerce.

O mecanismo de preços do Dynamics 365 Commerce fornece as seguintes APIs do Retail Server que podem ser consumidas por aplicativos externos para dar suporte a vários cenários de definição de preços:

- **GetActivePrices** – esta API obtém o preço calculado de um produto, incluindo descontos simples.
- **CalculateSalesDocument** – esta API calcula preços e descontos para produtos em determinadas quantidades, caso eles sejam comprados juntos.
- **GetAvailablePromotions** – esta API obtém descontos aplicáveis para produtos no carrinho. 
- **AddCoupons** – esta API adiciona cupons a um carrinho.
- **RemoveCoupons** – esta API remove os cupons de um carrinho.

Para obter mais informações sobre como consumir APIs do Retail Server em aplicativos externos, consulte [Consumir interfaces de programação de aplicativo do Retail Server em aplicativos externos](dev-itpro/consume-retail-server-api.md).

## <a name="getactiveprices"></a>GetActivePrices

A API *GetActivePrices* foi introduzida na versão 10.0.4 do Commerce Version. Essa API obtém o preço calculado de um produto, incluindo descontos simples. Ela não calcula os descontos combinados e supõe que cada produto em uma solicitação de API tem uma quantidade de 1. Essa API também pode usar uma lista de produtos como entrada e consultar o preço de produtos individuais em massa.

A API *GetActivePrices* oferece suporte às funções **Funcionário**, **Cliente**, **Anônimo** e **Aplicativo** do Commerce.

O principal caso de uso para a API *GetActivePrices* é a página de detalhes do produto (PDP), em que os varejistas desejam apresentar o melhor preço para um produto, incluindo qualquer desconto efetivo.

A tabela a seguir mostra os parâmetros de entrada para a API *GetActivePrices*.

| Nome                                    | Subnome | Tipo | Obrigatório/Opcional | Descrição |
|-----------------------------------------|----------|------|-------------------|-------------|
| projectDomain                           | | ProjectionDomain | Necessário | |
|                                         | ChannelId | long | Necessário | |
|                                         | CatalogId | long | Necessário | |
| productIds                              | | IEnumerable\<long\> | Necessário | A lista de produtos para os quais serão calculados os preços. |
| activeDate                              | | DateTimeOffset | Necessário | A data em que os preços serão calculados. |
| customerId                              | | cadeia de caracteres | Opcional | O número da conta do cliente. |
| affiliationLoyaltyTiers                 | | IEnumerable\<AffiliationLoyaltyTier\> | Opcional | As camadas de afiliação e do programa de fidelidade. |
|                                         | AffiliationId | long | Necessário | A ID da afiliação. |
|                                         | LoyaltyTierId | long | Opcional | A ID da camada do programa de fidelidade. |
| includeSimpleDiscountsInContextualPrice | | bool | Opcional | Defina este parâmetro como **verdadeiro** para incluir descontos simples no cálculo de definição de preços. O valor padrão é **false**. |
| includeVariantPriceRange                | | bool | Opcional | Defina este parâmetro como **verdadeiro** para obter os preços mínimo e máximo entre todas as grades de um produto mestre. O valor padrão é **false**. |
| includeAttainablePricesAndDiscounts     | | bool | Opcional | Defina este parâmetro como **verdadeiro** para obter preços e descontos mais acessíveis. O valor padrão é **false**. |

**Corpo da solicitação de amostra**

```json
{
    "projectDomain": 
    {
        "ChannelId": 5637144592,
        "CatalogId": 0
    },
    "productIds": 
    [
        68719489871
    ],
    "activeDate": "2022-06-20T14:40:05.873+08:00",
    "includeSimpleDiscountsInContextualPrice": true,
    "includeVariantPriceRange": false
}
```

**Corpo da resposta de amostra**

```json
{
    "value": 
    [
        {
            "ProductId": 68719489871,
            "ListingId": 68719489871,
            "BasePrice": 0,
            "TradeAgreementPrice": 0,
            "AdjustedPrice": 0,
            "MaxVariantPrice": 0,
            "MinVariantPrice": 0,
            "CustomerContextualPrice": 0,
            "DiscountAmount": 0,
            "CurrencyCode": "USD",
            "ItemId": "82000",
            "InventoryDimensionId": null,
            "UnitOfMeasure": "ea",
            "ValidFrom": "2022-06-20T01:40:05.873-05:00",
            "ProductLookupId": 0,
            "ChannelId": 5637144592,
            "CatalogId": 0,
            "SalesAgreementPrice": 0,
            "PriceSourceTypeValue": 1,
            "DiscountLines": [],
            "AttainablePriceLines": [],
        }
    ]
}
```

## <a name="calculatesalesdocument"></a>CalculateSalesDocument

A API *CalculateSalesDocument* foi introduzida na versão 10.0.25 do Commerce. Esta API calcula preços e descontos para produtos em determinadas quantidades, caso eles sejam comprados juntos. O cálculo de definição de preços por trás da API *CalculateSalesDocument* considera descontos de uma única linha e de várias linhas.

O principal caso de uso da API *CalculateSalesDocument* é o cálculo de definição de preços em cenários nos quais o contexto de carrinho total não é mantido (como cotações de venda). Os cenários no PDV (ponto de venda) e comércio eletrônico do Commerce também podem se beneficiar deste caso de uso. Um preço total menor quando os itens do carrinho são calculados como um conjunto (por exemplo, para pacotes discretos, produtos vinculados ou recomendados ou produtos que já foram adicionados ao carrinho) podem persuadir os clientes a adicionar produtos ao carrinho.

O modelo de dados para a solicitação e a resposta da API *CalculateSalesDocument* é **Carrinho**. No entanto, no contexto dessa API, o modelo de dados é denominado **SalesDocument**. Como a maioria das propriedades é opcional, e apenas algumas delas afetam o cálculo de definição de preços, somente os campos relacionados a preços são mostrados na tabela a seguir. Não é recomendável que outros campos sejam envolvidos na solicitação da API.

O escopo da API *CalculateSalesDocument* é apenas o cálculo de preços e descontos. Os impostos e os encargos não estão envolvidos.

A tabela a seguir mostra os parâmetros de entrada no objeto chamado **salesDocument**.

| Nome             | Subnome | Tipo | Obrigatório/Opcional | Descrição |
|------------------|----------|------|-------------------|-------------|
| Id               | | cadeia de caracteres | Necessário | O identificador do documento de venda. |
| CartLines        | | IList\<CartLine\> | Opcional | A lista de linhas para as quais serão calculados os preços e descontos. |
|                  | ID do Produto | long | Necessário no escopo da CartLine | A ID de registro do produto. |
|                  | ItemId | cadeia de caracteres | Opcional | O identificador do item. Se um valor for fornecido, ele deve corresponder ao valor do parâmetro **ProductID**. |
|                  | InventoryDimensionId | cadeia de caracteres | Opcional | O identificador de dimensão do estoque. Se um valor for fornecido, a combinação dos valores de **ItemId** e **InventoryDimensionId** deverá corresponder ao valor do parâmetro **ProductId**. |
|                  | Quantidade | decimal | Necessário no escopo da CartLine | A quantidade do produto. |
|                  | UnitOfMeasureSymbol | cadeia de caracteres | Opcional | A unidade do produto. Por padrão, se um valor não for fornecido, a API usará a unidade de venda do produto. |
| CustomerId       | | cadeia de caracteres | Opcional | O número da conta do cliente. |
| LoyaltyCardId    | | cadeia de caracteres | Opcional | O identificador do cartão-fidelidade. Qualquer conta de cliente associada ao cartão-fidelidade deve corresponder ao valor do parâmetro **CustomerId** (se for fornecido). O cartão-fidelidade não será considerado se não for encontrado ou seu status for **Bloqueado**. |
| AffiliationLines | | IList\<AffiliationLoyaltyTier\> | Opcional | Linhas da camada de fidelidade da afiliação. Se os valores de **CustomerId** e/ou **LoyaltyCardId** forem fornecidos, as linhas da camada de fidelidade de afiliação correspondentes serão mescladas com as linhas fornecidas no valor **AffiliationLines**. |
|                  | AffiliationId | long | Necessário no escopo de AffiliationLoyaltyTier | A ID de registro da afiliação. |
|                  | LoyaltyTierId | long | Necessário no escopo de AffiliationLoyaltyTier | A ID do registro da camada de fidelidade. |
|                  | AffiliationTypeValue | int | Necessário no escopo de AffiliationLoyaltyTier | Um valor que indica se a linha de afiliação é do tipo **Geral** (**0**) ou do tipo **Fidelidade** (**1**). Se esse parâmetro for definido como **0**, a API usará o valor **AffiliationId** como o identificador e ignorará o valor **LoyaltyTierId**. Se definido como **1**, a API usará o valor de **LoyaltyTierId** como o identificador e ignorará o valor **AffiliationId**. |
|                  | ReasonCodeLines | Coleção\<ReasonCodeLine\> | Necessário no escopo de AffiliationLoyaltyTier | Linhas do código do motivo. Esse parâmetro não tem efeito sobre o cálculo de preços, mas é necessário como parte do objeto **AffiliationLoyaltyTier**. |
|                  | CustomerId | cadeia de caracteres | Necessário no escopo de AffiliationLoyaltyTier | O número da conta do cliente. |
| Cupons          | | IList\<Coupon\> | Opcional | Os cupons que não são aplicáveis (inativos, expirados ou não) não serão considerados no cálculo de preços. |
|                  | Código | cadeia de caracteres | Necessário no escopo de Coupon | O código do cupom. |
|                  | CodeId | cadeia de caracteres | Opcional | O identificador do código do cupom. Se um valor for fornecido, ele deverá corresponder ao valor do parâmetro **Code**. |
|                  | DiscountOfferId | cadeia de caracteres | Opcional | O identificador do desconto. Se um valor for fornecido, ele deverá corresponder ao valor do parâmetro **Code**. |

**Corpo da solicitação de amostra**

```json
{
    "salesDocument": 
    {
        "Id": "CalculateSalesDocument",
        "CartLines": 
        [
            {
                "ProductId": 68719491408,
                "ItemId": "91003",
                "InventoryDimensionId": "",
                "Quantity": 1,
                "UnitOfMeasureSymbol": "ea"
            },
            {
                "ProductId": 68719493014,
                "Quantity": 2,
                "UnitOfMeasureSymbol": "ea"
            }
        ],
        "CustomerId": "3003",
        "AffiliationLines": 
        [
            {
                "AffiliationId": 68719476742,
                "LoyaltyTierId": 0,
                "AffiliationTypeValue": 0,
                "ReasonCodeLines": [],
                "CustomerId": null
            }
        ],
        "LoyaltyCardId": "55103",
        "Coupons": 
        [
            {
                "CodeId": "CODE-0005",
                "Code": "CPN0004",
                "DiscountOfferId": "ST100077"
            }
        ]
    }
}
```

O objeto do carrinho inteiro é devolvido como o corpo da resposta. Para verificar preços e descontos, você deve focar nos campos na tabela a seguir.

| Nome           | Subnome | Tipo | Descrição |
|----------------|----------|------|--------------|
| NetPrice       | | decimal | O preço líquido do documento de vendas inteiro antes dos descontos aplicados. |
| DiscountAmount | | decimal | O valor total do desconto do documento de vendas inteiro. |
| TotalAmount    | | decimal | O valor total do documento de vendas inteiro. |
| CartLines      | | IList\<CartLine\> | Linhas calculadas que incluem detalhes de preço e desconto. |
|                | Preço | decimal | O preço unitário do produto. |
|                | NetPrice | decimal | O preço líquido da linha antes dos descontos serem aplicados. (= *Preço* &times; *Quantidade*). |
|                | DiscountAmount | decimal | O valor do desconto. |
|                | TotalAmount | decimal | O resultado do preço total final da linha. |
|                | PriceLines | IList\<PriceLine\> | Detalhes de preço, incluindo a origem do preço (preço base, ajuste de preço ou contrato comercial) e o valor. |
|                | DiscountLines | IList\<DiscountLine\> | Detalhes do desconto. |

## <a name="getavailablepromotions"></a>GetAvailablePromotions 

Dado um carrinho com várias linhas de carrinho, a API *GetAvailablePromotions* retorna todos os descontos aplicáveis para as linhas do carrinho. 

O principal caso de uso para a API *GetAvailablePromotions* é a página do carrinho, em que os varejistas desejam exibir descontos aplicados ou cupons disponíveis para o carrinho atual.

A tabela a seguir mostra os parâmetros de entrada para a API *GetAvailablePromotions*.

| Nome        | Tipo | Obrigatório/Opcional | Descrição |
|-------------|------|-------------------|-------------|
| chave         | cadeia de caracteres | Necessário | A ID do carrinho. |
| cartLineIds | IEnumerable\<string\> | Opcional | Defina este parâmetro para retornar descontos somente para as linhas do carrinho selecionado. |

**Corpo da resposta de amostra**

```json
{
    "value": 
    [
        {
            "LineId": "f495ffa507bc4f63a47a409cd8713dd7",
            "Promotion": {
                "OfferId": "ST100012",
                "OfferName": "Loyalty 5% off over $100",
                "PeriodicDiscountTypeValue": 4,
                "IsDiscountCodeRequired": false,
                "ValidationPeriodId": null,
                "AdditionalRestrictions": null,
                "Description": "All loyalty members get 5% with transaction total above $10 unless some exclusive or best price discounts are already applied on the transaction",
                "ValidFromDate": "2022-06-20T06:52:56.2460219Z",
                "ValidToDate": "2022-06-20T06:52:56.2460224Z",
                "CouponCodes": [],
                "ValidationPeriod": null
            }
        }
    ]
}
```

## <a name="addcoupons"></a>AddCoupons

A API de *Addcupons* oferece suporte à adição de uma lista de cupons a um carrinho. Ela retorna o objeto do carrinho depois que os cupons são adicionados.

A tabela a seguir mostra os parâmetros de entrada para a API *AddCoupons*.

| Nome                 | Tipo | Obrigatório/Opcional | Descrição |
|----------------------|------|-------------------|-------------|
| chave                  | cadeia de caracteres | Necessário | A ID do carrinho. |
| couponCodes          | IEnumerable\<string\> | Necessário | Os códigos de cupom a serem adicionados ao carrinho. |
| isLegacyDiscountCode | bool | Opcional | Defina este parâmetro como **verdadeiro** para indicar que o cupom é um código de desconto herdado. O valor padrão é **false**. |

## <a name="removecoupons"></a>RemoveCoupons

A API *RemoveCoupons* oferece suporte à remoção de uma lista de cupons de um carrinho. Ela retorna o objeto do carrinho depois que os cupons são removidos.

A tabela a seguir mostra os parâmetros de entrada para a API *RemoveCoupons*.

| Nome        | Tipo | Obrigatório/Opcional | Descrição |
|-------------|------|-------------------|-------------|
| chave         | cadeia de caracteres | Necessário | A ID do carrinho. |
| couponCodes | IEnumerable\<string\> | Necessário | Os códigos de cupom a serem removidos do carrinho. |

[!INCLUDE[footer-include](../includes/footer-banner.md)]
