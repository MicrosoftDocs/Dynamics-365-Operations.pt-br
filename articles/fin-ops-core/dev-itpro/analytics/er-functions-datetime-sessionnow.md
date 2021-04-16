---
title: Função de ER SESSIONNOW
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SESSIONNOW é usada.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746782"
---
# <a name="sessionnow-er-function"></a>Função de ER SESSIONNOW

[!include [banner](../includes/banner.md)]

A função `SESSIONNOW` retorna um valor de *DateTime* que representa a data e a hora atual da sessão do aplicativo.

## <a name="syntax"></a>Sintaxe

```vb
SESSIONNOW ()
```

## <a name="return-values"></a>Valores de retorno

*Data/Hora*

O valor de data/hora resultante.

## <a name="example"></a>Exemplo

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]