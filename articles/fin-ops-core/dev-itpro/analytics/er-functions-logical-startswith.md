---
title: Função STARTSWITH ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) STARTSWITH é usada.
author: NickSelin
ms.date: 02/11/2021
ms.prod: ''
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
ms.openlocfilehash: b378f501ccf812cfa0ae09e7cfbfdcf4c8a24ab8747b8ffe6044769df14a3057
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6762215"
---
# <a name="startswith-er-function"></a>Função STARTSWITH ER

[!include [banner](../includes/banner.md)]

A função `STARTSWITH` determina se a entrada especificada começa com o texto especificado. Ele retorna um valor *Booliano* **TRUE** se a entrada especificada começa com o texto especificado. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O caminho válido de um item de uma fonte de dados do tipo *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode começar com o segundo argumento.

`start text`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo de dados *Cadeia de Caracteres* ou uma constante de cadeia de caracteres, o valor que pode estar no início do primeiro argumento.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função pode ser usada para especificar uma expressão de condição da função [FILTER](er-functions-list-filter.md) somente quando o mapeamento relevante é configurado no [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) para acessar o [Microsoft Dataverse](/power-platform/admin/data-integrator). Caso contrário, uma exceção é lançada no tempo de design. A mensagem recomenda que você use a função [WHERE](er-functions-list-where.md) em vez da função `FILTER`.

## <a name="example-1"></a>Exemplo 1

A expressão `STARTSWITH ("abc", "d")` retorna **FALSE**, enquanto a expressão `STARTSWITH ("abc", "A")` retorna **TRUE**.

## <a name="example-2"></a>Exemplo 2

A expressão `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` retornará **TRUE** se o valor do campo **Endereço** da fonte de dados do **modelo** iniciar com a cadeia de caracteres **123 Coffee Street**. Caso contrário, ele retornará **FALSO**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
