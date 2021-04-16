---
title: Função de ER JSONVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) JSONVALUE é usada.
author: NickSelin
ms.date: 12/11/2019
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
ms.openlocfilehash: e8336e43a236e3f3b875fb3cb81bc139507673c2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746354"
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

O identificador de um valor escalar de dados JSON.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor de texto resultante.

## <a name="example"></a>Exemplo

A fonte de dados **JsonField** contém os seguintes dados no formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**. Nesse caso, a expressão `JSONVALUE (JsonField, "BuildNumber")` retorna o seguinte valor do tipo de dados *Cadeia de caracteres*: **"7.3.1234.1"**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]