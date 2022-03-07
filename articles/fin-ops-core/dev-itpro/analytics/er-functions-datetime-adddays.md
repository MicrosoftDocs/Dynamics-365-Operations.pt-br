---
title: Função ADDDAYS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ADDDAYS é usada.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3d90c19ddc64286843347976c000267e416bf05
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688434"
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
