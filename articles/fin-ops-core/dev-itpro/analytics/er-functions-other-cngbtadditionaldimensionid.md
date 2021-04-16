---
title: Função de ER CN_GBT_ADDITIONALDIMENSIONID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CN_GBT_ADDITIONALDIMENSIONID é usada.
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
ms.openlocfilehash: ac0b54476265171b3826e43600f99097701231e1
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744382"
---
# <a name="cn_gbt_additionaldimensionid-er-function"></a><span data-ttu-id="ba77f-103">Função de ER CN_GBT_ADDITIONALDIMENSIONID</span><span class="sxs-lookup"><span data-stu-id="ba77f-103">CN_GBT_ADDITIONALDIMENSIONID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ba77f-104">A função `CN_GBT_ADDITIONALDIMENSIONID` retorna um valor de *Cadeia de caracteres* que representa uma única ID de dimensão financeira obtida da cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="ba77f-104">The `CN_GBT_ADDITIONALDIMENSIONID` function returns a *String* value that represents a single financial dimension ID that is taken from the specified string.</span></span> <span data-ttu-id="ba77f-105">A cadeira de caracteres específicos apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ba77f-105">The specified string presents all dimensions as a comma-separated list of IDs.</span></span>

## <a name="syntax"></a><span data-ttu-id="ba77f-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ba77f-106">Syntax</span></span>

```vb
CN_GBT_ADDITIONALDIMENSIONID (text, number)
```

## <a name="arguments"></a><span data-ttu-id="ba77f-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ba77f-107">Arguments</span></span>

<span data-ttu-id="ba77f-108">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ba77f-108">`text`: *String*</span></span>

<span data-ttu-id="ba77f-109">Um valor de *Cadeia de caracteres* que apresenta todas as dimensões como uma lista de IDs separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ba77f-109">A *String* value that presents all dimensions as a comma-separated list of IDs.</span></span>

<span data-ttu-id="ba77f-110">`number`: Inteiro</span><span class="sxs-lookup"><span data-stu-id="ba77f-110">`number`: Integer</span></span>

<span data-ttu-id="ba77f-111">Um valor *Inteiro* que define o código de sequência da dimensão solicitada na cadeia de caracteres especificada.</span><span class="sxs-lookup"><span data-stu-id="ba77f-111">An *Integer* value that defines the sequence code of the requested dimension in the specified string.</span></span>

## <a name="return-values"></a><span data-ttu-id="ba77f-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ba77f-112">Return values</span></span>

<span data-ttu-id="ba77f-113">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="ba77f-113">*String*</span></span>

<span data-ttu-id="ba77f-114">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="ba77f-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ba77f-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ba77f-115">Example</span></span>

<span data-ttu-id="ba77f-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` retorna **"CC"**.</span><span class="sxs-lookup"><span data-stu-id="ba77f-116">`CN_GBT_AdditionalDimensionID ("AA,BB,CC,DD,EE,FF,GG,HH", 3)` returns **"CC"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba77f-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ba77f-117">Additional resources</span></span>

[<span data-ttu-id="ba77f-118">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="ba77f-118">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]