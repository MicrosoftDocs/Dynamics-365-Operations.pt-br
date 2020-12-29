---
title: Módulo de ícone de carrinho
description: Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ebc5cfa490a4c8538fd081aced0844ed01d63a26
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2020
ms.locfileid: "4410348"
---
# <a name="cart-icon-module"></a>Módulo de ícone de carrinho

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

O módulo de ícone de carrinho representa o carrinho no módulo de cabeçalho da página e mostra o número de itens no carrinho. O módulo do ícone de carrinho também exibe um resumo do carrinho (também conhecido como um mini carrinho) quando mouse é passado pelo ícone de carrinho. O mini carrinho fornece ao usuário um resumo dos itens no carrinho sem ter que navegar até a página do carrinho. Além disso, ele também permite que o usuário vá diretamente para a página de check-out se estiver satisfeito com o resumo. Isso reduz o número de navegações de página e torna o check-out mais rápido. 

> [!NOTE]
> O suporte ao módulo de ícone de carrinho está disponível no Dynamics 365 Commerce versão 10.0.11.

A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho que exibe um minicarrinho no cabeçalho Fabrikam.

![Exemplo de um módulo de ícone de carrinho](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriedades do módulo

- **Mostrar mini carrinho** – Quando verdadeiro, esta propriedade permite que um resumo do carrinho (mini carrinho) seja exibido quando o ícone do carrinho é focalizado. Essa funcionalidade só tem suporte em portas de exibição de desktop.

## <a name="add-a-cart-icon-module-to-a-page"></a>Adicionar um módulo do ícone de carrinho a uma página

Para adicionar um módulo de ícone de carrinho, consulte [Módulo de cabeçalho](author-header-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de opções de entrega](delivery-options-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de cartão-presente](add-giftcard.md)
