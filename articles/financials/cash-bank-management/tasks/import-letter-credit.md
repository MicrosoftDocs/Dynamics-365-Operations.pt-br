--- 
title: "Importar uma carta de crédito"
description: "Este procedimento apresenta o processo de importação de uma carta de crédito."
author: kweekley
manager: AnnBe
ms.date: 02/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 02be2627186a149a05eaccfa3e5906a9fe1d74dd
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="import-a-letter-of-credit"></a><span data-ttu-id="b0753-103">Importar uma carta de crédito</span><span class="sxs-lookup"><span data-stu-id="b0753-103">Import a letter of credit</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b0753-104">Este procedimento apresenta o processo de importação de uma carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-104">This procedure walks through the process of importing a letter of credit.</span></span> <span data-ttu-id="b0753-105">As seguintes tarefas devem ser configuradas antes da conclusão deste procedimento: recursos bancários, perfis de lançamento, contrato de recurso bancário e detalhes bancários do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b0753-105">The following must be set up before completing this procedure: bank facilities, posting profiles, a bank facility agreement and vendor bank details.</span></span>

<span data-ttu-id="b0753-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="b0753-106">This procedure uses the USMF demo company.</span></span>


## <a name="create-a-purchase-order-with-letter-of-credit"></a><span data-ttu-id="b0753-107">Crie uma Ordem de compra com Carta de crédito</span><span class="sxs-lookup"><span data-stu-id="b0753-107">Create a Purchase order with Letter of credit</span></span>
1. <span data-ttu-id="b0753-108">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-108">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="b0753-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b0753-109">Click New.</span></span>
3. <span data-ttu-id="b0753-110">No campo Conta de fornecedor, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-110">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="b0753-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="b0753-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b0753-113">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="b0753-113">Expand the General section.</span></span>
7. <span data-ttu-id="b0753-114">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-114">In the Site field, enter or select a value.</span></span>
8. <span data-ttu-id="b0753-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b0753-116">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-116">In the Warehouse field, enter or select a value.</span></span>
10. <span data-ttu-id="b0753-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-117">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="b0753-118">No campo Data contábil, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-118">In the Accounting date field, enter a date.</span></span>
12. <span data-ttu-id="b0753-119">No campo Data de entrega, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-119">In the Delivery date field, enter a date.</span></span>
    * <span data-ttu-id="b0753-120">Observação: O campo 'Tipo de documento bancário' deve ser selecionado com o valor 'Carta de crédito'.</span><span class="sxs-lookup"><span data-stu-id="b0753-120">Note: The 'Bank document type' field should be selected with the value  'Letter of credit'.</span></span>  
13. <span data-ttu-id="b0753-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-121">Click OK.</span></span>
14. <span data-ttu-id="b0753-122">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-122">In the Item number field, enter or select a value.</span></span>
15. <span data-ttu-id="b0753-123">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="b0753-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="b0753-125">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="b0753-125">Expand the Line details section.</span></span>
18. <span data-ttu-id="b0753-126">Clique na guia Entrega.</span><span class="sxs-lookup"><span data-stu-id="b0753-126">Click the Delivery tab.</span></span>
19. <span data-ttu-id="b0753-127">No campo Data de entrega, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-127">In the Delivery date field, enter a date.</span></span>
20. <span data-ttu-id="b0753-128">No campo Data de entrega confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-128">In the Confirmed delivery date field, enter a date.</span></span>
21. <span data-ttu-id="b0753-129">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b0753-129">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="b0753-130">Define os detalhes da Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-130">Define the Letter of credit details.</span></span>  
22. <span data-ttu-id="b0753-131">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b0753-131">On the Action Pane, click Manage.</span></span>
23. <span data-ttu-id="b0753-132">Clique em Carta de crédito/coleção de importação.</span><span class="sxs-lookup"><span data-stu-id="b0753-132">Click Letter of credit / import collection.</span></span>
24. <span data-ttu-id="b0753-133">No campo Data da solicitação de emprego, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="b0753-133">In the Application date field, enter a date and time.</span></span>
    * <span data-ttu-id="b0753-134">Verifique se o campo “Conta bancária” tem a conta bancária ativa padrão, que é baseada na data de solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="b0753-134">Verify that the 'Bank account' field has the default active Bank account, which is based on the application date.</span></span>  
25. <span data-ttu-id="b0753-135">No campo Número do documento bancário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-135">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="b0753-136">No campo Data de recebimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="b0753-136">In the Date of receipt field, enter a date and time.</span></span>
27. <span data-ttu-id="b0753-137">Expanda a seção Documento bancário.</span><span class="sxs-lookup"><span data-stu-id="b0753-137">Expand the Bank document section.</span></span>
28. <span data-ttu-id="b0753-138">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="b0753-138">In the Expiration date field, enter a date and time.</span></span>
29. <span data-ttu-id="b0753-139">Expanda a seção Detalhes bancários.</span><span class="sxs-lookup"><span data-stu-id="b0753-139">Expand the Bank details section.</span></span>
30. <span data-ttu-id="b0753-140">No campo Banco avisador, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-140">In the Advising bank field, enter or select a value.</span></span>
31. <span data-ttu-id="b0753-141">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-141">In the list, click the link in the selected row.</span></span>
32. <span data-ttu-id="b0753-142">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0753-142">Click Save.</span></span>
33. <span data-ttu-id="b0753-143">Clique em Buscar remessas de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-143">Click Fetch purchase order shipments.</span></span>
34. <span data-ttu-id="b0753-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-144">Close the page.</span></span>
35. <span data-ttu-id="b0753-145">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-145">On the Action Pane, click Purchase.</span></span>
36. <span data-ttu-id="b0753-146">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="b0753-146">Click Confirm.</span></span>
37. <span data-ttu-id="b0753-147">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b0753-147">On the Action Pane, click Manage.</span></span>
38. <span data-ttu-id="b0753-148">Clique em Carta de crédito/coleção de importação.</span><span class="sxs-lookup"><span data-stu-id="b0753-148">Click Letter of credit / import collection.</span></span>
39. <span data-ttu-id="b0753-149">Clique em Processo.</span><span class="sxs-lookup"><span data-stu-id="b0753-149">Click Process.</span></span>
40. <span data-ttu-id="b0753-150">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="b0753-150">Click Confirm.</span></span>
    * <span data-ttu-id="b0753-151">Verifique se o saldo do recurso reduz o valor da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-151">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="b0753-152">Neste exemplo, valor de compra = 500,00, Limite de recurso = 10.000,00, consequentemente, Saldo de recursos = 9.500,00.</span><span class="sxs-lookup"><span data-stu-id="b0753-152">In this example, Purchase amount = 500.00,  Facility limit = 10000.00,  therefore, Facility balance = 9500.00.</span></span>  
41. <span data-ttu-id="b0753-153">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-153">Close the page.</span></span>
42. <span data-ttu-id="b0753-154">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b0753-154">In the Unit price field, enter a number.</span></span>
43. <span data-ttu-id="b0753-155">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b0753-155">Click Save.</span></span>
44. <span data-ttu-id="b0753-156">No Painel de Ação, clique em Compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-156">On the Action Pane, click Purchase.</span></span>
45. <span data-ttu-id="b0753-157">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="b0753-157">Click Confirm.</span></span>
    * <span data-ttu-id="b0753-158">Modifique a carta de crédito em decorrência de alteração no Preço unitário.</span><span class="sxs-lookup"><span data-stu-id="b0753-158">Amend the Letter of credit, due to the change in Unit price.</span></span>  
46. <span data-ttu-id="b0753-159">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b0753-159">On the Action Pane, click Manage.</span></span>
47. <span data-ttu-id="b0753-160">Clique em Carta de crédito/coleção de importação.</span><span class="sxs-lookup"><span data-stu-id="b0753-160">Click Letter of credit / import collection.</span></span>
    * <span data-ttu-id="b0753-161">Modifique a carta de crédito em decorrência de alteração no Preço unitário para compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-161">Amend the letter of credit, due to the change in Purchase unit price.</span></span>  
48. <span data-ttu-id="b0753-162">Clique em Processo.</span><span class="sxs-lookup"><span data-stu-id="b0753-162">Click Process.</span></span>
49. <span data-ttu-id="b0753-163">Clique em Corrigir.</span><span class="sxs-lookup"><span data-stu-id="b0753-163">Click Amend.</span></span>
50. <span data-ttu-id="b0753-164">Clique em Remover.</span><span class="sxs-lookup"><span data-stu-id="b0753-164">Click Remove.</span></span>
51. <span data-ttu-id="b0753-165">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="b0753-165">Click Yes.</span></span>
52. <span data-ttu-id="b0753-166">Clique em Buscar remessas de ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-166">Click Fetch purchase order shipments.</span></span>
53. <span data-ttu-id="b0753-167">Clique em Processo.</span><span class="sxs-lookup"><span data-stu-id="b0753-167">Click Process.</span></span>
54. <span data-ttu-id="b0753-168">Clique em Confirmar.</span><span class="sxs-lookup"><span data-stu-id="b0753-168">Click Confirm.</span></span>
    * <span data-ttu-id="b0753-169">Verifique se o saldo do recurso reduz o valor da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-169">Verify that the Facility balance reduces the purchase order amount.</span></span>  <span data-ttu-id="b0753-170">Neste exemplo, Valor de compra editado = 600,00, Limite de recurso = 10.000,00, consequentemente, Saldo de recursos = 9.400,00.</span><span class="sxs-lookup"><span data-stu-id="b0753-170">In this example, edited Purchase amount = 600.00,  Facility limit = 10000.00,  therefore, Facility balance = 9400.00.</span></span>  
55. <span data-ttu-id="b0753-171">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-171">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="b0753-172">Lance a guia de remessa</span><span class="sxs-lookup"><span data-stu-id="b0753-172">Post Packing slip</span></span>
1. <span data-ttu-id="b0753-173">No Painel de Ação, clique em Receber.</span><span class="sxs-lookup"><span data-stu-id="b0753-173">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="b0753-174">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="b0753-174">Click Product receipt.</span></span>
3. <span data-ttu-id="b0753-175">No campo PurchParmTable_Num, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-175">In the PurchParmTable_Num field, type a value.</span></span>
    * <span data-ttu-id="b0753-176">Selecione o número de remessa criado com referência à Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-176">Select the Shipment number created with reference to the Letter of credit.</span></span>  
4. <span data-ttu-id="b0753-177">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-177">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b0753-178">No campo Data de recebimento de produtos, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-178">In the Product receipt date field, enter a date.</span></span>
6. <span data-ttu-id="b0753-179">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-179">Click OK.</span></span>
7. <span data-ttu-id="b0753-180">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-180">Close the page.</span></span>
8. <span data-ttu-id="b0753-181">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-181">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="b0753-182">Verifique o status Importar carta de crédito</span><span class="sxs-lookup"><span data-stu-id="b0753-182">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="b0753-183">Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.</span><span class="sxs-lookup"><span data-stu-id="b0753-183">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="b0753-184">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-184">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b0753-185">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-185">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b0753-186">O status de Importar Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-186">Verify the Import letter of credit status.</span></span>  
4. <span data-ttu-id="b0753-187">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-187">Close the page.</span></span>
5. <span data-ttu-id="b0753-188">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-188">Close the page.</span></span>

## <a name="post-purchase-invoice"></a><span data-ttu-id="b0753-189">Lance a fatura de compra</span><span class="sxs-lookup"><span data-stu-id="b0753-189">Post purchase invoice</span></span>
1. <span data-ttu-id="b0753-190">Vá para Contas a pagar > Ordens de compra > Todas as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="b0753-190">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
    * <span data-ttu-id="b0753-191">Selecione a ordem de compra que foi criada com a carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-191">Select the purchase order that was created with letter of credit.</span></span>  
2. <span data-ttu-id="b0753-192">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-192">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b0753-193">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-193">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="b0753-194">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="b0753-194">On the Action Pane, click Invoice.</span></span>
5. <span data-ttu-id="b0753-195">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="b0753-195">Click Invoice.</span></span>
6. <span data-ttu-id="b0753-196">No campo Número, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-196">In the Number field, type a value.</span></span>
7. <span data-ttu-id="b0753-197">No campo Número da remessa, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-197">In the Shipment number field, enter or select a value.</span></span>
8. <span data-ttu-id="b0753-198">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-198">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="b0753-199">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-199">In the Invoice date field, enter a date.</span></span>
10. <span data-ttu-id="b0753-200">Clique em Atualizar status de conciliação.</span><span class="sxs-lookup"><span data-stu-id="b0753-200">Click Update match status.</span></span>
11. <span data-ttu-id="b0753-201">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b0753-201">Click Post.</span></span>
12. <span data-ttu-id="b0753-202">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-202">Close the page.</span></span>
13. <span data-ttu-id="b0753-203">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-203">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status"></a><span data-ttu-id="b0753-204">Verifique o status Importar carta de crédito</span><span class="sxs-lookup"><span data-stu-id="b0753-204">Verify Import letter of credit status</span></span>
1. <span data-ttu-id="b0753-205">Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.</span><span class="sxs-lookup"><span data-stu-id="b0753-205">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="b0753-206">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-206">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b0753-207">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-207">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b0753-208">Verifique Importar Carta de crédito 2.</span><span class="sxs-lookup"><span data-stu-id="b0753-208">Verify the Import letter of credit2.</span></span>  
    * <span data-ttu-id="b0753-209">Validar: Status da remessa = Detalhes do recurso bancário faturado</span><span class="sxs-lookup"><span data-stu-id="b0753-209">Validate :  Shipment status = Invoiced  Bank facility details</span></span>  
4. <span data-ttu-id="b0753-210">Clique em Exibir.</span><span class="sxs-lookup"><span data-stu-id="b0753-210">Click View.</span></span>
5. <span data-ttu-id="b0753-211">Clique em Imprimir solicitação de emprego.</span><span class="sxs-lookup"><span data-stu-id="b0753-211">Click Print application.</span></span>
6. <span data-ttu-id="b0753-212">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-212">Click OK.</span></span>
    * <span data-ttu-id="b0753-213">Verifique se a Carta da solicitação de crédito é impressa.</span><span class="sxs-lookup"><span data-stu-id="b0753-213">Verify that the Letter of credit application gets printed.</span></span>  
7. <span data-ttu-id="b0753-214">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-214">Close the page.</span></span>
8. <span data-ttu-id="b0753-215">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-215">Close the page.</span></span>
9. <span data-ttu-id="b0753-216">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-216">Close the page.</span></span>

## <a name="post-vendor-payment-journal-for-the-created-purchase-invoice-with-letter-of-credit"></a><span data-ttu-id="b0753-217">Lance o diário de pagamentos do fornecedor para a fatura de compra criada com a carta de crédito</span><span class="sxs-lookup"><span data-stu-id="b0753-217">Post Vendor payment journal for the created purchase invoice with letter of credit</span></span>
1. <span data-ttu-id="b0753-218">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="b0753-218">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="b0753-219">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b0753-219">Click New.</span></span>
3. <span data-ttu-id="b0753-220">No campo Nome, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-220">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="b0753-221">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-221">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="b0753-222">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="b0753-222">Click Lines.</span></span>
6. <span data-ttu-id="b0753-223">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="b0753-223">In the Date field, enter a date.</span></span>
7. <span data-ttu-id="b0753-224">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="b0753-224">In the Account field, specify the desired values.</span></span>
8. <span data-ttu-id="b0753-225">Clique em Liquidar transações.</span><span class="sxs-lookup"><span data-stu-id="b0753-225">Click Settle transactions.</span></span>
9. <span data-ttu-id="b0753-226">Expanda a seção Totais.</span><span class="sxs-lookup"><span data-stu-id="b0753-226">Expand the Totals section.</span></span>
10. <span data-ttu-id="b0753-227">No campo Mostrar, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="b0753-227">In the Show field, select an option.</span></span>
    * <span data-ttu-id="b0753-228">Verifique se os campos Número do documento bancário e Número de remessa foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="b0753-228">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
11. <span data-ttu-id="b0753-229">Marque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="b0753-229">Select the Mark check box.</span></span>
12. <span data-ttu-id="b0753-230">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-230">Click OK.</span></span>
13. <span data-ttu-id="b0753-231">Clique na aba Pagamento.</span><span class="sxs-lookup"><span data-stu-id="b0753-231">Click the Payment tab.</span></span>
    * <span data-ttu-id="b0753-232">Verifique se os campos Número do documento bancário e Número de remessa foram atualizados.</span><span class="sxs-lookup"><span data-stu-id="b0753-232">Verify that the Bank document number and Shipment number fields have been updated.</span></span>  
14. <span data-ttu-id="b0753-233">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b0753-233">Click Post.</span></span>
15. <span data-ttu-id="b0753-234">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-234">Close the page.</span></span>
16. <span data-ttu-id="b0753-235">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-235">Close the page.</span></span>

## <a name="verify-import-letter-of-credit-status-after-invoice-paid"></a><span data-ttu-id="b0753-236">Verifique o status de Importação da carta de crédito após a fatura ser paga</span><span class="sxs-lookup"><span data-stu-id="b0753-236">Verify Import letter of credit status after Invoice paid</span></span>
1. <span data-ttu-id="b0753-237">Vá para Gerenciamento de caixa e bancos > Cartas de crédito > Importar carta de crédito e importar coleção.</span><span class="sxs-lookup"><span data-stu-id="b0753-237">Go to Cash and bank management > Letters of credit > Import letter of credit and import collection.</span></span>
2. <span data-ttu-id="b0753-238">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="b0753-238">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="b0753-239">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-239">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b0753-240">O status de Importar Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="b0753-240">Verify the Import letter of credit status.</span></span>   
4. <span data-ttu-id="b0753-241">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-241">Close the page.</span></span>

## <a name="verify-the-bank-facility-limit-and-utilization-report"></a><span data-ttu-id="b0753-242">Verifique o limite de recurso do banco e o relatório de utilização</span><span class="sxs-lookup"><span data-stu-id="b0753-242">Verify the Bank facility limit and utilization report</span></span>
1. <span data-ttu-id="b0753-243">Vá para Gerenciamento de caixa e bancos > Consultas e relatórios > Cartas de crédito ou garantia > Relatório de utilização e facilidades bancárias.</span><span class="sxs-lookup"><span data-stu-id="b0753-243">Go to Cash and bank management > Inquiries and reports > Letters of credit or guarantee > Bank facilities and utilization report.</span></span>
2. <span data-ttu-id="b0753-244">Expanda os Registros para incluir a seção.</span><span class="sxs-lookup"><span data-stu-id="b0753-244">Expand the Records to include section.</span></span>
3. <span data-ttu-id="b0753-245">Clique em Filtro.</span><span class="sxs-lookup"><span data-stu-id="b0753-245">Click Filter.</span></span>
    * <span data-ttu-id="b0753-246">Defina o campo Critérios com a conta bancária necessária.</span><span class="sxs-lookup"><span data-stu-id="b0753-246">Define the Criteria field with the required bank account.</span></span>  
4. <span data-ttu-id="b0753-247">No campo Critérios, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="b0753-247">In the Criteria field, enter or select a value.</span></span>
5. <span data-ttu-id="b0753-248">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0753-248">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="b0753-249">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-249">Click OK.</span></span>
7. <span data-ttu-id="b0753-250">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b0753-250">Click OK.</span></span>
    * <span data-ttu-id="b0753-251">Verifique o relatório que lista as transações.</span><span class="sxs-lookup"><span data-stu-id="b0753-251">Verify the report which lists the transactions.</span></span>  
    * <span data-ttu-id="b0753-252">Verifique se o relatório lista as transações com número do documento bancário, limite de recurso, valor utilizado e valor de saldo de recurso.</span><span class="sxs-lookup"><span data-stu-id="b0753-252">Verify the report lists the transactions with Bank document number, Facility limit, utilized amount and the facility balance amount.</span></span>  
8. <span data-ttu-id="b0753-253">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b0753-253">Close the page.</span></span>

