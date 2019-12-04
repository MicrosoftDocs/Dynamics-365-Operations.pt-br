---
title: Guias de entrega (Brasil)
description: Você pode lançar uma guia de entrega para uma ordem de venda com várias linhas de ordem de venda com um código CFOP (Código Fiscal de Operações e Prestações).
author: sndray
manager: AnnBe
ms.date: 06/24/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83f55b3d78bd9804512b178b1d9a3cdea2cb383a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175181"
---
# <a name="delivery-slips-brazil"></a><span data-ttu-id="cd266-103">Guias de entrega (Brasil)</span><span class="sxs-lookup"><span data-stu-id="cd266-103">Delivery slips (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cd266-104">Você pode lançar uma guia de entrega para uma ordem de venda com várias linhas de ordem de venda com um código CFOP (Código Fiscal de Operações e Prestações).</span><span class="sxs-lookup"><span data-stu-id="cd266-104">You can post a delivery slip for a sales order that has multiple sales order lines that have a delivery Código Fiscal de Operações e Prestações (CFOP) code.</span></span> <span data-ttu-id="cd266-105">Para cada linha de ordem de venda, você deve especificar o código CFOP que tem um código CFOP de entrega atribuído a ele.</span><span class="sxs-lookup"><span data-stu-id="cd266-105">For each sales order line, you must specify the CFOP code that has a delivery CFOP code assigned to it.</span></span> <span data-ttu-id="cd266-106">Uma guia de entrega é usada quando o cliente para o qual você entrega itens difere do cliente que é faturado.</span><span class="sxs-lookup"><span data-stu-id="cd266-106">A delivery slip is used when the customer that you deliver items to differs from the customer that is invoiced.</span></span> <span data-ttu-id="cd266-107">(Ou seja, a conta do cliente e a conta da fatura diferem.) As guias de entrega são lançadas em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="cd266-107">(In other words, the customer account and invoice account differ.) Delivery slips are posted in chronological order.</span></span> <span data-ttu-id="cd266-108">É preciso anexar referências fiscais a guias de entrega antes de lançá-las.</span><span class="sxs-lookup"><span data-stu-id="cd266-108">You must attach fiscal references to delivery slips before you post them.</span></span> <span data-ttu-id="cd266-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="cd266-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="cd266-110">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="cd266-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="cd266-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="cd266-111">Click New.</span></span>
3. <span data-ttu-id="cd266-112">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="cd266-113">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cd266-113">Click OK.</span></span>
5. <span data-ttu-id="cd266-114">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cd266-114">In the Lines or header field, select an option.</span></span>
6. <span data-ttu-id="cd266-115">No campo Conta de fatura, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-115">In the Invoice account field, enter or select a value.</span></span>
    * <span data-ttu-id="cd266-116">Selecione o cliente que encomendou mercadorias.</span><span class="sxs-lookup"><span data-stu-id="cd266-116">Select the customer that ordered the goods.</span></span>  
7. <span data-ttu-id="cd266-117">No campo Linhas ou cabeçalho, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cd266-117">In the Lines or header field, select an option.</span></span>
8. <span data-ttu-id="cd266-118">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="cd266-118">Click Add line.</span></span>
9. <span data-ttu-id="cd266-119">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="cd266-119">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="cd266-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-120">In the Item number field, enter or select a value.</span></span>
11. <span data-ttu-id="cd266-121">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="cd266-121">In the Quantity field, enter a number.</span></span>
12. <span data-ttu-id="cd266-122">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-122">In the Site field, enter or select a value.</span></span>
13. <span data-ttu-id="cd266-123">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-123">In the Warehouse field, enter or select a value.</span></span>
14. <span data-ttu-id="cd266-124">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-124">In the CFOP field, enter or select a value.</span></span>
    * <span data-ttu-id="cd266-125">Os códigos de CFOP disponíveis dependem do estabelecimento fiscal do site, tipo de ordem, tipo de operação, localização do cliente e endereço de entrega do cliente.</span><span class="sxs-lookup"><span data-stu-id="cd266-125">The CFOP codes that are available depend on the fiscal establishment of the site, order type, operation type, location of the customer, and delivery address of the customer.</span></span>  
15. <span data-ttu-id="cd266-126">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="cd266-126">Expand the Line details section.</span></span>
16. <span data-ttu-id="cd266-127">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="cd266-127">Click the Setup tab.</span></span>
17. <span data-ttu-id="cd266-128">No campo Grupo de imposto do item de entrega, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-128">In the Delivery item sales tax group field, enter or select a value.</span></span>
    * <span data-ttu-id="cd266-129">Insira o grupo de impostos sobre vendas do item para a nota fiscal de entrega.</span><span class="sxs-lookup"><span data-stu-id="cd266-129">Enter the item sales tax group for the delivery fiscal document.</span></span>  
18. <span data-ttu-id="cd266-130">No campo Grupo de imposto de entrega, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-130">In the Delivery sales tax group field, enter or select a value.</span></span>
    * <span data-ttu-id="cd266-131">Insira o grupo de impostos sobre vendas para a nota fiscal de entrega.</span><span class="sxs-lookup"><span data-stu-id="cd266-131">Enter the sales tax group for the delivery fiscal document.</span></span>  
19. <span data-ttu-id="cd266-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd266-132">Click Save.</span></span>
20. <span data-ttu-id="cd266-133">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="cd266-133">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="cd266-134">Clique em Guia de entrega.</span><span class="sxs-lookup"><span data-stu-id="cd266-134">Click Delivery slip.</span></span>
22. <span data-ttu-id="cd266-135">Clique em Referência fiscal.</span><span class="sxs-lookup"><span data-stu-id="cd266-135">Click Fiscal reference.</span></span>
23. <span data-ttu-id="cd266-136">No campo Modelo do documento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-136">In the Document model field, enter or select a value.</span></span>
24. <span data-ttu-id="cd266-137">No campo Chave de acesso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-137">In the Access key field, type a value.</span></span>
    * <span data-ttu-id="cd266-138">Insira a chave de acesso da NF-e que foi emitida pelo cliente que encomendou mercadoria e ao qual as vendas devem ser faturadas.</span><span class="sxs-lookup"><span data-stu-id="cd266-138">Enter the access key from the NF-e that was issued by the customer that ordered to goods and that the sales must be invoiced to.</span></span>  
25. <span data-ttu-id="cd266-139">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="cd266-139">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="cd266-140">No campo Direção, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="cd266-140">In the Direction field, select an option.</span></span>
27. <span data-ttu-id="cd266-141">No campo Conta, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="cd266-141">In the Account field, enter or select a value.</span></span>
    * <span data-ttu-id="cd266-142">Selecione a conta do cliente que gerou a nota fiscal.</span><span class="sxs-lookup"><span data-stu-id="cd266-142">Select the customer account that generated the fiscal document.</span></span>  
28. <span data-ttu-id="cd266-143">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="cd266-143">Click Save.</span></span>
29. <span data-ttu-id="cd266-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd266-144">Close the page.</span></span>
30. <span data-ttu-id="cd266-145">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cd266-145">Click OK.</span></span>
31. <span data-ttu-id="cd266-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cd266-146">Click OK.</span></span>
32. <span data-ttu-id="cd266-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd266-147">Close the page.</span></span>
33. <span data-ttu-id="cd266-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="cd266-148">Close the page.</span></span>
34. <span data-ttu-id="cd266-149">Vá para Contas a receber > Notas fiscais > Notas fiscais eletrônicas > Exportar/importar processo de NF-e.</span><span class="sxs-lookup"><span data-stu-id="cd266-149">Go to Accounts receivable > Fiscal documents > Electronic fiscal documents > Export/import NF-e process.</span></span>
35. <span data-ttu-id="cd266-150">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="cd266-150">Click OK.</span></span>
