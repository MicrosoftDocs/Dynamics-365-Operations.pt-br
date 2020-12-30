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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a27fd30236a61576ab9063010ea6bc38d9cf7a1e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686777"
---
# <a name="convertcurrency-er-function"></a><span data-ttu-id="7a297-103">Função de ER CONVERTCURRENCY</span><span class="sxs-lookup"><span data-stu-id="7a297-103">CONVERTCURRENCY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a297-104">A função `CONVERTCURRENCY` retorna um valor *Real* que representa o resultado da conversão do valor monetário especificado da moeda de origem especificada para a moeda de destino especificada usando as configurações da empresa especificada na data especificada.</span><span class="sxs-lookup"><span data-stu-id="7a297-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a297-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7a297-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="7a297-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7a297-106">Arguments</span></span>

<span data-ttu-id="7a297-107">`amount`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="7a297-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="7a297-108">Um valor numérico que representa o valor monetário que deve ser convertido.</span><span class="sxs-lookup"><span data-stu-id="7a297-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="7a297-109">`source currency`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7a297-109">`source currency`: *String*</span></span>

<span data-ttu-id="7a297-110">O código da moeda de origem.</span><span class="sxs-lookup"><span data-stu-id="7a297-110">The code of the source currency.</span></span>

<span data-ttu-id="7a297-111">`target currency`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7a297-111">`target currency`: *String*</span></span>

<span data-ttu-id="7a297-112">O código da moeda de destino.</span><span class="sxs-lookup"><span data-stu-id="7a297-112">The code of the target currency.</span></span>

<span data-ttu-id="7a297-113">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="7a297-113">`date`: *Date*</span></span>

<span data-ttu-id="7a297-114">Um valor de *Data* que representa a data usada para determinar a taxa de câmbio da conversão.</span><span class="sxs-lookup"><span data-stu-id="7a297-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="7a297-115">`company`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7a297-115">`company`: *String*</span></span>

<span data-ttu-id="7a297-116">Um valor de *Cadeia de caracteres* que representa o código de uma empresa que fornece as configurações usadas para a conversão.</span><span class="sxs-lookup"><span data-stu-id="7a297-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="7a297-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7a297-117">Return values</span></span>

<span data-ttu-id="7a297-118">*Real*</span><span class="sxs-lookup"><span data-stu-id="7a297-118">*Real*</span></span>

<span data-ttu-id="7a297-119">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="7a297-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="7a297-120">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7a297-120">Example</span></span>

<span data-ttu-id="7a297-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` retorna o equivalente a um euro em dólares norte-americanos na data da sessão atual, com base nas configurações da empresa **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="7a297-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a297-122">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7a297-122">Additional resources</span></span>

[<span data-ttu-id="7a297-123">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="7a297-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
