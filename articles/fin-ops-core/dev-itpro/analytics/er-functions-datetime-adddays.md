---
title: Função ADDDAYS ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) ADDDAYS é usada.
author: kfend
ms.date: 12/03/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 69273794def0dc52dc8e31615c319ccf5067fa77
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274129"
---
# <a name="adddays-er-function"></a>Função ADDDAYS ER

[!include [banner](../includes/banner.md)]

A função `ADDDAYS` calcula um valor *DateTime* que é o número especificado de dias antes ou depois de uma data inicial especificada.

## <a name="syntax"></a>Sintaxe

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a>Argumentos

`datetime`: *DateTime*

Um valor de data/hora que representa a data inicial.

`days`: *Inteiro*

O número de dias antes ou depois de `datetime`.

## <a name="return-values"></a>Valores de retorno

*Data/Hora*

O valor de data/hora resultante.

## <a name="usage-notes"></a>Notas de uso

Um valor positivo para `days` gera uma data futura. Um valor negativo gera uma data passada.

## <a name="example-1"></a>Exemplo 1

`ADDDAYS (NOW(), 7)` retorna a data e a hora de sete dias no futuro.

## <a name="example-2"></a>Exemplo 2

`ADDDAYS (NOW(), -3)` retorna a data e a hora de três dias no passado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
