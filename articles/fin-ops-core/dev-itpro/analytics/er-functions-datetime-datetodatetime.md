---
title: Função DATETODATETIME ER
description: Este artigo fornece informações sobre como a função de relatório eletrônico (ER) DATETODATETIME é usada.
author: kfend
ms.date: 12/04/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 30fe75c7fd68edfff3e3778192723792d0f342ab
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287298"
---
# <a name="datetodatetime-er-function"></a>Função DATETODATETIME ER

[!include [banner](../includes/banner.md)]

A função `DATETODATETIME` retorna um valor *DateTime* convertido de um determinado valor de data para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]).

## <a name="syntax"></a>Sintaxe

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argumentos

`date`: *Data*

Um valor de data que representa a data da conversão.

## <a name="return-values"></a>Valores de retorno

*Data/Hora*

O valor de data/hora resultante.

## <a name="example-1"></a>Exemplo 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` retorna a data da sessão atual do Microsoft Dynamics 365 Finance, 24 de dezembro de 2015, como **24/12/2015 12:00:00 AM**. Neste exemplo, **CompInfo** é uma fonte de dados de relatório eletrônico (ER) do tipo **finanças e operações/Tabela** e se refere à tabela CompanyInfo.

## <a name="example-2"></a>Exemplo 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` retorna o valor de data/hora **12/11/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
