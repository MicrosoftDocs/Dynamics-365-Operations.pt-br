---
title: Função de ER ALLITEMSQUERY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ALLITEMSQUERY é usada.
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
ms.openlocfilehash: 37546fccf804a4522638147d39206997e8c0c24c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745360"
---
# <a name="allitemsquery-er-function"></a>Função de ER ALLITEMSQUERY

[!include [banner](../includes/banner.md)]

A função `ALLITEMSQUERY` é executada como uma consulta SQL associada. Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado.

## <a name="syntax"></a>Sintaxe

```vb
ALLITEMSQUERY (path)
```

## <a name="arguments"></a>Argumentos

`path`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*. Ele deve conter pelo menos uma relação.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

O caminho especificado deve ser definido como um caminho de fonte de dados válido de um elemento da fonte de dados do tipo *Lista de registros*. Ele também deve conter pelo menos uma relação. Os elementos de dados, como a *Cadeia de caracteres* e a *Data* do caminho, devem gerar um erro no construtor de expressões de relatório eletrônico (ER) no momento do design.

Quando esta função é aplicada a fontes de dados do tipo *Lista de registros* que se referem a um objeto de aplicativo que pode ser chamado diretamente usando o SQL (por exemplo, uma tabela, entidade ou consulta), ela é executada como uma consulta SQL associada. Caso contrário, ela é executada na memória como a função [ALLITEMS](er-functions-list-allitems.md).

## <a name="example"></a>Exemplo

Você define as seguintes fontes de dados no mapeamento de modelo:

- Uma fonte de dados **CustInv** do tipo *Registros de tabela* que se refere à tabela CustInvoiceTable
- Uma fonte de dados **FilteredInv** do tipo *Campo calculado* que contém a expressão `FILTER (CustInv, CustInv.InvoiceAccount = "US-001")`
- Uma **JourLines** do tipo *Campo calculado* que contém a expressão `ALLITEMSQUERY ( FilteredInv.'<Relations'.CustInvoiceJour.'<Relations'.CustInvoiceTrans)`

Ao executar o mapeamento de modelo para chamar a fonte de dados **JourLines**, a seguinte instrução SQL é executada:

```sql
SELECT ... FROM CUSTINVOICETABLE T1 CROSS JOIN CUSTINVOICEJOUR T2 CROSS JOIN
CUSTINVOICETRANS T3 WHERE...
```

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
