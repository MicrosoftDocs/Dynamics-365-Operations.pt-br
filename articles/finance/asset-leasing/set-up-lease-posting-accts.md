---
title: Configurar contas de lançamento de arrendamento
description: Este tópico lista as contas de lançamento necessárias Transações de arrendamento de ativo e explica como definir contas de lançamento na página Parâmetros de lançamento de arrendamento.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 26e046b627d71721f4a4d7b6a60171a482e3e357
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992780"
---
# <a name="set-up-lease-posting-accounts"></a><span data-ttu-id="f21d9-103">Configurar contas de lançamento de arrendamento</span><span class="sxs-lookup"><span data-stu-id="f21d9-103">Set up lease posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f21d9-104">Este tópico lista as contas de lançamento necessárias Transações de arrendamento de ativo e explica como definir contas de lançamento na página **Parâmetros de lançamento de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-104">This topic lists the posting accounts that are required for Asset leasing transactions and explains how to define posting accounts on the **Lease posting parameters** page.</span></span>

<span data-ttu-id="f21d9-105">Para obedecer ao Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e ao Padrão Internacional de Relatórios Financeiros 16 (IFRS 16), talvez você precise criar contas no seu plano de contas.</span><span class="sxs-lookup"><span data-stu-id="f21d9-105">To comply with Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16), you might have to create accounts in your chart of accounts.</span></span> <span data-ttu-id="f21d9-106">No entanto, as contas que você cria para atender aos padrões ASC e IFRS não são contas de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="f21d9-106">However, any accounts that you create to comply with ASC and IFRS standards aren't fixed asset accounts.</span></span> <span data-ttu-id="f21d9-107">Sob o ASC 842, um ativo de direito de uso (DDU) é registrado para arrendamentos mercantis e operacionais.</span><span class="sxs-lookup"><span data-stu-id="f21d9-107">Under ASC 842, a right-of-use (ROU) asset is recorded for both finance and operating leases.</span></span> <span data-ttu-id="f21d9-108">Esses arrendamentos são separados dos ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="f21d9-108">These leases are separate from fixed assets.</span></span> <span data-ttu-id="f21d9-109">(Ainda é possível manter um ativo DDU usando Ativos fixos).</span><span class="sxs-lookup"><span data-stu-id="f21d9-109">(You can still maintain an ROU asset by using Fixed assets.)</span></span>

<span data-ttu-id="f21d9-110">Para obter mais informações sobre como criar estruturas de conta, consulte [Criar estruturas de conta](../general-ledger/tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="f21d9-110">For information about how to create account structures, see [Create account structures](../general-ledger/tasks/create-account-structures.md).</span></span> <span data-ttu-id="f21d9-111">Para obter mais informações sobre como criar uma conta principal, consulte [Criar uma conta principal](../general-ledger/tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="f21d9-111">For information about how to create a main account, see [Create a main account](../general-ledger/tasks/create-main-account.md).</span></span>

<span data-ttu-id="f21d9-112">A tabela a seguir mostra exemplos de contas que devem ser criadas para transações de ativos arrendados, caso ainda não tenham sido criadas.</span><span class="sxs-lookup"><span data-stu-id="f21d9-112">The following table shows examples of accounts that you must create for leased asset transactions, if they haven't already been created.</span></span> <span data-ttu-id="f21d9-113">Sob o IFRS 16, as relações de arrendamento operacional ainda são usadas para arrendamentos de baixo valor e de curto prazo.</span><span class="sxs-lookup"><span data-stu-id="f21d9-113">Under IFRS 16, the operating lease relationships are still used for low-value and short-term leases.</span></span>

| <span data-ttu-id="f21d9-114">Nº de conta contábil</span><span class="sxs-lookup"><span data-stu-id="f21d9-114">Ledger account number</span></span> | <span data-ttu-id="f21d9-115">Tipo de conta</span><span class="sxs-lookup"><span data-stu-id="f21d9-115">Account type</span></span>  | <span data-ttu-id="f21d9-116">Nome da conta</span><span class="sxs-lookup"><span data-stu-id="f21d9-116">Account name</span></span>                                          |
|-----------------------|---------------|-------------------------------------------------------|
| <span data-ttu-id="f21d9-117">180150</span><span class="sxs-lookup"><span data-stu-id="f21d9-117">180150</span></span>                | <span data-ttu-id="f21d9-118">Ativo</span><span class="sxs-lookup"><span data-stu-id="f21d9-118">Asset</span></span>         | <span data-ttu-id="f21d9-119">Ativo DDU de veículo</span><span class="sxs-lookup"><span data-stu-id="f21d9-119">Vehicle ROU asset</span></span>                                     |
| <span data-ttu-id="f21d9-120">180160</span><span class="sxs-lookup"><span data-stu-id="f21d9-120">180160</span></span>                | <span data-ttu-id="f21d9-121">Ativo</span><span class="sxs-lookup"><span data-stu-id="f21d9-121">Asset</span></span>         | <span data-ttu-id="f21d9-122">Ativo DDU de imóvel</span><span class="sxs-lookup"><span data-stu-id="f21d9-122">Building ROU asset</span></span>                                    |
| <span data-ttu-id="f21d9-123">180250</span><span class="sxs-lookup"><span data-stu-id="f21d9-123">180250</span></span>                | <span data-ttu-id="f21d9-124">Ativo</span><span class="sxs-lookup"><span data-stu-id="f21d9-124">Asset</span></span>         | <span data-ttu-id="f21d9-125">Depreciação acumulada - veículos</span><span class="sxs-lookup"><span data-stu-id="f21d9-125">Accumulated depreciation - vehicles</span></span>                   |
| <span data-ttu-id="f21d9-126">180260</span><span class="sxs-lookup"><span data-stu-id="f21d9-126">180260</span></span>                | <span data-ttu-id="f21d9-127">Ativo</span><span class="sxs-lookup"><span data-stu-id="f21d9-127">Asset</span></span>         | <span data-ttu-id="f21d9-128">Depreciação acumulada - imóvel</span><span class="sxs-lookup"><span data-stu-id="f21d9-128">Accumulated depreciation - buildings</span></span>                  |
| <span data-ttu-id="f21d9-129">222300</span><span class="sxs-lookup"><span data-stu-id="f21d9-129">222300</span></span>                | <span data-ttu-id="f21d9-130">Passivo</span><span class="sxs-lookup"><span data-stu-id="f21d9-130">Liability</span></span>     | <span data-ttu-id="f21d9-131">Obrigações financeiras de curto prazo - arrendamentos mercantis</span><span class="sxs-lookup"><span data-stu-id="f21d9-131">Short-term obligation - finance leases</span></span>                |
| <span data-ttu-id="f21d9-132">222310</span><span class="sxs-lookup"><span data-stu-id="f21d9-132">222310</span></span>                | <span data-ttu-id="f21d9-133">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-133">Balance sheet</span></span> | <span data-ttu-id="f21d9-134">Obrigação de curto prazo - Arrendamentos operacionais</span><span class="sxs-lookup"><span data-stu-id="f21d9-134">Short-term obligation - Operating leases</span></span>              |
| <span data-ttu-id="f21d9-135">250200</span><span class="sxs-lookup"><span data-stu-id="f21d9-135">250200</span></span>                | <span data-ttu-id="f21d9-136">Passivo</span><span class="sxs-lookup"><span data-stu-id="f21d9-136">Liability</span></span>     | <span data-ttu-id="f21d9-137">Notas a Pagar</span><span class="sxs-lookup"><span data-stu-id="f21d9-137">Notes payable</span></span>                                         |
| <span data-ttu-id="f21d9-138">250601</span><span class="sxs-lookup"><span data-stu-id="f21d9-138">250601</span></span>                | <span data-ttu-id="f21d9-139">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-139">Balance sheet</span></span> | <span data-ttu-id="f21d9-140">Obrigação de longo prazo - arrendamentos mercantis</span><span class="sxs-lookup"><span data-stu-id="f21d9-140">Long-term obligation - finance leases</span></span>                 |
| <span data-ttu-id="f21d9-141">250602</span><span class="sxs-lookup"><span data-stu-id="f21d9-141">250602</span></span>                | <span data-ttu-id="f21d9-142">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-142">Balance sheet</span></span> | <span data-ttu-id="f21d9-143">Obrigação de longo prazo - arrendamentos operacionais</span><span class="sxs-lookup"><span data-stu-id="f21d9-143">Long-term obligation - operating leases</span></span>               |
| <span data-ttu-id="f21d9-144">250606</span><span class="sxs-lookup"><span data-stu-id="f21d9-144">250606</span></span>                | <span data-ttu-id="f21d9-145">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-145">Balance sheet</span></span> | <span data-ttu-id="f21d9-146">Arrendamento diferido</span><span class="sxs-lookup"><span data-stu-id="f21d9-146">Deferred rent</span></span>                                         |
| <span data-ttu-id="f21d9-147">300160</span><span class="sxs-lookup"><span data-stu-id="f21d9-147">300160</span></span>                | <span data-ttu-id="f21d9-148">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-148">Balance sheet</span></span> | <span data-ttu-id="f21d9-149">Lucros Retidos</span><span class="sxs-lookup"><span data-stu-id="f21d9-149">Retained earnings</span></span>                                     |
| <span data-ttu-id="f21d9-150">604500</span><span class="sxs-lookup"><span data-stu-id="f21d9-150">604500</span></span>                | <span data-ttu-id="f21d9-151">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-151">Expense</span></span>       | <span data-ttu-id="f21d9-152">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="f21d9-152">Lease Expense</span></span>                                         |
| <span data-ttu-id="f21d9-153">604501</span><span class="sxs-lookup"><span data-stu-id="f21d9-153">604501</span></span>                | <span data-ttu-id="f21d9-154">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-154">Expense</span></span>       | <span data-ttu-id="f21d9-155">Despesa de arrendamento operacional de veículo - acréscimo de juros</span><span class="sxs-lookup"><span data-stu-id="f21d9-155">Vehicle operating lease expense - interest accretion</span></span>  |
| <span data-ttu-id="f21d9-156">604502</span><span class="sxs-lookup"><span data-stu-id="f21d9-156">604502</span></span>                | <span data-ttu-id="f21d9-157">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-157">Expense</span></span>       | <span data-ttu-id="f21d9-158">Despesa de arrendamento operacional de veículo - amortização</span><span class="sxs-lookup"><span data-stu-id="f21d9-158">Vehicle operating lease expense - amortization</span></span>        |
| <span data-ttu-id="f21d9-159">605200</span><span class="sxs-lookup"><span data-stu-id="f21d9-159">605200</span></span>                | <span data-ttu-id="f21d9-160">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-160">Expense</span></span>       | <span data-ttu-id="f21d9-161">Despesa de arrendamento operacional de imóvel - acréscimo de juros</span><span class="sxs-lookup"><span data-stu-id="f21d9-161">Building operating lease expense - interest accretion</span></span> |
| <span data-ttu-id="f21d9-162">605201</span><span class="sxs-lookup"><span data-stu-id="f21d9-162">605201</span></span>                | <span data-ttu-id="f21d9-163">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-163">Expense</span></span>       | <span data-ttu-id="f21d9-164">Despesa de arrendamento operacional de imóvel - amortização</span><span class="sxs-lookup"><span data-stu-id="f21d9-164">Building operating lease expense - amortization</span></span>       |
| <span data-ttu-id="f21d9-165">607101</span><span class="sxs-lookup"><span data-stu-id="f21d9-165">607101</span></span>                | <span data-ttu-id="f21d9-166">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-166">Expense</span></span>       | <span data-ttu-id="f21d9-167">Despesa de amortização de arrendamento de veículo</span><span class="sxs-lookup"><span data-stu-id="f21d9-167">Vehicle lease amortization expense</span></span>                    |
| <span data-ttu-id="f21d9-168">607102</span><span class="sxs-lookup"><span data-stu-id="f21d9-168">607102</span></span>                | <span data-ttu-id="f21d9-169">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-169">Expense</span></span>       | <span data-ttu-id="f21d9-170">Despesa de amortização de arrendamento de imóvel</span><span class="sxs-lookup"><span data-stu-id="f21d9-170">Building lease amortization expense</span></span>                   |
| <span data-ttu-id="f21d9-171">607103</span><span class="sxs-lookup"><span data-stu-id="f21d9-171">607103</span></span>                | <span data-ttu-id="f21d9-172">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-172">Expense</span></span>       | <span data-ttu-id="f21d9-173">Despesa de redução ao valor recuperável - arrendamentos mercantis</span><span class="sxs-lookup"><span data-stu-id="f21d9-173">Impairment expense - finance leases</span></span>                   |
| <span data-ttu-id="f21d9-174">607104</span><span class="sxs-lookup"><span data-stu-id="f21d9-174">607104</span></span>                | <span data-ttu-id="f21d9-175">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-175">Expense</span></span>       | <span data-ttu-id="f21d9-176">Despesa de redução ao valor recuperável - Arrendamentos operacionais</span><span class="sxs-lookup"><span data-stu-id="f21d9-176">Impairment expense - Operating leases</span></span>                 |
| <span data-ttu-id="f21d9-177">618910</span><span class="sxs-lookup"><span data-stu-id="f21d9-177">618910</span></span>                | <span data-ttu-id="f21d9-178">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-178">Expense</span></span>       | <span data-ttu-id="f21d9-179">Despesa de arrendamento- arrendamentos mercantis</span><span class="sxs-lookup"><span data-stu-id="f21d9-179">Lease expense - finance leases</span></span>                        |
| <span data-ttu-id="f21d9-180">618920</span><span class="sxs-lookup"><span data-stu-id="f21d9-180">618920</span></span>                | <span data-ttu-id="f21d9-181">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-181">Expense</span></span>       | <span data-ttu-id="f21d9-182">Pagamentos variáveis - arrendamentos mercantis</span><span class="sxs-lookup"><span data-stu-id="f21d9-182">Variable payments - finance leases</span></span>                    |
| <span data-ttu-id="f21d9-183">618930</span><span class="sxs-lookup"><span data-stu-id="f21d9-183">618930</span></span>                | <span data-ttu-id="f21d9-184">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-184">Expense</span></span>       | <span data-ttu-id="f21d9-185">Pagamentos variáveis - arrendamentos operacionais</span><span class="sxs-lookup"><span data-stu-id="f21d9-185">Variable payments - operating leases</span></span>                  |
| <span data-ttu-id="f21d9-186">800600</span><span class="sxs-lookup"><span data-stu-id="f21d9-186">800600</span></span>                | <span data-ttu-id="f21d9-187">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-187">Expense</span></span>       | <span data-ttu-id="f21d9-188">Despesa de juros de arrendamento de veículo</span><span class="sxs-lookup"><span data-stu-id="f21d9-188">Vehicle lease interest expense</span></span>                        |
| <span data-ttu-id="f21d9-189">800601</span><span class="sxs-lookup"><span data-stu-id="f21d9-189">800601</span></span>                | <span data-ttu-id="f21d9-190">Expense</span><span class="sxs-lookup"><span data-stu-id="f21d9-190">Expense</span></span>       | <span data-ttu-id="f21d9-191">Despesa de juros de arrendamento de imóvel</span><span class="sxs-lookup"><span data-stu-id="f21d9-191">Building lease interest expense</span></span>                       |
| <span data-ttu-id="f21d9-192">801201</span><span class="sxs-lookup"><span data-stu-id="f21d9-192">801201</span></span>                | <span data-ttu-id="f21d9-193">Balanço</span><span class="sxs-lookup"><span data-stu-id="f21d9-193">Balance sheet</span></span> | <span data-ttu-id="f21d9-194">Ganhos e perdas - modificação de arrendamento</span><span class="sxs-lookup"><span data-stu-id="f21d9-194">Gain & loss - lease modification</span></span>                      |

## <a name="configure-posting-accounts"></a><span data-ttu-id="f21d9-195">Configurar contas de lançamento</span><span class="sxs-lookup"><span data-stu-id="f21d9-195">Configure posting accounts</span></span>

<span data-ttu-id="f21d9-196">Para atribuir contas aos registros e grupos de arrendamentos que foram criados, você deverá configurar parâmetros para Arrendamento de ativos.</span><span class="sxs-lookup"><span data-stu-id="f21d9-196">To assign accounts to the lease books and groups that have been created, you must configure parameters for Asset leasing.</span></span>

1. <span data-ttu-id="f21d9-197">Acesse **Gerenciamento de ativos \> Configuração \> Parâmetros de lançamento de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-197">Go to **Asset leasing \> Setup \> Lease posting parameters**.</span></span>
2. <span data-ttu-id="f21d9-198">Na guia **contas**, abra a Guia Rápida **Contas de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-198">On the **Accounts** tab, open the **Lease accounts** FastTab.</span></span> <span data-ttu-id="f21d9-199">Determine as contas principais para arrendamentos mercantis e operacionais ao **Tipo de lançamento** correspondente.</span><span class="sxs-lookup"><span data-stu-id="f21d9-199">Determine the main accounts for finance and operation leases to corresponding **Posting type**.</span></span> <span data-ttu-id="f21d9-200">A tabela anterior mostra as contas relacionadas a arrendamentos operacionais e mercantis.</span><span class="sxs-lookup"><span data-stu-id="f21d9-200">The preceding table shows the accounts that are related to operating and finance leases.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f21d9-201">Esta etapa requer que você configure contas separadas para arrendamentos operacionais e mercantis para cada tipo de lançamento, exceto **Compensação de despesas de arrendamento** e **Aumento/diminuição de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-201">This step requires that you set up separate accounts for both operating and finance leases for each posting type except **Lease expense offset** and **Lease increase/decrease**.</span></span> <span data-ttu-id="f21d9-202">As empresas que aderem à estrutura de contabilidade do IFRS 16 devem adicionar uma conta principal ao arrendamento operacional.</span><span class="sxs-lookup"><span data-stu-id="f21d9-202">Companies that adhere to the IFRS 16 accounting framework must add a main account for operating lease.</span></span> <span data-ttu-id="f21d9-203">No entanto, o sistema não usará essa conta, embora seja um campo obrigatório, pois todas as concessões no IFRS 16 são classificadas como arrendamentos mercantis.</span><span class="sxs-lookup"><span data-stu-id="f21d9-203">But the system will not use this account even though it's a required field because all leases under IFRS 16 are classified as finance leases.</span></span>
    >[!NOTE]
    > <span data-ttu-id="f21d9-204">**Aumento/redução de arrendamento** será usado como tipo de lançamento para considerações adicionais sobre ativos, incluindo **Custo direto inicial, Incentivos de arrendamento, Pré-pagamentos de arrendamento e Custos de desmontagem**, mas lance na conta principal do Ativo de direito de uso, que tem como padrão **Ativo de arrendamento**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-204">**Lease increase/decrease** will be used as posting type for additional asset considerations, including **Initial direct cost, Lease incentives, Lease prepayments and Dismantling costs**, but post to the Right-of-use asset main account which defaults to **Lease asset**.</span></span>        
    
3. <span data-ttu-id="f21d9-205">Para selecionar um grupo de arrendamentos específico correspondente à conta principal, no campo **Código da Conta**, selecione **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="f21d9-205">To select a specific lease group corresponding to main account, in the **Account Code** field, select **Group**.</span></span> <span data-ttu-id="f21d9-206">Em seguida, no campo **Número da Conta/Grupo**, selecione o grupo de arrendamentos a ser atribuído à conta principal.</span><span class="sxs-lookup"><span data-stu-id="f21d9-206">Then, in the **Account/Group number** field, select the lease group to assign to the main account.</span></span>
4. <span data-ttu-id="f21d9-207">Para atribuir códigos de conta aos custos administrativos que foram configurados no sistema, na Guia Rápida **Custos de execução**, no campo **Tipo de despesa**, selecione uma despesa.</span><span class="sxs-lookup"><span data-stu-id="f21d9-207">To assign account codes to the administrative costs that have been set up in the system, on the **Executory costs** FastTab, in the **Expense type** field, select an expense.</span></span> <span data-ttu-id="f21d9-208">Em seguida, atribua as contas mercantis e operacionais a serem usadas para cada registro.</span><span class="sxs-lookup"><span data-stu-id="f21d9-208">Then assign the finance and operating accounts to use for each book.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f21d9-209">A conta mercantil ou operacional selecionada será debitada quando a fatura da despesa agendada for lançada.</span><span class="sxs-lookup"><span data-stu-id="f21d9-209">The selected finance or operating account will be debited when the invoice for the scheduled expense is posted.</span></span>
    > <span data-ttu-id="f21d9-210">**Contrapartida de despesa de arrendamento** será usado como tipo de lançamento para transações de custos de execução, mas lance na **Contrapartida** definida nas **Linhas da agenda de pagamento de custos de execução** no formulário de detalhes do arrendamento ou de registro do arrendamento.</span><span class="sxs-lookup"><span data-stu-id="f21d9-210">**Lease expense offset** will be used as posting type for executory costs transactions but post to defined **Offset account** in the **Execuroty costs payment schedule lines** in lease details or lease book form.</span></span>   