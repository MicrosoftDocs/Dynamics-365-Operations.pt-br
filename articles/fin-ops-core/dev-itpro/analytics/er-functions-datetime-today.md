---
title: Função de ER TODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TODAY é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 9288baf4e6123a7c03152f524a852eae9b671dde
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567907"
---
# <a name="today-er-function"></a><span data-ttu-id="c2365-103">Função de ER TODAY</span><span class="sxs-lookup"><span data-stu-id="c2365-103">TODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c2365-104">A função `TODAY` retorna um valor de *Data* que representa a data atual do servidor do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c2365-104">The `TODAY` function returns a *Date* value that represents the current application server date.</span></span>

## <a name="syntax"></a><span data-ttu-id="c2365-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c2365-105">Syntax</span></span>

```xpp
TODAY ()
```

## <a name="return-values"></a><span data-ttu-id="c2365-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c2365-106">Return values</span></span>

<span data-ttu-id="c2365-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="c2365-107">*Date*</span></span>

<span data-ttu-id="c2365-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="c2365-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="c2365-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c2365-109">Example</span></span>

<span data-ttu-id="c2365-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` retorna a data atual do servidor do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="c2365-110">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c2365-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c2365-111">Additional resources</span></span>

[<span data-ttu-id="c2365-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="c2365-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]