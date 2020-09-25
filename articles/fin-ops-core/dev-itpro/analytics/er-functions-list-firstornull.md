---
title: Função de ER FIRSTORNULL
description: Este tópico explica como a função de relatório eletrônico (ER) FIRSTORNULL é usada.
author: NickSelin
manager: kfend
ms.date: 11/29/2019
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
ms.openlocfilehash: e360812c5b0dbfb8df4ab279bf3e0050acebbb25
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745184"
---
# <a name="firstornull-er-function"></a><span data-ttu-id="171cf-103">Função de ER FIRSTORNULL</span><span class="sxs-lookup"><span data-stu-id="171cf-103">FIRSTORNULL ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="171cf-104">A função `FIRSTORNULL` retorna o primeiro registro da lista especificada como um valor de *Contêiner (registro)*, se esse registro não estiver vazio.</span><span class="sxs-lookup"><span data-stu-id="171cf-104">The `FIRSTORNULL` function returns the first record of the specified list as a *Container (record)* value, if that record isn't empty.</span></span> <span data-ttu-id="171cf-105">Se o registro estiver vazio, essa função retornará um valor de *Contêiner (registro)* nulo.</span><span class="sxs-lookup"><span data-stu-id="171cf-105">If the record is empty, this function returns a null *Container (record)* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="171cf-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="171cf-106">Syntax</span></span>

```vb
FIRSTORNULL (list)
```

## <a name="arguments"></a><span data-ttu-id="171cf-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="171cf-107">Arguments</span></span>

<span data-ttu-id="171cf-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="171cf-108">`list`: *Record list*</span></span>

<span data-ttu-id="171cf-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="171cf-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="171cf-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="171cf-110">Return values</span></span>

<span data-ttu-id="171cf-111">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="171cf-111">*Container (record)*</span></span>

<span data-ttu-id="171cf-112">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="171cf-112">The resulting record value.</span></span>

## <a name="example"></a><span data-ttu-id="171cf-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="171cf-113">Example</span></span>

<span data-ttu-id="171cf-114">A expressão `FIRSTORNULL(SPLIT("",1)).Value` retorna uma cadeia de caracteres vazia (**""**).</span><span class="sxs-lookup"><span data-stu-id="171cf-114">The expression `FIRSTORNULL(SPLIT("",1)).Value` returns an empty string (**""**).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="171cf-115">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="171cf-115">Additional resources</span></span>

[<span data-ttu-id="171cf-116">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="171cf-116">List functions</span></span>](er-functions-category-list.md)
