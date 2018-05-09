--- 
title: "Criar uma hierarquia de relatórios da organização"
description: "Use este procedimento para criar uma hierarquia do relatório da organização."
author: YuyuScheller
manager: AnnBe
ms.date: 10/30/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 69fccd6b59e25fe0f39c107c59c1682cc545ebd2
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="57728-103">Criar uma hierarquia de relatórios da organização</span><span class="sxs-lookup"><span data-stu-id="57728-103">Create an organization report hierarchy</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57728-104">Use este procedimento para criar uma hierarquia do relatório da organização.</span><span class="sxs-lookup"><span data-stu-id="57728-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="57728-105">A finalidade desta gravação é guiá-lo pela hierarquia de dimensão, de forma que você possa continuar, enquanto toda a estrutura de relatório de organização é criada.</span><span class="sxs-lookup"><span data-stu-id="57728-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="57728-106">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="57728-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="57728-107">Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.</span><span class="sxs-lookup"><span data-stu-id="57728-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="57728-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-108">Click New.</span></span>
3. <span data-ttu-id="57728-109">No campo HierarchyTypeComboBox, selecione 'Hierarquia de classificação de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="57728-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="57728-110">Selecione Hierarquia de classificação de dimensões.</span><span class="sxs-lookup"><span data-stu-id="57728-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="57728-111">O tipo de Hierarquia de classificação de dimensões é usado para definir regras e para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="57728-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="57728-112">Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas.</span><span class="sxs-lookup"><span data-stu-id="57728-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="57728-113">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="57728-113">Click Create.</span></span>
5. <span data-ttu-id="57728-114">No campo Nome de hierarquia de dimensões, digite 'Organização USP2'.</span><span class="sxs-lookup"><span data-stu-id="57728-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="57728-115">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-116">Selecione Centros de custo.</span><span class="sxs-lookup"><span data-stu-id="57728-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="57728-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-117">Click Save.</span></span>
8. <span data-ttu-id="57728-118">Clique em Exibir hierarquia.</span><span class="sxs-lookup"><span data-stu-id="57728-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="57728-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-119">Click New.</span></span>
10. <span data-ttu-id="57728-120">No campo Nome do nó, digite 'CEO'.</span><span class="sxs-lookup"><span data-stu-id="57728-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="57728-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-121">Click Save.</span></span>
12. <span data-ttu-id="57728-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-122">Click New.</span></span>
13. <span data-ttu-id="57728-123">No campo Nome do nó, digite 'Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="57728-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="57728-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-124">Click Save.</span></span>
15. <span data-ttu-id="57728-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-125">Click New.</span></span>
16. <span data-ttu-id="57728-126">No campo Nome do nó, digite "Região Leste".</span><span class="sxs-lookup"><span data-stu-id="57728-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="57728-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-127">Click Save.</span></span>
18. <span data-ttu-id="57728-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-128">Click New.</span></span>
19. <span data-ttu-id="57728-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57728-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="57728-130">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-131">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="57728-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="57728-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-132">Click Save.</span></span>
22. <span data-ttu-id="57728-133">Na árvore, selecione 'Organização USP2\CEO\Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="57728-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="57728-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-134">Click New.</span></span>
24. <span data-ttu-id="57728-135">No campo Nome do nó, digite "Região Oeste".</span><span class="sxs-lookup"><span data-stu-id="57728-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="57728-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-136">Click Save.</span></span>
26. <span data-ttu-id="57728-137">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-137">Click New.</span></span>
27. <span data-ttu-id="57728-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57728-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="57728-139">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-140">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="57728-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="57728-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-141">Click Save.</span></span>
30. <span data-ttu-id="57728-142">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="57728-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="57728-143">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-143">Click New.</span></span>
32. <span data-ttu-id="57728-144">No campo Nome do nó, digite 'Centros de custos de CFO'.</span><span class="sxs-lookup"><span data-stu-id="57728-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="57728-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-145">Click Save.</span></span>
34. <span data-ttu-id="57728-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-146">Click New.</span></span>
35. <span data-ttu-id="57728-147">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="57728-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="57728-148">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="57728-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="57728-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-149">Click Save.</span></span>
38. <span data-ttu-id="57728-150">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-150">Click New.</span></span>
39. <span data-ttu-id="57728-151">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57728-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="57728-152">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-153">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="57728-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="57728-154">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-154">Click Save.</span></span>
42. <span data-ttu-id="57728-155">Na árvore, selecione 'Centros de custos da organização USP2\CEO\CFO'.</span><span class="sxs-lookup"><span data-stu-id="57728-155">In the tree, select 'Organization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="57728-156">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-156">Click New.</span></span>
44. <span data-ttu-id="57728-157">No campo Nome do nó, digite "Feiras profissionais".</span><span class="sxs-lookup"><span data-stu-id="57728-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="57728-158">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-158">Click Save.</span></span>
46. <span data-ttu-id="57728-159">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-159">Click New.</span></span>
47. <span data-ttu-id="57728-160">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57728-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="57728-161">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-162">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="57728-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="57728-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-163">Click Save.</span></span>
50. <span data-ttu-id="57728-164">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="57728-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="57728-165">No campo Nome do nó, digite 'Centros de custos de CIO'.</span><span class="sxs-lookup"><span data-stu-id="57728-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="57728-166">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-166">Click Save.</span></span>
53. <span data-ttu-id="57728-167">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-167">Click New.</span></span>
54. <span data-ttu-id="57728-168">No campo Nome do nó, digite 'Membro da dimensão de origem'.</span><span class="sxs-lookup"><span data-stu-id="57728-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="57728-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-169">Click Save.</span></span>
56. <span data-ttu-id="57728-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="57728-170">Click New.</span></span>
57. <span data-ttu-id="57728-171">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="57728-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="57728-172">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="57728-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="57728-173">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="57728-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="57728-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="57728-174">Click Save.</span></span>


