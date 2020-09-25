---
title: Função de ER FA_SUM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FA_SUM é usada.
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
ms.openlocfilehash: fccd318a8ab67528f0ce048fc770a2037f625d7a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744119"
---
# <a name="fa_sum-er-function"></a><span data-ttu-id="fed3a-103">Função de ER FA_SUM</span><span class="sxs-lookup"><span data-stu-id="fed3a-103">FA_SUM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fed3a-104">A função `FA_SUM` retorna um valor de *Contêiner (registro)* que consiste em dados dos valores de ativo fixo para o item de ativo fixo, o código do método de depreciação e o período de datas especificados.</span><span class="sxs-lookup"><span data-stu-id="fed3a-104">The `FA_SUM` function returns a *Container (record)* value that consists of data for the fixed asset amounts for the specified fixed asset item, value model code, and period of dates.</span></span>

## <a name="syntax"></a><span data-ttu-id="fed3a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="fed3a-105">Syntax</span></span>

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a><span data-ttu-id="fed3a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fed3a-106">Arguments</span></span>

<span data-ttu-id="fed3a-107">`fixed asset code`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="fed3a-107">`fixed asset code`: *String*</span></span>

<span data-ttu-id="fed3a-108">Um valor de *Cadeia de caracteres* que representa o código de um item de ativo fixo para o qual o saldo é calculado.</span><span class="sxs-lookup"><span data-stu-id="fed3a-108">A *String* value that represents the code of a fixed asset item that the balance is calculated for.</span></span>

<span data-ttu-id="fed3a-109">`value model code`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="fed3a-109">`value model code`: *String*</span></span>

<span data-ttu-id="fed3a-110">Um valor de *Cadeia de caracteres* que representa o código de um método de depreciação para o qual o saldo é calculado.</span><span class="sxs-lookup"><span data-stu-id="fed3a-110">A *String* value that represents the code of a value model that the balance is calculated for.</span></span>

<span data-ttu-id="fed3a-111">`start date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="fed3a-111">`start date`: *Date*</span></span>

<span data-ttu-id="fed3a-112">Um valor de *Data* que representa a data inicial de um período para o qual os valores de ativo fixo são calculados.</span><span class="sxs-lookup"><span data-stu-id="fed3a-112">A *Date* value that represents the start date of a period that the fixed asset amounts are calculated for.</span></span>

<span data-ttu-id="fed3a-113">`end date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="fed3a-113">`end date`: *Date*</span></span>

<span data-ttu-id="fed3a-114">Um valor de *Data* que representa a data final de um período para o qual os valores de ativo fixo são calculados.</span><span class="sxs-lookup"><span data-stu-id="fed3a-114">A *Date* value that represents the end date of a period that the fixed asset amounts are calculated for.</span></span>

## <a name="return-values"></a><span data-ttu-id="fed3a-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="fed3a-115">Return values</span></span>

<span data-ttu-id="fed3a-116">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="fed3a-116">*Container (record)*</span></span>

<span data-ttu-id="fed3a-117">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="fed3a-117">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="fed3a-118">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fed3a-118">Example</span></span>

<span data-ttu-id="fed3a-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` retorna o contêiner de dados para o ativo fixo **COMP-000001** que foi preparado para o método de depreciação **Atual** e para o período de **Date1** a **Date2**.</span><span class="sxs-lookup"><span data-stu-id="fed3a-119">`FA_SUM ("COMP-000001", "Current", Date1, Date2)` returns the data container for fixed asset **COMP-000001** that has been prepared for the **Current** value model and for a period from **Date1** to **Date2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fed3a-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="fed3a-120">Additional resources</span></span>

[<span data-ttu-id="fed3a-121">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="fed3a-121">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
