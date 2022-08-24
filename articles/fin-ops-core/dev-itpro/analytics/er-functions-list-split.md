---
title: Função de ER SPLIT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) SPLIT é usada.
author: kfend
ms.date: 04/01/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e95ecaae46ee73899736b1d5729d7f9639fc6803
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273985"
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

## <a name="example-3"></a>Exemplo 3

Você pode usar a função [INDEX](er-functions-list-index.md) para acessar elementos individuais da cadeia de caracteres de entrada especificada. Se você inserir a fonte de dados **MyList** do tipo **Campo calculado** e configurar a expressão `SPLIT("abc", 1)` para ela, a expressão `INDEX(MyList,2).Value` retornará o valor de texto **"b"**.

## <a name="example-4"></a>Exemplo 4

A função [ENUMERATE](er-functions-list-enumerate.md) também ajuda a acessar elementos individuais da cadeia de caracteres de entrada especificada. Se você inserir primeiro a fonte de dados **MyList** do tipo **Campo calculado** e configurá-la para a expressão `SPLIT("abc", 1)` e, em seguida, inserir a fonte de dados **EnumeratedList** do tipo **Campo calculado** e configurar a expressão `ENUMERATE(MyList)` para ela, a expressão `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` retornará o texto **"b"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
