---
title: Planejamento com quantidades disponíveis negativas
description: Este artigo explica como a quantidade negativa disponível é tratada quando você usa a otimização do planejamento.
author: t-benebo
ms.date: 07/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 04006bb12142be69c84bc8085dd82fc99280e90b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856125"
---
# <a name="planning-with-negative-on-hand-quantities"></a>Planejamento com quantidades disponíveis negativas

[!include [banner](../../includes/banner.md)]

Se o sistema mostrar uma quantidade disponível agregada negativa, o mecanismo de planejamento tratará a quantidade como 0 (zero) para ajudar a evitar o excesso de suprimento. Veja como essa funcionalidade funciona:

1. O recurso de otimização de planejamento agrega quantidades disponíveis no menor nível de dimensões de cobertura. (Por exemplo, se o *local* não é uma dimensão de cobertura, a otimização do planejamento agrega quantidades disponíveis no nível do *depósito*.)
1. Se a quantidade disponível agregada no nível mais baixo das dimensões de cobertura for negativa, o sistema assume que a quantidade disponível é realmente 0 (zero).

> [!IMPORTANT]
> O sistema de planejamento pode ser tão preciso quanto os dados de entrada. Se os dados de entrada forem imprecisos, os registros disponíveis negativos indicarão que as informações de estoque no Microsoft Dynamics 365 Supply Chain Management estão fora de sincronia com o mundo real. Portanto, o resultado do planejamento apresentará falha. Para obter um resultado de planejamento preciso, é preciso minimizar o número de registros que mostram uma quantidade disponível negativa.

## <a name="example-1"></a>Exemplo 1

O depósito 13 é configurado da seguinte maneira:

- **Código de cobertura:** mín./máx.
- **Mínimo:** 15 peças (pcs.)
- **Máximo:** 25 pcs.

O nível mais baixo das dimensões de cobertura é *depósito* e as seguintes quantidades disponíveis são registradas no nível do *local*:

- **Site 1, depósito 13, local 1:** 20 pcs.
- **Site 1, depósito 13, local 2:** &minus;8 pcs.

Portanto, a quantidade disponível agregada para o depósito 13 é de 12 peças. (= 20 pcs. &minus; 8 pcs.).

Nesse caso, o mecanismo de planejamento usa uma quantidade agregada disponível de 12 peças. para depósito 13.

O resultado é uma ordem planejada de 13 peças. (= 25 pcs. &minus; 12 pcs.) para reabastecer o depósito 13 de 12 peças. a 25 pcs.

## <a name="example-2"></a>Exemplo 2

O depósito 13 é configurado da seguinte maneira:

- **Código de cobertura:** mín./máx.
- **Mínimo:** 15 pcs.
- **Máximo:** 25 pcs.

O nível mais baixo das dimensões de cobertura é *depósito* e as seguintes quantidades disponíveis são registradas no nível do *local*:

- **Site 1, depósito 13, local 1:** 4 pcs.
- **Site 1, depósito 13, local 2:** &minus;8 pcs.

Portanto, a quantidade disponível agregada para o depósito 13 é de &minus;4 peças. (= 4 pcs. &minus; 8 pcs.). Em outras palavras, é menor que 0 (zero).

Nesse caso, o mecanismo de planejamento assume que a quantidade disponível para o depósito 13 é 0 unidades. em vez de &minus;4 pcs.

O resultado é uma ordem planejada de 25 peças. (= 25 pcs. &minus; 0 pcs.) para reabastecer o depósito 13 de 0 peças. a 25 pcs.

## <a name="planning-when-there-is-a-reservation-against-negative-on-hand-inventory"></a>Planejar quando haverá uma reserva em relação ao estoque disponível negativo

Se você ajustar o estoque enquanto houver reservas físicas, poderá causar uma situação em que uma ordem está fisicamente reservada contra estoque negativo. Nesse caso, como existe uma reserva física, você precisará ter o fornecimento para cobrir a quantidade reservada. Portanto, o reabastecimento é necessário e o sistema criará uma ordem planejada para reabastecer a quantidade que não foi coberta pelo estoque disponível existente ou cobri-la com uma ordem existente para o item.

O exemplo a seguir ilustra esse cenário.

### <a name="example"></a>Exemplo

O sistema está configurado da seguinte maneira:

- O produto *FG* existe e tem *10* unidades. de estoque disponível.
- A configuração do produto permite o estoque físico negativo.
- Existe uma ordem de venda para uma quantidade de *10* unidades. do produto *FG*.
- A quantidade da ordem de venda é fisicamente reservada em relação ao estoque disponível existente.

Em seguida, ajuste a quantidade do produto *FG* para que o estoque disponível seja 5. Como o estoque disponível do produto é 5, a quantidade da ordem de venda agora está reservada em relação à quantidade indisponível (isso seria semelhante se a quantidade disponível fosse 0, caso em que a ordem de venda seria reservada no estoque negativo). Se você executar o planejamento mestre agora, uma ordem planejada de quantidade 5 para *FG* será criada para fornecer a ordem de venda, pois a Otimização do Planejamento sempre usará o fornecimento existente ou criará uma nova ordem planejada para disponibilizar a reserva física.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Otimização do Planejamento](planning-optimization-overview.md)
- [Introdução à Otimização do Planejamento](get-started.md)
- [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)
- [Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)
- [Cancelar um trabalho de planejamento](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
