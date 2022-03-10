---
title: Função de ER POWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) POWER é usada.
author: NickSelin
ms.date: 12/17/2019
ms.prod: ''
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
ms.openlocfilehash: 6955d2787b2a9be6d38fe10165a9d5ef8310b108e3a9772709d9d1ff51712424
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6767135"
---
# <a name="power-er-function"></a>Função de ER POWER

[!include [banner](../includes/banner.md)]

A função `POWER` retorna um valor *Real* que representa o resultado da elevação do número positivo especificado à potência especificada.

## <a name="syntax"></a>Sintaxe

```vb
POWER (number, power)
```

## <a name="arguments"></a>Argumentos

`number`: *Real* ou *Inteiro*

Um valor numérico que deve ser elevado à potência especificada.

`power`: *Real* ou *Inteiro*

Um valor numérico que representa a potência específica.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="example-1"></a>Exemplo 1

`POWER (10, 2)` retorna **100**.

## <a name="example-2"></a>Exemplo 2

`POWER (4, 0.5)` retorna **2**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]