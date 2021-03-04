---
title: Função de ER CH_BANK_MOD_10
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CH_BANK_MOD_10 é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bca82cd596ba1e3ec42b3dba91ee6c4871ff8601
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686849"
---
# <a name="ch_bank_mod_10-er-function"></a>Função de ER CH_BANK_MOD_10

[!include [banner](../includes/banner.md)]

A função `CH_BANK_MOD_10` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD10, com base nos dígitos do número de fatura especificado.

## <a name="syntax"></a>Sintaxe

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadeia de caracteres*

Um valor de texto que representa os dígitos de um número de fatura.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CH_BANK_MOD_10 ("VEND-200002")` retorna **3**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]