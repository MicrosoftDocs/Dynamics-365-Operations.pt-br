---
title: Função de ER NUMERALSTOTEXT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) NUMERALSTOTEXT é usada.
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 172693583699edfad7deeb16f8fc081abb6119d5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287978"
---
# <a name="numeralstotext-er-function"></a>Função de ER NUMERALSTOTEXT

[!include [banner](../includes/banner.md)]

A função `NUMERALSTOTEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser soletrado (ou seja, convertido em cadeias de caracteres de texto) no idioma especificado.

## <a name="syntax"></a>Sintaxe

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a>Argumentos

`number`: *Inteiro* ou *Real*

Um valor numérico que especifica o número que deve ser soletrado.

`language`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de idioma.

`currency`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o código de moeda.

`print currency name flag`: *Booliano*

Um valor *Booliano* que indica se um nome de moeda deve ser adicionado ao texto soletrado.

`decimal points`: *Inteiro*

Um valor *Inteiro* que indica o número de casas decimais que o texto soletrado deve ter.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

O código de idioma é opcional. Se for definido como uma cadeia de caracteres vazia, o código de idioma do contexto em execução será utilizado. O código de idioma padrão é **EN-US**. O código de idioma do contexto em execução é definido em um elemento **Pasta** ou **Arquivo** do formato de relatório eletrônico (ER) que está sendo executado.

O código de moeda é opcional. Se for definido como uma cadeia de caracteres vazia, a moeda da empresa do contexto em execução será utilizada.

> [!NOTE] 
> Os argumentos `print currency name flag` e `decimal points` são analisados somente para os seguintes códigos de idioma: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** e **RU**. Além disso, o argumento `print currency name flag` é analisado somente para empresas nas quais o contexto do país ou da região ofereça suporte a variações de nomes de moeda.

## <a name="example-1"></a>Exemplo 1

`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` retorna **"One Thousand Two Hundred Thirty Four and 56"**.

## <a name="example-2"></a>Exemplo 2

`NUMERALSTOTEXT (120, "PL", "", false, 0)` retorna **"Sto dwadzieścia"**. 

## <a name="example-3"></a>Exemplo 3

`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` retorna **"Сто двадцать евро 21 евроцент"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
