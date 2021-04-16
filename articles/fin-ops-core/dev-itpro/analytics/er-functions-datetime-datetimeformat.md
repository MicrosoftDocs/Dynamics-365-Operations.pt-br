---
title: Função DATETIMEFORMAT ER
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) DATETIMEFORMAT é usada.
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 859753c04e3b3d3b61d9a61edaf396637ed5a003
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746978"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="4fd6b-103">Função DATETIMEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="4fd6b-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4fd6b-104">A função `DATETIMEFORMAT` retorna um valor de *Cadeia de caracteres* que apresenta um valor de data/hora determinado como texto no formato especificado e em uma [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="4fd6b-105">Para obter informações sobre os formatos com suporte, consulte [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="4fd6b-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="4fd6b-106">Sintaxe 1</span><span class="sxs-lookup"><span data-stu-id="4fd6b-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="4fd6b-107">Sintaxe 2</span><span class="sxs-lookup"><span data-stu-id="4fd6b-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="4fd6b-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4fd6b-108">Arguments</span></span>

<span data-ttu-id="4fd6b-109">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="4fd6b-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="4fd6b-110">Um valor de data/hora que representa a data e a hora para formatação.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="4fd6b-111">`format`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4fd6b-111">`format`: *String*</span></span>

<span data-ttu-id="4fd6b-112">O formato da cadeia de caracteres de saída.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="4fd6b-113">A cadeia de caracteres de formato diferencia maiúsculas de minúsculas quando você usa um formato padrão ou um formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="4fd6b-114">Por exemplo, o especificador de formato "d" [padrão](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) retorna a data usando o padrão de data abreviada, enquanto o especificador de formato "D" padrão retorna a data usando o padrão de data por extenso.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="4fd6b-115">Além disso, o especificador de formato "M" [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) retorna o mês de 1 a 12, enquanto o especificador "m" de formato personalizado retorna o minuto de 0 a 59.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="4fd6b-116">`culture`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4fd6b-116">`culture`: *String*</span></span>

<span data-ttu-id="4fd6b-117">A cultura a ser usada para formatação.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="4fd6b-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4fd6b-118">Return values</span></span>

<span data-ttu-id="4fd6b-119">*Sequência de caracteres*</span><span class="sxs-lookup"><span data-stu-id="4fd6b-119">*String*</span></span>

<span data-ttu-id="4fd6b-120">O valor da cadeia de caracteres resultante.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="4fd6b-121">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="4fd6b-121">Usage notes</span></span>

<span data-ttu-id="4fd6b-122">Se a cultura não é definida como um argumento da função chamada, o valor de `culture` é definido pelo contexto de chamada.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="4fd6b-123">Por exemplo, se a função `DATETIMEFORMAT` for chamada usando a sintaxe 1 em um formato de relatório eletrônico (ER) para um elemento **FILE** de arquivo configurado para usar a cultura alemã, a conversão será feita usando a cultura alemã.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="4fd6b-124">O valor padrão `culture` é **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="4fd6b-125">Quando a função `DATETIMEFORMAT` converte um determinado valor de data/hora, ela considera a configuração de fuso horário do usuário do aplicativo que está executando o formato ER no qual a função é chamada pelo contexto.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="4fd6b-126">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="4fd6b-126">Example 1</span></span>

<span data-ttu-id="4fd6b-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` retorna o valor da data/hora atual do servidor do aplicativo, 24 de dezembro de 2015, como **"24-12-2015"**, com base no formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="4fd6b-128">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="4fd6b-128">Example 2</span></span>

<span data-ttu-id="4fd6b-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` retorna o valor de data/hora atual da sessão do aplicativo, 24 de dezembro de 2015, como **"24.12.2015"**, com base na cultura alemã selecionada e no formato especificado.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="4fd6b-130">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="4fd6b-130">Example 3</span></span>

<span data-ttu-id="4fd6b-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` retorna o valor de cadeia de caracteres **2019-11-12T08:00:00.0000000-08:00** quando a função é chamada durante um processo iniciado por um usuário de aplicativo com o valor de fuso horário **(GMT-08:00) Hora do Pacífico (EUA e Canadá)** na seção **Preferências de idioma e país/região**.</span><span class="sxs-lookup"><span data-stu-id="4fd6b-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4fd6b-132">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4fd6b-132">Additional resources</span></span>

[<span data-ttu-id="4fd6b-133">Funções de data e de hora</span><span class="sxs-lookup"><span data-stu-id="4fd6b-133">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]