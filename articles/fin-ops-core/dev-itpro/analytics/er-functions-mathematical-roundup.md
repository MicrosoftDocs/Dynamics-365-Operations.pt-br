---
title: Função de ER ROUNDUP
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) ROUNDUP é usada.
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
ms.openlocfilehash: ec4fdce6f072c5c3d87b139c8f64bd63a8a3eccd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8855635"
---
# <a name="roundup-er-function"></a>Função de ER ROUNDUP

[!include [banner](../includes/banner.md)]

A função `ROUNDUP` retorna o número especificado como um valor *Real* após ele ser arredondado para cima para o número especificado de casas decimais.

## <a name="syntax"></a>Sintaxe

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Um valor numérico que deve ser arredondado para cima.

`decimals`: *Inteiro*

Um valor numérico que representa o número de casas decimais.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para cima (longe do zero).

## <a name="example-1"></a>Exemplo 1

`ROUNDUP (1200.763, 2)` arredonda para cima para duas casas decimais e retorna **1200,77**.

## <a name="example-2"></a>Exemplo 2

`ROUNDUP (1200.767, -3)` arredonda para cima para o múltiplo mais próximo de 1.000 e retorna **2000**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]