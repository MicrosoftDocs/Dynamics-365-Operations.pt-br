---
title: Inteiros arredondados incorretamente em cálculos de modelo de configuração do produto
description: Os resultados inteiros nem sempre são arredondados corretamente quando os modelos de configuração do produto são calculados. Corrija o problema com um atributo decimal adicional e um cálculo.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: b17145d7d17cb784fe11b3fbf65ddf5aa5530f27
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475599"
---
# <a name="integers-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Inteiros arredondados incorretamente quando os modelos de configuração do produto são calculados

## <a name="symptoms"></a>Sintomas

Esse problema pode ocorrer quando você executa a seguinte série de ações:

1. Defina estes atributos em um modelo de configuração de produção:

    - Entrada (inteiro)
    - Porcentagem (decimal)
    - Resultado (inteiro)

2. Crie um cálculo que tenha a seguinte expressão:

    *Resultado* = *Entrada* × *Porcentagem* ÷ 100

Nesse caso, o resultado inteiro nem sempre é arredondado corretamente. Por exemplo, se a entrada for 1.000 e a porcentagem for 2,40, você espera que o resultado inteiro seja 24 porque 2,40% de 1.000 é 24 (ou 24,00 no formato decimal). Em vez disso, o resultado é mostrado como 23. Contudo, quando a porcentagem é 2,39, o cálculo é arredondado para 24 em vez de 23. Quando a porcentagem é 2,50, o cálculo é arredondado para 25, conforme o esperado.

## <a name="cause"></a>Causa

Esse problema se deve à maneira como o Microsoft Solver Foundation representa internamente os números usando frações. No exemplo anterior, o resultado do cálculo em que a porcentagem é 2,40 é representado como 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Quando o .NET converte esse valor como um inteiro, ele retorna 23.

## <a name="resolution"></a>Resolução

Esse comportamento não será alterado pois outros cenários dependem dele. No exemplo anterior, você pode corrigir o problema introduzindo um atributo decimal adicional e cálculos.

Por exemplo, defina os seguintes atributos em um modelo de configuração de produção:

- Entrada (inteiro)
- Porcentagem (decimal)
- ResultDecimal (decimal)
- ResultInteger (inteiro)

Você pode então adicionar os seguintes cálculos:

- *ResultDecimal* = *Entrada* × *Porcentagem* ÷ 100
- *ResultInteger* = *ResultDecimal*
