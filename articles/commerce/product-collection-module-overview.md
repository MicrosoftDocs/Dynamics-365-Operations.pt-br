---
title: Módulos de coleta de produtos
description: Este tópico fornece uma visão geral das páginas dos módulos de coleta de produtos no Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785458"
---
# <a name="product-collection-modules"></a>Módulos de coleta de produtos  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tópico fornece uma visão geral das páginas dos módulos de coleta de produtos no Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visão geral

A descoberta de produtos é a principal ferramenta usada pelos varejistas para interagir com seus clientes em um site de comércio eletrônico. Os módulos de coleta de produtos ajudam os varejistas a criar experiências atraentes de compras, fornecendo uma interface visual intuitiva que pode ser usada para criar rapidamente coletas de produtos.

Os módulos de coleta de produtos representam produtos e serviços físicos no site. Um módulo de coleta de produtos geralmente está vinculado a uma página de detalhes em que os clientes podem comprar um produto ou serviço ou aprender mais sobre ele. 

As fontes para coletas de produtos podem ser listas de três tipos:

- As listas editoriais de produtos definidos manualmente no Dynamics 365 Retail como produtos relacionados para um produto ou listas de produtos
- Listas algorítmicas, como listas de produtos novos, mais vendidos ou mais populares
- Listas de recomendação que se baseiam em aprendizagem de máquina

A ilustração a seguir mostra os diferentes tipos de coletas de produto que estão sendo usadas em um site de comércio eletrônico.

![Exemplo dos diferentes tipos de coletas de produtos em um site de comércio eletrônico](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Sempre use módulos de coleta de produtos para mostrar um grupo de produtos de um tipo ou tema semelhante.

## <a name="product-collection-modules-and-types"></a>Módulos e tipos de coleta de produtos

A tabela a seguir descreve vários tipos de módulos de coleta de produtos no Dynamics 365 Commerce.

| Módulos de coleta de produtos  | Tipo | Descrição |
|----------------------------|------|-------------|
| Procura de categoria            | Editorial | Esse tipo de módulo de coleta de produtos usa a hierarquia de categorias de navegação que o varejista criou para um canal de varejo para mostrar um fluxo de navegação para produtos oferecidos em uma categoria de site específica. |
| Resultados da pesquisa             | Consulta de pesquisa | Esse tipo de módulo de coleta de produtos mostra uma lista de produtos que melhor corresponde à consulta de pesquisa inserida pelo cliente. |
| Produtos relacionados           | Editorial | Esse tipo de módulo de coleta de produtos mostra uma lista de produtos que um gerente de merchandising configurou como produtos relacionados no Varejo, para o tipo de relação que o autor selecionou. |
| Listas de produtos selecionados      | Editorial | Esse tipo de módulo de coleta de produtos mostra listas personalizadas criadas por comerciantes e editores no Varejo. |
| Novos                        | Algorítmico | Este tipo de módulo de coleta de produtos mostra uma lista dos produtos mais novos que foram classificados em canais e catálogos. |
| Mais vendidos               | Algorítmico | Este tipo de módulo de coleta de produtos mostra uma lista de produtos que estão classificados por número mais alto de venda. |
| Mais populares                   | Algorítmico | Este tipo de módulo de coleta de produtos mostra uma lista dos produtos com melhor desempenho por um determinado período. |
| Frequentemente comprado junto | Inteligência artificial/aprendizado de máquina | Esse tipo de módulo de coleta de produtos usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados que são frequentemente comprados em conjunto com um determinado produto. |
| As pessoas também gostam           | Inteligência artificial/aprendizado de máquina | Esse tipo de módulo de coleta de produtos usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados a um determinado produto. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Adicionar um módulo de coleta de produtos a uma página de categoria

Para adicionar um módulo de coleta de produtos a uma página de categoria, siga estas etapas.

1. No Dynamics 365 Commerce, acesse seu site e crie uma página que usa o mesmo modelo da sua página de categoria padrão.
1. Na estrutura de tópicos da página, selecione o slot de **Sub-rodapé**, selecione o botão de reticências (**...**) e depois **Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione **Contêiner** e depois **OK**.
1. No módulo de contêiner, selecione o botão de reticências e selecione**Adicionar Módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione **Coleta do produto** e depois **OK**.
1. Defina as configurações selecionando uma fonte de dados e entradas apropriadas para a coleta de produtos.
1. No painel de propriedades do módulo de coleta de produtos, selecione **Adicionar uma lista de produtos**.
1. Na caixa de diálogo **Selecionar configuração da lista de produtos** selecione o tipo de lista, insira o número de itens e qualquer outra opção disponível para o tipo de lista. Para obter mais informações sobre os tipos de listas, consulte a tabela a seguir. 
1. Selecione **OK**.
1. Salve a página e faça check-in.

A tabela a seguir mostra os tipos de lista disponíveis para seleção na caixa de diálogo **Selecionar configuração da lista de produtos**.
   
| Tipo                       | Descrição | Prática geral | O contexto que pode ser obtido do contexto de página | O contexto pelo qual o autor pode substituir o contexto da página |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Produtos por categoria       | Uma lista de produtos que pertencem uma categoria específica. Esta categoria é determinada do contexto de página ou do contexto que o autor fornece. | Enriqueça a página da categoria, a página inicial, as páginas de finalização da compra e do carrinho e as páginas de produtos | Categoria | Categoria determinada pelo autor |
| Produtos relacionados           | Uma lista de produtos que um gerente de merchandising configurou como produtos relacionados no Varejo para o tipo de relação. | Páginas de produtos, páginas do carrinho e de finalização da compra, página da lista de desejos e página da conta do cliente | Produto, Tipo de relação (Obrigatório)  | Produto, Tipo de relação |
| Selecionado                    | Uma lista personalizada criada por comerciantes e editores no varejo. | Enriqueça a página da categoria, a página inicial, as páginas de finalização da compra e do carrinho e as páginas de produtos | Não aplicável | Seletor de lista |
| Algorítmico                | <ul><li>**Novos** – Uma lista de produtos mais novos que foram classificadas para canais e os catálogos.</li><li>**Mais vendidos** – Uma lista de produtos que estão classificados por número mais alto de venda.</li><li>**Mais populares** – Uma lista de produtos de melhor desempenho para um determinado período.</li></ul> | Página inicial, página de categoria enriquecida e páginas de carrinho e de finalização de compra | Categoria | Categoria determinada pelo autor |
| Frequentemente comprado junto | Uma lista que usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados que são frequentemente comprados em conjunto com um determinado produto. | Páginas de produto, e páginas do carrinho e de finalização de compra | Produto, Carrinho | Incluir carrinho |
| As pessoas também gostam           | Uma lista que usa o aprendizado de máquina para analisar padrões de compra do consumidor e recomendar itens relacionados a um determinado produto. | Páginas de produto, e páginas do carrinho e de finalização de compra | Produto, Carrinho | Não aplicável |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do kit de início](starter-kit-overview.md)

[Módulo do carrossel](add-carousel.md)

[Módulo de bloco de conteúdo sofisticado](add-content-rich-block.md)

[Módulo de posicionamento de conteúdo](add-content-placement-modules.md)

[Módulo de contêiner](add-container-module.md)

[Módulo de caixa de compra](add-buy-box.md)

