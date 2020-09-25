---
title: Função de ER JSONVALUE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) JSONVALUE é usada.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 985a7e4f46756e595580d77ac904c883c305b04a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743798"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="dc295-103">Função de ER JSONVALUE</span><span class="sxs-lookup"><span data-stu-id="dc295-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dc295-104">A função `JSONVALUE` analisa os dados no formato JSON (JavaScript Object Notation) que são acessados no caminho especificado e extrai um valor escalar que tem a ID especificada.</span><span class="sxs-lookup"><span data-stu-id="dc295-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="dc295-105">Em seguida, ela retorna o valor escalar extraído como um valor de *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="dc295-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="dc295-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dc295-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="dc295-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dc295-107">Arguments</span></span>

<span data-ttu-id="dc295-108">`input`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dc295-108">`input`: *String*</span></span>

<span data-ttu-id="dc295-109">O caminho válido de uma fonte de dados do tipo *Cadeia de caracteres* que contém dados JSON.</span><span class="sxs-lookup"><span data-stu-id="dc295-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="dc295-110">`path`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dc295-110">`path`: *String*</span></span>

<span data-ttu-id="dc295-111">O identificador de um valor escalar de dados JSON.</span><span class="sxs-lookup"><span data-stu-id="dc295-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="dc295-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dc295-112">Return values</span></span>

<span data-ttu-id="dc295-113">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="dc295-113">*String*</span></span>

<span data-ttu-id="dc295-114">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="dc295-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="dc295-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="dc295-115">Example</span></span>

<span data-ttu-id="dc295-116">A fonte de dados **JsonField** contém os seguintes dados no formato JSON: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="dc295-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="dc295-117">Nesse caso, a expressão `JSONVALUE (JsonField, "BuildNumber")` retorna o seguinte valor do tipo de dados *Cadeia de caracteres*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="dc295-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dc295-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dc295-118">Additional resources</span></span>

[<span data-ttu-id="dc295-119">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="dc295-119">Text functions</span></span>](er-functions-category-text.md)
