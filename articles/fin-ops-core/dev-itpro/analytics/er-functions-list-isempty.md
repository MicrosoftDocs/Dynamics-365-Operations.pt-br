---
title: Função de ER ISEMPTY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISEMPTY é usada.
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
ms.openlocfilehash: 41d1f773e3fc2f076dbe3d826d14a364548d6656c95c03e54eb36345c004fecd
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6740957"
---
# <a name="isempty-er-function"></a>Função de ER ISEMPTY

[!include [banner](../includes/banner.md)]

A função `ISEMPTY` retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
ISEMPTY (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="example-1"></a>Exemplo 1

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `ISEMPTY(DS)` retornará **FALSE**.

## <a name="example-2"></a>Exemplo 2

A expressão `ISEMPTY (SPLIT ("",1))` retorna **TRUE**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]