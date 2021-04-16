---
title: Função de ER SESSIONTODAY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SESSIONTODAY é usada.
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
ms.openlocfilehash: 6d0fcbbf1a1fb0809e3f76161314f38bcd8a74aa
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746762"
---
# <a name="sessiontoday-er-function"></a><span data-ttu-id="64fec-103">Função de ER SESSIONTODAY</span><span class="sxs-lookup"><span data-stu-id="64fec-103">SESSIONTODAY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64fec-104">A função `SESSIONTODAY` retorna um valor de *Data* que representa a data atual da sessão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="64fec-104">The `SESSIONTODAY` function returns a *Date* value that represents the current application session date.</span></span>

## <a name="syntax"></a><span data-ttu-id="64fec-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="64fec-105">Syntax</span></span>

```vb
SESSIONTODAY ()
```

## <a name="return-values"></a><span data-ttu-id="64fec-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="64fec-106">Return values</span></span>

<span data-ttu-id="64fec-107">*Data*</span><span class="sxs-lookup"><span data-stu-id="64fec-107">*Date*</span></span>

<span data-ttu-id="64fec-108">O valor de data resultante.</span><span class="sxs-lookup"><span data-stu-id="64fec-108">The resulting date value.</span></span>

## <a name="example"></a><span data-ttu-id="64fec-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="64fec-109">Example</span></span>

<span data-ttu-id="64fec-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` retorna a data atual da sessão do aplicativo, 24 de dezembro de 2015, como a cadeia de caracteres **"24-12-2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="64fec-110">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64fec-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="64fec-111">Additional resources</span></span>

[<span data-ttu-id="64fec-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="64fec-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]