---
title: Função DATETIMEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETIMEFORMAT é usada.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 98919f40751a77465ae26acbd46af4396c588b13
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916398"
---
# <span data-ttu-id="73f97-103"><a name="DATETIMEFORMAT">Função DATETIMEFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="73f97-103"><a name="DATETIMEFORMAT">DATETIMEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="73f97-104">A função `DATETIMEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data/hora determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="73f97-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="73f97-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="73f97-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="73f97-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="73f97-106">Syntax 1</span></span>

```
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="73f97-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="73f97-107">Syntax 2</span></span>

```
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="73f97-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="73f97-108">Arguments</span></span>

<span data-ttu-id="73f97-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="73f97-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="73f97-110">Um valor de data/hora que representa a data e a hora para formatação.</span><span class="sxs-lookup"><span data-stu-id="73f97-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="73f97-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="73f97-111">`format`: *String*</span></span>

<span data-ttu-id="73f97-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="73f97-112">The format of the output string.</span></span>

<span data-ttu-id="73f97-113">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="73f97-113">`culture`: *String*</span></span>

<span data-ttu-id="73f97-114">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="73f97-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="73f97-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="73f97-115">Return values</span></span>

<span data-ttu-id="73f97-116">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="73f97-116">*String*</span></span>

<span data-ttu-id="73f97-117">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="73f97-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="73f97-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="73f97-118">Usage notes</span></span>

<span data-ttu-id="73f97-119">Quando a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="73f97-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="73f97-120">Por exemplo, se a função `DATETIMEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="73f97-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="73f97-121">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="73f97-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="73f97-122">Quando a função `DATETIMEFORMAT` converte um determinado valor de data/hora, ela considera a configuração de fuso horário do usuário do aplicativo que está executando o formato ER no qual a função é chamada pelo contexto.</span><span class="sxs-lookup"><span data-stu-id="73f97-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="73f97-123">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="73f97-123">Example 1</span></span>

<span data-ttu-id="73f97-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="73f97-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="73f97-125">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="73f97-125">Example 2</span></span>

<span data-ttu-id="73f97-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="73f97-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="73f97-127">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="73f97-127">Example 3</span></span>

<span data-ttu-id="73f97-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` retorna o valor de cadeia de caracteres **2019-11-12T08:00:00.0000000-08:00** quando é chamada durante um processo iniciado por um usuário de aplicativo com o valor de fuso horário **(GMT-08:00) Hora do Pacífico (EUA e Canadá)** na seção **Preferências de idioma e país/região**.</span><span class="sxs-lookup"><span data-stu-id="73f97-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="73f97-129">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="73f97-129">Additional resources</span></span>

[<span data-ttu-id="73f97-130">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="73f97-130">Date and time functions</span></span>](er-functions-category-datetime.md)
