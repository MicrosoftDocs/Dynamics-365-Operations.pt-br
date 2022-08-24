---
title: Função VALUE ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) VALUE é usada.
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 0a47637c47ca6c947451efa1230191779401b4e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277652"
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
