---
title: Módulo de ícone de carrinho
description: Este artigo abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a5b86b0c843a680dd0c46295a69e12d6e3542619
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859104"
---
# <a name="cart-icon-module"></a>Módulo de ícone de carrinho

[!include [banner](includes/banner.md)]

Este artigo abrange o módulo de ícone de carrinho e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

O módulo de ícone de carrinho representa o carrinho no módulo de cabeçalho da página e mostra o número de itens no carrinho. O módulo do ícone de carrinho também exibe um resumo do carrinho (também conhecido como um mini carrinho) quando mouse é passado pelo ícone de carrinho. O mini carrinho fornece ao usuário um resumo dos itens no carrinho sem ter que navegar até a página do carrinho. Além disso, ele também permite que o usuário vá diretamente para a página de check-out se estiver satisfeito com o resumo. Isso reduz o número de navegações de página e torna o check-out mais rápido. 

A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho que exibe um minicarrinho no cabeçalho Fabrikam.

![Exemplo de um módulo de ícone de carrinho.](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Propriedades do módulo

- **Mostrar mini carrinho**: quando esta propriedade estiver configurada como **Verdadeiro**, um resumo do carrinho (mini carrinho) será exibido sempre que o usuário passar o mouse sobre o ícone do carrinho. Essa funcionalidade tem suporte apenas em portas de exibição de desktop.
- **Permitir finalização anônima**: quando esta propriedade estiver configurada como **Verdadeiro**, o mini carrinho permitirá que os usuários que não fizeram login façam uma finalização de convidado. Essa propriedade está disponível na versão 10.0.21 do Commerce, como parte do pacote de biblioteca do módulo do Commerce.
- **Ordem dos itens**: esta propriedade controla a ordem em que os itens são exibidos no mini carrinho. Quando a opção **Novos itens adicionados à parte superior da lista** estiver selecionada, novos itens adicionados ao carrinho serão exibidos na parte superior da lista de itens do mini carrinho. Quando a opção padrão **Novos itens adicionados à parte inferior da lista** estiver selecionada, novos itens adicionados ao carrinho serão exibidos na parte inferior da lista de itens do mini carrinho. Essa propriedade está disponível a partir da versão 10.0.21 do Commerce, como parte do pacote de biblioteca do módulo do Commerce.

> [!IMPORTANT]
> As propriedades **Permitir finalização anônima** e **Ordem dos itens** estão disponíveis na versão 10.0.21 do Commerce. Elas requerem que o pacote de biblioteca do módulo da versão 9.31 do Commerce esteja instalado.

## <a name="module-properties-and-slots-in-the-adventure-works-theme"></a>Propriedades e slots do módulo no tema Adventure Works

No tema Adventure Works, o módulo ícone de carrinho contém dois slots adicionais para o mini carrinho. Esses slots são incluídos como uma extensão de definição de módulo.

- **Promoções de carrinhos vazias** – Este slot usa um módulo de bloco de conteúdo. Quando o carrinho está vazio, o módulo de bloco de conteúdo especificado é exibido. O módulo de bloco de conteúdo pode ser usado para promoções, conteúdo de marketing e links para páginas de categoria, ajudando os clientes a continuar a jornada de compras.
- **Conteúdo promocional** – Este slot pode ser usado para exibir promoções, como "Frete grátis em ordens acima de U$100". Os módulos bloco de conteúdo, bloco de texto e lista de imagens podem ser usados no slot de conteúdo promocional.

A imagem a seguir mostra um exemplo de um módulo de ícone de carrinho no tema Adventure Works que exibe conteúdo promocional no mini carrinho.

![Exemplo de um módulo de ícone de carrinho no tema Adventure Works](./media/AW_minicart.PNG)

> [!IMPORTANT]
> Os slots de tema Adventure Works estão disponíveis a partir da versão 10.0.20 do Dynamics 365 Commerce.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
