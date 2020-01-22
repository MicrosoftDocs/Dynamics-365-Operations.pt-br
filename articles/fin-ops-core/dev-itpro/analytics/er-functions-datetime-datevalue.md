---
title: Função DATEVALUE ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATEVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 700a48d2c5a77398267e6daaaea3ecb6c95e7f6e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916352"
---
# <a name="DATEVALUE">Função DATEVALUE ER</a>

[!include [banner](../includes/banner.md)]

A função `DATEVALUE` retorna um valor de *Data* que é convertido de um valor de texto determinado no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada para um valor de data. Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxe 1

```
DATEVALUE (text, format)
```

## <a name="syntax-2"></a>Sintaxe 2

```
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
