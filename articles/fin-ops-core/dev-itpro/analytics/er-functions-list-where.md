---
title: Função de ER WHERE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) WHERE é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: ca218f87eb1f9235ab475809fbbdfecf3fe0c7fb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566033"
---
# <a name="where-er-function"></a>Função de ER WHERE

[!include [banner](../includes/banner.md)]

A função `WHERE` retorna a lista especificada como um valor de *Lista de registros* após ser filtrada de acordo com a condição especificada.

## <a name="syntax"></a>Sintaxe

```vb
WHERE (list, condition)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`condition`: *Booliano*

Uma expressão condicional válida que é usada para filtrar os registros da lista especificada.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função difere da função [FILTER](er-functions-list-filter.md) porque a condição especificada é aplicada a todas as fontes de dados de relatório eletrônico (ER) do tipo *Lista de registros* presentes na memória.

Se os argumentos configurados para esta função (`list` e `condition`) permitirem que essa solicitação seja traduzida para a chamada SQL direta, uma mensagem de aviso será gerada no momento do design. Essa mensagem informa o usuário que o desempenho pode ser melhorado se a função [FILTER](er-functions-list-filter.md) for usada em vez de `WHERE`.

## <a name="example-1"></a>Exemplo 1

Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable, a expressão `WHERE (Vendors, Vendors.VendGroup = "40")` retornará uma lista apenas com os fornecedores que pertencem ao grupo de fornecedores 40.

## <a name="example-2"></a>Exemplo 2

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `WHERE( DS, DS.Value = "B")` retornará uma lista com apenas um registro que contém o texto **"B"** no campo **Valor**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]