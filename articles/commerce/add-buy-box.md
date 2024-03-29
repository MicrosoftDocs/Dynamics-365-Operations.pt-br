---
title: Módulo de caixa de compra
description: Este artigo abrange os módulos de caixa de compra e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 7a3dfa347aac7b1ee7b318761c873beef8322bd9
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270500"
---
# <a name="buy-box-module"></a>Módulo de caixa de compra

[!include [banner](includes/banner.md)]

Este artigo abrange os módulos de caixa de compra e descreve como adicioná-los às páginas de site no Microsoft Dynamics 365 Commerce.

O termo *caixa de compra* geralmente se refere à área de uma página de detalhes de produto (PDP) que está "na primeira página" e que hospeda todas as informações mais importantes necessárias para a compra de um produto. (Uma área que está na "primeira página" fica visível quando a página é carregada pela primeira vez, para que os usuários não precisem rolar para baixo para vê-la.)

Um módulo de caixa de compra é um contêiner especial usado para hospedar todos os módulos mostrados na área da caixa de compra de uma página de detalhes do produto.

A URL da página de detalhes do produto inclui a ID do produto. Todas as informações necessárias para renderizar um módulo de caixa de compra são derivadas dessa ID de produto. Se uma ID de produto não for fornecida, o módulo da caixa de compra não será renderizado corretamente em uma página. Portanto, um módulo de caixa de compra pode ser usado somente em páginas que têm contexto de produto. Para usá-lo em uma página que não tenha um contexto de produto (por exemplo, uma página inicial ou uma página de marketing), você deve fazer personalizações adicionais.

A imagem a seguir mostra um exemplo de um módulo de caixa de compra em uma página de detalhes de produtos.

![Exemplo de um módulo de caixa de compra.](./media/ecommerce-pdp-buybox.PNG)

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

As seguintes configurações de módulo de caixa de compra podem ser definidas em **Configurações de Site \> Extensões**:

- **Limite de quantidade de linha de carrinho** – Esta propriedade é usada para especificar o número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Estoque** – para obter informações sobre como aplicar configurações de estoque, consulte [Aplicar configurações de estoque](inventory-settings.md).
- **Adicionar produto ao carrinho** – Para obter informações sobre como aplicar as configurações de **Adicionar produto ao carrinho**, consulte [configurações de Adicionar produto ao carrinho](add-cart-settings.md).

## <a name="buy-box-module-definition-extensions-in-the-adventure-works-theme"></a>Extensões de definição do módulo de caixa de compra no tema Adventure Works

O módulo de caixa de compra que o tema da Adventure Works fornece tem uma extensão de definição de módulo que oferece suporte à implementação de um módulo de especificações de produtos em um módulo acordeão em uma caixa de compra de PDP. Para exibir atributos de especificação de produto em uma caixa de compra de PDP, adicione um módulo de especificação de produto ao slot do módulo acordeão no slot da caixa de compra.


> [!IMPORTANT]
> O tema Adventure Works está disponível a partir da versão 10.0.20 do Dynamics 365 Commerce.


## <a name="commerce-scale-unit-interaction"></a>Interação do Commerce Scale Unit

O módulo de caixa de compra recupera informações do produto usando as interfaces de programação de aplicativos (APIs) de Commerce Scale Unit. A ID de produto na página de detalhes do produto é usada para recuperar todas as informações.

## <a name="add-a-buy-box-module-to-a-page"></a>Adicionar um módulo de caixa de compra a uma página

Para adicionar um módulo de caixa de compra a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Acesse **Fragmentos** e selecione **Novo** para criar um novo fragmento.
1. Na caixa de diálogo **Novo fragmento**, selecione o módulo **Caixa de compra**.
1. Em **Nome do fragmento**, digite o nome **Fragmento de caixa de compra** e selecione **OK**.
1. No slot **Galeria de Mídia** do módulo de caixa de compra, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Galeria de mídia** e, depois, **OK**.
1. No slot **Seletor de loja** do módulo de caixa de compra, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Seletor de loja** e, depois, **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do fragmento e depois selecione **Publicar** para publicá-lo.
1. Acesse **Modelos** e selecione **Novo** para criar um novo modelo.
1. Na caixa de diálogo **Novo modelo**, em **Nome do modelo**, insira **Modelo PDP** e selecione **OK**.
1. No slot **Corpo**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Página Padrão** e, depois, **OK**.
1. No slot **Principal** da página padrão, selecione as reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o fragmento **Fragmento de caixa de compra** criado anteriormente e, depois, selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in do modelo e depois selecione **Publicar** para publicá-lo.
1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira uma **Página PDP** e, depois, selecione **Avançar**.
1. Em **Escolha um modelo**, selecione **Modelo de PDP** e, depois, **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**.
1. No slot **Principal** da nova página, selecione as reticências (**...**) e, em seguida, selecione **Adicionar fragmento**.
1. Na caixa de diálogo **Selecionar um fragmento**, selecione o fragmento **Fragmento de caixa de compra** criado anteriormente e, depois, selecione **OK**.
1. Salve e exiba a página. Adicione o parâmetro da sequência de caracteres da consulta **?productid=&lt;product id&gt;** à URL da página de exibição. Dessa forma, o contexto do produto é usado para carregar e renderizar a página de exibição.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo. Uma caixa de compra deve aparecer na página de detalhes do produto.

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

[Configurações de adicionar produto ao carrinho](add-cart-settings.md)

[Calcular disponibilidade de estoque para canais de varejo](calculated-inventory-retail-channels.md)

[SDK e atualizações da biblioteca de módulos](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
