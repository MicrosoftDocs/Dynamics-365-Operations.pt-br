---
title: Depreciação por fator
description: Este artigo oferece uma visão geral do método de depreciação por fator.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdb35f7b0efaf2f1a5f63eb0dbdf14363f63a389c5449b7fe145a46fd5c14cc2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746455"
---
# <a name="factor-depreciation"></a>Depreciação por fator

[!include [banner](../includes/banner.md)]

Este artigo oferece uma visão geral do método de depreciação por fator.

Fatores são as porcentagens usadas na depreciação de ativos. Quando você configura um perfil de depreciação de ativo fixo e seleciona **Fator** no campo **Método** na página **Perfis de depreciação**, é possível configurar depreciação progressiva, digressiva ou linear:

-   Na depreciação progressiva, o valor da depreciação aumenta a cada período de depreciação.
-   Na depreciação digressiva, o valor da depreciação por período diminui com o tempo.
-   Na depreciação linear, a depreciação é a mesma em todos os períodos.

As regras e os exemplos a seguir indicam como é possível definir fatores para cada tipo de depreciação. 

> [!NOTE] 
> Quando você seleciona **Fator** no campo **Método**, os campos **Fator** e **Intervalo** são exibidos.

## <a name="progressive-depreciation"></a>Depreciação progressiva
O valor no campo **Fator** é maior que **50**.

### <a name="example"></a>Exemplo

O preço de aquisição é 100.000, o fator é 70, a vida útil é 10 anos e a depreciação começa em 1º de janeiro. Os valores de depreciação e os valores líquidos contábeis são mostrados apenas durante os seis primeiros anos de vida útil.

| Ano | Período      | Valor de depreciação | Valor líquido contábil |
|------|-------------|---------------------|-----------------------|
| 1    | 31 de dezembro | 307,69              | 99.692,31             |
| 2    | 31 de dezembro | 1.447,21            | 98.245,10             |
| 3    | 31 de dezembro | 3.104,50            | 95.140,60             |
| 4    | 31 de dezembro | 5.150,21            | 89.990,39             |
| 5    | 31 de dezembro | 7.522,95            | 82.467,44             |
| 6    | 31 de dezembro | 10.184,06           | 72.283,38             |

## <a name="digressive-depreciation"></a>Depreciação digressiva
O valor do campo **Fator** é menor do que **50**.

### <a name="example"></a>Exemplo

O preço de aquisição é 100.000, o fator é 20, a vida útil é 10 anos e a depreciação começa em 1º de janeiro. Os valores de depreciação e os valores líquidos contábeis são mostrados apenas durante os seis primeiros anos de vida útil.

| Ano | Período      | Valor de depreciação | Valor líquido contábil |
|------|-------------|---------------------|-----------------------|
| 1    | 31 de dezembro | 56.080,43           | 43.919,57             |
| 2    | 31 de dezembro | 10.665,70           | 33.253,87             |
| 3    | 31 de dezembro | 7.156,22            | 26.097,65             |
| 4    | 31 de dezembro | 5.538,06            | 20.559,59             |
| 5    | 31 de dezembro | 4.579,89            | 15.979,70             |
| 6    | 31 de dezembro | 3.937,36            | 12.042,34             |

## <a name="straight-line-depreciation"></a>Depreciação linear
O valor no campo **Fator** é igual a **50**. Nesse caso, a depreciação é a mesma em todos os períodos, e devem ser consideradas as implicações de valores que você especificou em outros campos, conforme descrito em [Depreciação linear com base na vida útil](straight-line-service-life-depreciation.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]