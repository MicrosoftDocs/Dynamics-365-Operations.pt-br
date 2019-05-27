---
title: Definições de lançamento
description: Este artigo oferece exemplos que mostram como as definições de lançamento são usadas para ônus de ordem de compra e apropriações de orçamento.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: JournalizingDefinition, JournalizingDefinitionTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5fb08a86639e9a9a79dca5fc1200e73e5870432
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564684"
---
# <a name="posting-definition-examples"></a><span data-ttu-id="35501-103">Exemplos de definições de lançamento</span><span class="sxs-lookup"><span data-stu-id="35501-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="35501-104">Este artigo oferece exemplos que mostram como as definições de lançamento são usadas para ônus de ordem de compra e apropriações de orçamento.</span><span class="sxs-lookup"><span data-stu-id="35501-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="35501-105">Antes que você leu este tópico, você deve estar familiarizado com as definições de lançamento e as definições de lançamento da transação.</span><span class="sxs-lookup"><span data-stu-id="35501-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="35501-106">Para obter informações, consulte [Definições de lançamento](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="35501-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="35501-107">Os exemplos a seguir podem ser configurados na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="35501-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="35501-108">Cada exemplo contém estas seções:</span><span class="sxs-lookup"><span data-stu-id="35501-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="35501-109">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="35501-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="35501-110">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="35501-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="35501-111">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="35501-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="35501-112">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="35501-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="35501-113">Quando ocorre uma correspondência entre as contas e os valores de dimensão no painel de **Fazer a correspondência de critérios** para a definição de lançamento e as contas e os valores de dimensão na transação, as entradas do razão são geradas com base no painel **Entradas geradas** para a definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="35501-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="35501-114">Para associar uma definição de lançamento a um tipo de transação específico, use a página **Definições de lançamento da transação**.</span><span class="sxs-lookup"><span data-stu-id="35501-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="35501-115">Depois de associar uma definição de lançamento a um tipo de transação e selecionar **Usar definições de lançamento** na página **Parâmetros da contabilidade**, todas as transações do tipo de transação selecionado devem usar as definições de lançamento.</span><span class="sxs-lookup"><span data-stu-id="35501-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="35501-116">exemplo: Ônus da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="35501-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="35501-117">Ao habilitar o processamento de ônus selecionando **Habilitar processo de ônus** na página **Parâmetros da contabilidade** as definições de lançamento devem ser usadas para registrar ônus na contabilidade para todas as contas que devem ser reservadas.</span><span class="sxs-lookup"><span data-stu-id="35501-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="35501-118">Na maioria dos casos, todas as contas de despesas estão reservados no balanço.</span><span class="sxs-lookup"><span data-stu-id="35501-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="35501-119">As definições de lançamento para ônus são configuradas para o módulo **Compras** na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="35501-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="35501-120">Em seguida, na área de **Compras** da página **Definições de lançamento de transação**, é possível selecionar o tipo de transação **Ordem de compra** para associar a definição de lançamento às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="35501-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="35501-121">Todas as transações de comprovante para ônus da ordem de compra devem conferir (isto é, débitos devem ser iguais aos créditos), em cada dimensão exclusiva em um comprovante.</span><span class="sxs-lookup"><span data-stu-id="35501-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="35501-122">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="35501-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="35501-123">Estrutura da conta</span><span class="sxs-lookup"><span data-stu-id="35501-123">Account structure</span></span>       | <span data-ttu-id="35501-124">Fazer a correspondência de número de conta</span><span class="sxs-lookup"><span data-stu-id="35501-124">Match account number</span></span> | <span data-ttu-id="35501-125">Prioridade</span><span class="sxs-lookup"><span data-stu-id="35501-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="35501-126">Estrutura de conta - </span><span class="sxs-lookup"><span data-stu-id="35501-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="35501-127">1</span><span class="sxs-lookup"><span data-stu-id="35501-127">1</span></span>        |

<span data-ttu-id="35501-128"><em>Um valor em branco no campo \**Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="35501-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="35501-129">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="35501-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="35501-130">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="35501-130">Account structure</span></span> | <span data-ttu-id="35501-131">Número de conta gerado</span><span class="sxs-lookup"><span data-stu-id="35501-131">Generated account number</span></span>                    | <span data-ttu-id="35501-132">Débito/crédito gerado</span><span class="sxs-lookup"><span data-stu-id="35501-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="35501-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="35501-133">Balance</span></span>           | <span data-ttu-id="35501-134">300143 - -(Conta de ônus)</span><span class="sxs-lookup"><span data-stu-id="35501-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="35501-135">Igual</span><span class="sxs-lookup"><span data-stu-id="35501-135">Same</span></span>                   |
| <span data-ttu-id="35501-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="35501-136">Balance</span></span>           | <span data-ttu-id="35501-137">300144 - -(Reserva para a conta de ônus)</span><span class="sxs-lookup"><span data-stu-id="35501-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="35501-138">Balancear</span><span class="sxs-lookup"><span data-stu-id="35501-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="35501-139">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="35501-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="35501-140">As contas e os valores de dimensão são originários de distribuições contábeis que você insere para uma linha da ordem de compra, ou vêm de contas e dimensões que são geradas automaticamente com base nas configurações padrão para fornecedores, itens, categorias e modelos de dimensão.</span><span class="sxs-lookup"><span data-stu-id="35501-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="35501-141">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="35501-141">Account + dimensions</span></span>           | <span data-ttu-id="35501-142">Débito</span><span class="sxs-lookup"><span data-stu-id="35501-142">Debit</span></span>  | <span data-ttu-id="35501-143">Crédito</span><span class="sxs-lookup"><span data-stu-id="35501-143">Credit</span></span> | <span data-ttu-id="35501-144">Comentário</span><span class="sxs-lookup"><span data-stu-id="35501-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="35501-145">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="35501-146">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="35501-147">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="35501-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="35501-148">As entradas do razão geradas são criadas para registrar os ônus.</span><span class="sxs-lookup"><span data-stu-id="35501-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="35501-149">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="35501-149">Account + dimensions</span></span>           | <span data-ttu-id="35501-150">Débito</span><span class="sxs-lookup"><span data-stu-id="35501-150">Debit</span></span>  | <span data-ttu-id="35501-151">Crédito</span><span class="sxs-lookup"><span data-stu-id="35501-151">Credit</span></span> | <span data-ttu-id="35501-152">Comentário</span><span class="sxs-lookup"><span data-stu-id="35501-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="35501-153">300143-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="35501-154">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-154">250.00</span></span> |        |         |
| <span data-ttu-id="35501-155">300144-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="35501-156">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-156">250.00</span></span> |         |

<span data-ttu-id="35501-157">Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="35501-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="35501-158">Portanto, quando 606500-OU\_1-OU\_3566-Training é avaliado, as entradas geradas são criadas para as contas que são definidas no painel de **Entradas geradas** para a definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="35501-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="35501-159">habilitar apropriações do orçamento</span><span class="sxs-lookup"><span data-stu-id="35501-159">Example: Budget appropriations</span></span>
<span data-ttu-id="35501-160">Quando você habilita a apropriação do orçamento selecionando **Habilitar apropriação do orçamento** na página **Parâmetros da contabilidade**, as definições de lançamento devem ser usadas para registrar entradas de registro de orçamento na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35501-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="35501-161">Quando uma configuração de controle de orçamento estiver ativa e habilitada, as definições de lançamento e as definições de lançamento da transação poderão ser usadas para oferecer suporte à gravação de entradas de apropriações, revisões, transferências, projetos, ativos fixos e previsão de suprimento e demanda para a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35501-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="35501-162">Para configurar uma definição de lançamento para entradas de registro de orçamento que possuam **Orçamento original** e que tenha as apropriações ativadas, selecione o módulo **Orçamento** na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="35501-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="35501-163">Em seguida, na área **Orçamento** da página **Definições de lançamento de transação**, você pode usar os códigos de orçamento para associar a definição de lançamento às entradas de registro de orçamento que têm um tipo de orçamento de **Orçamento original**.</span><span class="sxs-lookup"><span data-stu-id="35501-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="35501-164">Quando apropriações de orçamento e as definições de lançamento são habilitadas, as entradas de registro de orçamento são registradas para controle de orçamento e na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="35501-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="35501-165">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="35501-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="35501-166">Estrutura da conta</span><span class="sxs-lookup"><span data-stu-id="35501-166">Account structure</span></span>       | <span data-ttu-id="35501-167">Fazer a correspondência de número de conta</span><span class="sxs-lookup"><span data-stu-id="35501-167">Match account number</span></span> | <span data-ttu-id="35501-168">Prioridade</span><span class="sxs-lookup"><span data-stu-id="35501-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="35501-169">Estrutura de conta - </span><span class="sxs-lookup"><span data-stu-id="35501-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="35501-170">1</span><span class="sxs-lookup"><span data-stu-id="35501-170">1</span></span>        |

<span data-ttu-id="35501-171"><em>Um valor em branco no campo \**Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="35501-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="35501-172">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="35501-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="35501-173">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="35501-173">Account structure</span></span> | <span data-ttu-id="35501-174">Número de conta gerado</span><span class="sxs-lookup"><span data-stu-id="35501-174">Generated account number</span></span>              | <span data-ttu-id="35501-175">Débito/crédito gerado</span><span class="sxs-lookup"><span data-stu-id="35501-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="35501-176">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="35501-176">Account structure</span></span> | <span data-ttu-id="35501-177">300145 - -(Conta de receita prevista)</span><span class="sxs-lookup"><span data-stu-id="35501-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="35501-178">Igual</span><span class="sxs-lookup"><span data-stu-id="35501-178">Same</span></span>                   |
| <span data-ttu-id="35501-179">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="35501-179">Account structure</span></span> | <span data-ttu-id="35501-180">300146 - -(Conta de apropriação)</span><span class="sxs-lookup"><span data-stu-id="35501-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="35501-181">Balancear</span><span class="sxs-lookup"><span data-stu-id="35501-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="35501-182">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="35501-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="35501-183">Você insere as contas, valores de dimensão e valores para a entrada da conta de orçamento na página **Entrada de registro de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="35501-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="35501-184">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="35501-184">Account + dimensions</span></span>           | <span data-ttu-id="35501-185">Débito</span><span class="sxs-lookup"><span data-stu-id="35501-185">Debit</span></span> | <span data-ttu-id="35501-186">Crédito</span><span class="sxs-lookup"><span data-stu-id="35501-186">Credit</span></span> | <span data-ttu-id="35501-187">Comentário</span><span class="sxs-lookup"><span data-stu-id="35501-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="35501-188">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="35501-189">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="35501-190">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="35501-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="35501-191">As entradas do razão geradas são criadas para registrar o orçamento original em cada dimensão.</span><span class="sxs-lookup"><span data-stu-id="35501-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="35501-192">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="35501-192">Account + dimensions</span></span>           | <span data-ttu-id="35501-193">Débito</span><span class="sxs-lookup"><span data-stu-id="35501-193">Debit</span></span>  | <span data-ttu-id="35501-194">Crédito</span><span class="sxs-lookup"><span data-stu-id="35501-194">Credit</span></span> | <span data-ttu-id="35501-195">Comentário</span><span class="sxs-lookup"><span data-stu-id="35501-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="35501-196">300145-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="35501-197">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-197">250.00</span></span> |         |
| <span data-ttu-id="35501-198">300146-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="35501-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="35501-199">250,00</span><span class="sxs-lookup"><span data-stu-id="35501-199">250.00</span></span> |        |         |

<span data-ttu-id="35501-200">Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="35501-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="35501-201">Portanto, quando 606400-OU\_1-OU\_3566-Training é avaliado, as entradas do razão geradas são criadas.</span><span class="sxs-lookup"><span data-stu-id="35501-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>





