---
title: Função de ER INDEX
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) INDEX é usada.
author: NickSelin
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
ms.openlocfilehash: 14f10359a3f20fb9d23639babce764b9ef64243d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750451"
---
# <a name="index-er-function"></a>Função de ER INDEX

[!include [banner](../includes/banner.md)]

A função `INDEX` retorna um valor de *Contêiner (registro)* que é selecionado usando o índice numérico especificado na lista especificada. Se o índice estiver fora do intervalo dos registros na lista especificada, uma exceção será gerada.

## <a name="syntax"></a>Sintaxe

```vb
INDEX (list, index)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

`index`: *Inteiro*

Um índice numérico que indica a posição do registro desejado na lista especificada.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="example-1"></a>Exemplo 1

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `DS.Value` retornará o valor de texto **"B"** para o segundo registro dessa lista de registros. A expressão `INDEX (SPLIT ("A|B|C", "|"), 2).Value` também retorna o valor de texto **"B"**.

## <a name="example-2"></a>Exemplo 2

Se você inserir a fonte de dados **DS** do tipo *Campo calculado* e ela contiver a expressão `SPLIT ("A|B|C", "|")`, a expressão `INDEX (SPLIT ("A|B|C", "|"), 4).Value` gerará uma exceção no tempo de execução.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]