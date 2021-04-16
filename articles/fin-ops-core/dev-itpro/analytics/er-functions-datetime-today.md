---
title: Função de ER TODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TODAY é usada.
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 45ee4282acf4d6a5febe4b74b6955410e73e86a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746738"
---
# <a name="today-er-function"></a><span data-ttu-id="a11cc-103">Função de ER TODAY</span><span class="sxs-lookup"><span data-stu-id="a11cc-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a11cc-104">A função `TODAY` retorna um valor de *Data* que representa a data atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="a11cc-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="a11cc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a11cc-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="a11cc-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a11cc-106">Return values</span></span>

<span data-ttu-id="a11cc-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="a11cc-107">*Date*</span></span>

<span data-ttu-id="a11cc-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="a11cc-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="a11cc-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a11cc-109">Example</span></span>

<span data-ttu-id="a11cc-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="a11cc-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a11cc-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a11cc-111">Additional resources</span></span>

[<span data-ttu-id="a11cc-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="a11cc-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]