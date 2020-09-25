---
title: Função de ER CONVERTCURRENCY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONVERTCURRENCY é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: ae6e0069c6e9227d4cf1045eeebbb825a2f943c3
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744302"
---
# <a name="convertcurrency-er-function"></a><span data-ttu-id="22d0c-103">Função de ER CONVERTCURRENCY</span><span class="sxs-lookup"><span data-stu-id="22d0c-103">CONVERTCURRENCY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22d0c-104">A função `CONVERTCURRENCY` retorna um valor *Real* que representa o resultado da conversão do valor monetário especificado da moeda de origem especificada para a moeda de destino especificada usando as configurações da empresa especificada na data especificada.</span><span class="sxs-lookup"><span data-stu-id="22d0c-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="22d0c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22d0c-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="22d0c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="22d0c-106">Arguments</span></span>

<span data-ttu-id="22d0c-107">`amount`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="22d0c-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="22d0c-108">Um valor numérico que representa o valor monetário que deve ser convertido.</span><span class="sxs-lookup"><span data-stu-id="22d0c-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="22d0c-109">`source currency`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="22d0c-109">`source currency`: *String*</span></span>

<span data-ttu-id="22d0c-110">O código da moeda de origem.</span><span class="sxs-lookup"><span data-stu-id="22d0c-110">The code of the source currency.</span></span>

<span data-ttu-id="22d0c-111">`target currency`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="22d0c-111">`target currency`: *String*</span></span>

<span data-ttu-id="22d0c-112">O código da moeda de destino.</span><span class="sxs-lookup"><span data-stu-id="22d0c-112">The code of the target currency.</span></span>

<span data-ttu-id="22d0c-113">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="22d0c-113">`date`: *Date*</span></span>

<span data-ttu-id="22d0c-114">Um valor de *Data* que representa a data usada para determinar a taxa de câmbio da conversão.</span><span class="sxs-lookup"><span data-stu-id="22d0c-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="22d0c-115">`company`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="22d0c-115">`company`: *String*</span></span>

<span data-ttu-id="22d0c-116">Um valor de *Cadeia de caracteres* que representa o código de uma empresa que fornece as configurações usadas para a conversão.</span><span class="sxs-lookup"><span data-stu-id="22d0c-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="22d0c-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="22d0c-117">Return values</span></span>

<span data-ttu-id="22d0c-118">*Real*</span><span class="sxs-lookup"><span data-stu-id="22d0c-118">*Real*</span></span>

<span data-ttu-id="22d0c-119">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="22d0c-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="22d0c-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="22d0c-120">Example</span></span>

<span data-ttu-id="22d0c-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` retorna o equivalente a um euro em dólares norte-americanos na data da sessão atual, com base nas configurações da empresa **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="22d0c-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22d0c-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="22d0c-122">Additional resources</span></span>

[<span data-ttu-id="22d0c-123">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="22d0c-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
