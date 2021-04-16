---
title: Função de ER NULLDATETIME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLDATETIME é usada.
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
ms.openlocfilehash: f7282b7c161b6e183186ba81e6bcf7b34ce6e612
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746810"
---
# <a name="nulldatetime-er-function"></a>Função de ER NULLDATETIME

[!include [banner](../includes/banner.md)]

A função `NULLDATETIME` retorna um valor de *DateTime* que representa o valor de data/hora **nulo** (1º de janeiro de 1900) no Tempo Universal Coordenado (Horário do Meridiano de Greenwich \[GMT\]).

## <a name="syntax"></a>Sintaxe

```vb
NULLDATETIME ()
```

## <a name="return-values"></a>Valores de retorno

*Data/Hora*

O valor de data/hora resultante.

## <a name="example"></a>Exemplo

`DATETIMEFORMAT( NULLDATETIME(), "O")` retorna o valor de cadeia de caracteres **1900-01-01T00:00:00.0000000+00:00** quando é chamada durante um processo iniciado por um usuário de aplicativo com o valor de fuso horário **(GMT) Tempo Universal Coordenado** na seção **Preferências de idioma e país/região**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]