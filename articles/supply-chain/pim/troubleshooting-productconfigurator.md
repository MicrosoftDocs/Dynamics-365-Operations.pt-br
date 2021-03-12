---
title: Solucionar problemas do configurador de produto
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com configurador de produto.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: e6cfeb6a2b4166dfa9a5a5cc1b7d3d913b865ce2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4999597"
---
# <a name="troubleshoot-the-product-configurator"></a>Solucionar problemas do configurador de produto

Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com o configurador de produto.

## <a name="item-text-is-overwritten-when-i-configure-a-product-on-a-sales-order-line"></a>O texto do item é substituído quando eu configuro um produto em uma linha de ordem de venda.

### <a name="issue-description"></a>Descrição do problema

Esse problema ocorre quando você cria uma linha de ordem de venda para um item configurável e, em seguida, modifica o texto do item. Ao configurar o item e selecionar **OK**, o texto é substituído pelo texto padrão.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é esperado. O campo de texto inclui o nome da variante, que é preenchido somente após a configuração da linha. Portanto, você deve alterar o texto depois de configurar a linha, não antes.

## <a name="integer-attributes-are-incorrectly-rounded-when-product-configuration-models-are-calculated"></a>Atributos Inteiro são arredondados incorretamente quando os modelos de configuração do produto são calculados.

### <a name="issue-description"></a>Descrição do problema

Esse problema pode ocorrer quando você executa a seguinte série de ações:

1. Defina os seguintes atributos em um modelo de configuração de produção:

    - Entrada (inteiro)
    - Porcentagem (decimal)
    - Resultado (inteiro)

2. Crie um cálculo que tenha a seguinte expressão:

    *Resultado* = *Entrada* × *Porcentagem* ÷ 100

Nesse caso, o resultado inteiro nem sempre é arredondado corretamente. Por exemplo, a entrada é 1.000 e a porcentagem é 2,40. Portanto, você espera que o resultado inteiro seja 24, porque 2,40% de 1.000 é 24 (ou 24,00 na forma decimal). Em vez disso, o resultado é mostrado como 23. Contudo, quando a porcentagem é 2,39, o cálculo é arredondado para 24 em vez de 23. Quando a porcentagem é 2,50, o cálculo é arredondado para 25, conforme o esperado.

### <a name="issue-resolution"></a>Resolução do problema

Esse problema se deve à maneira como o Microsoft Solver Foundation representa internamente os números usando frações. No exemplo anterior, o resultado do cálculo em que a porcentagem é 2,40 é representado como 27021597764222975 ÷ 1125899906842624 = 23,99999999999999911182158029987476766109466552734375. Quando o .NET converte esse valor como um inteiro, ele retorna 23.

Esse comportamento não será alterado, pois outros cenários dependem dele. No exemplo anterior, você pode corrigir o problema introduzindo um atributo decimal adicional e um cálculo.

Por exemplo, você pode definir os seguintes atributos em um modelo de configuração de produção:

- Entrada (inteiro)
- Porcentagem (decimal)
- ResultDecimal (decimal)
- ResultInteger (inteiro)

Você pode então adicionar os seguintes cálculos:

- *ResultDecimal* = *Entrada* × *Porcentagem* ÷ 100
- *ResultInteger* = *ResultDecimal*
