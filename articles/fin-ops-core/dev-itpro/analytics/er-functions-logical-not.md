---
title: Função de ER NOT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) NOT é usada.
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
ms.openlocfilehash: da30e9a0092f594da7cef7b425e2b89af7bda491
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890475"
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