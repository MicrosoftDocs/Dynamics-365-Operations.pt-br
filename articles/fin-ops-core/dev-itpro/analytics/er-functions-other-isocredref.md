---
title: Função de ER ISOCREDREF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISOCREDREF é usada.
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
ms.openlocfilehash: 6c9a75cedcf543b318df2850df3e4a60bac2dc6b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680677"
---
# <a name="isocredref-er-function"></a>Função de ER ISOCREDREF

[!include [banner](../includes/banner.md)]

A função `ISOCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número de fatura especificado.

## <a name="syntax"></a>Sintaxe

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a>Argumentos

`invoice number digits`: *Cadeia de caracteres*

Um valor de texto que representa os dígitos de um número de fatura.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

> [!NOTE] 
> Para eliminar símbolos de alfabetos que não são compatíveis com ISO, o argumento `invoice number digits` deve ser traduzido antes de ser passado para esta função.

## <a name="example"></a>Exemplo

`ISOCredRef ("VEND-200002")` retorna **"RF23VEND-200002"**.

## <a name="additional-resources"></a>Recursos adicionais

[Outras funções (específicas de domínio comercial)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]