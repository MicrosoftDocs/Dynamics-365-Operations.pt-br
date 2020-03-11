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
ms.openlocfilehash: d91caff1a1b89e060a16833e53f3647208ed3826
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041414"
---
# <span data-ttu-id="7b079-103"><a name="GETCURRENTCOMPANY">Função de ER GETCURRENTCOMPANY</a></span><span class="sxs-lookup"><span data-stu-id="7b079-103"><a name="GETCURRENTCOMPANY">GETCURRENTCOMPANY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b079-104">A função `GETCURRENTCOMPANY` retorna um valor de *Cadeia de caracteres* que representa o código da entidade legal (empresa) à qual um usuário está conectado no momento.</span><span class="sxs-lookup"><span data-stu-id="7b079-104">The `GETCURRENTCOMPANY` function returns a *String* value that represents the code for the legal entity (company) that a user is currently signed in to.</span></span>

## <a name="syntax"></a><span data-ttu-id="7b079-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="7b079-105">Syntax</span></span>

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a><span data-ttu-id="7b079-106">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7b079-106">Return values</span></span>

<span data-ttu-id="7b079-107">*Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="7b079-107">*String*</span></span>

<span data-ttu-id="7b079-108">O valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="7b079-108">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="7b079-109">Exemplo</span><span class="sxs-lookup"><span data-stu-id="7b079-109">Example</span></span>

<span data-ttu-id="7b079-110">`GETCURRENTCOMPANY ()` retorna **USMF** para um usuário que está conectado à empresa **Contoso Entertainment System USA**.</span><span class="sxs-lookup"><span data-stu-id="7b079-110">`GETCURRENTCOMPANY ()` returns **USMF** for a user who is signed in to the **Contoso Entertainment System USA** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b079-111">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="7b079-111">Additional resources</span></span>

[<span data-ttu-id="7b079-112">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="7b079-112">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
