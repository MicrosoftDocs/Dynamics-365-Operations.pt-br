---
title: Módulo de carrinho
description: Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696752"
---
# <a name="cart-module"></a>Módulo de carrinho

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico abrange os módulos de carrinho e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

Um módulo de carrinho é um contêiner usado para hospedar todos os módulos necessários para mostrar itens que estão no carrinho. Por exemplo, inclui todos os itens que foram adicionados ao carrinho, o resumo do pedido e os códigos promocionais.

O módulo do carrinho processa dados com base na ID do carrinho. A ID do carrinho é um cookie do navegador disponível em todo o site.

## <a name="cart-module-properties-and-slots"></a>Propriedades e slots do módulo de carrinho

Como um contêiner, um módulo de carrinho controla algumas propriedades básicas, como o cabeçalho e a largura. O cabeçalho é tipicamente texto como **Bolsa de compras**, **Seu carrinho** ou **Itens em seu carrinho**. A configuração de largura determina se os módulos dentro do contêiner devem se ajustar a esse contêiner ou se podem preencher a tela.

A página do carrinho é dividida em várias regiões: itens de linha do carrinho, resumo da ordem e finalização de compra e a funcionalidade "localização na loja". Cada região é mapeada para um slot no módulo de carrinho e cada slot aceita um conjunto predefinido de módulos.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que podem ser usados em um módulo de carrinho

- **Linha do carrinho de compras** – Este módulo mostra um resumo de cada item que foi adicionado ao carrinho. As informações incluem o título do produto, dimensões selecionadas, preço, quantidade e descontos. Este módulo também permite ações como "remover do carrinho" e "adicionar à lista de desejos". Para cada item de linha, há uma opção para enviar o item ou retirá-lo na loja. Esta opção deve ser configurada separadamente no módulo de retirada na loja.
- **Resumo da ordem** – Este módulo mostra um resumo da ordem. As informações incluem subtotal, remessa, impostos e economia. Um cabeçalho pode ser configurado para esse módulo.
- **Código promocional** – Este módulo permite ao cliente resgatar códigos promocionais. Um código promocional pode ser aplicado ou removido.
- **Finalização da compra** – Este módulo inicia a ação de finalização de compra e redireciona o usuário para a página de finalização de compra. Três links devem ser configurados para esse módulo:

    - **Finalização da compra** – Esse link força os clientes a entrar se ainda não estiverem conectados.
    - **Finalização de compra do convidado** – Esse link permite que clientes anônimos coloquem ordens. É mostrado apenas quando os clientes não estão conectados.
    - **Voltar para compra** – Este link permite que os clientes acessem a home page ou qualquer outra página, para que possam continuar comprando.

- **Bloco de conteúdo sofisticado** – Este módulo permite mensagens personalizadas no módulo de carrinho. As mensagens são direcionadas pelo sistema de gerenciamento de conteúdo (CMS). Qualquer mensagem pode ser adicionada, como "For issues with the order, contact 1-800-Fabrikam" (Caso você tenha problemas com a ordem, entre em contato com 1-800-Fabrikam).
- **Retirar na loja** – Este módulo mostra uma lista de lojas próximas, onde um item está disponível para retirada. Por padrão, esse módulo mostra lojas que estão dentro de um raio de 80 quilômetros da localização do cliente. Contudo, o raio de pesquisa pode ser personalizado no módulo. Para cada loja, é feita uma verificação de estoque, se a funcionalidade de verificação de estoque estiver ativada e uma mensagem apropriada informando o que está no estoque ou esgotado do estoque for exibida.
- **Pesquisa na loja pelo Bing Maps** – Este módulo pode ser usado no módulo de retirada na loja. Permite que os clientes pesquisem lojas inserindo um local. A interface de programação de aplicativos (API) de geocodificação do Bing Maps é usada para converter o local inserido pelo cliente em latitude e longitude. Se esse módulo não for usado, apenas as lojas próximas à localização atual do cliente serão exibidas e o cliente não poderá procurar um local diferente.

## <a name="cart-module-settings"></a>Configurações do módulo de carrinho

Os módulos de carrinho têm três configurações que podem ser configuradas:

- **Quantidade máxima** – O número máximo de cada item que pode ser adicionado ao carrinho. Por exemplo, um varejista pode decidir que apenas 10 de cada produto podem ser vendidos em uma única transação.
- **Verificação de estoque** – Quando o valor é definido como **Verdadeiro**, um item é adicionado ao carrinho somente após o módulo da caixa de compra garantir que ele esteja em estoque. Essa verificação de estoque é feita tanto para os cenários em que o item será enviado como para os cenários em que ele será retirado na loja. Se o valor estiver definido como **Falso**, nenhuma verificação de estoque será feita antes que um item seja adicionado ao carrinho e a ordem seja feita.
- **Buffer de estoque** – O estoque é mantido em tempo real e, quando muitos clientes colocam ordens, pode ser difícil manter uma contagem precisa do estoque. Portanto, um buffer pode ser definido para o estoque. Quando uma verificação de estoque é feita, se o estoque for menor que a quantidade do buffer, o produto é tratado como esgotado no estoque. Sendo assim, quando as vendas ocorrem rapidamente por meio de vários canais, para que a contagem do estoque não seja totalmente sincronizada, há menos risco de que um item esgotado no estoque seja vendido.

## <a name="retail-server-interaction"></a>Interação do Retail Server

O módulo de carrinho recupera informações do produto usando as APIs do Retail Server. A ID de carrinho do cookie do navegador é usada para recuperar todas as informações do produto do Retail Server.

## <a name="add-a-cart-module-to-a-page"></a>Adicionar um módulo de carrinho a uma página

Para adicionar um módulo de carrinho a uma nova página e definir as propriedades necessárias, siga estas etapas.

1. Crie um fragmento denominado **fragmento do carrinho** e adicione um módulo de carrinho a ele.
1. No slot **Linha do carrinho de compras** do módulo do carrinho, adicione um módulo de itens de linha do carrinho.
1. No slot **Resumo da ordem**, adicione um módulo de resumo da ordem.
1. No slot **Código promocional**, adicione um módulo de código promocional.
1. No slot **Finalização da compra**, adicione um módulo de finalização da compra.
1. No slot **Localizar na loja**, adicione um módulo de retirada na loja.
1. No módulo de retirada na loja, selecione o slot **Pesquisa na loja** e adicione um módulo de pesquisa na loja pelo Bing Maps.
1. Insira o fragmento e publique-o.
1. Crie um modelo chamado **modelo de carrinho** e adicione o fragmento do carrinho que você acabou de criar.
1. Salve o modelo, insira-o e publique-o.
1. Crie uma página que use o novo modelo.
1. Salve e exiba a página.
1. Insira a página e publique-a.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulo de finalização da compra](add-checkout-module.md)

[Módulo de confirmação da ordem](order-confirmation-module.md)

[Módulo de cabeçalho](author-header-module.md)

[Módulo de rodapé](author-footer-module.md)
