---
title: Função de ER SESSIONNOW
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SESSIONNOW é usada.
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: 47b88a1ca0ea9fd09c2a82963901d9ace78891bb
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746782"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="f02d4-103">Função de ER SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="f02d4-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f02d4-104">A função `SESSIONNOW` retorna um valor de *DateTime* que representa a data e a hora atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f02d4-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="f02d4-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f02d4-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="f02d4-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f02d4-106">Return values</span></span>

<span data-ttu-id="f02d4-107">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="f02d4-107">*DateTime*</span></span>

<span data-ttu-id="f02d4-108">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="f02d4-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="f02d4-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f02d4-109">Example</span></span>

<span data-ttu-id="f02d4-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="f02d4-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f02d4-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f02d4-111">Additional resources</span></span>

[<span data-ttu-id="f02d4-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="f02d4-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]