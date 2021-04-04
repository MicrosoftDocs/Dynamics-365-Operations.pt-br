---
title: ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)
description: Este tópico descreve como configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER. (Parte 2)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERDataModelDesigner, ERModelMappingTable, ERModelMappingDesigner, ERExpressionDesignerFormula
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 59f65962ef8f6ae79190b6595a313831eca53830
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570159"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-2---model-mapping"></a><span data-ttu-id="29ea5-104">ER Usar dimensões financeiras como uma fonte de dados (Parte 2 - Mapeamento de modelo)</span><span class="sxs-lookup"><span data-stu-id="29ea5-104">ER Use financial dimensions as a data source (Part 2 - Model mapping)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="29ea5-105">As etapas a seguir explicam como um usuário atribuído ao administrador do sistema ou função do desenvolvedor de relatório eletrônico pode configurar um modelo de relatório eletrônico (ER) para usar dimensões financeiras como uma fonte de dados para relatórios ER.</span><span class="sxs-lookup"><span data-stu-id="29ea5-105">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) model to use financial dimensions as a data source for ER reports.</span></span> <span data-ttu-id="29ea5-106">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="29ea5-106">These steps can be performed in any company.</span></span>

<span data-ttu-id="29ea5-107">Para concluir estas etapas, primeiramente conclua as etapas no procedimento "ER Usar dimensões financeiras como fonte de dados (Parte 1: projetar modelo de dados".</span><span class="sxs-lookup"><span data-stu-id="29ea5-107">To complete these steps, you must first complete the steps in the "ER Use financial dimensions as a data source (Part 1: Design data model" procedure.</span></span>


## <a name="add-required-data-sources-to-model-mapping"></a><span data-ttu-id="29ea5-108">Adicionar fontes de dados necessários para criar mapeamento</span><span class="sxs-lookup"><span data-stu-id="29ea5-108">Add required data sources to model mapping</span></span>
1. <span data-ttu-id="29ea5-109">Vá para Administração da organização > Relatório eletrônico > Configurações.</span><span class="sxs-lookup"><span data-stu-id="29ea5-109">Go to Organization administration > Electronic reporting > Configurations.</span></span>
2. <span data-ttu-id="29ea5-110">Na árvore, selecione "Modelo de amostra de dimensão financeira".</span><span class="sxs-lookup"><span data-stu-id="29ea5-110">In the tree, select 'Financial dimensions sample model'.</span></span>
3. <span data-ttu-id="29ea5-111">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="29ea5-111">Click Designer.</span></span>
4. <span data-ttu-id="29ea5-112">Clique em Mapear modelo para fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="29ea5-112">Click Map model to datasource.</span></span>
5. <span data-ttu-id="29ea5-113">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="29ea5-113">Click New.</span></span>
6. <span data-ttu-id="29ea5-114">No campo Definição, selecione Entrada.</span><span class="sxs-lookup"><span data-stu-id="29ea5-114">In the Definition field, select Entry.</span></span>
7. <span data-ttu-id="29ea5-115">No campo Nome, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="29ea5-115">In the Name field, type 'Dimensions data mapping'.</span></span>
8. <span data-ttu-id="29ea5-116">No campo Descrição, digite "Mapeamento de dados de dimensão".</span><span class="sxs-lookup"><span data-stu-id="29ea5-116">In the Description field, type 'Dimensions data mapping'.</span></span>
9. <span data-ttu-id="29ea5-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-117">Click Save.</span></span>
10. <span data-ttu-id="29ea5-118">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="29ea5-118">Click Designer.</span></span>
11. <span data-ttu-id="29ea5-119">Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-119">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
12. <span data-ttu-id="29ea5-120">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="29ea5-120">Click Add root.</span></span>
13. <span data-ttu-id="29ea5-121">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-121">In the Name field, type 'Company'.</span></span>
14. <span data-ttu-id="29ea5-122">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-122">In the Table field, type 'CompanyInfo'.</span></span>
15. <span data-ttu-id="29ea5-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="29ea5-123">Click OK.</span></span>
16. <span data-ttu-id="29ea5-124">Na árvore, selecione "Detalhes de funções\dimensões financeiras".</span><span class="sxs-lookup"><span data-stu-id="29ea5-124">In the tree, select 'Functions\Financial dimensions details'.</span></span>
17. <span data-ttu-id="29ea5-125">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="29ea5-125">Click Add root.</span></span>
    * <span data-ttu-id="29ea5-126">Essa fonte de dados especifica como o escopo de dimensões financeiras será definido para todos os relatórios que usa esse método como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="29ea5-126">This data source specifies how the scope of financial dimensions will be defined for any report that will use this model as a data source.</span></span>  
18. <span data-ttu-id="29ea5-127">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="29ea5-127">In the Name field, type a value.</span></span>
19. <span data-ttu-id="29ea5-128">Selecione Sim no campo Pedir dimensões.</span><span class="sxs-lookup"><span data-stu-id="29ea5-128">Select Yes in the Ask for dimensions field.</span></span>
    * <span data-ttu-id="29ea5-129">Selecione Sim para permitir que o usuário seleciona dimensões em tempo de execução na caixa de diálogo formulário.</span><span class="sxs-lookup"><span data-stu-id="29ea5-129">Select Yes to allow the user to select dimensions at run-time on the User dialog form.</span></span> <span data-ttu-id="29ea5-130">Se selecionado Não, as dimensões financeiras da instância atual serão usadas por padrão.</span><span class="sxs-lookup"><span data-stu-id="29ea5-130">If set to No, all financial dimensions of the current instance will be used by default.</span></span>  
20. <span data-ttu-id="29ea5-131">No campo de seleção Dimensões financeiras, selecione "Entidade legal".</span><span class="sxs-lookup"><span data-stu-id="29ea5-131">In the Financial dimensions selection field, select 'Legal entity'.</span></span>
    * <span data-ttu-id="29ea5-132">Selecionar todos para permitir que o usuário seleciona dimensões de desejo para a instância atual no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29ea5-132">Select All to allow the user to select desire dimensions for the current  instance in the Lookup field.</span></span>  <span data-ttu-id="29ea5-133">Selecionar Entidade legal para permitir que o usuário seleciona dimensões para a empresa no campo de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="29ea5-133">Select Legal entity to allow the user to select dimensions for the company in the Lookup field.</span></span>  <span data-ttu-id="29ea5-134">Selecione a dimensão para permitir que o usuário seleciona dimensões com um único conjunto de dimensões.</span><span class="sxs-lookup"><span data-stu-id="29ea5-134">Select Dimension to allow the user to select dimensions using a single dimension set.</span></span>  
21. <span data-ttu-id="29ea5-135">Selecione Sim no campo Pedir conta principal.</span><span class="sxs-lookup"><span data-stu-id="29ea5-135">Select Yes in the Ask for main account field.</span></span>
    * <span data-ttu-id="29ea5-136">Defina "Solicitar conta principal" como Sim para permitir que usuários selecionem a contra principal como parte da lista de dimensões.</span><span class="sxs-lookup"><span data-stu-id="29ea5-136">Set 'Ask for main account' to Yes to allow users to select the main account as part of the list of dimensions.</span></span>   <span data-ttu-id="29ea5-137">Defina como Não. A contra principal não será incluída na lista de dimensões, e a opção "A conta principal é obrigatória?" será habilitada.</span><span class="sxs-lookup"><span data-stu-id="29ea5-137">If set to No, the main account will not be included to the list of dimensions and the 'Is main account mandatory' option is enabled.</span></span> <span data-ttu-id="29ea5-138">Se "A conta principal é obrigatória?" for definida como Sim, inclua a contra principal na lista de dimensões, independentemente da seleção do usuário.</span><span class="sxs-lookup"><span data-stu-id="29ea5-138">If "Is main account mandatory' is set to Yes, include the main account in the list of dimensions regardless of the user's selection.</span></span>  
22. <span data-ttu-id="29ea5-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="29ea5-139">Click OK.</span></span>
<span data-ttu-id="29ea5-140">![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping1.png)</span><span class="sxs-lookup"><span data-stu-id="29ea5-140">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping1.png)</span></span>
23. <span data-ttu-id="29ea5-141">Na árvore, selecione 'Dynamics 365 for Operations\Registros da tabela'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-141">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
24. <span data-ttu-id="29ea5-142">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="29ea5-142">Click Add root.</span></span>
25. <span data-ttu-id="29ea5-143">No campo Nome, digite "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="29ea5-143">In the Name field, type 'LedgerJournal'.</span></span>
26. <span data-ttu-id="29ea5-144">Selecione Sim no campo Pedir consulta.</span><span class="sxs-lookup"><span data-stu-id="29ea5-144">Select Yes in the Ask for query field.</span></span>
27. <span data-ttu-id="29ea5-145">No campo Tabela, digite 'LedgerJournalTable'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-145">In the Table field, type 'LedgerJournalTable'.</span></span>
28. <span data-ttu-id="29ea5-146">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="29ea5-146">Click OK.</span></span>
<span data-ttu-id="29ea5-147">![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping2.png)</span><span class="sxs-lookup"><span data-stu-id="29ea5-147">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping2.png)</span></span>

## <a name="map-data-model-elements-to-added-data-sources"></a><span data-ttu-id="29ea5-148">Mapear elementos de modelo de dados para adicionar fontes de dados</span><span class="sxs-lookup"><span data-stu-id="29ea5-148">Map data model elements to added data sources</span></span>
1. <span data-ttu-id="29ea5-149">Na árvore, expanda 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-149">In the tree, expand 'Journal'.</span></span>
2. <span data-ttu-id="29ea5-150">Na árvore, expanda 'Diário\Transação'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-150">In the tree, expand 'Journal\Transaction'.</span></span>
3. <span data-ttu-id="29ea5-151">Na árvore, expanda 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-151">In the tree, expand 'Journal\Transaction\Dimensions data'.</span></span>
4. <span data-ttu-id="29ea5-152">Na árvore, expandir "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="29ea5-152">In the tree, expand 'Dimensions setting'.</span></span>
5. <span data-ttu-id="29ea5-153">Na árvore, expandir "LedgerJournal".</span><span class="sxs-lookup"><span data-stu-id="29ea5-153">In the tree, expand 'LedgerJournal'.</span></span>
6. <span data-ttu-id="29ea5-154">Na árvore, expanda "LedgerJournal\<Relações".</span><span class="sxs-lookup"><span data-stu-id="29ea5-154">In the tree, expand 'LedgerJournal\<Relations'.</span></span>
7. <span data-ttu-id="29ea5-155">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="29ea5-155">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
8. <span data-ttu-id="29ea5-156">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Comprovante".</span><span class="sxs-lookup"><span data-stu-id="29ea5-156">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Voucher'.</span></span>
9. <span data-ttu-id="29ea5-157">Na árvore, selecione 'Diário\Transações\Comprovante'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-157">In the tree, select 'Journal\Transaction\Voucher'.</span></span>
10. <span data-ttu-id="29ea5-158">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-158">Click Bind.</span></span>
11. <span data-ttu-id="29ea5-159">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-159">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
    * <span data-ttu-id="29ea5-160">Lembre-se que para qualquer referência às dimensões financeiras a que é definido, por exemplo, LedgerDimension, de item correspondente fonte de dados disponível (LedgerDimension.Dimension).</span><span class="sxs-lookup"><span data-stu-id="29ea5-160">Note that for any reference to financial dimensions that is set to, for instance, LedgerDimension, a corresponding data source item is available (LedgerDimension.Dimension).</span></span> <span data-ttu-id="29ea5-161">Este item de fonte de dados oferece as dimensões financeiras das dimensões definidas como a lista do registro.</span><span class="sxs-lookup"><span data-stu-id="29ea5-161">This data source item offers the financial dimensions of that dimensions set as the record's list.</span></span>  
12. <span data-ttu-id="29ea5-162">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-162">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)'.</span></span>
13. <span data-ttu-id="29ea5-163">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="29ea5-163">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
14. <span data-ttu-id="29ea5-164">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor".</span><span class="sxs-lookup"><span data-stu-id="29ea5-164">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value'.</span></span>
15. <span data-ttu-id="29ea5-165">Na árvore, expanda "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição".</span><span class="sxs-lookup"><span data-stu-id="29ea5-165">In the tree, expand 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition'.</span></span>
16. <span data-ttu-id="29ea5-166">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Definição\Nome".</span><span class="sxs-lookup"><span data-stu-id="29ea5-166">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Definition\Name'.</span></span>
17. <span data-ttu-id="29ea5-167">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Nome'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-167">In the tree, select 'Journal\Transaction\Dimensions data\Name'.</span></span>
18. <span data-ttu-id="29ea5-168">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-168">Click Bind.</span></span>
19. <span data-ttu-id="29ea5-169">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Descrição".</span><span class="sxs-lookup"><span data-stu-id="29ea5-169">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Description'.</span></span>
20. <span data-ttu-id="29ea5-170">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Descrição'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-170">In the tree, select 'Journal\Transaction\Dimensions data\Description'.</span></span>
21. <span data-ttu-id="29ea5-171">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-171">Click Bind.</span></span>
22. <span data-ttu-id="29ea5-172">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões\Valor\Código".</span><span class="sxs-lookup"><span data-stu-id="29ea5-172">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions\Value\Code'.</span></span>
23. <span data-ttu-id="29ea5-173">Na árvore, selecione 'Diário\Transação\Dados de dimensões\Código'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-173">In the tree, select 'Journal\Transaction\Dimensions data\Code'.</span></span>
24. <span data-ttu-id="29ea5-174">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-174">Click Bind.</span></span>
25. <span data-ttu-id="29ea5-175">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Conta principal e dimensões".</span><span class="sxs-lookup"><span data-stu-id="29ea5-175">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Account.Dimension(LedgerDimension.Dimension)\Main account and dimensions'.</span></span>
26. <span data-ttu-id="29ea5-176">Na árvore, selecione 'Diário\Transação\Dados de dimensões'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-176">In the tree, select 'Journal\Transaction\Dimensions data'.</span></span>
27. <span data-ttu-id="29ea5-177">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-177">Click Bind.</span></span>
<span data-ttu-id="29ea5-178">![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping3.png)</span><span class="sxs-lookup"><span data-stu-id="29ea5-178">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping3.png)</span></span>
28. <span data-ttu-id="29ea5-179">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Débito(AmountCurDebit)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-179">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Debit(AmountCurDebit)'.</span></span>
29. <span data-ttu-id="29ea5-180">Na árvore, selecione 'Diário\Transações\Débito'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-180">In the tree, select 'Journal\Transaction\Debit'.</span></span>
30. <span data-ttu-id="29ea5-181">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-181">Click Bind.</span></span>
31. <span data-ttu-id="29ea5-182">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Data(TransDate)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-182">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Date(TransDate)'.</span></span>
32. <span data-ttu-id="29ea5-183">Na árvore, selecione 'Diário\Transações\Data'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-183">In the tree, select 'Journal\Transaction\Date'.</span></span>
33. <span data-ttu-id="29ea5-184">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-184">Click Bind.</span></span>
34. <span data-ttu-id="29ea5-185">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Moeda(CurrencyCode)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-185">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Currency(CurrencyCode)'.</span></span>
35. <span data-ttu-id="29ea5-186">Na árvore, selecione 'Diário\Transações\Moeda'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-186">In the tree, select 'Journal\Transaction\Currency'.</span></span>
36. <span data-ttu-id="29ea5-187">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-187">Click Bind.</span></span>
37. <span data-ttu-id="29ea5-188">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans\Crédito(AmountCurCredit)".</span><span class="sxs-lookup"><span data-stu-id="29ea5-188">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans\Credit(AmountCurCredit)'.</span></span>
38. <span data-ttu-id="29ea5-189">Na árvore, selecione 'Diário\Transações\Crédito'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-189">In the tree, select 'Journal\Transaction\Credit'.</span></span>
39. <span data-ttu-id="29ea5-190">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-190">Click Bind.</span></span>
40. <span data-ttu-id="29ea5-191">Na árvore, selecione "LedgerJournal\<Relações\LedgerJournalTrans".</span><span class="sxs-lookup"><span data-stu-id="29ea5-191">In the tree, select 'LedgerJournal\<Relations\LedgerJournalTrans'.</span></span>
41. <span data-ttu-id="29ea5-192">Na árvore, selecione 'Diário\Transações'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-192">In the tree, select 'Journal\Transaction'.</span></span>
42. <span data-ttu-id="29ea5-193">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-193">Click Bind.</span></span>
43. <span data-ttu-id="29ea5-194">Na árvore, selecione 'LedgerJournal\Número do lote do diário(JournalNum)'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-194">In the tree, select 'LedgerJournal\Journal batch number(JournalNum)'.</span></span>
44. <span data-ttu-id="29ea5-195">Na árvore, selecione 'Diário\Lote'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-195">In the tree, select 'Journal\Batch'.</span></span>
45. <span data-ttu-id="29ea5-196">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-196">Click Bind.</span></span>
46. <span data-ttu-id="29ea5-197">Na árvore, selecione 'LedgerJournal'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-197">In the tree, select 'LedgerJournal'.</span></span>
47. <span data-ttu-id="29ea5-198">Na árvore, selecione 'Diário'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-198">In the tree, select 'Journal'.</span></span>
48. <span data-ttu-id="29ea5-199">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-199">Click Bind.</span></span>
49. <span data-ttu-id="29ea5-200">Na árvore, expanda 'Dimensões'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-200">In the tree, expand 'Dimensions'.</span></span>
50. <span data-ttu-id="29ea5-201">Na árvore, expanda 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-201">In the tree, expand 'Dimensions\Main account and dimensions'.</span></span>
51. <span data-ttu-id="29ea5-202">Na árvore, expanda “dimensões \ conta principal e dimensões\Definição.</span><span class="sxs-lookup"><span data-stu-id="29ea5-202">In the tree, expand 'Dimensions\Main account and dimensions\Definition'.</span></span>
52. <span data-ttu-id="29ea5-203">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-203">In the tree, select 'Dimensions\Main account and dimensions\Definition\Name'.</span></span>
53. <span data-ttu-id="29ea5-204">Na árvore, selecione "Configurações de dimensões\Código".</span><span class="sxs-lookup"><span data-stu-id="29ea5-204">In the tree, select 'Dimensions setting\Code'.</span></span>
54. <span data-ttu-id="29ea5-205">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-205">Click Bind.</span></span>
55. <span data-ttu-id="29ea5-206">Na árvore, selecione 'Dimensões\Conta principal e dimensões\Definição\Nome\Nome da coluna de relatório'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-206">In the tree, select 'Dimensions\Main account and dimensions\Definition\Report column name'.</span></span>
56. <span data-ttu-id="29ea5-207">Na árvore, selecione "Configurações de dimensões\Nome".</span><span class="sxs-lookup"><span data-stu-id="29ea5-207">In the tree, select 'Dimensions setting\Name'.</span></span>
57. <span data-ttu-id="29ea5-208">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-208">Click Bind.</span></span>
58. <span data-ttu-id="29ea5-209">Na árvore, selecione 'Dimensões\Conta principal e dimensões'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-209">In the tree, select 'Dimensions\Main account and dimensions'.</span></span>
59. <span data-ttu-id="29ea5-210">Na árvore, selecione "Configurações de dimensões".</span><span class="sxs-lookup"><span data-stu-id="29ea5-210">In the tree, select 'Dimensions setting'.</span></span>
60. <span data-ttu-id="29ea5-211">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-211">Click Bind.</span></span>
61. <span data-ttu-id="29ea5-212">Na árvore, selecione 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="29ea5-212">In the tree, select 'Company'.</span></span>
62. <span data-ttu-id="29ea5-213">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-213">Click Edit.</span></span>
63. <span data-ttu-id="29ea5-214">No campo expressionAsStringText, insira 'Company.'find()'.'name()''.</span><span class="sxs-lookup"><span data-stu-id="29ea5-214">In the expressionAsStringText field, enter 'Company.'find()'.'name()''.</span></span>
    * <span data-ttu-id="29ea5-215">Empresa.'find()'.'name()'</span><span class="sxs-lookup"><span data-stu-id="29ea5-215">Company.'find()'.'name()'</span></span>  
64. <span data-ttu-id="29ea5-216">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-216">Click Save.</span></span>
<span data-ttu-id="29ea5-217">![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping4.png)</span><span class="sxs-lookup"><span data-stu-id="29ea5-217">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping4.png)</span></span>
65. <span data-ttu-id="29ea5-218">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29ea5-218">Close the page.</span></span>
66. <span data-ttu-id="29ea5-219">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="29ea5-219">Click Save.</span></span>
67. <span data-ttu-id="29ea5-220">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29ea5-220">Close the page.</span></span>

## <a name="complete-this-draft-models-version"></a><span data-ttu-id="29ea5-221">Conclua esta versão do modelo de rascunho</span><span class="sxs-lookup"><span data-stu-id="29ea5-221">Complete this draft model's version</span></span>
1. <span data-ttu-id="29ea5-222">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29ea5-222">Close the page.</span></span>
2. <span data-ttu-id="29ea5-223">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="29ea5-223">Close the page.</span></span>
3. <span data-ttu-id="29ea5-224">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="29ea5-224">Click Change status.</span></span>
4. <span data-ttu-id="29ea5-225">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="29ea5-225">Click Complete.</span></span>
5. <span data-ttu-id="29ea5-226">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="29ea5-226">Click OK.</span></span>
<span data-ttu-id="29ea5-227">![Página de designer de mapeamento de modelo de ER](../media/er-financial-dimensions-guides-model-mapping5.png)</span><span class="sxs-lookup"><span data-stu-id="29ea5-227">![ER model mapping designer page](../media/er-financial-dimensions-guides-model-mapping5.png)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]