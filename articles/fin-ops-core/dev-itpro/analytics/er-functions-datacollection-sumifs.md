---
title: Função SUMIFS ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SUMIFS é usada.
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
ms.openlocfilehash: ff5ad3371a6e18ca1a3ee855e3b35f51f7513ef0
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564750"
---
# <a name="sumifs-er-function"></a>Função SUMIFS ER

[!include [banner](../includes/banner.md)]

A função `SUMIFS` retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam as condições especificadas. Cada condição consiste em um intervalo de chaves e um valor de chave.

## <a name="syntax"></a>Sintaxe

```vb
SUMIFS (key name for summing, condition 1 range, condition 1 value[, condition 2 range, condition 2 value, …, condition N range, condition N value])
```

## <a name="arguments"></a>Argumentos

`key name for summing`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletados** do componente de formato de relatório eletrônico (ER) para o qual o valor da associação deve ser usado para fins de soma.

A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Numérico** ou um componente **Cadeia de caracteres** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

`condition 1 range`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER. Esse argumento é obrigatório.

A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

`condition 1 value`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER. Esse argumento é obrigatório.

A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

`condition N range`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de ER. Esses argumentos adicionais são opcionais.

A propriedade **Nome da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

`condition N value`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER. Esses argumentos adicionais são opcionais.

A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.

Nos argumentos `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

Nos argumentos `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

## <a name="example"></a>Exemplo

Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de coleta de dados](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]