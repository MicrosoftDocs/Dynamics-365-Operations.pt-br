---
title: Função de ER ISVALIDCHARACTERISO7064
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) ISVALIDCHARACTERISO7064 é usada.
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
ms.openlocfilehash: 21962952bb3bdd016831dc5e196af27c69ecc6db
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744062"
---
# <a name="isvalidcharacteriso7064-er-function"></a><span data-ttu-id="81fec-103">Função de ER ISVALIDCHARACTERISO7064</span><span class="sxs-lookup"><span data-stu-id="81fec-103">ISVALIDCHARACTERISO7064 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81fec-104">A função `ISVALIDCHARACTERISO7064` retorna um valor *Booliano* de **TRUE** se a cadeia de caracteres especificada representar um IBAN (Número de Conta Bancária Internacional) válido.</span><span class="sxs-lookup"><span data-stu-id="81fec-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="81fec-105">Caso contrário, ela retorna um valor *Booliano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="81fec-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="81fec-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="81fec-106">Syntax</span></span>

```vb
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="81fec-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81fec-107">Arguments</span></span>

<span data-ttu-id="81fec-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="81fec-108">`text`: *String*</span></span>

<span data-ttu-id="81fec-109">Um valor de texto que representa um IBAN.</span><span class="sxs-lookup"><span data-stu-id="81fec-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="81fec-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="81fec-110">Return values</span></span>

<span data-ttu-id="81fec-111">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="81fec-111">*String*</span></span>

<span data-ttu-id="81fec-112">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="81fec-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="81fec-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="81fec-113">Example</span></span>

<span data-ttu-id="81fec-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` retorna **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="81fec-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="81fec-115">`ISVALIDCHARACTERISO7064 ("AT61")` retorna **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="81fec-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81fec-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="81fec-116">Additional resources</span></span>

[<span data-ttu-id="81fec-117">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="81fec-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
