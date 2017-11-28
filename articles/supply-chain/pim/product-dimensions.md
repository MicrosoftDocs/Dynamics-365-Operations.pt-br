---
title: "Dimensões do produto"
description: "Existem quatro dimensões do produto - Cor, Configuração, Tamanho e Estilo. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 68f4bfcf62b5e7c65cbe361b510c2769b0e9bebb
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="product-dimensions"></a>Dimensões do produto

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


Existem quatro dimensões do produto - Cor, Configuração, Tamanho e Estilo. Você combina dimensões de produto em grupos de dimensões e atribui grupos de dimensões a produtos mestres. As combinações de dimensões de produto determinam como as variantes de produto serão definidas.

As dimensões de produto são as características que servem para identificar uma variante do produto. Você pode usar combinações de dimensões do produto para definir variantes de produto. Você deve definir pelo menos uma dimensão de produto para um produto mestre para criar uma variante do produto.
Grades de produtos
----------------

As variantes dos produtos também são chamadas de itens. Um item é um produto real, que não é o mesmo que um serviço. Também é possível definir um produto mestre com o tipo Serviço. Usando o tipo de Serviço você poderá especificar as variantes de produtos que incluem serviços. Por exemplo, você pode especificar um produto mestre do serviço de consultoria e variantes de produtos para serviços que são realizados por consultores superiores e por consultores júnior.

## <a name="product-dimensions"></a>Dimensões do produto
As dimensões de produto a seguir estão disponíveis: Configuração, Cor, Tamanho e Estilo. Uma grade de produto pode ser gerada com base nos valores de dimensão de produto.

Os valores das dimensões do produto como Tamanho, Cor e Estilo podem ser criados nas páginas **Tamanho**, **Cor** e **Estilo**, que podem ser acessadas dos seguintes locais **Gerenciamento de informações do produto** &gt; **Configuração** &gt; **Grupos de dimensões e variantes** &gt; **Tamanhos/Cores/Estilos**. Os valores de dimensão do produto para a Dimensão de configuração, geralmente, são desenvolvidos usando o Configurador de produtos ou o Configurador com base na dimensão. As dimensões do produto também podem ser criadas e mantidas na página **Dimensões do produto**, que podem ser acessadas dos seguintes locais:
-   Clique em **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos mestres**. No **Painel de Ação**, clique em **Dimensões do produto**.
-   Clique em **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Todos os produtos e produtos mestres**. Selecione um produto mestre. No **Painel de Ação**, clique em **Dimensões do produto**.
-   Clique em **Gerenciamento de informações do produto** &gt; **Produtos liberados**. Selecione um produto mestre. No **Painel de Ação**, clique em **Produto**. No grupo de **Produto mestre**, clique em **Dimensões do produto**.

O número de variantes que você pode criar para um item é limitado pelo número de possíveis combinações de dimensão do produto.
| **Dica**                                                                                                                                              |
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






