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
ms.openlocfilehash: 3ed0e0aaf29e2a67a4842d71121f1adc24f524f7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745216"
---
# <a name="first-er-function"></a><span data-ttu-id="dba79-103">Função de ER FIRST</span><span class="sxs-lookup"><span data-stu-id="dba79-103">FIRST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dba79-104">A função `FIRST` retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se essa lista não estiver vazia.</span><span class="sxs-lookup"><span data-stu-id="dba79-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="dba79-105">Se a lista estiver vazia, essa função gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="dba79-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="dba79-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="dba79-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="dba79-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dba79-107">Arguments</span></span>

<span data-ttu-id="dba79-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="dba79-108">`list`: *Record list*</span></span>

<span data-ttu-id="dba79-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="dba79-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="dba79-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dba79-110">Return values</span></span>

<span data-ttu-id="dba79-111">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="dba79-111">*Container (record)*</span></span>

<span data-ttu-id="dba79-112">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="dba79-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="dba79-113">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="dba79-113">Example 1</span></span>

<span data-ttu-id="dba79-114">A expressão `FIRST(SPLIT("ABC",1)).Value` retorna o valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="dba79-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="dba79-115">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="dba79-115">Example 2</span></span>

<span data-ttu-id="dba79-116">A expressão `FIRST(SPLIT("",1)).Value` gera uma exceção no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="dba79-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dba79-117">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="dba79-117">Additional resources</span></span>

[<span data-ttu-id="dba79-118">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="dba79-118">List functions</span></span>](er-functions-category-list.md)
