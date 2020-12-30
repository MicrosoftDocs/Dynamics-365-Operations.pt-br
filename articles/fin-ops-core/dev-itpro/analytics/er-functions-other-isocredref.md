---
title: Função de ER ISOCREDREF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISOCREDREF é usada.
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
ms.openlocfilehash: 6c9a75cedcf543b318df2850df3e4a60bac2dc6b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4680677"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="286f0-103">Função de ER ISOCREDREF</span><span class="sxs-lookup"><span data-stu-id="286f0-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="286f0-104">A função `ISOCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="286f0-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="286f0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="286f0-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="286f0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="286f0-106">Arguments</span></span>

<span data-ttu-id="286f0-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="286f0-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="286f0-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="286f0-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="286f0-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="286f0-109">Return values</span></span>

<span data-ttu-id="286f0-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="286f0-110">*String*</span></span>

<span data-ttu-id="286f0-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="286f0-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="286f0-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="286f0-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="286f0-113">Para eliminar símbolos de alfabetos que não são compatíveis com ISO, o argumento `invoice number digits` deve ser traduzido antes de ser passado para esta função.</span><span class="sxs-lookup"><span data-stu-id="286f0-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="286f0-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="286f0-114">Example</span></span>

<span data-ttu-id="286f0-115">`ISOCredRef ("VEND-200002")` retorna **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="286f0-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="286f0-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="286f0-116">Additional resources</span></span>

[<span data-ttu-id="286f0-117">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="286f0-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
