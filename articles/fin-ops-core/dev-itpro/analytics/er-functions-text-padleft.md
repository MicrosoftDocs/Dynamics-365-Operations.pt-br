---
title: Função de ER PADLEFT
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) PADLEFT é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 551b508bc6a17b1c6a08e25d5db0094713d9634f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8892556"
---
# <a name="padleft-er-function"></a>Função de ER PADLEFT

[!include [banner](../includes/banner.md)]

A função `PADLEFT` retorna um valor de *Cadeia de caracteres* do tamanho especificado, em que o início da cadeia de caracteres especificada é preenchido com os caracteres especificados.

## <a name="syntax"></a>Sintaxe

```vb
PADLEFT (text, length, padding chars)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de *Cadeia de caracteres* que representa o texto original.

`length`: *Inteiro*

Um valor *Inteiro* que representa o número final de caracteres na cadeia de caracteres preenchida.

`padding chars`: *Cadeia de caracteres*

Os caracteres a serem usados para o preenchimento.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`PADLEFT ("1234", 10, "`&nbsp;`")` retorna a cadeia de caracteres de texto **"&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1234"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]