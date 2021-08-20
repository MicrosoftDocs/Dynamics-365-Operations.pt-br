---
title: Função de ER AND
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) AND é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 4d327f0f961a11fecdbc055ffbb1f3d8bc15bcfdd732e2565d0a5e9e2c0a31ca
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756420"
---
# <a name="and-er-function"></a>Função de ER AND

[!include [banner](../includes/banner.md)]

A função `AND` retorna um valor *Booliano* de **TRUE** se todas as condições especificadas forem verdadeiras. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentos

`condition 1`: *Booliano*

Uma expressão condicional válida que deve ser testada. Esse argumento é obrigatório.

`condition N`: *Booliano*

Uma expressão condicional válida que deve ser testada. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="usage-notes"></a>Notas de uso

Nos argumentos de funções lógicas, você pode usar referências de fontes de dados, valores numéricos e de texto, valores boolianos, operadores de comparação e outras funções de relatório eletrônico (ER). No entanto, todos os argumentos devem ser avaliados como um valor *Booliano* de **TRUE** ou **FALSE**.

## <a name="example"></a>Exemplo

`AND (1=1, "a"="a")` retorna **TRUE**.

`AND (1=2, "a"="a")` retorna **FALSE**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]