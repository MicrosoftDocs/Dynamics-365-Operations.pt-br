---
title: Função de ER MOD_97
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) MOD_97 é usada.
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: f57b55a9c4182b411e098ebce2f36b78ef03b6f8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898423"
---
# <a name="mod_97-er-function"></a>Função de ER MOD_97

[!include [banner](../includes/banner.md)]

A função `MOD_97` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD97, com base nos dígitos do número de fatura especificado.

## <a name="syntax"></a>Sintaxe

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadeia de caracteres*

Um valor de texto que representa os dígitos de um número de fatura.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`MOD_97 ("VEND-200002")` retorna **"20000285"**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]