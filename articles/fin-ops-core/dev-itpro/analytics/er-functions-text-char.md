---
title: Função de ER CHAR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CHAR é usada.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041219"
---
# <span data-ttu-id="cf5bc-103"><a name="CHAR">Função de ER CHAR</a></span><span class="sxs-lookup"><span data-stu-id="cf5bc-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cf5bc-104">A função `CHAR` retorna um valor de *Cadeia de caracteres* que apresenta um caractere único referenciado pelo número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="cf5bc-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="cf5bc-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="cf5bc-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="cf5bc-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="cf5bc-106">Arguments</span></span>

<span data-ttu-id="cf5bc-107">`number`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="cf5bc-107">`number`: *Integer*</span></span>

<span data-ttu-id="cf5bc-108">Um número que corresponde a um caractere único esperado.</span><span class="sxs-lookup"><span data-stu-id="cf5bc-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="cf5bc-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="cf5bc-109">Return values</span></span>

<span data-ttu-id="cf5bc-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="cf5bc-110">*String*</span></span>

<span data-ttu-id="cf5bc-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="cf5bc-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cf5bc-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="cf5bc-112">Usage notes</span></span>

<span data-ttu-id="cf5bc-113">A cadeia de caracteres que esta função retorna depende da codificação selecionada no elemento de formato **FILE** pai.</span><span class="sxs-lookup"><span data-stu-id="cf5bc-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="cf5bc-114">Para obter uma lista das codificações com suporte, consulte [Classe de codificação](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="cf5bc-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="cf5bc-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="cf5bc-115">Example</span></span>

<span data-ttu-id="cf5bc-116">`CHAR (255)` retorna **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="cf5bc-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cf5bc-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="cf5bc-117">Additional resources</span></span>

[<span data-ttu-id="cf5bc-118">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="cf5bc-118">Text functions</span></span>](er-functions-category-text.md)
