---
title: Função de ER INT64VALUE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) INT64VALUE é usada.
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
ms.openlocfilehash: 37fae9cdc5a833009b0ca1cbeb851e5e6e1b6608
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892154"
---
# <a name="int64value-er-function"></a>Função de ER INT64VALUE

[!include [banner](../includes/banner.md)]

A função `INT64VALUE` retorna um valor *Int64* que representa a cadeia de caracteres especificada.

## <a name="syntax-1"></a>Sintaxe 1

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
INT64VALUE (number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de texto que deve ser convertido para um número *Int64*.

`number`: *Real* ou *Inteiro*

Um valor *Real* ou *Inteiro* numérico que deve ser convertido a um número *Int64*.

## <a name="return-values"></a>Valores de retorno

*Int64*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Todas as casas decimais são truncadas.

## <a name="example-1"></a>Exemplo 1

`INT64VALUE ("22565422744")` retorna o valor *Int64* **22565422744**.

## <a name="example-2"></a>Exemplo 2

`INT64VALUE ( VALUE("22565422744.77"))` retorna o valor *Int64* **22565422744**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de conversão de tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]