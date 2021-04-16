---
title: Função DATETODATETIME ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETODATETIME é usada.
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
ms.openlocfilehash: bb90c58544eeba804cd39542cc70fab3b840af80
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746953"
---
# <a name="datetodatetime-er-function"></a><span data-ttu-id="50339-103">Função DATETODATETIME ER</span><span class="sxs-lookup"><span data-stu-id="50339-103">DATETODATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50339-104">A função `DATETODATETIME` retorna um valor *DateTime* convertido de um determinado valor de data para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="50339-104">The `DATETODATETIME` function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="50339-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="50339-105">Syntax</span></span>

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a><span data-ttu-id="50339-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="50339-106">Arguments</span></span>

<span data-ttu-id="50339-107">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="50339-107">`date`: *Date*</span></span>

<span data-ttu-id="50339-108">Um valor de data que representa a data da conversão.</span><span class="sxs-lookup"><span data-stu-id="50339-108">A date value that represents the date to convert.</span></span>

## <a name="return-values"></a><span data-ttu-id="50339-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="50339-109">Return values</span></span>

<span data-ttu-id="50339-110">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="50339-110">*DateTime*</span></span>

<span data-ttu-id="50339-111">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="50339-111">The resulting date/time value.</span></span>

## <a name="example-1"></a><span data-ttu-id="50339-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="50339-112">Example 1</span></span>

<span data-ttu-id="50339-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` retorna a data da sessão atual do Dynamics 365 Finance Microsoft, 24 de dezembro de 2015, como **24/12/2015 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="50339-113">`DATETODATETIME (CompInfo. 'getCurrentDate()')` returns the date of the current Microsoft Dynamics 365 Finance session, December 24, 2015, as **12/24/2015 12:00:00 AM**.</span></span> <span data-ttu-id="50339-114">Neste exemplo, **CompInfo** é uma fonte de dados de relatório eletrônico (ER) do tipo **Finance and Operations/Tabela** e se refere à tabela CompanyInfo.</span><span class="sxs-lookup"><span data-stu-id="50339-114">In this example, **CompInfo** is an Electronic reporting (ER) data source of the **Finance and Operations/Table** type, and it refers to the CompanyInfo table.</span></span>

## <a name="example-2"></a><span data-ttu-id="50339-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="50339-115">Example 2</span></span>

<span data-ttu-id="50339-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` retorna o valor de data/hora **12/11/2019 12:00:00 AM**.</span><span class="sxs-lookup"><span data-stu-id="50339-116">`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` returns the date/time value **11/12/2019 12:00:00 AM**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50339-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="50339-117">Additional resources</span></span>

[<span data-ttu-id="50339-118">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="50339-118">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]