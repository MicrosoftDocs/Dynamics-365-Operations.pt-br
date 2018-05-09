--- 
title: "Configurar perfis de lançamento de ativos fixos"
description: "Este guia de tarefa definirá os perfis de postagem de ativo fixo."
author: saraschi2
manager: AnnBe
ms.date: 02/24/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d07df2c2779833485bd70240c47bb569622800f8
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="set-up-fixed-asset-posting-profiles"></a><span data-ttu-id="45c0c-103">Configurar perfis de lançamento de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="45c0c-103">Set up fixed asset posting profiles</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="45c0c-104">Este guia de tarefa definirá os perfis de postagem de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="45c0c-104">This task guide will set up Fixed asset posting profiles.</span></span>  <span data-ttu-id="45c0c-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="45c0c-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>  <span data-ttu-id="45c0c-106">Os exemplos dados no guia da tarefa são para um perfil de lançamentos básicos, embora os perfis de lançamento devam ser criados para seus requisitos do plano de contas e específico de relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="45c0c-106">Examples given in the task guide are for a basic posting profile, though posting profiles must be created for your specific chart of accounts and financial reporting requirements.</span></span>

1. <span data-ttu-id="45c0c-107">Vá para Ativos fixos > Configuração > Perfis de postagem de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="45c0c-107">Go to Fixed assets > Setup > Fixed asset posting profiles.</span></span>
2. <span data-ttu-id="45c0c-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="45c0c-108">Click New.</span></span>
3. <span data-ttu-id="45c0c-109">No campo de perfil de lançamento, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-109">In the Posting profile field, type a value.</span></span>
4. <span data-ttu-id="45c0c-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="45c0c-111">Será necessário criar um perfil de lançamento para cada tipo de transação de ativo fixo que você utilizará ao trabalhar com ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="45c0c-111">You will need to create a posting profile for each fixed asset transaction type you will be using when working with fixed assets.</span></span>  <span data-ttu-id="45c0c-112">Esta guia será iniciada com tarefas com o tipo de transação de aquisição.</span><span class="sxs-lookup"><span data-stu-id="45c0c-112">This task guide will start with the Acquisition transaction type.</span></span>  
5. <span data-ttu-id="45c0c-113">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-113">Click Add.</span></span>
6. <span data-ttu-id="45c0c-114">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-114">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="45c0c-115">O campo de agrupamentos permite que você defina o perfil de lançamentos para baixo na tabela (uma configuração de conta para cada ativo fixo) ou ao grupo (uma conta configurada para cada grupo de ativos fixos).</span><span class="sxs-lookup"><span data-stu-id="45c0c-115">The Groupings field allows you to define the posting profile down to the Table (one account set up for each fixed asset) or Group (one account set up for each fixed asset group).</span></span>  <span data-ttu-id="45c0c-116">Para este guia de tarefa deixarei o conjunto de valores “Tudo“ a ser aplicado a todos os ativos fixos com o registro especificado.</span><span class="sxs-lookup"><span data-stu-id="45c0c-116">For this task guide I will leave the value set to “All” to apply to all fixed assets with the specified Book.</span></span>  
7. <span data-ttu-id="45c0c-117">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-117">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="45c0c-118">Para aquisições, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.</span><span class="sxs-lookup"><span data-stu-id="45c0c-118">For Acquisitions, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
8. <span data-ttu-id="45c0c-119">No campo Tipo de transação, selecione o 'Ajuste de aquisição'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-119">In the Transaction type field, select 'Acquisition adjustment'.</span></span>
    * <span data-ttu-id="45c0c-120">Para transações de ajuste de aquisição, usaremos as mesmas contas usadas para transações de aquisição.</span><span class="sxs-lookup"><span data-stu-id="45c0c-120">For Acquisition adjustment transactions, we will use the same accounts as used for Acquisition transactions.</span></span>  
9. <span data-ttu-id="45c0c-121">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-121">Click Add.</span></span>
10. <span data-ttu-id="45c0c-122">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-122">In the Book field, enter or select a value.</span></span>
11. <span data-ttu-id="45c0c-123">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-123">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="45c0c-124">Para ajustes de aquisições, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.</span><span class="sxs-lookup"><span data-stu-id="45c0c-124">For Acquisition adjustments, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>    
12. <span data-ttu-id="45c0c-125">No Tipo de transação, selecione 'Depreciação'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-125">In the Transaction type field, select 'Depreciation'.</span></span>
13. <span data-ttu-id="45c0c-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-126">Click Add.</span></span>
14. <span data-ttu-id="45c0c-127">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-127">In the Book field, enter or select a value.</span></span>
15. <span data-ttu-id="45c0c-128">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-128">In the Main account field, specify the desired values.</span></span>
16. <span data-ttu-id="45c0c-129">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-129">In the Offset account field, specify the desired values.</span></span>
17. <span data-ttu-id="45c0c-130">No campo Tipo de transação, selecione 'Ajuste de depreciação'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-130">In the Transaction type field, select 'Depreciation adjustment'.</span></span>
    * <span data-ttu-id="45c0c-131">Para transações de ajuste de depreciação, usaremos as mesmas contas usadas para transações de depreciação.</span><span class="sxs-lookup"><span data-stu-id="45c0c-131">For Depreciation adjustment transactions, we will use the same accounts as used for Depreciation transactions.</span></span>  
18. <span data-ttu-id="45c0c-132">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-132">Click Add.</span></span>
19. <span data-ttu-id="45c0c-133">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-133">In the Book field, enter or select a value.</span></span>
20. <span data-ttu-id="45c0c-134">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-134">In the Main account field, specify the desired values.</span></span>
21. <span data-ttu-id="45c0c-135">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-135">In the Offset account field, specify the desired values.</span></span>
22. <span data-ttu-id="45c0c-136">No campo Tipo de transação, selecione 'Descarte - venda'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-136">In the Transaction type field, select 'Disposal - sale'.</span></span>
23. <span data-ttu-id="45c0c-137">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-137">Click Add.</span></span>
24. <span data-ttu-id="45c0c-138">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-138">In the Book field, enter or select a value.</span></span>
25. <span data-ttu-id="45c0c-139">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-139">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="45c0c-140">Para Descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.</span><span class="sxs-lookup"><span data-stu-id="45c0c-140">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
26. <span data-ttu-id="45c0c-141">No campo Tipo de transação, selecione 'Descarte - sucata'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-141">In the Transaction type field, select 'Disposal - scrap'.</span></span>
    * <span data-ttu-id="45c0c-142">Usaremos as mesmas contas para Descarte e Descarte de sucata.</span><span class="sxs-lookup"><span data-stu-id="45c0c-142">We will use the same accounts for Disposal sale and Disposal scrap.</span></span>  
27. <span data-ttu-id="45c0c-143">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-143">Click Add.</span></span>
28. <span data-ttu-id="45c0c-144">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-144">In the Book field, enter or select a value.</span></span>
29. <span data-ttu-id="45c0c-145">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-145">In the Main account field, specify the desired values.</span></span>
    * <span data-ttu-id="45c0c-146">Para Descartes, você pode inserir uma contrapartida ou deixá-la em branco para ser preenchida com a transação específica.</span><span class="sxs-lookup"><span data-stu-id="45c0c-146">For Disposals, you can enter an offset account or leave it blank to be filled in for the specific transaction.</span></span>  
30. <span data-ttu-id="45c0c-147">Expanda a seção Alienação.</span><span class="sxs-lookup"><span data-stu-id="45c0c-147">Expand the Disposal section.</span></span>
    * <span data-ttu-id="45c0c-148">Você deve configurar perfis de lançamentos de eliminação para venda e sucata.</span><span class="sxs-lookup"><span data-stu-id="45c0c-148">You must set up disposal posting profiles for both sale and scrap.</span></span>  <span data-ttu-id="45c0c-149">Começaremos com transações de venda de eliminação.</span><span class="sxs-lookup"><span data-stu-id="45c0c-149">We will start with disposal sale transactions.</span></span>  
31. <span data-ttu-id="45c0c-150">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-150">Click Add.</span></span>
32. <span data-ttu-id="45c0c-151">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-151">In the Book field, enter or select a value.</span></span>
33. <span data-ttu-id="45c0c-152">No campo Postar valor de lançamentos, selecione o 'Valor de aquisição'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-152">In the Post value field, select 'Acquisition value'.</span></span>
    * <span data-ttu-id="45c0c-153">O valor de aquisição endereçará valores de aquisição e de ajuste de aquisição para todos os anos.</span><span class="sxs-lookup"><span data-stu-id="45c0c-153">Acquisition value will address Acquisition and Acquisition adjustment values for all years.</span></span>  <span data-ttu-id="45c0c-154">Você também pode definir contas para esses tipos de transação separadamente.</span><span class="sxs-lookup"><span data-stu-id="45c0c-154">You can also define accounts for these transaction types separately.</span></span>  
    * <span data-ttu-id="45c0c-155">Você pode definir o processo de eliminação para usar contas diferentes dependendo dos resultados de descarte em um ganho ou perda.</span><span class="sxs-lookup"><span data-stu-id="45c0c-155">You can set the disposal process to use different accounts depending upon if the disposal results in a gain or loss.</span></span>  <span data-ttu-id="45c0c-156">Definirei o tipo de valor de venda 'Tudo” para usar as mesmas contas para todos os tipos de descarte.</span><span class="sxs-lookup"><span data-stu-id="45c0c-156">I will set the Sales value type to “All” to use the same accounts for all types of disposals.</span></span>  
34. <span data-ttu-id="45c0c-157">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-157">In the Main account field, specify the desired values.</span></span>
35. <span data-ttu-id="45c0c-158">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-158">In the Offset account field, specify the desired values.</span></span>
36. <span data-ttu-id="45c0c-159">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-159">Click Add.</span></span>
37. <span data-ttu-id="45c0c-160">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-160">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="45c0c-161">No campo Valor de lançamentos, selecione 'Depreciação (anos anteriores)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-161">In the Post value field, select 'Depreciation (prior years)'.</span></span>  
38. <span data-ttu-id="45c0c-162">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-162">In the Main account field, specify the desired values.</span></span>
39. <span data-ttu-id="45c0c-163">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-163">In the Offset account field, specify the desired values.</span></span>
40. <span data-ttu-id="45c0c-164">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-164">Click Add.</span></span>
41. <span data-ttu-id="45c0c-165">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-165">In the Book field, enter or select a value.</span></span>
42. <span data-ttu-id="45c0c-166">No campo Valor de lançamentos, selecione 'Depreciação (este ano)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-166">In the Post value field, select 'Depreciation (this year)'.</span></span>
43. <span data-ttu-id="45c0c-167">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-167">In the Main account field, specify the desired values.</span></span>
44. <span data-ttu-id="45c0c-168">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-168">In the Offset account field, specify the desired values.</span></span>
45. <span data-ttu-id="45c0c-169">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-169">Click Add.</span></span>
46. <span data-ttu-id="45c0c-170">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-170">In the Book field, enter or select a value.</span></span>
47. <span data-ttu-id="45c0c-171">No campo Valor de lançamentos, selecione 'Ajustes de depreciação (anos anteriores)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-171">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
48. <span data-ttu-id="45c0c-172">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-172">In the Main account field, specify the desired values.</span></span>
49. <span data-ttu-id="45c0c-173">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-173">In the Offset account field, specify the desired values.</span></span>
50. <span data-ttu-id="45c0c-174">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-174">Click Add.</span></span>
51. <span data-ttu-id="45c0c-175">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-175">In the Book field, enter or select a value.</span></span>
52. <span data-ttu-id="45c0c-176">No campo Valor de lançamentos, selecione 'Ajustes de depreciação (este ano)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-176">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
53. <span data-ttu-id="45c0c-177">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-177">In the Main account field, specify the desired values.</span></span>
54. <span data-ttu-id="45c0c-178">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-178">In the Offset account field, specify the desired values.</span></span>
55. <span data-ttu-id="45c0c-179">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-179">Click Add.</span></span>
56. <span data-ttu-id="45c0c-180">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-180">In the Book field, enter or select a value.</span></span>
57. <span data-ttu-id="45c0c-181">No campo Postar valor de lançamentos, selecione o 'Valor líquido contábil'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-181">In the Post value field, select 'Net book value'.</span></span>
58. <span data-ttu-id="45c0c-182">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-182">In the Main account field, specify the desired values.</span></span>
59. <span data-ttu-id="45c0c-183">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-183">In the Offset account field, specify the desired values.</span></span>
60. <span data-ttu-id="45c0c-184">Na venda ou no campo de sucata, selecione o tópico 'Sucata'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-184">In the Sale or scrap field, select 'Scrap'.</span></span>
61. <span data-ttu-id="45c0c-185">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-185">Click Add.</span></span>
62. <span data-ttu-id="45c0c-186">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-186">In the Book field, enter or select a value.</span></span>
63. <span data-ttu-id="45c0c-187">No campo Postar valor de lançamentos, selecione o 'Valor de aquisição'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-187">In the Post value field, select 'Acquisition value'.</span></span>
64. <span data-ttu-id="45c0c-188">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-188">In the Main account field, specify the desired values.</span></span>
65. <span data-ttu-id="45c0c-189">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-189">In the Offset account field, specify the desired values.</span></span>
66. <span data-ttu-id="45c0c-190">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-190">Click Add.</span></span>
67. <span data-ttu-id="45c0c-191">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-191">In the Book field, enter or select a value.</span></span>
    * <span data-ttu-id="45c0c-192">No campo Valor de lançamentos, selecione 'Depreciação (anos anteriores)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-192">In Post value field, select 'Depreciation (prior years)'.</span></span>  
68. <span data-ttu-id="45c0c-193">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-193">In the Main account field, specify the desired values.</span></span>
69. <span data-ttu-id="45c0c-194">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-194">In the Offset account field, specify the desired values.</span></span>
70. <span data-ttu-id="45c0c-195">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-195">Click Add.</span></span>
71. <span data-ttu-id="45c0c-196">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-196">In the Book field, enter or select a value.</span></span>
72. <span data-ttu-id="45c0c-197">No campo Valor de lançamentos, selecione 'Depreciação (este ano)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-197">In the Post value field, select 'Depreciation (this year)'.</span></span>
73. <span data-ttu-id="45c0c-198">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-198">In the Main account field, specify the desired values.</span></span>
74. <span data-ttu-id="45c0c-199">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-199">In the Offset account field, specify the desired values.</span></span>
75. <span data-ttu-id="45c0c-200">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-200">Click Add.</span></span>
76. <span data-ttu-id="45c0c-201">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-201">In the Book field, enter or select a value.</span></span>
77. <span data-ttu-id="45c0c-202">No campo Valor de lançamentos, selecione 'Ajustes de depreciação (anos anteriores)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-202">In the Post value field, select 'Depreciation adjustments (prior years)'.</span></span>
78. <span data-ttu-id="45c0c-203">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-203">In the Main account field, specify the desired values.</span></span>
79. <span data-ttu-id="45c0c-204">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-204">In the Offset account field, specify the desired values.</span></span>
80. <span data-ttu-id="45c0c-205">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-205">Click Add.</span></span>
81. <span data-ttu-id="45c0c-206">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-206">In the Book field, enter or select a value.</span></span>
82. <span data-ttu-id="45c0c-207">No campo Valor de lançamentos, selecione 'Ajustes de depreciação (este ano)'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-207">In the Post value field, select 'Depreciation adjustments (this year)'.</span></span>
83. <span data-ttu-id="45c0c-208">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-208">In the Main account field, specify the desired values.</span></span>
84. <span data-ttu-id="45c0c-209">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-209">In the Offset account field, specify the desired values.</span></span>
85. <span data-ttu-id="45c0c-210">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="45c0c-210">Click Add.</span></span>
86. <span data-ttu-id="45c0c-211">No campo Livro, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="45c0c-211">In the Book field, enter or select a value.</span></span>
87. <span data-ttu-id="45c0c-212">No campo Postar valor de lançamentos, selecione o 'Valor líquido contábil'.</span><span class="sxs-lookup"><span data-stu-id="45c0c-212">In the Post value field, select 'Net book value'.</span></span>
88. <span data-ttu-id="45c0c-213">No campo Conta principal, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-213">In the Main account field, specify the desired values.</span></span>
89. <span data-ttu-id="45c0c-214">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="45c0c-214">In the Offset account field, specify the desired values.</span></span>


