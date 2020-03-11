---
title: Função DATETODATETIME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETODATETIME é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 961ccd18e70d4f9851027492366a7d9408a668c5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042403"
---
# <a name="DATETODATETIME">Função DATETODATETIME ER</a>

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

`DATETODATETIME (CompInfo. 'getCurrentDate()')` retorna a data da sessão atual do Dynamics 365 Finance Microsoft, 24 de dezembro de 2015, como **24/12/2015 12:00:00 AM**. Neste exemplo, **CompInfo** é uma fonte de dados de relatório eletrônico (ER) do tipo **Finance and Operations/Tabela** e se refere à tabela CompanyInfo.

## <a name="example-2"></a>Exemplo 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` retorna o valor de data/hora **12/11/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Recursos adicionais

[Funções de data e de hora](er-functions-category-datetime.md)
