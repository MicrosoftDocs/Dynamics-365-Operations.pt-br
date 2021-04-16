---
title: Função de ER NULLDATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLDATE é usada.
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
ms.openlocfilehash: 6ac8da3f18c7793512685d52dd64a9bd55bfb8fc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746834"
---
# <a name="nulldate-er-function"></a>Função de ER NULLDATE

[!include [banner](../includes/banner.md)]

A função `NULLDATE` retorna um valor de *Data* que representa a data **nula** (1º de janeiro de 1900).

## <a name="syntax"></a>Sintaxe

```vb
NULLDATE () as 
```

## <a name="return-values"></a>Valores de retorno

*Data*

O valor de data resultante.

## <a name="example-1"></a>Exemplo 1

`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` retorna a data **nula**, 1º de janeiro de 1900, como **"1900-01-01"**, com base no formato personalizado especificado.

## <a name="example-2"></a>Exemplo 2

A expressão `IF( Invoice.DocumentDate = NULLDATE(), true, false)` retorna **Verdadeiro** quando o valor do campo **DocumentDate** é igual à data **nula**. Nesse exemplo, **Fatura** é uma fonte de dados de relatório eletrônico (ER) do tipo **Registros de tabela/finanças** e se refere à tabela CustInvoiceJour.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]