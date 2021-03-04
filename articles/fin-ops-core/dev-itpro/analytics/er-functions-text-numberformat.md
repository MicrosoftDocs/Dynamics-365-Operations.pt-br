---
title: Função de ER NUMBERFORMAT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NUMBERFORMAT é usada.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 2c3907d1d2c74c852f4f90731e5f4bc23bfbd717
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680257"
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