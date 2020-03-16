---
title: Função de ER GUIDVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GUIDVALUE é usada.
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
ms.openlocfilehash: a7b8c782aff488a433c40a49ab7f4fe2d0e944e4
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041141"
---
# <a name="GUIDVALUE">Função de ER GUIDVALUE</a>

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
