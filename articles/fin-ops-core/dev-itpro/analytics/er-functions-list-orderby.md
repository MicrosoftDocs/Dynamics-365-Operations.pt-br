---
title: Função de ER ORDERBY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ORDERBY é usada.
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
ms.openlocfilehash: 6ff280d66fd2c418984f2d7fd31a32609932e89c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745000"
---
# <a name="orderby-er-function"></a>Função de ER ORDERBY

[!include [banner](../includes/banner.md)]

A função `ORDERBY` retorna a lista especificada como um valor de *Lista de registros* após ela ser classificada de acordo com os argumentos especificados. Esses argumentos podem ser definidos como expressões.

## <a name="syntax"></a>Sintaxe

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`expression 1`: *Campo*

O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada. O campo referenciado deve ser um campo do tipo de dados primitivo. Esse argumento é obrigatório.

`expression N`: *Campo*

O caminho válido de um campo da fonte de dados que é referenciado pelo argumento `list` da função chamada. O campo referenciado deve ser um campo do tipo de dados primitivo. Esses argumentos adicionais são opcionais.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="example-1"></a>Exemplo 1

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("C|B|A", "|")`, a expressão `FIRST( ORDERBY( DS, DS. Value)).Value` retornará o valor de texto **"A"**.

## <a name="example-2"></a>Exemplo 2

Se **Fornecedor** estiver configurado como uma fonte de dados de relatório eletrônico (ER) que se refere à tabela VendTable, a expressão `ORDERBY (Vendors, Vendors.'name()')` retornará uma lista de fornecedores que é classificada por nome em ordem crescente.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
