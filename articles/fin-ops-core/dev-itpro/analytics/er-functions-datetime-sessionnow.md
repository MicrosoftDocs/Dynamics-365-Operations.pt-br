---
title: Função de ER SESSIONNOW
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SESSIONNOW é usada.
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 00c41564b18eed477e1cefb0bc3bb2bca3fa6fdd
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745456"
---
# <a name="sessionnow-er-function"></a><span data-ttu-id="22534-103">Função de ER SESSIONNOW</span><span class="sxs-lookup"><span data-stu-id="22534-103">SESSIONNOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="22534-104">A função `SESSIONNOW` retorna um valor de *DateTime* que representa a data e a hora atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="22534-104">The `SESSIONNOW` function returns a *DateTime* value that represents the current application session date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="22534-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="22534-105">Syntax</span></span>

```vb
SESSIONNOW ()
```

## <a name="return-values"></a><span data-ttu-id="22534-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="22534-106">Return values</span></span>

<span data-ttu-id="22534-107">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="22534-107">*DateTime*</span></span>

<span data-ttu-id="22534-108">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="22534-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="22534-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="22534-109">Example</span></span>

<span data-ttu-id="22534-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="22534-110">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="22534-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="22534-111">Additional resources</span></span>

[<span data-ttu-id="22534-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="22534-112">Date and time functions</span></span>](er-functions-category-datetime.md)
