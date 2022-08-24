---
title: Função de NEWGUID
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) NEWGUID é usada.
author: kfend
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-09-08
ms.dyn365.ops.version: AX 10.0.23
ms.custom: ''
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 381dbcbe816c189c1966ffe962020d5aa2b1f3eb
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274762"
---
# <a name="newguid-er-function"></a>Função de NEWGUID

[!include [banner](../includes/banner.md)]

A função `NEWGUID` gera um novo identificador global exclusivo (GUID) e o retorna como um valor *[GUID](er-formula-supported-data-types-primitive.md#guid)*.

## <a name="syntax"></a>Sintaxe

```vb
NEWGUID ()
```

## <a name="return-values"></a>Valores de retorno

*GUID*

O valor GUID resultante.

## <a name="example"></a>Exemplo

`NEWGUID()` sempre retorna um novo valor *GUID*, como **3afcf7ff-af10-ec11-b6e6-000d3a13209e**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de texto](er-functions-category-text.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
