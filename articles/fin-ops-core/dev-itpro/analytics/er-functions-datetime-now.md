---
title: Função NOW ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico NOW é usada.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: c93aa2a0e3f6aa07ab9e843d3c5f11c5265e8c40
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746858"
---
# <a name="now-er-function"></a>Função NOW ER

[!include [banner](../includes/banner.md)]

A função `NOW` retorna um valor de *DateTime* que representa a data e a hora atual do servidor do aplicativo.

## <a name="syntax"></a>Sintaxe

```vb
NOW ()
```

## <a name="return-values"></a>Valores de retorno

*Data/Hora*

O valor de data/hora resultante.

## <a name="example"></a>Exemplo

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]