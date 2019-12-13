---
title: Módulo de caixa de compra
description: Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
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
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811132"
---
# <a name="buy-box-module"></a>Módulo de caixa de compra

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O termo *caixa de compra* geralmente se refere à área de uma página de detalhes de produto que está "na primeira página" e que hospeda todas as informações mais importantes necessárias para a compra de um produto. (Uma área que está na "primeira página" fica visível quando a página é carregada pela primeira vez, para que os usuários não precisem rolar para baixo para vê-la.)

Um módulo de caixa de compra é um contêiner especial usado para hospedar todos os módulos mostrados na área da caixa de compra de uma página de detalhes do produto.

A URL da página de detalhes do produto inclui a ID do produto. Todas as informações necessárias para renderizar um módulo de caixa de compra são derivadas dessa ID de produto. Se uma ID de produto não for fornecida, o módulo da caixa de compra não será renderizado corretamente em uma página. Portanto, um módulo de caixa de compra não pode ser usado em nenhuma página que não tenha contexto de produto (por exemplo, uma home page ou uma página de marketing).

## <a name="buy-box-module-properties-and-slots"></a>Propriedades e slots do módulo de caixa de compra 

Como um contêiner, um módulo de caixa de compra controla algumas propriedades básicas, como a largura. A configuração de largura determina se os módulos dentro do contêiner devem se ajustar a esse contêiner ou se podem preencher a tela.

Na página de detalhes do produto, uma caixa de compra é dividida em duas regiões: uma região de mídia à esquerda e uma região de conteúdo à direita. Essas duas regiões são representadas por slots no módulo de caixa de compra. Cada slot é pré-configurado para aceitar apenas módulos específicos compatíveis com o slot. Por exemplo, um slot **Mídia** é compatível com apenas o módulo da galeria de mídia.

Por padrão, a proporção das larguras das colunas para a região de mídia e a região de conteúdo é 2:1. Contudo, as larguras da coluna podem ser substituídas pelo tema. Além disso, em dispositivos móveis, as duas regiões são empilhadas, para que uma região apareça abaixo da outra região.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que podem ser usados em um módulo de caixa de compra

- **Galeria de mídia** – Este módulo é usado para mostrar imagens de um produto em uma página de detalhes do produto. Ele permite uma a muitas imagens. Ele também permite imagens em miniatura. As imagens em miniatura podem ser organizadas horizontalmente (como uma linha abaixo da imagem) ou verticalmente (como uma coluna ao lado da imagem). O módulo da galeria de mídia pode ser adicionado ao slot **Mídia** no módulo da caixa de compra. Atualmente, ele permite apenas imagens e vídeos.
- **Título do produto** – Este módulo mostra o título do produto em uma página de detalhes do produto. Por padrão, a tag de cabeçalho **H1** é usada, mas a tag de cabeçalho pode ser alterada conforme necessário.
- **Classificação do produto** – Este módulo mostra as classificações por estrelas, com base nas classificações dos clientes para um produto. O módulo da caixa de compra recupera as classificações do produto para cada produto do serviço de classificações.
- **Preço do produto** – Este módulo mostra o preço do produto. O preço inclui preços tachados e descontos.
- **Descrição do produto** – Este módulo mostra a descrição do produto.
- **Configuração do produto** – Este módulo mostra o tamanho, o estilo e as dimensões do produto. Os seletores de dimensão podem ser empilhados verticalmente ou podem aparecer lado a lado. Quando uma variante de produto é selecionada, outras propriedades na caixa de compra (por exemplo, a descrição e as imagens do produto) são atualizadas para refletir as informações da variante.
- **Quantidade de produtos** – Este módulo é usado para configurar a quantidade do produto. Uma configuração limita a quantidade de um produto ou variante que pode ser adicionada ao carrinho.
- **Adicionar ao carrinho** – Este módulo é usado para executar a ação "adicionar ao carrinho". Somente um produto ou uma variante pode ser adicionado ao carrinho. Em outras palavras, um produto mestre não pode ser adicionado ao carrinho. O módulo possui uma propriedade **Navegar até o carrinho** que o autor do site pode definir. Quando essa propriedade é definida como **Verdadeiro**, o usuário é levado para a página do carrinho sempre que uma ação "adicionar ao carrinho" é acionada. Quando é definida como **Falso**, o cliente pode continuar navegando na página de detalhes do produto após a adição de itens ao carrinho.
- **Adicionar a lista de desejos** – Este módulo é usado para adicionar um item à lista de desejos do cliente. Somente um produto ou uma variante pode ser adicionado a uma lista de desejos. Além disso, o cliente deve estar conectado ao site. O módulo inclui lógica de tratamento de erros para garantir que essas duas condições sejam atendidas.
- **Localizar na loja** – Este módulo aciona o fluxo "compre online, retire na loja".
- **Retirar na loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Por padrão, esse módulo mostra lojas que estão dentro de um raio de 80 quilômetros da localização do cliente. Contudo, o raio de pesquisa pode ser personalizado no módulo. Para cada loja, é feita uma verificação de estoque, se a funcionalidade de verificação de estoque estiver ativada e uma mensagem apropriada informando o que está no estoque ou esgotado do estoque for exibida.
- **Pesquisa na loja pelo Bing Maps** – Este módulo pode ser usado no módulo de retirada na loja. Permite que os clientes pesquisem lojas inserindo um local. A interface de programação de aplicativos (API) de geocodificação do Bing Maps é usada para converter o local especificado em latitude e longitude. Se este módulo for usado, apenas as lojas próximas à localização atual do cliente serão exibidas e o cliente não poderá procurar um local diferente.
- **Bloco de conteúdo sofisticado** – Este módulo pode mostrar uma mensagem que o autor ou revendedor do site deseja promover na caixa de compra, como "For issues with order, contact 1-800-FABRIKAM" (Caso você tenha problemas com uma ordem, entre em contato com 1-800-FABRIKAM) ou "Free shipping on orders over $100" (Envio grátis para encomendas acima de US$ 100). As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS).

## <a name="buy-box-module-settings"></a>Configurações do módulo de caixa de compra

Os módulos de caixa de compra têm três configurações que podem ser configuradas:

- **Quantidade máxima** – O número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque. Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja. Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.
- **Buffer de estoque** – O estoque é mantido em tempo real e, quando muitos clientes colocam ordens, pode ser difícil manter uma contagem precisa do estoque. Portanto, um buffer pode ser definido para o estoque. Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque. Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, para que a contagem do estoque não seja totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.

## <a name="retail-server-interaction"></a>Interação do Retail Server

O módulo de caixa de compra recupera informações do produto usando as APIs do Retail Server. A ID de produto na página de detalhes do produto é usada para recuperar todas as informações.

## <a name="add-a-buy-box-module-to-a-page"></a>Adicionar um módulo de caixa de compra a uma página

Para adicionar um módulo de caixa de compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Crie um fragmento denominado **fragmento da caixa de compra** e adicione um módulo de caixa de compra a ele.
1. No slot **Mídia** do módulo da caixa de compra, adicione um módulo da galeria de mídia.
1. No slot **Conteúdo** do módulo de caixa de compra, adicione os seguintes módulos: título do produto, classificação do produto, preço do produto, descrição do produto, configuração do produto, adicionar ao carrinho, lista de desejos e localizar na loja. Você pode reorganizar os módulos no slot **Conteúdo** para obter o layout desejado.
1. Selecione o módulo Localizar na loja. No slot dentro deste módulo, adicione um módulo Retirar na loja.
1. No slot dentro do módulo Retirar na loja, adicione um módulo de pesquisa na loja pelo Bing Maps.
1. Insira a página e publique-a.
1. Crie um modelo para uma página de detalhes do produto e denomine-o **Modelo do PDP**.
1. Adicione uma página padrão.
1. No slot **Principal** da página padrão, adicione um fragmento da caixa de compra.
1. Salve o modelo, insira-o e publique-o.
1. Use o modelo que criou para criar uma página nomeada **Página PDP**.
1. No slot **Principal** da nova página, adicione um fragmento da caixa de compra.
1. Salve e exiba a página. Adicione o parâmetro da sequência de caracteres da consulta **?productid=&lt;product id&gt;** à URL da página de exibição. Dessa forma, o contexto do produto é usado para carregar e renderizar a página de exibição.
1. Insira a página e publique-a. Uma caixa de compra deve aparecer na página de detalhes do produto.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
