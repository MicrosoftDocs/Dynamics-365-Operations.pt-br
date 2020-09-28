---
title: Função de ER AND
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) AND é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 4a246496eca0d5a8538ac7f1577957e6b9eae4e3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743461"
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
