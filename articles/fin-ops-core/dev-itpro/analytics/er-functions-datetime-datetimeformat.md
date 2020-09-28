---
title: Função DATETIMEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETIMEFORMAT é usada.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 65b988e6c58aed35577288e01157b8c1f76e6efd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744854"
---
# <a name="datetimeformat-er-function"></a>Função DATETIMEFORMAT ER

[!include [banner](../includes/banner.md)]

A função `DATETIMEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data/hora determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada. Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintaxe 1

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Sintaxe 2

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argumentos

`datetime`: *DateTime*

Um valor de data/hora que representa a data e a hora para formatação.

`format`: *Cadeia de caracteres*

O formato da cadeia de caracteres de saída.

`culture`: *Cadeia de caracteres*

A cultura a ser usada para formatação.

## <a name="return-values"></a>Valores de retorno

*Cadeia de caracteres*

O valor da cadeia de caracteres resultante.

## <a name="usage-notes"></a>Notas de uso

Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada. Por exemplo, se a função `DATETIMEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã. O valor padrão `culture` é **EN-US**.

Quando a função `DATETIMEFORMAT` converte um determinado valor de data/hora, ela considera a configuração de fuso horário do usuário do aplicativo que está executando o formato ER no qual a função é chamada pelo contexto.

## <a name="example-1"></a>Exemplo 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.

## <a name="example-2"></a>Exemplo 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.

## <a name="example-3"></a>Exemplo 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` retorna o valor de cadeia de caracteres **2019-11-12T08:00:00.0000000-08:00** quando é chamada durante um processo iniciado por um usuário de aplicativo com o valor de fuso horário **(GMT-08:00) Hora do Pacífico (EUA e Canadá)** na seção **Preferências de idioma e país/região**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)
