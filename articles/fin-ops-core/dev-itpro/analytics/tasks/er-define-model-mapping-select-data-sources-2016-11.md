---
title: Definir mapeamentos do modelo de ER e selecionar fontes de dados para eles
description: As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46dc13416aa094f33879c017c1a1815fc791409d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185097"
---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a><span data-ttu-id="4e9ce-103">Definir mapeamentos do modelo de ER e selecionar fontes de dados para eles</span><span class="sxs-lookup"><span data-stu-id="4e9ce-103">Define ER model mappings and select data sources for them</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e9ce-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico (RE).</span><span class="sxs-lookup"><span data-stu-id="4e9ce-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can select data sources for an Electronic reporting (ER) data model.</span></span> <span data-ttu-id="4e9ce-105">As fontes de dados serão associadas a componentes individuais do modelo de dados selecionado durante o projeto e povoarão dados comerciais àquele modelo de dados durante a execução.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-105">The data sources will be bound to individual components of the selected data model at design time and populate business data to that data model at run-time.</span></span> <span data-ttu-id="4e9ce-106">Neste exemplo, você selecionará fontes de dados para um modelo de dados existentes que foi criado para a empresa de exemplo, Litware, Inc. Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "criar um novo modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-106">In this example, you will select data sources for an existing data model that has been created for sample company, Litware, Inc. To complete these steps, you must first complete the steps in the “Create a new data model” procedure.</span></span>


## <a name="open-the-electronic-reporting-configurations-tree"></a><span data-ttu-id="4e9ce-107">Abrir a árvore de configurações Relatório eletrônico</span><span class="sxs-lookup"><span data-stu-id="4e9ce-107">Open the Electronic Reporting configurations tree</span></span>
1. <span data-ttu-id="4e9ce-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="4e9ce-109">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-109">Click Reporting configurations.</span></span>

## <a name="insert-a-new-model-mapping"></a><span data-ttu-id="4e9ce-110">Inserir um novo mapeamento de modelo</span><span class="sxs-lookup"><span data-stu-id="4e9ce-110">Insert a new model mapping</span></span>
1. <span data-ttu-id="4e9ce-111">Na árvore, selecione 'Pagamentos (modelo simplificado)'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-111">In the tree, select 'Payments (simplified model)'.</span></span>
2. <span data-ttu-id="4e9ce-112">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-112">Click Designer.</span></span>
3. <span data-ttu-id="4e9ce-113">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-113">Click Map model to datasource.</span></span>
4. <span data-ttu-id="4e9ce-114">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-114">Click New.</span></span>
    * <span data-ttu-id="4e9ce-115">Isso irá criar um novo registro que mapeará o modelo de dados a fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-115">This will create a new record that will map the data model to data sources.</span></span> <span data-ttu-id="4e9ce-116">Neste exemplo, você mapeará o modelo de dados a fontes de dados para o tipo de pagamento desejado: transferência de crédito.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-116">In this example, you will map the data model to data sources for the desired payment type: credit transfer.</span></span>     <span data-ttu-id="4e9ce-117">É possível projetar mais de um mapeamento para um modelo de dados específico.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-117">It is possible to design more than one mapping for a particular data model.</span></span> <span data-ttu-id="4e9ce-118">Por exemplo, você pode criar um mapeamento para os diferentes tipos de pagamentos, como para o débito direto ou para transferências de crédito.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-118">For example, you could create a mapping for the different types of payments, such as for direct debit or for credit transfers.</span></span> <span data-ttu-id="4e9ce-119">Neste exemplo, você irá criar um mapeamento para transferências de crédito.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-119">In this example, you will create a mapping for credit transfers.</span></span>  
5. <span data-ttu-id="4e9ce-120">No campo Nome, digite 'Mapeamento CT'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-120">In the Name field, type 'CT mapping'.</span></span>
    * <span data-ttu-id="4e9ce-121">Mapeamento do CT</span><span class="sxs-lookup"><span data-stu-id="4e9ce-121">CT mapping</span></span>  
6. <span data-ttu-id="4e9ce-122">No campo Descrição, digite 'Modelo de pagamento mapeando CT'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-122">In the Description field, type 'Payment model mapping CT'.</span></span>
    * <span data-ttu-id="4e9ce-123">Modelo de pagamento mapeando CT</span><span class="sxs-lookup"><span data-stu-id="4e9ce-123">Payment model mapping CT</span></span>  
7. <span data-ttu-id="4e9ce-124">No campo Definição, digite "CustomerCreditTransferInitiation".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-124">In the Definition field, type 'CustomerCreditTransferInitiation'.</span></span>
    * <span data-ttu-id="4e9ce-125">Início da Transferência de Crédito do Cliente</span><span class="sxs-lookup"><span data-stu-id="4e9ce-125">CustomerCreditTransferInitiation</span></span>  
8. <span data-ttu-id="4e9ce-126">Resolver altera a definição.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-126">ResolveChanges the Definition.</span></span>
9. <span data-ttu-id="4e9ce-127">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-127">Click Save.</span></span>

## <a name="define-required-data-sources-for-the-current-model-mapping"></a><span data-ttu-id="4e9ce-128">Defina as fontes de dados necessárias para mapeamento de modelo atual</span><span class="sxs-lookup"><span data-stu-id="4e9ce-128">Define required data sources for the current model mapping</span></span>
1. <span data-ttu-id="4e9ce-129">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-129">Click Designer.</span></span>
2. <span data-ttu-id="4e9ce-130">Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-130">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
3. <span data-ttu-id="4e9ce-131">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-131">Click Add root.</span></span>
    * <span data-ttu-id="4e9ce-132">Insira essa fonte de dados para acessar as transações de pagamento.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-132">Enter this data source to access payment transactions.</span></span>  
4. <span data-ttu-id="4e9ce-133">No campo Nome, digite 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-133">In the Name field, type 'Transactions'.</span></span>
    * <span data-ttu-id="4e9ce-134">Transações</span><span class="sxs-lookup"><span data-stu-id="4e9ce-134">Transactions</span></span>  
5. <span data-ttu-id="4e9ce-135">No campo Rótulo, insira 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-135">In the Label field, enter 'Transactions'.</span></span>
    * <span data-ttu-id="4e9ce-136">Transações</span><span class="sxs-lookup"><span data-stu-id="4e9ce-136">Transactions</span></span>  
6. <span data-ttu-id="4e9ce-137">No campo Ajuda, insira 'Linhas do diário-razão'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-137">In the Help field, enter 'Ledger journal lines'.</span></span>
    * <span data-ttu-id="4e9ce-138">Linhas do diário-razão</span><span class="sxs-lookup"><span data-stu-id="4e9ce-138">Ledger journal lines</span></span>  
7. <span data-ttu-id="4e9ce-139">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-139">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="4e9ce-140">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-140">Select Yes.</span></span>  
8. <span data-ttu-id="4e9ce-141">No campo Tabela, digite 'LedgerJournalTrans'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-141">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="4e9ce-142">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="4e9ce-142">LedgerJournalTrans</span></span>  
9. <span data-ttu-id="4e9ce-143">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-143">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-144">Selecione a tabela LedgerJournalTrans como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-144">Select the LedgerJournalTrans table as a data source for the current data model.</span></span>  
10. <span data-ttu-id="4e9ce-145">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-145">In the tree, select 'Functions\Calculated field'.</span></span>
11. <span data-ttu-id="4e9ce-146">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-146">Click Add.</span></span>
    * <span data-ttu-id="4e9ce-147">Clique em Adicionar para adicionar um novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-147">Click Add to add a new calculated field.</span></span>  
12. <span data-ttu-id="4e9ce-148">No campo Nome, digite '$EndToEndID'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-148">In the Name field, type '$EndToEndID'.</span></span>
    * <span data-ttu-id="4e9ce-149">$EndToEndID</span><span class="sxs-lookup"><span data-stu-id="4e9ce-149">$EndToEndID</span></span>  
13. <span data-ttu-id="4e9ce-150">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-150">Click Edit formula.</span></span>
14. <span data-ttu-id="4e9ce-151">Na árvore, selecione 'Cadeia de caracteres\CONCATENATE'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-151">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="4e9ce-152">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-152">Click Add function.</span></span>
16. <span data-ttu-id="4e9ce-153">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-153">In the tree, expand 'Transactions'.</span></span>
17. <span data-ttu-id="4e9ce-154">Na árvore, selecione 'Transações\Comprovante'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-154">In the tree, select 'Transactions\Voucher'.</span></span>
18. <span data-ttu-id="4e9ce-155">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-155">Click Add data source.</span></span>
19. <span data-ttu-id="4e9ce-156">No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", ".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-156">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", '.</span></span>
    * <span data-ttu-id="4e9ce-157">Digite [ , “-“, ] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-157">Type [ , “-“, ] at the end of the formula.</span></span>  
20. <span data-ttu-id="4e9ce-158">Na árvore, selecione 'Cadeia de caracteres\TEXTO'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-158">In the tree, select 'String\TEXT'.</span></span>
21. <span data-ttu-id="4e9ce-159">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-159">Click Add function.</span></span>
22. <span data-ttu-id="4e9ce-160">Na árvore, selecione 'Transações\ID-Registro(RecId)'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-160">In the tree, select 'Transactions\Record-ID(RecId)'.</span></span>
23. <span data-ttu-id="4e9ce-161">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-161">Click Add data source.</span></span>
24. <span data-ttu-id="4e9ce-162">No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-162">In the Formula field, enter 'CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))'.</span></span>
    * <span data-ttu-id="4e9ce-163">Digite [))] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-163">Type [))] at the end of the formula.</span></span>  
25. <span data-ttu-id="4e9ce-164">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-164">Click Save.</span></span>
    * <span data-ttu-id="4e9ce-165">Verifique se nenhum erro foi descoberto na fórmula criada.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-165">Make sure that no errors have been discovered for the created formula.</span></span> <span data-ttu-id="4e9ce-166">Consulte a aba ERROS abaixo do controle do editor da fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-166">See the ERRORS tab below the formula editor control.</span></span>  
26. <span data-ttu-id="4e9ce-167">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-167">Close the page.</span></span>
27. <span data-ttu-id="4e9ce-168">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-168">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-169">Adicione o campo calculado a essa fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-169">Add the calculated field to this data source.</span></span>  
28. <span data-ttu-id="4e9ce-170">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-170">Click Add.</span></span>
    * <span data-ttu-id="4e9ce-171">Clique em Adicionar para adicionar um novo campo calculado.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-171">Click Add to add a new calculated field.</span></span>  
29. <span data-ttu-id="4e9ce-172">No campo Nome, digite '$Amount'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-172">In the Name field, type '$Amount'.</span></span>
    * <span data-ttu-id="4e9ce-173">$Amount</span><span class="sxs-lookup"><span data-stu-id="4e9ce-173">$Amount</span></span>  
30. <span data-ttu-id="4e9ce-174">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-174">Click Edit formula.</span></span>
31. <span data-ttu-id="4e9ce-175">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-175">In the tree, expand 'Transactions'.</span></span>
32. <span data-ttu-id="4e9ce-176">Na árvore, selecione 'Transações\Débito(AmountCurDebit)'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-176">In the tree, select 'Transactions\Debit(AmountCurDebit)'.</span></span>
33. <span data-ttu-id="4e9ce-177">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-177">Click Add data source.</span></span>
34. <span data-ttu-id="4e9ce-178">No campo Fórmula, insira "Transactions.AmountCurDebit - ".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-178">In the Formula field, enter 'Transactions.AmountCurDebit - '.</span></span>
    * <span data-ttu-id="4e9ce-179">Digite [ - ] no final da fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-179">Type [ - ] at the end of the formula.</span></span>  
35. <span data-ttu-id="4e9ce-180">Na árvore, selecione 'Transações\Crédito(AmountCurCredit)'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-180">In the tree, select 'Transactions\Credit(AmountCurCredit)'.</span></span>
36. <span data-ttu-id="4e9ce-181">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-181">Click Add data source.</span></span>
37. <span data-ttu-id="4e9ce-182">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-182">Click Save.</span></span>
38. <span data-ttu-id="4e9ce-183">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-183">Close the page.</span></span>
39. <span data-ttu-id="4e9ce-184">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-184">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-185">Isso irá adicionar o campo calculado $Amount à fonte de dados selecionada para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-185">This will add the $Amount calculated field to the selected data source for the current data model.</span></span>  
40. <span data-ttu-id="4e9ce-186">Na árvore, selecione "Transações\$Valor".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-186">In the tree, select 'Transactions\$Amount'.</span></span>
41. <span data-ttu-id="4e9ce-187">Na árvore, expanda 'Transações'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-187">In the tree, expand 'Transactions'.</span></span>
42. <span data-ttu-id="4e9ce-188">Na árvore, expanda ou recolha "Transações\$Valor".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-188">In the tree, expand or collapse 'Transactions\$Amount'.</span></span>
43. <span data-ttu-id="4e9ce-189">Na árvore, expanda ou recolha "Transações".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-189">In the tree, expand or collapse 'Transactions'.</span></span>
44. <span data-ttu-id="4e9ce-190">Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-190">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
45. <span data-ttu-id="4e9ce-191">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-191">Click Add root.</span></span>
    * <span data-ttu-id="4e9ce-192">Insira essa fonte de dados para acessar os detalhes da conta bancária da empresa.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-192">Enter this data source to access the company’s bank account details.</span></span>  
46. <span data-ttu-id="4e9ce-193">No campo Nome, digite 'BankAccount'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-193">In the Name field, type 'BankAccount'.</span></span>
    * <span data-ttu-id="4e9ce-194">BankAccount</span><span class="sxs-lookup"><span data-stu-id="4e9ce-194">BankAccount</span></span>  
47. <span data-ttu-id="4e9ce-195">No campo Rótulo, insira 'Conta Bancária'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-195">In the Label field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="4e9ce-196">Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="4e9ce-196">Bank Account</span></span>  
48. <span data-ttu-id="4e9ce-197">No campo Ajuda, insira 'Conta Bancária'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-197">In the Help field, enter 'Bank Account'.</span></span>
    * <span data-ttu-id="4e9ce-198">Conta Bancária</span><span class="sxs-lookup"><span data-stu-id="4e9ce-198">Bank Account</span></span>  
49. <span data-ttu-id="4e9ce-199">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-199">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="4e9ce-200">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-200">Select Yes.</span></span>  
50. <span data-ttu-id="4e9ce-201">No campo Tabela, digite 'BankAccountTable'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-201">In the Table field, type 'BankAccountTable'.</span></span>
    * <span data-ttu-id="4e9ce-202">BankAccountTable</span><span class="sxs-lookup"><span data-stu-id="4e9ce-202">BankAccountTable</span></span>  
51. <span data-ttu-id="4e9ce-203">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-203">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-204">Selecione a tabela BankAccountTable como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-204">Select the BankAccountTable table as a data source for the current data model.</span></span>  
52. <span data-ttu-id="4e9ce-205">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-205">Click Add root.</span></span>
    * <span data-ttu-id="4e9ce-206">Insira essa fonte de dados para acessar os requisitos da empresa.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-206">Enter this data source to access the company’s requisites.</span></span>  
53. <span data-ttu-id="4e9ce-207">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-207">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="4e9ce-208">Empresa</span><span class="sxs-lookup"><span data-stu-id="4e9ce-208">Company</span></span>  
54. <span data-ttu-id="4e9ce-209">No campo Rótulo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-209">In the Label field, type a value.</span></span>
    * <span data-ttu-id="4e9ce-210">Informações da empresa</span><span class="sxs-lookup"><span data-stu-id="4e9ce-210">Company information</span></span>  
55. <span data-ttu-id="4e9ce-211">No campo Ajuda, insira 'Informação da empresa'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-211">In the Help field, enter 'Company information'.</span></span>
    * <span data-ttu-id="4e9ce-212">Informações da empresa</span><span class="sxs-lookup"><span data-stu-id="4e9ce-212">Company information</span></span>  
56. <span data-ttu-id="4e9ce-213">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-213">Select Yes in the Ask for query field.</span></span>
    * <span data-ttu-id="4e9ce-214">Selecione Sim.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-214">Select Yes.</span></span>  
57. <span data-ttu-id="4e9ce-215">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-215">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="4e9ce-216">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="4e9ce-216">CompanyInfo</span></span>  
58. <span data-ttu-id="4e9ce-217">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-217">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-218">Selecione a tabela CompanyInfo como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-218">Select the CompanyInfo table as a data source for the current data model.</span></span>  
59. <span data-ttu-id="4e9ce-219">Na árvore, selecione 'Funções\Campo calculado'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-219">In the tree, select 'Functions\Calculated field'.</span></span>
60. <span data-ttu-id="4e9ce-220">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-220">Click Add root.</span></span>
    * <span data-ttu-id="4e9ce-221">Insira um campo calculado como uma nova fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-221">Insert a calculated field as a new data source.</span></span>  
61. <span data-ttu-id="4e9ce-222">No campo Nome, digite 'ProcessamentoDataHora'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-222">In the Name field, type 'ProcessingDateTime'.</span></span>
    * <span data-ttu-id="4e9ce-223">ProcessamentoDataHora</span><span class="sxs-lookup"><span data-stu-id="4e9ce-223">ProcessingDateTime</span></span>  
62. <span data-ttu-id="4e9ce-224">No campo Rótulo, insira 'Data e hora de processamento'.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-224">In the Label field, enter 'Processing date & time'.</span></span>
    * <span data-ttu-id="4e9ce-225">Data e hora de processamento</span><span class="sxs-lookup"><span data-stu-id="4e9ce-225">Processing date & time</span></span>  
63. <span data-ttu-id="4e9ce-226">Clique em Editar fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-226">Click Edit formula.</span></span>
64. <span data-ttu-id="4e9ce-227">Na árvore, selecione "Data/hora\SESSIONNOW".</span><span class="sxs-lookup"><span data-stu-id="4e9ce-227">In the tree, select 'Date/time\SESSIONNOW'.</span></span>
65. <span data-ttu-id="4e9ce-228">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-228">Click Add function.</span></span>
66. <span data-ttu-id="4e9ce-229">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-229">Click Save.</span></span>
67. <span data-ttu-id="4e9ce-230">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-230">Close the page.</span></span>
68. <span data-ttu-id="4e9ce-231">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-231">Click OK.</span></span>
    * <span data-ttu-id="4e9ce-232">Adiciona o campo calculado DataHoraProcessamento como uma fonte de dados para o modelo de dados atual.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-232">Add the ProcessingDateTime calculated field as a data source for the current data model.</span></span>  
69. <span data-ttu-id="4e9ce-233">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-233">Click Save.</span></span>
70. <span data-ttu-id="4e9ce-234">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-234">Close the page.</span></span>
71. <span data-ttu-id="4e9ce-235">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-235">Close the page.</span></span>
72. <span data-ttu-id="4e9ce-236">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e9ce-236">Close the page.</span></span>
