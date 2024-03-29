---
title: Função de ER GUIDVALUE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) GUIDVALUE é usada.
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: cb706a3607b4443c283a91c42c4dc1c389972e44
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285175"
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
