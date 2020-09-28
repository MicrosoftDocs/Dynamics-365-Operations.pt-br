---
title: Função de ER INTVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INTVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743630"
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
