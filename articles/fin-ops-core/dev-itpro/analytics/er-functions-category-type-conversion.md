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
ms.openlocfilehash: d160c02403bf067ed523fbd634e65c622b522b97
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686065"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="07320-103">Lista de funções ER na categoria de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="07320-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="07320-104">As funções de conversão de tipo de relatório eletrônico (ER) podem ser usadas para converter valores entre tipos.</span><span class="sxs-lookup"><span data-stu-id="07320-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="07320-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="07320-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="07320-106">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="07320-106">Type conversion functions</span></span>

| <span data-ttu-id="07320-107">Função</span><span class="sxs-lookup"><span data-stu-id="07320-107">Function</span></span> | <span data-ttu-id="07320-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="07320-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="07320-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="07320-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="07320-110">Esta função retorna um valor *Int64* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="07320-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="07320-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="07320-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="07320-112">Esta função retorna um valor *Int* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="07320-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="07320-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="07320-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="07320-114">Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="07320-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="07320-115">Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.</span><span class="sxs-lookup"><span data-stu-id="07320-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="07320-116">Alíquota</span><span class="sxs-lookup"><span data-stu-id="07320-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="07320-117">Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="07320-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="07320-118">Funções de conversão de tipo na categoria de dia e hora</span><span class="sxs-lookup"><span data-stu-id="07320-118">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="07320-119">A tabela a seguir descreve as funções de conversão de tipo na [categoria de data e hora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="07320-119">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="07320-120">Função</span><span class="sxs-lookup"><span data-stu-id="07320-120">Function</span></span> | <span data-ttu-id="07320-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="07320-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="07320-122">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="07320-122">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="07320-123">Essa função retorna um valor de *DateTime* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data/hora.</span><span class="sxs-lookup"><span data-stu-id="07320-123">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="07320-124">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="07320-124">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="07320-125">Esta função retorna um valor *DateTime* convertido de um determinado valor de *Data* para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="07320-125">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="07320-126">DateValue</span><span class="sxs-lookup"><span data-stu-id="07320-126">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="07320-127">Essa função retorna um valor de *Data* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data.</span><span class="sxs-lookup"><span data-stu-id="07320-127">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="07320-128">Funções de conversão de tipo na categoria de lista</span><span class="sxs-lookup"><span data-stu-id="07320-128">Type conversion functions in the list category</span></span>

<span data-ttu-id="07320-129">A tabela a seguir descreve as funções de conversão de tipo na [categoria de lista](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="07320-129">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="07320-130">Função</span><span class="sxs-lookup"><span data-stu-id="07320-130">Function</span></span> | <span data-ttu-id="07320-131">Descrição</span><span class="sxs-lookup"><span data-stu-id="07320-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="07320-132">Lista</span><span class="sxs-lookup"><span data-stu-id="07320-132">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="07320-133">Essa função retorna um valor de *Lista de registros* como uma nova lista criada de argumentos especificados do tipo *Registro do contêiner*.</span><span class="sxs-lookup"><span data-stu-id="07320-133">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="07320-134">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="07320-134">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="07320-135">Essa função retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento determinado do tipo *Enumeração* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="07320-135">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="07320-136">Dividir</span><span class="sxs-lookup"><span data-stu-id="07320-136">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="07320-137">Essa função divide o valor da *Cadeia de caracteres* especificado em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="07320-137">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="07320-138">StringJoin</span><span class="sxs-lookup"><span data-stu-id="07320-138">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="07320-139">Essa função retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado do valor *Lista de registro* especificado.</span><span class="sxs-lookup"><span data-stu-id="07320-139">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="07320-140">Os valores podem ser separados pelo delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="07320-140">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="07320-141">Funções de conversão de tipo na categoria de texto</span><span class="sxs-lookup"><span data-stu-id="07320-141">Type conversion functions in the text category</span></span>

<span data-ttu-id="07320-142">A tabela a seguir descreve as funções de conversão de tipo na [categoria de texto](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="07320-142">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="07320-143">Função</span><span class="sxs-lookup"><span data-stu-id="07320-143">Function</span></span> | <span data-ttu-id="07320-144">Descrição</span><span class="sxs-lookup"><span data-stu-id="07320-144">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="07320-145">Char</span><span class="sxs-lookup"><span data-stu-id="07320-145">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="07320-146">Essa função retorna um valor de *Cadeia de caracteres* que representa um caractere único referenciado pelo número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="07320-146">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="07320-147">GuidValue</span><span class="sxs-lookup"><span data-stu-id="07320-147">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="07320-148">Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="07320-148">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="07320-149">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="07320-149">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="07320-150">Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado no formato especificado e em uma cultura opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="07320-150">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="07320-151">QrCode</span><span class="sxs-lookup"><span data-stu-id="07320-151">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="07320-152">Essa função retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário.</span><span class="sxs-lookup"><span data-stu-id="07320-152">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="07320-153">Texto</span><span class="sxs-lookup"><span data-stu-id="07320-153">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="07320-154">Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="07320-154">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="07320-155">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="07320-155">Additional resources</span></span>

[<span data-ttu-id="07320-156">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="07320-156">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="07320-157">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="07320-157">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="07320-158">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="07320-158">Electronic reporting formula language</span></span>](er-formula-language.md)
