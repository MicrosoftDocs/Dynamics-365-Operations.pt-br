---
title: Função de ER CHAR
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) CHAR é usada.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b008cf6ddf51d816a17e0fae1fa0db464adeabde
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563189"
---
# <a name="char-er-function"></a><span data-ttu-id="673e5-103">Função de ER CHAR</span><span class="sxs-lookup"><span data-stu-id="673e5-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="673e5-104">A função `CHAR` retorna um valor de *Cadeia de caracteres* que apresenta um caractere único referenciado pelo número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="673e5-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="673e5-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="673e5-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="673e5-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="673e5-106">Arguments</span></span>

<span data-ttu-id="673e5-107">`number`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="673e5-107">`number`: *Integer*</span></span>

<span data-ttu-id="673e5-108">Um número que corresponde a um caractere único esperado.</span><span class="sxs-lookup"><span data-stu-id="673e5-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="673e5-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="673e5-109">Return values</span></span>

<span data-ttu-id="673e5-110">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="673e5-110">*String*</span></span>

<span data-ttu-id="673e5-111">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="673e5-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="673e5-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="673e5-112">Usage notes</span></span>

<span data-ttu-id="673e5-113">A cadeia de caracteres que esta função retorna depende da codificação selecionada no elemento de formato **FILE** pai.</span><span class="sxs-lookup"><span data-stu-id="673e5-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="673e5-114">Para obter uma lista das codificações com suporte, consulte [Classe de codificação](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="673e5-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="673e5-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="673e5-115">Example</span></span>

<span data-ttu-id="673e5-116">`CHAR (255)` retorna **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="673e5-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="673e5-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="673e5-117">Additional resources</span></span>

[<span data-ttu-id="673e5-118">Funções de texto</span><span class="sxs-lookup"><span data-stu-id="673e5-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]