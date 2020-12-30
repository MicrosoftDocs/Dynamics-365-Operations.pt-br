---
title: Função de ER NOT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NOT é usada.
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
ms.openlocfilehash: 2308ab4d222863312441b3f17559ac4d3afbfb29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686945"
---
# <a name="not-er-function"></a>Função de ER NOT

[!include [banner](../includes/banner.md)]

A função `NOT` retorna o valor lógico revertido da condição especificada como um valor *Booliano*.

## <a name="syntax"></a>Sintaxe

```vb
NOT (condition)
```

## <a name="arguments"></a>Argumentos

`condition`: *Booliano*

Uma expressão condicional válida que deve ser revertida.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="example"></a>Exemplo

`NOT (TRUE)` retorna **FALSE**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
