---
title: Função de ER ABS
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ABS é usada.
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
ms.openlocfilehash: 214fb2808f024487795f27de45de1d4de8cead2d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041644"
---
# <a name="ABS">Função de ER ABS</a>

[!include [banner](../includes/banner.md)]

A função `ABS` retorna o valor absoluto (módulo) do número especificado como um valor *Real*. Em outras palavras, ela retorna o número sem seu sinal.

## <a name="syntax"></a>Sintaxe

```vb
ABS (number)
```

## <a name="arguments"></a>Argumentos

`number`: *Real*

Um valor numérico do qual você deseja obter o módulo.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="example"></a>Exemplo

`ABS (-1)` retorna **1**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções matemáticas](er-functions-category-mathematical.md)
