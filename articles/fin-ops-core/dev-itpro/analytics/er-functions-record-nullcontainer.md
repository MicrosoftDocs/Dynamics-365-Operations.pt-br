---
title: Função de ER NULLCONTAINER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLCONTAINER é usada.
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
ms.openlocfilehash: ea71bfc4b30164fd32e804bf83a46c49cd18d155
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041460"
---
# <a name="NULLCONTAINER">Função de ER NULLCONTAINER</a>

[!include [banner](../includes/banner.md)]

A função `NULLCONTAINER` retorna um valor de *Contêiner (registro)* nulo que tem a mesma estrutura do registro ou da lista de registros especificada.

## <a name="syntax"></a>Sintaxe

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a>Argumentos

`list`: *Lista de registros* ou *Contêiner (registro)*

O caminho válido de uma fonte de dados do tipo *Lista de registros* ou *Contêiner (registro)*.

## <a name="return-values"></a>Valores de retorno

*Contêiner (registro)*

O valor de registro resultante.

## <a name="usage-notes"></a>Notas de uso

> [!NOTE] 
> Esta função é obsoleta. Em vez dela, use a função `EMPTYRECORD`. Para obter mais informações, consulte [EMPTYRECORD](er-functions-record-emptyrecord.md).

## <a name="example"></a>Exemplo

`NULLCONTAINER (SPLIT ("abc", 1))` retorna um novo registro vazio que tem a mesma estrutura da lista retornada pela função `SPLIT`. Para obter mais informações, consulte [SPLIT](er-functions-list-split.md).

## <a name="additional-resources"></a>Recursos adicionais

[Funções de registro](er-functions-category-record.md)
