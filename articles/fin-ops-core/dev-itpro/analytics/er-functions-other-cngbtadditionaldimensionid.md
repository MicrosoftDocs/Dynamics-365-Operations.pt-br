---
title: Função de ER CN_GBT_ADDITIONALDIMENSIONID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CN_GBT_ADDITIONALDIMENSIONID é usada.
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
ms.openlocfilehash: 2395a1932e543e35ced28a2a6e56ab44835de19a
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041529"
---
# <span data-ttu-id="8fd6b-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">Função de ER CN_GBT_ADDITIONALDIMENSIONID</a></span><span class="sxs-lookup"><span data-stu-id="8fd6b-103"><a name="CN_GBT_ADDITIONALDIMENSIONID">CN_GBT_ADDITIONALDIMENSIONID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8fd6b-104">A função `CN_GBT_ADDITIONALDIMENSIONID` retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="8fd6b-105">A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="8fd6b-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8fd6b-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="8fd6b-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8fd6b-107">Arguments</span></span>

<span data-ttu-id="8fd6b-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8fd6b-108">`text`: *String*</span></span>

<span data-ttu-id="8fd6b-109">Um valor de *Cadeia de caracteres* que apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="8fd6b-110">`number`: Inteiro</span><span class="sxs-lookup"><span data-stu-id="8fd6b-110">`number`: Integer</span></span>

<span data-ttu-id="8fd6b-111">Um valor *Inteiro* que define o código de sequência da dimensão solicitada na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="8fd6b-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8fd6b-112">Return values</span></span>

<span data-ttu-id="8fd6b-113">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="8fd6b-113">*String*</span></span>

<span data-ttu-id="8fd6b-114">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="8fd6b-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8fd6b-115">Example</span></span>

<span data-ttu-id="8fd6b-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` retorna **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="8fd6b-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8fd6b-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8fd6b-117">Additional resources</span></span>

[<span data-ttu-id="8fd6b-118">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="8fd6b-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
