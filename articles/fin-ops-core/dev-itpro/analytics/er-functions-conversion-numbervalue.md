---
title: Função NUMBERVALUE ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) NUMBERVALUE é usada.
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
ms.openlocfilehash: 9701fe7a1ce2a96fa5fa8df8aeda125c861a117a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871517"
---
# <a name="numbervalue-er-function"></a>Função NUMBERVALUE ER

[!include [banner](../includes/banner.md)]

A função `NUMBERVALUE` retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado. Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.

## <a name="syntax"></a>Sintaxe

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de texto que deve ser convertido para um número *Real*.

`decimal separator`: Cadeia de caracteres

Um separador decimal. Ele é usado para separar as partes inteira e fracionária de um número decimal.

`digit grouping separator`: *Cadeia de caracteres*

Um separador de agrupamento de dígitos. É usado como separador de milhar.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="example"></a>Exemplo

`NUMBERVALUE( "1 234,56", ",", " ")` retorna **1234.56**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de conversão de tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]