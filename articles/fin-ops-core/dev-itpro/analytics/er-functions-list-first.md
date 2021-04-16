---
title: Função de ER FIRST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FIRST é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: d30c8481866ccf3f7080197b37586a0460a4ad2c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746570"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]