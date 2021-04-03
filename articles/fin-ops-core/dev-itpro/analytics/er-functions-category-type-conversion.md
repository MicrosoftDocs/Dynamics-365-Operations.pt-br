---
title: Lista de funções ER na categoria de conversão de tipo
description: Este tópico fornece informações sobre as funções de conversão que são compatíveis no relatório eletrônico (ER).
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
ms.openlocfilehash: 5613496d3131ccd39b198cac214eb791a6d07355
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561509"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="f5df2-103">Lista de funções ER na categoria de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="f5df2-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5df2-104">As funções de conversão de tipo de relatório eletrônico (ER) podem ser usadas para converter valores entre tipos.</span><span class="sxs-lookup"><span data-stu-id="f5df2-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="f5df2-105">Este tópico fornece um resumo dessas funções.</span><span class="sxs-lookup"><span data-stu-id="f5df2-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="f5df2-106">Funções de conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="f5df2-106">Type conversion functions</span></span>

| <span data-ttu-id="f5df2-107">Função</span><span class="sxs-lookup"><span data-stu-id="f5df2-107">Function</span></span> | <span data-ttu-id="f5df2-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5df2-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f5df2-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="f5df2-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="f5df2-110">Esta função retorna um valor *Int64* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="f5df2-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="f5df2-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="f5df2-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="f5df2-112">Esta função retorna um valor *Int* que representa a cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="f5df2-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="f5df2-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="f5df2-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="f5df2-114">Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="f5df2-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="f5df2-115">Durante a conversão, os separadores de agrupamento de dígitos e decimais especificados são considerados.</span><span class="sxs-lookup"><span data-stu-id="f5df2-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="f5df2-116">Alíquota</span><span class="sxs-lookup"><span data-stu-id="f5df2-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="f5df2-117">Esta função retorna um valor *Real* que é convertido do valor de *Cadeia de caracteres* especificado.</span><span class="sxs-lookup"><span data-stu-id="f5df2-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="f5df2-118">Funções de conversão de tipo na categoria contêiner</span><span class="sxs-lookup"><span data-stu-id="f5df2-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="f5df2-119">A tabela a seguir descreve as funções de conversão de tipo na categoria [contêiner](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="f5df2-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="f5df2-120">Função</span><span class="sxs-lookup"><span data-stu-id="f5df2-120">Function</span></span> | <span data-ttu-id="f5df2-121">descrição</span><span class="sxs-lookup"><span data-stu-id="f5df2-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f5df2-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="f5df2-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="f5df2-123">Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *Contêiner*.</span><span class="sxs-lookup"><span data-stu-id="f5df2-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="f5df2-124">Funções de conversão de tipo na categoria de dia e hora</span><span class="sxs-lookup"><span data-stu-id="f5df2-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="f5df2-125">A tabela a seguir descreve as funções de conversão de tipo na [categoria de data e hora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="f5df2-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="f5df2-126">Função</span><span class="sxs-lookup"><span data-stu-id="f5df2-126">Function</span></span> | <span data-ttu-id="f5df2-127">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5df2-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f5df2-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="f5df2-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="f5df2-129">Essa função retorna um valor de *DateTime* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data/hora.</span><span class="sxs-lookup"><span data-stu-id="f5df2-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="f5df2-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="f5df2-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="f5df2-131">Esta função retorna um valor *DateTime* convertido de um determinado valor de *Data* para um valor de data/hora no Tempo Universal Coordenado (Greenwich Mean Time \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="f5df2-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="f5df2-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="f5df2-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="f5df2-133">Essa função retorna um valor de *Data* que é convertido de um valor de *Cadeia de caracteres* determinado no formato especificado e em uma cultura opcionalmente especificada para um valor de data.</span><span class="sxs-lookup"><span data-stu-id="f5df2-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="f5df2-134">Funções de conversão de tipo na categoria de lista</span><span class="sxs-lookup"><span data-stu-id="f5df2-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="f5df2-135">A tabela a seguir descreve as funções de conversão de tipo na [categoria de lista](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="f5df2-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="f5df2-136">Função</span><span class="sxs-lookup"><span data-stu-id="f5df2-136">Function</span></span> | <span data-ttu-id="f5df2-137">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5df2-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f5df2-138">Lista</span><span class="sxs-lookup"><span data-stu-id="f5df2-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="f5df2-139">Essa função retorna um valor de *Lista de registros* como uma nova lista criada de argumentos especificados do tipo *Registro do contêiner*.</span><span class="sxs-lookup"><span data-stu-id="f5df2-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="f5df2-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="f5df2-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="f5df2-141">Essa função retorna um valor de *Lista de registros* que é criado com base na estrutura do argumento determinado do tipo *Enumeração* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="f5df2-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="f5df2-142">Dividir</span><span class="sxs-lookup"><span data-stu-id="f5df2-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="f5df2-143">Essa função divide o valor da *Cadeia de caracteres* especificado em subcadeias de caracteres e retorna o resultado como um novo valor de *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="f5df2-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="f5df2-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="f5df2-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="f5df2-145">Essa função retorna um valor de *Cadeia de caracteres* que consiste em valores concatenados do campo especificado do valor *Lista de registro* especificado.</span><span class="sxs-lookup"><span data-stu-id="f5df2-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="f5df2-146">Os valores podem ser separados pelo delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="f5df2-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="f5df2-147">Funções de conversão de tipo na categoria de texto</span><span class="sxs-lookup"><span data-stu-id="f5df2-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="f5df2-148">A tabela a seguir descreve as funções de conversão de tipo na [categoria de texto](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="f5df2-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="f5df2-149">Função</span><span class="sxs-lookup"><span data-stu-id="f5df2-149">Function</span></span> | <span data-ttu-id="f5df2-150">Descrição</span><span class="sxs-lookup"><span data-stu-id="f5df2-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f5df2-151">Char</span><span class="sxs-lookup"><span data-stu-id="f5df2-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="f5df2-152">Essa função retorna um valor de *Cadeia de caracteres* que representa um caractere único referenciado pelo número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="f5df2-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="f5df2-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="f5df2-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="f5df2-154">Essa função converte a entrada especificada do tipo *Cadeia de caracteres* em um item de dados do tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="f5df2-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="f5df2-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="f5df2-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="f5df2-156">Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado no formato especificado e em uma cultura opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="f5df2-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="f5df2-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="f5df2-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="f5df2-158">Essa função retorna um valor de *Contêiner* que apresenta a imagem do código de Resposta Rápida (código QR) para a cadeia de caracteres especificada em formato binário.</span><span class="sxs-lookup"><span data-stu-id="f5df2-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="f5df2-159">Texto</span><span class="sxs-lookup"><span data-stu-id="f5df2-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="f5df2-160">Essa função retorna um valor de *Cadeia de caracteres* que representa o número especificado após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f5df2-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="f5df2-161">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f5df2-161">Additional resources</span></span>

[<span data-ttu-id="f5df2-162">Visão geral do Relatório Eletrônico</span><span class="sxs-lookup"><span data-stu-id="f5df2-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="f5df2-163">Designer de fórmulas no Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="f5df2-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="f5df2-164">Linguagem da fórmula de relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="f5df2-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]