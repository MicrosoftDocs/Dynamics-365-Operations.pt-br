---
title: Função de ER ROUND
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) ROUND é usada.
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: 5dce96077ab25f8e545bb99d4bed8fc5bba61e2a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905189"
---
# <a name="round-er-function"></a>Função de ER ROUND

[!include [banner](../includes/banner.md)]

A função `ROUND` retorna o número especificado como um valor *Real* após ele ser arredondado para o número especificado de casas decimais.

## <a name="syntax"></a>Sintaxe

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Um valor numérico que deve ser arredondado.

`decimals`: *Inteiro*

Um valor numérico que representa o número de casas decimais.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Se o valor do argumento `decimals` for maior do que 0 (zero), o número especificado é arredondado para essa quantidade de casas decimais.

Se o valor do argumento `decimals` for **0** (zero), o número especificado é arredondado para o inteiro par mais próximo.

Se o valor do argumento `decimals` for menor do que 0 (zero), o número especificado é arredondado para a esquerda do separador decimal.

## <a name="example-1"></a>Exemplo 1

`ROUND (1200.767, 2)` arredonda para duas casas decimais e retorna **1200,77**.

## <a name="example-2"></a>Exemplo 2

`ROUND (1200.767, -3)` arredonda para o múltiplo mais próximo de 1.000 e retorna **1000**.

## <a name="example-3"></a>Exemplo 3

`ROUND (1200.5, 0)` arredonda para o inteiro par mais próximo e retorna **1200**, enquanto `ROUND (1201.5, 0)` faz o mesmo e retorna **1202**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]