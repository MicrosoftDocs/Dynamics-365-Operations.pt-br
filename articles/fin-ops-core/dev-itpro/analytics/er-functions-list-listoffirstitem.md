---
title: Função de ER LISTOFFIRSTITEM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIRSTITEM é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: f2e1f7e55c61f883aebb9d5a522a883a9a9de694
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5569831"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]