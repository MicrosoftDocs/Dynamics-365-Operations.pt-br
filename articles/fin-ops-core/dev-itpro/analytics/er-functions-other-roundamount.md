---
title: Função de ER ROUNDAMOUNT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDAMOUNT é usada.
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
ms.openlocfilehash: 1b05c6024d9eeecfe74022df10d793055a026d5a159e9c011f37708f6a4e6e0d
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770852"
---
# <a name="roundamount-er-function"></a>Função de ER ROUNDAMOUNT

[!include [banner](../includes/banner.md)]

A função `ROUNDAMOUNT` retorna um valor *Real* como resultado do arredondamento do número especificado para o múltiplo mais próximo de outro número de acordo com a regra de arredondamento especificada.

## <a name="syntax"></a>Sintaxe

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a>Argumentos

`number`: *Int* ou *Real*

Um valor numérico que deve ser arredondado.

`decimals`: *Int* ou *Real*

O valor do parâmetro `number` deve ser arredondado para um múltiplo desse número.

`round rule`: *Valor de enumeração*

Um valor de enumeração da enumeração **RoundOffType** que define a regra de arredondamento. Essa enumeração oferece os seguintes valores:

- Normal (Ordinary)
- Para baixo (RoundDown)
- Para cima (RoundUp)

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante é um múltiplo do valor especificado pelo parâmetro `decimals` e está mais próximo do valor especificado pelo parâmetro `number`.

## <a name="usage-notes"></a>Notas de uso

Quando o parâmetro `number` é zero, esta função sempre retorna zero.

Quando o parâmetro `decimals` é zero, esta função arredonda para o valor de arredondamento padrão. Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, o valor de arredondamento padrão é **0,01**. Caso contrário, o valor de arredondamento padrão é **1,0**.

Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, esta função arredonda para o valor de arredondamento mais próximo.

Quando o parâmetro `round rule` está definido como **RoundOffType.RoundDown**, esta função arredonda em direção ao zero para o valor de arredondamento mais próximo.

Quando o parâmetro `round rule` está definido como **RoundOffType.RoundUp**, esta função arredonda se afastando do zero para o valor de arredondamento mais próximo.

Quando o parâmetro `round rule` está definido como **RoundOffType.Ordinary**, esta função se comporta como a função [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) do Excel e a função [ROUND](../dev-ref/xpp-math-run-time-functions.md#round) do X++.

## <a name="remarks"></a>Comentários

Para arredondar um valor numérico para um número especificado de casas decimais, use a função [ROUND](er-functions-mathematical-round.md).

## <a name="example"></a>Exemplo

Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 7,35. 

Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 7,35. 

Se o parâmetro **model.RoundOff** estiver definido como **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` retorna 8,4.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)

[Funções matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]