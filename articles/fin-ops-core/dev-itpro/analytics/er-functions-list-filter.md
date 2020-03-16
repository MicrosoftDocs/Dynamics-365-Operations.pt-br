---
title: Função de ER FILTER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FILTER é usada.
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
ms.openlocfilehash: adeefd08531f59e478efbb45ab294b3bc8216f4c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042127"
---
# <a name="FILTER">Função de ER FILTER</a>

[!include [banner](../includes/banner.md)]

A função `FILTER` retorna a lista especificada como um valor de *Lista de registros* após a consulta ser alterada, de forma que ela filtre para a condição especificada.

## <a name="syntax"></a>Sintaxe

```vb
FILTER (list, condition)
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

Esta função difere da função [WHERE](er-functions-list-where.md) porque a condição especificada é aplicada a todas as fontes de dados de relatório eletrônico (ER) do tipo *Registros de tabela* no nível do banco de dados. A lista e a condição podem ser definidas usando tabelas e relações.

Se um ou ambos os argumentos configurados para esta função (`list` e `condition`) não permitirem que essa solicitação seja traduzida para a chamada SQL direta, uma exceção será gerada no momento do design. Essa exceção informa o usuário que `list` ou `condition` não pode ser usado para consultar o banco de dados.

## <a name="example-1"></a>Exemplo 1

Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable, a expressão `FILTER (Vendors, Vendors.VendGroup = "40")` retornará uma lista apenas com os fornecedores que pertencem ao grupo de fornecedores 40.

## <a name="example-2"></a>Exemplo 2

Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable e se **parmVendorBankGroup** estiver configurado como uma fonte de dados de ER que retorna um valor do tipo *Cadeia de caracteres*, a expressão `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` retornará uma lista apenas com as contas de fornecedores que pertencem a um grupo bancário específico.

## <a name="example-3"></a>Exemplo 3

Você insere a fonte de dados **DS** do tipo *Campo calculado* e ela contém a expressão `SPLIT ("A,B,C", ",")`. Em seguida, você insere outra expressão, `FILTER( DS, DS.Value = "B")`. Ao tentar salvar essa expressão no designer de fórmulas de ER, a seguinte exceção é gerada: "Erro de validação: A expressão de lista da função FILTER não é consultável".

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
