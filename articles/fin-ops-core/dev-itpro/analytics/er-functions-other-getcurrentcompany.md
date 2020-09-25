---
title: Função de ER GETCURRENTCOMPANY
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) GETCURRENTCOMPANY é usada.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 7e3c164c6d54d8387eed5018219da5fd82c765c8
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744110"
---
# <a name="getcurrentcompany-er-function"></a><span data-ttu-id="6f170-103">Função de ER GETCURRENTCOMPANY</span><span class="sxs-lookup"><span data-stu-id="6f170-103">GETCURRENTCOMPANY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f170-104">A função `GETCURRENTCOMPANY` retorna um valor de *Cadeia de caracteres* que representa o código da entidade legal (empresa) à qual um usuário está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="6f170-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="6f170-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="6f170-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="6f170-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6f170-106">Return values</span></span>

<span data-ttu-id="6f170-107">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="6f170-107">*String*</span></span>

<span data-ttu-id="6f170-108">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="6f170-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="6f170-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6f170-109">Example</span></span>

<span data-ttu-id="6f170-110">`GETCURRENTCOMPANY ()` retorna **USMF** para um usuário que está conectado à empresa **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="6f170-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f170-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="6f170-111">Additional resources</span></span>

[<span data-ttu-id="6f170-112">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="6f170-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
