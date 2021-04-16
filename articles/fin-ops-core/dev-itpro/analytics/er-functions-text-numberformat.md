---
title: Função de ER NUMBERFORMAT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERFORMAT é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 8de57d8b0a45b8b58849a24f2d8f0cde41e0ea3a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746195"
---
# <a name="numberformat-er-function"></a>Função de ER NUMBERFORMAT

[!include [banner](../includes/banner.md)]

A função `NUMBERFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta o número especificado no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada. Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/dwhawy9k(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/0c899ak8(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxe 1

```vb
NUMBERFORMAT (number, format)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
NUMBERFORMAT (number, format, culture)
```

## <a name="arguments"></a>Argumentos

`number`: *Inteiro* ou *Real*

Um valor numérico que especifica o número que deve ser formatado.

`format`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o formato.

`culture`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa a cultura a ser usada para a formatação.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Se a cultura não estiver definida como um argumento da função chamada, o contexto no qual esta função é executada determinará a cultura usada para formatar números.

## <a name="example-1"></a>Exemplo 1

Para a cultura **EN-US**, `NUMBERFORMAT (0.45, "p")` retorna **"45.00 %"** e `NUMBERFORMAT (10.45, "#")` retorna **"10"**.

## <a name="example-2"></a>Exemplo 2

`NUMBERFORMAT (10/3, "F2", "de")` retorna **3,33**, enquanto `NUMBERFORMAT (10/3, "F2", "en-us")` retorna **3.33**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]