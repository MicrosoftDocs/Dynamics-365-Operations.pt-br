---
title: Função de ER TODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TODAY é usada.
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
ms.openlocfilehash: 94ef15d1971287e8bf13944bc8f693b567950031
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411428"
---
# <a name=""></a><span data-ttu-id="d6b68-103"><a name="TODAY">Função de ER TODAY</a></span><span class="sxs-lookup"><span data-stu-id="d6b68-103"><a name="TODAY">TODAY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d6b68-104">A função `TODAY` retorna um valor de *Data* que representa a data atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d6b68-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="d6b68-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d6b68-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="d6b68-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d6b68-106">Return values</span></span>

<span data-ttu-id="d6b68-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="d6b68-107">*Date*</span></span>

<span data-ttu-id="d6b68-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="d6b68-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="d6b68-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d6b68-109">Example</span></span>

<span data-ttu-id="d6b68-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="d6b68-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d6b68-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d6b68-111">Additional resources</span></span>

[<span data-ttu-id="d6b68-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="d6b68-112">Date and time functions</span></span>](er-functions-category-datetime.md)
