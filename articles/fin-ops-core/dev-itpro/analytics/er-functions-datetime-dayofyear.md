---
title: Função DAYOFYEAR ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DAYOFYEAR é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: b9b937e7fae3e90d1a87196fab653dfac8e94179
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682380"
---
# <a name="dayofyear-er-function"></a>Função DAYOFYEAR ER

[!include [banner](../includes/banner.md)]

A função `DAYOFYEAR` retorna um valor *Inteiro* que representa o número de dias entre 1 de janeiro e a data especificada.

## <a name="syntax"></a>Sintaxe

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a>Argumentos

`date`: *Data*

Um valor de data que representa a data para usar o cálculo do número de dias.

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="example-1"></a>Exemplo 1

`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` retorna **61**.

## <a name="example-2"></a>Exemplo 2

`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` retorna **1**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]