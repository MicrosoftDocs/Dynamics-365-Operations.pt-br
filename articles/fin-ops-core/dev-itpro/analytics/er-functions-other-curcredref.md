---
title: Função de ER CURCREDREF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CURCREDREF é usada.
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
ms.openlocfilehash: 6e684a8e063cb3c049d13005cbcf6ebbe688af00
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041483"
---
# <span data-ttu-id="3554a-103"><a name="CURCREDREF">Função de ER CURCREDREF</a></span><span class="sxs-lookup"><span data-stu-id="3554a-103"><a name="CURCREDREF">CURCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3554a-104">A função `CURCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor, com base nos dígitos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="3554a-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="3554a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3554a-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="3554a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3554a-106">Arguments</span></span>

<span data-ttu-id="3554a-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="3554a-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="3554a-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="3554a-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="3554a-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="3554a-109">Return values</span></span>

<span data-ttu-id="3554a-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="3554a-110">*String*</span></span>

<span data-ttu-id="3554a-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="3554a-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="3554a-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3554a-112">Example</span></span>

<span data-ttu-id="3554a-113">`CURCredRef ("VEND-200002")` retorna **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="3554a-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3554a-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3554a-114">Additional resources</span></span>

[<span data-ttu-id="3554a-115">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="3554a-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
