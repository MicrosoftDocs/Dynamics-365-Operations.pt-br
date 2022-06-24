---
title: Função de ER SESSIONTODAY
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) SESSIONTODAY é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 755dc867d518da9cb4511b2daeb4832a3c6d90f9
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888220"
---
# <a name="sessiontoday-er-function"></a>Função de ER SESSIONTODAY

[!include [banner](../includes/banner.md)]

A função `SESSIONTODAY` retorna um valor de *Data* que representa a data atual da sessão do aplicativo.

## <a name="syntax"></a>Sintaxe

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a>Valores de retorno

*Data*

O valor de data resultante.

## <a name="example"></a>Exemplo

`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]