---
title: Funções CONTAINS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONTAINS é usada.
author: NickSelin
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: c1d2d761a38d0edfb9abd439e0f710b336f54927
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745416"
---
# <a name="contains-er-function"></a>Funções CONTAINS ER

[!include [banner](../includes/banner.md)]

A função `CONTAINS` determina se a entrada especificada contém o texto especificado. Ele retorna um valor *Booliano* **TRUE** se a entrada especificada contém o texto especificado. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O caminho válido de um item de uma fonte de dados do tipo *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode conter o segundo argumento.

`search text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo de dados *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode estar contido no primeiro argumento.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função pode ser usada para especificar uma expressão de condição da função [FILTER](er-functions-list-filter.md) somente quando o mapeamento relevante é configurado no [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acessar o [Microsoft Dataverse](../data-entities/data-integration-cds.md). Caso contrário, uma exceção é lançada no tempo de design. A mensagem recomenda que você use a função [WHERE](er-functions-list-where.md) em vez da função `FILTER`.

## <a name="example-1"></a>Exemplo 1

A expressão `CONTAINS ("abc", "d")` retorna **FALSE**, enquanto a expressão `CONTAINS ("abc", "C")` retorna **TRUE**.

## <a name="example-2"></a>Exemplo 2

A expressão `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` retornará **TRUE** se o valor do campo **Endereço** da fonte de dados do **modelo** contiver a cadeia de caracteres **DEU**. Caso contrário, ele retornará **FALSO**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
