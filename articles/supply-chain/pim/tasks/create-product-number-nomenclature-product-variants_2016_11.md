---
title: Criar uma nomenclatura de produtos de grades de produto configuradas
description: Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e52b7a5aff3e86e845484e1e84b4003cc4a52c95
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992361"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="34712-103">Criar uma nomenclatura de produtos de grades de produto configuradas</span><span class="sxs-lookup"><span data-stu-id="34712-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34712-104">Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.</span><span class="sxs-lookup"><span data-stu-id="34712-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="34712-105">O procedimento também demonstra como você pode criar uma nomenclatura de configuração para um componente de modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="34712-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="34712-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="34712-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="34712-107">A nova nomenclatura de número de produto é atribuída ao produto mestre D0004.</span><span class="sxs-lookup"><span data-stu-id="34712-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="34712-108">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="34712-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="34712-109">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="34712-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="34712-110">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="34712-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="34712-111">Clique em Nomenclatura de produto.</span><span class="sxs-lookup"><span data-stu-id="34712-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="34712-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="34712-112">Click New.</span></span>
4. <span data-ttu-id="34712-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="34712-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="34712-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-115">Click Add.</span></span>
7. <span data-ttu-id="34712-116">Clique em Número do produto mestre.</span><span class="sxs-lookup"><span data-stu-id="34712-116">Click Product master number.</span></span>
8. <span data-ttu-id="34712-117">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-117">Click Add.</span></span>
9. <span data-ttu-id="34712-118">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="34712-118">Click Text constant.</span></span>
10. <span data-ttu-id="34712-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="34712-120">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="34712-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-121">Click Add.</span></span>
13. <span data-ttu-id="34712-122">Clique em Configuração.</span><span class="sxs-lookup"><span data-stu-id="34712-122">Click Configuration.</span></span>
14. <span data-ttu-id="34712-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="34712-124">Atribuir a nomenclatura de número de produto a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="34712-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="34712-125">Clique em Produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="34712-125">Click Product masters.</span></span>
2. <span data-ttu-id="34712-126">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="34712-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="34712-127">Por exemplo, filtre no campo Número do produto com um valor de "D".</span><span class="sxs-lookup"><span data-stu-id="34712-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="34712-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="34712-129">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="34712-129">Click Edit.</span></span>
5. <span data-ttu-id="34712-130">Selecione Sim no campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="34712-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="34712-131">No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="34712-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-132">Close the page.</span></span>
8. <span data-ttu-id="34712-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="34712-134">Criar nomenclatura para um componente de modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="34712-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="34712-135">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="34712-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="34712-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="34712-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="34712-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="34712-138">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="34712-138">Click Edit.</span></span>
5. <span data-ttu-id="34712-139">Selecione Sim no campo Usar nomenclatura de configuração.</span><span class="sxs-lookup"><span data-stu-id="34712-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="34712-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-140">Click Add.</span></span>
7. <span data-ttu-id="34712-141">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="34712-141">Click Attribute value.</span></span>
8. <span data-ttu-id="34712-142">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="34712-143">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="34712-144">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-144">Click Add.</span></span>
11. <span data-ttu-id="34712-145">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="34712-145">Click Text constant.</span></span>
12. <span data-ttu-id="34712-146">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="34712-147">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="34712-148">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-148">Click Add.</span></span>
15. <span data-ttu-id="34712-149">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="34712-149">Click Attribute value.</span></span>
16. <span data-ttu-id="34712-150">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="34712-151">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="34712-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-152">Click Add.</span></span>
19. <span data-ttu-id="34712-153">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="34712-153">Click Text constant.</span></span>
20. <span data-ttu-id="34712-154">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="34712-155">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="34712-156">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-156">Click Add.</span></span>
23. <span data-ttu-id="34712-157">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="34712-157">Click Attribute value.</span></span>
24. <span data-ttu-id="34712-158">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="34712-159">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="34712-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-160">Click Add.</span></span>
27. <span data-ttu-id="34712-161">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="34712-161">Click Text constant.</span></span>
28. <span data-ttu-id="34712-162">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="34712-163">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="34712-164">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-164">Click Add.</span></span>
31. <span data-ttu-id="34712-165">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="34712-165">Click Attribute value.</span></span>
32. <span data-ttu-id="34712-166">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="34712-167">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="34712-168">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-168">Click Add.</span></span>
35. <span data-ttu-id="34712-169">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="34712-169">Click Text constant.</span></span>
36. <span data-ttu-id="34712-170">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="34712-171">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="34712-172">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="34712-172">Click Add.</span></span>
39. <span data-ttu-id="34712-173">Clique em Valor de sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="34712-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="34712-174">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="34712-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="34712-175">No campo Sequência numérica, digite ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="34712-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="34712-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-176">Close the page.</span></span>
43. <span data-ttu-id="34712-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-177">Close the page.</span></span>
44. <span data-ttu-id="34712-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="34712-178">Close the page.</span></span>

