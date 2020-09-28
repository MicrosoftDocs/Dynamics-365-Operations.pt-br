---
title: Função de ER ISVALIDCHARACTERISO7064
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISVALIDCHARACTERISO7064 é usada.
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
ms.openlocfilehash: 21962952bb3bdd016831dc5e196af27c69ecc6db
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744062"
---
# <a name="isvalidcharacteriso7064-er-function"></a>Função de ER ISVALIDCHARACTERISO7064

[!include [banner](../includes/banner.md)]

A função `ISVALIDCHARACTERISO7064` retorna um valor *Booliano* de **TRUE** se a cadeia de caracteres especificada representar um IBAN (Número de Conta Bancária Internacional) válido. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadeia de caracteres*

Um valor de texto que representa um IBAN.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` retorna **TRUE**. 

`ISVALIDCHARACTERISO7064 ("AT61")` retorna **FALSE**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
