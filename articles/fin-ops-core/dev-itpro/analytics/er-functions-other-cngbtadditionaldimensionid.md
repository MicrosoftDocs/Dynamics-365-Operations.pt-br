---
title: Função de ER CN_GBT_ADDITIONALDIMENSIONID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CN_GBT_ADDITIONALDIMENSIONID é usada.
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
ms.openlocfilehash: 2395a1932e543e35ced28a2a6e56ab44835de19a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041529"
---
# <a name="CN_GBT_ADDITIONALDIMENSIONID">Função de ER CN_GBT_ADDITIONALDIMENSIONID</a>

[!include [banner](../includes/banner.md)]

A função `CN_GBT_ADDITIONALDIMENSIONID` retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada. A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.

## <a name="syntax"></a>Sintaxe

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.

`number`: Inteiro

Um valor *Inteiro* que define o código de sequência da dimensão solicitada na cadeia de caracteres especificada.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` retorna **"CC"**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
