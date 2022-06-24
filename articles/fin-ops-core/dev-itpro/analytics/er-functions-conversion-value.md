---
title: Função VALUE ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) VALUE é usada.
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
ms.openlocfilehash: e96d274962ad79969a3158f7e352d3c72bd4072c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892970"
---
# <a name="value-er-function"></a>Função VALUE ER

[!include [banner](../includes/banner.md)]

A função `VALUE` retorna um valor Real que é convertido do valor de *Cadeia de caracteres especificado*.

## <a name="syntax"></a>Sintaxe

```vb
VALUE (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Uma cadeia de caracteres deve ser convertida para um valor numérico.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

As vírgulas e os caracteres de ponto (.) são considerados separadores decimais, e um hífen principal (-) é usado como um sinal negativo. Uma exceção é gerada no momento de execução da sequência de caracteres especificada contiver outros caracteres não numéricos.

## <a name="example-1"></a>Exemplo 1

`VALUE ("1 234,56")` aciona uma exceção.

## <a name="example-2"></a>Exemplo 2

`VALUE ("1234,56")` retorna **1234.56**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de conversão de tipo](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]