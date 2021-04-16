---
title: Função de ER TEXT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TEXT é usada.
author: NickSelin
ms.date: 12/10/2019
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
ms.openlocfilehash: 0694480f5d6892d13fe0c0d9ad191cdf2332dfec
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746090"
---
# <a name="text-er-function"></a><span data-ttu-id="9c127-103">Função de ER TEXT</span><span class="sxs-lookup"><span data-stu-id="9c127-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c127-104">A função `TEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9c127-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="9c127-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="9c127-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="9c127-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c127-106">Arguments</span></span>

<span data-ttu-id="9c127-107">`number`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="9c127-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="9c127-108">Um número que deve ser convertido em uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="9c127-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="9c127-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9c127-109">Return values</span></span>

<span data-ttu-id="9c127-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="9c127-110">*String*</span></span>

<span data-ttu-id="9c127-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9c127-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9c127-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9c127-112">Usage notes</span></span>

<span data-ttu-id="9c127-113">Para valores do tipo *Real*, a conversão de cadeia de caracteres é limitada a duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="9c127-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="9c127-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9c127-114">Example</span></span>

<span data-ttu-id="9c127-115">Se a localidade do servidor da instância do Microsoft Dynamics 365 Finance for definida como **EN-US**, `TEXT (NOW ())` retornará a data da sessão atual do Finance, 17 de dezembro de 2015, como a cadeia de caracteres de texto **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="9c127-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="9c127-116">`TEXT (1/3)` retorna **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="9c127-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c127-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9c127-117">Additional resources</span></span>

[<span data-ttu-id="9c127-118">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="9c127-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]