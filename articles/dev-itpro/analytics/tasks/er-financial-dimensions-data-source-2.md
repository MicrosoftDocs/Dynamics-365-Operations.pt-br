--- 
title: "Mapear modelos para usar dimensões financeiras como uma fonte de dados"
description: "As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER."
author: NickSelin
manager: AnnBe
ms.date: 10/14/2016
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
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 184071661f4256b0b241b8dd580c2e421e68c8a2
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---
# <a name="map-models--to-use-financial-dimensions-as-a-data-source"></a><span data-ttu-id="c907d-103">Mapear modelos para usar dimensões financeiras como uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="c907d-103">Map models  to use financial dimensions as a data source</span></span> 

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c907d-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="c907d-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="c907d-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="c907d-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="c907d-106">Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento “ER Usar dimensões financeiras como uma fonte de dados (Parte 1: Modelo de dados de design).</span><span class="sxs-lookup"><span data-stu-id="c907d-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="c907d-107">Adicionar fontes de dados necessários para criar mapeamento</span><span class="sxs-lookup"><span data-stu-id="c907d-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="c907d-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="c907d-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="c907d-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="c907d-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="c907d-110">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="c907d-110">Click Designer.</span></span>
4. <span data-ttu-id="c907d-111">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c907d-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="c907d-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c907d-112">Click New.</span></span>
6. <span data-ttu-id="c907d-113">No campo Definição, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="c907d-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="c907d-114">No campo Nome, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="c907d-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="c907d-115">No campo Descrição, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="c907d-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="c907d-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c907d-116">Click Save.</span></span>
10. <span data-ttu-id="c907d-117">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="c907d-117">Click Designer.</span></span>
11. <span data-ttu-id="c907d-118">Na árvore, selecione "Dynamics 365 for Operations\Tabela".</span><span class="sxs-lookup"><span data-stu-id="c907d-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="c907d-119">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="c907d-119">Click Add root.</span></span>
13. <span data-ttu-id="c907d-120">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="c907d-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="c907d-121">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="c907d-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="c907d-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c907d-122">Click OK.</span></span>
16. <span data-ttu-id="c907d-123">Na árvore, selecione "Detalhes de funções\dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="c907d-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="c907d-124">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="c907d-124">Click Add root.</span></span>
    * <span data-ttu-id="c907d-125">Essa fonte de dados especifica como o escopo de dimensões financeiras será definido para todos os relatórios que usa esse método como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c907d-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="c907d-126">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c907d-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="c907d-127">Selecione Sim no campo Pedir dimensões.</span><span class="sxs-lookup"><span data-stu-id="c907d-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="c907d-128">Selecione Sim para permitir que o usuário seleciona dimensões em tempo de execução na caixa de diálogo formulário.</span><span class="sxs-lookup"><span data-stu-id="c907d-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="c907d-129">Se selecionado Não, as dimensões financeiras da instância atual serão usadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="c907d-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="c907d-130">No campo de seleção Dimensões financeiras, selecione "Entidade legal".</span><span class="sxs-lookup"><span data-stu-id="c907d-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="c907d-131">Selecionar todos para permitir que o usuário seleciona dimensões de desejo para a instância atual no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c907d-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="c907d-132">Selecionar Entidade legal para permitir que o usuário seleciona dimensões para a empresa no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="c907d-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="c907d-133">Selecione a dimensão para permitir que o usuário seleciona dimensões com um único conjunto de dimensões.</span><span class="sxs-lookup"><span data-stu-id="c907d-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="c907d-134">Selecione Sim no campo Pedir conta principal.</span><span class="sxs-lookup"><span data-stu-id="c907d-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="c907d-135">Defina "Pedir para conta principal" como Sim para permitir que os usuários selecionem a conta principal como parte da lista de dimensões.</span><span class="sxs-lookup"><span data-stu-id="c907d-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="c907d-136">Se definido como Não, a conta principal não será incluída na lista de dimensões e a opção "Conta principal obrigatória" é ativada.</span><span class="sxs-lookup"><span data-stu-id="c907d-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="c907d-137">Se "Conta principal obrigatória" é definido como Sim, inclui a conta principal na lista de dimensões independentemente da seleção do usuário.</span><span class="sxs-lookup"><span data-stu-id="c907d-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="c907d-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c907d-138">Click OK.</span></span>
23. <span data-ttu-id="c907d-139">Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".</span><span class="sxs-lookup"><span data-stu-id="c907d-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="c907d-140">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="c907d-140">Click Add root.</span></span>
25. <span data-ttu-id="c907d-141">No campo Nome, digite "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="c907d-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="c907d-142">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="c907d-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="c907d-143">No campo Tabela, digite 'LedgerJournalTable'.</span><span class="sxs-lookup"><span data-stu-id="c907d-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="c907d-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c907d-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="c907d-145">Mapear elementos de modelo de dados para adicionar fontes de dados</span><span class="sxs-lookup"><span data-stu-id="c907d-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="c907d-146">Na árvore, expanda 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="c907d-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="c907d-147">Na árvore, expanda 'Diário\Transação'.</span><span class="sxs-lookup"><span data-stu-id="c907d-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="c907d-148">Na árvore, expanda 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="c907d-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="c907d-149">Na árvore, expandir "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="c907d-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="c907d-150">Na árvore, expandir "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="c907d-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="c907d-151">Na árvore, expanda "LedgerJournal\<Relações".</span><span class="sxs-lookup"><span data-stu-id="c907d-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="c907d-152">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="c907d-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="c907d-153">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Comprovante".</span><span class="sxs-lookup"><span data-stu-id="c907d-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="c907d-154">Na árvore, selecione 'Diário\Transações\Comprovante'.</span><span class="sxs-lookup"><span data-stu-id="c907d-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="c907d-155">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-155">Click Bind.</span></span>
11. <span data-ttu-id="c907d-156">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="c907d-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="c907d-157">Lembre-se que para qualquer referência às dimensões financeiras a que é definido, por exemplo, LedgerDimension, de item correspondente fonte de dados disponível (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="c907d-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="c907d-158">Esse item da fonte de dados oferece a dimensões financeiras de aquele que as dimensões definidas como a lista de registros.</span><span class="sxs-lookup"><span data-stu-id="c907d-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="c907d-159">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="c907d-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="c907d-160">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="c907d-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="c907d-161">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor".</span><span class="sxs-lookup"><span data-stu-id="c907d-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="c907d-162">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição".</span><span class="sxs-lookup"><span data-stu-id="c907d-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="c907d-163">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição\Nome".</span><span class="sxs-lookup"><span data-stu-id="c907d-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="c907d-164">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Nome'.</span><span class="sxs-lookup"><span data-stu-id="c907d-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="c907d-165">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-165">Click Bind.</span></span>
19. <span data-ttu-id="c907d-166">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Descrição".</span><span class="sxs-lookup"><span data-stu-id="c907d-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="c907d-167">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Descrição'.</span><span class="sxs-lookup"><span data-stu-id="c907d-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="c907d-168">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-168">Click Bind.</span></span>
22. <span data-ttu-id="c907d-169">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Código".</span><span class="sxs-lookup"><span data-stu-id="c907d-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="c907d-170">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Código'.</span><span class="sxs-lookup"><span data-stu-id="c907d-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="c907d-171">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-171">Click Bind.</span></span>
25. <span data-ttu-id="c907d-172">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="c907d-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="c907d-173">Na árvore, selecione 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="c907d-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="c907d-174">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-174">Click Bind.</span></span>
28. <span data-ttu-id="c907d-175">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Débito(AmountCurDebit)".</span><span class="sxs-lookup"><span data-stu-id="c907d-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="c907d-176">Na árvore, selecione 'Diário\Transações\Débito'.</span><span class="sxs-lookup"><span data-stu-id="c907d-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="c907d-177">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-177">Click Bind.</span></span>
31. <span data-ttu-id="c907d-178">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Data(TransDate)".</span><span class="sxs-lookup"><span data-stu-id="c907d-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="c907d-179">Na árvore, selecione 'Diário\Transações\Data'.</span><span class="sxs-lookup"><span data-stu-id="c907d-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="c907d-180">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-180">Click Bind.</span></span>
34. <span data-ttu-id="c907d-181">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Moeda(CurrencyCode)".</span><span class="sxs-lookup"><span data-stu-id="c907d-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="c907d-182">Na árvore, selecione 'Diário\Transações\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="c907d-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="c907d-183">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-183">Click Bind.</span></span>
37. <span data-ttu-id="c907d-184">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Crédito(AmountCurCredit)".</span><span class="sxs-lookup"><span data-stu-id="c907d-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="c907d-185">Na árvore, selecione 'Diário\Transações\Crédito'.</span><span class="sxs-lookup"><span data-stu-id="c907d-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="c907d-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-186">Click Bind.</span></span>
40. <span data-ttu-id="c907d-187">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="c907d-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="c907d-188">Na árvore, selecione 'Diário\Transações'.</span><span class="sxs-lookup"><span data-stu-id="c907d-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="c907d-189">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-189">Click Bind.</span></span>
43. <span data-ttu-id="c907d-190">Na árvore, selecione 'LedgerJournal\Número do lote do diário(JournalNum)'.</span><span class="sxs-lookup"><span data-stu-id="c907d-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="c907d-191">Na árvore, selecione 'Diário\Lote'.</span><span class="sxs-lookup"><span data-stu-id="c907d-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="c907d-192">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-192">Click Bind.</span></span>
46. <span data-ttu-id="c907d-193">Na árvore, selecione 'LedgerJournal'.</span><span class="sxs-lookup"><span data-stu-id="c907d-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="c907d-194">Na árvore, selecione 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="c907d-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="c907d-195">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-195">Click Bind.</span></span>
49. <span data-ttu-id="c907d-196">Na árvore, expanda 'Dimensões'.</span><span class="sxs-lookup"><span data-stu-id="c907d-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="c907d-197">Na árvore, expanda 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="c907d-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="c907d-198">Na árvore, expanda “dimensões \ conta principal e dimensões\Definição.</span><span class="sxs-lookup"><span data-stu-id="c907d-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="c907d-199">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome'.</span><span class="sxs-lookup"><span data-stu-id="c907d-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="c907d-200">Na árvore, selecione "Configurações de dimensões\Código".</span><span class="sxs-lookup"><span data-stu-id="c907d-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="c907d-201">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-201">Click Bind.</span></span>
55. <span data-ttu-id="c907d-202">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome\Nome da coluna de relatório'.</span><span class="sxs-lookup"><span data-stu-id="c907d-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="c907d-203">Na árvore, selecione "Configurações de dimensões\Nome".</span><span class="sxs-lookup"><span data-stu-id="c907d-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="c907d-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-204">Click Bind.</span></span>
58. <span data-ttu-id="c907d-205">Na árvore, selecione 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="c907d-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="c907d-206">Na árvore, selecione "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="c907d-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="c907d-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="c907d-207">Click Bind.</span></span>
61. <span data-ttu-id="c907d-208">Na árvore, selecione 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="c907d-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="c907d-209">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c907d-209">Click Edit.</span></span>
63. <span data-ttu-id="c907d-210">No campo expressionAsStringText, insira 'Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="c907d-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="c907d-211">Empresa.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="c907d-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="c907d-212">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c907d-212">Click Save.</span></span>
65. <span data-ttu-id="c907d-213">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c907d-213">Close the page.</span></span>
66. <span data-ttu-id="c907d-214">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c907d-214">Click Save.</span></span>
67. <span data-ttu-id="c907d-215">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c907d-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="c907d-216">Preencher a versão do modelo de rascunho</span><span class="sxs-lookup"><span data-stu-id="c907d-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="c907d-217">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c907d-217">Close the page.</span></span>
2. <span data-ttu-id="c907d-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c907d-218">Close the page.</span></span>
3. <span data-ttu-id="c907d-219">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="c907d-219">Click Change status.</span></span>
4. <span data-ttu-id="c907d-220">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="c907d-220">Click Complete.</span></span>
5. <span data-ttu-id="c907d-221">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c907d-221">Click OK.</span></span>


