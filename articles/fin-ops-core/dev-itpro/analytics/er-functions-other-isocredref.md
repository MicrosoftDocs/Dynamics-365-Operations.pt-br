---
title: Função de ER ISOCREDREF
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISOCREDREF é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: a9378028a4b308aae7796b861b37a5f89ddfe49c
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563392"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="eb27b-103">Função de ER ISOCREDREF</span><span class="sxs-lookup"><span data-stu-id="eb27b-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="eb27b-104">A função `ISOCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="eb27b-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="eb27b-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="eb27b-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="eb27b-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="eb27b-106">Arguments</span></span>

<span data-ttu-id="eb27b-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="eb27b-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="eb27b-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="eb27b-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="eb27b-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="eb27b-109">Return values</span></span>

<span data-ttu-id="eb27b-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="eb27b-110">*String*</span></span>

<span data-ttu-id="eb27b-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="eb27b-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="eb27b-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="eb27b-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="eb27b-113">Para eliminar símbolos de alfabetos que não são compatíveis com ISO, o argumento `invoice number digits` deve ser traduzido antes de ser passado para esta função.</span><span class="sxs-lookup"><span data-stu-id="eb27b-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="eb27b-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eb27b-114">Example</span></span>

<span data-ttu-id="eb27b-115">`ISOCredRef ("VEND-200002")` retorna **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="eb27b-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="eb27b-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="eb27b-116">Additional resources</span></span>

[<span data-ttu-id="eb27b-117">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="eb27b-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]