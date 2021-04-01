---
title: Calcular juros e multas sobre pagamentos de fornecedores (Brasil)
description: Você pode aplicar juros e multas a pagamentos de fornecedor que estejam atrasados.
author: sndray
manager: AnnBe
ms.date: 06/26/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: af04adef9ba7a2c7b6e28ab5907beb56b5eb952e
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5231490"
---
# <a name="calculate-interest-and-fines-on-vendor-payments-brazil"></a><span data-ttu-id="1e55c-103">Calcular juros e multas sobre pagamentos de fornecedores (Brasil)</span><span class="sxs-lookup"><span data-stu-id="1e55c-103">Calculate interest and fines on vendor payments (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1e55c-104">Você pode aplicar juros e multas a pagamentos de fornecedor que estejam atrasados.</span><span class="sxs-lookup"><span data-stu-id="1e55c-104">You can apply interest and fines on vendor payments that are delayed.</span></span> <span data-ttu-id="1e55c-105">Os valores dos juros e da multa que se aplicam a um pagamento podem ser calculados quando você faz um pagamento para um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-105">The interest and fine amounts that apply to a payment can be calculated when you make a payment to a vendor.</span></span> <span data-ttu-id="1e55c-106">Antes de calcular os códigos de juros ou de multa para pagamentos de fornecedor, você deverá configurar uma lista de feriados bancários e de feriados nacionais.</span><span class="sxs-lookup"><span data-stu-id="1e55c-106">Before you calculate interest or fine codes for vendor payments, you must set up a list of bank holidays and national holidays.</span></span> <span data-ttu-id="1e55c-107">Uma data de feriado que é configurada na página Calendário de pagamentos será considerada como um dia que não é útil.</span><span class="sxs-lookup"><span data-stu-id="1e55c-107">A holiday date that is set up on the Payment calendar page is considered a non-working day.</span></span> <span data-ttu-id="1e55c-108">Se uma fatura vencer em um dia que não seja útil, a data de vencimento se deslocará para o próximo dia útil no calendário, e os juros e as multas serão calculadas de acordo com essa data.</span><span class="sxs-lookup"><span data-stu-id="1e55c-108">If an invoice is due on a non-working day, the due date is moved to the next working day in the calendar, and the interest and fines are calculated accordingly.</span></span> <span data-ttu-id="1e55c-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="1e55c-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="1e55c-110">Vá para Contas a pagar > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="1e55c-110">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="1e55c-111">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1e55c-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="1e55c-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1e55c-113">Expandir a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="1e55c-113">Expand the Payment section.</span></span>
5. <span data-ttu-id="1e55c-114">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-114">Click Edit.</span></span>
6. <span data-ttu-id="1e55c-115">No campo Plano de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-115">In the Payment schedule field, enter or select a value.</span></span>
7. <span data-ttu-id="1e55c-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-116">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="1e55c-117">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-117">In the Fine code field, enter or select a value.</span></span>
9. <span data-ttu-id="1e55c-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-118">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="1e55c-119">No campo Código de juros, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-119">In the Interest code field, enter or select a value.</span></span>
11. <span data-ttu-id="1e55c-120">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-120">Click Save.</span></span>
12. <span data-ttu-id="1e55c-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-121">Close the page.</span></span>
13. <span data-ttu-id="1e55c-122">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-122">Close the page.</span></span>
14. <span data-ttu-id="1e55c-123">Vá para Aquisição e fornecimento > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="1e55c-123">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
15. <span data-ttu-id="1e55c-124">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1e55c-124">Click New.</span></span>
16. <span data-ttu-id="1e55c-125">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-125">In the Vendor account field, enter or select a value.</span></span>
17. <span data-ttu-id="1e55c-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1e55c-126">Click OK.</span></span>
18. <span data-ttu-id="1e55c-127">Clique em Adicionar nova linha.</span><span class="sxs-lookup"><span data-stu-id="1e55c-127">Click Add line.</span></span>
19. <span data-ttu-id="1e55c-128">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-128">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="1e55c-129">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-129">In the Item number field, enter or select a value.</span></span>
21. <span data-ttu-id="1e55c-130">No campo CFOP, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-130">In the CFOP field, enter or select a value.</span></span>
22. <span data-ttu-id="1e55c-131">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="1e55c-131">In the Quantity field, enter a number.</span></span>
23. <span data-ttu-id="1e55c-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-132">Click Save.</span></span>
24. <span data-ttu-id="1e55c-133">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="1e55c-133">On the Action Pane, click Purchase.</span></span>
25. <span data-ttu-id="1e55c-134">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-134">Click Confirm.</span></span>
26. <span data-ttu-id="1e55c-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-135">Close the page.</span></span>
27. <span data-ttu-id="1e55c-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-136">Close the page.</span></span>
28. <span data-ttu-id="1e55c-137">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="1e55c-137">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
29. <span data-ttu-id="1e55c-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-138">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="1e55c-139">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="1e55c-139">On the Action Pane, click Invoice.</span></span>
31. <span data-ttu-id="1e55c-140">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="1e55c-140">Click Invoice.</span></span>
32. <span data-ttu-id="1e55c-141">Clique em Padrão de: Quantidade de recebimento de produtos para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="1e55c-141">Click Default from: Product receipt quantity to open the drop dialog.</span></span>
33. <span data-ttu-id="1e55c-142">No campo Quantidade padrão para linhas, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="1e55c-142">In the Default quantity for lines field, select an option.</span></span>
34. <span data-ttu-id="1e55c-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1e55c-143">Click OK.</span></span>
35. <span data-ttu-id="1e55c-144">No campo Chave de acesso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-144">In the Access key field, type a value.</span></span>
36. <span data-ttu-id="1e55c-145">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1e55c-145">In the Invoice date field, enter a date.</span></span>
37. <span data-ttu-id="1e55c-146">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-146">Click Post.</span></span>
38. <span data-ttu-id="1e55c-147">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-147">Close the page.</span></span>
39. <span data-ttu-id="1e55c-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-148">Close the page.</span></span>
40. <span data-ttu-id="1e55c-149">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="1e55c-149">Go to Accounts payable > Payments > Payment journal.</span></span>
41. <span data-ttu-id="1e55c-150">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="1e55c-150">Click New.</span></span>
42. <span data-ttu-id="1e55c-151">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-151">In the list, mark the selected row.</span></span>
43. <span data-ttu-id="1e55c-152">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-152">In the Name field, enter or select a value.</span></span>
44. <span data-ttu-id="1e55c-153">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="1e55c-153">Click Lines.</span></span>
45. <span data-ttu-id="1e55c-154">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-154">In the list, mark the selected row.</span></span>
46. <span data-ttu-id="1e55c-155">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="1e55c-155">In the Date field, enter a date.</span></span>
47. <span data-ttu-id="1e55c-156">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="1e55c-156">In the Account field, specify the desired values.</span></span>
48. <span data-ttu-id="1e55c-157">No campo Descrição, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="1e55c-157">In the Description field, enter or select a value.</span></span>
49. <span data-ttu-id="1e55c-158">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="1e55c-158">Click Settle transactions.</span></span>
50. <span data-ttu-id="1e55c-159">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="1e55c-159">In the list, find and select the desired record.</span></span>
51. <span data-ttu-id="1e55c-160">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-160">Select the Mark check box.</span></span>
52. <span data-ttu-id="1e55c-161">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-161">Select the Mark check box.</span></span>
53. <span data-ttu-id="1e55c-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="1e55c-162">Click OK.</span></span>
54. <span data-ttu-id="1e55c-163">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="1e55c-163">In the list, mark the selected row.</span></span>
55. <span data-ttu-id="1e55c-164">No campo Contrapartida, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="1e55c-164">In the Offset account field, specify the desired values.</span></span>
56. <span data-ttu-id="1e55c-165">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="1e55c-165">Click Post.</span></span>
57. <span data-ttu-id="1e55c-166">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-166">Close the page.</span></span>
58. <span data-ttu-id="1e55c-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="1e55c-167">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]