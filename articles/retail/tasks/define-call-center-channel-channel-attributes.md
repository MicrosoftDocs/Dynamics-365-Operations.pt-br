--- 
title: " Definir canal de call center e atributos de canal"
description: Este procedimento orienta como criar um novo canal de varejo e definir atributos do canal.
author: mugunthanm
manager: AnnBe
ms.date: 05/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.author: mumani
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: 1418f04d8fb4d05756ac7a5f4b92a1950037be1d
ms.contentlocale: pt-br
ms.lasthandoff: 02/07/2018

---
# <a name="define-call-center-channel-and-channel-attributes"></a><span data-ttu-id="fcce4-103"> Definir canal de call center e atributos de canal</span><span class="sxs-lookup"><span data-stu-id="fcce4-103">Define call center channel and channel attributes</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="fcce4-104">Este procedimento orienta como criar um novo canal de varejo e definir atributos do canal.</span><span class="sxs-lookup"><span data-stu-id="fcce4-104">This procedure walks through creating a new retail channel and defining channel attributes.</span></span> <span data-ttu-id="fcce4-105">A empresa de dados de demonstração usada para criar esta tarefa é USRT.</span><span class="sxs-lookup"><span data-stu-id="fcce4-105">The demo data company used to create this task is USRT.</span></span> <span data-ttu-id="fcce4-106">Esse procedimento é destinado para a função TI de Varejo.</span><span class="sxs-lookup"><span data-stu-id="fcce4-106">This procedure is intended for the Retail IT role.</span></span>


## <a name="create-new-store"></a><span data-ttu-id="fcce4-107">Criar nova loja</span><span class="sxs-lookup"><span data-stu-id="fcce4-107">Create new store</span></span>
1. <span data-ttu-id="fcce4-108">Vá para Todos os espaços de trabalho > Implementação do canal.</span><span class="sxs-lookup"><span data-stu-id="fcce4-108">Go to All workspaces > Channel deployment.</span></span>
2. <span data-ttu-id="fcce4-109">Clique em Novo canal.</span><span class="sxs-lookup"><span data-stu-id="fcce4-109">Click New channel.</span></span>
3. <span data-ttu-id="fcce4-110">Clique em Loja.</span><span class="sxs-lookup"><span data-stu-id="fcce4-110">Click Store.</span></span>
4. <span data-ttu-id="fcce4-111">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcce4-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="fcce4-112">No campo Número da loja, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="fcce4-112">In the Store number field, type a value.</span></span>
6. <span data-ttu-id="fcce4-113">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-113">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="fcce4-114">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-114">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fcce4-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fcce4-116">No campo Fuso horário da loja, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="fcce4-116">In the Store time zone field, select an option.</span></span>
10. <span data-ttu-id="fcce4-117">No campo Perfil do canal, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-117">In the Channel profile field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="fcce4-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="fcce4-119">No campo Idioma, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-119">In the Language field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="fcce4-120">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-120">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="fcce4-121">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-121">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="fcce4-122">No campo Grupo de imposto, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-122">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="fcce4-123">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-123">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="fcce4-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="fcce4-125">No campo Catálogo de endereços do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-125">In the Customer address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fcce4-126">Selecione o catálogo de endereço usado para vincular clientes a esta loja.</span><span class="sxs-lookup"><span data-stu-id="fcce4-126">Select the address book used to link customers to this store.</span></span>  
19. <span data-ttu-id="fcce4-127">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-127">In the list, find and select the desired record.</span></span>
20. <span data-ttu-id="fcce4-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-128">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="fcce4-129">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-129">Click Select.</span></span>
22. <span data-ttu-id="fcce4-130">No campo Catálogo de endereços do funcionário, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-130">In the Employee address book field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fcce4-131">Selecione o catálogo de endereço usado para vincular caixas a este canal.</span><span class="sxs-lookup"><span data-stu-id="fcce4-131">Select the address book used to link cashiers to this channel.</span></span>  
23. <span data-ttu-id="fcce4-132">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-132">In the list, find and select the desired record.</span></span>
24. <span data-ttu-id="fcce4-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-133">In the list, click the link in the selected row.</span></span>
25. <span data-ttu-id="fcce4-134">Clique em Selecionar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-134">Click Select.</span></span>
26. <span data-ttu-id="fcce4-135">No campo Cliente padrão, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-135">In the Default customer field, click the drop-down button to open the lookup.</span></span>
27. <span data-ttu-id="fcce4-136">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-136">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="fcce4-137">Expandir ou recolha a seção Layout da tela.</span><span class="sxs-lookup"><span data-stu-id="fcce4-137">Expand or collapse the Screen layout section.</span></span>
29. <span data-ttu-id="fcce4-138">No campo ID do layout da tela, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-138">In the Screen layout ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="fcce4-139">Selecione o layout da tela do PDV padrão para esta loja</span><span class="sxs-lookup"><span data-stu-id="fcce4-139">Select the default POS screen layout for this store.</span></span>  
30. <span data-ttu-id="fcce4-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-140">In the list, find and select the desired record.</span></span>
31. <span data-ttu-id="fcce4-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="fcce4-142">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-142">On the Action Pane, click Set up.</span></span>
33. <span data-ttu-id="fcce4-143">Clique em Atributos de canal.</span><span class="sxs-lookup"><span data-stu-id="fcce4-143">Click Channel attributes.</span></span>
34. <span data-ttu-id="fcce4-144">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fcce4-144">Click New.</span></span>
35. <span data-ttu-id="fcce4-145">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-145">In the Name field, click the drop-down button to open the lookup.</span></span>
36. <span data-ttu-id="fcce4-146">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-146">In the list, find and select the desired record.</span></span>
37. <span data-ttu-id="fcce4-147">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-147">In the list, click the link in the selected row.</span></span>
38. <span data-ttu-id="fcce4-148">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-148">Click Save.</span></span>
39. <span data-ttu-id="fcce4-149">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fcce4-149">Close the page.</span></span>
40. <span data-ttu-id="fcce4-150">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-150">On the Action Pane, click Set up.</span></span>
41. <span data-ttu-id="fcce4-151">Clique em Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="fcce4-151">Click Payment methods.</span></span>
42. <span data-ttu-id="fcce4-152">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fcce4-152">Click New.</span></span>
43. <span data-ttu-id="fcce4-153">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-153">In the Payment method field, click the drop-down button to open the lookup.</span></span>
44. <span data-ttu-id="fcce4-154">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-154">In the list, click the link in the selected row.</span></span>
45. <span data-ttu-id="fcce4-155">Expandir ou recolher a seção Lançamento.</span><span class="sxs-lookup"><span data-stu-id="fcce4-155">Expand or collapse the Posting section.</span></span>
46. <span data-ttu-id="fcce4-156">No campo Número da conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="fcce4-156">In the Account number field, specify the desired values.</span></span>
47. <span data-ttu-id="fcce4-157">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-157">Click Save.</span></span>
48. <span data-ttu-id="fcce4-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fcce4-158">Close the page.</span></span>
49. <span data-ttu-id="fcce4-159">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-159">On the Action Pane, click Set up.</span></span>
50. <span data-ttu-id="fcce4-160">Clique em Declaração de valores em caixa</span><span class="sxs-lookup"><span data-stu-id="fcce4-160">Click Cash declaration.</span></span>
51. <span data-ttu-id="fcce4-161">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fcce4-161">Click New.</span></span>
52. <span data-ttu-id="fcce4-162">No campo Valor na moeda da transação, insira um número.</span><span class="sxs-lookup"><span data-stu-id="fcce4-162">In the Amount in transaction currency field, enter a number.</span></span>
53. <span data-ttu-id="fcce4-163">No campo Moeda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-163">In the Currency field, click the drop-down button to open the lookup.</span></span>
54. <span data-ttu-id="fcce4-164">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-164">In the list, find and select the desired record.</span></span>
55. <span data-ttu-id="fcce4-165">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-165">In the list, click the link in the selected row.</span></span>
56. <span data-ttu-id="fcce4-166">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-166">Click Save.</span></span>
57. <span data-ttu-id="fcce4-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fcce4-167">Close the page.</span></span>
58. <span data-ttu-id="fcce4-168">No Painel de Ação, clique em Configurar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-168">On the Action Pane, click Set up.</span></span>
59. <span data-ttu-id="fcce4-169">Clique na Atribuição de grupo de localizador de loja.</span><span class="sxs-lookup"><span data-stu-id="fcce4-169">Click Store locator group assignment.</span></span>
60. <span data-ttu-id="fcce4-170">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="fcce4-170">Click New.</span></span>
61. <span data-ttu-id="fcce4-171">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-171">In the list, mark the selected row.</span></span>
62. <span data-ttu-id="fcce4-172">No campo Grupo de localizador, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="fcce4-172">In the Locator group field, click the drop-down button to open the lookup.</span></span>
63. <span data-ttu-id="fcce4-173">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="fcce4-173">In the list, find and select the desired record.</span></span>
64. <span data-ttu-id="fcce4-174">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="fcce4-174">In the list, click the link in the selected row.</span></span>
65. <span data-ttu-id="fcce4-175">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="fcce4-175">Click Save.</span></span>
66. <span data-ttu-id="fcce4-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fcce4-176">Close the page.</span></span>


