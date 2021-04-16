---
title: Transação da carta de garantia
description: Este procedimento mostra o processo de Carta de garantia.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 089515287fc5706983b10614f69b4b1cd90178c5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834707"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="117c1-103">Transação da carta de garantia</span><span class="sxs-lookup"><span data-stu-id="117c1-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="117c1-104">Este procedimento mostra o processo de Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="117c1-105">As tarefas a seguir devem ser concluídas antes de concluir este procedimento:</span><span class="sxs-lookup"><span data-stu-id="117c1-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="117c1-106">Configurar recursos bancários e perfis de lançamento para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="117c1-107">Criar um contrato de recursos bancários para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="117c1-108">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="117c1-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="117c1-109">Criar Ordem de venda com a Carta de garantia</span><span class="sxs-lookup"><span data-stu-id="117c1-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="117c1-110">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="117c1-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="117c1-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="117c1-111">Click New.</span></span>
3. <span data-ttu-id="117c1-112">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="117c1-113">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="117c1-113">Expand the General section.</span></span>
5. <span data-ttu-id="117c1-114">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="117c1-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="117c1-116">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="117c1-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="117c1-118">No campo Tipo de documento bancário, selecione 'Carta de garantia'.</span><span class="sxs-lookup"><span data-stu-id="117c1-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="117c1-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-119">Click OK.</span></span>
11. <span data-ttu-id="117c1-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="117c1-121">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="117c1-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="117c1-122">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="117c1-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="117c1-123">Clique na guia Entrega.</span><span class="sxs-lookup"><span data-stu-id="117c1-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="117c1-124">Observação: Selecione controle da data de entrega = nenhum</span><span class="sxs-lookup"><span data-stu-id="117c1-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="117c1-125">No campo Data de remessa solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="117c1-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="117c1-126">No campo Data de remessa confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="117c1-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="117c1-127">Processar carta de garantia_Solicitar</span><span class="sxs-lookup"><span data-stu-id="117c1-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="117c1-128">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="117c1-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="117c1-129">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="117c1-130">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="117c1-131">Clique em Solicitar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="117c1-132">No campo Tipo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="117c1-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="117c1-134">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="117c1-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="117c1-135">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="117c1-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="117c1-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-136">Click OK.</span></span>
10. <span data-ttu-id="117c1-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="117c1-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="117c1-138">Processar carta de garantia ao banco_Enviar ao banco</span><span class="sxs-lookup"><span data-stu-id="117c1-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="117c1-139">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="117c1-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="117c1-141">Clique em Enviar ao banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="117c1-142">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="117c1-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="117c1-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="117c1-145">Processar carta de garantia_Receber do banco</span><span class="sxs-lookup"><span data-stu-id="117c1-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="117c1-146">Clique em Receber do banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="117c1-147">No campo Número do banco, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="117c1-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="117c1-148">Verifique os valores nos campos calculados Margem e Despesa.</span><span class="sxs-lookup"><span data-stu-id="117c1-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="117c1-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-149">Click OK.</span></span>
4. <span data-ttu-id="117c1-150">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="117c1-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="117c1-151">Verifique o registro 'Receber do banco'.</span><span class="sxs-lookup"><span data-stu-id="117c1-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="117c1-152">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="117c1-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="117c1-153">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="117c1-153">Click Lines.</span></span>
    * <span data-ttu-id="117c1-154">Verifique o lançamento de entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="117c1-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="117c1-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="117c1-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="117c1-156">Processar carta de garantia_Conceder ao beneficiário</span><span class="sxs-lookup"><span data-stu-id="117c1-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="117c1-157">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="117c1-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="117c1-158">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="117c1-159">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="117c1-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="117c1-160">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="117c1-161">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="117c1-162">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="117c1-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-163">Click OK.</span></span>
8. <span data-ttu-id="117c1-164">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="117c1-165">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="117c1-166">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="117c1-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-167">Click OK.</span></span>
12. <span data-ttu-id="117c1-168">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="117c1-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="117c1-169">Valide o registro 'Conceder ao beneficiário'.</span><span class="sxs-lookup"><span data-stu-id="117c1-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="117c1-170">Processar carta de garantia_Aumentar valor</span><span class="sxs-lookup"><span data-stu-id="117c1-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="117c1-171">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="117c1-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="117c1-172">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="117c1-173">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="117c1-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="117c1-174">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="117c1-175">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="117c1-176">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="117c1-177">No campo Valor a ser adicionado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="117c1-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="117c1-178">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-178">Click OK.</span></span>
9. <span data-ttu-id="117c1-179">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="117c1-180">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="117c1-181">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="117c1-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-182">Click OK.</span></span>
13. <span data-ttu-id="117c1-183">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="117c1-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="117c1-184">Verifique o registro 'Aumentar valor'.</span><span class="sxs-lookup"><span data-stu-id="117c1-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="117c1-185">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="117c1-186">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="117c1-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="117c1-187">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="117c1-187">Click Lines.</span></span>
    * <span data-ttu-id="117c1-188">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="117c1-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="117c1-189">Processar carta de garantia_Liquidar</span><span class="sxs-lookup"><span data-stu-id="117c1-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="117c1-190">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="117c1-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="117c1-191">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="117c1-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="117c1-192">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="117c1-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="117c1-193">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="117c1-194">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="117c1-195">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="117c1-196">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-196">Click OK.</span></span>
8. <span data-ttu-id="117c1-197">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="117c1-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="117c1-198">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="117c1-199">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="117c1-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="117c1-200">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="117c1-200">Click OK.</span></span>
12. <span data-ttu-id="117c1-201">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="117c1-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="117c1-202">Verifique o registro 'Liquidar'.</span><span class="sxs-lookup"><span data-stu-id="117c1-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="117c1-203">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="117c1-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="117c1-204">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="117c1-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="117c1-205">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="117c1-205">Click Lines.</span></span>
    * <span data-ttu-id="117c1-206">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="117c1-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="117c1-207">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="117c1-207">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]