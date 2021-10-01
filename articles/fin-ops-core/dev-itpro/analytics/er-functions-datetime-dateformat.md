---
title: Função DATEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEFORMAT é usada.
author: NickSelin
ms.date: 09/08/2021
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
ms.openlocfilehash: 4a6c113f5f8147cbeaab103e86a44d4c66272c13
ms.sourcegitcommit: e7eeca05d738e9e46d6185d1ba349836ebafc1a4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7485483"
---
# <a name="dateformat-er-function"></a>Função DATEFORMAT ER

[!include [banner](../includes/banner.md)]

A função `DATEFORMAT` retorna um valor de *[Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string)* que apresenta um valor de data determinado como texto no formato especificado e em uma [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada. Para obter informações sobre os formatos com suporte, consulte [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintaxe 1

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a>Argumentos

`date`: *[Data](er-formula-supported-data-types-primitive.md#date)*

Um valor de data que representa a data do formato.

`format`: *Cadeia de caracteres*

O formato da cadeia de caracteres de saída. Para obter informações sobre os formatos com suporte, consulte [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

> [!NOTE]
> A cadeia de caracteres de formato diferencia maiúsculas de minúsculas quando você usa um formato padrão ou um formato personalizado. Por exemplo, o especificador de formato "d" [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) retorna a data usando o padrão de data abreviada, enquanto o especificador de formato "D" padrão retorna a data usando o padrão de data por extenso. Além disso, o especificador de formato "M" [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings) retorna o mês de 1 a 12, enquanto o especificador "m" de formato personalizado retorna o minuto de 0 a 59.

`culture`: *Cadeia de caracteres*

A cultura a ser usada para formatação. Para obter informações sobre culturas com suporte, consulte [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).

## <a name="return-values"></a>Valores de retorno

*Sequência de caracteres*

O valor da cadeia de caracteres resultante.

## <a name="usage-notes"></a>Notas de uso

Se a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada. Por exemplo, se a função `DATEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã. O valor padrão `culture` é **EN-US**.

## <a name="example-1"></a>Exemplo 1

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.

## <a name="example-2"></a>Exemplo 2

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
