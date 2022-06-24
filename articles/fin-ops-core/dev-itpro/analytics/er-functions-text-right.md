---
title: Função de ER RIGHT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) RIGHT é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 99e4d3811b1df25a7f6068e0dd31836d1b402952
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895356"
---
# <a name="right-er-function"></a>Função de ER RIGHT

[!include [banner](../includes/banner.md)]

A função `RIGHT` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do final da cadeia de caracteres especificada.

## <a name="syntax"></a>Sintaxe

```vb
RIGHT (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o texto original.

`number`: *Inteiro*

O número de caracteres que deve ser retornado a partir do final do texto original.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`RIGHT ("Sample", 3)` retorna **"ple"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]