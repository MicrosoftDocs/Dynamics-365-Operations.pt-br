---
title: Função de ER TRIM
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) TRIM é usada.
author: kfend
ms.date: 02/28/2022
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
ms.openlocfilehash: 95b8d2989d705c4998da0af8e683adf567edfe92
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273088"
---
# <a name="trim-er-function"></a>Função de ER TRIM

[!include [banner](../includes/banner.md)]

A função `TRIM` retorna a sequência de texto especificada como um valor de *Cadeia de caracteres* após a substituição de guia, retorno de carro, avanço de linha e caracteres de avanço de forma por um único caractere de espaço, após o truncamento dos espaços à esquerda e à direita, e a remoção de vários espaços entre palavras.

## <a name="syntax"></a>Sintaxe

```vb
TRIM (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

## <a name="return-values"></a>Valores de retorno

*Sequência de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Em alguns casos, talvez você queira truncar espaços à esquerda e à direita, mas prefere manter a formatação para o texto especificado. Por exemplo, quando esse texto representa um endereço que pode ser inserido na caixa de texto de várias linhas e pode conter avanço de linha e formatação de retorno de carro. Nesse caso, use a seguinte expressão: `REPLACE(text,"^[ \t]+|[ \t]+$","", true)` onde `text` é o argumento que se refere à cadeia de texto especificada.

## <a name="example-1"></a>Exemplo 1

`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` retorna **"Texto de exemplo"**.

## <a name="example-2"></a>Exemplo 2

`TRIM (CONCATENATE (CHAR(10), "`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(9),"`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`", CHAR(13)))` retorna **"Texto de exemplo"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)

[Função de ER REPLACE](er-functions-text-replace.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
