--- 
title: "Definir o mapeamento de modelo e selecionar fontes de dados para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 512e24b5d0e20f00890e2a9abfe45b660a913913
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="define-model-mapping-and-select-data-sources-for-electronic-reporting-er"></a><span data-ttu-id="b8db6-103">Definir o mapeamento de modelo e selecionar fontes de dados para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="b8db6-103">Define model mapping and select data sources for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8db6-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="b8db6-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="b8db6-105">As fontes de dados serão associadas a componentes individuais do modelo de dados selecionado durante o projeto e povoarão dados comerciais àquele modelo de dados durante a execução.</span><span class="sxs-lookup"><span data-stu-id="b8db6-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="b8db6-106">Neste exemplo, você selecionará fontes de dados para um modelo de dados existentes que foi criado para a empresa de exemplo, Litware, Inc. Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "criar um novo modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="b8db6-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="b8db6-107">Abrir a árvore de configurações Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="b8db6-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="b8db6-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="b8db6-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="b8db6-109">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="b8db6-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="b8db6-110">Inserir um novo mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="b8db6-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="b8db6-111">Na árvore, selecione 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="b8db6-112">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="b8db6-112">Click Designer.</span></span>
3. <span data-ttu-id="b8db6-113">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="b8db6-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b8db6-114">Click New.</span></span>
    * <span data-ttu-id="b8db6-115">Isso irá criar um novo registro que mapeará o modelo de dados a fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="b8db6-116">Neste exemplo, você mapeará o modelo de dados a fontes de dados para o tipo de pagamento desejado: transferência de crédito.</span><span class="sxs-lookup"><span data-stu-id="b8db6-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="b8db6-117">É possível projetar mais de um mapeamento para um modelo de dados específico.</span><span class="sxs-lookup"><span data-stu-id="b8db6-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="b8db6-118">Por exemplo, você pode criar um mapeamento para os diferentes tipos de pagamentos, como para o débito direto ou para transferências de crédito.</span><span class="sxs-lookup"><span data-stu-id="b8db6-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="b8db6-119">Neste exemplo, você irá criar um mapeamento para transferências de crédito.</span><span class="sxs-lookup"><span data-stu-id="b8db6-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="b8db6-120">No campo Nome, digite 'Mapeamento CT'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="b8db6-121">Mapeamento do CT</span><span class="sxs-lookup"><span data-stu-id="b8db6-121">CT mapping</span></span>  
6. <span data-ttu-id="b8db6-122">No campo Descrição, digite 'Modelo de pagamento mapeando CT'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="b8db6-123">Modelo de pagamento mapeando CT</span><span class="sxs-lookup"><span data-stu-id="b8db6-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="b8db6-124">No campo Definição, digite "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="b8db6-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="b8db6-125">Início da Transferência de Crédito do Cliente</span><span class="sxs-lookup"><span data-stu-id="b8db6-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="b8db6-126">Resolver altera a definição.</span><span class="sxs-lookup"><span data-stu-id="b8db6-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="b8db6-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="b8db6-128">Defina as fontes de dados necessárias para mapeamento de modelo atual</span><span class="sxs-lookup"><span data-stu-id="b8db6-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="b8db6-129">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="b8db6-129">Click Designer.</span></span>
2. <span data-ttu-id="b8db6-130">Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".</span><span class="sxs-lookup"><span data-stu-id="b8db6-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="b8db6-131">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="b8db6-131">Click Add root.</span></span>
    * <span data-ttu-id="b8db6-132">Insira essa fonte de dados para acessar as transações de pagamento.</span><span class="sxs-lookup"><span data-stu-id="b8db6-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="b8db6-133">No campo Nome, digite 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="b8db6-134">Transações</span><span class="sxs-lookup"><span data-stu-id="b8db6-134">Transactions</span></span>  
5. <span data-ttu-id="b8db6-135">No campo Rótulo, insira 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="b8db6-136">Transações</span><span class="sxs-lookup"><span data-stu-id="b8db6-136">Transactions</span></span>  
6. <span data-ttu-id="b8db6-137">No campo Ajuda, insira 'Linhas do diário-razão'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="b8db6-138">Linhas do diário-razão</span><span class="sxs-lookup"><span data-stu-id="b8db6-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="b8db6-139">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="b8db6-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b8db6-140">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="b8db6-140">Select Yes.</span></span>  
8. <span data-ttu-id="b8db6-141">No campo Tabela, digite 'LedgerJournalTrans'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="b8db6-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="b8db6-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="b8db6-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-143">Click OK.</span></span>
    * <span data-ttu-id="b8db6-144">Selecione a tabela LedgerJournalTrans como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b8db6-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="b8db6-145">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="b8db6-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-146">Click Add.</span></span>
    * <span data-ttu-id="b8db6-147">Clique em Adicionar para adicionar um novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="b8db6-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="b8db6-148">No campo Nome, digite '$EndToEndID'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="b8db6-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="b8db6-149">$EndToEndID</span></span>  
13. <span data-ttu-id="b8db6-150">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-150">Click Edit formula.</span></span>
14. <span data-ttu-id="b8db6-151">Na árvore, selecione 'Cadeia de caracteres\CONCATENATE'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="b8db6-152">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="b8db6-152">Click Add function.</span></span>
16. <span data-ttu-id="b8db6-153">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="b8db6-154">Na árvore, selecione 'Transações\Comprovante'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="b8db6-155">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-155">Click Add data source.</span></span>
19. <span data-ttu-id="b8db6-156">No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", ".</span><span class="sxs-lookup"><span data-stu-id="b8db6-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="b8db6-157">Digite [ , “-“, ] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="b8db6-158">Na árvore, selecione 'Cadeia de caracteres\TEXTO'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="b8db6-159">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="b8db6-159">Click Add function.</span></span>
22. <span data-ttu-id="b8db6-160">Na árvore, selecione 'Transações\ID-Registro(RecId)'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="b8db6-161">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-161">Click Add data source.</span></span>
24. <span data-ttu-id="b8db6-162">No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".</span><span class="sxs-lookup"><span data-stu-id="b8db6-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="b8db6-163">Digite [))] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="b8db6-164">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-164">Click Save.</span></span>
    * <span data-ttu-id="b8db6-165">Verifique se nenhum erro foi descoberto na fórmula criada.</span><span class="sxs-lookup"><span data-stu-id="b8db6-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="b8db6-166">Consulte a aba ERROS abaixo do controle do editor da fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="b8db6-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-167">Close the page.</span></span>
27. <span data-ttu-id="b8db6-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-168">Click OK.</span></span>
    * <span data-ttu-id="b8db6-169">Adicione o campo calculado a essa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="b8db6-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-170">Click Add.</span></span>
    * <span data-ttu-id="b8db6-171">Clique em Adicionar para adicionar um novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="b8db6-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="b8db6-172">No campo Nome, digite '$Amount'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="b8db6-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="b8db6-173">$Amount</span></span>  
30. <span data-ttu-id="b8db6-174">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-174">Click Edit formula.</span></span>
31. <span data-ttu-id="b8db6-175">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="b8db6-176">Na árvore, selecione 'Transações\Débito(AmountCurDebit)'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="b8db6-177">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-177">Click Add data source.</span></span>
34. <span data-ttu-id="b8db6-178">No campo Fórmula, insira "Transactions.AmountCurDebit - ".</span><span class="sxs-lookup"><span data-stu-id="b8db6-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="b8db6-179">Digite [ - ] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="b8db6-180">Na árvore, selecione 'Transações\Crédito(AmountCurCredit)'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="b8db6-181">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-181">Click Add data source.</span></span>
37. <span data-ttu-id="b8db6-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-182">Click Save.</span></span>
38. <span data-ttu-id="b8db6-183">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-183">Close the page.</span></span>
39. <span data-ttu-id="b8db6-184">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-184">Click OK.</span></span>
    * <span data-ttu-id="b8db6-185">Isso irá adicionar o campo calculado $Amount à fonte de dados selecionada para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b8db6-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="b8db6-186">Na árvore, selecione "Transações\$Valor".</span><span class="sxs-lookup"><span data-stu-id="b8db6-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="b8db6-187">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="b8db6-188">Na árvore, expanda ou recolha "Transações\$Valor".</span><span class="sxs-lookup"><span data-stu-id="b8db6-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="b8db6-189">Na árvore, expanda ou recolha "Transações".</span><span class="sxs-lookup"><span data-stu-id="b8db6-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="b8db6-190">Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".</span><span class="sxs-lookup"><span data-stu-id="b8db6-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="b8db6-191">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="b8db6-191">Click Add root.</span></span>
    * <span data-ttu-id="b8db6-192">Insira essa fonte de dados para acessar os detalhes da conta bancária da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8db6-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="b8db6-193">No campo Nome, digite 'BankAccount'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="b8db6-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="b8db6-194">BankAccount</span></span>  
47. <span data-ttu-id="b8db6-195">No campo Rótulo, insira 'Conta Bancária'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="b8db6-196">Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="b8db6-196">Bank Account</span></span>  
48. <span data-ttu-id="b8db6-197">No campo Ajuda, insira 'Conta Bancária'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="b8db6-198">Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="b8db6-198">Bank Account</span></span>  
49. <span data-ttu-id="b8db6-199">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="b8db6-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b8db6-200">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="b8db6-200">Select Yes.</span></span>  
50. <span data-ttu-id="b8db6-201">No campo Tabela, digite 'BankAccountTable'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="b8db6-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="b8db6-202">BankAccountTable</span></span>  
51. <span data-ttu-id="b8db6-203">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-203">Click OK.</span></span>
    * <span data-ttu-id="b8db6-204">Selecione a tabela BankAccountTable como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b8db6-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="b8db6-205">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="b8db6-205">Click Add root.</span></span>
    * <span data-ttu-id="b8db6-206">Insira essa fonte de dados para acessar os requisitos da empresa.</span><span class="sxs-lookup"><span data-stu-id="b8db6-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="b8db6-207">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="b8db6-208">Empresa</span><span class="sxs-lookup"><span data-stu-id="b8db6-208">Company</span></span>  
54. <span data-ttu-id="b8db6-209">No campo Rótulo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8db6-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="b8db6-210">Informações da empresa</span><span class="sxs-lookup"><span data-stu-id="b8db6-210">Company information</span></span>  
55. <span data-ttu-id="b8db6-211">No campo Ajuda, insira 'Informação da empresa'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="b8db6-212">Informações da empresa</span><span class="sxs-lookup"><span data-stu-id="b8db6-212">Company information</span></span>  
56. <span data-ttu-id="b8db6-213">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="b8db6-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="b8db6-214">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="b8db6-214">Select Yes.</span></span>  
57. <span data-ttu-id="b8db6-215">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="b8db6-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="b8db6-216">CompanyInfo</span></span>  
58. <span data-ttu-id="b8db6-217">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-217">Click OK.</span></span>
    * <span data-ttu-id="b8db6-218">Selecione a tabela CompanyInfo como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b8db6-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="b8db6-219">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="b8db6-220">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="b8db6-220">Click Add root.</span></span>
    * <span data-ttu-id="b8db6-221">Insira um campo calculado como uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b8db6-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="b8db6-222">No campo Nome, digite 'ProcessamentoDataHora'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="b8db6-223">ProcessamentoDataHora</span><span class="sxs-lookup"><span data-stu-id="b8db6-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="b8db6-224">No campo Rótulo, insira 'Data e hora de processamento'.</span><span class="sxs-lookup"><span data-stu-id="b8db6-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="b8db6-225">Data e hora de processamento</span><span class="sxs-lookup"><span data-stu-id="b8db6-225">Processing date & time</span></span>  
63. <span data-ttu-id="b8db6-226">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="b8db6-226">Click Edit formula.</span></span>
64. <span data-ttu-id="b8db6-227">Na árvore, selecione "Data/hora\SESSIONNOW".</span><span class="sxs-lookup"><span data-stu-id="b8db6-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="b8db6-228">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="b8db6-228">Click Add function.</span></span>
66. <span data-ttu-id="b8db6-229">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-229">Click Save.</span></span>
67. <span data-ttu-id="b8db6-230">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-230">Close the page.</span></span>
68. <span data-ttu-id="b8db6-231">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8db6-231">Click OK.</span></span>
    * <span data-ttu-id="b8db6-232">Adiciona o campo calculado DataHoraProcessamento como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="b8db6-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="b8db6-233">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b8db6-233">Click Save.</span></span>
70. <span data-ttu-id="b8db6-234">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-234">Close the page.</span></span>
71. <span data-ttu-id="b8db6-235">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-235">Close the page.</span></span>
72. <span data-ttu-id="b8db6-236">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b8db6-236">Close the page.</span></span>


