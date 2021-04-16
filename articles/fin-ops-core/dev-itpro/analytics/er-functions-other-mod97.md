---
title: Função de ER MOD_97
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MOD_97 é usada.
author: NickSelin
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
ms.openlocfilehash: 1054407addaf6f7c2a7d2f72bf1479e9dc374389
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5749156"
---
# <a name="mod_97-er-function"></a><span data-ttu-id="84251-103">Função de ER MOD_97</span><span class="sxs-lookup"><span data-stu-id="84251-103">MOD_97 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84251-104">A função `MOD_97` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD97, com base nos dígitos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="84251-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="84251-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="84251-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="84251-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="84251-106">Arguments</span></span>

<span data-ttu-id="84251-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="84251-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="84251-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="84251-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="84251-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="84251-109">Return values</span></span>

<span data-ttu-id="84251-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="84251-110">*String*</span></span>

<span data-ttu-id="84251-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="84251-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="84251-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="84251-112">Example</span></span>

<span data-ttu-id="84251-113">`MOD_97 ("VEND-200002")` retorna **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="84251-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="84251-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="84251-114">Additional resources</span></span>

[<span data-ttu-id="84251-115">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="84251-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]