---
title: Função de ER COUNT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) COUNT é usada.
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
ms.openlocfilehash: c48483a6677aaeb36eac57a57cec71bf54c7991d
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745336"
---
# <a name="count-er-function"></a>Função de ER COUNT

[!include [banner](../includes/banner.md)]

A função `COUNT` retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia. Se a lista estiver vazia, essa função retornará **0** (zero).

## <a name="syntax"></a>Sintaxe

```vb
COUNT (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="example"></a>Exemplo

`COUNT (SPLIT("abcd" , 3))` retorna **2**, porque a função `SPLIT` usada neste exemplo cria uma lista que consiste em dois registros.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
