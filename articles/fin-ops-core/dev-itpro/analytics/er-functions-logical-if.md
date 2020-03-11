---
title: Função de ER IF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) IF é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 198210f15e75de761dbb03e5087ba7c77a95721a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041736"
---
# <a name="IF">Função de ER IF</a>

[!include [banner](../includes/banner.md)]

A função `IF` retorna o primeiro valor especificado se a condição especificada for atendida. Caso contrário, ele retorna o segundo valor especificado. O valor retornado pode ser um valor de qualquer um dos tipos de dados com suporte.

## <a name="syntax"></a>Sintaxe

```vb
IF (condition, first value, second value) as any of the supported data types
```

## <a name="arguments"></a>Argumentos

`condition`: *Booliano*

Uma expressão condicional válida que deve ser testada.

`first value`: *Qualquer um dos tipos de dados com suporte*

O resultado que será retornado se a condição for atendida.

`second value`: *Qualquer um dos tipos de dados com suporte*

O resultado que será retornado se a condição não for atendida.

## <a name="return-values"></a>Valores de retorno

*Qualquer um dos tipos de dados com suporte*

O valor resultante de qualquer um dos tipos de dados com suporte.

## <a name="usage-notes"></a>Notas de uso

Os argumentos `first value` e `second value` devem ser especificados usando o mesmo tipo de dados. Uma exceção é gerada no momento do design se os tipos de dados dos valores configurados não forem correspondentes.

Se o primeiro e o segundo valor forem valores do tipo de dados *Contêiner (registro)* ou *Lista de registros*, o resultado terá somente os campos existentes nos dois valores.

## <a name="example"></a>Exemplo

`IF (1=2, "condition is met", "condition is not met")` retorna a cadeia de caracteres **"condição não atendida"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções lógicas](er-functions-category-logical.md)
