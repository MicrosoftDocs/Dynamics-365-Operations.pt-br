--- 
title: Emitir notas fiscais para fornecedores (Brasil)
description: "Você pode criar e lançar faturas de fornecedor em nome dos fornecedores que não são contribuintes."
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 82de46c4e9b03aa15fdfad189cc55925eb40281a
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="issue-fiscal-documents-for-vendors-brazil"></a><span data-ttu-id="d5db3-103">Emitir notas fiscais para fornecedores (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d5db3-103">Issue fiscal documents for vendors (Brazil)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d5db3-104">Você pode criar e lançar faturas de fornecedor em nome dos fornecedores que não são contribuintes.</span><span class="sxs-lookup"><span data-stu-id="d5db3-104">You can create and post vendor invoices on behalf of nontaxpayer vendors.</span></span> <span data-ttu-id="d5db3-105">Você deve atribuir um estabelecimento fiscal a um site.</span><span class="sxs-lookup"><span data-stu-id="d5db3-105">You must assign a fiscal establishment to a site.</span></span> <span data-ttu-id="d5db3-106">Você também deve configurar um tipo de documento fiscal para as ordens de compra que você criar e lançar no nome de fornecedores que não são contribuintes.</span><span class="sxs-lookup"><span data-stu-id="d5db3-106">You must also set up a fiscal document type for purchase orders that you create and post on behalf of nontaxpayer vendors.</span></span> <span data-ttu-id="d5db3-107">Antes de criar e lançar faturas de fornecedores no nome de fornecedores que não são contribuintes, é necessário especificar o fornecedor como fornecedor que não é contribuinte.</span><span class="sxs-lookup"><span data-stu-id="d5db3-107">Before you can create and post vendor invoices on behalf of a nontaxpayer vendor, you must specify the vendor as a nontaxpayer vendor.</span></span> <span data-ttu-id="d5db3-108">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="d5db3-108">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="d5db3-109">Vá para Contas a pagar > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="d5db3-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="d5db3-110">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d5db3-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d5db3-111">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d5db3-111">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d5db3-112">Expanda a seção Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="d5db3-112">Expand the Fiscal information section.</span></span>
5. <span data-ttu-id="d5db3-113">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d5db3-113">Click Edit.</span></span>
6. <span data-ttu-id="d5db3-114">Selecione Sim no campo Gerar nota fiscal recebida.</span><span class="sxs-lookup"><span data-stu-id="d5db3-114">Select Yes in the Generate incoming fiscal document field.</span></span>
    * <span data-ttu-id="d5db3-115">Marque esta opção para indicar que o fornecedor é um não contribuinte.</span><span class="sxs-lookup"><span data-stu-id="d5db3-115">Select this option to indicate that the vendor is a nontaxpayer.</span></span>  
7. <span data-ttu-id="d5db3-116">Selecione Sim no campo Uso e consumo.</span><span class="sxs-lookup"><span data-stu-id="d5db3-116">Select Yes in the Use and consumption field.</span></span>
8. <span data-ttu-id="d5db3-117">Selecione Não no campo Contribuinte do ICMS.</span><span class="sxs-lookup"><span data-stu-id="d5db3-117">Select No in the ICMS contributor field.</span></span>
9. <span data-ttu-id="d5db3-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d5db3-118">Click Save.</span></span>
10. <span data-ttu-id="d5db3-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-119">Close the page.</span></span>
11. <span data-ttu-id="d5db3-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-120">Close the page.</span></span>
12. <span data-ttu-id="d5db3-121">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d5db3-121">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
13. <span data-ttu-id="d5db3-122">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d5db3-122">Click New.</span></span>
14. <span data-ttu-id="d5db3-123">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5db3-123">In the Vendor account field, enter or select a value.</span></span>
    * <span data-ttu-id="d5db3-124">Selecione uma conta de fornecedor que é classificada como não contribuinte.</span><span class="sxs-lookup"><span data-stu-id="d5db3-124">Select a vendor account that is classified as a nontaxpayer.</span></span>  
15. <span data-ttu-id="d5db3-125">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d5db3-125">Click OK.</span></span>
16. <span data-ttu-id="d5db3-126">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5db3-126">In the Item number field, enter or select a value.</span></span>
17. <span data-ttu-id="d5db3-127">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5db3-127">In the CFOP field, enter or select a value.</span></span>
18. <span data-ttu-id="d5db3-128">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5db3-128">In the Site field, enter or select a value.</span></span>
19. <span data-ttu-id="d5db3-129">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d5db3-129">In the Warehouse field, enter or select a value.</span></span>
20. <span data-ttu-id="d5db3-130">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d5db3-130">In the Quantity field, enter a number.</span></span>
21. <span data-ttu-id="d5db3-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d5db3-131">Click Save.</span></span>
22. <span data-ttu-id="d5db3-132">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="d5db3-132">On the Action Pane, click Purchase.</span></span>
23. <span data-ttu-id="d5db3-133">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d5db3-133">Click Confirm.</span></span>
24. <span data-ttu-id="d5db3-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-134">Close the page.</span></span>
25. <span data-ttu-id="d5db3-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-135">Close the page.</span></span>
26. <span data-ttu-id="d5db3-136">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d5db3-136">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
27. <span data-ttu-id="d5db3-137">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d5db3-137">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="d5db3-138">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="d5db3-138">On the Action Pane, click Invoice.</span></span>
29. <span data-ttu-id="d5db3-139">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="d5db3-139">Click Invoice.</span></span>
30. <span data-ttu-id="d5db3-140">Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d5db3-140">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
31. <span data-ttu-id="d5db3-141">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d5db3-141">In the Default quantity for lines field, select an option.</span></span>
32. <span data-ttu-id="d5db3-142">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d5db3-142">Click OK.</span></span>
33. <span data-ttu-id="d5db3-143">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="d5db3-143">Click Post.</span></span>
34. <span data-ttu-id="d5db3-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-144">Close the page.</span></span>
35. <span data-ttu-id="d5db3-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d5db3-145">Close the page.</span></span>
36. <span data-ttu-id="d5db3-146">Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.</span><span class="sxs-lookup"><span data-stu-id="d5db3-146">Go to Accounts receivable > Fiscal documents > Electronic fiscal documents > Export/import NF-e process.</span></span>
37. <span data-ttu-id="d5db3-147">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d5db3-147">Click OK.</span></span>


