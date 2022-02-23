---
title: Lista de funções ER na categoria de conversão de tipo
description: Este tópico fornece informações sobre as funções de conversão que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: eb2d4ab3434a563e907f6540809888cd3f671c1a
ms.sourcegitcommit: fcc4596eeadac5dfe9a3242afa49b9b1c0c96575
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/15/2020
ms.locfileid: "4740799"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Lista de funções ER na categoria de conversão de tipo

[!include [banner](../includes/banner.md)]

As funções de conversão de tipo de relatório eletrônico (ER) podem ser usadas para converter valores entre tipos. Este tópico fornece um resumo dessas funções.

## <a name="type-conversion-functions"></a>Funções de conversão de tipo

| Função | Descrição |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Esta função retorna um valor *Int64* que representa a cadeia de caracteres especificada. |
| [IntValue](er-functions-conversion-intvalue.md)       | Esta função retorna um valor *Int* que representa a cadeia de caracteres especificada. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado. Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados. |
| [Alíquota](er-functions-conversion-value.md)             | Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado. |

## <a name="type-conversion-functions-in-the-container-category"></a>Funções de conversão de tipo na categoria contêiner

A tabela a seguir descreve as funções de conversão de tipo na categoria [contêiner](er-functions-category-container.md).

| Função | descrição |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *Contêiner*. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Funções de conversão de tipo na categoria de dia e hora

A tabela a seguir descreve as funções de conversão de tipo na [categoria de data e hora](er-functions-category-datetime.md).

| Função | Descrição |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Essa função retorna um valor de *DateTime* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data/hora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Esta função retorna um valor *DateTime* convertido de um determinado valor de *Data* para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Essa função retorna um valor de *Data* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data. |

## <a name="type-conversion-functions-in-the-list-category"></a>Funções de conversão de tipo na categoria de lista

A tabela a seguir descreve as funções de conversão de tipo na [categoria de lista](er-functions-category-list.md).

| Função | Descrição |
|----------|-------------|
| [Lista](er-functions-list-list.md)                 | Essa função retorna um valor de *Lista de registros* como uma nova lista criada de argumentos especificados do tipo *Registro do contêiner*. |
| [ListOfFields](er-functions-list-listoffields.md) | Essa função retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento determinado do tipo *Enumeração* ou *Contêiner (registro)*. |
| [Dividir](er-functions-list-split.md)               | Essa função divide o valor da *Cadeia de caracteres* especificado em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*. |
| [StringJoin](er-functions-list-stringjoin.md)     | Essa função retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado do valor *Lista de registro* especificado. Os valores podem ser separados pelo delimitador especificado. |

## <a name="type-conversion-functions-in-the-text-category"></a>Funções de conversão de tipo na categoria de texto

A tabela a seguir descreve as funções de conversão de tipo na [categoria de texto](er-functions-category-text.md).

| Função | Descrição |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Essa função retorna um valor de *Cadeia de caracteres* que representa um caractere único referenciado pelo número Unicode especificado. |
| [GuidValue](er-functions-text-guidvalue.md)       | Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado no formato especificado e em uma cultura opcionalmente especificada. |
| [QrCode](er-functions-text-qrcode.md)             | Essa função retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário. |
| [Texto](er-functions-text-text.md)                 | Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo. |

## <a name="additional-resources"></a>Recursos adicionais

[Visão geral do Relatório Eletrônico](general-electronic-reporting.md)

[Designer de fórmulas no Relatório eletrônico](general-electronic-reporting-formula-designer.md)

[Linguagem da fórmula de relatório eletrônico](er-formula-language.md)
