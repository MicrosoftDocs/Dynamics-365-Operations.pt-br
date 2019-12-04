---
title: ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)
description: As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 788564bfd7c3df146266976d8eef6621ff37ca2a
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550616"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="ff242-103">ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)</span><span class="sxs-lookup"><span data-stu-id="ff242-103">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff242-104">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="ff242-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="ff242-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="ff242-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="ff242-106">Para concluir essas etapas, você deve primeiro concluir as etapas no procedimento “ER Usar dimensões financeiras como uma fonte de dados (Parte 1: Modelo de dados de design).</span><span class="sxs-lookup"><span data-stu-id="ff242-106">To complete these steps, you must first complete the steps in the “ER Use financial dimensions as a data source (Part 1: Design data model” procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="ff242-107">Adicionar fontes de dados necessários para criar mapeamento</span><span class="sxs-lookup"><span data-stu-id="ff242-107">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="ff242-108">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="ff242-108">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="ff242-109">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="ff242-109">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="ff242-110">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ff242-110">Click Designer.</span></span>
4. <span data-ttu-id="ff242-111">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ff242-111">Click Map model to datasource.</span></span>
5. <span data-ttu-id="ff242-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ff242-112">Click New.</span></span>
6. <span data-ttu-id="ff242-113">No campo Definição, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="ff242-113">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="ff242-114">No campo Nome, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="ff242-114">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="ff242-115">No campo Descrição, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="ff242-115">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="ff242-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ff242-116">Click Save.</span></span>
10. <span data-ttu-id="ff242-117">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="ff242-117">Click Designer.</span></span>
11. <span data-ttu-id="ff242-118">Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.</span><span class="sxs-lookup"><span data-stu-id="ff242-118">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="ff242-119">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="ff242-119">Click Add root.</span></span>
13. <span data-ttu-id="ff242-120">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="ff242-120">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="ff242-121">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="ff242-121">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="ff242-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ff242-122">Click OK.</span></span>
16. <span data-ttu-id="ff242-123">Na árvore, selecione "Detalhes de funções\dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="ff242-123">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="ff242-124">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="ff242-124">Click Add root.</span></span>
    * <span data-ttu-id="ff242-125">Essa fonte de dados especifica como o escopo de dimensões financeiras será definido para todos os relatórios que usa esse método como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="ff242-125">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="ff242-126">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ff242-126">In the Name field, type a value.</span></span>
19. <span data-ttu-id="ff242-127">Selecione Sim no campo Pedir dimensões.</span><span class="sxs-lookup"><span data-stu-id="ff242-127">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="ff242-128">Selecione Sim para permitir que o usuário seleciona dimensões em tempo de execução na caixa de diálogo formulário.</span><span class="sxs-lookup"><span data-stu-id="ff242-128">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="ff242-129">Se selecionado Não, as dimensões financeiras da instância atual serão usadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="ff242-129">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="ff242-130">No campo de seleção Dimensões financeiras, selecione "Entidade legal".</span><span class="sxs-lookup"><span data-stu-id="ff242-130">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="ff242-131">Selecionar todos para permitir que o usuário seleciona dimensões de desejo para a instância atual no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff242-131">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="ff242-132">Selecionar Entidade legal para permitir que o usuário seleciona dimensões para a empresa no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="ff242-132">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="ff242-133">Selecione a dimensão para permitir que o usuário seleciona dimensões com um único conjunto de dimensões.</span><span class="sxs-lookup"><span data-stu-id="ff242-133">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="ff242-134">Selecione Sim no campo Pedir conta principal.</span><span class="sxs-lookup"><span data-stu-id="ff242-134">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="ff242-135">Defina "Pedir para conta principal" como Sim para permitir que os usuários selecionem a conta principal como parte da lista de dimensões.</span><span class="sxs-lookup"><span data-stu-id="ff242-135">Set ‘Ask for main account’ to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="ff242-136">Se definido como Não, a conta principal não será incluída na lista de dimensões e a opção "Conta principal obrigatória" é ativada.</span><span class="sxs-lookup"><span data-stu-id="ff242-136">If set to No, the main account will not be included to the list of dimensions and the ‘Is main account mandatory’ option is enabled.</span></span> <span data-ttu-id="ff242-137">Se "Conta principal obrigatória" é definido como Sim, inclui a conta principal na lista de dimensões independentemente da seleção do usuário.</span><span class="sxs-lookup"><span data-stu-id="ff242-137">If “Is main account mandatory’ is set to Yes, include the main account in the list of dimensions regardless of the user’s selection.</span></span>  
22. <span data-ttu-id="ff242-138">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ff242-138">Click OK.</span></span>
23. <span data-ttu-id="ff242-139">Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.</span><span class="sxs-lookup"><span data-stu-id="ff242-139">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="ff242-140">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="ff242-140">Click Add root.</span></span>
25. <span data-ttu-id="ff242-141">No campo Nome, digite "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="ff242-141">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="ff242-142">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="ff242-142">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="ff242-143">No campo Tabela, digite 'LedgerJournalTable'.</span><span class="sxs-lookup"><span data-stu-id="ff242-143">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="ff242-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ff242-144">Click OK.</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="ff242-145">Mapear elementos de modelo de dados para adicionar fontes de dados</span><span class="sxs-lookup"><span data-stu-id="ff242-145">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="ff242-146">Na árvore, expanda 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="ff242-146">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="ff242-147">Na árvore, expanda 'Diário\Transação'.</span><span class="sxs-lookup"><span data-stu-id="ff242-147">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="ff242-148">Na árvore, expanda 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="ff242-148">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="ff242-149">Na árvore, expandir "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="ff242-149">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="ff242-150">Na árvore, expandir "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="ff242-150">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="ff242-151">Na árvore, expanda "LedgerJournal\<Relações".</span><span class="sxs-lookup"><span data-stu-id="ff242-151">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="ff242-152">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="ff242-152">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="ff242-153">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Comprovante".</span><span class="sxs-lookup"><span data-stu-id="ff242-153">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="ff242-154">Na árvore, selecione 'Diário\Transações\Comprovante'.</span><span class="sxs-lookup"><span data-stu-id="ff242-154">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="ff242-155">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-155">Click Bind.</span></span>
11. <span data-ttu-id="ff242-156">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="ff242-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="ff242-157">Lembre-se que para qualquer referência às dimensões financeiras a que é definido, por exemplo, LedgerDimension, de item correspondente fonte de dados disponível (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="ff242-157">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="ff242-158">Esse item da fonte de dados oferece a dimensões financeiras de aquele que as dimensões definidas como a lista de registros.</span><span class="sxs-lookup"><span data-stu-id="ff242-158">This data source item offers the financial dimensions of that dimensions set as the record’s list.</span></span>  
12. <span data-ttu-id="ff242-159">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="ff242-159">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="ff242-160">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="ff242-160">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="ff242-161">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor".</span><span class="sxs-lookup"><span data-stu-id="ff242-161">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="ff242-162">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição".</span><span class="sxs-lookup"><span data-stu-id="ff242-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="ff242-163">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição\Nome".</span><span class="sxs-lookup"><span data-stu-id="ff242-163">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="ff242-164">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Nome'.</span><span class="sxs-lookup"><span data-stu-id="ff242-164">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="ff242-165">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-165">Click Bind.</span></span>
19. <span data-ttu-id="ff242-166">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Descrição".</span><span class="sxs-lookup"><span data-stu-id="ff242-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="ff242-167">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Descrição'.</span><span class="sxs-lookup"><span data-stu-id="ff242-167">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="ff242-168">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-168">Click Bind.</span></span>
22. <span data-ttu-id="ff242-169">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Código".</span><span class="sxs-lookup"><span data-stu-id="ff242-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="ff242-170">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Código'.</span><span class="sxs-lookup"><span data-stu-id="ff242-170">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="ff242-171">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-171">Click Bind.</span></span>
25. <span data-ttu-id="ff242-172">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="ff242-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="ff242-173">Na árvore, selecione 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="ff242-173">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="ff242-174">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-174">Click Bind.</span></span>
28. <span data-ttu-id="ff242-175">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Débito(AmountCurDebit)".</span><span class="sxs-lookup"><span data-stu-id="ff242-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="ff242-176">Na árvore, selecione 'Diário\Transações\Débito'.</span><span class="sxs-lookup"><span data-stu-id="ff242-176">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="ff242-177">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-177">Click Bind.</span></span>
31. <span data-ttu-id="ff242-178">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Data(TransDate)".</span><span class="sxs-lookup"><span data-stu-id="ff242-178">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="ff242-179">Na árvore, selecione 'Diário\Transações\Data'.</span><span class="sxs-lookup"><span data-stu-id="ff242-179">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="ff242-180">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-180">Click Bind.</span></span>
34. <span data-ttu-id="ff242-181">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Moeda(CurrencyCode)".</span><span class="sxs-lookup"><span data-stu-id="ff242-181">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="ff242-182">Na árvore, selecione 'Diário\Transações\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="ff242-182">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="ff242-183">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-183">Click Bind.</span></span>
37. <span data-ttu-id="ff242-184">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Crédito(AmountCurCredit)".</span><span class="sxs-lookup"><span data-stu-id="ff242-184">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="ff242-185">Na árvore, selecione 'Diário\Transações\Crédito'.</span><span class="sxs-lookup"><span data-stu-id="ff242-185">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="ff242-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-186">Click Bind.</span></span>
40. <span data-ttu-id="ff242-187">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="ff242-187">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="ff242-188">Na árvore, selecione 'Diário\Transações'.</span><span class="sxs-lookup"><span data-stu-id="ff242-188">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="ff242-189">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-189">Click Bind.</span></span>
43. <span data-ttu-id="ff242-190">Na árvore, selecione 'LedgerJournal\Número do lote do diário(JournalNum)'.</span><span class="sxs-lookup"><span data-stu-id="ff242-190">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="ff242-191">Na árvore, selecione 'Diário\Lote'.</span><span class="sxs-lookup"><span data-stu-id="ff242-191">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="ff242-192">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-192">Click Bind.</span></span>
46. <span data-ttu-id="ff242-193">Na árvore, selecione 'LedgerJournal'.</span><span class="sxs-lookup"><span data-stu-id="ff242-193">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="ff242-194">Na árvore, selecione 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="ff242-194">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="ff242-195">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-195">Click Bind.</span></span>
49. <span data-ttu-id="ff242-196">Na árvore, expanda 'Dimensões'.</span><span class="sxs-lookup"><span data-stu-id="ff242-196">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="ff242-197">Na árvore, expanda 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="ff242-197">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="ff242-198">Na árvore, expanda “dimensões \ conta principal e dimensões\Definição.</span><span class="sxs-lookup"><span data-stu-id="ff242-198">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="ff242-199">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome'.</span><span class="sxs-lookup"><span data-stu-id="ff242-199">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="ff242-200">Na árvore, selecione "Configurações de dimensões\Código".</span><span class="sxs-lookup"><span data-stu-id="ff242-200">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="ff242-201">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-201">Click Bind.</span></span>
55. <span data-ttu-id="ff242-202">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome\Nome da coluna de relatório'.</span><span class="sxs-lookup"><span data-stu-id="ff242-202">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="ff242-203">Na árvore, selecione "Configurações de dimensões\Nome".</span><span class="sxs-lookup"><span data-stu-id="ff242-203">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="ff242-204">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-204">Click Bind.</span></span>
58. <span data-ttu-id="ff242-205">Na árvore, selecione 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="ff242-205">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="ff242-206">Na árvore, selecione "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="ff242-206">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="ff242-207">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="ff242-207">Click Bind.</span></span>
61. <span data-ttu-id="ff242-208">Na árvore, selecione 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="ff242-208">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="ff242-209">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="ff242-209">Click Edit.</span></span>
63. <span data-ttu-id="ff242-210">No campo expressionAsStringText, insira 'Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="ff242-210">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="ff242-211">Empresa.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="ff242-211">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="ff242-212">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ff242-212">Click Save.</span></span>
65. <span data-ttu-id="ff242-213">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ff242-213">Close the page.</span></span>
66. <span data-ttu-id="ff242-214">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="ff242-214">Click Save.</span></span>
67. <span data-ttu-id="ff242-215">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ff242-215">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="ff242-216">Preencher a versão do modelo de rascunho</span><span class="sxs-lookup"><span data-stu-id="ff242-216">Complete this draft model’s version</span></span>
1. <span data-ttu-id="ff242-217">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ff242-217">Close the page.</span></span>
2. <span data-ttu-id="ff242-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="ff242-218">Close the page.</span></span>
3. <span data-ttu-id="ff242-219">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="ff242-219">Click Change status.</span></span>
4. <span data-ttu-id="ff242-220">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="ff242-220">Click Complete.</span></span>
5. <span data-ttu-id="ff242-221">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="ff242-221">Click OK.</span></span>
