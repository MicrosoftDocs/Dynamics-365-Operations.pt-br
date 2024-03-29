---
title: Visão geral das páginas de detalhes do produto
description: Este artigo fornece uma visão geral das páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/23/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 4856e6e208834d7dcc16d19ad4afb63c329a5868
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278491"
---
# <a name="product-details-pages-overview"></a>Visão geral das páginas de detalhes do produto

[!include [banner](includes/banner.md)]

Este artigo fornece uma visão geral das páginas de detalhes do produto (PDPs) no Microsoft Dynamics 365 Commerce.

Uma PDP fornece informações detalhadas sobre um produto e permite que os clientes selecionem opções de produtos, como tamanho, estilo e cor. Uma PDP deve mostrar todas as informações do produto que um cliente precisa para tomar uma decisão de compra.

A ilustração a seguir mostra um exemplo de uma PDP.

![Exemplo de uma página de detalhes do produto.](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Módulos de cabeçalho e rodapé

A parte superior de uma PDP possui um cabeçalho que mostra todas as categorias de produtos e outras páginas pelas quais o varejista deseja que os clientes naveguem. A parte inferior da página possui um rodapé que contém links rápidos para vários artigos que podem interessar aos clientes.

## <a name="buy-box-module"></a>Módulo de caixa de compra

O módulo mais importante em um PDP é o módulo de caixa de compra, que aparece como o primeiro item na seção principal da página. Um módulo de caixa de compra mostra informações importantes sobre os produtos, como o nome do produto, a descrição do produto, o preço do produto, imagens do produto e classificações de produtos.

O módulo da caixa de compra permite que o cliente selecione as opções do produto (por exemplo, tamanho, estilo e cor) e adicione o produto ao carrinho. Ele também permite que o cliente compre o produto on-line e o retire em uma loja. O módulo de compra on-line e retirada na loja usa a integração com as APIs (interfaces de programação de aplicativos) do Bing Maps para encontrar lojas próximas em outro local que o cliente especificar.

Um módulo da caixa de compra requer uma ID de produto. Essa ID é derivada do contexto de página. Se um módulo de caixa de compra for adicionado a uma página em que o contexto da página não inclua um ID do produto, ele não renderizará as informações corretamente.

## <a name="product-specifications-module"></a>Módulo de especificações do produto

O módulo de especificações de produto pode ser usado para apresentar detalhes adicionais sobre o produto. Esses detalhes são obtidos dos atributos do produto no Commerce. O módulo de especificações do produto mostra cada atributo onde a propriedade **visível** é definida como **verdadeiro**. Requer uma ID de produto para recuperar os atributos do produto.

## <a name="recommendations-module"></a>Módulo de recomendações

O módulo de recomendações é um módulo importante em uma PDP. Enquanto os clientes procuram produtos, mais opções de produtos devem ser apresentadas a eles, para que eles possam encontrar o produto correto e fazer uma compra. As recomendações ajudam os clientes a descobrir facilmente o conteúdo relacionado e continuar comprando.

Diferentes tipos de listas de recomendações estão disponíveis:

- A lista **As pessoas também gostam de** é baseada no aprendizado de máquina. Ela usa o histórico de transações de outros clientes para fornecer recomendações. Essa lista é gerada pelo serviço de recomendações e se parece com as listas "Clientes que compraram isso também compraram ...". Uma ID de produtos é necessária para gerar esta lista.
- Uma lista **Relacionada** pode ser configurada para um produto no Commerce. Por exemplo, para uma bolsa de viagem de couro marrom, mais bolsas de couro ou projetadas para viagem podem ser configuradas para a lista relacionada. Outros tipos de listas relacionadas, como **Acessórios** e **Mais deste tipo**, também podem ser configurados no Commerce. Uma ID de produtos é necessária para gerar esta lista. Portanto, se ele for adicionado a uma página inicial, em que o contexto da página não inclua uma ID do produto, a lista ficará vazia.
- Listas de recomendações geradas algoritmicamente, como **Mais Populares**, **Mais Vendidos** e **Novo** podem ser usadas em PDPs. Embora essas listas possam não estar diretamente relacionadas ao produto na PDP, elas são outra maneira de ajudar os clientes a encontrar produtos que possam interessá-los. Esses tipos de listas não exigem uma ID de produto. São listas genéricas que são geradas com base nos padrões de compras no site.
- As listas editoriais são listas selecionadas manualmente. Por exemplo, um fornecedor pode decidir selecionar as listas de produtos manualmente que ele deseja mostrar.

## <a name="ratings-and-reviews-modules"></a>Módulos de classificações e revisões

Três módulos podem ser usados para mostrar e adicionar revisões:

- **Revisões** – este módulo lista classificações e revisões fornecidas por outros clientes. Os clientes podem classificar e filtrar as revisões. Este módulo também permite que os clientes gostem ou não das revisões e relatem problemas.
- **Escrever revisão** – este módulo permite que os clientes escrevam suas próprias revisões de um produto.
- **Histograma de classificações** – este módulo inclui um histograma que mostra a tendência de classificações de um produto.

Para obter mais detalhes, consulte [Visão geral de classificações e opiniões](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Módulos de marketing

Se o conteúdo de marketing for exclusivo de um produto específico, qualquer módulo de marketing poderá ser adicionado à PDP. Você pode adicionar os módulos de marketing para uma PDP "enriquecendo" a página. Para obter mais detalhes, consulte [Enriquecer uma página de produto](enrich-product-page.md).

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da home page](quick-tour-home-page.md)

[Visão geral das páginas de carrinho e de finalização da compra](quick-tour-cart-checkout.md)

[Visão geral das páginas de gerenciamento da conta](quick-tour-account-management.md)

[Enriquecer uma página de detalhes de produto](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
