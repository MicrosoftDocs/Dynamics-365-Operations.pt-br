---
title: Planejamento com quantidades disponíveis negativas
description: Este tópico explica como a quantidade negativa disponível é tratada quando você usa a otimização do planejamento.
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 97688e09aae9706dd85e7965aa08c7ea873a44d81391c39406e2e6367660e0d0
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758535"
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

Se você ajustar o estoque enquanto houver reservas físicas, poderá causar uma situação em que uma ordem está fisicamente reservada contra estoque negativo. Nesse caso, como existe uma reserva física, a Otimização do Planejamento supõe que haja suporte para o estoque disponível, mesmo que o recebimento do estoque disponível ainda não esteja registrado no sistema. Portanto, ele supõe que o reabastecimento não é necessário e não cria uma ordem planejada para reabastecer a quantidade da ordem.

O exemplo a seguir ilustra esse cenário.

### <a name="example"></a>Exemplo

O sistema está configurado da seguinte maneira:

- O produto *FG* existe e tem *10* unidades. de estoque disponível.
- A configuração do produto permite o estoque físico negativo.
- Existe uma ordem de venda para uma quantidade de *10* unidades. do produto *FG*.
- A quantidade da ordem de venda é fisicamente reservada em relação ao estoque disponível existente.

Em seguida, você ajuste a quantidade do produto *FG* para que o estoque disponível se torne 0 (zero). Como o estoque disponível do produto é zero, a quantidade da ordem de venda agora está reservada para o estoque negativo. No entanto, se você executar o planejamento mestre agora, nenhuma ordem planejada será criada para fornecer a ordem de venda, pois a Otimização do Planejamento deduzirá que o estoque disponível necessário existe para fornecer a reserva física.

## <a name="related-resources"></a>Recursos relacionados

- [Visão geral da Otimização do Planejamento](planning-optimization-overview.md)
- [Introdução à Otimização do Planejamento](get-started.md)
- [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md)
- [Exibir logs de histórico de plano e de planejamento](plan-history-logs.md)
- [Cancelar um trabalho de planejamento](cancel-planning-job.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
