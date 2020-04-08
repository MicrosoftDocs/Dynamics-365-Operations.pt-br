---
title: Módulo de caixa de compra
description: Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3417156cbf3cb20a5190e5e51b61b3423816895a
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154054"
---
# <a name="buy-box-module"></a>Módulo de caixa de compra


[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O termo *caixa de compra* geralmente se refere à área de uma página de detalhes de produto que está "na primeira página" e que hospeda todas as informações mais importantes necessárias para a compra de um produto. (Uma área que está na "primeira página" fica visível quando a página é carregada pela primeira vez, para que os usuários não precisem rolar para baixo para vê-la.)

Um módulo de caixa de compra é um contêiner especial usado para hospedar todos os módulos mostrados na área da caixa de compra de uma página de detalhes do produto.

A URL da página de detalhes do produto inclui a ID do produto. Todas as informações necessárias para renderizar um módulo de caixa de compra são derivadas dessa ID de produto. Se uma ID de produto não for fornecida, o módulo da caixa de compra não será renderizado corretamente em uma página. Portanto, um módulo de caixa de compra pode ser usado somente em páginas que têm contexto de produto. Para usá-lo em uma página que não tenha um contexto de produto (por exemplo, uma página inicial ou uma página de marketing), você deve fazer personalizações adicionais.

## <a name="buy-box-module-properties-and-slots"></a>Propriedades e slots do módulo de caixa de compra 

Na página de detalhes do produto, uma caixa de compra é dividida em duas regiões: uma região de mídia à esquerda e uma região de conteúdo à direita. Por padrão, a razão entre a largura da coluna da região da mídia e a largura da coluna da região do conteúdo é 2:1. Nos dispositivos móveis, as duas regiões são empilhadas, para que uma região apareça abaixo da outra região. Os temas podem ser usados para personalizar as larguras de coluna e a classificação de empilhamento.

Um módulo de caixa de compra renderiza o título, a descrição, o preço e as classificações de um produto. Ele também permite que os clientes selecionem grades de produtos que têm atributos de produto diferentes, como tamanho, estilo e cor. Quando uma variante de produto é selecionada, outras propriedades na caixa de compra (por exemplo, a descrição e as imagens do produto) são atualizadas para refletir as informações da variante. 

Um seletor de quantidade é fornecido para que os clientes possam especificar a quantidade de itens a comprar. A quantidade máxima que pode ser comprada pode ser definida nas configurações do site.
 
Na caixa comprar, os clientes também podem executar ações como adicionar um produto ao carrinho, adicionar um produto à sua lista de desejos e selecionar um local de retirada. Essas ações podem ser executadas em um produto ou em uma grade de produto. Para adicionar um produto a uma lista de desejos, o cliente deve estar conectado.

Os temas podem ser usados para remover ou alterar a ordem das propriedades do produto da caixa de compra e os controles de ação. 

## <a name="module-properties"></a>Propriedades do módulo

- **Marca do título** – Esta propriedade define a marca do título para o título do produto. Se a caixa de compra estiver na parte superior da página, essa propriedade deverá ser definida como **h1** para atender aos padrões de acessibilidade. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que podem ser usados em um módulo de caixa de compra

- **Galeria de mídia** – Este módulo é usado para mostrar imagens de um produto em uma página de detalhes do produto. Ele permite uma a muitas imagens. Ele também permite imagens em miniatura. As imagens em miniatura podem ser organizadas horizontalmente (como uma linha abaixo da imagem) ou verticalmente (como uma coluna ao lado da imagem). O módulo da galeria de mídia pode ser adicionado ao slot **Mídia** no módulo da caixa de compra. Atualmente, ele é compatível apenas com imagens. 
- **Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Ele permite que os usuários insiram um local para encontrar lojas próximas. Para obter mais informações sobre este módulo, consulte [Módulo do seletor de armazenamento](store-selector.md).

## <a name="buy-box-module-settings"></a>Configurações do módulo de caixa de compra

Os módulos de caixa de compra têm três configurações que podem ser definidas em **Configurações de Site \> Extensões**:

- **Quantidade máxima** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque. Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja. Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.
- **Buffer de estoque** – Esta propriedade é usada para especificar um número de buffer para o estoque. O estoque é mantido em tempo real e, quando muitos clientes fazem pedidos, pode ser difícil manter uma contagem precisa do estoque. Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque. Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, e a contagem do estoque não está totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

O módulo de caixa de compra recupera informações do produto usando as APIs de Commerce Scale Unit. A ID de produto na página de detalhes do produto é usada para recuperar todas as informações.

## <a name="add-a-buy-box-module-to-a-page"></a>Adicionar um módulo de caixa de compra a uma página

Para adicionar um módulo de caixa de compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Crie um fragmento denominado **fragmento da caixa de compra** e adicione um módulo de caixa de compra a ele.
1. No slot **Mídia** do módulo da caixa de compra, adicione um módulo da galeria de mídia.
1. No slot **Seletor de armazenamento** do módulo da caixa de compra, adicione um módulo de seletor de armazenamento.
1. Insira a página e publique-a.
1. Crie um modelo para uma página de detalhes do produto e denomine-o **Modelo do PDP**.
1. Adicione uma página padrão.
1. No slot **Principal** da página padrão, adicione um fragmento da caixa de compra.
1. Salve o modelo, termine de editá-lo e publique-o.
1. Use o modelo que criou para criar uma página nomeada **Página PDP**.
1. No slot **Principal** da nova página, adicione um fragmento da caixa de compra.
1. Salve e exiba a página. Adicione o parâmetro da sequência de caracteres da consulta **?productid=&lt;product id&gt;** à URL da página de exibição. Dessa forma, o contexto do produto é usado para carregar e renderizar a página de exibição.
1. Salve a página, termine de editá-la e publique-a. Uma caixa de compra deve aparecer na página de detalhes do produto.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo seletor de armazenamento](store-selector.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
