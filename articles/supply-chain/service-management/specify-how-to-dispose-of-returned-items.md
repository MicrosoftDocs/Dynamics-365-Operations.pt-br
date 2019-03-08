---
title: Especificar o destino dos itens devolvidos
description: Especificar o destino dos itens devolvidos.
author: ShylaThompson
manager: AnnBe
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e6fcdfec083aeb9c58d63f6e03542758e4d07e4d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "325057"
---
# <a name="specify-how-to-dispose-of-returned-items"></a><span data-ttu-id="95c74-103">Especificar o destino dos itens devolvidos</span><span class="sxs-lookup"><span data-stu-id="95c74-103">Specify how to dispose of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="95c74-104">Ao lidar com uma ordem de devolução, você deve especificar um código de motivo de devolução para identificar porque o produto está sendo devolvido.</span><span class="sxs-lookup"><span data-stu-id="95c74-104">When you handle a return order, you must specify a reason return code to identify why the product is being returned.</span></span> <span data-ttu-id="95c74-105">Você também deve especificar um código de disposição e uma ação de disposição para determinar o que deve ser feito com o produto devolvido.</span><span class="sxs-lookup"><span data-stu-id="95c74-105">You must also specify a disposition code and a disposition action to determine what should be done with the returned product itself.</span></span>

<span data-ttu-id="95c74-106">Um código de disposição pode ser aplicado quando você cria a ordem de devolução, registra a entrada de item ou atualiza a guia de remessa da entrada de item e conclui uma ordem de quarentena.</span><span class="sxs-lookup"><span data-stu-id="95c74-106">A disposition code can be applied when you create the return order, register item arrival or packing-slip update an item arrival, and end a quarantine order.</span></span>

<span data-ttu-id="95c74-107">Você pode definir quaisquer códigos de disposição necessários para dar suporte aos processos comerciais.</span><span class="sxs-lookup"><span data-stu-id="95c74-107">You can define any disposition codes that you need in order to support the business processes.</span></span> <span data-ttu-id="95c74-108">A tabela a seguir fornece um conjunto de códigos tipicamente usados para atribuir disposição item de devolução.</span><span class="sxs-lookup"><span data-stu-id="95c74-108">The following table provides a set of typically used codes to assign return-item disposition.</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="95c74-109">Tipo de disposição</span><span class="sxs-lookup"><span data-stu-id="95c74-109">Disposition type</span></span></p></th>
<th><p><span data-ttu-id="95c74-110">Código comum</span><span class="sxs-lookup"><span data-stu-id="95c74-110">Common code</span></span></p></th>
<th><p><span data-ttu-id="95c74-111">Descrição</span><span class="sxs-lookup"><span data-stu-id="95c74-111">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95c74-112">Alienação</span><span class="sxs-lookup"><span data-stu-id="95c74-112">Disposal</span></span></p></td>
<td><p><span data-ttu-id="95c74-113">SC</span><span class="sxs-lookup"><span data-stu-id="95c74-113">SC</span></span></p></td>
<td><p><span data-ttu-id="95c74-114">Sucata/Destruir</span><span class="sxs-lookup"><span data-stu-id="95c74-114">Scrap/Destroy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-115">Alienação</span><span class="sxs-lookup"><span data-stu-id="95c74-115">Disposal</span></span></p></td>
<td><p><span data-ttu-id="95c74-116">DC</span><span class="sxs-lookup"><span data-stu-id="95c74-116">DC</span></span></p></td>
<td><p><span data-ttu-id="95c74-117">Doar para caridade</span><span class="sxs-lookup"><span data-stu-id="95c74-117">Donate to Charity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-118">Alienação</span><span class="sxs-lookup"><span data-stu-id="95c74-118">Disposal</span></span></p></td>
<td><p><span data-ttu-id="95c74-119">TD</span><span class="sxs-lookup"><span data-stu-id="95c74-119">TD</span></span></p></td>
<td><p><span data-ttu-id="95c74-120">Eliminação de terceiros</span><span class="sxs-lookup"><span data-stu-id="95c74-120">Third-Party Disposal</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-121">Alienação</span><span class="sxs-lookup"><span data-stu-id="95c74-121">Disposal</span></span></p></td>
<td><p><span data-ttu-id="95c74-122">SL</span><span class="sxs-lookup"><span data-stu-id="95c74-122">SL</span></span></p></td>
<td><p><span data-ttu-id="95c74-123">Recuperar</span><span class="sxs-lookup"><span data-stu-id="95c74-123">Salvage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-124">Alienação</span><span class="sxs-lookup"><span data-stu-id="95c74-124">Disposal</span></span></p></td>
<td><p><span data-ttu-id="95c74-125">TS</span><span class="sxs-lookup"><span data-stu-id="95c74-125">TS</span></span></p></td>
<td><p><span data-ttu-id="95c74-126">Venda de terceiros (mercados secunDiários)</span><span class="sxs-lookup"><span data-stu-id="95c74-126">Third-Party Sale (Secondary Markets)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-127">Reparar/Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-127">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="95c74-128">RW</span><span class="sxs-lookup"><span data-stu-id="95c74-128">RW</span></span></p></td>
<td><p><span data-ttu-id="95c74-129">Reformular</span><span class="sxs-lookup"><span data-stu-id="95c74-129">Rework</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-130">Reparar/Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-130">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="95c74-131">RF</span><span class="sxs-lookup"><span data-stu-id="95c74-131">RF</span></span></p></td>
<td><p><span data-ttu-id="95c74-132">Refabricar/Recondicionar</span><span class="sxs-lookup"><span data-stu-id="95c74-132">Remanufacture/Refurbish</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-133">Reparar/Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-133">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="95c74-134">MD</span><span class="sxs-lookup"><span data-stu-id="95c74-134">MD</span></span></p></td>
<td><p><span data-ttu-id="95c74-135">Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-135">Modify</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-136">Reparar/Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-136">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="95c74-137">RP</span><span class="sxs-lookup"><span data-stu-id="95c74-137">RP</span></span></p></td>
<td><p><span data-ttu-id="95c74-138">Reparar</span><span class="sxs-lookup"><span data-stu-id="95c74-138">Repair</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-139">Reparar/Modificar</span><span class="sxs-lookup"><span data-stu-id="95c74-139">Repair/Modify</span></span></p></td>
<td><p><span data-ttu-id="95c74-140">RV</span><span class="sxs-lookup"><span data-stu-id="95c74-140">RV</span></span></p></td>
<td><p><span data-ttu-id="95c74-141">Devolver para o fornecedor</span><span class="sxs-lookup"><span data-stu-id="95c74-141">Return to Vendor</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-142">Outros</span><span class="sxs-lookup"><span data-stu-id="95c74-142">Other</span></span></p></td>
<td><p><span data-ttu-id="95c74-143">AI</span><span class="sxs-lookup"><span data-stu-id="95c74-143">AI</span></span></p></td>
<td><p><span data-ttu-id="95c74-144">Usar como</span><span class="sxs-lookup"><span data-stu-id="95c74-144">Use as is</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-145">Outro</span><span class="sxs-lookup"><span data-stu-id="95c74-145">Other</span></span></p></td>
<td><p><span data-ttu-id="95c74-146">RS</span><span class="sxs-lookup"><span data-stu-id="95c74-146">RS</span></span></p></td>
<td><p><span data-ttu-id="95c74-147">Revenda</span><span class="sxs-lookup"><span data-stu-id="95c74-147">Resale</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-148">Outro</span><span class="sxs-lookup"><span data-stu-id="95c74-148">Other</span></span></p></td>
<td><p><span data-ttu-id="95c74-149">EX</span><span class="sxs-lookup"><span data-stu-id="95c74-149">EX</span></span></p></td>
<td><p><span data-ttu-id="95c74-150">Troca</span><span class="sxs-lookup"><span data-stu-id="95c74-150">Exchange</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-151">Outro</span><span class="sxs-lookup"><span data-stu-id="95c74-151">Other</span></span></p></td>
<td><p><span data-ttu-id="95c74-152">MS</span><span class="sxs-lookup"><span data-stu-id="95c74-152">MS</span></span></p></td>
<td><p><span data-ttu-id="95c74-153">Diversos</span><span class="sxs-lookup"><span data-stu-id="95c74-153">Miscellaneous</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95c74-154">Para cada código de disposição definidos por você, selecione uma ação de disposição.</span><span class="sxs-lookup"><span data-stu-id="95c74-154">For each disposition code that you define, you must select a disposition action.</span></span> <span data-ttu-id="95c74-155">A ação de disposição determina as implicações físicas e financeiras dos códigos de disposição.</span><span class="sxs-lookup"><span data-stu-id="95c74-155">The disposition action determines the physical and financial implications of the disposition codes.</span></span> <span data-ttu-id="95c74-156">Por exemplo, a ação de disposição determina o manuseio físico do item devolvido, o efeito financeiro do item devolvido e se um item de substituição deverá ser enviado ao cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-156">For example, the disposition action determines the physical handling of the returned item, the financial effect of the returned item, and if a replacement item must be sent to the customer.</span></span> <span data-ttu-id="95c74-157">Você pode definir um número ilimitado de códigos de disposição de acordo com suas necessidades comerciais, mas existem apenas seis ações de disposição predefinidas que podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="95c74-157">You can define an unlimited number of disposition codes according to your business needs, but there are only six predefined disposition actions that you can select from.</span></span> <span data-ttu-id="95c74-158">A tabela a seguir oferece as ações de disposição e suas definições.</span><span class="sxs-lookup"><span data-stu-id="95c74-158">The following table provides the disposition actions and their definitions.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="95c74-159">Ação de disposição</span><span class="sxs-lookup"><span data-stu-id="95c74-159">Disposition action</span></span></p></th>
<th><p><span data-ttu-id="95c74-160">descrição</span><span class="sxs-lookup"><span data-stu-id="95c74-160">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95c74-161"><strong>Crédito</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-161"><strong>Credit</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-162">Devolver o item ao estoque e creditar o cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-162">Return the item to inventory and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-163"><strong>Somente crédito</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-163"><strong>Credit only</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-164">creditar o cliente sem exigir ou esperar que o item seja devolvido.</span><span class="sxs-lookup"><span data-stu-id="95c74-164">Credit the customer without requiring or expecting the item to be returned.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-165"><strong>Sucata</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-165"><strong>Scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-166">Sucatear o item e creditar o cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-166">Scrap the item and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-167"><strong>Substituir e creditar</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-167"><strong>Replace and credit</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-168">Devolver o item ao estoque, criar uma ordem de substituição e creditar o cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-168">Return the item to inventory, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95c74-169"><strong>Substituir e sucata</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-169"><strong>Replace and scrap</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-170">Sucatear o item, criar uma ordem de substituição e creditar o cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-170">Scrap the item, create a replacement order, and credit the customer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95c74-171"><strong>Devolver ao cliente</strong></span><span class="sxs-lookup"><span data-stu-id="95c74-171"><strong>Return to customer</strong></span></span></p></td>
<td><p><span data-ttu-id="95c74-172">Rejeitar o item devolvido e devolvê-lo ao cliente.</span><span class="sxs-lookup"><span data-stu-id="95c74-172">Reject the returned item and return it to the customer.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="select-a-disposition-code-for-a-quarantine-order"></a><span data-ttu-id="95c74-173">Selecione um código de disposição para uma ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="95c74-173">Select a disposition code for a quarantine order</span></span>

1.  <span data-ttu-id="95c74-174">Clique em **Gerenciamento de estoque** \> **Periódico** \> **Gerenciamento de qualidade** \> **Ordens de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="95c74-174">Click **Inventory management** \> **Periodic** \> **Quality management** \> **Quarantine orders**.</span></span>

2.  <span data-ttu-id="95c74-175">Para uma ordem de quarentena existente, selecione uma ação do campo **Código de disposição** na guia **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="95c74-175">For an existing quarantine order, select an action from the **Disposition code** field on the **Overview** tab.</span></span>



## <a name="see-also"></a><span data-ttu-id="95c74-176">Consulte também</span><span class="sxs-lookup"><span data-stu-id="95c74-176">See also</span></span>

<span data-ttu-id="95c74-177">[Ordem de quarentena (formulário)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span><span class="sxs-lookup"><span data-stu-id="95c74-177">[Quarantine order (form)](https://technet.microsoft.com/en-us/library/aa554073(v=ax.60))</span></span>

<span data-ttu-id="95c74-178">[Códigos de disposição (formulário)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="95c74-178">[Disposition codes (form)](https://technet.microsoft.com/en-us/library/hh597113\(v=ax.60\))</span></span>

  


