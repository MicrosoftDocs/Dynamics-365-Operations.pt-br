---
title: Função de ER OR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) OR é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 107241dbf9a5127d61343fc1cf42c3bab577adb3
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686969"
---
# <a name="or-er-function"></a>Função de ER OR

[!include [banner](../includes/banner.md)]

A função `OR` retorna um valor *Booliano* de **FALSE** se todas as condições especificadas forem falsas. Se qualquer condição especificada for verdade, a função retorna um valor *Booliano* como **TRUE**.

## <a name="syntax"></a>Sintaxe

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a>Argumentos

`condition 1`: *Booliano*

Uma expressão condicional válida que deve ser testada. Esse argumento é obrigatório.

`condition N`: *Booliano*

Uma expressão condicional válida que deve ser testada. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="example"></a>Exemplo

`OR (1=2, "a"="a")` retorna **TRUE**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
