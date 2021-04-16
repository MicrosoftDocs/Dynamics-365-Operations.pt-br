---
title: Função de ER TODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TODAY é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 45ee4282acf4d6a5febe4b74b6955410e73e86a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746738"
---
# <a name="today-er-function"></a>Função de ER TODAY

[!include [banner](../includes/banner.md)]

A função `TODAY` retorna um valor de *Data* que representa a data atual do servidor do aplicativo.

## <a name="syntax"></a>Sintaxe

```xpp
TODAY ()
```

## <a name="return-values"></a>Valores de retorno

*Data*

O valor de data resultante.

## <a name="example"></a>Exemplo

`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]