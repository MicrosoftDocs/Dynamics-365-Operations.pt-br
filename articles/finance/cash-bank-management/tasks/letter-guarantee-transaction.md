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
ms.openlocfilehash: ff105bdefff2ea93c853d590c77391653f50a4dc
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176433"
---
# <a name="letter-of-guarantee-transaction"></a><span data-ttu-id="6682d-103">Transação da carta de garantia</span><span class="sxs-lookup"><span data-stu-id="6682d-103">Letter of guarantee transaction</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6682d-104">Este procedimento mostra o processo de Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-104">This procedure walks through the Letter of guarantee process.</span></span>



<span data-ttu-id="6682d-105">As tarefas a seguir devem ser concluídas antes de concluir este procedimento:</span><span class="sxs-lookup"><span data-stu-id="6682d-105">The following tasks must be complete before completing this procedure:</span></span>

- <span data-ttu-id="6682d-106">Configurar recursos bancários e perfis de lançamento para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-106">Set up bank facilities and posting profiles for a letter of guarantee.</span></span>

- <span data-ttu-id="6682d-107">Criar um contrato de recursos bancários para uma carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-107">Create a bank facility agreement for a letter of guarantee.</span></span>



<span data-ttu-id="6682d-108">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="6682d-108">This procedure uses the USMF demo company.</span></span>


## <a name="create-sales-order-with-letter-of-guarantee"></a><span data-ttu-id="6682d-109">Criar Ordem de venda com a Carta de garantia</span><span class="sxs-lookup"><span data-stu-id="6682d-109">Create Sales Order with Letter of Guarantee</span></span>
1. <span data-ttu-id="6682d-110">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="6682d-110">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6682d-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="6682d-111">Click New.</span></span>
3. <span data-ttu-id="6682d-112">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-112">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="6682d-113">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="6682d-113">Expand the General section.</span></span>
5. <span data-ttu-id="6682d-114">No campo Local, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-114">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="6682d-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-115">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6682d-116">No campo Depósito, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-116">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="6682d-117">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="6682d-118">No campo Tipo de documento bancário, selecione 'Carta de garantia'.</span><span class="sxs-lookup"><span data-stu-id="6682d-118">In the Bank document type field, select 'Letter of guarantee'.</span></span>
10. <span data-ttu-id="6682d-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-119">Click OK.</span></span>
11. <span data-ttu-id="6682d-120">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-120">In the Item number field, enter or select a value.</span></span>
12. <span data-ttu-id="6682d-121">No campo Preço unitário, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6682d-121">In the Unit price field, enter a number.</span></span>
13. <span data-ttu-id="6682d-122">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="6682d-122">Expand the Line details section.</span></span>
14. <span data-ttu-id="6682d-123">Clique na guia Entrega.</span><span class="sxs-lookup"><span data-stu-id="6682d-123">Click the Delivery tab.</span></span>
    * <span data-ttu-id="6682d-124">Observação: Selecione controle da data de entrega = nenhum</span><span class="sxs-lookup"><span data-stu-id="6682d-124">Note: Select Delivery date control = None</span></span>  
15. <span data-ttu-id="6682d-125">No campo Data de remessa solicitada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="6682d-125">In the Requested ship date field, enter a date.</span></span>
16. <span data-ttu-id="6682d-126">No campo Data de remessa confirmada, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="6682d-126">In the Confirmed ship date field, enter a date.</span></span>

## <a name="process-letter-of-guarantee_request"></a><span data-ttu-id="6682d-127">Processar carta de garantia_Solicitar</span><span class="sxs-lookup"><span data-stu-id="6682d-127">Process letter of guarantee_Request</span></span>
1. <span data-ttu-id="6682d-128">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6682d-128">On the Action Pane, click Manage.</span></span>
2. <span data-ttu-id="6682d-129">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-129">Click Letter of guarantee.</span></span>
3. <span data-ttu-id="6682d-130">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-130">On the Action Pane, click Letter of guarantee.</span></span>
4. <span data-ttu-id="6682d-131">Clique em Solicitar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-131">Click Request to open the drop dialog.</span></span>
5. <span data-ttu-id="6682d-132">No campo Tipo, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-132">In the Type field, enter or select a value.</span></span>
6. <span data-ttu-id="6682d-133">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-133">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="6682d-134">No campo Valor, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6682d-134">In the Value field, enter a number.</span></span>
8. <span data-ttu-id="6682d-135">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="6682d-135">In the Expiration date field, enter a date and time.</span></span>
9. <span data-ttu-id="6682d-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-136">Click OK.</span></span>
10. <span data-ttu-id="6682d-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6682d-137">Close the page.</span></span>

## <a name="process-letter-of-guarantee_submit-to-bank"></a><span data-ttu-id="6682d-138">Processar carta de garantia ao banco_Enviar ao banco</span><span class="sxs-lookup"><span data-stu-id="6682d-138">Process letter of guarantee_Submit to bank</span></span>
1. <span data-ttu-id="6682d-139">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-139">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
2. <span data-ttu-id="6682d-140">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-140">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="6682d-141">Clique em Enviar ao banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-141">Click Submit to bank to open the drop dialog.</span></span>
4. <span data-ttu-id="6682d-142">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-142">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="6682d-143">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-143">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="6682d-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-144">Click OK.</span></span>

## <a name="process-letter-of-guarantee_receive-from-bank"></a><span data-ttu-id="6682d-145">Processar carta de garantia_Receber do banco</span><span class="sxs-lookup"><span data-stu-id="6682d-145">Process letter of guarantee_Receive from bank</span></span>
1. <span data-ttu-id="6682d-146">Clique em Receber do banco para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-146">Click Receive from bank to open the drop dialog.</span></span>
2. <span data-ttu-id="6682d-147">No campo Número do banco, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6682d-147">In the Bank number field, type a value.</span></span>
    * <span data-ttu-id="6682d-148">Verifique os valores nos campos calculados Margem e Despesa.</span><span class="sxs-lookup"><span data-stu-id="6682d-148">Verify the values in the calculated Margin and Expense fields.</span></span>  
3. <span data-ttu-id="6682d-149">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-149">Click OK.</span></span>
4. <span data-ttu-id="6682d-150">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="6682d-150">Expand the Actions section.</span></span>
    * <span data-ttu-id="6682d-151">Verifique o registro 'Receber do banco'.</span><span class="sxs-lookup"><span data-stu-id="6682d-151">Verify the 'Receive from bank' record.</span></span>  
5. <span data-ttu-id="6682d-152">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="6682d-152">Click to follow the link in the Journal batch number field.</span></span>
6. <span data-ttu-id="6682d-153">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="6682d-153">Click Lines.</span></span>
    * <span data-ttu-id="6682d-154">Verifique o lançamento de entradas de diário.</span><span class="sxs-lookup"><span data-stu-id="6682d-154">Verify the posting of journal entries.</span></span>  
7. <span data-ttu-id="6682d-155">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6682d-155">Close the page.</span></span>

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a><span data-ttu-id="6682d-156">Processar carta de garantia_Conceder ao beneficiário</span><span class="sxs-lookup"><span data-stu-id="6682d-156">Process letter of guarantee_Give to beneficiary</span></span>
1. <span data-ttu-id="6682d-157">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="6682d-157">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6682d-158">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-158">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6682d-159">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6682d-159">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6682d-160">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-160">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6682d-161">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-161">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6682d-162">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-162">Click Give to beneficiary to open the drop dialog.</span></span>
7. <span data-ttu-id="6682d-163">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-163">Click OK.</span></span>
8. <span data-ttu-id="6682d-164">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-164">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="6682d-165">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-165">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6682d-166">Clique em Conceder ao beneficiário para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-166">Click Give to beneficiary to open the drop dialog.</span></span>
11. <span data-ttu-id="6682d-167">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-167">Click OK.</span></span>
12. <span data-ttu-id="6682d-168">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="6682d-168">Expand the Actions section.</span></span>
    * <span data-ttu-id="6682d-169">Valide o registro 'Conceder ao beneficiário'.</span><span class="sxs-lookup"><span data-stu-id="6682d-169">Validate the 'Give to beneficiary' record.</span></span>  

## <a name="process-letter-of-guarantee_increase-value"></a><span data-ttu-id="6682d-170">Processar carta de garantia_Aumentar valor</span><span class="sxs-lookup"><span data-stu-id="6682d-170">Process letter of guarantee_Increase value</span></span>
1. <span data-ttu-id="6682d-171">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="6682d-171">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6682d-172">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-172">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6682d-173">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6682d-173">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6682d-174">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-174">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6682d-175">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-175">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6682d-176">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-176">Click Increase value to open the drop dialog.</span></span>
7. <span data-ttu-id="6682d-177">No campo Valor a ser adicionado, insira um número.</span><span class="sxs-lookup"><span data-stu-id="6682d-177">In the Value to add field, enter a number.</span></span>
8. <span data-ttu-id="6682d-178">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-178">Click OK.</span></span>
9. <span data-ttu-id="6682d-179">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-179">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
10. <span data-ttu-id="6682d-180">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-180">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="6682d-181">Clique em Aumentar valor para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-181">Click Increase value to open the drop dialog.</span></span>
12. <span data-ttu-id="6682d-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-182">Click OK.</span></span>
13. <span data-ttu-id="6682d-183">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="6682d-183">Expand the Actions section.</span></span>
    * <span data-ttu-id="6682d-184">Verifique o registro 'Aumentar valor'.</span><span class="sxs-lookup"><span data-stu-id="6682d-184">Verify the 'Increase value' record.</span></span>  
14. <span data-ttu-id="6682d-185">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-185">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="6682d-186">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="6682d-186">Click to follow the link in the Journal batch number field.</span></span>
16. <span data-ttu-id="6682d-187">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="6682d-187">Click Lines.</span></span>
    * <span data-ttu-id="6682d-188">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="6682d-188">Verify the posted journal entries.</span></span>  

## <a name="process-letter-of-guarantee_liquidate"></a><span data-ttu-id="6682d-189">Processar carta de garantia_Liquidar</span><span class="sxs-lookup"><span data-stu-id="6682d-189">Process letter of guarantee_Liquidate</span></span>
1. <span data-ttu-id="6682d-190">Vá para Contas a receber > Ordens > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="6682d-190">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="6682d-191">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="6682d-191">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="6682d-192">No Painel de Ação, clique em Gerenciar.</span><span class="sxs-lookup"><span data-stu-id="6682d-192">On the Action Pane, click Manage.</span></span>
4. <span data-ttu-id="6682d-193">Clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-193">Click Letter of guarantee.</span></span>
5. <span data-ttu-id="6682d-194">No Painel de Ação, clique em Carta de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-194">On the Action Pane, click Letter of guarantee.</span></span>
6. <span data-ttu-id="6682d-195">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-195">Click Liquidate to open the drop dialog.</span></span>
7. <span data-ttu-id="6682d-196">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-196">Click OK.</span></span>
8. <span data-ttu-id="6682d-197">Vá para Gerenciamento de caixa e bancos > Cartas de garantia > Cartas de garantia.</span><span class="sxs-lookup"><span data-stu-id="6682d-197">Go to Cash and bank management > Letters of guarantee > Letters of guarantee.</span></span>
9. <span data-ttu-id="6682d-198">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-198">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="6682d-199">Clique em Liquidar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="6682d-199">Click Liquidate to open the drop dialog.</span></span>
11. <span data-ttu-id="6682d-200">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="6682d-200">Click OK.</span></span>
12. <span data-ttu-id="6682d-201">Expandir a seção Ações.</span><span class="sxs-lookup"><span data-stu-id="6682d-201">Expand the Actions section.</span></span>
    * <span data-ttu-id="6682d-202">Verifique o registro 'Liquidar'.</span><span class="sxs-lookup"><span data-stu-id="6682d-202">Verify the 'Liquidate' record.</span></span>  
13. <span data-ttu-id="6682d-203">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="6682d-203">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="6682d-204">Clique para seguir o link no campo Número do lote do diário.</span><span class="sxs-lookup"><span data-stu-id="6682d-204">Click to follow the link in the Journal batch number field.</span></span>
15. <span data-ttu-id="6682d-205">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="6682d-205">Click Lines.</span></span>
    * <span data-ttu-id="6682d-206">Verifique as entradas de diário lançadas.</span><span class="sxs-lookup"><span data-stu-id="6682d-206">Verify the posted journal entries.</span></span>  
16. <span data-ttu-id="6682d-207">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6682d-207">Close the page.</span></span>

