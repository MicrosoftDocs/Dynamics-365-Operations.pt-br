---
title: Função de ER OR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) OR é usada.
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
ms.openlocfilehash: f6751c70599b5e3c05b9d1c69a95e82673b230210170cfead1e6a87c57d59c7f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6747560"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]