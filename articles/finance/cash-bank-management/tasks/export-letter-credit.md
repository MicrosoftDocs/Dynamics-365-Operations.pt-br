---
title: Exportar carta de crédito
description: Este procedimento apresenta o processo de exportação de uma carta de crédito.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, DefaultDashboard, SalesTableListPage, SalesCreateOrder, SalesTable, BankLCExport, SalesEditLines,  LedgerJournalTable, LedgerJournalTransCustPaym, CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b46ba174d658d27f5349762f3314ea8110490d2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976382"
---
# <a name="export-letter-of-credit"></a><span data-ttu-id="53f8e-103">Exportar carta de crédito</span><span class="sxs-lookup"><span data-stu-id="53f8e-103">Export letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="53f8e-104">Este procedimento apresenta o processo de exportação de uma carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="53f8e-104">This procedure walks through the process of the Export letter of credit.</span></span>

<span data-ttu-id="53f8e-105">Uma carta de crédito é um contrato emitido por um banco, no qual o banco garante o pagamento em nome do comprador, se as condições do contrato entre o comprador e o vendedor forem atendidas.</span><span class="sxs-lookup"><span data-stu-id="53f8e-105">A letter of credit is an agreement that is issued by a bank, in which the bank agrees to ensure payment on behalf of the buyer, if the terms of the agreement between the buyer and seller are met.</span></span>



<span data-ttu-id="53f8e-106">Execute o procedimento 'Configurar recursos bancários e perfis de lançamento' e o procedimento 'Criar um contrato de recursos bancários para carta de crédito' antes deste procedimento.</span><span class="sxs-lookup"><span data-stu-id="53f8e-106">Run the 'Set up bank facilities and posting profiles' procedure and the 'Letter of Credit_Create a bank facility agreement' procedure prior to this procedure.</span></span> <span data-ttu-id="53f8e-107">A empresa de demonstração de USMF deve ser selecionada para executar com êxito este procedimento.</span><span class="sxs-lookup"><span data-stu-id="53f8e-107">The USMF demo company must be selected in order to run this procedure successfully.</span></span>




## <a name="create-sales-order-for-export-letter-of-credit"></a><span data-ttu-id="53f8e-108">Criar Ordem de venda para exportação de carta de crédito</span><span class="sxs-lookup"><span data-stu-id="53f8e-108">Create Sales Order for Export letter of credit</span></span>
1. <span data-ttu-id="53f8e-109">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="53f8e-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="53f8e-110">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="53f8e-110">Click New.</span></span>
3. <span data-ttu-id="53f8e-111">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="53f8e-112">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-112">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="53f8e-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-113">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="53f8e-114">Expandir ou recolher a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="53f8e-114">Expand or collapse the General section.</span></span>
7. <span data-ttu-id="53f8e-115">No campo Local, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-115">In the Site field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="53f8e-116">Selecione o local no qual o item a ser emitido está estocado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-116">Select the Site where the item to be issued is stocked.</span></span>  
8. <span data-ttu-id="53f8e-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="53f8e-118">No campo Depósito, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-118">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="53f8e-119">Selecione o depósito no qual o item a ser emitido está estocado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-119">Select the Warehouse where item to be issued is stocked.</span></span>  
10. <span data-ttu-id="53f8e-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="53f8e-121">Observação: O campo Tipo de documento bancário deve ser selecionado com o valor 'Carta de crédito'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-121">Note: The Bank document type field should be selected with the value 'Letter of credit'.</span></span>  
11. <span data-ttu-id="53f8e-122">No campo Tipo de documento bancário, selecione 'Carta de crédito'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-122">In the Bank document type field, select 'Letter of credit'.</span></span>
12. <span data-ttu-id="53f8e-123">Expanda ou recolha a seção Entrega.</span><span class="sxs-lookup"><span data-stu-id="53f8e-123">Expand or collapse the Delivery section.</span></span>
    * <span data-ttu-id="53f8e-124">Selecione controle da data de entrega = nenhum.</span><span class="sxs-lookup"><span data-stu-id="53f8e-124">Select Delivery date control = None.</span></span>  
13. <span data-ttu-id="53f8e-125">No campo Data de recebimento solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-125">In the Requested receipt date field, enter a date.</span></span>
14. <span data-ttu-id="53f8e-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-126">Click OK.</span></span>
15. <span data-ttu-id="53f8e-127">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-127">In the Item number field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="53f8e-128">Selecione o item obrigatório a ser emitido/vendido.</span><span class="sxs-lookup"><span data-stu-id="53f8e-128">Select the required item to be Issued/Sold.</span></span>  
16. <span data-ttu-id="53f8e-129">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-129">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="53f8e-130">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="53f8e-131">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="53f8e-131">In the Unit price field, enter a number.</span></span>
19. <span data-ttu-id="53f8e-132">Expandir ou recolher a seção Detalhes de linha.</span><span class="sxs-lookup"><span data-stu-id="53f8e-132">Expand or collapse the Line details section.</span></span>
20. <span data-ttu-id="53f8e-133">Clique na guia Entrega.</span><span class="sxs-lookup"><span data-stu-id="53f8e-133">Click the Delivery tab.</span></span>
21. <span data-ttu-id="53f8e-134">No campo Data de remessa solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-134">In the Requested ship date field, enter a date.</span></span>
22. <span data-ttu-id="53f8e-135">No campo Data de remessa confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-135">In the Confirmed ship date field, enter a date.</span></span>
23. <span data-ttu-id="53f8e-136">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="53f8e-136">On the Action Pane, click Manage.</span></span>
24. <span data-ttu-id="53f8e-137">Clique em Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="53f8e-137">Click Letter of credit.</span></span>
25. <span data-ttu-id="53f8e-138">No campo Número do documento bancário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="53f8e-138">In the Bank document number field, type a value.</span></span>
26. <span data-ttu-id="53f8e-139">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="53f8e-139">In the Expiration date field, enter a date and time.</span></span>
27. <span data-ttu-id="53f8e-140">Expandir ou recolher a seção Detalhes bancários.</span><span class="sxs-lookup"><span data-stu-id="53f8e-140">Expand or collapse the Bank details section.</span></span>
28. <span data-ttu-id="53f8e-141">No campo Banco emissor, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-141">In the Issuing bank field, click the drop-down button to open the lookup.</span></span>
29. <span data-ttu-id="53f8e-142">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-142">In the list, click the link in the selected row.</span></span>
30. <span data-ttu-id="53f8e-143">No campo Banco avisador, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-143">In the Advising bank field, click the drop-down button to open the lookup.</span></span>
31. <span data-ttu-id="53f8e-144">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-144">In the list, find and select the desired record.</span></span>
32. <span data-ttu-id="53f8e-145">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-145">In the list, click the link in the selected row.</span></span>
33. <span data-ttu-id="53f8e-146">Clique em Buscar remessas de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="53f8e-146">Click Fetch sales order shipments.</span></span>
34. <span data-ttu-id="53f8e-147">Clique em Emitir o documento bancário.</span><span class="sxs-lookup"><span data-stu-id="53f8e-147">Click Issue bank document.</span></span>
35. <span data-ttu-id="53f8e-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="53f8e-148">Close the page.</span></span>

## <a name="post-packing-slip"></a><span data-ttu-id="53f8e-149">Lance a guia de remessa</span><span class="sxs-lookup"><span data-stu-id="53f8e-149">Post Packing slip</span></span>
1. <span data-ttu-id="53f8e-150">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="53f8e-150">On the Action Pane, click Pick and pack.</span></span>
2. <span data-ttu-id="53f8e-151">Clique em Lançar guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-151">Click Post packing slip.</span></span>
3. <span data-ttu-id="53f8e-152">Expanda e recolha a seção Parâmetros.</span><span class="sxs-lookup"><span data-stu-id="53f8e-152">Expand or collapse the Parameters section.</span></span>
4. <span data-ttu-id="53f8e-153">No campo Quantidade, selecione 'Todas'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-153">In the Quantity field, select 'All'.</span></span>
5. <span data-ttu-id="53f8e-154">Expanda ou recolha a seção Configuração.</span><span class="sxs-lookup"><span data-stu-id="53f8e-154">Expand or collapse the Setup section.</span></span>
6. <span data-ttu-id="53f8e-155">No campo Data da guia de remessa, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-155">In the Packing slip date field, enter a date.</span></span>
7. <span data-ttu-id="53f8e-156">Selecione o Número da remessa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-156">Select the Shipment number.</span></span>
8. <span data-ttu-id="53f8e-157">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-157">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="53f8e-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-158">Click OK.</span></span>
10. <span data-ttu-id="53f8e-159">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-159">Click OK.</span></span>

## <a name="post-sales-invoice"></a><span data-ttu-id="53f8e-160">Lance uma fatura de venda</span><span class="sxs-lookup"><span data-stu-id="53f8e-160">Post sales invoice</span></span>
1. <span data-ttu-id="53f8e-161">No Painel de Ação, clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="53f8e-161">On the Action Pane, click Invoice.</span></span>
2. <span data-ttu-id="53f8e-162">Clique em Fatura.</span><span class="sxs-lookup"><span data-stu-id="53f8e-162">Click Invoice.</span></span>
3. <span data-ttu-id="53f8e-163">Expanda ou recolha a seção Visão geral.</span><span class="sxs-lookup"><span data-stu-id="53f8e-163">Expand or collapse the Overview section.</span></span>
4. <span data-ttu-id="53f8e-164">Selecione o Número da remessa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-164">Select the Shipment number.</span></span>
5. <span data-ttu-id="53f8e-165">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-165">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="53f8e-166">Expanda ou recolha a seção Configuração.</span><span class="sxs-lookup"><span data-stu-id="53f8e-166">Expand or collapse the Setup section.</span></span>
7. <span data-ttu-id="53f8e-167">No campo Data da fatura, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-167">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="53f8e-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-168">Click OK.</span></span>
9. <span data-ttu-id="53f8e-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-169">Click OK.</span></span>

## <a name="shipment-document-submitted-status"></a><span data-ttu-id="53f8e-170">Status de envio do documento de remessa</span><span class="sxs-lookup"><span data-stu-id="53f8e-170">Shipment document submitted status</span></span>
1. <span data-ttu-id="53f8e-171">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="53f8e-171">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="53f8e-172">Clique em Carta de crédito.</span><span class="sxs-lookup"><span data-stu-id="53f8e-172">Click Letter of credit.</span></span>
3. <span data-ttu-id="53f8e-173">Expandir ou recolher a seção Linhas.</span><span class="sxs-lookup"><span data-stu-id="53f8e-173">Expand or collapse the Lines section.</span></span>
    * <span data-ttu-id="53f8e-174">Observação: O campo 'Documento enviado” deve ser definido como 'Sim'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-174">Note: The 'Document submitted' field should be set to 'Yes'.</span></span>  

## <a name="verify-export-letter-of-credit"></a><span data-ttu-id="53f8e-175">Verificar carta de crédito de exportação</span><span class="sxs-lookup"><span data-stu-id="53f8e-175">Verify Export letter of credit</span></span>
1. <span data-ttu-id="53f8e-176">Vá para Gerenciamento de caixa de bando > Cartas de crédito > Exportar carta de crédito e importar cobranças.</span><span class="sxs-lookup"><span data-stu-id="53f8e-176">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="53f8e-177">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-177">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="53f8e-178">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="53f8e-179">Verifique se a Carta de crédito de exportação tem o Status da remessa 'Faturado'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-179">Verify that the Export letter of credit has a Shipment status of 'Invoiced'.</span></span>  

## <a name="customer-payment"></a><span data-ttu-id="53f8e-180">Pagamento de cliente</span><span class="sxs-lookup"><span data-stu-id="53f8e-180">Customer payment</span></span>
1. <span data-ttu-id="53f8e-181">Vá para Contas a receber > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="53f8e-181">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="53f8e-182">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="53f8e-182">Click New.</span></span>
3. <span data-ttu-id="53f8e-183">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-183">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="53f8e-184">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="53f8e-184">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="53f8e-185">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-185">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="53f8e-186">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="53f8e-186">Click Lines.</span></span>
7. <span data-ttu-id="53f8e-187">No campo Data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="53f8e-187">In the Date field, enter a date.</span></span>
8. <span data-ttu-id="53f8e-188">No campo Conta, especifique os valores desejados.</span><span class="sxs-lookup"><span data-stu-id="53f8e-188">In the Account field, specify the desired values.</span></span>
9. <span data-ttu-id="53f8e-189">Clique em Liquidação.</span><span class="sxs-lookup"><span data-stu-id="53f8e-189">Click Settlement.</span></span>
10. <span data-ttu-id="53f8e-190">Marque a caixa de seleção no cabeçalho de Totais.</span><span class="sxs-lookup"><span data-stu-id="53f8e-190">Select the check box on the header of Totals.</span></span>
    * <span data-ttu-id="53f8e-191">Observação: Defina o campo Mostrar para 'Carta de crédito'.</span><span class="sxs-lookup"><span data-stu-id="53f8e-191">Note: Set the Show field to 'Letter of credit'.</span></span>  
11. <span data-ttu-id="53f8e-192">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-192">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="53f8e-193">Marque ou desmarque a caixa de seleção Marcar.</span><span class="sxs-lookup"><span data-stu-id="53f8e-193">Select or clear the Mark check box.</span></span>
13. <span data-ttu-id="53f8e-194">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="53f8e-194">Click OK.</span></span>
14. <span data-ttu-id="53f8e-195">Clique na aba Pagamento.</span><span class="sxs-lookup"><span data-stu-id="53f8e-195">Click the Payment tab.</span></span>
    * <span data-ttu-id="53f8e-196">Verifique o Número do documento bancário e os Detalhes do número de remessa</span><span class="sxs-lookup"><span data-stu-id="53f8e-196">Verify Bank document number and Shipment number details</span></span>  
15. <span data-ttu-id="53f8e-197">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="53f8e-197">Click Post.</span></span>

## <a name="verify-export-letter-of-credit-after-payment"></a><span data-ttu-id="53f8e-198">Verifique a carta de crédito de exportação após o pagamento</span><span class="sxs-lookup"><span data-stu-id="53f8e-198">Verify Export letter of credit after payment</span></span>
1. <span data-ttu-id="53f8e-199">Vá para Gerenciamento de caixa de bando > Cartas de crédito > Exportar carta de crédito e importar cobranças.</span><span class="sxs-lookup"><span data-stu-id="53f8e-199">Go to Cash and bank management > Letters of credit > Export letter of credit and import collection.</span></span>
2. <span data-ttu-id="53f8e-200">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="53f8e-200">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="53f8e-201">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="53f8e-201">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="53f8e-202">Verifique o Status da remessa = Pagamento recebido e o Valor do saldo = 0,00.</span><span class="sxs-lookup"><span data-stu-id="53f8e-202">Verify Shipment status = Payment received and balance amount = 0.00.</span></span>  

