---
title: Função VALUEINLARGE do ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) VALUEINLARGE é usada.
author: kfend
ms.date: 08/17/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 425dbce8f229acbb9c8d721c8f1a554989e0533c
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288068"
---
# <a name="valueinlarge-er-function"></a>Função VALUEINLARGE do ER

[!include [banner](../includes/banner.md)]

A função `VALUEINLARGE` determina se a entrada especificada do tipo *Int64* ou *Inteiro* corresponde a qualquer valor de um item especificado na lista especificada. A função retorna um valor *Booliano* de **TRUE** se a entrada especificada corresponder ao resultado da execução da expressão especificada para pelo menos um registro da lista especificada. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. Para compreender a diferença com a função `VALUEIN`, consulte a seção [Observação de uso](#usage_note) posteriormente neste artigo.

## <a name="syntax"></a>Sintaxe

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a>Argumentos

`input`: *Campo*

O caminho válido de um item da fonte de dados do tipo *Lista de registros*. O valor desse item será correspondido.

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`list item expression`: *Expressão*

Uma expressão condicional válida que aponta para ou contém um único campo da lista especificada que deve ser usado na correspondência.

## <a name="return-values"></a>Valores de retorno

*Booleano*

O valor *Booliano* resultante.

## <a name=""></a><a name="usage_note">Notas de uso</a>

Quando a entrada especificada representa um tipo *Int64* ou *Inteiro* de um item da fonte de dados, a chamada para a qual é traduzível para uma instrução SQL direta, a lista especificada é convertida em uma tabela SQL temporária e a correspondência é realizada no banco de dados executando uma única consulta `EXISTS JOIN`. Caso contrário, essa função funcionará como a função [`VALUEIN`](er-functions-logical-valuein.md).

Quando a entrada especificada representa um item de fonte de dados criado como um item diferente do tipo *Int64* e *Inteiro*, ocorre um erro no tempo de design informando que a função `VALUEINLARGE` não é aplicável à expressão de ER configurada.

Quando expressão da função `VALUEINLARGE` é executada e mais de uma tabela temporária é usada no escopo dessa execução, ocorre um erro de tempo de execução.

## <a name="example"></a>Exemplo

Você define as seguintes fontes de dados no mapeamento de modelo:

- A fonte de dados **In** do tipo *Registros de tabela*.
    - Essa fonte de dados se refere à tabela **Intrastat**.
    - A opção **Interempresarial** é definida como **Não**.
- A fonte de dados **InMemory** do tipo *Campo calculado*.
    - Essa fonte de dados contém a expressão `WHERE (In, In.Port <> "")`.
- A fonte de dados **InFiltered** do tipo *Campo calculado*.
    - Essa fonte de dados contém a expressão `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.

Quando a fonte de dados **InFiltered** é chamada no contexto da empresa **DEMF**, uma nova tabela temporária é criada no banco de dados do aplicativo, a lista de códigos de identificação de registros coletada na memória é inserida nesta tabela, e a instrução SQL a seguir é gerada para retornar os registros filtrados da **Intrastat**.

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)

[Funções VALUEIN](er-functions-logical-valuein.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
