---
title: Função de ER GUIDVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GUIDVALUE é usada.
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746378"
---
# <a name="guidvalue-er-function"></a>Função de ER GUIDVALUE

[!include [banner](../includes/banner.md)]

A função `GUIDVALUE` converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*.

## <a name="syntax"></a>Sintaxe

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a>Argumentos

`input`: *Cadeia de caracteres*

O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres*.

## <a name="return-values"></a>Valores de retorno

*GUID*

O valor do Identificador Global Exclusivo (GUID) resultante.

## <a name="usage-notes"></a>Notas de uso

Para fazer uma conversão na direção oposta (isto é, para converter a entrada especificada do tipo de dados *GUID* em um item de dados do tipo *Cadeia de caracteres*), você pode usar a função [TEXT](er-functions-text-text.md).

## <a name="example"></a>Exemplo

Você define as seguintes fontes de dados no mapeamento de modelo:

- Uma fonte de dados **myID** do tipo *Campo calculado* que contém a expressão `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Uma fonte de dados **Usuários** do tipo *Registros de tabela* que se refere à tabela UserInfo

Em seguida, você pode usar uma expressão como `FILTER (Users, Users.objectId = myID)` para filtrar a tabela UserInfo pelo campo **objectId** do tipo de dados *GUID*.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]