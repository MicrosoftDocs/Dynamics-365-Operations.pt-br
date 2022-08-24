---
title: Função de ER FILTER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) FILTER é usada.
author: kfend
ms.date: 12/14/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: cfaf76daa8118942c3650e6b39c853434a20ee30
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272578"
---
# <a name="filter-er-function"></a>Função de ER FILTER

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

## <a name="usage-notes"></a><a name="usage-notes"></a>Notas de uso

Esta função difere da função [WHERE](er-functions-list-where.md) porque a condição especificada é aplicada a todas as fontes de dados de relatório eletrônico (ER) do tipo *Registros de tabela* no nível do banco de dados. A lista e a condição podem ser definidas usando tabelas e relações.

Se um ou ambos os argumentos configurados para esta função (`list` e `condition`) não permitirem que essa solicitação seja traduzida para a chamada SQL direta, uma exceção será gerada no momento do design. Essa exceção informa o usuário que `list` ou `condition` não pode ser usado para consultar o banco de dados.

> [!NOTE]
> A função `FILTER` se comporta de forma diferente da função `WHERE` quando a função [`VALUEIN`](er-functions-logical-valuein.md) é usada para especificar os critérios de seleção.
> 
> - Se a função `VALUEIN` for usada no escopo da função `WHERE` e o segundo argumento de `VALUEIN` se referir a uma fonte de dados que não retorna registros, o valor booliano *[False](er-formula-supported-data-types-primitive.md#boolean)* que `VALUEIN` retorna será considerado. Portanto, a expressão `WHERE(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` não retornará nenhum registro de fornecedor se a fonte de dados **VendGroups** não retornar registros de grupo de fornecedores.
> - Se a função `VALUEIN` for usada no escopo da função `FILTER` e o segundo argumento de `VALUEIN` se referir a uma fonte de dados que não retorna registros, o valor booliano *[False](er-formula-supported-data-types-primitive.md#boolean)* que `VALUEIN` retorna será ignorado. Portanto, a expressão `FILTER(Vendors, VALUEIN(Vendors.VendGroup, VendGroups, VendGroups.VendGroup))` retornará todos os registros de fornecedores da fonte de dados **Fornecedores**, mesmo que a fonte de dados **VendGroups** não retorne nenhum registro de grupo de fornecedores.

## <a name="example-1"></a>Exemplo 1

Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable, a expressão `FILTER (Vendors, Vendors.VendGroup = "40")` retornará uma lista apenas com os fornecedores que pertencem ao grupo de fornecedores 40.

## <a name="example-2"></a>Exemplo 2

Se **Fornecedor** estiver configurado como uma fonte de dados de ER que se refere à tabela VendTable e se **parmVendorBankGroup** estiver configurado como uma fonte de dados de ER que retorna um valor do tipo *Cadeia de caracteres*, a expressão `FILTER ( Vendor.'<Relations'.VendBankAccount, Vendor.'<Relations'.VendBankAccount.BankGroupID = parmVendorBankGroup)` retornará uma lista apenas com as contas de fornecedores que pertencem a um grupo bancário específico.

## <a name="example-3"></a>Exemplo 3

Você insere a fonte de dados **DS** do tipo *Campo calculado* e ela contém a expressão `SPLIT ("A,B,C", ",")`. Em seguida, você insere outra expressão, `FILTER( DS, DS.Value = "B")`. Ao tentar salvar essa expressão no designer de fórmulas de ER, a seguinte exceção é gerada: "Erro de validação: A expressão de lista da função FILTER não é consultável".

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
