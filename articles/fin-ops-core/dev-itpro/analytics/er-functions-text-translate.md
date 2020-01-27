---
title: Função de ER TRANSLATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TRANSLATE é usada.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 11954f3e48d8dc2257b3a0bc8768df47af3c5c0c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916697"
---
# <a name="TRANSLATE">Função de ER TRANSLATE</a>

[!include [banner](../includes/banner.md)]

A função `TRANSLATE` retorna a cadeia de caracteres de texto especificada como um valor de *Cadeia de caracteres* após toda ou parte dela ser substituída por outra cadeia de caracteres.

## <a name="syntax"></a>Sintaxe

```
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

`pattern`: *Cadeia de caracteres*

O texto que deve ser substituído.

`replacement`: *Cadeia de caracteres*

O texto a ser usado como substituto.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`TRANSLATE ("abcdef", "cd", "GH")` substitui o padrão **"cd"** pela cadeia de caracteres **"GH"** e retorna **"abGHef"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)
