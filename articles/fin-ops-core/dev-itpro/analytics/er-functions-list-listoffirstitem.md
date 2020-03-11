---
title: Função de ER LISTOFFIRSTITEM
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) LISTOFFIRSTITEM é usada.
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
ms.openlocfilehash: 8cd48732280c9af0b89129a32b42285207f97fb7
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041966"
---
# <span data-ttu-id="d9f23-103"><a name="LISTOFFIRSTITEM">Função de ER LISTOFFIRSTITEM</a></span><span class="sxs-lookup"><span data-stu-id="d9f23-103"><a name="LISTOFFIRSTITEM">LISTOFFIRSTITEM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9f23-104">A função `LISTOFFIRSTITEM` retorna um valor de *Lista de registros* que consiste somente no primeiro registro da lista especificada.</span><span class="sxs-lookup"><span data-stu-id="d9f23-104">The `LISTOFFIRSTITEM` function returns a *Record list* value that consists of only the first record of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9f23-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="d9f23-105">Syntax</span></span>

```vb
LISTOFFIRSTITEM (list)
```

## <a name="arguments"></a><span data-ttu-id="d9f23-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d9f23-106">Arguments</span></span>

<span data-ttu-id="d9f23-107">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="d9f23-107">`list`: *Record list*</span></span>

<span data-ttu-id="d9f23-108">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="d9f23-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d9f23-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d9f23-109">Return values</span></span>

<span data-ttu-id="d9f23-110">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="d9f23-110">*Record list*</span></span>

<span data-ttu-id="d9f23-111">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="d9f23-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="d9f23-112">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d9f23-112">Example</span></span>

<span data-ttu-id="d9f23-113">A expressão `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` retorna o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="d9f23-113">The expression `FIRST( LISTOFFIRSTITEM ( SPLIT ("ABC",1))).Value` returns the text value **"A"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9f23-114">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d9f23-114">Additional resources</span></span>

[<span data-ttu-id="d9f23-115">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="d9f23-115">List functions</span></span>](er-functions-category-list.md)
