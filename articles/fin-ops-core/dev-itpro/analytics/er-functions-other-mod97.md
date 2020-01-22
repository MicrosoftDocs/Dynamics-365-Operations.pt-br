---
title: Função de ER MOD_97
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) MOD_97 é usada.
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
ms.openlocfilehash: 23e63f6b7999399fd5365c616613cbc603774d53
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916927"
---
# <span data-ttu-id="634dc-103"><a name="MOD_97">Função de ER MOD_97</a></span><span class="sxs-lookup"><span data-stu-id="634dc-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="634dc-104">A função `MOD_97` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor como uma expressão MOD97, com base nos dígitos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="634dc-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="634dc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="634dc-105">Syntax</span></span>

```
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="634dc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="634dc-106">Arguments</span></span>

<span data-ttu-id="634dc-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="634dc-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="634dc-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="634dc-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="634dc-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="634dc-109">Return values</span></span>

<span data-ttu-id="634dc-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="634dc-110">*String*</span></span>

<span data-ttu-id="634dc-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="634dc-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="634dc-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="634dc-112">Example</span></span>

<span data-ttu-id="634dc-113">`MOD_97 ("VEND-200002")` retorna **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="634dc-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="634dc-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="634dc-114">Additional resources</span></span>

[<span data-ttu-id="634dc-115">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="634dc-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
