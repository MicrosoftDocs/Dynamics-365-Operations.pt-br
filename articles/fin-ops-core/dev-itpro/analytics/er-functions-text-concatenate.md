---
title: Função de ER CONCATENATE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) CONCATENATE é usada
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
ms.openlocfilehash: 926c3acf92fc8017c3c4a7814855a6871c1cacc4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8863254"
---
# <a name="concatenate-er-function"></a>Função de ER CONCATENATE

[!include [banner](../includes/banner.md)]

A função `CONCATENATE` retorna todas as cadeias de caracteres de texto especificadas como um valor de *Cadeia de caracteres* depois que elas são unidas em uma cadeias de caracteres.

## <a name="syntax"></a>Sintaxe

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumentos

`text 1`: *Cadeia de caracteres*

Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*. Esse argumento é obrigatório.

`text N`: *Cadeia de caracteres*

Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CONCATENATE ("abc", "def")` retorna **"abcdef"**.

## <a name="usage-notes"></a>Notas de uso

A expressão `"abc" & "def"` também retorna **"abcdef"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]