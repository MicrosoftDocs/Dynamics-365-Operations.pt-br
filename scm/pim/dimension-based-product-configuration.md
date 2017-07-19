---
title: "Configuração de produto baseada em dimensão"
description: "A configuração do produto com base na dimensão representa uma solução simples para criação de diversas variantes de produtos de um único produto mestre e sua lista de materiais."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d13fc55342030d96d38f264f6bff9586832b4ab5
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017

---

# <a name="dimension-based-product-configuration"></a>Configuração de produto baseada em dimensão

[!include[banner](../includes/banner.md)]


A configuração do produto com base na dimensão representa uma solução simples para criação de diversas variantes de produtos de um único produto mestre e sua lista de materiais.

A configuração de produto baseada em dimensão é uma das três tecnologias de configuração de produto internas. As duas outras tecnologias são variações pré-definidas e configuração baseada em restrições. As três tecnologias usam um produto mestre como ponto de partida e permitem que o usuário crie várias variantes de produto para um produto mestre.

## <a name="key-concepts"></a>Conceitos principais
A configuração de produto baseada em dimensão baseia-se nos seguintes conceitos principais:

-   Produtos mestres
-   Dimensão de configuração do produto
-   Grupos de configuração
-   Lista de materiais (BOM)
-   Roteiro de configuração
-   Regras de configuração

### <a name="product-masters"></a>Produtos mestres

Um produto mestre é o ponto de partida para qualquer processo de configuração de produto. Para a configuração de produto baseada em dimensão, você precisa de um produto mestre com essa tecnologia de configuração específica e um grupo de dimensões de produto que inclui a dimensão de configuração de produto.

### <a name="configuration-product-dimension"></a>Dimensão de configuração do produto

A dimensão de produto de configuração é usada para identificar variantes de produtos para um produto mestre com a tecnologia de configuração baseada em dimensão. O valor de dimensão de configuração é inserido pelo usuário e deve ajudar a identificar as variantes de produto individuais.

### <a name="configuration-groups"></a>Grupos de configuração

Os grupos de configuração são definidos em um repositório central e podem ser usados para todos os modelos de configuração de produto baseados em dimensão. Os grupos de configuração são associados às linhas individuais de BOM e compõem um grupo de linhas que são mutuamente exclusivas. Isso significa que apenas uma linha em um grupo pode ser selecionada para uma única variante de produto.

### <a name="bill-of-materials-bom"></a>Lista de materiais (BOM)

A BOM representa os blocos de construção para uma configuração de produto baseada em dimensão. Ela deve incluir todos os produtos diferentes que podem ser usados em qualquer variante de produto. Cada linha na BOM pode fazer referência a um grupo de configuração. Se uma linha não fizer referência a um grupo de configuração, ela será incluída em todas as variantes de produto.

### <a name="configuration-route"></a>Roteiro de configuração

O roteiro de configuração determina a sequência dos grupos de configurações, pois serão exibidos ao usuário durante o processo de configuração de produto.

### <a name="configuration-rules"></a>Regras de configuração

As regras de configuração representam um mecanismo para assegurar que um produto incluído em um grupo de configuração em uma BOM garanta uma inclusão ou uma exclusão de um produto em um grupo de configurações diferentes na mesma BOM.

## <a name="product-modeling-process"></a>Processo de modelagem do produto
A sequência natural para compilar um modelo de produto para um produto baseado em dimensão começa com a definição dos grupos de configuração relevantes. É importante garantir que todos os produtos que serão usados na BOM tenham sido liberados para a empresa para a qual o modelo de produto foi criado. Com esses blocos de construção em vigor, o usuário poderá criar a BOM e atribuir grupos de configuração a todas as linhas relevantes da BOM. Quando a BOM estiver concluída, um roteiro de configuração poderá ser definido para o pedido de grupos de configuração na sequência apropriada. \[caption id="attachment\_282671" align="alignnone" width="1187"\][![Processo de modelagem de produto baseado em dimensão](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Processo de modelagem de produto baseado em dimensão\[/caption\] Se houver alguns produtos de grupos de configuração diferentes que devem ou não ser usados em conjunto, é possível criar regras de configuração que impõem esses relacionamentos de produtos. Após a BOM ser vinculada a um produto mestre baseado em dimensão por meio de uma versão da BOM e ambos serem aprovados e ativados, será possível criar configurações de produto e inserir um nome para cada configuração. As configurações podem ser definidas antes que qualquer transação seja gerada ou possa ser feita quando houver necessidade de uma determinada configuração.

### <a name="suggested-use"></a>Uso sugerido

A tecnologia de configuração baseada em dimensão é melhor usada para produtos com variabilidade limitada e a combinação de estilo, cor, tamanho e configuração das dimensões do produto não for adequada para identificar uma variante de produto específica. Um exemplo poderia ser uma bicicleta com altura de quadro, tamanho de roda, tipos de freio, e embreagem diferente.




