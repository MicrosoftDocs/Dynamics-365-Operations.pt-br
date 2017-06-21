---
title: Grupos de custos
description: "Os grupos de custos fornecem a base para a segmentação e análise de contribuições de custo no custo calculado de um item fabricado, como as contribuições de custo para materiais, trabalho e custos gerais indiretos. A segmentação de grupos de custo tem vários sinônimos dentro dos ambientes de fabricação, como divisão de custo, decomposição de custo ou classificação de custo."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: fb335a521a1a79ea7d978171d233364c58765a0b
ms.contentlocale: pt-br
ms.lasthandoff: 05/25/2017


---

# <a name="cost-groups"></a>Grupos de custos

[!include[banner](../includes/banner.md)]


Os grupos de custos fornecem a base para a segmentação e análise de contribuições de custo no custo calculado de um item fabricado, como as contribuições de custo para materiais, trabalho e custos gerais indiretos. A segmentação de grupos de custo tem vários sinônimos dentro dos ambientes de fabricação, como divisão de custo, decomposição de custo ou classificação de custo. 

A segmentação de grupos de custo tem vários sinônimos dentro dos ambientes de fabricação, como divisão de custo, decomposição de custo ou classificação de custo. A segmentação de grupo de custos pode servir a vários propósitos. Eis alguns exemplos:

-   Ela pode segmentar custos para tipos de material diferentes, como ingredientes e material de embalagem para um produto enlatado, feitos com base nos grupos de custo atribuídos aos itens.
-   Ela pode segmentar custos para tipos de recursos de operações diferentes, como tipos de trabalho ou máquinas diferentes, feitos com base nos grupos de custo atribuídos às categorias de custo relacionadas aos recursos de operações e operações de roteiro.
-   Ela pode segmentar custos para a configuração e o tempo de execução em operações de roteiro, feitos com base nos grupos de custo atribuídos às categorias de custo relacionadas a operações de roteiro.
-   Ela pode segmentar custos para tipos de custos gerais indiretos diferentes, como custos gerais indiretos relacionados a trabalho e máquinas, feitos com base nos grupos de custo atribuídos aos custos indiretos na configuração da folha de custos.
-   Pode atuar como base para calcular vários tipos de custos gerais indiretos de fabricação na configuração da folha de custos. Isso custo geral indireto pode incluir diferentes tipos de custos gerais indiretos relacionados às informações de roteiro sobre os recursos de operações, ou informações sobre o tempo de configuração e o tempo de execução. Os custos gerais indiretos de fabricação também podem ser relacionados a contribuições de custo de material componente, refletindo uma filosofia de lean manufacturing que elimina a necessidade de informações de roteiro.

A segmentação de grupos de custo se aplica ao custo calculado de um item fabricado, independentemente de esse custo ser baseado nos custos padrão ou planejados. A página **Resumo** exibe esta segmentação por grupo de custos, por nível, ou por grupo de custos e por nível. 

A capacidade de reter segmentação de grupos de custo entre vários níveis em uma estrutura de produto é conhecida como *divisão*. A divisão se aplica somente a itens fabricados que usam um modelo de estoque de custo padrão. Se a divisão não for usada, o custo para de um componente fabricado é tratado como uma contribuição de custo de material. O parâmetro de estoque para divisão de custo por sub-razão indica que a segmentação de grupo de custo será retida entre vários níveis em cálculos de custo padrão. Por outro lado, se uma política não tiver níveis, a segmentação de grupos de custo é aplicada apenas a um cálculo de nível único. Por exemplo, a página **Acúmulo de custo por grupo de custo** exibe a segmentação de grupos de custo entre vários níveis para itens de custo padrão. 

A segmentação de grupos de custo também se aplica a variações para um item de custo padrão. Um segundo parâmetro de estoque define se as variações serão identificadas por um grupo de custos ou apenas resumidas. 

A um grupo de custo pode ser atribuído um tipo de grupo de custo e um comportamento para finalidade de segmentação complementar.

-   **Tipo de grupo de custos** − A cada grupo de custo deve ser atribuído um tipo de grupo de custo para indicar que o grupo de custos é aplicado a material direto, fabricação direta, terceirização direta ou para designá-lo como indireto ou indefinido. Um grupo de custo designado como material direto pode ser atribuído a itens. Um grupo de custo de fabricação direta pode ser atribuído a categorias de custo. Um grupo de custos de terceirização direta pode ser atribuído a um tipo de produto de serviço, de forma que você possa classificar os custos associados com a compra de serviço para atividades de subcontratação. Um grupo de custo indireto pode ser atribuído a custos indiretos para sobretaxas ou taxas. Um grupo de custo designado como indefinido pode ser atribuído para itens, categorias de custo ou custos indiretos. A atribuição de um tipo de grupo de custo serve para várias finalidades. Primeiro, ele restringe a capacidade de atribuir um grupo de custo e exibir uma lista suspensa de grupos de custos aplicáveis. Segundo, esta fornece segmentação completar para finalidade de relatório. Terceiro, esta pode ser usada para atribuir contas contábeis para variações.
-   **Comportamento** − Cada grupo de custos pode, opcionalmente, ser atribuído um comportamento para indicar se o grupo de custos é aplicado a custos fixos ou variáveis. Um grupo de custo com um valor nulo para comportamento é tratado como um custo variável. A atribuição de um comportamento serve somente para a finalidade de relatório. Por exemplo, os custos podem ser exibidos com segmentação de custos fixos e variáveis na folha de custos e na página**Acúmulo de custo por grupo de custo**. Se você atribuir uma porcentagem de definição de lucro para cada grupo de custo, o cálculo da lista de materiais (BOM) fornece um preço de venda sugerido com base em uma abordagem custo mais marcação.





