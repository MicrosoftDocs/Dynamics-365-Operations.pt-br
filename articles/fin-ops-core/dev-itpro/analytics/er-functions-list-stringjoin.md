---
title: Função de ER STRINGJOIN
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) STRINGJOIN é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 08ed76f4dc61ed8afd63ffe99cead4866b63aba9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908493"
---
# <a name="stringjoin-er-function"></a>Função de ER STRINGJOIN

[!include [banner](../includes/banner.md)]

A função `STRINGJOIN` retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado da lista especificada. Os valores podem ser separados pelo delimitador especificado.

## <a name="syntax"></a>Sintaxe

```vb
STRINGJOIN (list, field, delimiter)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`field`: *Campo*

O caminho válido de um campo do tipo de dados *Cadeia de caracteres* na lista especificada.

`delimiter`: *Cadeia de caracteres*

Um delimitador usado para separar as subcadeias de caracteres.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

Se você inserir `SPLIT("abc" , 1)` como a fonte de dados **DS**, a expressão `STRINGJOIN (DS, DS.Value, "-")` retornará **"a-b-c"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]