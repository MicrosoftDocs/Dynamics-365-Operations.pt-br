---
title: Função SUMIF ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) SUMIF é usada.
author: NickSelin
ms.date: 04/27/2020
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
ms.openlocfilehash: 2b488b00e10b749ff67a7eb5b18b5ca114e55a43
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879852"
---
# <a name="sumif-er-function"></a>Função SUMIF ER

[!include [banner](../includes/banner.md)]

A função `SUMIF` retorna um valor *Real* que representa a soma de valores que foram retornados por associações de elementos de formato e coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada. A condição consiste em um intervalo de chaves e um valor de chave.

## <a name="syntax"></a>Sintaxe

```vb
SUMIF (key name for summing, condition range, condition value)
```

## <a name="arguments"></a>Argumentos

`key name for summing`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletados** do componente de formato de relatório eletrônico (ER) para o qual o valor da associação deve ser usado para fins de soma.

A propriedade **Valor da chave de dados coletada** pode ser configurada para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

## <a name="return-values"></a>Valores de retorno

*Real*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.

No argumento `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

No argumento `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

## <a name="example"></a>Exemplo

Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.

Para obter mais informações e exemplos sobre como usar essa função, consulte [Adiar a execução de elementos de sequência nos formatos ER](er-defer-sequence-element.md#Example) e [Adiar a execução de elementos XML nos formatos ER](er-defer-xml-element.md#Example).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de coleta de dados](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]