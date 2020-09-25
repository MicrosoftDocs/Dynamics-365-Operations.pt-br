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
ms.openlocfilehash: 20313133ce29b8d5048814ff78ce4ea4f5c54d4a
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743679"
---
# <a name="text-er-function"></a><span data-ttu-id="c35f2-103">Função de ER TEXT</span><span class="sxs-lookup"><span data-stu-id="c35f2-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c35f2-104">A função `TEXT` retorna o número especificado como um valor de *Cadeia de caracteres* após ele ser convertido em uma cadeia de caracteres de texto que é formatada de acordo com as configurações de localidade do servidor da instância atual do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c35f2-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="c35f2-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c35f2-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="c35f2-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c35f2-106">Arguments</span></span>

<span data-ttu-id="c35f2-107">`number`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="c35f2-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="c35f2-108">Um número que deve ser convertido em uma cadeia de caracteres de texto.</span><span class="sxs-lookup"><span data-stu-id="c35f2-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="c35f2-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c35f2-109">Return values</span></span>

<span data-ttu-id="c35f2-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="c35f2-110">*String*</span></span>

<span data-ttu-id="c35f2-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c35f2-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c35f2-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="c35f2-112">Usage notes</span></span>

<span data-ttu-id="c35f2-113">Para valores do tipo *Real*, a conversão de cadeia de caracteres é limitada a duas casas decimais.</span><span class="sxs-lookup"><span data-stu-id="c35f2-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="c35f2-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c35f2-114">Example</span></span>

<span data-ttu-id="c35f2-115">Se a localidade do servidor da instância do Microsoft Dynamics 365 Finance for definida como **EN-US**, `TEXT (NOW ())` retornará a data da sessão atual do Finance, 17 de dezembro de 2015, como a cadeia de caracteres de texto **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="c35f2-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="c35f2-116">`TEXT (1/3)` retorna **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="c35f2-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c35f2-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c35f2-117">Additional resources</span></span>

[<span data-ttu-id="c35f2-118">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="c35f2-118">Text functions</span></span>](er-functions-category-text.md)
