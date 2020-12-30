---
title: Função de ER EMPTYRECORD
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) EMPTYRECORD é usada.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d50b31fcbbb99050fca46b0a5ce10cc3fd243691
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684802"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="3cd5c-103">Função de ER EMPTYRECORD</span><span class="sxs-lookup"><span data-stu-id="3cd5c-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3cd5c-104">A função `EMPTYRECORD` retorna um valor de *Contêiner (registro)* nulo que tem a mesma estrutura do registro ou da lista de registros especificada.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="3cd5c-105">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="3cd5c-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="3cd5c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3cd5c-106">Arguments</span></span>

<span data-ttu-id="3cd5c-107">`list`: *Lista de registros* ou *Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="3cd5c-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="3cd5c-108">O caminho válido de uma fonte de dados do tipo *Lista de registros* ou *Contêiner (registro)*.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="3cd5c-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="3cd5c-109">Return values</span></span>

<span data-ttu-id="3cd5c-110">*Contêiner (registro)*</span><span class="sxs-lookup"><span data-stu-id="3cd5c-110">*Container (record)*</span></span>

<span data-ttu-id="3cd5c-111">O valor de registro resultante.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="3cd5c-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="3cd5c-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="3cd5c-113">Um registro nulo é um registro no qual todos os campos tem um valor vazio.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="3cd5c-114">Um valor vazio é **0** (zero) para número, uma sequência de caracteres vazia para sequência de caracteres e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="3cd5c-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3cd5c-115">Example</span></span>

<span data-ttu-id="3cd5c-116">`EMPTYRECORD (SPLIT ("abc", 1))` retorna um novo registro vazio que tem a mesma estrutura da lista retornada pela função `SPLIT`.</span><span class="sxs-lookup"><span data-stu-id="3cd5c-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="3cd5c-117">Para obter mais informações, consulte [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="3cd5c-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3cd5c-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="3cd5c-118">Additional resources</span></span>

[<span data-ttu-id="3cd5c-119">Funções de registro</span><span class="sxs-lookup"><span data-stu-id="3cd5c-119">Record functions</span></span>](er-functions-category-record.md)
