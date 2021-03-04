---
title: Opções de cálculo de intervalo e valor total para códigos de imposto
description: Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3e18eac934eb109e8f3f509b2bd78f76dd5f74d
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4440354"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a>Opções de cálculo de intervalo e valor total para códigos de imposto

[!include [banner](../includes/banner.md)]

Este artigo explica as opções para o campo Método de cálculo em códigos de imposto e como o imposto é calculado para intervalos e valores inteiros.

Você pode configurar um código de imposto a ser calculado com base em um valor inteiro ou em um intervalo de valores. Na página Códigos de imposto, use o campo Método de cálculo na Guia Rápida Cálculo para selecionar como calcular um código de imposto.
- Valor total - a taxa de imposto é aplicada ao valor tributável total.
- Intervalo - o valor tributável é dividido em partes, cada uma dentro de um intervalo que tem uma taxa de imposto sobre vendas específica. A parte do valor inserida em um determinado intervalo é taxada de acordo com a taxa de imposto do intervalo. O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.
  > [!NOTE]                                                                                                                              
  > A opção Intervalo está disponível somente quando você seleciona Linha no campo Método de cálculo na área Impostos da página Parâmetros da contabilidade. 

Os intervalos são configurados na página Valores de código de imposto inserindo valores de limite Mínimo e Máximo por taxa de impostos. Para que os impostos possam ser calculados em todos os valores tributáveis, independente do método de cálculo selecionado, os intervalos devem seguir as seguintes regras:
-   O primeiro intervalo deve ter um limite Mínimo de zero.
-   O último intervalo deve ter um limite Máximo de zero, que indica infinito.
-   O limite Máximo de um intervalo deve ser o limite Mínimo do próximo intervalo.

Se um valor for o limite Máximo de um intervalo anterior e o limite Mínimo do próximo intervalo, a taxa de imposto do primeiro intervalo será aplicada ao valor. Se um valor estiver fora dos intervalos definidos pelos limites superior e inferior, uma taxa de imposto igual a 0 será aplicada.

## <a name="example-whole-amount-method-of-calculation"></a>Exemplo: método de cálculo de valor total
Na página Valores do código de imposto, as taxas de imposto são configuradas nos intervalos a seguir:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Limite mínimo** | **Limite máximo** | **Taxa de imposto** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

O imposto é calculado sobre o valor tributável total.

| Valor tributável (preço) | Cálculo    | Imposto |
|------------------------|----------------|-----------|
| 35,00                  | 35,00 \* 0,30  | R$ 10,50     |
| 50,00                  | 50,00 \* 0,30  | 15,00     |
| 85,00                  | 85,00 \* 0,20  | 17,00     |
| 305,00                 | 305,00 \* 0,10 | 30,50     |

## <a name="example-interval-method-of-calculation"></a>Exemplo: método de cálculo de intervalo
Na página Valores, as taxas de imposto são configuradas nos intervalos a seguir:

|                   |                   |              |
|-------------------|-------------------|--------------|
| **Limite mínimo** | **Limite máximo** | **Taxa de imposto** |
| 0,00              | 50,00             | 30%          |
| 50,00             | 100,00            | 20%          |
| 100,00            | 0,00              | 10%          |

O imposto sobre vendas é a soma dos valores de imposto calculados para cada intervalo de valor.

| Valor tributável (preço) | Cálculo                                                               | Imposto |
|------------------------|---------------------------------------------------------------------------|-----------|
| 35,00                  | 35,00 \* 0,30                                                             | R$ 10,50     |
| 50,00                  | 50,00 \* 0,30                                                             | 15,00     |
| 85,00                  | (50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)                          | 22,00     |
| 305,00                 | (50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50) | 45.50     |



Para obter mais informações, consulte [Taxas de imposto baseadas nos métodos Base marginal e Cálculo](marginal-base-field.md)







[!INCLUDE[footer-include](../../includes/footer-banner.md)]