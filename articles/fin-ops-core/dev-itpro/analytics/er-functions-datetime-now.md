---
title: Função NOW ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico NOW é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 8e549634b3856777aff610fa0e61c19bcad71dd7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563501"
---
# <a name="now-er-function"></a><span data-ttu-id="30c0a-103">Função NOW ER</span><span class="sxs-lookup"><span data-stu-id="30c0a-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30c0a-104">A função `NOW` retorna um valor de *DateTime* que representa a data e a hora atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="30c0a-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="30c0a-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="30c0a-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="30c0a-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="30c0a-106">Return values</span></span>

<span data-ttu-id="30c0a-107">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="30c0a-107">*DateTime*</span></span>

<span data-ttu-id="30c0a-108">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="30c0a-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="30c0a-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="30c0a-109">Example</span></span>

<span data-ttu-id="30c0a-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="30c0a-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30c0a-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="30c0a-111">Additional resources</span></span>

[<span data-ttu-id="30c0a-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="30c0a-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]