---
title: Função de ER POWER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) POWER é usada.
author: kfend
ms.date: 12/17/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 9b6693d7c1afebcf9c30d1bf8d72950053c305bd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273980"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
