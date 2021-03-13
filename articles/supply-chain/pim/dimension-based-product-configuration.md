---
title: Visão geral de configuração de produtos baseada em dimensão
description: A configuração do produto com base na dimensão representa uma solução simples para criação de diversas variantes de produtos de um único produto mestre e sua lista de materiais.
author: cvocph
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConfigRule, BOMTable, ConfigChooseFromRoute, ConfigGroup, ConfigHierarchy, EcoResDimensionBasedConfiguration
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19821
ms.assetid: 4db9890b-306b-4be7-ba98-3be2094d561f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1e1dbf7364b13e6a7abcfc563364bbea329e9ac
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007732"
---
# <a name="dimension-based-product-configuration-overview"></a>Visão geral de configuração de produtos baseada em dimensão

[!include [banner](../includes/banner.md)]

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
A sequência natural para compilar um modelo de produto para um produto baseado em dimensão começa com a definição dos grupos de configuração relevantes. É importante garantir que todos os produtos que serão usados na BOM tenham sido liberados para a empresa para a qual o modelo de produto foi criado. Com esses blocos de construção em vigor, o usuário poderá criar a BOM e atribuir grupos de configuração a todas as linhas relevantes da BOM. Quando a BOM estiver concluída, um roteiro de configuração poderá ser definido para o pedido de grupos de configuração na sequência apropriada. [![Processo de modelagem de produto baseado em dimensão](./media/dimension-based-product-modeling-process-v1.png)](./media/dimension-based-product-modeling-process-v1.png) Se houver alguns produtos de grupos de configuração diferentes que devem ou não ser usados junto, você poderá criar regras de configuração que aplicam esses relacionamentos de produto. Após a BOM ser vinculada a um produto mestre baseado em dimensão por meio de uma versão da BOM e ambos serem aprovados e ativados, será possível criar configurações de produto e inserir um nome para cada configuração. As configurações podem ser definidas antes que qualquer transação seja gerada ou possa ser feita quando houver necessidade de uma determinada configuração.

### <a name="suggested-use"></a>Uso sugerido

A tecnologia de configuração baseada em dimensão é melhor usada para produtos com variabilidade limitada e a combinação de estilo, cor, tamanho e configuração das dimensões do produto não for adequada para identificar uma variante de produto específica. Um exemplo poderia ser uma bicicleta com altura de quadro, tamanho de roda, tipos de freio, e embreagem diferente.

### <a name="next-step"></a>Próxima etapa 

As seguintes oito guias de tarefa são listadas na ordem em que devem ser concluídas. 

1.  [Criar um produto mestre baseado em dimensão](tasks/create-dimension-based-product-master.md)
2.  [Liberar um produto mestre baseado na dimensão](tasks/release-dimension-based-product-master.md)
3.  [Completar instalação básica de um produto mestre lançado](tasks/complete-basic-setup-released-product-master.md)
4.  [Definir grupos de configuração](tasks/define-configuration-groups.md)
5.  [Criar uma lista de materiais para um produto mestre baseado na dimensão](tasks/create-bill-materials-dimension-based-product-master.md)
6.  [Definir roteiros de configuração](tasks/define-configuration-route.md)
7.  [Criar regras de configuração](tasks/create-configuration-rules.md)
8.  [Criar configurações baseadas em dimensão](tasks/create-dimension-based-configurations.md)

