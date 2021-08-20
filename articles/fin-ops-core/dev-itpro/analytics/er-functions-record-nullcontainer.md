---
title: Função de ER NULLCONTAINER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLCONTAINER é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: 13159d9d7c8d1871886beb3cb1938ca8b0097e0efb6f10a9d1b229c49b9ff947
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738567"
---
# <a name="nullcontainer-er-function"></a>Função de ER NULLCONTAINER

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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]