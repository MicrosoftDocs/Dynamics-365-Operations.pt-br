---
title: Função de ER NULLCONTAINER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) NULLCONTAINER é usada.
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
ms.openlocfilehash: 8efa4cce3bda1707eff052e882b74e3da9542353
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291754"
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
