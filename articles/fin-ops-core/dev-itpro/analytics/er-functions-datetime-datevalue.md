---
title: Função DATEVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEVALUE é usada.
author: NickSelin
ms.date: 12/04/2019
ms.topic: article
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
ms.openlocfilehash: cfaf183c61d3663442cbc244239b872b9e1957bb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891224"
---
# <a name="datevalue-er-function"></a>Função DATEVALUE ER

[!include [banner](../includes/banner.md)]

A função `DATEVALUE` retorna um valor de *Data* que é convertido de um valor de texto determinado no formato especificado e em uma [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada para um valor de data. Para obter informações sobre os formatos com suporte, consulte [padrão](/dotnet/standard/base-types/standard-date-and-time-format-strings) e [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="syntax-1"></a>Sintaxe 1

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Texto que representa o valor do formato.

`format`: *Cadeia de caracteres*

O formato de determinado texto.

`culture`: *Cadeia de caracteres*

A cultura usada para a formatação do texto especificado.

## <a name="return-values"></a>Valores de retorno

*Data*

O valor de data resultante.

## <a name="usage-notes"></a>Notas de uso

Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada. Por exemplo, se a função `DATEVALUE` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã. O valor padrão `culture` é **EN-US**.

## <a name="example-1"></a>Exemplo 1

`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` retorna o valor de data **21 de dezembro de 2016** com base no formato personalizado especificado e na cultura padrão **EN-US** do aplicativo.

## <a name="example-2"></a>Exemplo 2

`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` retorna o valor de data **21 de janeiro de 2016**, com base no formato e cultura personalizados especificados.

Porém, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` gerará uma exceção para informar ao usuário que a sequência de caracteres especificada não é reconhecida como uma data válida da cultura especificada.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]