---
title: Função de ER FIRSTORNULL
description: Este tópico explica como a função de relatório eletrônico (ER) FIRSTORNULL é usada.
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: 86c8a0ae21ffeb6268efbbd198f7c709c2ad54f6
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042104"
---
# <a name="FIRSTORNULL">Função de ER FIRSTORNULL</a>

[!include [banner](../includes/banner.md)]

A função `FIRSTORNULL` retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se esse registro não estiver vazio. Se o registro estiver vazio, essa função retornará um valor de *Contêiner (registro)* nulo.

## <a name="syntax"></a>Sintaxe

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros*

O caminho válido de uma fonte de dados do tipo *Lista de registros*.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="example"></a>Exemplo

A expressão `FIRSTORNULL(SPLIT("",1)).Value` retorna uma cadeia de caracteres vazia (**""**).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de listagem](er-functions-category-list.md)
