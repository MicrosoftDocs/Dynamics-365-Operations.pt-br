---
title: Impostos retidos na fonte em pagamentos de clientes (Brasil)
description: Use a página Comprovante de diário para inserir e lançar pagamentos recebidos de clientes pela venda de itens ou serviços.
author: sndray
manager: AnnBe
ms.date: 06/27/2017
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
ms.openlocfilehash: afed7152babd231d2665b09926c8cc1b820efd00
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2183874"
---
# <a name="withholding-taxes-on-customer-payments-brazil"></a><span data-ttu-id="b4b69-103">Impostos retidos na fonte em pagamentos de clientes (Brasil)</span><span class="sxs-lookup"><span data-stu-id="b4b69-103">Withholding taxes on customer payments (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4b69-104">Use a página Comprovante de diário para inserir e lançar pagamentos recebidos de clientes pela venda de itens ou serviços.</span><span class="sxs-lookup"><span data-stu-id="b4b69-104">You use the Journal voucher page to enter and post payments that you receive from customers for the sale of items or services.</span></span> <span data-ttu-id="b4b69-105">Quando você lança um diário de pagamento de cliente, o grupo de impostos retidos na fonte que está configurado para o cliente é usado para calcular o imposto retido na fonte na transação.</span><span class="sxs-lookup"><span data-stu-id="b4b69-105">When you post a customer payment journal, the withholding tax group that is set up for the customer is used to calculate the withholding tax on the transaction.</span></span> <span data-ttu-id="b4b69-106">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="b4b69-106">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="b4b69-107">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="b4b69-107">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="b4b69-108">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b4b69-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b4b69-109">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4b69-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b4b69-110">Expanda a seção Fatura e entrega.</span><span class="sxs-lookup"><span data-stu-id="b4b69-110">Expand the Invoice and delivery section.</span></span>
5. <span data-ttu-id="b4b69-111">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-111">Click Edit.</span></span>
6. <span data-ttu-id="b4b69-112">Selecione Sim no campo Calcular imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b4b69-112">Select Yes in the Calculate withholding tax field.</span></span>
7. <span data-ttu-id="b4b69-113">No campo Grupo de impostos retidos na fonte, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-113">In the Withholding tax group field, enter or select a value.</span></span>
8. <span data-ttu-id="b4b69-114">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-114">Click Save.</span></span>
9. <span data-ttu-id="b4b69-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-115">Close the page.</span></span>
10. <span data-ttu-id="b4b69-116">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-116">Close the page.</span></span>
11. <span data-ttu-id="b4b69-117">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b4b69-117">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
12. <span data-ttu-id="b4b69-118">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b4b69-118">Click New.</span></span>
13. <span data-ttu-id="b4b69-119">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-119">In the Customer account field, enter or select a value.</span></span>
14. <span data-ttu-id="b4b69-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b4b69-120">Click OK.</span></span>
15. <span data-ttu-id="b4b69-121">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4b69-121">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="b4b69-122">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-122">In the Item number field, enter or select a value.</span></span>
17. <span data-ttu-id="b4b69-123">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b4b69-123">In the Quantity field, enter a number.</span></span>
18. <span data-ttu-id="b4b69-124">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-124">In the Site field, enter or select a value.</span></span>
19. <span data-ttu-id="b4b69-125">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="b4b69-125">Expand the Line details section.</span></span>
20. <span data-ttu-id="b4b69-126">Clique na guia Configuração.</span><span class="sxs-lookup"><span data-stu-id="b4b69-126">Click the Setup tab.</span></span>
21. <span data-ttu-id="b4b69-127">No campo Grupo de impostos retidos na fonte do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-127">In the Item withholding tax group field, enter or select a value.</span></span>
22. <span data-ttu-id="b4b69-128">No campo Grupo de impostos retidos na fonte, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-128">In the Withholding tax group field, enter or select a value.</span></span>
23. <span data-ttu-id="b4b69-129">Clique na guia Informações fiscais.</span><span class="sxs-lookup"><span data-stu-id="b4b69-129">Click the Fiscal information tab.</span></span>
24. <span data-ttu-id="b4b69-130">No campo Nota fiscal, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-130">In the Fiscal document type field, enter or select a value.</span></span>
25. <span data-ttu-id="b4b69-131">No campo Código de serviço, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-131">In the Service code field, enter or select a value.</span></span>
26. <span data-ttu-id="b4b69-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-132">Click Save.</span></span>
27. <span data-ttu-id="b4b69-133">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="b4b69-133">Click Invoice.</span></span>
28. <span data-ttu-id="b4b69-134">No campo Quantidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="b4b69-134">In the Quantity field, select an option.</span></span>
29. <span data-ttu-id="b4b69-135">Selecione Sim no campo Imprimir fatura.</span><span class="sxs-lookup"><span data-stu-id="b4b69-135">Select Yes in the Print invoice field.</span></span>
30. <span data-ttu-id="b4b69-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b4b69-136">Click OK.</span></span>
31. <span data-ttu-id="b4b69-137">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="b4b69-137">Click Yes.</span></span>
32. <span data-ttu-id="b4b69-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-138">Close the page.</span></span>
33. <span data-ttu-id="b4b69-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-139">Close the page.</span></span>
34. <span data-ttu-id="b4b69-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-140">Close the page.</span></span>
35. <span data-ttu-id="b4b69-141">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="b4b69-141">Go to Accounts receivable > Payments > Payment journal.</span></span>
36. <span data-ttu-id="b4b69-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b4b69-142">Click New.</span></span>
37. <span data-ttu-id="b4b69-143">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4b69-143">In the list, mark the selected row.</span></span>
38. <span data-ttu-id="b4b69-144">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-144">In the Name field, enter or select a value.</span></span>
39. <span data-ttu-id="b4b69-145">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="b4b69-145">Click Lines.</span></span>
40. <span data-ttu-id="b4b69-146">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4b69-146">In the list, mark the selected row.</span></span>
41. <span data-ttu-id="b4b69-147">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b4b69-147">In the Account field, specify the desired values.</span></span>
42. <span data-ttu-id="b4b69-148">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="b4b69-148">Click Settle transactions.</span></span>
43. <span data-ttu-id="b4b69-149">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b4b69-149">In the list, find and select the desired record.</span></span>
44. <span data-ttu-id="b4b69-150">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-150">Select the Mark check box.</span></span>
45. <span data-ttu-id="b4b69-151">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-151">Select the Mark check box.</span></span>
46. <span data-ttu-id="b4b69-152">Clique na guia Imposto retido na fonte.</span><span class="sxs-lookup"><span data-stu-id="b4b69-152">Click the Withholding tax tab.</span></span>
47. <span data-ttu-id="b4b69-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b4b69-153">Click OK.</span></span>
48. <span data-ttu-id="b4b69-154">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4b69-154">In the list, mark the selected row.</span></span>
49. <span data-ttu-id="b4b69-155">No campo Descrição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b4b69-155">In the Description field, enter or select a value.</span></span>
50. <span data-ttu-id="b4b69-156">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b4b69-156">In the Offset account field, specify the desired values.</span></span>
51. <span data-ttu-id="b4b69-157">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b4b69-157">Click Post.</span></span>
52. <span data-ttu-id="b4b69-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-158">Close the page.</span></span>
53. <span data-ttu-id="b4b69-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4b69-159">Close the page.</span></span>
