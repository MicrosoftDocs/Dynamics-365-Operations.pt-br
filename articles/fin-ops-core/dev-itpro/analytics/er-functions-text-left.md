---
title: Função de ER LEFT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LEFT é usada.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 4293db244d04debf3679cf2bde0b892bd74e8ead
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041115"
---
# <a name="LEFT">Função de ER LEFT</a>

[!include [banner](../includes/banner.md)]

A função `LEFT` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado a partir do início da cadeia de caracteres especificada.

## <a name="syntax"></a>Sintaxe

```vb
LEFT (text, number)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o texto original.

`number`: *Inteiro*

O número de caracteres que deve ser retornado a partir do início do texto original.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`LEFT ("Sample", 3)` retorna **"Sam"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)
