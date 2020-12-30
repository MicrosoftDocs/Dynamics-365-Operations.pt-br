---
title: Função de ER LISTOFFIRSTITEM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIRSTITEM é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ea81bce8cd6b922f3ef1d53ec0c4b2574780377
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686479"
---
# <a name="listoffirstitem-er-function"></a>Função de ER LISTOFFIRSTITEM

[!include [banner](../includes/banner.md)]

A função `LISTOFFIRSTITEM` retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.

## <a name="syntax"></a>Sintaxe

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="example"></a>Exemplo

A expressão `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` retorna o valor de texto **"A"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
