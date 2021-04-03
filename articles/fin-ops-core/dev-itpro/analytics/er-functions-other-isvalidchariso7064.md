---
title: Função de ER ISVALIDCHARACTERISO7064
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISVALIDCHARACTERISO7064 é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 26300adce5f9a8a567510885577c6cfb9b1c859a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563357"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]