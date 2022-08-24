---
title: Função de ER REPLACE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) REPLACE é usada.
author: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: e7a27b5015615d9b0f26e8fcddd812b3f51fb945
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278461"
---
# <a name="replace-er-function"></a>Função de ER REPLACE

[!include [banner](../includes/banner.md)]

A função `REPLACE` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres.

## <a name="syntax"></a>Sintaxe

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

`pattern`: *Cadeia de caracteres*

Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto que deve ser substituído.

Se o argumento `regular expression flag` for **TRUE**, este argumento conterá uma expressão regular que define um padrão de pesquisa e o texto substituto.

`replacement`: *Cadeia de caracteres*

Se o argumento `regular expression flag` for **FALSE**, este argumento conterá o texto a ser usado como substituto.

Se o argumento `regular expression flag` for **TRUE**, este argumento não será usado.

`regular expression flag`: *Booliano*

Um valor *Booliano* que indica se uma expressão regular é usada para fazer a substituição.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Se o argumento `regular expression flag` for **TRUE**, esta função retornará a cadeia de caracteres especificada depois de ter sido alterada, aplicando a expressão regular especificada pelo argumento `pattern`. A expressão regular é usada para encontrar os caracteres que devem ser substituídos.

Se o argumento `regular expression flag` for **FALSE**, essa função retorna a cadeia de caracteres especificada após o conjunto de caracteres que foram definidos no argumento `pattern` foram substituídos pelos caracteres do argumento `replacement`. 

## <a name="example-1"></a>Exemplo 1

`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica uma expressão regular que remove todos os símbolos não numéricos e retorna **"19234564971"**. 

## <a name="example-2"></a>Exemplo 2

`REPLACE ("abcdef", "cd", "GH", false)` substitui o padrão **"cd"** pela cadeia de caracteres **"GH"** e retorna **"abGHef"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
