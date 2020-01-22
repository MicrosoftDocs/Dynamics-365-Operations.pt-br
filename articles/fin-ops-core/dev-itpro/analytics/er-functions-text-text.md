---
title: Função de ER TEXT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TEXT é usada.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c26d0c4c8c6290bd2dbb10a288bbd59941a8d98e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915547"
---
# <span data-ttu-id="92fc0-103"><a name="TEXT">Função de ER TEXT</a></span><span class="sxs-lookup"><span data-stu-id="92fc0-103"><a name="TEXT">TEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92fc0-104">A função `TEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="92fc0-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="92fc0-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="92fc0-105">Syntax</span></span>

```
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="92fc0-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="92fc0-106">Arguments</span></span>

<span data-ttu-id="92fc0-107">`number`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="92fc0-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="92fc0-108">Um número que deve ser convertido em uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="92fc0-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="92fc0-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="92fc0-109">Return values</span></span>

<span data-ttu-id="92fc0-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="92fc0-110">*String*</span></span>

<span data-ttu-id="92fc0-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="92fc0-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="92fc0-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="92fc0-112">Usage notes</span></span>

<span data-ttu-id="92fc0-113">Para valores do tipo *Real*, a conversão de cadeia de caracteres é limitada a duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="92fc0-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="92fc0-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="92fc0-114">Example</span></span>

<span data-ttu-id="92fc0-115">Se a localidade do servidor da instância do Microsoft Dynamics 365 Finance for definida como **EN-US**, `TEXT (NOW ())` retornará a data da sessão atual do Finance, 17 de dezembro de 2015, como a cadeia de caracteres de texto **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="92fc0-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="92fc0-116">`TEXT (1/3)` retorna **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="92fc0-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92fc0-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="92fc0-117">Additional resources</span></span>

[<span data-ttu-id="92fc0-118">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="92fc0-118">Text functions</span></span>](er-functions-category-text.md)
