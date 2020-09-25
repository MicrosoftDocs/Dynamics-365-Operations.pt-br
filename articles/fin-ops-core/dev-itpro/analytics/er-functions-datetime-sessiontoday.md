---
title: Função de ER SESSIONTODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SESSIONTODAY é usada.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 2aa3d5e34e6dcd9b5d4a3fe3f21d7e3285adbcad
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745408"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="82bc9-103">Função de ER SESSIONTODAY</span><span class="sxs-lookup"><span data-stu-id="82bc9-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82bc9-104">A função `SESSIONTODAY` retorna um valor de *Data* que representa a data atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="82bc9-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="82bc9-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="82bc9-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="82bc9-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="82bc9-106">Return values</span></span>

<span data-ttu-id="82bc9-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="82bc9-107">*Date*</span></span>

<span data-ttu-id="82bc9-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="82bc9-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="82bc9-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="82bc9-109">Example</span></span>

<span data-ttu-id="82bc9-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="82bc9-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="82bc9-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="82bc9-111">Additional resources</span></span>

[<span data-ttu-id="82bc9-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="82bc9-112">Date and time functions</span></span>](er-functions-category-datetime.md)
