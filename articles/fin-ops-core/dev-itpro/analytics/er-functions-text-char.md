---
title: Função de ER CHAR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CHAR é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: e422ccc406e919b2191f4bccb1ac8198bba84b09e9f01f6971876e2c6507d6d3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6754357"
---
# <a name="char-er-function"></a>Função de ER CHAR

[!include [banner](../includes/banner.md)]

A função `CHAR` retorna um valor de *Cadeia de caracteres* que apresenta um caractere único referenciado pelo número Unicode especificado.

## <a name="syntax"></a>Sintaxe

```vb
CHAR (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Inteiro*

Um número que corresponde a um caractere único esperado.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

A cadeia de caracteres que esta função retorna depende da codificação selecionada no elemento de formato **FILE** pai. Para obter uma lista das codificações com suporte, consulte [Classe de codificação](/dotnet/api/system.text.encoding).

## <a name="example"></a>Exemplo

`CHAR (255)` retorna **"ÿ"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]