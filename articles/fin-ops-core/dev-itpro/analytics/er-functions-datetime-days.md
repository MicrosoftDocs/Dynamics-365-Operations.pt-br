---
title: Função DAYS ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) DAYS é usada.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 41a324ca93497f8b297c8c944f622b7829f1ceff
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8881207"
---
# <a name="days-er-function"></a>Função DAYS ER

[!include [banner](../includes/banner.md)]

A função `DAYS` retorna um valor *Inteiro* que representa o número de dias entre uma data especificada e uma segunda data especificada.

## <a name="syntax"></a>Sintaxe

```vb
DAYS (date 1, date 2) as Integer
```

## <a name="arguments"></a>Argumentos

`date 1`: *Data*

Um valor de data que representa a data inicial para o cálculo do número de dias.

`date 2`: *Data*

Um valor de data que representa a data final para o cálculo do número de dias.

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

A função `DAYS` retorna um valor positivo quando a primeira data for posterior à segunda, retorna **0** (zero) quando a primeira data for igual à segunda e retorna um valor negativo quando a primeira data for anterior à segunda data.

## <a name="example"></a>Exemplo

`DAYS (TODAY (), DATEVALUE( DATETIMEFORMAT( ADDDAYS ( NOW(), 1), "yyyyMMdd"), "yyyyMMdd"))` retorna **-1**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]