---
title: Módulo de caixa de compra
description: Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: beb705852be99ce817997d7017c41a0159f75419
ms.sourcegitcommit: 69075e001d1fb4ef69282667052cd8d082273094
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4022020"
---
# <a name="buy-box-module"></a>Módulo de caixa de compra

[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de caixa de compra e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

O termo *caixa de compra* geralmente se refere à área de uma página de detalhes de produto que está "na primeira página" e que hospeda todas as informações mais importantes necessárias para a compra de um produto. (Uma área que está na "primeira página" fica visível quando a página é carregada pela primeira vez, para que os usuários não precisem rolar para baixo para vê-la.)

Um módulo de caixa de compra é um contêiner especial usado para hospedar todos os módulos mostrados na área da caixa de compra de uma página de detalhes do produto.

A URL da página de detalhes do produto inclui a ID do produto. Todas as informações necessárias para renderizar um módulo de caixa de compra são derivadas dessa ID de produto. Se uma ID de produto não for fornecida, o módulo da caixa de compra não será renderizado corretamente em uma página. Portanto, um módulo de caixa de compra pode ser usado somente em páginas que têm contexto de produto. Para usá-lo em uma página que não tenha um contexto de produto (por exemplo, uma página inicial ou uma página de marketing), você deve fazer personalizações adicionais.

A imagem a seguir mostra um exemplo de um módulo de caixa de compra em uma página de detalhes de produtos.

![Exemplo de um módulo de caixa de compra](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Propriedades e slots do módulo de caixa de compra 

Na página de detalhes do produto, uma caixa de compra é dividida em duas regiões: uma região de mídia à esquerda e uma região de conteúdo à direita. Por padrão, a razão entre a largura da coluna da região da mídia e a largura da coluna da região do conteúdo é 2:1. Nos dispositivos móveis, as duas regiões são empilhadas, para que uma região apareça abaixo da outra região. Os temas podem ser usados para personalizar as larguras de coluna e a classificação de empilhamento.

Um módulo de caixa de compra renderiza o título, a descrição, o preço e as classificações de um produto. Ele também permite que os clientes selecionem grades de produtos que têm atributos de produto diferentes, como tamanho, estilo e cor. Quando uma variante de produto é selecionada, outras propriedades na caixa de compra (por exemplo, a descrição e as imagens do produto) são atualizadas para refletir as informações da variante. 

Um seletor de quantidade é fornecido para que os clientes possam especificar a quantidade de itens a comprar. A quantidade máxima que pode ser comprada pode ser definida nas configurações do site.

Na caixa comprar, os clientes também podem executar ações como adicionar um produto ao carrinho, adicionar um produto à sua lista de desejos e selecionar um local de retirada. Essas ações podem ser executadas em um produto ou em uma grade de produto. Para adicionar um produto a uma lista de desejos, o cliente deve estar conectado.

Os temas podem ser usados para remover ou alterar a ordem das propriedades do produto da caixa de compra e os controles de ação. 

## <a name="module-properties"></a>Propriedades do módulo

- **Marca do título** – Esta propriedade define a marca do título para o título do produto. Se a caixa de compra estiver na parte superior da página, essa propriedade deverá ser definida como **h1** para atender aos padrões de acessibilidade. 

- **Habilitar recomendações de "comprar looks semelhantes"** - Esta propriedade permite à caixa de compra mostrar links para produtos semelhantes ao item exibido no momento. Este recurso está disponível nas versões 10.0.13 e posterior do Commerce.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que podem ser usados em um módulo de caixa de compra

- **Galeria de mídia** – Este módulo é usado para mostrar imagens de um produto em uma página de detalhes do produto. Para obter mais informações sobre esse módulo, consulte [Módulo de galeria de mídia](media-gallery-module.md).
- **Seletor de loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Ele permite que os usuários insiram um local para encontrar lojas próximas. Para obter mais informações sobre esse módulo, consulte [Módulo de seletor de loja](store-selector.md).
- **Compartilhamento social** - Este módulo pode ser adicionado à caixa de compra para permitir que os usuários compartilhem informações do produto nas redes sociais. Para obter mais informações, consulte [Módulo de compartilhamento social](social-share-module.md).

## <a name="buy-box-module-settings"></a>Configurações do módulo de caixa de compra

As seguintes configurações de módulo de caixa de compra podem ser definidas em **Configurações de Site \> Extensões** :

- **Limite de quantidade de linha de carrinho** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Estoque** – para obter informações sobre como aplicar configurações de estoque, consulte [Aplicar configurações de estoque](inventory-settings.md).
- **Adicionar ao carrinho** – esta propriedade é usada para especificar o comportamento depois que um item é adicionado ao carrinho. Os valores possíveis são **Navegar até o carrinho** , **Não navegar até o carrinho** e **Mostrar notificações**. Quando o valor for definido como **Navegar até o carrinho** , os usuários serão enviados para a página do carrinho depois que adicionarem um item. Quando o valor for definido como **Não navegar até o carrinho** , os usuários não serão enviados para a página do carrinho depois que adicionarem um item. Quando o valor for definido como **Mostrar notificações** , os usuários receberão uma notificação de confirmação e poderão continuar a procurar na página detalhes do produto. 

> [!IMPORTANT]
> As configurações de **Adicionar ao carrinho** do site estão disponíveis na versão 10.0.11 do Dynamics 365 Commerce. Se estiver atualizando de uma versão mais antiga do Dynamics 365 Commerce, você deverá atualizar manualmente o arquivo appsettings.json. Para obter instruções sobre como atualizar o arquivo appsettings.json, consulte [SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

A imagem a seguir mostra um exemplo de notificação de confirmação "adicionado ao carrinho" no site da Fabrikam.

![Exemplo de um módulo de notificação](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

O módulo de caixa de compra recupera informações do produto usando as interfaces de programação de aplicativos (APIs) de Commerce Scale Unit. A ID de produto na página de detalhes do produto é usada para recuperar todas as informações.

## <a name="add-a-buy-box-module-to-a-page"></a>Adicionar um módulo de caixa de compra a uma página

Para adicionar um módulo de caixa de compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Vá para **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Novo fragmento** , selecione o módulo **Caixa de compra**.
1. Em **Nome do fragmento** , digite o nome **Fragmento de caixa de compra** e selecione **OK**.
1. No slot **Galeria de Mídia** do módulo de caixa de compra, selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Galeria de mídia** e, depois, **OK**.
1. No slot **Seletor de loja** do módulo de caixa de compra, selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Seletor de loja** e, depois, **OK**.
1. Selecione **Salvar** , **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.
1. Vá para **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo Modelo** , em **Nome do modelo** , insira **Modelo PDP** e selecione **OK**.
1. No slot **Corpo** , selecione as reticências ( **...** ) e, depois, **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo** , selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** da página padrão, selecione as reticências ( **...** ) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar fragmento** , selecione o fragmento **Fragmento de caixa de compra** criado anteriormente e, em seguida, selecione **OK**.
1. Selecione **Salvar** , **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Vá para **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Escolher um modelo** , selecione o modelo **Modelo de PDP**. Em **Nome da página** , insira **Página PDP** e selecione **OK**.
1. No slot **Principal** da nova página, selecione as reticências ( **...** ) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar fragmento** , selecione o fragmento **Fragmento de caixa de compra** criado anteriormente e, em seguida, selecione **OK**.
1. Salve e exiba a página. Adicione o parâmetro da sequência de caracteres da consulta **?productid=&lt;product id&gt;** à URL da página de exibição. Dessa forma, o contexto do produto é usado para carregar e renderizar a página de exibição.
1. Selecione **Salvar** , **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. Uma caixa de compra deve aparecer na página de detalhes do produto.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de seletor de loja](store-selector.md)

[Módulo de galeria de mídia](media-gallery-module.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de carrinho](add-cart-module.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)

[Módulo de compartilhamento social](social-share-module.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)
