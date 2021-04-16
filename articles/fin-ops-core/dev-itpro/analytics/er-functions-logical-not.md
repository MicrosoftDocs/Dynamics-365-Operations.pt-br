---
title: Função de ER NOT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NOT é usada.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751696"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]