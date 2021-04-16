---
title: Função de ER NULLDATETIME
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) NULLDATETIME é usada.
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
ms.openlocfilehash: f7282b7c161b6e183186ba81e6bcf7b34ce6e612
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746810"
---
# <a name="nulldatetime-er-function"></a><span data-ttu-id="7b2a6-103">Função de ER NULLDATETIME</span><span class="sxs-lookup"><span data-stu-id="7b2a6-103">NULLDATETIME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b2a6-104">A função `NULLDATETIME` retorna um valor de *DateTime* que representa o valor de data/hora **nulo** (1º de janeiro de 1900) no Tempo Universal Coordenado (Horário do Meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="7b2a6-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="7b2a6-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7b2a6-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="7b2a6-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7b2a6-106">Return values</span></span>

<span data-ttu-id="7b2a6-107">*Data/Hora*</span><span class="sxs-lookup"><span data-stu-id="7b2a6-107">*DateTime*</span></span>

<span data-ttu-id="7b2a6-108">O valor de data/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="7b2a6-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="7b2a6-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7b2a6-109">Example</span></span>

<span data-ttu-id="7b2a6-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` retorna o valor de cadeia de caracteres **1900-01-01T00:00:00.0000000+00:00** quando é chamada durante um processo iniciado por um usuário de aplicativo com o valor de fuso horário **(GMT) Tempo Universal Coordenado** na seção **Preferências de idioma e país/região**.</span><span class="sxs-lookup"><span data-stu-id="7b2a6-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b2a6-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7b2a6-111">Additional resources</span></span>

[<span data-ttu-id="7b2a6-112">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="7b2a6-112">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]