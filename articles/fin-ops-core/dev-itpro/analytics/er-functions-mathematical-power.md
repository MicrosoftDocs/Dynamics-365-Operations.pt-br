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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 858f59cf0bc6387b09cbb6f0c59f58ba8107582c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683320"
---
# <a name="power-er-function"></a>Função de ER POWER

[!include [banner](../includes/banner.md)]

A função `POWER` retorna um valor *Real* que representa o resultado da elevação do número positivo especificado à potência especificada.

## <a name="syntax"></a>Sintaxe

```vb
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
