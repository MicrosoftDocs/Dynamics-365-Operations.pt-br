---
title: Função de ER CONCATENATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONCATENATE é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 1a21140e5636ebd96eca4be90308c915e77510e1
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743894"
---
# <a name="concatenate-er-function"></a>Função de ER CONCATENATE

[!include [banner](../includes/banner.md)]

A função `CONCATENATE` retorna todas as cadeias de caracteres de texto especificadas como um valor de *Cadeia de caracteres* depois que elas são unidas em uma cadeias de caracteres.

## <a name="syntax"></a>Sintaxe

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a>Argumentos

`text 1`: *Cadeia de caracteres*

Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*. Esse argumento é obrigatório.

`text N`: *Cadeia de caracteres*

Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CONCATENATE ("abc", "def")` retorna **"abcdef"**.

## <a name="usage-notes"></a>Notas de uso

A expressão `"abc" & "def"` também retorna **"abcdef"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)
