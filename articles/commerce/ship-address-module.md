---
title: módulo de endereço de remessa
description: Este tópico abrange o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 6a5eb69c7746be419779b1a844ee35ec375a324c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985627"
---
# <a name="shipping-address-module"></a>módulo de endereço de remessa

[!include [banner](includes/banner.md)]

Este tópico descreve o módulo de endereço de remessa e explica como configurá-lo no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O módulo de endereço de remessa permite que os clientes adicionem ou selecionem o endereço de remessa para uma ordem durante o o fluxo de finalização de compra. Se o cliente estiver conectado, quaisquer endereços que foram salvos anteriormente para esse cliente serão exibidos e o cliente poderá selecionar entre eles. O cliente também pode adicionar um novo endereço. O módulo de endereço de remessa é usado para todos os itens em uma ordem que exija remessa.

Os formatos de endereço de remessa podem ser definidos na sede do Commerce para cada país ou região, e o módulo de endereço de remessa reforça as regras específicas do país/região.

Quando os clientes inserem um endereço de remessa durante o fluxo de finalização de compra, eles têm a opção de salvar o endereço como o endereço principal. Esta opção é exibida somente se o cliente estiver conectado.

Embora o módulo de endereço de remessa não forneça validação de endereço, essa funcionalidade pode ser implementada por meio da personalização.

A ilustração a seguir mostra um exemplo de um novo módulo de endereço de remessa em uma página de finalização de compra.

![Exemplo de um módulo de endereço de remessa em uma página de finalização de compra](./media/ecommerce-shippingaddress.PNG)

## <a name="module-properties"></a>Propriedades do módulo

| Nome da propriedade | Valores | descrição |
|---------------|--------|-------------|
| Cabeçalho | Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um título opcional para o módulo de endereço de remessa. |
| Mostrar tipo de endereço | **Verdadeiro** ou **Falso** | Se essa propriedade opcional for definida como **Verdadeira**, um tipo de endereço, como **Residencial** ou **Comercial**, será exibido. Se nenhum tipo de endereço for especificado, o endereço será salvo automaticamente como **Tipo**=**Outro**. |

## <a name="add-a-shipping-address-module-to-a-checkout-page-and-set-the-required-properties"></a>Adicionar um módulo de endereço de remessa a uma página de finalização da compra e definir as propriedades necessárias

Um módulo de endereço de remessa pode ser adicionado somente a um módulo de finalização da compra. Para obter mais informações sobre como configurar o módulo endereço de remessa e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de ícone de carrinho](cart-icon-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de cartão-presente](add-giftcard.md)
