--- 
title: "Criar uma hierarquia de relatórios da organização"
description: "Use este procedimento para criar uma hierarquia do relatório da organização."
author: YuyuScheller
manager: AnnBe
ms.date: 06/28/2017
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: f593c59660abcf5b0d5771ddd9daced6ec5fbfb4
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-an-organization-report-hierarchy"></a><span data-ttu-id="5c79e-103">Criar uma hierarquia de relatórios da organização</span><span class="sxs-lookup"><span data-stu-id="5c79e-103">Create an organization report hierarchy</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5c79e-104">Use este procedimento para criar uma hierarquia do relatório da organização.</span><span class="sxs-lookup"><span data-stu-id="5c79e-104">Use this procedure to create a report hierarchy for organization reporting.</span></span> <span data-ttu-id="5c79e-105">A finalidade desta gravação é guiá-lo pela hierarquia de dimensão, de forma que você possa continuar, enquanto toda a estrutura de relatório de organização é criada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-105">The purpose of this recording is to guide you through the dimension hierarchy so that you can continue until the whole organization reporting structure is created.</span></span> <span data-ttu-id="5c79e-106">Esta gravação usa os dados da empresa de demonstração USP2.</span><span class="sxs-lookup"><span data-stu-id="5c79e-106">This recording uses the USP2 demo data company.</span></span>

1. <span data-ttu-id="5c79e-107">Vá para Contabilização de custos > Dimensões > Hierarquias de dimensões.</span><span class="sxs-lookup"><span data-stu-id="5c79e-107">Go to Cost accounting > Dimensions > Dimension hierarchies.</span></span>
2. <span data-ttu-id="5c79e-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-108">Click New.</span></span>
3. <span data-ttu-id="5c79e-109">No campo HierarchyTypeComboBox, selecione 'Hierarquia de classificação de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-109">In the HierarchyTypeComboBox field, select 'Dimension classification hierarchy'.</span></span>
    * <span data-ttu-id="5c79e-110">Selecione Hierarquia de classificação de dimensões.</span><span class="sxs-lookup"><span data-stu-id="5c79e-110">Select Dimension classification hierarchy.</span></span> <span data-ttu-id="5c79e-111">O tipo de Hierarquia de classificação de dimensões é usado para definir regras e para fins de relatório.</span><span class="sxs-lookup"><span data-stu-id="5c79e-111">The Dimension classification hierarchy type is used to define rules and for reporting purposes.</span></span> <span data-ttu-id="5c79e-112">Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas.</span><span class="sxs-lookup"><span data-stu-id="5c79e-112">It supports all dimensions, such as cost objects, cost elements, and statistical dimensions.</span></span>  
4. <span data-ttu-id="5c79e-113">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-113">Click Create.</span></span>
5. <span data-ttu-id="5c79e-114">No campo Nome de hierarquia de dimensões, digite 'Organização USP2'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-114">In the Dimension hierarchy name field, type 'Oganization USP2'.</span></span>
6. <span data-ttu-id="5c79e-115">No campo Dimensão, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-115">In the Dimension field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-116">Selecione Centros de custo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-116">Select Cost centers.</span></span>  
7. <span data-ttu-id="5c79e-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-117">Click Save.</span></span>
8. <span data-ttu-id="5c79e-118">Clique em Exibir hierarquia.</span><span class="sxs-lookup"><span data-stu-id="5c79e-118">Click View hierarchy.</span></span>
9. <span data-ttu-id="5c79e-119">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-119">Click New.</span></span>
10. <span data-ttu-id="5c79e-120">No campo Nome do nó, digite 'CEO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-120">In the Node name field, type 'CEO'.</span></span>
11. <span data-ttu-id="5c79e-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-121">Click Save.</span></span>
12. <span data-ttu-id="5c79e-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-122">Click New.</span></span>
13. <span data-ttu-id="5c79e-123">No campo Nome do nó, digite 'Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-123">In the Node name field, type 'CEO cost centers'.</span></span>
14. <span data-ttu-id="5c79e-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-124">Click Save.</span></span>
15. <span data-ttu-id="5c79e-125">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-125">Click New.</span></span>
16. <span data-ttu-id="5c79e-126">No campo Nome do nó, digite "Região Leste".</span><span class="sxs-lookup"><span data-stu-id="5c79e-126">In the Node name field, type 'Region East'.</span></span>
17. <span data-ttu-id="5c79e-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-127">Click Save.</span></span>
18. <span data-ttu-id="5c79e-128">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-128">Click New.</span></span>
19. <span data-ttu-id="5c79e-129">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-129">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="5c79e-130">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-130">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-131">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="5c79e-131">Select the dimension member that corresponds to the node.</span></span>  
21. <span data-ttu-id="5c79e-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-132">Click Save.</span></span>
22. <span data-ttu-id="5c79e-133">Na árvore, selecione 'Organização USP2\CEO\Centros de custos de CEO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-133">In the tree, select 'Oganization USP2\CEO\CEO cost centers'.</span></span>
23. <span data-ttu-id="5c79e-134">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-134">Click New.</span></span>
24. <span data-ttu-id="5c79e-135">No campo Nome do nó, digite "Região Oeste".</span><span class="sxs-lookup"><span data-stu-id="5c79e-135">In the Node name field, type 'Region West'.</span></span>
25. <span data-ttu-id="5c79e-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-136">Click Save.</span></span>
26. <span data-ttu-id="5c79e-137">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-137">Click New.</span></span>
27. <span data-ttu-id="5c79e-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-138">In the list, mark the selected row.</span></span>
28. <span data-ttu-id="5c79e-139">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-139">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-140">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="5c79e-140">Select the dimension member that corresponds to the node.</span></span>  
29. <span data-ttu-id="5c79e-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-141">Click Save.</span></span>
30. <span data-ttu-id="5c79e-142">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-142">In the tree, select 'Oganization USP2\CEO'.</span></span>
31. <span data-ttu-id="5c79e-143">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-143">Click New.</span></span>
32. <span data-ttu-id="5c79e-144">No campo Nome do nó, digite 'Centros de custos de CFO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-144">In the Node name field, type 'CFO cost centers'.</span></span>
33. <span data-ttu-id="5c79e-145">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-145">Click Save.</span></span>
34. <span data-ttu-id="5c79e-146">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-146">Click New.</span></span>
35. <span data-ttu-id="5c79e-147">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="5c79e-147">In the Node name field, type 'Marketing campa'.</span></span>
36. <span data-ttu-id="5c79e-148">No campo Nome do nó, digite "Campanha de Marketing".</span><span class="sxs-lookup"><span data-stu-id="5c79e-148">In the Node name field, type 'Marketing campaign'.</span></span>
37. <span data-ttu-id="5c79e-149">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-149">Click Save.</span></span>
38. <span data-ttu-id="5c79e-150">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-150">Click New.</span></span>
39. <span data-ttu-id="5c79e-151">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-151">In the list, mark the selected row.</span></span>
40. <span data-ttu-id="5c79e-152">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-152">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-153">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="5c79e-153">Select the dimension member that corresponds to the node.</span></span>  
41. <span data-ttu-id="5c79e-154">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-154">Click Save.</span></span>
42. <span data-ttu-id="5c79e-155">Na árvore, selecione 'Organização USP2\CEO\Centros de custos de CFO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-155">In the tree, select 'Oganization USP2\CEO\CFO cost centers'.</span></span>
43. <span data-ttu-id="5c79e-156">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-156">Click New.</span></span>
44. <span data-ttu-id="5c79e-157">No campo Nome do nó, digite "Feiras profissionais".</span><span class="sxs-lookup"><span data-stu-id="5c79e-157">In the Node name field, type 'Trade shows'.</span></span>
45. <span data-ttu-id="5c79e-158">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-158">Click Save.</span></span>
46. <span data-ttu-id="5c79e-159">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-159">Click New.</span></span>
47. <span data-ttu-id="5c79e-160">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-160">In the list, mark the selected row.</span></span>
48. <span data-ttu-id="5c79e-161">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-161">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-162">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="5c79e-162">Select the dimension member that corresponds to the node.</span></span>  
49. <span data-ttu-id="5c79e-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-163">Click Save.</span></span>
50. <span data-ttu-id="5c79e-164">Na árvore, selecione 'Organização USP2\CEO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-164">In the tree, select 'Oganization USP2\CEO'.</span></span>
51. <span data-ttu-id="5c79e-165">No campo Nome do nó, digite 'Centros de custos de CIO'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-165">In the Node name field, type 'CIO cost centers'.</span></span>
52. <span data-ttu-id="5c79e-166">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-166">Click Save.</span></span>
53. <span data-ttu-id="5c79e-167">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-167">Click New.</span></span>
54. <span data-ttu-id="5c79e-168">No campo Nome do nó, digite 'Membro da dimensão de origem'.</span><span class="sxs-lookup"><span data-stu-id="5c79e-168">In the Node name field, type 'Call centers'.</span></span>
55. <span data-ttu-id="5c79e-169">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-169">Click Save.</span></span>
56. <span data-ttu-id="5c79e-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5c79e-170">Click New.</span></span>
57. <span data-ttu-id="5c79e-171">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5c79e-171">In the list, mark the selected row.</span></span>
58. <span data-ttu-id="5c79e-172">No campo Membro da dimensão de origem, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5c79e-172">In the From dimension member field, enter or select a value.</span></span>
    * <span data-ttu-id="5c79e-173">Selecione o membro da dimensão que corresponde ao nó.</span><span class="sxs-lookup"><span data-stu-id="5c79e-173">Select the dimension member that corresponds to the node.</span></span>  
59. <span data-ttu-id="5c79e-174">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5c79e-174">Click Save.</span></span>


