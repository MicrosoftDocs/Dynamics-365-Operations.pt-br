---
title: Lista de funções ER na categoria de data e hora
description: Este artigo fornece informações sobre as funções de data e hora que são compatíveis no relatório eletrônico (ER).
author: NickSelin
ms.date: 09/09/2021
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
ms.openlocfilehash: e6e15d143bad016883f03ecf0125ce9429215a71
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880221"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Lista de funções ER na categoria de data e hora

[!include [banner](../includes/banner.md)]

Funções de data e hora de relatório eletrônico (ER) podem ser usadas para extrair informações de valores de data e hora e para realizar operações nelas. Este artigo fornece um resumo dessas funções.

## <a name="list-of-supported-functions"></a>Lista de funções com suporte

| Função | Descrição |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Esta função retorna um valor *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* que é o número especificado de dias antes ou depois de uma data inicial especificada. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Esta função retorna um valor *DateTime* convertido de um determinado valor de data/hora em um fuso horário para um valor de data/hora em outro fuso horário. |
| [DateFormat](er-functions-datetime-dateformat.md) | Essa função retorna um valor de *[Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string)* que apresenta um valor de data determinado como texto no formato especificado e em uma cultura opcionalmente especificada. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Essa função retorna um valor de *Cadeia de caracteres* que apresenta um valor de data/hora determinado como texto no formato especificado e em uma cultura opcionalmente especificada. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Essa função retorna um valor de *DateTime* que é convertido de um valor de texto determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data/hora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Esta função retorna um valor *DateTime* convertido de um determinado valor de data para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Essa função retorna um valor de *[Data](er-formula-supported-data-types-primitive.md#date)* que é convertido de um valor de texto determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | Essa função retorna um valor *[Inteiro](er-formula-supported-data-types-primitive.md#integer)* que representa o número de dias entre 1º de janeiro e a data especificada. |
| [Dias](er-functions-datetime-days.md) | Essa função retorna um valor *Inteiro* que representa o número de dias entre uma data especificada e uma segunda data especificada. |
| [Now](er-functions-datetime-now.md) | Essa função retorna um valor de *DateTime* que representa a data e a hora atual do servidor do aplicativo. |
| [NullDate](er-functions-datetime-nulldate.md) | Essa função retorna um valor de *Data* que representa a data **nula** (1º de janeiro de 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Essa função retorna um valor de *DateTime* que representa o valor de data/hora **nulo** (1º de janeiro de 1900) no Tempo Universal Coordenado. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Essa função retorna um valor de *DateTime* que representa a data e a hora atual da sessão do aplicativo. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Essa função retorna um valor de *Data* que representa a data atual da sessão do aplicativo. |
| [Hoje](er-functions-datetime-today.md) | Essa função retorna um valor de *Data* que representa a data atual do servidor do aplicativo. |
| [WeekNum](er-functions-datetime-weeknum.md) | Esta função retorna um valor *Inteiro* que representa a semana do ano. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
