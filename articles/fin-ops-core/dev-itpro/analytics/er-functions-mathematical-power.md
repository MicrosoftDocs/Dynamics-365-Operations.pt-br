---
title: Função de ER POWER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) POWER é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915892"
---
# <a name="POWER">Função de ER POWER</a>

[!include [banner](../includes/banner.md)]

A função `POWER` retorna um valor *Real* que representa o resultado da elevação do número positivo especificado à potência especificada.

## <a name="syntax"></a>Sintaxe

```
POWER (number, power)
```

## <a name="arguments"></a>Argumentos

`number`: *Real* ou *Inteiro*

Um valor numérico que deve ser elevado à potência especificada.

`power`: *Real* ou *Inteiro*

Um valor numérico que representa a potência específica.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="example-1"></a>Exemplo 1

`POWER (10, 2)` retorna **100**.

## <a name="example-2"></a>Exemplo 2

`POWER (4, 0.5)` retorna **2**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)
