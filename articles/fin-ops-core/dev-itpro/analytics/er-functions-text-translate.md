---
title: Função de ER TRANSLATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRANSLATE é usada.
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: 415444bda097c00522155d1b37988a79da836902
ms.sourcegitcommit: fb8ad8e2b142441a6530b364f3258bbcc0c724d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3201103"
---
# <a name=""></a><a name="TRANSLATE">Função de ER TRANSLATE</a>

[!include [banner](../includes/banner.md)]

A função `TRANSLATE` retorna um valor *Cadeia de caracteres* que contém o resultado da substituição de caractere do texto especificado em caracteres para outro conjunto fornecido.

## <a name="syntax"></a>Sintaxe

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

`pattern`: *Cadeia de caracteres*

O texto que deve ser substituído.

`replacement`: *Cadeia de caracteres*

O texto a ser usado como substituto.

## <a name="return-values"></a>Valores de retorno

*Sequência de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

A função `TRANSLATE` substitui um caractere por vez. A função substitui o primeiro caractere do argumento `text` pelo primeiro caractere do argumento `pattern` e, em seguida, o segundo caractere e segue o mesmo fluxo até concluir. Quando um caractere dos argumentos `text` e `pattern` é correspondente, ele é substituído por um caractere do argumento `replacement` localizado na mesma posição que o caractere do argumento `pattern`. Se um caractere aparecer várias vezes no argumento `pattern`, será usado o mapeamento de argumento `replacement` que corresponde à primeira ocorrência deste caractere.

## <a name="example-1"></a>Exemplo 1

`TRANSLATE ("abcdef", "cd", "GH")` substitui o caractere **"c"** do texto **“abcdef”** especificado com o caractere **"G"** do texto `replacement` devido ao seguinte:
-   O caractere **"c"** é apresentado no texto `pattern` da primeira posição.
-   A primeira posição do texto `replacement` contém o caractere **"G"**.

## <a name="example-2"></a>Exemplo 2

`TRANSLATE ("abcdef", "ccd", "GH")` retorna **"abGdef"**.

## <a name="example-3"></a>Exemplo 3

`TRANSLATE ("abccba", "abc", "123")` retorna **"123321"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)
