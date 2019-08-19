---
title: Criar uma hierarquia de relatórios da organização
description: Use este procedimento para criar uma hierarquia do relatório da organização.
author: ShylaThompson
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5684c710b8e167a4a39f106eb3c0fd77e3011dbd
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841336"
---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="10b19-103">Criar uma hierarquia de relatórios da organização</span><span class="sxs-lookup"><span data-stu-id="10b19-103">Create an organization report hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="10b19-104">Use este procedimento para criar uma hierarquia do relatório da organização.</span><span class="sxs-lookup"><span data-stu-id="10b19-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="10b19-105">A finalidade desta gravação é guiá-lo pela hierarquia de dimensão, de forma que você possa continuar, enquanto toda a estrutura de relatório de organização é criada.</span><span class="sxs-lookup"><span data-stu-id="10b19-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="10b19-106">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="10b19-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="10b19-107">Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.</span><span class="sxs-lookup"><span data-stu-id="10b19-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="10b19-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-108">Click New.</span></span>
3. <span data-ttu-id="10b19-109">No campo HierarchyTypeComboBox, selecione 'Hierarquia de classificação de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="10b19-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="10b19-110">Selecione Hierarquia de classificação de dimensões.</span><span class="sxs-lookup"><span data-stu-id="10b19-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="10b19-111">O tipo de Hierarquia de classificação de dimensões é usado para definir regras e para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="10b19-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="10b19-112">Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas.</span><span class="sxs-lookup"><span data-stu-id="10b19-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="10b19-113">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="10b19-113">Click Create.</span></span>
5. <span data-ttu-id="10b19-114">No campo Nome de hierarquia de dimensões, digite 'Organização USP2'.</span><span class="sxs-lookup"><span data-stu-id="10b19-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="10b19-115">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-116">Selecione Centros de custo.</span><span class="sxs-lookup"><span data-stu-id="10b19-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="10b19-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-117">Click Save.</span></span>
8. <span data-ttu-id="10b19-118">Clique em Exibir hierarquia.</span><span class="sxs-lookup"><span data-stu-id="10b19-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="10b19-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-119">Click New.</span></span>
10. <span data-ttu-id="10b19-120">No campo Nome do nó, digite 'CEO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="10b19-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-121">Click Save.</span></span>
12. <span data-ttu-id="10b19-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-122">Click New.</span></span>
13. <span data-ttu-id="10b19-123">No campo Nome do nó, digite 'Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="10b19-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-124">Click Save.</span></span>
15. <span data-ttu-id="10b19-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-125">Click New.</span></span>
16. <span data-ttu-id="10b19-126">No campo Nome do nó, digite "Região Leste".</span><span class="sxs-lookup"><span data-stu-id="10b19-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="10b19-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-127">Click Save.</span></span>
18. <span data-ttu-id="10b19-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-128">Click New.</span></span>
19. <span data-ttu-id="10b19-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="10b19-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="10b19-130">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-131">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="10b19-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="10b19-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-132">Click Save.</span></span>
22. <span data-ttu-id="10b19-133">Na árvore, selecione 'Organização USP2\CEO\Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="10b19-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-134">Click New.</span></span>
24. <span data-ttu-id="10b19-135">No campo Nome do nó, digite "Região Oeste".</span><span class="sxs-lookup"><span data-stu-id="10b19-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="10b19-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-136">Click Save.</span></span>
26. <span data-ttu-id="10b19-137">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-137">Click New.</span></span>
27. <span data-ttu-id="10b19-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="10b19-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="10b19-139">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-140">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="10b19-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="10b19-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-141">Click Save.</span></span>
30. <span data-ttu-id="10b19-142">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="10b19-143">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-143">Click New.</span></span>
32. <span data-ttu-id="10b19-144">No campo Nome do nó, digite 'Centros de custos de CFO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="10b19-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-145">Click Save.</span></span>
34. <span data-ttu-id="10b19-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-146">Click New.</span></span>
35. <span data-ttu-id="10b19-147">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="10b19-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="10b19-148">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="10b19-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="10b19-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-149">Click Save.</span></span>
38. <span data-ttu-id="10b19-150">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-150">Click New.</span></span>
39. <span data-ttu-id="10b19-151">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="10b19-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="10b19-152">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-153">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="10b19-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="10b19-154">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-154">Click Save.</span></span>
42. <span data-ttu-id="10b19-155">Na árvore, selecione 'Centros de custos da organização USP2\CEO\CFO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="10b19-156">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-156">Click New.</span></span>
44. <span data-ttu-id="10b19-157">No campo Nome do nó, digite "Feiras profissionais".</span><span class="sxs-lookup"><span data-stu-id="10b19-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="10b19-158">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-158">Click Save.</span></span>
46. <span data-ttu-id="10b19-159">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-159">Click New.</span></span>
47. <span data-ttu-id="10b19-160">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="10b19-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="10b19-161">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-162">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="10b19-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="10b19-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-163">Click Save.</span></span>
50. <span data-ttu-id="10b19-164">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="10b19-165">No campo Nome do nó, digite 'Centros de custos de CIO'.</span><span class="sxs-lookup"><span data-stu-id="10b19-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="10b19-166">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-166">Click Save.</span></span>
53. <span data-ttu-id="10b19-167">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-167">Click New.</span></span>
54. <span data-ttu-id="10b19-168">No campo Nome do nó, digite 'Membro da dimensão de origem'.</span><span class="sxs-lookup"><span data-stu-id="10b19-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="10b19-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-169">Click Save.</span></span>
56. <span data-ttu-id="10b19-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="10b19-170">Click New.</span></span>
57. <span data-ttu-id="10b19-171">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="10b19-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="10b19-172">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="10b19-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="10b19-173">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="10b19-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="10b19-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="10b19-174">Click Save.</span></span>

