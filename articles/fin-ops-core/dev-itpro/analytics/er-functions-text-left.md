---
title: Função de ER LEFT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LEFT é usada.
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: 5d0056dbe46b20432aacb35a971895b987fdbf1b8ebc0d2679bb1e52eb3c4cc2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762467"
---
# <a name="left-er-function"></a>Função de ER LEFT

[!include [banner](../includes/banner.md)]

A função `LEFT` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do início da cadeia de caracteres especificada.

## <a name="syntax"></a>Sintaxe

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o texto original.

`number`: *Inteiro*

O número de caracteres que deve ser retornado a partir do início do texto original.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`LEFT ("Sample", 3)` retorna **"Sam"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]