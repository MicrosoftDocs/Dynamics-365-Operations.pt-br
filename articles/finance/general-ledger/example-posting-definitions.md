---
title: ​Exemplos de definição de lançamento​
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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15772
ms.assetid: 3864e4da-853f-403d-b906-79631d80b363
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 301f15f1d7d8f0e10bbaf2546fcf727aff284624
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552293"
---
# <a name="posting-definition-examples"></a><span data-ttu-id="b959f-103">Exemplos de definições de lançamento</span><span class="sxs-lookup"><span data-stu-id="b959f-103">Posting definition examples</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b959f-104">Este artigo oferece exemplos que mostram como as definições de lançamento são usadas para ônus de ordem de compra e apropriações de orçamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-104">This article provides examples that show how posting definitions are used for purchase order encumbrances and budget appropriations.</span></span>

<span data-ttu-id="b959f-105">Antes que você leu este tópico, você deve estar familiarizado com as definições de lançamento e as definições de lançamento da transação.</span><span class="sxs-lookup"><span data-stu-id="b959f-105">Before you read this topic, you should be familiar with posting definitions and transaction posting definitions.</span></span> <span data-ttu-id="b959f-106">Para obter informações, consulte [Definições de lançamento](posting-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="b959f-106">For information, see [Posting definitions](posting-definitions.md).</span></span> <span data-ttu-id="b959f-107">Os exemplos a seguir podem ser configurados na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b959f-107">The following examples can be set up on the **Posting definitions** page.</span></span> <span data-ttu-id="b959f-108">Cada exemplo contém estas seções:</span><span class="sxs-lookup"><span data-stu-id="b959f-108">Each example contains these sections:</span></span>

-   <span data-ttu-id="b959f-109">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="b959f-109">Posting definition – Match criteria</span></span>
-   <span data-ttu-id="b959f-110">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="b959f-110">Posting definition – Generated entries</span></span>
-   <span data-ttu-id="b959f-111">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="b959f-111">Transactions with the accounts, dimension values, and amounts</span></span>
-   <span data-ttu-id="b959f-112">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="b959f-112">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="b959f-113">Quando ocorre uma correspondência entre as contas e os valores de dimensão no painel de **Fazer a correspondência de critérios** para a definição de lançamento e as contas e os valores de dimensão na transação, as entradas do razão são geradas com base no painel **Entradas geradas** para a definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-113">When a match occurs between the accounts and dimension values in the **Match criteria** pane for the posting definition and the accounts and dimension values on the transaction, ledger entries are generated based on the **Generated entries** pane for the posting definition.</span></span> 
> [!NOTE]
> <span data-ttu-id="b959f-114">Para associar uma definição de lançamento a um tipo de transação específico, use a página **Definições de lançamento da transação**.</span><span class="sxs-lookup"><span data-stu-id="b959f-114">To associate a posting definition with a specific transaction type, use the **Transaction posting definitions** page.</span></span> <span data-ttu-id="b959f-115">Depois de associar uma definição de lançamento a um tipo de transação e selecionar **Usar definições de lançamento** na página **Parâmetros da contabilidade**, todas as transações do tipo de transação selecionado devem usar as definições de lançamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-115">After you associate a posting definition with a transaction type and select **Use posting definitions** on the **General ledger parameters** page, all transactions of the selected transaction type must use posting definitions.</span></span>

## <a name="example-purchase-order-encumbrances"></a><span data-ttu-id="b959f-116">exemplo: Ônus da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="b959f-116">Example: Purchase order encumbrances</span></span>
<span data-ttu-id="b959f-117">Ao habilitar o processamento de ônus selecionando **Habilitar processo de ônus** na página **Parâmetros da contabilidade** as definições de lançamento devem ser usadas para registrar ônus na contabilidade para todas as contas que devem ser reservadas.</span><span class="sxs-lookup"><span data-stu-id="b959f-117">When you enable encumbrance processing by selecting **Enable encumbrance process** on the **General ledger parameters** page, posting definitions must be used to record encumbrances to the general ledger for any accounts that should be reserved.</span></span> <span data-ttu-id="b959f-118">Na maioria dos casos, todas as contas de despesas estão reservados no balanço.</span><span class="sxs-lookup"><span data-stu-id="b959f-118">In most cases, all expense accounts are reserved on the balance sheet.</span></span> 

<span data-ttu-id="b959f-119">As definições de lançamento para ônus são configuradas para o módulo **Compras** na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b959f-119">Posting definitions for encumbrances are set up for the **Purchasing** module on the **Posting definitions** page.</span></span> <span data-ttu-id="b959f-120">Em seguida, na área de **Compras** da página **Definições de lançamento de transação**, é possível selecionar o tipo de transação **Ordem de compra** para associar a definição de lançamento às ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="b959f-120">Then, in the **Purchasing** area of the **Transaction posting definitions** page, you can select the **Purchase order** transaction type to associate the posting definition with purchase orders.</span></span> 

<span data-ttu-id="b959f-121">Todas as transações de comprovante para ônus da ordem de compra devem conferir (isto é, débitos devem ser iguais aos créditos), em cada dimensão exclusiva em um comprovante.</span><span class="sxs-lookup"><span data-stu-id="b959f-121">All voucher transactions for purchase order encumbrances must balance (that is, debits must equal credits) in each unique dimension on a voucher.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="b959f-122">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="b959f-122">Posting definition – Match criteria</span></span>

| <span data-ttu-id="b959f-123">Estrutura da conta</span><span class="sxs-lookup"><span data-stu-id="b959f-123">Account structure</span></span>       | <span data-ttu-id="b959f-124">Fazer a correspondência de número de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-124">Match account number</span></span> | <span data-ttu-id="b959f-125">Prioridade</span><span class="sxs-lookup"><span data-stu-id="b959f-125">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="b959f-126">Estrutura de conta - </span><span class="sxs-lookup"><span data-stu-id="b959f-126">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="b959f-127">1</span><span class="sxs-lookup"><span data-stu-id="b959f-127">1</span></span>        |

<span data-ttu-id="b959f-128"><em>Um valor em branco no campo \**Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="b959f-128"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="b959f-129">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="b959f-129">Posting definition – Generated entries</span></span>

| <span data-ttu-id="b959f-130">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-130">Account structure</span></span> | <span data-ttu-id="b959f-131">Número de conta gerado</span><span class="sxs-lookup"><span data-stu-id="b959f-131">Generated account number</span></span>                    | <span data-ttu-id="b959f-132">Débito/crédito gerado</span><span class="sxs-lookup"><span data-stu-id="b959f-132">Generated debit/credit</span></span> |
|-------------------|---------------------------------------------|------------------------|
| <span data-ttu-id="b959f-133">Saldo</span><span class="sxs-lookup"><span data-stu-id="b959f-133">Balance</span></span>           | <span data-ttu-id="b959f-134">300143 - -(Conta de ônus)</span><span class="sxs-lookup"><span data-stu-id="b959f-134">300143 - -(Encumbrance account)</span></span>             | <span data-ttu-id="b959f-135">Igual</span><span class="sxs-lookup"><span data-stu-id="b959f-135">Same</span></span>                   |
| <span data-ttu-id="b959f-136">Saldo</span><span class="sxs-lookup"><span data-stu-id="b959f-136">Balance</span></span>           | <span data-ttu-id="b959f-137">300144 - -(Reserva para a conta de ônus)</span><span class="sxs-lookup"><span data-stu-id="b959f-137">300144 - -(Reserve for encumbrance account)</span></span> | <span data-ttu-id="b959f-138">Balancear</span><span class="sxs-lookup"><span data-stu-id="b959f-138">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="b959f-139">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="b959f-139">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="b959f-140">As contas e os valores de dimensão são originários de distribuições contábeis que você insere para uma linha da ordem de compra, ou vêm de contas e dimensões que são geradas automaticamente com base nas configurações padrão para fornecedores, itens, categorias e modelos de dimensão.</span><span class="sxs-lookup"><span data-stu-id="b959f-140">The accounts and dimension values come either from the accounting distributions that you enter for a purchase order line, or from the accounts and dimensions that are automatically generated based on the default settings for vendors, items, categories, and dimension templates.</span></span>

| <span data-ttu-id="b959f-141">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="b959f-141">Account + dimensions</span></span>           | <span data-ttu-id="b959f-142">Débito</span><span class="sxs-lookup"><span data-stu-id="b959f-142">Debit</span></span>  | <span data-ttu-id="b959f-143">Crédito</span><span class="sxs-lookup"><span data-stu-id="b959f-143">Credit</span></span> | <span data-ttu-id="b959f-144">Comentário</span><span class="sxs-lookup"><span data-stu-id="b959f-144">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="b959f-145">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-145">606400-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="b959f-146">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-146">250.00</span></span> |        |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="b959f-147">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="b959f-147">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="b959f-148">As entradas do razão geradas são criadas para registrar os ônus.</span><span class="sxs-lookup"><span data-stu-id="b959f-148">Generated ledger entries are created to record the encumbrances.</span></span>

| <span data-ttu-id="b959f-149">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="b959f-149">Account + dimensions</span></span>           | <span data-ttu-id="b959f-150">Débito</span><span class="sxs-lookup"><span data-stu-id="b959f-150">Debit</span></span>  | <span data-ttu-id="b959f-151">Crédito</span><span class="sxs-lookup"><span data-stu-id="b959f-151">Credit</span></span> | <span data-ttu-id="b959f-152">Comentário</span><span class="sxs-lookup"><span data-stu-id="b959f-152">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="b959f-153">300143-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-153">300143-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="b959f-154">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-154">250.00</span></span> |        |         |
| <span data-ttu-id="b959f-155">300144-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-155">300144-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="b959f-156">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-156">250.00</span></span> |         |

<span data-ttu-id="b959f-157">Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-157">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="b959f-158">Portanto, quando 606500-OU\_1-OU\_3566-Training é avaliado, as entradas geradas são criadas para as contas que são definidas no painel de **Entradas geradas** para a definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-158">Therefore, when 606500-OU\_1-OU\_3566-Training is evaluated, generated entries are created for the accounts that are defined in the **Generated entries** pane for the posting definition.</span></span>

## <a name="example-budget-appropriations"></a><span data-ttu-id="b959f-159">habilitar apropriações do orçamento</span><span class="sxs-lookup"><span data-stu-id="b959f-159">Example: Budget appropriations</span></span>
<span data-ttu-id="b959f-160">Quando você habilita a apropriação do orçamento selecionando **Habilitar apropriação do orçamento** na página **Parâmetros da contabilidade**, as definições de lançamento devem ser usadas para registrar entradas de registro de orçamento na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b959f-160">When you enable budget appropriation by selecting **Enable budget appropriation** on the **General ledger parameters** page, posting definitions must be used to record budget register entries to the general ledger.</span></span> <span data-ttu-id="b959f-161">Quando uma configuração de controle de orçamento estiver ativa e habilitada, as definições de lançamento e as definições de lançamento da transação poderão ser usadas para oferecer suporte à gravação de entradas de apropriações, revisões, transferências, projetos, ativos fixos e previsão de suprimento e demanda para a contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b959f-161">When a budget control configuration is active and is turned on, posting definitions and transaction posting definitions can be used to support the recording of entries for appropriations, revisions, transfers, projects, fixed assets, and supply and demand forecasts to the general ledger.</span></span> 

<span data-ttu-id="b959f-162">Para configurar uma definição de lançamento para entradas de registro de orçamento que possuam **Orçamento original** e que tenha as apropriações ativadas, selecione o módulo **Orçamento** na página **Definições de lançamento**.</span><span class="sxs-lookup"><span data-stu-id="b959f-162">To set up a posting definition for budget register entries that has a budget type of **Original budget**, and that has appropriations enabled, select the **Budget** module on the **Posting definitions** page.</span></span> <span data-ttu-id="b959f-163">Em seguida, na área **Orçamento** da página **Definições de lançamento de transação**, você pode usar os códigos de orçamento para associar a definição de lançamento às entradas de registro de orçamento que têm um tipo de orçamento de **Orçamento original**.</span><span class="sxs-lookup"><span data-stu-id="b959f-163">Then, in the **Budget** area of the **Transaction posting definitions** page, you can use budget codes to associate the posting definition with budget register entries that have a budget type of **Original budget**.</span></span> 

<span data-ttu-id="b959f-164">Quando apropriações de orçamento e as definições de lançamento são habilitadas, as entradas de registro de orçamento são registradas para controle de orçamento e na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="b959f-164">When budget appropriations and posting definitions are enabled, the budget register entries are recorded for budget control and in the general ledger.</span></span>

### <a name="posting-definition--match-criteria"></a><span data-ttu-id="b959f-165">Definição dos critérios de correspondência lançamento –</span><span class="sxs-lookup"><span data-stu-id="b959f-165">Posting definition – Match criteria</span></span>

| <span data-ttu-id="b959f-166">Estrutura da conta</span><span class="sxs-lookup"><span data-stu-id="b959f-166">Account structure</span></span>       | <span data-ttu-id="b959f-167">Fazer a correspondência de número de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-167">Match account number</span></span> | <span data-ttu-id="b959f-168">Prioridade</span><span class="sxs-lookup"><span data-stu-id="b959f-168">Priority</span></span> |
|-------------------------|----------------------|----------|
| <span data-ttu-id="b959f-169">Estrutura de conta - </span><span class="sxs-lookup"><span data-stu-id="b959f-169">Account Structure - P&L</span></span> | \*                   | <span data-ttu-id="b959f-170">1</span><span class="sxs-lookup"><span data-stu-id="b959f-170">1</span></span>        |

<span data-ttu-id="b959f-171"><em>Um valor em branco no campo \**Fazer a correspondência de número de conta</em>* significa que todas as contas correspondentes na estrutura de conta definida fazem parte da regra correspondente.</span><span class="sxs-lookup"><span data-stu-id="b959f-171"><em>A blank value in the \**Match account number</em>* field means that all matching accounts in the defined account structure are part of the matching rule.</span></span>

### <a name="posting-definition--generated-entries"></a><span data-ttu-id="b959f-172">definição de lançamento – entradas gerados</span><span class="sxs-lookup"><span data-stu-id="b959f-172">Posting definition – Generated entries</span></span>

| <span data-ttu-id="b959f-173">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-173">Account structure</span></span> | <span data-ttu-id="b959f-174">Número de conta gerado</span><span class="sxs-lookup"><span data-stu-id="b959f-174">Generated account number</span></span>              | <span data-ttu-id="b959f-175">Débito/crédito gerado</span><span class="sxs-lookup"><span data-stu-id="b959f-175">Generated debit/credit</span></span> |
|-------------------|---------------------------------------|------------------------|
| <span data-ttu-id="b959f-176">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-176">Account structure</span></span> | <span data-ttu-id="b959f-177">300145 - -(Conta de receita prevista)</span><span class="sxs-lookup"><span data-stu-id="b959f-177">300145 - -(Estimated revenue account)</span></span> | <span data-ttu-id="b959f-178">Igual</span><span class="sxs-lookup"><span data-stu-id="b959f-178">Same</span></span>                   |
| <span data-ttu-id="b959f-179">Estrutura de conta</span><span class="sxs-lookup"><span data-stu-id="b959f-179">Account structure</span></span> | <span data-ttu-id="b959f-180">300146 - -(Conta de apropriação)</span><span class="sxs-lookup"><span data-stu-id="b959f-180">300146 - -(Appropriation account)</span></span>     | <span data-ttu-id="b959f-181">Balancear</span><span class="sxs-lookup"><span data-stu-id="b959f-181">Balancing</span></span>              |

### <a name="transactions-with-the-accounts-dimension-values-and-amounts"></a><span data-ttu-id="b959f-182">transações com as contas, os valores de dimensão, e os valores</span><span class="sxs-lookup"><span data-stu-id="b959f-182">Transactions with the accounts, dimension values, and amounts</span></span>

<span data-ttu-id="b959f-183">Você insere as contas, valores de dimensão e valores para a entrada da conta de orçamento na página **Entrada de registro de orçamento**.</span><span class="sxs-lookup"><span data-stu-id="b959f-183">You enter the accounts, dimension values, and amounts for the budget account entry on the **Budget register entry** page.</span></span>

| <span data-ttu-id="b959f-184">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="b959f-184">Account + dimensions</span></span>           | <span data-ttu-id="b959f-185">Débito</span><span class="sxs-lookup"><span data-stu-id="b959f-185">Debit</span></span> | <span data-ttu-id="b959f-186">Crédito</span><span class="sxs-lookup"><span data-stu-id="b959f-186">Credit</span></span> | <span data-ttu-id="b959f-187">Comentário</span><span class="sxs-lookup"><span data-stu-id="b959f-187">Comment</span></span> |
|--------------------------------|-------|--------|---------|
| <span data-ttu-id="b959f-188">606400-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-188">606400-OU\_1-OU\_3566-Training</span></span> |       | <span data-ttu-id="b959f-189">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-189">250.00</span></span> |         |

### <a name="ledger-entries-generated-from-the-posting-definition"></a><span data-ttu-id="b959f-190">Entrada do razão geradas na definição de lançamento</span><span class="sxs-lookup"><span data-stu-id="b959f-190">Ledger entries generated from the posting definition</span></span>

<span data-ttu-id="b959f-191">As entradas do razão geradas são criadas para registrar o orçamento original em cada dimensão.</span><span class="sxs-lookup"><span data-stu-id="b959f-191">Generated ledger entries are created to record the original budget in each dimension.</span></span>

| <span data-ttu-id="b959f-192">Conta + dimensões</span><span class="sxs-lookup"><span data-stu-id="b959f-192">Account + dimensions</span></span>           | <span data-ttu-id="b959f-193">Débito</span><span class="sxs-lookup"><span data-stu-id="b959f-193">Debit</span></span>  | <span data-ttu-id="b959f-194">Crédito</span><span class="sxs-lookup"><span data-stu-id="b959f-194">Credit</span></span> | <span data-ttu-id="b959f-195">Comentário</span><span class="sxs-lookup"><span data-stu-id="b959f-195">Comment</span></span> |
|--------------------------------|--------|--------|---------|
| <span data-ttu-id="b959f-196">300145-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-196">300145-OU\_1-OU\_3566-Training</span></span> |        | <span data-ttu-id="b959f-197">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-197">250.00</span></span> |         |
| <span data-ttu-id="b959f-198">300146-OU\_1-OU\_3566-Training</span><span class="sxs-lookup"><span data-stu-id="b959f-198">300146-OU\_1-OU\_3566-Training</span></span> | <span data-ttu-id="b959f-199">250,00</span><span class="sxs-lookup"><span data-stu-id="b959f-199">250.00</span></span> |        |         |

<span data-ttu-id="b959f-200">Neste exemplo, qualquer conta que está parte da estrutura de conta - L&P coincidir com os critérios de definição de lançamento.</span><span class="sxs-lookup"><span data-stu-id="b959f-200">In this example, any account that is part of Account Structure - P&L matches the posting definition criteria.</span></span> <span data-ttu-id="b959f-201">Portanto, quando 606400-OU\_1-OU\_3566-Training é avaliado, as entradas do razão geradas são criadas.</span><span class="sxs-lookup"><span data-stu-id="b959f-201">Therefore, when 606400-OU\_1-OU\_3566-Training is evaluated, the generated ledger entries are created.</span></span>





