---
title: Função de ER INTVALUE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) INTVALUE é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: e2357541f922ad9af5c5ce342d0e7d89e8709734
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879881"
---
# <a name="intvalue-er-function"></a>Função de ER INTVALUE

[!include [banner](../includes/banner.md)]

A função `INTVALUE` retorna um valor *Int* que representa a cadeia de caracteres especificada.

## <a name="syntax-1"></a>Sintaxe 1

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
INTVALUE (number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de texto que deve ser convertido para um número *Int*.

`number`: *Real* ou *Inteiro*

Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int*.

## <a name="return-values"></a>Valores de retorno

*Int*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Todas as casas decimais são truncadas.

## <a name="example-1"></a>Exemplo 1

`INTVALUE ("100.77")` retorna o valor *Int* **100**.

## <a name="example-2"></a>Exemplo 2

`INTVALUE (-100.77)` retorna o valor *Int* **-100**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de conversão de tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]