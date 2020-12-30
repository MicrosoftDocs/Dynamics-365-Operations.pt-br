---
title: Função de ER NULLDATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLDATE é usada.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 327a06ab7657c334338073f67cb244cc40bfee31
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682308"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="9c388-103">Função de ER NULLDATE</span><span class="sxs-lookup"><span data-stu-id="9c388-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c388-104">A função `NULLDATE` retorna um valor de *Data* que representa a data **nula** (1º de janeiro de 1900).</span><span class="sxs-lookup"><span data-stu-id="9c388-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="9c388-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9c388-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="9c388-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9c388-106">Return values</span></span>

<span data-ttu-id="9c388-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="9c388-107">*Date*</span></span>

<span data-ttu-id="9c388-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="9c388-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="9c388-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="9c388-109">Example 1</span></span>

<span data-ttu-id="9c388-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` retorna a data **nula**, 1º de janeiro de 1900, como **"1900-01-01"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="9c388-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="9c388-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="9c388-111">Example 2</span></span>

<span data-ttu-id="9c388-112">A expressão `IF( Invoice.DocumentDate = NULLDATE(), true, false)` retorna **Verdadeiro** quando o valor do campo **DocumentDate** é igual à data **nula**.</span><span class="sxs-lookup"><span data-stu-id="9c388-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="9c388-113">Nesse exemplo, **Fatura** é uma fonte de dados de relatório eletrônico (ER) do tipo **Registros de tabela/finanças** e se refere à tabela CustInvoiceJour.</span><span class="sxs-lookup"><span data-stu-id="9c388-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c388-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9c388-114">Additional resources</span></span>

[<span data-ttu-id="9c388-115">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="9c388-115">Date and time functions</span></span>](er-functions-category-datetime.md)
