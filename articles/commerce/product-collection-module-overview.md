---
title: Módulos de coleção de produtos
description: Este artigo fornece uma visão geral dos módulos de coleta de produtos no Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 05/18/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 02a3d6314729f51d6c1dced5037f78d12355c09a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871650"
---
# <a name="product-collection-modules"></a>Módulos de coleção de produtos

[!include [banner](includes/banner.md)]

Este artigo fornece uma visão geral dos módulos de coleta de produtos no Microsoft Dynamics 365 Commerce.

A descoberta de produtos é a principal ferramenta usada pelos varejistas para interagir com seus clientes em um site de comércio eletrônico. Os módulos de coleta de produtos ajudam os varejistas a criar experiências atraentes de compras, fornecendo uma interface visual intuitiva que pode ser usada para criar rapidamente coletas de produtos.

Os módulos de coleta de produtos representam produtos e serviços físicos no site. Um módulo de coleta de produtos geralmente está vinculado a uma página de detalhes em que os clientes podem comprar um produto ou serviço ou aprender mais sobre ele. 

As fontes para coletas de produtos podem ser listas dos seguintes quatro tipos:

- As listas editoriais de produtos definidos manualmente no Dynamics 365 Commerce como produtos relacionados para um produto ou listas de produtos
- Listas algorítmicas, como listas de produtos novos, mais vendidos ou mais populares
- Listas de recomendação que se baseiam em aprendizagem de máquina
- Listas de personalização que dão suporte a resultados personalizados para um cliente. Os clientes devem fazer logon no site de comércio eletrônico para ver resultados personalizados. Os usuários convidados não veem resultados personalizados. Os clientes podem cancelar a personalização da [página de gerenciamento de contas](account-management.md).

A ilustração a seguir mostra os diferentes tipos de coletas de produto que estão sendo usadas em um site de comércio eletrônico.

![Exemplo dos diferentes tipos de coletas de produtos em um site de comércio eletrônico.](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Sempre use módulos de coleta de produtos para mostrar um grupo de produtos de um tipo semelhante.

## <a name="product-collection-modules-and-types"></a>Módulos e tipos de coleta de produtos

A tabela a seguir descreve vários tipos de módulos de coleta de produtos no Dynamics 365 Commerce.

| Módulos de coleta de produtos  | Tipo | Descrição |
|----------------------------|------|-------------|
| Categoria                   | Categoria | Este módulo mostra uma lista de produtos em uma categoria, conforme definido pela hierarquia de categoria de navegação que o varejista criou para um canal. |
| Produtos relacionados           | Editorial | Esse módulo mostra uma lista de produtos que um gerente de merchandising configurou como produtos relacionados no Commerce, para o tipo de relação que o autor selecionou. |
| Resultados da pesquisa             | Consulta de pesquisa | Esse tipo de módulo de coleta de produtos mostra uma lista de produtos que melhor corresponde à consulta de pesquisa inserida pelo cliente. |
| Listas de produtos selecionados      | Editorial | Este módulo mostra listas personalizadas que os comerciantes e editores criaram no Commerce. |
| Novos                        | Algorítmico | Este módulo mostra uma lista de produtos mais novos que foram classificadas para canais e os catálogos. Esta lista pode mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção. |
| Mais vendidos               | Algorítmico | Este módulo mostra uma lista de produtos que estão classificados por número mais alto de venda. Esta lista pode mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção. |
| Mais populares                   | Algorítmico | Este módulo mostra uma lista de produtos de melhor desempenho para um determinado período. Esta lista pode mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção. |
| Frequentemente comprado junto | Inteligência artificial/aprendizado de máquina | Este módulo usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados que são frequentemente comprados em conjunto com um determinado produto. Esta lista pode mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção. |
| As pessoas também gostam           | Inteligência artificial/aprendizado de máquina | Este módulo usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados a um determinado produto. Esta lista pode mostrar resultados personalizados para um usuário conectado, caso o autor do site escolha essa opção. |
| Seleções para Você              | Inteligência artificial/aprendizado de máquina | Este módulo usa o aprendizado de máquina para analisar os padrões de compra do usuário conectado e fornecer recomendações personalizadas que se baseiam nesses padrões de compra. Para um usuário convidado, esta lista será recolhida. |

## <a name="supported-modules"></a>Módulos com suporte 

O módulo de coleção de produtos oferece suporte ao [módulo de exibição rápida](quick-view-module.md), que permite que os usuários vejam informações sobre o produto e adicionem itens ao carrinho usando uma página de coleção de produtos.

## <a name="add-a-product-collection-module-to-a-category-page"></a>Adicionar um módulo de coleta de produtos a uma página de categoria

Para adicionar um módulo de coleta de produtos a uma página de categoria, siga estas etapas.

1. Acesse **Páginas** e selecione **Novo** para criar uma nova página.
1. Na caixa de diálogo **Criar uma nova página**, em **Nome da página**, insira um nome de página apropriado e selecione **Avançar**.
1. Em **Escolher um modelo**, selecione o mesmo modelo usado pela página de categoria padrão e selecione **Avançar**.
1. Em **Escolher um layout**, selecione um layout de página (por exemplo, **Layout flexível**) e selecione **Avançar**.
1. Em **Revisar e concluir**, revise a configuração da página. Se você precisar editar as informações da página, selecione **Voltar**. Se as informações da página estiverem corretas, selecione **Criar página**. 
1. No slot **Sub-rodapé**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Contêiner** e, depois, **OK**.
1. No slot **Contêiner**, selecione as reticências (**...**) e, depois, **Adicionar módulo**.
1. Na caixa de diálogo **Selecionar módulos**, selecione o módulo **Coleção de produtos** e, depois, **OK**.  
1. No painel de propriedades do módulo de coleta de produtos, selecione **Adicionar uma lista de produtos**.
1. Na caixa de diálogo **Selecionar configuração da lista de produtos**, selecione o tipo de lista, a origem da lista e insira o número de itens e qualquer outra opção disponível para o tipo de lista. Configure quaisquer outras opções disponíveis para o tipo de lista. Para obter mais informações sobre os tipos de listas, consulte a tabela a seguir. 
1. Selecione **OK**.
1. Selecione **Salvar** e depois selecione **Visualizar** para visualizar a página.
1. Selecione **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

A tabela a seguir mostra os tipos de lista disponíveis para seleção na caixa de diálogo **Selecionar configuração da lista de produtos**.

| Tipo                       | Descrição | Utilização | Contexto da página | Contexto específico | Personalização |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Produtos por categoria       | Uma lista de produtos que pertencem uma categoria específica. Esta categoria é determinada do contexto de página ou do contexto que o autor fornece. | Esse tipo de lista pode ser usado em qualquer página (por exemplo, uma home page, página de categorias, página de marketing ou página de detalhes do produto\[PDP\]) para promover uma categoria de produtos específica. | Categoria do contexto da página, onde disponível (por exemplo, uma página de categoria) | O autor pode fornecer uma categoria específica como contexto para a lista. | Não aplicável |
| Produtos relacionados           | Uma lista de produtos que um gerente de merchandising configurou como produtos relacionados para o tipo de relação no Commerce. | Esse tipo de lista é usado principalmente em PDPs, mas pode ser usado em qualquer página se um produto pai for fornecido. | Produto da página, tipo de relação (obrigatório) | O produto pode ser selecionado no seletor, e o tipo de relação é usado. | Não aplicável |
| Selecionado                    | Uma lista personalizada criada por comerciantes e editores no Commerce. | Enriqueça a página da categoria, a página inicial, as páginas de finalização da compra e do carrinho e as páginas de produtos | Não aplicável | Não aplicável | Não aplicável |
| Algorítmico                | <ul><li>**Novos** – Uma lista de produtos mais novos que foram classificadas para canais e os catálogos.</li><li>**Mais vendidos** – Uma lista de produtos que estão classificados por número mais alto de venda.</li><li>**Mais populares** – Uma lista de produtos de melhor desempenho para um determinado período.</li></ul> | Página inicial, página de categoria enriquecida e páginas de carrinho e de finalização de compra | Categoria do contexto da página (por exemplo, uma página de categoria) | A categoria que é determinada pelo autor do site | Suportado |
| Frequentemente comprado junto | Uma lista que usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados que são frequentemente comprados em conjunto com um determinado produto. | Este tipo de lista é aplicável somente à página do carrinho. | Carrinho | Não aplicável | Suportado |
| As pessoas também gostam           | Uma lista que usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados a um determinado produto. | Esse tipo de lista é usado no PDPs para mostrar os produtos que outros clientes compraram. | Contexto do produto na página | O produto que é fornecido pelo autor do site | Suportado |
| Seleções para Você              | Uma lista que usa o aprendizado de máquina para determinar as preferências do cliente. | Este tipo de lista pode ser usado em qualquer página. | Não Aplicável| Não Aplicável | Suportado | 

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

[Visão geral das recomendações de produtos](product-recommendations.md)

[Módulo de exibição rápida](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
