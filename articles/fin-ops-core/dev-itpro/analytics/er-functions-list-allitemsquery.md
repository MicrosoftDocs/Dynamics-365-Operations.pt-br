---
title: Função de ER ALLITEMSQUERY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ALLITEMSQUERY é usada.
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
ms.openlocfilehash: 56ac956cdfe28d282b8a80d7caec34a50eca5dbe
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5559594"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]