---
title: Tolerância de atraso (dias negativos)
description: Este tópico fornece informações sobre o cálculo de tolerância de atraso e como ele afeta a criação de ordens planejadas na Otimização de Planejamento.
author: ChristianRytt
ms.date: 07/30/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-30
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: cb03ccb208f19f540fefafd9964f74309736dc05
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577471"
---
# <a name="delay-tolerance-negative-days"></a>Tolerância de atraso (dias negativos)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

A funcionalidade de tolerância ao atraso permite que a Otimização de Planejamento considere o valor **Dias negativos** definido para grupos de cobertura. Ela é usada para estender o período de tolerância de atraso que é aplicado durante o planejamento mestre. Desta forma, você pode evitar a criação de novas ordens de suprimento se a oferta existente for capaz de cobrir a demanda após um curto atraso. O objetivo da funcionalidade é determinar se faz sentido criar uma nova ordem de suprimento para uma determinada demanda.

## <a name="turn-on-the-feature-in-your-system"></a>Ative o recurso no seu sistema

Para disponibilizar a funcionalidade de tolerância de atraso no sistema, acesse [Gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative o recurso *Dias negativos para Otimização de Planejamento*.

## <a name="delay-tolerance-in-planning-optimization"></a>Tolerância de atraso na Otimização de Planejamento

A tolerância de atraso representa o número de dias fora do prazo que você está disposto a esperar antes de encomendar um novo reabastecimento quando a oferta existente já está planejada. A tolerância de atraso é definida usando dias corridos, e não dias úteis.

No momento do planejamento mestre, quando o sistema calcula a tolerância de atraso, ele considera a configuração **Dias negativos**. Você pode definir o valor de **Dias negativos** nas páginas **Grupos de cobertura** ou **Cobertura de item**.

O sistema vincula o cálculo de tolerância de atraso à *data de reabastecimento mais antiga*, que equivale à data de hoje mais o tempo de início. A tolerância de atraso é calculada usando a seguinte fórmula, na qual *max()* encontra o maior de dois valores:

*max (Data de reabastecimento mais antiga, data de conclusão da demanda)* – *Data de conclusão da demanda* + *Dias negativos*

Esta fórmula garante que o planejamento mestre não crie novas ordens de suprimento quando existir suprimento suficiente durante o prazo do produto.

> [!NOTE]
> O cálculo de tolerância de atraso na Otimização de Planejamento sempre utiliza o cálculo dinâmico de dias negativos do planejamento mestre incorporado. A configuração **Usar dias negativos dinâmicos** na página **Parâmetros de planejamento Mestre não tem efeito** sobre esse comportamento.

Se a oferta existente implicar um atraso de demanda menor ou igual à tolerância de atraso calculada, a Otimização de Planejamento associará a oferta existente com a demanda. Em alguns casos, é melhor atrasar a demanda do que acabar com o excesso de oferta.

As seguintes subseções fornecem exemplos que mostram como a tolerância de atraso afeta a criação de ordens planejadas na Otimização de Planejamento.

### <a name="example-1"></a>Exemplo 1

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *2*

Existem a seguinte oferta e demanda para o produto:

- **Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10
- **Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente pode cobrir a demanda dentro de 12 dias, e esse período é igual à tolerância de atraso. Portanto, quando o planejamento mestre é executado, nenhuma ordem planejada é criada.

### <a name="example-2"></a>Exemplo 2

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *0*

Existem a seguinte oferta e demanda para o produto:

- **Demanda para hoje:** Uma ordem de vendas para uma quantidade de 10
- **Suprimento em 12 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente só pode cobrir a demanda após 12 dias. No entanto, a tolerância de atraso é de 10 dias. Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.

### <a name="example-3"></a>Exemplo 3

Um produto tem a seguinte configuração:

- **Prazo:** *10*
- **Dias negativos:** *2*

Existem a seguinte oferta e demanda para o produto:

- **Demanda em 11 dias:** Uma ordem de venda para uma quantidade de 10
- **Suprimento em 14 dias:** Uma ordem de compra para uma quantidade de 10

A oferta existente só pode cobrir a demanda após três dias. No entanto, a tolerância de atraso é de dois dias. (Neste caso, a tolerância de atraso inclui apenas os dois dias negativos. A data da demanda não está incluída porque ela é posterior ao prazo do produto.) Portanto, quando o planejamento mestre é executado, uma ordem planejada para uma quantidade de 10 é criada.
