---
title: Módulo de opções de entrega
description: Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 8342afefa6eeda3a53decb39caddb62d1e4e1963
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6270852"
---
# <a name="delivery-options-module"></a>Módulo de opções de entrega

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de opções de entrega e explica como configurá-los no Microsoft Dynamics 365 Commerce.

Os módulos de opções de entrega permitem que os clientes selecionem um modo de entrega, como remessa ou retirada do pedido online. É necessário um endereço de remessa para determinar o modo de entrega. Se o endereço de remessa for alterado, as opções de entrega deverão ser recuperadas novamente. Se uma ordem incluir somente itens que serão retirados em uma loja, esse módulo ficará oculto automaticamente.

Para obter mais informações sobre como configurar os modos de entrega, consulte [Configuração de canal online](channel-setup-online.md) e [Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Cada modo de entrega pode ter um encargo associado. Para obter mais informações sobre como configurar encargos de uma loja online, consulte [Encargos automáticos avançados do Omnicanal](omni-auto-charges.md).

No Commerce versão 10.0.13, o módulo de opções de entrega foi atualizado para oferecer suporte aos recursos **Encargos de cabeçalho sem rateio** e **Remessa como encargo de linha**. Se o rateio for desativado, a expectativa é que o fluxo de trabalho do comércio eletrônico não permita um modo misto de entrega para os itens no carrinho (ou seja, alguns itens são selecionados para remessa, mas outros são selecionados para retirada). O recurso **Encargos de cabeçalho sem rateio** requer que o sinalizador **Habilitar manuseio de modo de entrega consistente no canal** seja ativado no Commerce Headquarters. Quando o sinalizador do recurso for ativado, as cobranças de remessa serão aplicadas no nível do cabeçalho ou no nível da linha, dependendo da configuração no Commerce Headquarters.

O tema Fabrikam oferece suporte a um modo misto de entrega em que alguns itens são selecionados para remessa, mas outros são selecionados para retirada. Nesse modo, os encargos de remessa serão rateados para todos os itens selecionados no modo de remessa da entrega. Para que um modo misto de entrega funcione, é necessário configurar o recurso **Encargos de cabeçalho com rateio** no Commerce Headquarters. Para obter mais informações sobre essa configuração, consulte [Ratear encargos de cabeçalho para coincidir com linhas de vendas](pro-rate-charges-matching-lines.md).

Se os encargos de remessa forem aplicáveis aos itens de linha, eles poderão ser exibidos para cada item na linha do carrinho. Esta funcionalidade requer que a propriedade **Mostrar encargos de remessa no item da linha** seja ativada para o módulo do carrinho e o módulo de finalização da compra. Para obter mais informações, consulte [Módulo de carrinho](add-cart-module.md) e [Módulo de finalização da compra](add-checkout-module.md).

A ilustração a seguir mostra um exemplo de um módulo de opções de entrega em uma página de finalização da compra.

![Exemplo de um módulo de opções de entrega em uma página de finalização de compra](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Propriedades do módulo de opções de entrega

| Propriedade | Valores | descrição |
|----------|--------|-------------|
| Cabeçalho | Texto do cabeçalho e uma tag do cabeçalho (**H1**, **H2**, **H3**, **H4**, **H5** ou **H6**) | Um título opcional para o módulo de opções de entrega. |
| Nome da classe CSS personalizada | Texto | Um nome de classe de Folhas de Estilo em Cascata (CSS) que será usado para renderizar esse módulo, se aplicável. |
| Opção de Modo de Entrega do Filtro | **Não filtrar** ou **Modos não remessa** | Um valor que especifica se o módulo de opções de entrega devem filtrar todos os modos de entrega não remessa. |
| Seleção automática de uma opção de entrega | **Não filtrar**, **Seleção automática de uma opção de entrega e mostrar resumo** ou **Seleção automática de uma opção de entrega e não mostrar resumo** | Esta propriedade aplica automaticamente a primeira opção de entrega disponível para finalizar a compra, sem exigir que o usuário a selecione. Deve ser usada somente se houver uma opção de entrega disponível. Essa propriedade é suportada a partir da versão 10.0.19 do Commerce. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Adicionar um módulo de opções de entrega a uma página de finalização da compra e definir as propriedades necessárias

Um módulo de opções de entrega pode ser adicionado somente a um módulo de finalização da compra. Para obter mais informações sobre como configurar o módulo de opções de entrega e adicioná-lo a uma página de finalização da compra, consulte [Módulo de finalização da compra](add-checkout-module.md).

## <a name="additional-resources"></a>Recursos adicionais

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de pagamento](payment-module.md)

[Módulo de endereço de remessa](ship-address-module.md)

[Módulo de informações sobre retirada](pickup-info-module.md)

[Módulo de detalhes da ordem](order-confirmation-module.md)

[Módulo de cartão-presente](add-giftcard.md)

[Configuração de canal online](channel-setup-online.md)

[Encargos automáticos Avançados de Omnicanal](omni-auto-charges.md)

[Ratear encargos do cabeçalho para coincidir com linhas de vendas](pro-rate-charges-matching-lines.md)

[Configurar os modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
