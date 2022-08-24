---
title: Função de ER WEEKNUM
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) WEEKNUM é usada.
author: kfend
ms.date: 01/15/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2021-12-03
ms.dyn365.ops.version: AX 10.0.24
ms.custom: 58771
ms.assetid: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 4658f88b7e353e651177fad0c8636c5403be1256
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268136"
---
# <a name="weeknum-er-function"></a>Função de ER WEEKNUM

[!include [banner](../includes/banner.md)]

A função `WEEKNUM` retorna um valor *[Inteiro](er-formula-supported-data-types-primitive.md#integer)* que representa a semana do ano que inclui um valor de *[Data](er-formula-supported-data-types-primitive.md#date)* especificado. O cálculo é baseado em regras dependentes da cultura que definem uma semana do calendário e o primeiro dia da semana.

## <a name="syntax"></a>Sintaxe

```vb
WEEKNUM (date, culture) as Integer
```

## <a name=""></a><a name="arguments">Argumentos</a>

`date`: *Data*

Um valor de data que representa a data a ser usada para calcular a semana do ano.

`culture`: *[Cadeia de caracteres](er-formula-supported-data-types-primitive.md#string)*

A cultura a ser usada para o cálculo. Você pode usar códigos de cultura com suporte de acordo com os [padrões .NET](/dotnet/api/system.globalization.cultureinfo.getcultures?view=net-5.0).

## <a name="return-values"></a>Valores de retorno

*Inteiro*

O valor numérico resultante.

## <a name="usage-notes"></a>Notas de uso

A semana do ano é calculada com base no [padrão ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html), se esse padrão foi adotado por um país ou região para o qual o local é fornecido no tempo de execução. Caso contrário, o cálculo será baseado em padrões nacionais específicos do país/região.

Se um código de [cultura](#arguments) sem suporte é fornecido como um argumento da função `WEEKNUM` no tempo de execução, uma exceção é lançada. Se a cadeia de caracteres em branco for fornecida como um código de cultura, o calendário neutro em relação ao país em inglês será usado para calcular o número da semana.

## <a name="examples"></a>Exemplos

`WEEKNUM (DATEVALUE ("01-01-2020", "de"))` retorna **1**.

`WEEKNUM (DATEVALUE ("01-01-2021", "de"))` retorna **53**.

`WEEKNUM (DATEVALUE ("01-01-2022", "de"))` retorna **52**.

`WEEKNUM (DATEVALUE ("01-01-2022", "ar"))` retorna **21**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
