---
title: Calcular juros e multas em pagamentos de clientes (Brasil)
description: Você pode aplicar juros e multas a pagamentos de cliente que estejam atrasados.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1f126644ce6f6ca53a118201f4c4cfe6375e8be
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174729"
---
# <a name="calculate-interest-and-fines-on-customer-payments-brazil"></a><span data-ttu-id="26a76-103">Calcular juros e multas em pagamentos de clientes (Brasil)</span><span class="sxs-lookup"><span data-stu-id="26a76-103">Calculate interest and fines on customer payments (Brazil)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="26a76-104">Você pode aplicar juros e multas a pagamentos de cliente que estejam atrasados.</span><span class="sxs-lookup"><span data-stu-id="26a76-104">You can apply interest and fines on customer payments that are delayed.</span></span> <span data-ttu-id="26a76-105">Os valores dos juros e da multa que se aplicam a um pagamento podem ser calculados quando você recebe um pagamento de um cliente.</span><span class="sxs-lookup"><span data-stu-id="26a76-105">The interest and fine amounts that apply to a payment can be calculated when you receive a payment from a customer.</span></span> <span data-ttu-id="26a76-106">Antes de calcular os códigos de juros ou de multa para pagamentos de cliente, você deverá configurar uma lista de feriados bancários e de feriados nacionais.</span><span class="sxs-lookup"><span data-stu-id="26a76-106">Before you calculate interest or fine codes for customer payments, you must set up a list of bank holidays and national holidays.</span></span> <span data-ttu-id="26a76-107">Uma data de feriado que é configurada na página Calendário de pagamentos será considerada como um dia que não é útil.</span><span class="sxs-lookup"><span data-stu-id="26a76-107">A holiday date that is set up on the Payment calendar page is considered a non-working day.</span></span> <span data-ttu-id="26a76-108">Se uma fatura vencer em um dia que não seja útil, a data de vencimento se deslocará para o próximo dia útil no calendário, e os juros e as multas serão calculadas de acordo com essa data.</span><span class="sxs-lookup"><span data-stu-id="26a76-108">If an invoice is due on a non-working day, the due date is moved to the next working day in the calendar, and the interest and fines are calculated accordingly.</span></span> <span data-ttu-id="26a76-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="26a76-109">This task uses the BRMF demo company.</span></span>



1. <span data-ttu-id="26a76-110">Ir para Contas recebíveis > Clientes > Todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="26a76-110">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="26a76-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="26a76-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="26a76-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="26a76-113">Expanda a seção de padrões de pagamento.</span><span class="sxs-lookup"><span data-stu-id="26a76-113">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="26a76-114">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="26a76-114">Click Edit.</span></span>
6. <span data-ttu-id="26a76-115">No campo Plano de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-115">In the Payment schedule field, enter or select a value.</span></span>
7. <span data-ttu-id="26a76-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="26a76-117">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-117">In the Fine code field, enter or select a value.</span></span>
9. <span data-ttu-id="26a76-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="26a76-119">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-119">In the Interest code field, enter or select a value.</span></span>
11. <span data-ttu-id="26a76-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="26a76-120">Click Save.</span></span>
12. <span data-ttu-id="26a76-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-121">Close the page.</span></span>
13. <span data-ttu-id="26a76-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-122">Close the page.</span></span>
14. <span data-ttu-id="26a76-123">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="26a76-123">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
15. <span data-ttu-id="26a76-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="26a76-124">Click New.</span></span>
16. <span data-ttu-id="26a76-125">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-125">In the Customer account field, enter or select a value.</span></span>
17. <span data-ttu-id="26a76-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="26a76-126">Click OK.</span></span>
18. <span data-ttu-id="26a76-127">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="26a76-127">Click Add line.</span></span>
19. <span data-ttu-id="26a76-128">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-128">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="26a76-129">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-129">In the Item number field, enter or select a value.</span></span>
21. <span data-ttu-id="26a76-130">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="26a76-130">In the Quantity field, enter a number.</span></span>
22. <span data-ttu-id="26a76-131">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-131">In the CFOP field, enter or select a value.</span></span>
23. <span data-ttu-id="26a76-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="26a76-132">Click Save.</span></span>
24. <span data-ttu-id="26a76-133">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="26a76-133">Click Invoice.</span></span>
25. <span data-ttu-id="26a76-134">No campo Quantidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="26a76-134">In the Quantity field, select an option.</span></span>
26. <span data-ttu-id="26a76-135">Selecione Sim no campo Imprimir fatura.</span><span class="sxs-lookup"><span data-stu-id="26a76-135">Select Yes in the Print invoice field.</span></span>
27. <span data-ttu-id="26a76-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="26a76-136">Click OK.</span></span>
28. <span data-ttu-id="26a76-137">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="26a76-137">Click Yes.</span></span>
29. <span data-ttu-id="26a76-138">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-138">Close the page.</span></span>
30. <span data-ttu-id="26a76-139">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-139">Close the page.</span></span>
31. <span data-ttu-id="26a76-140">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-140">Close the page.</span></span>
32. <span data-ttu-id="26a76-141">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="26a76-141">Go to Accounts receivable > Payments > Payment journal.</span></span>
33. <span data-ttu-id="26a76-142">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="26a76-142">Click New.</span></span>
34. <span data-ttu-id="26a76-143">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-143">In the list, mark the selected row.</span></span>
35. <span data-ttu-id="26a76-144">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-144">In the Name field, enter or select a value.</span></span>
36. <span data-ttu-id="26a76-145">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="26a76-145">Click Lines.</span></span>
37. <span data-ttu-id="26a76-146">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-146">In the list, mark the selected row.</span></span>
38. <span data-ttu-id="26a76-147">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="26a76-147">In the Date field, enter a date.</span></span>
39. <span data-ttu-id="26a76-148">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="26a76-148">In the Account field, specify the desired values.</span></span>
40. <span data-ttu-id="26a76-149">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="26a76-149">Click Settle transactions.</span></span>
41. <span data-ttu-id="26a76-150">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="26a76-150">In the list, find and select the desired record.</span></span>
42. <span data-ttu-id="26a76-151">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="26a76-151">Select the Mark check box.</span></span>
43. <span data-ttu-id="26a76-152">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="26a76-152">Select the Mark check box.</span></span>
44. <span data-ttu-id="26a76-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="26a76-153">Click OK.</span></span>
45. <span data-ttu-id="26a76-154">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="26a76-154">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="26a76-155">No campo Descrição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="26a76-155">In the Description field, enter or select a value.</span></span>
47. <span data-ttu-id="26a76-156">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="26a76-156">In the Offset account field, specify the desired values.</span></span>
48. <span data-ttu-id="26a76-157">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="26a76-157">Click Post.</span></span>
49. <span data-ttu-id="26a76-158">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-158">Close the page.</span></span>
50. <span data-ttu-id="26a76-159">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="26a76-159">Close the page.</span></span>

