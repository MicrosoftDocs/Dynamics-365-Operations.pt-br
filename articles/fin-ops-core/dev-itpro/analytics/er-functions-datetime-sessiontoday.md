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
ms.openlocfilehash: 483ff46a27068bc2d70c80a848f0329861c914b3
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042247"
---
# <span data-ttu-id="8ebb7-103"><a name="SESSIONTODAY">Função de ER SESSIONTODAY</a></span><span class="sxs-lookup"><span data-stu-id="8ebb7-103"><a name="SESSIONTODAY">SESSIONTODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8ebb7-104">A função `SESSIONTODAY` retorna um valor de *Data* que representa a data atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="8ebb7-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="8ebb7-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="8ebb7-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="8ebb7-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8ebb7-106">Return values</span></span>

<span data-ttu-id="8ebb7-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="8ebb7-107">*Date*</span></span>

<span data-ttu-id="8ebb7-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="8ebb7-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="8ebb7-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8ebb7-109">Example</span></span>

<span data-ttu-id="8ebb7-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="8ebb7-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8ebb7-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="8ebb7-111">Additional resources</span></span>

[<span data-ttu-id="8ebb7-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="8ebb7-112">Date and time functions</span></span>](er-functions-category-datetime.md)
