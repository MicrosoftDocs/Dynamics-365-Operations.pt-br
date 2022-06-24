---
title: Função de ER JSONVALUE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) JSONVALUE é usada.
author: NickSelin
ms.date: 10/25/2021
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
ms.openlocfilehash: 7deaed83959f033d11333efb5a2b398cbe57076d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8909490"
---
# <a name="jsonvalue-er-function"></a>Função de ER JSONVALUE

[!include [banner](../includes/banner.md)]

A função `JSONVALUE` analisa os dados no formato JSON (JavaScript Object Notation) que são acessados no caminho especificado e extrai um valor escalar que tem a ID especificada. Em seguida, ela retorna o valor escalar extraído como um valor de *Cadeia de caracteres*.

## <a name="syntax"></a>Sintaxe

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres* que contém dados JSON.

`path`: *Cadeia de caracteres*

O identificador de um valor escalar de dados JSON. Use uma barra (/) para separar os nomes de nós JSON relacionados. Use a notação de colchete (\[\]) para especificar o índice de um valor específico em uma matriz JSON. Observe que a numeração baseada em zero é usada para este índice.

## <a name="return-values"></a>Valores de retorno

*Sequência de caracteres*

O valor de texto resultante.

## <a name="example-1"></a>Exemplo 1

A fonte de dados **JsonField** contém os seguintes dados no formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. Nesse caso, a expressão `JSONVALUE (JsonField, "BuildNumber")` retorna o seguinte valor do tipo de dados *Cadeia de caracteres*: **"7.3.1234.1"**.

## <a name="example-2"></a>Exemplo 2

A fonte de dados **JsonField** do tipo *Campo calculado* contém esta expressão: `"{""workers"": [ {""name"": ""Adam"", ""age"": 30, ""emails"": [""AdamS@Contoso.com"", ""AdamS@Hotmail.com"" ]}, { ""name"": ""John"", ""age"": 21, ""emails"": [""JohnS@Contoso.com"", ""JohnS@Aol.com""]}]}"`

Esta expressão configurada para retornar um valor [*Cadeia de caracteres*](er-formula-supported-data-types-primitive.md#string) que representa os seguintes dados no formato JSON.

```json
{
    "workers": [
        {
            "name": "Adam",
            "age": 30,
            "emails": [ "AdamS@Contoso.com", "AdamS@Hotmail.com" ]
        },
        {
            "name": "John",
            "age": 21,
            "emails": [ "JohnS@Contoso.com", "JohnS@Aol.com" ]
        }
    ]
}
```

Nesse caso, a expressão `JSONVALUE(json, "workers/[1]/emails/[0]")` retorna o seguinte valor do tipo de dados *Cadeia de caracteres*: `JohnS@Contoso.com`.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
