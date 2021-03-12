---
title: Objetos de custo
description: Este artigo fornece informações sobre os objetos de custos, e explica como os custos e quantidades serão acumulados. Um objeto de custo é uma entidade para os quais os custos e as quantidades são acumulados. Uma entidade de custo prevista do objeto pode ser um produto ou variantes de produto, como grades para o estilo e cor.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65a0f72f8d97bda36bacd691d545807c413f8825
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967649"
---
# <a name="cost-objects"></a><span data-ttu-id="c5e7f-105">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="c5e7f-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c5e7f-106">Este artigo fornece informações sobre os objetos de custos, e explica como os custos e quantidades serão acumulados.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="c5e7f-107">Um objeto de custo é uma entidade para os quais os custos e as quantidades são acumulados.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="c5e7f-108">Uma entidade de custo prevista do objeto pode ser um produto ou variantes de produto, como grades para o estilo e cor.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="c5e7f-109">Objetos de custo</span><span class="sxs-lookup"><span data-stu-id="c5e7f-109">Cost objects</span></span>

<span data-ttu-id="c5e7f-110">A página **Objetos de custo** lista todos os objetos de custo que foram registrados em um produto.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="c5e7f-111">Os objetos de custo são definidos pelos dados das seguintes origens:</span><span class="sxs-lookup"><span data-stu-id="c5e7f-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="c5e7f-112">Produto</span><span class="sxs-lookup"><span data-stu-id="c5e7f-112">Product</span></span>
-   <span data-ttu-id="c5e7f-113">Grupo de dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="c5e7f-113">Product dimension group</span></span>
-   <span data-ttu-id="c5e7f-114">Grupo de dimensões de armazenamento</span><span class="sxs-lookup"><span data-stu-id="c5e7f-114">Storage dimension group</span></span>
-   <span data-ttu-id="c5e7f-115">Grupo de dimensões de rastreamento</span><span class="sxs-lookup"><span data-stu-id="c5e7f-115">Tracking dimension group</span></span>

<span data-ttu-id="c5e7f-116">**Observação:** Um objeto de custo representa um elemento de custo apenas do tipo **Material direto**.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="c5e7f-117">Um objeto de custo e um objeto de estoque são diferentes na forma como um objeto de custo é definido pelas dimensões de estoque e selecionados para o estoque financeiro.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="c5e7f-118">Por exemplo, um item tem a seguinte configuração:</span><span class="sxs-lookup"><span data-stu-id="c5e7f-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="c5e7f-119">**Local:** Estoque físico = Sim, Estoque financeiro = Sim</span><span class="sxs-lookup"><span data-stu-id="c5e7f-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="c5e7f-120">**Depósito:** Estoque físico = Sim, Estoque financeiro = Não</span><span class="sxs-lookup"><span data-stu-id="c5e7f-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="c5e7f-121">**Nº do lote:** Estoque físico = Sim, Estoque financeiro = Não</span><span class="sxs-lookup"><span data-stu-id="c5e7f-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="c5e7f-122">A tabela a seguir mostra o que é um objeto de custo e o que é um objeto de estoque.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="c5e7f-123">Tipo de Objeto</span><span class="sxs-lookup"><span data-stu-id="c5e7f-123">Object type</span></span>      | <span data-ttu-id="c5e7f-124">Nº do item</span><span class="sxs-lookup"><span data-stu-id="c5e7f-124">Item number</span></span> | <span data-ttu-id="c5e7f-125">Local</span><span class="sxs-lookup"><span data-stu-id="c5e7f-125">Site</span></span> | <span data-ttu-id="c5e7f-126">Depósito</span><span class="sxs-lookup"><span data-stu-id="c5e7f-126">Warehouse</span></span> | <span data-ttu-id="c5e7f-127">Nº do lote</span><span class="sxs-lookup"><span data-stu-id="c5e7f-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="c5e7f-128">Objeto de custo</span><span class="sxs-lookup"><span data-stu-id="c5e7f-128">Cost object</span></span>      | <span data-ttu-id="c5e7f-129">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-129">x</span></span>           | <span data-ttu-id="c5e7f-130">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-130">x</span></span>    |           |           |
| <span data-ttu-id="c5e7f-131">Objeto de estoque</span><span class="sxs-lookup"><span data-stu-id="c5e7f-131">Inventory object</span></span> | <span data-ttu-id="c5e7f-132">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-132">x</span></span>           | <span data-ttu-id="c5e7f-133">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-133">x</span></span>    |  <span data-ttu-id="c5e7f-134">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-134">x</span></span>        | <span data-ttu-id="c5e7f-135">x</span><span class="sxs-lookup"><span data-stu-id="c5e7f-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="c5e7f-136">Acúmulo de custos e quantidades</span><span class="sxs-lookup"><span data-stu-id="c5e7f-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="c5e7f-137">O valor no campo **Valor** é uma soma dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c5e7f-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="c5e7f-138">Valor de custo físico</span><span class="sxs-lookup"><span data-stu-id="c5e7f-138">Physical cost amount</span></span>
    -   <span data-ttu-id="c5e7f-139">Valor de custo financeiro</span><span class="sxs-lookup"><span data-stu-id="c5e7f-139">Financial cost amount</span></span>
    -   <span data-ttu-id="c5e7f-140">Ajustes</span><span class="sxs-lookup"><span data-stu-id="c5e7f-140">Adjustments</span></span>
-   <span data-ttu-id="c5e7f-141">O valor no campo **Quantidade** é uma soma dos seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c5e7f-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="c5e7f-142">Recebido</span><span class="sxs-lookup"><span data-stu-id="c5e7f-142">Received</span></span>
    -   <span data-ttu-id="c5e7f-143">Deduzido</span><span class="sxs-lookup"><span data-stu-id="c5e7f-143">Deducted</span></span>
    -   <span data-ttu-id="c5e7f-144">Quantidade lançada</span><span class="sxs-lookup"><span data-stu-id="c5e7f-144">Posted quantity</span></span>
-   <span data-ttu-id="c5e7f-145">O campo **Custo unitário médio** é um campo calculado.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="c5e7f-146">O valor é calculado dividindo o valor **Valor** pelo valor **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="c5e7f-147">**Observação:** O parâmetro **Incluir valor físico** não tem efeito nos cálculos precedentes.</span><span class="sxs-lookup"><span data-stu-id="c5e7f-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="c5e7f-148">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="c5e7f-148">Additional resources</span></span>
--------

[<span data-ttu-id="c5e7f-149">Grupo de dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="c5e7f-149">Product dimension group</span></span>](https://technet.microsoft.com/library/aa499382.aspx)

[<span data-ttu-id="c5e7f-150">Grupo de dimensões de armazenamento</span><span class="sxs-lookup"><span data-stu-id="c5e7f-150">Storage dimension group</span></span>](https://technet.microsoft.com/library/hh209317.aspx)

[<span data-ttu-id="c5e7f-151">Grupo de dimensões de rastreamento</span><span class="sxs-lookup"><span data-stu-id="c5e7f-151">Tracking dimension group</span></span>](https://technet.microsoft.com/library/hh209465.aspx)

[<span data-ttu-id="c5e7f-152">Novidades ou alterações</span><span class="sxs-lookup"><span data-stu-id="c5e7f-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="c5e7f-153">Entradas de custo</span><span class="sxs-lookup"><span data-stu-id="c5e7f-153">Cost entries</span></span>](cost-entries.md)



