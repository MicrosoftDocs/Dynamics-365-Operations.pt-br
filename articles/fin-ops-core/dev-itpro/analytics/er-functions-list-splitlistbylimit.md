---
title: Função de ER SPLITLISTBYLIMIT
description: Este tópico fornece informações sobre como a função de relatório eletrônico (ER) SPLITLISTBYLIMIT é usada.
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
ms.openlocfilehash: f9b740b7d46fcfdf0d0b08d03411017cf909265d
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916168"
---
# <span data-ttu-id="ff5a7-103"><a name="SPLITLISTBYLIMIT">Função de ER SPLITLISTBYLIMIT</a></span><span class="sxs-lookup"><span data-stu-id="ff5a7-103"><a name="SPLITLISTBYLIMIT">SPLITLISTBYLIMIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ff5a7-104">A função `SPLITLISTBYLIMIT` divide a lista especificada em uma nova lista de sublistas (lotes).</span><span class="sxs-lookup"><span data-stu-id="ff5a7-104">The `SPLITLISTBYLIMIT` function splits the specified list into a new list of sublists (batches).</span></span> <span data-ttu-id="ff5a7-105">O número de registros em cada lote é calculado dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-105">The number of records in each batch is dynamically calculated.</span></span> <span data-ttu-id="ff5a7-106">Em seguida, a função retorna o resultado como um novo valor de *Lista de registros* que consiste nos lotes.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-106">The function then returns the result as a new *Record list* value that consists of the batches.</span></span>

## <a name="syntax"></a><span data-ttu-id="ff5a7-107">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="ff5a7-107">Syntax</span></span>

```
SPLITLISTBYLIMIT (list, limit value, limit source)
```

## <a name="arguments"></a><span data-ttu-id="ff5a7-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ff5a7-108">Arguments</span></span>

<span data-ttu-id="ff5a7-109">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-109">`list`: *Record list*</span></span>

<span data-ttu-id="ff5a7-110">O caminho válido de uma fonte de dados do tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-110">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="ff5a7-111">`limit value`: *Inteiro* ou *Real*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-111">`limit value`: *Integer* or *Real*</span></span>

<span data-ttu-id="ff5a7-112">O valor máximo do limite usado para dividir a lista original em lotes.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-112">The maximum value of the limit that is used to split the original list into batches.</span></span>

<span data-ttu-id="ff5a7-113">`limit source`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-113">`limit source`: *Field*</span></span>

<span data-ttu-id="ff5a7-114">O caminho válido de um campo do tipo *Inteiro* ou *Real* na lista especificada.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-114">The valid path of a field of the *Integer* or *Real* type in the specified list.</span></span> <span data-ttu-id="ff5a7-115">O valor desse campo define a etapa em que a soma total é aumentada.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-115">The value of this field defines the step that the total sum is increased on.</span></span>

## <a name="return-values"></a><span data-ttu-id="ff5a7-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ff5a7-116">Return values</span></span>

<span data-ttu-id="ff5a7-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-117">*Record list*</span></span>

<span data-ttu-id="ff5a7-118">A lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ff5a7-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ff5a7-119">Usage notes</span></span>

<span data-ttu-id="ff5a7-120">A lista de lotes retornada contém os seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="ff5a7-120">The list of batches that is returned contains the following elements:</span></span>

- <span data-ttu-id="ff5a7-121">**Valor**: *Lista*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-121">**Value**: *List*</span></span>

    <span data-ttu-id="ff5a7-122">A lista de registros que pertencem ao lote atual.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-122">The list of records that belong to the current batch.</span></span>

- <span data-ttu-id="ff5a7-123">**BatchNumber**: *Inteiro*</span><span class="sxs-lookup"><span data-stu-id="ff5a7-123">**BatchNumber**: *Integer*</span></span>

    <span data-ttu-id="ff5a7-124">O número do lote atual na lista retornada.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-124">The number of the current batch in the returned list.</span></span>

<span data-ttu-id="ff5a7-125">O limite não é aplicado a um único item da lista original, se a fonte do limite exceder o limite definido.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-125">The limit isn't applied to a single item of the original list if the limit source exceeds the defined limit.</span></span>

## <a name="example"></a><span data-ttu-id="ff5a7-126">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ff5a7-126">Example</span></span>

<span data-ttu-id="ff5a7-127">A ilustração a seguir mostra um formato de relatório eletrônico (ER).</span><span class="sxs-lookup"><span data-stu-id="ff5a7-127">The following illustration shows an Electronic reporting (ER) format.</span></span>

<a href="./media/ger-splitlistbylimit-format.png"><img src="./media/ger-splitlistbylimit-format.png" alt="Format" class="alignnone size-full wp-image-1204063" width="396" height="195" /></a>

<span data-ttu-id="ff5a7-128">A ilustração a seguir mostra as fontes de dados que são usadas para o formato.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-128">The following illustration shows the data sources that are used for the format.</span></span>

<a href="./media/ger-splitlistbylimit-datasources.png"><img src="./media/ger-splitlistbylimit-datasources.png" alt="Data sources" class="alignnone size-full wp-image-1204073" width="320" height="208" /></a>

<span data-ttu-id="ff5a7-129">A ilustração a seguir mostra o resultado quando o formato é executado.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-129">The following illustration shows the result when the format is run.</span></span> <span data-ttu-id="ff5a7-130">Nesse caso, a saída é uma lista simples de itens de mercadoria.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-130">In this case, the output is a flat list of commodity items.</span></span>

<a href="./media/ger-splitlistbylimit-output.png"><img src="./media/ger-splitlistbylimit-output.png" alt="Output" class="alignnone size-full wp-image-1204083" width="462" height="204" /></a>

<span data-ttu-id="ff5a7-131">Nas ilustrações a seguir, o mesmo formato foi ajustado, de forma que apresente a lista de itens de mercadoria em lotes caso um lote único precise incluir mercadorias e o peso total não exceda um limite de 9.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-131">In the following illustrations, the same format has been adjusted so that it presents the list of commodity items in batches if a single batch must include commodities and the total weight should not exceed a limit of 9.</span></span>

<a href="./media/ger-splitlistbylimit-format-1.png"><img src="./media/ger-splitlistbylimit-format-1.png" alt="Adjusted format" class="alignnone size-full wp-image-1204103" width="466" height="438" /></a>

<a href="./media/ger-splitlistbylimit-datasources-1.png"><img src="./media/ger-splitlistbylimit-datasources-1.png" alt="Data sources for the adjusted format" class="alignnone size-full wp-image-1204093" width="645" height="507" /></a>

<span data-ttu-id="ff5a7-132">A ilustração a seguir mostra o resultado quando o formato ajustado é executado.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-132">The following illustration shows the result when the adjusted format is run.</span></span>

<a href="./media/ger-splitlistbylimit-output-1.png"><img src="./media/ger-splitlistbylimit-output-1.png" alt="Output of the adjusted format" class="alignnone size-full wp-image-1204113" width="676" height="611" /></a>

> [!NOTE] 
> <span data-ttu-id="ff5a7-133">O limite não será aplicado ao último item da lista original porque o valor (**11**) da fonte de limite (**peso**) excede o limite definido (**9**).</span><span class="sxs-lookup"><span data-stu-id="ff5a7-133">The limit isn't applied to the last item of the original list, because the value (**11**) of the limit source (**weight**) exceeds the defined limit (**9**).</span></span> <span data-ttu-id="ff5a7-134">Para ignorar as sublistas durante a geração de relatórios, use a função `WHERE` ou a expressão **Habilitada** do elemento de formato correspondente, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ff5a7-134">To ignore sublists during report generation, use either the `WHERE` function or the **Enabled** expression of the corresponding format element, as you require.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff5a7-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="ff5a7-135">Additional resources</span></span>

[<span data-ttu-id="ff5a7-136">Funções de listagem</span><span class="sxs-lookup"><span data-stu-id="ff5a7-136">List functions</span></span>](er-functions-category-list.md)