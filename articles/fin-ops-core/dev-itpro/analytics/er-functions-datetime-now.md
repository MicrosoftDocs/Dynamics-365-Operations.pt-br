---
title: Função NOW ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico NOW é usada.
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
ms.openlocfilehash: 0c3cfefd36db44608f05225746704aa3fbe4fc2c
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682356"
---
# <a name="now-er-function"></a><span data-ttu-id="8a3fc-103">Função NOW ER</span><span class="sxs-lookup"><span data-stu-id="8a3fc-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8a3fc-104">A função `NOW` retorna um valor de *DateTime* que representa a data e a hora atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8a3fc-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="8a3fc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8a3fc-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="8a3fc-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8a3fc-106">Return values</span></span>

<span data-ttu-id="8a3fc-107">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="8a3fc-107">*DateTime*</span></span>

<span data-ttu-id="8a3fc-108">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="8a3fc-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="8a3fc-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8a3fc-109">Example</span></span>

<span data-ttu-id="8a3fc-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="8a3fc-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a3fc-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8a3fc-111">Additional resources</span></span>

[<span data-ttu-id="8a3fc-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="8a3fc-112">Date and time functions</span></span>](er-functions-category-datetime.md)
