---
title: Lista de funções ER na categoria de lista
description: Este tópico fornece informações sobre as funções de lista que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
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
ms.openlocfilehash: b98ad6c2c7eb2881ede83b9bd2d02aac71efc4c9
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561677"
---
# <a name="list-of-er-functions-in-the-list-category"></a>Lista de funções ER na categoria de lista

[!include [banner](../includes/banner.md)]

As funções de lista de relatório eletrônico (ER) podem ser usadas para extrair informações de e executar operações em, fontes de dados dos tipos de dados *Lista de registros* e *Contêiner (registro)*. Este tópico fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [AllItems](er-functions-list-allitems.md)                 | Essa função é executada como uma seleção na memória. Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado. |
| [AllItemsQuery](er-functions-list-allitemsquery.md)       | Essa função é executada como uma consulta SQL associada. Ela retorna um novo valor de *Lista de registros* simplificado que consiste em uma lista de registros que representam todos os itens correspondentes ao caminho especificado. |
| [Contagem](er-functions-list-count.md)                       | Essa função retorna um valor *Inteiro* que representa o número de registros na lista especificada, se a lista não estiver vazia. Se a lista estiver vazia, essa função retornará **0** (zero). |
| [EmptyList](er-functions-list-emptylist.md)               | Essa função retorna um valor de *Lista de registros vazio* usando a lista especificada como uma fonte para a estrutura da lista.|
| [Enumerar](er-functions-list-enumerate.md)               | Essa função retorna um novo valor de *Lista de registros* que consiste em registros enumerados da lista especificada. |
| [Filtro](er-functions-list-filter.md)                     | Essa função retorna a lista especificada como um valor de *Lista de registros* após a consulta ser alterada, de forma que ela filtre para a condição especificada. |
| [Primeiro](er-functions-list-first.md)                       | Essa função retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se essa lista não estiver vazia. Se a lista estiver vazia, essa função gerará uma exceção. |
| [FirstOrNull](er-functions-list-firstornull.md)           | Essa função retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se esse registro não estiver vazio. Se o registro estiver vazio, essa função retornará um valor de *Contêiner (registro)* nulo. |
| [Índice](er-functions-list-index.md)                       | Essa função retorna um valor de *Contêiner (registro)* que é selecionado usando o índice numérico especificado na lista especificada. Se o índice estiver fora do intervalo dos registros na lista especificada, essa função gerará uma exceção. |
| [IsEmpty](er-functions-list-isempty.md)                   | Essa função retorna um valor *Booliano* de **TRUE** se a lista especificada não contiver registros. Caso contrário, ela retorna um valor *Booliano* de **FALSE**. |
| [Lista](er-functions-list-list.md)                         | Essa função retorna um valor de *Lista de registros* que consiste em uma nova lista criada a partir dos argumentos especificados.|
| [ListDistinct](er-functions-list-listdistinct.md)         | Esta função calcula a expressão especificada como um seletor para cada registro da lista especificada. Ela retorna um novo valor *Lista de registros* que contém um único registro para cada valor de seletor único.|
| [ListJoin](er-functions-list-listjoin.md)                 | Essa função retorna um valor de *Lista de registros* que representa uma nova lista associada criada dos argumentos especificados.|
| [ListOfFields](er-functions-list-listoffields.md)         | Essa função retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento especificado do tipo *Enumeração* ou *Contêiner (registro)*. |
| [ListOfFirstItem](er-functions-list-listoffirstitem.md)   | Essa função retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.|
| [OrderBy](er-functions-list-orderby.md)                   | Essa função retorna a lista especificada como um valor de *Lista de registros* após ela ser classificada de acordo com os argumentos especificados. Esses argumentos podem ser definidos como expressões. |
| [Reverter](er-functions-list-reverse.md)                   | Essa função retorna a lista especificada como um valor de *Lista de registros* na ordem de classificação inversa. |
| [Dividir](er-functions-list-split.md)                       | Essa função divide a cadeia de caracteres de entrada especificada em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*. |
| [SplitList](er-functions-list-splitlist.md)               | Essa função divide a lista especificada em sublistas (ou lotes) e cada uma delas contém o número de registros especificado. Em seguida, ela retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes. |
| [SplitListByLimit](er-functions-list-splitlistbylimit.md) | Essa função divide a lista especificada em uma nova lista de sublistas (lotes). O número de registros em cada lote é calculado dinamicamente. Em seguida, a função retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes. |
| [StringJoin](er-functions-list-stringjoin.md)             | Essa função retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado da lista especificada. Os valores podem ser separados pelo delimitador especificado. |
| [Onde](er-functions-list-where.md)                       | Essa função retorna a lista especificada como um valor de *Lista de registros* após ser filtrada de acordo com a condição especificada. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]