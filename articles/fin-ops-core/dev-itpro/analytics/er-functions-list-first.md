---
title: Função de ER FIRST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FIRST é usada.
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
ms.openlocfilehash: 3ed0e0aaf29e2a67a4842d71121f1adc24f524f7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745216"
---
# <a name="first-er-function"></a>Função de ER FIRST

[!include [banner](../includes/banner.md)]

A função `FIRST` retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se essa lista não estiver vazia. Se a lista estiver vazia, essa função gerará uma exceção.

## <a name="syntax"></a>Sintaxe

```vb
FIRST (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="example-1"></a>Exemplo 1

A expressão `FIRST(SPLIT("ABC",1)).Value` retorna o valor de texto **"A"**.

## <a name="example-2"></a>Exemplo 2

A expressão `FIRST(SPLIT("",1)).Value` gera uma exceção no tempo de execução.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
