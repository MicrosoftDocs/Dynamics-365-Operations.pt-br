---
title: Função LISTDISTINCT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTDISTINCT é usada.
author: NickSelin
manager: kfend
ms.date: 7/30/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2333cfc21a16a5905acadd590982020fdf878330
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682258"
---
# <a name="listdistinct-er-function"></a>Função LISTDISTINCT ER

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

A função `LISTDISTINCT` calcula a expressão especificada como um seletor para cada registro da lista especificada. Ela retorna um novo valor *Lista de registros* que contém um único registro para cada valor de seletor único.

## <a name="syntax"></a>Sintaxe

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`selector`: *tipo de dados primitivos*

Uma expressão válida que é usada para calcular um valor de seletor para cada registro na lista especificada.

Os seguintes tipos de dados têm suporte para este parâmetro:

- Booleano
- Data 
- Data e Hora
- Guid
- Inteiro
- Int64
- Real
- Sequência de caracteres

## <a name="return-values"></a>Valores de retorno

*Registrar lista*

A lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

A estrutura da lista criada corresponde à estrutura da lista especificada.

O mesmo valor do seletor pode ser calculado para vários registros na lista especificada. Nesse caso, os valores de campo do registro correspondente na lista criada são iguais aos valores do primeiro registro da lista especificada para as quais o valor do seletor é calculado.

A execução dessa função é feita em qualquer fonte de dados de [relatório eletrônico (ER)](general-electronic-reporting.md) do tipo de *Lista de registros* presente na memória.

A fonte de dados **GROUPBY** também pode ser usada para gerar a lista de registros para a qual é calculado o seletor que tem valores distintos. No entanto, de uma perspectiva de desempenho e de consumo de memória, convém usar a função `LISTDISTINCT` do que a fonte de de dados **GROUPBY**, pois a execução da função é realizada na memória.

## <a name="example"></a>Exemplo

O exemplo a seguir mostra como é possível obter a lista de números de conta de cliente únicos para os quais pelo menos uma fatura de venda ou de projeto foi emitida durante um período específico.

1. Insira a fonte de dados **SalesInvoice** do tipo `Record list` que se refere à tabela do aplicativo **CustInvoiceJour** e filtre as faturas de venda para períodos específicos.

    O campo `InvoiceAccount` dessa fonte de dados retorna o número da conta de um cliente faturado.

2. Insira a fonte de dados **ProjectInvoice** do tipo `Record list` que se refere à tabela do aplicativo **ProjInvoiceJour** e filtre as faturas do projeto para períodos específicos.

    O campo `InvoiceAccount` dessa fonte de dados retorna o número da conta de um cliente faturado.

3. Configura a fonte de dados **AllInvoices** do tipo `Calculated field` que contém a expressão `LISTJOIN(SalesInvoice, ProjectInvoice)`.

    Essa fonte de dados retorna a lista unida de faturas de venda e de projeto.

4. Configure a fonte de dados **InvoicedCustomer** do tipo `Record list` que contém a expressão `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.

    Essa fonte de dados retorna uma nova lista que contém um único registro para cada cliente único que foi faturado durante o período definido. O campo `InvoiceAccount` desta lista contém um número de conta de cliente.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]