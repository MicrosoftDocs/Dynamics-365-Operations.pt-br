---
title: Função de ER CONCATENATE
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CONCATENATE é usada.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f1a47a05127412588f4628cb425eab0379493c3c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746467"
---
# <a name="concatenate-er-function"></a><span data-ttu-id="2f571-103">Função de ER CONCATENATE</span><span class="sxs-lookup"><span data-stu-id="2f571-103">CONCATENATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2f571-104">A função `CONCATENATE` retorna todas as cadeias de caracteres de texto especificadas como um valor de *Cadeia de caracteres* depois que elas são unidas em uma cadeias de caracteres.</span><span class="sxs-lookup"><span data-stu-id="2f571-104">The `CONCATENATE` function returns all the specified text strings as a *String* value after they have been joined into one string.</span></span>

## <a name="syntax"></a><span data-ttu-id="2f571-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="2f571-105">Syntax</span></span>

```vb
CONCATENATE (text 1[, text 2, …, text N])
```

## <a name="arguments"></a><span data-ttu-id="2f571-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2f571-106">Arguments</span></span>

<span data-ttu-id="2f571-107">`text 1`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="2f571-107">`text 1`: *String*</span></span>

<span data-ttu-id="2f571-108">Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="2f571-108">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="2f571-109">Esse argumento é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="2f571-109">This argument is required.</span></span>

<span data-ttu-id="2f571-110">`text N`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="2f571-110">`text N`: *String*</span></span>

<span data-ttu-id="2f571-111">Uma referência a uma fonte de dados do tipo *Cadeia de caracteres*.</span><span class="sxs-lookup"><span data-stu-id="2f571-111">A reference to a data source of the *String* data type.</span></span> <span data-ttu-id="2f571-112">Esses argumentos adicionais são opcionais.</span><span class="sxs-lookup"><span data-stu-id="2f571-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="2f571-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2f571-113">Return values</span></span>

<span data-ttu-id="2f571-114">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="2f571-114">*String*</span></span>

<span data-ttu-id="2f571-115">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="2f571-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2f571-116">Exemplo</span><span class="sxs-lookup"><span data-stu-id="2f571-116">Example</span></span>

<span data-ttu-id="2f571-117">`CONCATENATE ("abc", "def")` retorna **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="2f571-117">`CONCATENATE ("abc", "def")` returns **"abcdef"**.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2f571-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="2f571-118">Usage notes</span></span>

<span data-ttu-id="2f571-119">A expressão `"abc" & "def"` também retorna **"abcdef"**.</span><span class="sxs-lookup"><span data-stu-id="2f571-119">The expression `"abc" & "def"` also returns **"abcdef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2f571-120">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="2f571-120">Additional resources</span></span>

[<span data-ttu-id="2f571-121">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="2f571-121">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]