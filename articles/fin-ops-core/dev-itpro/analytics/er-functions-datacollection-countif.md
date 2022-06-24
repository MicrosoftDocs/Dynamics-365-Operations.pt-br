---
title: Função COUNTIF ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico COUNTIF é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 60a17d6a5e089cc6006a5fb3493654963de1b392
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906848"
---
# <a name="countif-er-function"></a>Função COUNTIF ER

[!include [banner](../includes/banner.md)]

A função `COUNTIF` retorna um valor *Inteiro* que representa o número de elementos de formato que foram coletados quando os elementos de formato foram usados para gerar um documento de saída durante a execução do formato, e que satisfaçam a condição especificada. A condição consiste em um intervalo de chaves e um valor de chave.

## <a name="syntax"></a>Sintaxe

```vb
COUNTIF (condition range, condition value)
```

## <a name="arguments"></a>Argumentos

`condition range`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Nome da chave de dados coletada** de um componente de formato de relatório eletrônico (ER).

`condition value`: *Cadeia de caracteres*

Um valor retornado pela expressão que foi configurada na propriedade **Valor da chave de dados coletada** de um componente de formato de ER.

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

As propriedade **Nome da chave de dados coletada** e **Valor da chave de dados coletada** podem ser configuradas para um componente **Sequência** ou um componente **Elemento XML** de um formato de ER que está no componente **Arquivo \\ comum** onde a opção **Coletar detalhes de saída** está ativada.

Esta função retorna um valor de **0** (zero) quando a opção **Coletar detalhes de saída** do componente **Arquivo \\ comum** está desativada.

No argumento `condition range`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

No argumento `condition value`, o caractere curinga **"\*"** pode ser usado para representar quaisquer caracteres múltiplos.

## <a name="example"></a>Exemplo

Para obter informações sobre como usar esta função, consulte o guia de tarefas [ER Usar dados de saída do formato contagem e soma](tasks/er-format-counting-summing-1.md), que faz parte do processo de negócios **Adquirir/Desenvolver componentes de solução/serviço de TI**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de coleta de dados](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]