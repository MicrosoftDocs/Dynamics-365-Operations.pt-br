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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 38908c63c35465747505479bc983ada891f9e2bf
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686800"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="59e8e-103">Função de ER CN_GBT_ADDITIONALDIMENSIONID</span><span class="sxs-lookup"><span data-stu-id="59e8e-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59e8e-104">A função `CN_GBT_ADDITIONALDIMENSIONID` retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="59e8e-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="59e8e-105">A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="59e8e-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="59e8e-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="59e8e-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="59e8e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="59e8e-107">Arguments</span></span>

<span data-ttu-id="59e8e-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="59e8e-108">`text`: *String*</span></span>

<span data-ttu-id="59e8e-109">Um valor de *Cadeia de caracteres* que apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="59e8e-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="59e8e-110">`number`: Inteiro</span><span class="sxs-lookup"><span data-stu-id="59e8e-110">`number`: Integer</span></span>

<span data-ttu-id="59e8e-111">Um valor *Inteiro* que define o código de sequência da dimensão solicitada na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="59e8e-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="59e8e-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="59e8e-112">Return values</span></span>

<span data-ttu-id="59e8e-113">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="59e8e-113">*String*</span></span>

<span data-ttu-id="59e8e-114">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="59e8e-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="59e8e-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="59e8e-115">Example</span></span>

<span data-ttu-id="59e8e-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` retorna **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="59e8e-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59e8e-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="59e8e-117">Additional resources</span></span>

[<span data-ttu-id="59e8e-118">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="59e8e-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
