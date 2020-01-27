---
title: Função de ER STRINGJOIN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) STRINGJOIN é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 99d50313f8097d43b820ffc1c36eef0097e7ec55
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917180"
---
# <a name="STRINGJOIN">Função de ER STRINGJOIN</a>

[!include [banner](../includes/banner.md)]

A função `STRINGJOIN` retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado da lista especificada. Os valores podem ser separados pelo delimitador especificado.

## <a name="syntax"></a>Sintaxe

```
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
