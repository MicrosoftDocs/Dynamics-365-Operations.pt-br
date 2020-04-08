---
title: Criar uma nomenclatura de produtos de grades de produto configuradas
description: Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a837721db5281b0626f37b7a793349b91afa6f85
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147747"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a><span data-ttu-id="c6fc3-103">Criar uma nomenclatura de produtos de grades de produto configuradas</span><span class="sxs-lookup"><span data-stu-id="c6fc3-103">Create a product number nomenclature for configured product variants</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c6fc3-104">Este procedimento mostra como configurar uma nomenclatura de número de produto para grades de produtos configurados e como ela pode ser anexada a um produto mestre configurável.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-104">This procedure shows you how to set up a product number nomenclature for configured product variants, and how it can be attached to a configurable product master.</span></span> <span data-ttu-id="c6fc3-105">O procedimento também demonstra como você pode criar uma nomenclatura de configuração para um componente de modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-105">This procedure also demonstrates how you can build a configuration nomenclature for a product configuration model component.</span></span> <span data-ttu-id="c6fc3-106">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="c6fc3-107">A nova nomenclatura de número de produto é atribuída ao produto mestre D0004.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-107">The new product number nomenclature is assigned to the D0004 product master.</span></span> <span data-ttu-id="c6fc3-108">A tarefa geralmente seria realizada por um designer de produto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-108">This task would typically be done by a product designer.</span></span>


## <a name="create-a-product-number-nomenclature"></a><span data-ttu-id="c6fc3-109">Criar uma nomenclatura de número de produto</span><span class="sxs-lookup"><span data-stu-id="c6fc3-109">Create a product number nomenclature</span></span>
1. <span data-ttu-id="c6fc3-110">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-110">Click Product variant model definition.</span></span>
2. <span data-ttu-id="c6fc3-111">Clique em Nomenclatura de produto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-111">Click Product nomenclature.</span></span>
3. <span data-ttu-id="c6fc3-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-112">Click New.</span></span>
4. <span data-ttu-id="c6fc3-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-113">In the Name field, type a value.</span></span>
5. <span data-ttu-id="c6fc3-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-114">In the Description field, type a value.</span></span>
6. <span data-ttu-id="c6fc3-115">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-115">Click Add.</span></span>
7. <span data-ttu-id="c6fc3-116">Clique em Número do produto mestre.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-116">Click Product master number.</span></span>
8. <span data-ttu-id="c6fc3-117">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-117">Click Add.</span></span>
9. <span data-ttu-id="c6fc3-118">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-118">Click Text constant.</span></span>
10. <span data-ttu-id="c6fc3-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-119">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="c6fc3-120">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-120">In the Text field, type a value.</span></span>
12. <span data-ttu-id="c6fc3-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-121">Click Add.</span></span>
13. <span data-ttu-id="c6fc3-122">Clique em Configuração.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-122">Click Configuration.</span></span>
14. <span data-ttu-id="c6fc3-123">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-123">Close the page.</span></span>

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a><span data-ttu-id="c6fc3-124">Atribuir a nomenclatura de número de produto a um produto mestre</span><span class="sxs-lookup"><span data-stu-id="c6fc3-124">Assign the product number nomenclature to a product master</span></span>
1. <span data-ttu-id="c6fc3-125">Clique em Produtos mestres.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-125">Click Product masters.</span></span>
2. <span data-ttu-id="c6fc3-126">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-126">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c6fc3-127">Por exemplo, filtre no campo Número do produto com um valor de "D".</span><span class="sxs-lookup"><span data-stu-id="c6fc3-127">For example, filter on the Product number field with a value of 'D'.</span></span>
3. <span data-ttu-id="c6fc3-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-128">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c6fc3-129">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-129">Click Edit.</span></span>
5. <span data-ttu-id="c6fc3-130">Selecione Sim no campo Usar nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-130">Select Yes in the Use nomenclature field.</span></span>
6. <span data-ttu-id="c6fc3-131">No campo Nomenclatura de número de grade de produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-131">In the Product variant number nomenclature field, enter or select a value.</span></span>
7. <span data-ttu-id="c6fc3-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-132">Close the page.</span></span>
8. <span data-ttu-id="c6fc3-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-133">Close the page.</span></span>

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a><span data-ttu-id="c6fc3-134">Criar nomenclatura para um componente de modelo de configuração de produto</span><span class="sxs-lookup"><span data-stu-id="c6fc3-134">Create nomenclature for a product configuration model component</span></span>
1. <span data-ttu-id="c6fc3-135">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-135">Click Product configuration models.</span></span>
2. <span data-ttu-id="c6fc3-136">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-136">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c6fc3-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-137">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c6fc3-138">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-138">Click Edit.</span></span>
5. <span data-ttu-id="c6fc3-139">Selecione Sim no campo Usar nomenclatura de configuração.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-139">Select Yes in the Use configuration nomenclature field.</span></span>
6. <span data-ttu-id="c6fc3-140">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-140">Click Add.</span></span>
7. <span data-ttu-id="c6fc3-141">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-141">Click Attribute value.</span></span>
8. <span data-ttu-id="c6fc3-142">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-142">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="c6fc3-143">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-143">In the Attribute field, enter or select a value.</span></span>
10. <span data-ttu-id="c6fc3-144">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-144">Click Add.</span></span>
11. <span data-ttu-id="c6fc3-145">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-145">Click Text constant.</span></span>
12. <span data-ttu-id="c6fc3-146">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-146">In the list, mark the selected row.</span></span>
13. <span data-ttu-id="c6fc3-147">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-147">In the Text field, type a value.</span></span>
14. <span data-ttu-id="c6fc3-148">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-148">Click Add.</span></span>
15. <span data-ttu-id="c6fc3-149">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-149">Click Attribute value.</span></span>
16. <span data-ttu-id="c6fc3-150">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-150">In the list, mark the selected row.</span></span>
17. <span data-ttu-id="c6fc3-151">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-151">In the Attribute field, enter or select a value.</span></span>
18. <span data-ttu-id="c6fc3-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-152">Click Add.</span></span>
19. <span data-ttu-id="c6fc3-153">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-153">Click Text constant.</span></span>
20. <span data-ttu-id="c6fc3-154">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-154">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="c6fc3-155">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-155">In the Text field, type a value.</span></span>
22. <span data-ttu-id="c6fc3-156">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-156">Click Add.</span></span>
23. <span data-ttu-id="c6fc3-157">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-157">Click Attribute value.</span></span>
24. <span data-ttu-id="c6fc3-158">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-158">In the list, mark the selected row.</span></span>
25. <span data-ttu-id="c6fc3-159">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-159">In the Attribute field, enter or select a value.</span></span>
26. <span data-ttu-id="c6fc3-160">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-160">Click Add.</span></span>
27. <span data-ttu-id="c6fc3-161">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-161">Click Text constant.</span></span>
28. <span data-ttu-id="c6fc3-162">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-162">In the list, mark the selected row.</span></span>
29. <span data-ttu-id="c6fc3-163">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-163">In the Text field, type a value.</span></span>
30. <span data-ttu-id="c6fc3-164">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-164">Click Add.</span></span>
31. <span data-ttu-id="c6fc3-165">Clique em Valor do atributo.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-165">Click Attribute value.</span></span>
32. <span data-ttu-id="c6fc3-166">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-166">In the list, mark the selected row.</span></span>
33. <span data-ttu-id="c6fc3-167">No campo Atributo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-167">In the Attribute field, enter or select a value.</span></span>
34. <span data-ttu-id="c6fc3-168">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-168">Click Add.</span></span>
35. <span data-ttu-id="c6fc3-169">Clique em Constante de texto.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-169">Click Text constant.</span></span>
36. <span data-ttu-id="c6fc3-170">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-170">In the list, mark the selected row.</span></span>
37. <span data-ttu-id="c6fc3-171">No campo Texto, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-171">In the Text field, type a value.</span></span>
38. <span data-ttu-id="c6fc3-172">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-172">Click Add.</span></span>
39. <span data-ttu-id="c6fc3-173">Clique em Valor de sequência numérica.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-173">Click Number sequence value.</span></span>
40. <span data-ttu-id="c6fc3-174">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-174">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="c6fc3-175">No campo Sequência numérica, digite ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-175">In the Number sequence field, enter or select a value.</span></span>
42. <span data-ttu-id="c6fc3-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-176">Close the page.</span></span>
43. <span data-ttu-id="c6fc3-177">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-177">Close the page.</span></span>
44. <span data-ttu-id="c6fc3-178">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-178">Close the page.</span></span>

