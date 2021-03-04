---
title: Função de ER VALUEIN
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) VALUEIN é usada.
author: NickSelin
manager: kfend
ms.date: 08/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 0a133067ab74c711084cc1d7f456cbe49acdf79d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686921"
---
# <a name="valuein-er-function"></a>Função de ER VALUEIN

[!include [banner](../includes/banner.md)]

A função `VALUEIN` determina se a entrada especificada corresponde a algum valor de um item especificado na lista especificada. Ela retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada. Caso contrário, ela retorna um valor *Booliano* de **FALSE**.

## <a name="syntax"></a>Sintaxe

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a>Argumentos

`input`: *Campo*

O caminho válido de um item de uma fonte de dados do tipo *Lista de registros*. O valor desse item será correspondido.

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`list item expression`: *Booliano*

Uma expressão condicional válida que aponta para ou contém um único campo da lista especificada que deve ser usado na correspondência.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name="usage-notes"></a>Notas de uso

Em geral, a função `VALUEIN` é convertida em um conjunto de condições **OR**. Se a lista de condições **OU** for grande e o tamanho máximo total de uma instrução SQL puder ser excedido, use a função [`VALUEINLARGE`](er-functions-logical-valueinlarge.md).

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

Em alguns casos, ela pode ser convertida em uma instrução SQL de banco de dados usando o operador `EXISTS JOIN`.

## <a name="example-1"></a>Exemplo 1

No seu mapeamento de modelo, você define a fonte de dados **Lista** do tipo *Campo calculado*. Essa fonte de dados contém a expressão `SPLIT ("a,b,c", ",")`.

Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, List.Value)`, ela retorna **TRUE**. Nesse caso, a função `VALUEIN` é convertida no seguinte conjunto de condições: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, onde `("B" = "b")` é igual a **TRUE**.

Quando uma fonte de dados é chamada, se tiver sido configurada como a expressão `VALUEIN ("B", List, LEFT(List.Value, 0))`, ela retorna **FALSE**. Nesse caso, a função `VALUEIN` é convertida na seguinte condição: `("B" = "")`, que não é igual a **TRUE**.

O limite superior para o número de caracteres no texto dessa condição é de 32.768 caracteres. Portanto, você não deve criar fontes de dados que possam exceder esse limite no tempo de execução. Se o limite for excedido, o aplicativo interrompe a execução e uma exceção é gerada. Por exemplo, essa situação poderá ocorrer se a fonte de dados for configurada como `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)` e as listas **List1** e **List2** contiverem muitos registros.

Em alguns casos, a função `VALUEIN` é convertida em uma instrução de banco de dados usando o operador `EXISTS JOIN`. Esse comportamento ocorre quando a função [`FILTER`](er-functions-list-filter.md) é usada e as seguintes condições são atendidas:

- A opção **SOLICITAR CONSULTA** é desativada para a fonte de dados da função `VALUEIN` que se refere à lista de registros. Nenhuma condição adicional será aplicada a essa fonte de dados no tempo de execução.
- Nenhuma expressão aninhada é configurada para a fonte de dados da função `VALUEIN` que se refere à lista de registros.
- Um item de lista da função `VALUEIN` se refere a um campo da fonte de dados especificada, não a uma expressão ou um método dessa fonte de dados.

Use esta opção, em vez da função [`WHERE`](er-functions-list-where.md) descrita anteriormente neste exemplo.

## <a name="example-2"></a>Exemplo 2

Você define as seguintes fontes de dados no mapeamento de modelo:

- A fonte de dados **In** do tipo *Registros de tabela*. Essa fonte de dados se refere à tabela Intrastat.
- A fonte de dados **Port** do tipo *Registros de tabela*. Essa fonte de dados se refere à tabela IntrastatPort.

Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` é chamada, a seguinte instrução SQL é gerada para retornar registros filtrados da tabela Intrastat.

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

Para campos **dataAreaId**, a instrução SQL final é gerada usando o operador `IN`.

## <a name="example-3"></a>Exemplo 3

Você define as seguintes fontes de dados no mapeamento de modelo:

- A fonte de dados **Le** do tipo *Campo calculado*. Essa fonte de dados contém a expressão `SPLIT ("DEMF,GBSI,USMF", ",")`.
- A fonte de dados **In** do tipo *Registros de tabela*. Essa fonte de dados se refere à tabela Intrastat e a opção **Interempresarial** é ativada para ela.

Quando uma fonte de dados que tenha sido configurada como a expressão `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` é chamada, a instrução SQL final contém a seguinte condição.

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)

[Funções VALUEINLARGE](er-functions-logical-valueinlarge.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]