---
title: Função de ER FIRST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) FIRST é usada.
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
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042081"
---
# <span data-ttu-id="26b7c-103"><a name="FIRST">Função de ER FIRST</a></span><span class="sxs-lookup"><span data-stu-id="26b7c-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="26b7c-104">A função `FIRST` retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se essa lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="26b7c-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="26b7c-105">Se a lista estiver vazia, essa função gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="26b7c-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="26b7c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="26b7c-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="26b7c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="26b7c-107">Arguments</span></span>

<span data-ttu-id="26b7c-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="26b7c-108">`list`: *Record list*</span></span>

<span data-ttu-id="26b7c-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="26b7c-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="26b7c-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="26b7c-110">Return values</span></span>

<span data-ttu-id="26b7c-111">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="26b7c-111">*Container (record)*</span></span>

<span data-ttu-id="26b7c-112">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="26b7c-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="26b7c-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="26b7c-113">Example 1</span></span>

<span data-ttu-id="26b7c-114">A expressão `FIRST(SPLIT("ABC",1)).Value` retorna o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="26b7c-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="26b7c-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="26b7c-115">Example 2</span></span>

<span data-ttu-id="26b7c-116">A expressão `FIRST(SPLIT("",1)).Value` gera uma exceção no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="26b7c-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="26b7c-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="26b7c-117">Additional resources</span></span>

[<span data-ttu-id="26b7c-118">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="26b7c-118">List functions</span></span>](er-functions-category-list.md)
