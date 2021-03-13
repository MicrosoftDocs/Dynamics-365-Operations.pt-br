---
title: Módulo de exibição rápida
description: Este tópico abrange os módulos de exibição rápida e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 7e8244a06c515029b559b2061d9a25c7355e9e14
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097043"
---
# <a name="quick-view-module"></a>Módulo de exibição rápida

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Este tópico abrange os módulos de exibição rápida e descreve como adicioná-los a páginas de site no Microsoft Dynamics 365 Commerce.

O módulo de exibição rápida permite que os usuários visualizem rapidamente as informações do produto quando pesquisam produtos em uma página de lista e adicionem um ou mais produtos ao carrinho da página da lista, sem precisarem ir à página de detalhes do produto (PDP). O módulo de exibição rápida fornece uma visão geral das informações sobre o produto de que os usuários precisam para criar uma decisão de "adicionar ao carrinho". Ele também fornece um link para a PDP, de forma que os usuários possam ver mais detalhes e opções de compra dos produtos.

O módulo de exibição rápida é compatível com os módulos [coleção de produtos](product-collection-module-overview.md) e [resultados de pesquisa](search-result-module.md).

> [!IMPORTANT]
> O módulo de exibição rápida está disponível a partir do Commerce versão 10.0.17.

A ilustração a seguir mostra um exemplo de um módulo de exibição rápida em uma página de lista de produtos.

![Exemplo de um módulo de exibição rápida em uma página de lista de produtos](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a>Propriedades do módulo

O módulo de exibição rápida oferece suporte a algumas das mesmas funções que o módulo de caixa de compra. Portanto, as propriedades de um módulo de exibição rápida são parecidas com as propriedades de um módulo de caixa de compra.

| Propriedade | Valores | descrição |
|----------------|--------|-------------|
| Marca do título | **H1**, **H2**, **H3**, **H4**, **H5** ou **H6** | Esta propriedade define a marca do título para o título do produto. Se o módulo de exibição rápida estiver na parte superior da página, essa propriedade deverá ser definida como **H1** para atender aos padrões de acessibilidade. |
| Permitir preço personalizado | **Verdadeiro** ou **Falso** | Se esta propriedade for definida como **Verdadeiro**, o usuário poderá inserir um preço personalizado. |
| Preço mínimo | Inteiro | Esta propriedade será aplicável somente se a propriedade **Permitir preço personalizado** estiver definida como **Verdadeiro**. Ela define o preço mínimo que o usuário pode inserir (por exemplo, US$ 1). |
| Preço máximo | Inteiro | Esta propriedade será aplicável somente se a propriedade **Permitir preço personalizado** estiver definida como **Verdadeiro**. Ela define o preço máximo que o usuário pode inserir (por exemplo, US$ 1.000). |

## <a name="commerce-site-builder-settings"></a>Configurações do construtor de sites do Commerce

Assim como o módulo de caixa de compra, o módulo de exibição rápida respeita as configurações em **Configurações do site \> Extensões \> Adicionar produto ao carrinho**. No entanto, a configuração **Navegar para a página do carrinho** é ignorada, pois ela é inconsistente com a finalidade do módulo de exibição rápida, que permite que os usuários pesquisem vários produtos em uma página de lista e os adicionem ao carrinho sem sair da página de lista.

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a>Adicionar um módulo de exibição rápida a um módulo de coleção de produtos

É possível adicionar um módulo de exibição rápida aos módulos coleção de produtos e resultados de pesquisa.

Para adicionar um módulo de exibição rápida a um módulo de coleção de produtos no construtor de sites do Commerce, siga estas etapas.

1. Vá para **Páginas** e selecione a página inicial do site da Fabrikam.
1. Vá para qualquer módulo de **Coleção de produtos** na página inicial, selecione as reticências (**...**) e depois **Adicionar módulo**.
1. Na caixa de diálogo **Adicionar Módulo**, selecione o módulo **Exibição rápida** e depois **OK**.
1. No painel propriedades do módulo **Exibição rápida**, selecione **Título**. Na caixa de diálogo **Título**, defina o campo **Nível do título** como **H2** e então selecione **OK**.
1. Selecione **Salvar**, **Concluir edição** para fazer check-in da página e depois selecione **Publicar** para publicá-lo.

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral da biblioteca de módulos](starter-kit-overview.md)

[Módulo de caixa de compra](add-buy-box.md)

[Módulos de coleta de produtos](product-collection-module-overview.md)

[Módulo de resultados de pesquisa](search-result-module.md)
