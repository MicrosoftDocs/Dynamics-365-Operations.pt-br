---
title: Função de ER EMPTYLIST
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) EMPTYLIST é usada.
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
ms.openlocfilehash: 0157257d46070a9e497dccfef669a3d2d321a122
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905360"
---
# <a name="emptylist-er-function"></a>Função de ER EMPTYLIST

[!include [banner](../includes/banner.md)]

A função `EMPTYLIST` retorna um valor de *Lista de registros* vazio usando a lista especificada como uma fonte para a estrutura da lista.

## <a name="syntax"></a>Sintaxe

```vb
EMPTYLIST (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="example"></a>Exemplo

`EMPTYLIST (SPLIT ("abc", 1))` retorna uma nova lista vazia que tem a mesma estrutura da lista retornada pela função `SPLIT` usada.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]