---
title: Função de ER ROUNDDOWN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ROUNDDOWN é usada.
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
ms.openlocfilehash: 89fc134ec11a47506211ce68ec3aaf966d9a308b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744454"
---
# <a name="rounddown-er-function"></a>Função de ER ROUNDDOWN

[!include [banner](../includes/banner.md)]

A função `ROUNDDOWN` retorna o número especificado como um valor *Real* após ele ser arredondado para baixo para o número especificado de casas decimais.

## <a name="syntax"></a>Sintaxe

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Um valor numérico que deve ser arredondado para baixo.

`decimals`: *Inteiro*

Um valor numérico que representa o número de casas decimais.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função comporta-se como [ROUND](er-functions-mathematical-round.md), mas sempre arredonda o número especificado para baixo (para zero).

## <a name="example-1"></a>Exemplo 1

`ROUNDDOWN (1200.767, 2)` arredonda para baixo para duas casas decimais e retorna **1200,76**. 

## <a name="example-2"></a>Exemplo 2

`ROUNDDOWN (1700.767, -3)` arredonda para baixo para o múltiplo mais próximo de 1.000 e retorna **1000**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]