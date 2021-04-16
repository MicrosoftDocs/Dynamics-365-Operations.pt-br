---
title: Função de ER MID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MID é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 9a9ff3f1055f6757d6d4073dbb816773d8bfc8ba
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746258"
---
# <a name="mid-er-function"></a>Função de ER MID

[!include [banner](../includes/banner.md)]

A função `MID` retorna um valor de *Cadeia de caracteres* que apresenta o número de caracteres especificado da cadeia de caracteres especificada, a partir da posição especificada.

## <a name="syntax"></a>Sintaxe

```vb
MID (text, starting position, number of characters)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que especifica o texto do qual os caracteres devem ser retornados.

`starting position`: *Inteiro*

Um valor *Inteiro* que especifica a posição do primeiro caractere que deve ser retornado do texto especificado.

`number of characters`: *Inteiro*

Um valor *Inteiro* que especifica o número de caracteres que deve ser retornado, a partir da posição inicial especificada.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Se o valor do argumento `starting position` for menor do que 0 (zero), os caracteres retornados serão contados a partir da primeira posição na cadeia de caracteres especificada.

Se o valor do argumento `starting position` exceder o tamanho da cadeia de caracteres especificada, uma cadeia de caracteres vazia será retornada.

## <a name="example"></a>Exemplo

`MID ("Sample", 2, 3)` retorna **"amp"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]