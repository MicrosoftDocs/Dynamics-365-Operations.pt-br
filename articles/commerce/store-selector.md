---
title: Módulo de seletor de loja
description: Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 460d05ca29d5b8da70a971a649d9edd786f7260d
ms.sourcegitcommit: 15c5ec742d648c5f3506d031a2ab6150dcbae348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "3378199"
---
# <a name="store-selector-module"></a>Módulo de seletor de loja

[!include [banner](includes/banner.md)]

Este tópico abrange o módulo de seletor de loja e descreve como adicioná-lo às páginas do site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão Geral

Um módulo de seletor de loja é usado para o cenário de cliente "compre online, retire na loja" (buy online, pick up in store - BOPIS). Ele exibe uma lista de lojas onde um produto está disponível para retirada, além de horários e estoque de produtos de cada loja.

O módulo de seletor de loja requer o contexto de um produto e um local de pesquisa para encontrar lojas. Na ausência de um local de pesquisa, o padrão é o local do navegador do cliente, desde que o cliente dê consentimento. O módulo tem uma caixa de entrada que permite ao cliente inserir um local (CEP ou cidade e estado) para encontrar lojas próximas.

O módulo de seletor de loja é integrado à interface de programação de aplicativos (API) de Geocodificação do Bing Mapas para converter o local em latitude e longitude. Uma chave de API do Bing Mapas é necessária e deve ser adicionada à página parâmetros compartilhados de comércio no Dynamics 365 Commerce.

O módulo de seletor de loja pode ser adicionado a um módulo de caixa de compra na página de detalhes do produto (PDP) para exibir as lojas onde um produto está disponível para retirada. Também pode ser adicionado a um módulo de carrinho. Quando adicionado a um módulo de carrinho, o módulo de seletor de loja exibe opções de retirada para cada item de linha do carrinho. Além disso, com a codificação personalizada, esse módulo pode ser adicionado a outras páginas ou módulos por meio de extensões e personalizações.

Para que o cenário BOPIS funcione, os produtos devem ser configurados com o modo de entrega "retirada do cliente". Caso contrário, o módulo não será mostrado nas respectivas páginas. Para detalhes sobre como configurar o modo de entrega, consulte [Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

A imagem a seguir mostra um exemplo de um módulo de seletor de loja usado em uma PDP.

![Exemplo de um módulo de seletor de loja](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Uso do módulo de seletor de loja no comércio eletrônico

- Um módulo de seletor de loja pode ser usado em uma página de detalhes do produto (PDP) na pesquisa de lojas próximas onde um produto está disponível para retirada.
- Um módulo de seletor de loja pode ser usado em uma página do carrinho na pesquisa de lojas próximas onde um produto no carrinho está disponível para retirada.

## <a name="store-selector-module-properties"></a>Propriedades do módulo de seletor de loja

| Nome da propriedade             | Alíquota                 | descrição |
|---------------------------|-----------------------|-------------|
| Pesquisar raio | Número | Define o raio de pesquisa para lojas, em milhas. Se nenhum valor for especificado, o raio de pesquisa padrão de 50 milhas será usado.|
|Termos de Serviço | URL    |  A URL dos termos de serviço necessária para o serviço Bing Mapas. |

## <a name="add-a-store-selector-module-to-a-page"></a>Adicionar um módulo de seletor de loja a uma página

Um módulo de seletor de loja precisa do contexto de um produto, para que ele possa ser usado apenas nos módulos de caixa de compra e carrinho. Os módulos de seletor de loja não funcionam fora desses módulos.

- Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de caixa de compra, consulte [Módulo de caixa de compra](add-buy-box.md). 
- Para obter informações sobre como adicionar um módulo de seletor de loja a um módulo de carrinho, consulte [Módulo de carrinho](add-cart-module.md)

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de carrinho](add-cart-module.md)

[Tour rápido da PDP](quick-tour-pdp.md)

[Tour rápido do carrinho e do check-out](quick-tour-cart-checkout.md)

[Configurar os modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Gerenciar o Bing Maps da sua organização](dev-itpro/manage-bing-maps.md)
