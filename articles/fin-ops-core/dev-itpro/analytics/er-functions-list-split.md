---
title: Função de ER SPLIT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLIT é usada.
author: NickSelin
ms.date: 12/12/2019
ms.topic: article
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
ms.openlocfilehash: 5c99ee5e8129ed45253893dc83acdef99b4ce2c9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745584"
---
# <a name="split-er-function"></a>Função de ER SPLIT

[!include [banner](../includes/banner.md)]

A função `SPLIT` divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.

## <a name="syntax-1"></a>Sintaxe 1

```vb
SPLIT (input, length)
```

Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, cada uma com o tamanho especificado.

## <a name="syntax-2"></a>Sintaxe 2

```vb
SPLIT (input, delimiter)
```

Esta sintaxe é usada para dividir a cadeia de caracteres de entrada especificada em subcadeias de caracteres, com base no delimitador especificado.

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O texto a ser dividido.

`length`: *Inteiro*

O tamanho máximo de uma única subcadeia de caracteres.

`delimiter`: *Cadeia de caracteres*

Um delimitador usado para separar as subcadeias de caracteres.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A estrutura de registro da lista retornada consiste no campo **Valor** do tipo *Cadeia de caracteres*. Todos os registros da lista retornada contêm subcadeias de caracteres geradas nesse campo.

Se o argumento `delimiter` estiver vazio, a nova lista retornada consistirá em um registro com o campo **Valor** do tipo *Cadeia de caracteres*. Esse campo contém o texto de entrada.

Se o argumento `input` estiver vazio, uma nova lista vazia será retornada. Se o argumento `input` ou `delimiter` não estiver especificado (nulo), uma exceção de aplicativo será gerada.

## <a name="example-1"></a>Exemplo 1

`SPLIT ("abcd", 3)` retorna uma nova lista que consiste em dois registros com o campo **Valor** do tipo *Cadeia de caracteres*. O campo **Valor** no primeiro registro contém o texto **"abc"** e o campo **Valor** no segundo registro contém o texto **“d”**.

## <a name="example-2"></a>Exemplo 2

`SPLIT ("XAb aBy", "aB")` retorna uma nova lista que consiste em três registros com o campo **Valor** do tipo *Cadeia de caracteres*. O campo **Valor** no primeiro registro contém o texto **"X"**, o campo **Valor** no segundo registro contém o texto **"&nbsp;"** e o campo **Valor** no terceiro registro contém o texto **"y"**. 

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]