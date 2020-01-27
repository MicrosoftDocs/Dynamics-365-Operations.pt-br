---
title: Função de ER CURCREDREF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CURCREDREF é usada.
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
ms.openlocfilehash: 5633541b1c7e25a0cfb837c4679691506806421b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916996"
---
# <a name="CURCREDREF">Função de ER CURCREDREF</a>

[!include [banner](../includes/banner.md)]

A função `CURCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor, com base nos dígitos do número de fatura especificado.

## <a name="syntax"></a>Sintaxe

```
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadeia de caracteres*

Um valor de texto que representa os dígitos de um número de fatura.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

`CURCredRef ("VEND-200002")` retorna **"2200002"**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)
