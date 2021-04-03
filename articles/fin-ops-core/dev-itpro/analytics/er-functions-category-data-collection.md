---
title: Lista de funções ER na categoria de coleção de dados
description: Este tópico fornece informações sobre as funções de coleção de dados que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba3a1f031a4a98592081b04a4128450aeb8218ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561725"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a>Lista de funções ER na categoria de coleção de dados

[!include [banner](../includes/banner.md)]

As funções de coleta de dados de relatório eletrônico (ER) são usadas para contabilizar e somar em um formato ER que está sendo executado, com base nos dados da saída que já foram gerados no formato **Texto** ou **XML**. Essa abordagem é usada para ajudar a melhorar o desempenho de um formato ER que é executado, inserir valores de totais acumulados em documentos gerados e para outros fins. Este tópico fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [CollectedList](er-functions-datacollection-collectedlist.md) | Essa função retorna um valor de *Lista de registros* que contém a lista de valores que foram retornados pela propriedade **Valor da chave de dados coletada** de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas. Cada condição consiste em um intervalo de chaves e um valor de chave. |
| [CountIF](er-functions-datacollection-countif.md) | Essa função retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada. A condição consiste em um intervalo de chaves e um valor de chave. |
| [CountIFs](er-functions-datacollection-countifs.md) | Essa função retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas. Cada condição consiste em um intervalo de chaves e um valor de chave. |
| [FormatElementName](er-functions-datacollection-formatelementname.md) | Esta função retorna um valor de *Cadeia de caracteres* que representa o nome do elemento do formato ER atual. |
| [SumIF](er-functions-datacollection-sumif.md) | Essa função retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada. A condição consiste em um intervalo de chaves e um valor de chave. |
| [SumIFs](er-functions-datacollection-sumifs.md) | Essa função retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas. Cada condição consiste em um intervalo de chaves e um valor de chave. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]