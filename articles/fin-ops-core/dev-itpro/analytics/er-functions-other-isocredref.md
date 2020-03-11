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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd692720872314d533274f392f84e5ac7d36c7c1
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041368"
---
# <span data-ttu-id="afa58-103"><a name="ISOCREDREF">Função de ER ISOCREDREF</a></span><span class="sxs-lookup"><span data-stu-id="afa58-103"><a name="ISOCREDREF">ISOCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afa58-104">A função `ISOCREDREF` retorna um valor de *Cadeia de caracteres* que representa uma referência de credor ISO (Organização Internacional de Normalização), com base nos dígitos e símbolos alfabéticos do número de fatura especificado.</span><span class="sxs-lookup"><span data-stu-id="afa58-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="afa58-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="afa58-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="afa58-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="afa58-106">Arguments</span></span>

<span data-ttu-id="afa58-107">`invoice number digits`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="afa58-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="afa58-108">Um valor de texto que representa os dígitos de um número de fatura.</span><span class="sxs-lookup"><span data-stu-id="afa58-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="afa58-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="afa58-109">Return values</span></span>

<span data-ttu-id="afa58-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="afa58-110">*String*</span></span>

<span data-ttu-id="afa58-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="afa58-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="afa58-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="afa58-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="afa58-113">Para eliminar símbolos de alfabetos que não são compatíveis com ISO, o argumento `invoice number digits` deve ser traduzido antes de ser passado para esta função.</span><span class="sxs-lookup"><span data-stu-id="afa58-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="afa58-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="afa58-114">Example</span></span>

<span data-ttu-id="afa58-115">`ISOCredRef ("VEND-200002")` retorna **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="afa58-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="afa58-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="afa58-116">Additional resources</span></span>

[<span data-ttu-id="afa58-117">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="afa58-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
