--- 
title: "Receber notas fiscais de fornecedor (ativos fixos - ICMS recuperável de longo prazo) (Brasil)"
description: "Você pode lançar uma nota fiscal recebida da aquisição dos ativos fixos."
author: sndray
manager: AnnBe
ms.date: 06/24/2017
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6f921a69e747eb0f9c2c6517034600e76665a74f
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="receive-vendor-fiscal-documents-fixed-assets---icms-long-term-recoverable-brazil"></a><span data-ttu-id="d72d5-103">Receber notas fiscais de fornecedor (ativos fixos - ICMS recuperável de longo prazo) (Brasil)</span><span class="sxs-lookup"><span data-stu-id="d72d5-103">Receive vendor fiscal documents (fixed assets - ICMS long term recoverable) (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d72d5-104">Você pode lançar uma nota fiscal recebida da aquisição dos ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d72d5-104">You can post a fiscal document that you receive from the acquisition of fixed assets.</span></span> <span data-ttu-id="d72d5-105">Você pode recuperar o ICMS ou o PIS/COFINS, ou ambos.</span><span class="sxs-lookup"><span data-stu-id="d72d5-105">You can recover the ICMS or PIS/COFINS taxes, or both.</span></span> <span data-ttu-id="d72d5-106">Você também pode recuperar mensalmente prestações de reembolso.</span><span class="sxs-lookup"><span data-stu-id="d72d5-106">You can also recover monthly refund installments.</span></span> <span data-ttu-id="d72d5-107">Esses valores são usados para deduzir o valor devido durante a apuração de imposto.</span><span class="sxs-lookup"><span data-stu-id="d72d5-107">These amounts are used to deduct the amount that is due during the tax assessment.</span></span> <span data-ttu-id="d72d5-108">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="d72d5-108">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="d72d5-109">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d72d5-109">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="d72d5-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d72d5-110">Click New.</span></span>
3. <span data-ttu-id="d72d5-111">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-111">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="d72d5-112">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d72d5-112">Click OK.</span></span>
5. <span data-ttu-id="d72d5-113">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="d72d5-113">Click Add line.</span></span>
6. <span data-ttu-id="d72d5-114">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d72d5-114">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="d72d5-115">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-115">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="d72d5-116">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-116">In the CFOP field, enter or select a value.</span></span>
9. <span data-ttu-id="d72d5-117">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-117">In the Site field, enter or select a value.</span></span>
10. <span data-ttu-id="d72d5-118">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-118">In the Warehouse field, enter or select a value.</span></span>
11. <span data-ttu-id="d72d5-119">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d72d5-119">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="d72d5-120">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d72d5-120">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="d72d5-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d72d5-121">Click Save.</span></span>
14. <span data-ttu-id="d72d5-122">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="d72d5-122">Expand the Line details section.</span></span>
15. <span data-ttu-id="d72d5-123">Clique na guia Ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="d72d5-123">Click the Fixed assets tab.</span></span>
16. <span data-ttu-id="d72d5-124">Selecione Sim no campo Novo ativo fixo? .</span><span class="sxs-lookup"><span data-stu-id="d72d5-124">Select Yes in the New fixed asset? field.</span></span>
17. <span data-ttu-id="d72d5-125">No campo Grupo de ativo fixo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-125">In the Fixed asset group field, enter or select a value.</span></span>
18. <span data-ttu-id="d72d5-126">Clique na guia Dimensões financeiras.</span><span class="sxs-lookup"><span data-stu-id="d72d5-126">Click the Financial dimensions tab.</span></span>
19. <span data-ttu-id="d72d5-127">No campo CostCenter, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-127">In the CostCenter field, enter or select a value.</span></span>
20. <span data-ttu-id="d72d5-128">No campo Filial, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-128">In the Filial field, enter or select a value.</span></span>
21. <span data-ttu-id="d72d5-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d72d5-129">Click Save.</span></span>
22. <span data-ttu-id="d72d5-130">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="d72d5-130">On the Action Pane, click Purchase.</span></span>
23. <span data-ttu-id="d72d5-131">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="d72d5-131">Click Confirm.</span></span>
24. <span data-ttu-id="d72d5-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d72d5-132">Close the page.</span></span>
25. <span data-ttu-id="d72d5-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d72d5-133">Close the page.</span></span>
26. <span data-ttu-id="d72d5-134">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d72d5-134">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
27. <span data-ttu-id="d72d5-135">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d72d5-135">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="d72d5-136">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="d72d5-136">On the Action Pane, click Invoice.</span></span>
29. <span data-ttu-id="d72d5-137">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="d72d5-137">Click Invoice.</span></span>
30. <span data-ttu-id="d72d5-138">Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="d72d5-138">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
31. <span data-ttu-id="d72d5-139">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="d72d5-139">In the Default quantity for lines field, select an option.</span></span>
32. <span data-ttu-id="d72d5-140">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d72d5-140">Click OK.</span></span>
33. <span data-ttu-id="d72d5-141">No campo Modelo do documento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-141">In the Document model field, enter or select a value.</span></span>
34. <span data-ttu-id="d72d5-142">No campo Chave de acesso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d72d5-142">In the Access key field, type a value.</span></span>
35. <span data-ttu-id="d72d5-143">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d72d5-143">In the Invoice date field, enter a date.</span></span>
36. <span data-ttu-id="d72d5-144">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d72d5-144">Click Save.</span></span>
37. <span data-ttu-id="d72d5-145">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="d72d5-145">Click Post.</span></span>
38. <span data-ttu-id="d72d5-146">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d72d5-146">Close the page.</span></span>
39. <span data-ttu-id="d72d5-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d72d5-147">Close the page.</span></span>


