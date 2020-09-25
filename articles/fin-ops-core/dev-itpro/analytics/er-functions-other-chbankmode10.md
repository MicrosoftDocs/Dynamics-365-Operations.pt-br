---
title: Função de ER CH_BANK_MOD_10
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CH_BANK_MOD_10 é usada.
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
ms.openlocfilehash: c18a7f96096fbc6bbc7b6d15135c11bd70960d26
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744461"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="6b3d9-103">Função de ER CH_BANK_MOD_10</span><span class="sxs-lookup"><span data-stu-id="6b3d9-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6b3d9-104">A função `CH_BANK_MOD_10` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD10, com base nos dígitos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="6b3d9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6b3d9-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="6b3d9-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6b3d9-106">Arguments</span></span>

<span data-ttu-id="6b3d9-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="6b3d9-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="6b3d9-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="6b3d9-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6b3d9-109">Return values</span></span>

<span data-ttu-id="6b3d9-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="6b3d9-110">*String*</span></span>

<span data-ttu-id="6b3d9-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6b3d9-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6b3d9-112">Example</span></span>

<span data-ttu-id="6b3d9-113">`CH_BANK_MOD_10 ("VEND-200002")` retorna **3**.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6b3d9-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6b3d9-114">Additional resources</span></span>

[<span data-ttu-id="6b3d9-115">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="6b3d9-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
