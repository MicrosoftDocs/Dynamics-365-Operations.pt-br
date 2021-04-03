---
title: Lista de funções ER na categoria de data e hora
description: Este tópico fornece informações sobre as funções de data e hora que são compatíveis no relatório eletrônico (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 52b84f9b611f703fd390eca58c1364a4992bece2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561701"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="39fda-103">Lista de funções ER na categoria de data e hora</span><span class="sxs-lookup"><span data-stu-id="39fda-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39fda-104">Funções de data e hora de relatório eletrônico (ER) podem ser usadas para extrair informações de valores de data e hora e para realizar operações nelas.</span><span class="sxs-lookup"><span data-stu-id="39fda-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="39fda-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="39fda-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="39fda-106">Lista de funções com suporte</span><span class="sxs-lookup"><span data-stu-id="39fda-106">List of supported functions</span></span>

| <span data-ttu-id="39fda-107">Função</span><span class="sxs-lookup"><span data-stu-id="39fda-107">Function</span></span> | <span data-ttu-id="39fda-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="39fda-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="39fda-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="39fda-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="39fda-110">Esta função retorna um valor *DateTime* que é o número especificado de dias antes ou depois de uma data inicial especificada.</span><span class="sxs-lookup"><span data-stu-id="39fda-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="39fda-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="39fda-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="39fda-112">Essa função retorna um valor de *Cadeia de caracteres* que apresenta um valor de data determinado como texto no formato especificado e em uma cultura opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="39fda-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="39fda-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="39fda-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="39fda-114">Essa função retorna um valor de *Cadeia de caracteres* que apresenta um valor de data/hora determinado como texto no formato especificado e em uma cultura opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="39fda-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="39fda-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="39fda-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="39fda-116">Essa função retorna um valor de *DateTime* que é convertido de um valor de texto determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data/hora.</span><span class="sxs-lookup"><span data-stu-id="39fda-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="39fda-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="39fda-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="39fda-118">Esta função retorna um valor *DateTime* convertido de um determinado valor de data para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="39fda-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="39fda-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="39fda-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="39fda-120">Essa função retorna um valor de *Data* que é convertido de um valor de texto determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data.</span><span class="sxs-lookup"><span data-stu-id="39fda-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="39fda-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="39fda-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="39fda-122">Essa função retorna um valor *Inteiro* que representa o número de dias entre 1 de janeiro e a data especificada.</span><span class="sxs-lookup"><span data-stu-id="39fda-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="39fda-123">Dias</span><span class="sxs-lookup"><span data-stu-id="39fda-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="39fda-124">Essa função retorna um valor *Inteiro* que representa o número de dias entre uma data especificada e uma segunda data especificada.</span><span class="sxs-lookup"><span data-stu-id="39fda-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="39fda-125">Now</span><span class="sxs-lookup"><span data-stu-id="39fda-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="39fda-126">Essa função retorna um valor de *DateTime* que representa a data e a hora atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="39fda-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="39fda-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="39fda-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="39fda-128">Essa função retorna um valor de *Data* que representa a data **nula** (1º de janeiro de 1900).</span><span class="sxs-lookup"><span data-stu-id="39fda-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="39fda-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="39fda-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="39fda-130">Essa função retorna um valor de *DateTime* que representa o valor de data/hora **nulo** (1º de janeiro de 1900) no Tempo Universal Coordenado.</span><span class="sxs-lookup"><span data-stu-id="39fda-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="39fda-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="39fda-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="39fda-132">Essa função retorna um valor de *DateTime* que representa a data e a hora atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="39fda-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="39fda-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="39fda-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="39fda-134">Essa função retorna um valor de *Data* que representa a data atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="39fda-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="39fda-135">Hoje</span><span class="sxs-lookup"><span data-stu-id="39fda-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="39fda-136">Essa função retorna um valor de *Data* que representa a data atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="39fda-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="39fda-137">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="39fda-137">Additional resources</span></span>

[<span data-ttu-id="39fda-138">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="39fda-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="39fda-139">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="39fda-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="39fda-140">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="39fda-140">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]