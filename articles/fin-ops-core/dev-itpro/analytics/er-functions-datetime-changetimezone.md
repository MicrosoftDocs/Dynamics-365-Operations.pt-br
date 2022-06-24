---
title: Função de ER CHANGETIMEZONE
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) CHANGETIMEZONE é usada.
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: be94f57cfcb6115ea386a279c379662f7d401d11
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8903575"
---
# <a name="changetimezone-er-function"></a>Função de ER CHANGETIMEZONE

[!include [banner](../includes/banner.md)]

A função `CHANGETIMEZONE` retorna um valor *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]) convertido de um determinado valor de data em um fuso horário para um valor de data/hora em outro fuso horário.

## <a name="syntax"></a>Sintaxe

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argumentos

`datetime`: *DateTime*

Um valor de data/hora no fuso horário do Tempo Universal Coordenado que representa o valor de data/hora a ser convertido.

`base time zone`: *[Sequência de caracteres](er-formula-supported-data-types-primitive.md#string)*

O nome do fuso horário para o qual um determinado valor de data/hora é deslocado antes da conversão.

`target time zone`: *Cadeia de caracteres*

O nome do fuso horário para o qual um valor de data/hora convertido é deslocado durante a conversão.

## <a name="return-values"></a>Valores de retorno

*Data e Hora*

O valor de data/hora resultante no fuso horário do Tempo Universal Coordenado.

## <a name="usage-notes"></a>Notas de uso

Para especificar fusos horários de origem e destino, você pode usar os nomes de fuso horário [fornecidos](https://data.iana.org/time-zones/releases/) pela [IANA (Internet Assigned Numbers Authority)](https://www.iana.org/) ou que são [disponibilizados](/windows-hardware/manufacture/desktop/default-time-zones) pelo Microsoft Windows.

No runtime, a exceção "Fuso horário '\<time zone name\>' não existe" será lançada se o nome fornecido não for encontrado na lista da IANA nem no registro do Windows.

No caso de fusos horários em que o horário de verão tem influência, a conversão considera a diferença do horário de verão no Tempo Universal Coordenado. As informações mais recentes disponíveis sobre essa diferença são usadas durante a conversão.

## <a name="example-1"></a>Exemplo 1

Neste exemplo, os nomes de fuso horário para Windows são usados.

Você configura a fonte de dados **DSX** do tipo **Campo calculado**. Ela contém esta expressão.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Se você configurar a expressão da fonte de dados **DSY** do tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, a fonte de dados **DSX** retornará o texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Esse texto mostra que a diferença de tempo entre os dois fusos horários fornecidos em 1º de junho é de mais de 24 horas. Assim, o valor de data/hora convertido é um dia a menos do valor de data/hora especificado, porque o fuso horário básico está adiantado no fuso horário de destino.

Se você configurar a expressão da fonte de dados **DSY** do tipo **Campo calculado** como `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, a fonte de dados **DSX** retornará o texto **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Esse texto mostra que a diferença de tempo entre os dois fusos horários fornecidos em 1º de dezembro é de menos de 24 horas. Assim, o valor de data/hora convertido é igual ao valor de data/hora especificado.

> [!NOTE]
> A mesma expressão retorna uma variação diferente entre os valores de data/hora fornecidos e convertidos para o mesmo par de fusos horários porque outra diferença de horário de verão de Tempo Universal Coordenado é observada para os fusos horários fornecidos em uma determinada data/hora.

## <a name="example-2"></a>Exemplo 2

Neste exemplo, os nomes de fuso horário IANA são usados.

Você configura a fonte de dados **DSX** do tipo **Campo calculado**. Ela contém esta expressão.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Se você configurar a expressão da fonte de dados **DSY** do tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, a fonte de dados **DSX** retornará o texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Esse texto mostra que a diferença de tempo entre os dois fusos horários fornecidos em 1º de junho é de mais de 24 horas. Assim, o valor de data/hora convertido é um dia a menos do valor de data/hora especificado, porque o fuso horário básico está adiantado no fuso horário de destino.

Se você configurar a expressão da fonte de dados **DSY** do tipo **Campo calculado** como `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, a fonte de dados **DSX** retornará o texto **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Esse texto mostra que a diferença de tempo entre os dois fusos horários fornecidos em 1º de dezembro é de menos de 24 horas. Assim, o valor de data/hora convertido é igual ao valor de data/hora especificado.

## <a name="example-3"></a>Exemplo 3

Você configura a fonte de dados **DSX** do tipo **Campo calculado**. Ela contém esta expressão.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Se você configurar a expressão da fonte de dados **DSY** do tipo **Campo calculado** como `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, a fonte de dados **DSX** retornará o texto **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00'**. Esse texto mostra que a diferença de tempo entre os dois fusos horários fornecidos em 1º de junho é de mais de 24 horas. Assim, o valor de data/hora convertido é um dia a mais do valor de data/hora especificado, porque o fuso horário de destino está adiantado no fuso horário básico.

## <a name="example-4"></a>Exemplo 4

Você pode receber uma marcação de data/hora de uma fonte externa como texto que não contém informações sobre fuso horário. No entanto, você pode saber o fuso horário em que a origem é operada. Por exemplo, você recebe a marcação de data/hora **01/12/2021 12:55:00** de um serviço operado na Espanha. Para salvar corretamente esse valor de data/hora no banco de dados, faça a seguinte conversão:

- Configure a fonte de dados **DSY** do tipo **Campo calculado** para converter uma marcação de data/hora do texto para o valor de data/hora do Tempo Universal Coordenado.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Configure a fonte de dados **DSX** do tipo **Campo calculado** para alterar o valor de data/hora convertido para o Tempo Universal Coordenado como o valor de data/hora do fuso horário da fonte externa.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Ao usar a função `CHANGETIMEZONE` para a conversão de data/hora, lembre-se de que qualquer valor de data/hora será armazenado no banco de dados como o valor no fuso horário do Tempo Universal Coordenado. Antes que esse valor possa ser apresentado nas páginas do aplicativo, ele é transformado. A transformação considera o fuso horário [definido](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) como uma zona preferida para o usuário do aplicativo conectado no momento.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
