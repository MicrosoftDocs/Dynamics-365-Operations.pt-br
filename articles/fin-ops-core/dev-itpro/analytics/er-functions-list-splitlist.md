---
title: Função de ER SPLITLIST
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLITLIST é usada.
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
ms.openlocfilehash: b324d42a53b35074ba62ccf3df7b77cb4db70450
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917203"
---
# <span data-ttu-id="a9d1c-103"><a name="SPLITLIST">Função de ER SPLITLIST</a></span><span class="sxs-lookup"><span data-stu-id="a9d1c-103"><a name="SPLITLIST">SPLITLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9d1c-104">A função `SPLITLIST` divide a lista especificada em sublistas (ou lotes) e cada uma delas contém o número de registros especificado.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-104">The `SPLITLIST` function splits the specified list into sublists (or batches), each of which contains the specified number of records.</span></span> <span data-ttu-id="a9d1c-105">Em seguida, ela retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-105">It then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9d1c-106">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="a9d1c-106">Syntax</span></span>

```
SPLITLIST (list, number)
```

## <a name="arguments"></a><span data-ttu-id="a9d1c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a9d1c-107">Arguments</span></span>

<span data-ttu-id="a9d1c-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a9d1c-108">`list`: *Record list*</span></span>

<span data-ttu-id="a9d1c-109">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="a9d1c-110">`number`: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a9d1c-110">`number`: *Integer*</span></span>

<span data-ttu-id="a9d1c-111">O número máximo de registros por lote.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-111">The maximum number of records per batch.</span></span>

## <a name="return-values"></a><span data-ttu-id="a9d1c-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a9d1c-112">Return values</span></span>

<span data-ttu-id="a9d1c-113">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="a9d1c-113">*Record list*</span></span>

<span data-ttu-id="a9d1c-114">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-114">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a9d1c-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a9d1c-115">Usage notes</span></span>

<span data-ttu-id="a9d1c-116">A lista de lotes retornada contém os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="a9d1c-116">The list of batches that is returned contains the following elements:</span></span>

 - <span data-ttu-id="a9d1c-117">**Valor:** *Lista*</span><span class="sxs-lookup"><span data-stu-id="a9d1c-117">**Value:** *List*</span></span>

    <span data-ttu-id="a9d1c-118">A lista de registros que pertencem ao lote atual.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-118">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="a9d1c-119">**BatchNumber:** *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="a9d1c-119">**BatchNumber:** *Integer*</span></span>

    <span data-ttu-id="a9d1c-120">O número do lote atual na lista retornada.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-120">The number of the current batch in the returned list.</span></span>

## <a name="example"></a><span data-ttu-id="a9d1c-121">Exemplo</span><span class="sxs-lookup"><span data-stu-id="a9d1c-121">Example</span></span>

<span data-ttu-id="a9d1c-122">Na ilustração a seguir, uma fonte de dados **Linhas** é criada como uma lista de registros com três registros.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-122">In the following illustration, a **Lines** data source is created as a record list that has three records.</span></span> <span data-ttu-id="a9d1c-123">Esta lista é dividida em lotes, cada um contendo até dois registros.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-123">This list is divided into batches, each of which contains up to two records.</span></span>

<a href="./media/picture-splitlist-datasource.jpg"><img src="./media/picture-splitlist-datasource.jpg" alt="Data source that is divided into batches" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

<span data-ttu-id="a9d1c-124">A ilustração a seguir mostra o formato de layout criado.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-124">The following illustration shows the designed format layout.</span></span> <span data-ttu-id="a9d1c-125">Nesse formato de layout, as associações à fonte de dados de **Linhas** são criados para gerar saída no formato XML.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-125">In this format layout, bindings to the **Lines** data source are created to generate output in XML format.</span></span> <span data-ttu-id="a9d1c-126">Esta saída apresenta nós individuais para cada lote e os registros existentes nele.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-126">This output presents individual nodes for each batch and the records in it.</span></span>

<a href="./media/picture-splitlist-format.jpg"><img src="./media/picture-splitlist-format.jpg" alt="Format layout that has bindings to a data source" class="alignnone wp-image-290691 size-full" width="374" height="161" /></a>

<span data-ttu-id="a9d1c-127">A ilustração a seguir mostra o formato o resultado quando o formato criado é executado.</span><span class="sxs-lookup"><span data-stu-id="a9d1c-127">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-splitlist-result.jpg"><img src="./media/picture-splitlist-result.jpg" alt="Result of running the format" class="alignnone wp-image-290701 size-full" width="358" height="191" /></a>

## <a name="additional-resources"></a><span data-ttu-id="a9d1c-128">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a9d1c-128">Additional resources</span></span>

[<span data-ttu-id="a9d1c-129">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="a9d1c-129">List functions</span></span>](er-functions-category-list.md)