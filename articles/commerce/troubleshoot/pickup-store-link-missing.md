---
title: A opção Retirar este item não aparece nas páginas de detalhes do carrinho ou do produto
description: Este tópico fornece orientações de solução de problemas que podem ajudar quando a opção de retirada na loja não aparece na página do carrinho ou nas páginas de detalhes do produto.
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
ms.openlocfilehash: 46eeed18bb547035603d7e9a01e8f131a2393f01
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801618"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>A opção "Retirar este item" não aparece nas páginas de detalhes do carrinho ou do produto

[!include [banner](../../includes/banner.md)]

Este tópico fornece orientações de solução de problemas que podem ajudar quando a opção de retirada na loja não aparece na página do carrinho ou nas páginas de detalhes do produto.

## <a name="description"></a>descrição

O botão **Retirar este item** não aparece nas páginas de detalhes do carrinho ou do produto.

A ilustração a seguir mostra um exemplo de uma página que inclui o botão **Retirar este item**.

![Botão Retirar este item](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Resolução

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Habilitar a extensão de BOPIS no criador de sites do Commerce

Para habilitar a extensão "comprar online, retirar na Store" (BOPIS) no criador de sites do Commerce, siga estas etapas.

1. Selecione seu site.
1. Selecione **Configurações do site** e, em seguida, selecione **Extensões**.
1. Verifique se a opção **Desativar BOPIS** está desmarcada.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Configurar modos de entrega na matriz do Commerce

Para configurar modos de entrega na matriz do Commerce, siga estas etapas:

1. Vá para **Compras e fornecimento \> Configuração \> Modos de entrega**.
1. Verifique se o modo de entrega **Retirada do cliente** foi criado e se os produtos e endereços estão atribuídos a ele.
1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros**.
1. No painel de navegação à esquerda, selecione **Ordens do cliente**.
1. Verifique se o **Modo de entrega de retirada** está configurado corretamente.

### <a name="configure-customer-orders-payments"></a>Configurar pagamentos de ordens de cliente

Para configurar pagamentos de ordens do cliente na matriz do Commerce, siga estas etapas.

1. Vá para **Varejo e Comércio \> Configuração da sede \> Parâmetros**.
1. No painel de navegação à esquerda, selecione **Ordens do cliente**.
1. Na guia rápida **Pagamentos**, verifique se os campos **Condições de pagamento** e **Método de pagamento** estão definidos corretamente.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar BOPIS](../cpe-bopis.md)

[Habilitar vários modos de entrega de retirada para ordens de cliente](../multiple-pickup-modes.md)

[Pagamentos de ordens de omnicanal do Commerce](../dev-itpro/commerce-payments.md)

[Módulo de seletor de loja](../store-selector.md)
