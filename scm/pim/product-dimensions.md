---
title: "Dimensões do produto"
description: "Existem quatro dimensões do produto - cor, tamanho e configuração, estilo. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Dimensões do produto

Existem quatro dimensões do produto - cor, tamanho e configuração, estilo. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas.

As dimensões de produto são as características que servem para identificar uma variante do produto. Você pode usar combinações de dimensões do produto para definir variantes de produto. Você deve definir pelo menos uma dimensão de produto para um produto mestre para criar uma variante do produto.
Grades de produtos
----------------

As variantes dos produtos também são chamadas de itens. Um item é um produto real, que não é o mesmo que um serviço. Também é possível definir um produto mestre ao tipo de serviço. Usando o tipo de Serviço você poderá especificar as variantes de produtos que incluem serviços. Por exemplo, você pode especificar um produto mestre do serviço de consultoria e variantes de produtos para serviços que são realizados por consultores superiores e por consultores júnior.

## <a name="product-dimensions"></a>Dimensões do produto
As seguintes dimensões de produto estão disponíveis: Configuração, tamanho, cor, estilo e. Uma grade de produto pode ser gerada com base nos valores de dimensão do produto.

Os valores de dimensões de produto como tamanho, cor e estilo podem ser criados em ** ** ** tamanho, cor e estilo ** ** ** em páginas, que podem ser acessados dos seguintes locais: ** O gerenciamento de informações sobre produtos ** &gt; ** ** ** &gt; dimensão de instalação e grade agrupa ** &gt; ** tamanhos/cores e estilos **. Os valores de dimensão do produto para a Dimensão de configuração, geralmente, são desenvolvidos usando o Configurador de produtos ou o Configurador com base na dimensão. As dimensões do produto também podem ser criadas e mantidas na página **Dimensões do produto**, que podem ser acessadas dos seguintes locais:
-   Clique ** gerenciamento de informações sobre produtos ** &gt; ** produtos ** &gt; ** produtos mestres **. ** O painel de ações **, clique ** ** dimensões do produto.
-   Clique ** gerenciamento de informações sobre produtos ** &gt; ** produtos ** &gt; ** todos os produtos e produtos mestres **. Selecione um produto mestre. ** O painel de ações **, clique ** ** dimensões do produto.
-   Clique ** gerenciamento de informações sobre produtos ** &gt; ** produtos lançados **. Selecione um produto mestre. ** O painel de ações **, clique ** ** produto. No grupo de **Produto mestre**, clique em **Dimensões do produto**.

O número de variantes que você pode criar para um item é limitado pelo número de possíveis combinações de dimensão do produto.
| **Dica **                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| Quando você usa um produto, por exemplo, em uma linha de ordem, você seleciona as dimensões do produto para identificar a variante do produto com a qual você deseja trabalhar. |

## <a name="example"></a>Exemplo
Uma empresa vende jeans denim. O item, Jeans, usa as dimensões de Cor e de Tamanho do produto. Os jeans são vendidos em três cores diferentes e seis tamanhos diferentes. Cores: Azul, Preto, Marrom - Tamanhos: PP, P, M, G, GG, GGG Nem todos estão disponíveis nas três cores. Se todas as combinações estivessem disponíveis, seriam criados 18 tipos diferentes de jeans. Neste exemplo, somente as nove combinações de variante de produto a seguir são produzidas.

| Cor | Tamanho |
|-------|------|
| Azul  | PP   |
| Azul  | D    |
| Azul  | S    |
| Preto | S    |
| Preto | G    |
| Preto | GG   |
| Marrom | P    |
| Marrom | GG   |
| Marrom | GGG  |




