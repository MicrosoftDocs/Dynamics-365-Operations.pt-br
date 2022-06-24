---
title: Função de ER CN_GBT_ADDITIONALDIMENSIONID
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) CN_GBT_ADDITIONALDIMENSIONID é usada.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 80ce6846cd4687c2a12815ef0da1e1684c57d1f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898759"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a>Função de ER CN_GBT_ADDITIONALDIMENSIONID

[!include [banner](../includes/banner.md)]

A função `CN_GBT_ADDITIONALDIMENSIONID` retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada. A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.

## <a name="syntax"></a>Sintaxe

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.

`number`: Inteiro

Um valor *Inteiro* que define o código de sequência da dimensão solicitada na cadeia de caracteres especificada.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` retorna **"CC"**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]