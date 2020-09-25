---
title: Função de ER CASE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CASE é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 605bd50005ee4e5866a5be9e16df6da3139ad19c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744758"
---
# <a name="case-er-function"></a>Função de ER CASE

[!include [banner](../includes/banner.md)]

A função `CASE` avalia o valor da expressão especificada em relação às opções alternativas especificadas e retorna o resultado da primeira opção igual ao valor dessa expressão. Caso contrário, ela retorna o resultado padrão opcional, se um resultado padrão for especificado como o último argumento da função chamada não precedida por uma opção. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.

## <a name="syntax"></a>Sintaxe

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a>Argumentos

`expression`: *Tipo de dados primitivo* (booliano, numérico ou texto)

Uma expressão válida que retorna um valor do tipo de dados primitivo.

`option 1`: *Tipo de dados primitivo* (booliano, numérico ou texto)

Uma expressão válida que retorna um valor do mesmo tipo de dados primitivo que o argumento `expression` da função chamada. Esse argumento é obrigatório.

`result 1`: *Qualquer um dos tipos de dados com suporte*

O resultado retornado que corresponde à opção anterior. Esse argumento é obrigatório.

`option N`: *Tipo de dados primitivo* (booliano, numérico ou texto)

Uma expressão válida que retorna um valor do mesmo tipo de dados primitivo que o argumento `expression` da função chamada. Esse argumento é opcional.

`result N`: *Qualquer um dos tipos de dados com suporte*

O resultado retornado que corresponde à opção anterior. Esse argumento é opcional.

`default result`: *Qualquer um dos tipos de dados com suporte*

O resultado que deve ser retornado se não houver correspondência. Esse argumento é opcional.

## <a name="return-values"></a>Valores de retorno

*Qualquer um dos tipos de dados com suporte*

O valor resultante de qualquer um dos tipos de dados com suporte.

## <a name="usage-notes"></a>Notas de uso

Uma exceção é gerada no tempo de execução se não houver correspondência e um resultado padrão opcional não estiver definido.

Todos os resultados devem ser especificados usando o mesmo tipo de dados. Uma exceção é gerada no momento do design se os tipos de dados dos resultados configurados não forem correspondentes.

Se o primeiro valor de resultado e o *N*º valor de resultado forem valores do tipo de dados *Contêiner (registro)* ou *Lista de registros*, o resultado terá somente os campos existentes nos dois valores.

## <a name="example"></a>Exemplo

`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` retorna a cadeia de caracteres **"WINTER"** se a data atual da sessão do aplicativo estiver entre outubro e dezembro. Caso contrário, retorna uma cadeia de caracteres em branco.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
