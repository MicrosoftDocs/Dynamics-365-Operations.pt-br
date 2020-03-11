---
title: Função de ER TABLENAME2ID
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) TABLENAME2ID é usada.
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
ms.openlocfilehash: 951de1d1505508ebb6abeff5b80ecef10573e117
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041253"
---
# <span data-ttu-id="5e819-103"><a name="TABLENAME2ID">Função de ER TABLENAME2ID</a></span><span class="sxs-lookup"><span data-stu-id="5e819-103"><a name="TABLENAME2ID">TABLENAME2ID ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e819-104">A função `TABLENAME2ID` retorna uma representação numérica da ID da tabela para o nome de tabela especificado como um valor *Inteiro*.</span><span class="sxs-lookup"><span data-stu-id="5e819-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e819-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="5e819-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="5e819-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5e819-106">Arguments</span></span>

<span data-ttu-id="5e819-107">`text`: *Cadeia de caracteres*</span><span class="sxs-lookup"><span data-stu-id="5e819-107">`text`: *String*</span></span>

<span data-ttu-id="5e819-108">Um valor de texto que representa um nome de tabela válido.</span><span class="sxs-lookup"><span data-stu-id="5e819-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e819-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5e819-109">Return values</span></span>

<span data-ttu-id="5e819-110">*Inteiro*</span><span class="sxs-lookup"><span data-stu-id="5e819-110">*Integer*</span></span>

<span data-ttu-id="5e819-111">O valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="5e819-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5e819-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5e819-112">Usage notes</span></span>

<span data-ttu-id="5e819-113">A execução desta função pode ter resultados diferentes em instâncias diferentes do Microsoft Dynamics 365 Finance, mesmo que o mesmo nome de empresa seja usado.</span><span class="sxs-lookup"><span data-stu-id="5e819-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="5e819-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="5e819-114">Example</span></span>

<span data-ttu-id="5e819-115">`TABLENAME2ID ("Intrastat")` retorna **1510**.</span><span class="sxs-lookup"><span data-stu-id="5e819-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e819-116">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5e819-116">Additional resources</span></span>

[<span data-ttu-id="5e819-117">Outras funções (específicas de domínio comercial)</span><span class="sxs-lookup"><span data-stu-id="5e819-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
