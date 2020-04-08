---
title: Transação da carta de garantia
description: Este procedimento mostra o processo de Carta de garantia.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 05abad6898c2b97cf66abdff21b30407dacd6488
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141778"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="501c6-103">Transação da carta de garantia</span><span class="sxs-lookup"><span data-stu-id="501c6-103">Letter of guarantee transaction</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="501c6-104">Este procedimento mostra o processo de Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="501c6-105">As tarefas a seguir devem ser concluídas antes de concluir este procedimento:</span><span class="sxs-lookup"><span data-stu-id="501c6-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="501c6-106">Configurar recursos bancários e perfis de lançamento para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="501c6-107">Criar um contrato de recursos bancários para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="501c6-108">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="501c6-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="501c6-109">Criar Ordem de venda com a Carta de garantia</span><span class="sxs-lookup"><span data-stu-id="501c6-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="501c6-110">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="501c6-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="501c6-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="501c6-111">Click New.</span></span>
3. <span data-ttu-id="501c6-112">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="501c6-113">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="501c6-113">Expand the General section.</span></span>
5. <span data-ttu-id="501c6-114">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="501c6-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="501c6-116">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="501c6-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="501c6-118">No campo Tipo de documento bancário, selecione 'Carta de garantia'.</span><span class="sxs-lookup"><span data-stu-id="501c6-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="501c6-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-119">Click OK.</span></span>
11. <span data-ttu-id="501c6-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="501c6-121">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="501c6-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="501c6-122">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="501c6-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="501c6-123">Clique na guia Entrega.</span><span class="sxs-lookup"><span data-stu-id="501c6-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="501c6-124">Observação: Selecione controle da data de entrega = nenhum</span><span class="sxs-lookup"><span data-stu-id="501c6-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="501c6-125">No campo Data de remessa solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="501c6-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="501c6-126">No campo Data de remessa confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="501c6-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="501c6-127">Processar carta de garantia_Solicitar</span><span class="sxs-lookup"><span data-stu-id="501c6-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="501c6-128">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="501c6-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="501c6-129">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="501c6-130">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="501c6-131">Clique em Solicitar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="501c6-132">No campo Tipo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="501c6-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="501c6-134">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="501c6-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="501c6-135">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="501c6-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="501c6-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-136">Click OK.</span></span>
10. <span data-ttu-id="501c6-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="501c6-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="501c6-138">Processar carta de garantia ao banco_Enviar ao banco</span><span class="sxs-lookup"><span data-stu-id="501c6-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="501c6-139">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="501c6-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="501c6-141">Clique em Enviar ao banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="501c6-142">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="501c6-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="501c6-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="501c6-145">Processar carta de garantia_Receber do banco</span><span class="sxs-lookup"><span data-stu-id="501c6-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="501c6-146">Clique em Receber do banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="501c6-147">No campo Número do banco, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="501c6-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="501c6-148">Verifique os valores nos campos calculados Margem e Despesa.</span><span class="sxs-lookup"><span data-stu-id="501c6-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="501c6-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-149">Click OK.</span></span>
4. <span data-ttu-id="501c6-150">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="501c6-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="501c6-151">Verifique o registro 'Receber do banco'.</span><span class="sxs-lookup"><span data-stu-id="501c6-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="501c6-152">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="501c6-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="501c6-153">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="501c6-153">Click Lines.</span></span>
    * <span data-ttu-id="501c6-154">Verifique o lançamento de entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="501c6-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="501c6-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="501c6-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="501c6-156">Processar carta de garantia_Conceder ao beneficiário</span><span class="sxs-lookup"><span data-stu-id="501c6-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="501c6-157">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="501c6-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="501c6-158">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="501c6-159">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="501c6-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="501c6-160">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="501c6-161">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="501c6-162">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="501c6-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-163">Click OK.</span></span>
8. <span data-ttu-id="501c6-164">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="501c6-165">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="501c6-166">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="501c6-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-167">Click OK.</span></span>
12. <span data-ttu-id="501c6-168">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="501c6-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="501c6-169">Valide o registro 'Conceder ao beneficiário'.</span><span class="sxs-lookup"><span data-stu-id="501c6-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="501c6-170">Processar carta de garantia_Aumentar valor</span><span class="sxs-lookup"><span data-stu-id="501c6-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="501c6-171">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="501c6-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="501c6-172">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="501c6-173">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="501c6-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="501c6-174">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="501c6-175">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="501c6-176">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="501c6-177">No campo Valor a ser adicionado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="501c6-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="501c6-178">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-178">Click OK.</span></span>
9. <span data-ttu-id="501c6-179">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="501c6-180">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="501c6-181">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="501c6-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-182">Click OK.</span></span>
13. <span data-ttu-id="501c6-183">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="501c6-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="501c6-184">Verifique o registro 'Aumentar valor'.</span><span class="sxs-lookup"><span data-stu-id="501c6-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="501c6-185">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="501c6-186">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="501c6-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="501c6-187">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="501c6-187">Click Lines.</span></span>
    * <span data-ttu-id="501c6-188">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="501c6-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="501c6-189">Processar carta de garantia_Liquidar</span><span class="sxs-lookup"><span data-stu-id="501c6-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="501c6-190">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="501c6-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="501c6-191">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="501c6-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="501c6-192">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="501c6-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="501c6-193">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="501c6-194">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="501c6-195">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="501c6-196">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-196">Click OK.</span></span>
8. <span data-ttu-id="501c6-197">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="501c6-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="501c6-198">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="501c6-199">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="501c6-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="501c6-200">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="501c6-200">Click OK.</span></span>
12. <span data-ttu-id="501c6-201">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="501c6-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="501c6-202">Verifique o registro 'Liquidar'.</span><span class="sxs-lookup"><span data-stu-id="501c6-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="501c6-203">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="501c6-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="501c6-204">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="501c6-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="501c6-205">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="501c6-205">Click Lines.</span></span>
    * <span data-ttu-id="501c6-206">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="501c6-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="501c6-207">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="501c6-207">Close the page.</span></span>

