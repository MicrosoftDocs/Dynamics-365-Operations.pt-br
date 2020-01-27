---
title: Função de ER EMPTYLIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) EMPTYLIST é usada.
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
ms.openlocfilehash: a60bc948ff6223b6e3acccd0ba40bf64f238aac2
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917387"
---
# <a name="EMPTYLIST">Função de ER EMPTYLIST</a>

[!include [banner](../includes/banner.md)]

A função `EMPTYLIST` retorna um valor de *Lista de registros* vazio usando a lista especificada como uma fonte para a estrutura da lista.

## <a name="syntax"></a>Sintaxe

```
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
