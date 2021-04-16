---
title: Tipos de lançamento de arrendamento
description: Este tópico descreve os tipos de lançamento usados para transações de arrendamento de ativo.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: ddc229f3ab8e048390f27503e2c6c26bd1a6f24f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841132"
---
# <a name="lease-posting-types"></a><span data-ttu-id="a468e-103">Tipos de lançamento de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-103">Lease posting types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a468e-104">Este tópico descreve os tipos de lançamento usados para transações de arrendamento de ativo.</span><span class="sxs-lookup"><span data-stu-id="a468e-104">This topic describes the posting types that are used for asset leasing transactions.</span></span>

## <a name="lease-asset"></a><span data-ttu-id="a468e-105">Ativo de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-105">Lease asset</span></span>

<span data-ttu-id="a468e-106">A conta é associada ao ativo de direito de uso (DDU).</span><span class="sxs-lookup"><span data-stu-id="a468e-106">The account is associated with the right-of-use (ROU) asset.</span></span> <span data-ttu-id="a468e-107">Essa conta é debitada quando um arrendamento é reconhecido inicialmente sob os novos padrões de contabilidade de arrendamento, o Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e o Padrão Internacional de Relatórios Financeiros 16 (IFRS 16).</span><span class="sxs-lookup"><span data-stu-id="a468e-107">This account is debited when a lease is initially recognized under the new lease accounting standards, Accounting Standards Codification Topic 842 (ASC 842) and International Financial Reporting Standard 16 (IFRS 16).</span></span> <span data-ttu-id="a468e-108">Para um arrendamento modificada, essa conta pode ser debitada ou creditada, dependendo se a modificação aumenta ou diminui a responsabilidade com arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a468e-108">For a modified lease, this account might be either debited or credited, depending on whether the modification increases or decreases the lease liability.</span></span>

<span data-ttu-id="a468e-109">**Exemplo de entradas de diário:** reconhecimento inicial</span><span class="sxs-lookup"><span data-stu-id="a468e-109">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="a468e-110">**Débito:** ativo de arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-110">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="a468e-111">**Crédito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-111">**Credit:** Lease liability XXX</span></span>

## <a name="lease-liability"></a><span data-ttu-id="a468e-112">Responsabilidade com arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-112">Lease liability</span></span>

<span data-ttu-id="a468e-113">A conta é associada à responsabilidade de arrendamento que ocorre quando os pagamentos são descontados sob os novos padrões IFRS 16 e ASC 842.</span><span class="sxs-lookup"><span data-stu-id="a468e-113">The account is associated with the lease liability that occurs when payments are discounted under the new IFRS 16 and ASC 842 standards.</span></span> <span data-ttu-id="a468e-114">Essa conta é creditada quando um arrendamento é reconhecido inicialmente sob os novos padrões.</span><span class="sxs-lookup"><span data-stu-id="a468e-114">This account is credited when a lease is initially recognized under the new standards.</span></span> <span data-ttu-id="a468e-115">É debitado de pagamentos do arrendamento e creditado para acúmulos de juros.</span><span class="sxs-lookup"><span data-stu-id="a468e-115">It's debited for lease payments and credited for interest accruals.</span></span>

<span data-ttu-id="a468e-116">**Exemplo de entradas de diário:** reconhecimento inicial</span><span class="sxs-lookup"><span data-stu-id="a468e-116">**Example journal entries:** Initial recognition</span></span><br>
<span data-ttu-id="a468e-117">**Débito:** ativo de arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-117">**Debit:** Lease asset XXX</span></span><br>
<span data-ttu-id="a468e-118">**Crédito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-118">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="a468e-119">**Exemplo de entradas de diário:** acúmulo de juros</span><span class="sxs-lookup"><span data-stu-id="a468e-119">**Example journal entries:** Interest accrual</span></span><br>
<span data-ttu-id="a468e-120">**Débito:** despesa de juros XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-120">**Debit:** Interest expense XXX</span></span><br>
<span data-ttu-id="a468e-121">**Crédito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-121">**Credit:** Lease liability XXX</span></span>

<span data-ttu-id="a468e-122">**Exemplo de entradas de diário:** pagamento do arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-122">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="a468e-123">**Débito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-123">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="a468e-124">**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-124">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="short-term-lease-liability"></a><span data-ttu-id="a468e-125">Responsabilidade com arrendamento de curto prazo</span><span class="sxs-lookup"><span data-stu-id="a468e-125">Short-term lease liability</span></span>

<span data-ttu-id="a468e-126">A conta é associada à responsabilidade com arrendamento de curto prazo quando a entrada de diário de reclassificação de responsabilidade com arrendamento de curto prazo é lançada.</span><span class="sxs-lookup"><span data-stu-id="a468e-126">The account is associated with the short-term lease liability when the short-term lease liability reclass journal entry is posted.</span></span> <span data-ttu-id="a468e-127">Essa conta é creditada no passivo de curto prazo da agenda de amortização no último dia do mês.</span><span class="sxs-lookup"><span data-stu-id="a468e-127">This account is credited for the short-term liability from the amortization schedule on the last day of the month.</span></span> <span data-ttu-id="a468e-128">No entanto, o mesmo valor é debitado no primeiro dia do mês seguinte.</span><span class="sxs-lookup"><span data-stu-id="a468e-128">However, the same amount is debited on the first day of the next month.</span></span>

<span data-ttu-id="a468e-129">**Exemplo de entradas de diário:** reclassificação de responsabilidade com arrendamento de curto prazo</span><span class="sxs-lookup"><span data-stu-id="a468e-129">**Example journal entries:** Short-term lease liability reclass</span></span><br>
<span data-ttu-id="a468e-130">**Débito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-130">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="a468e-131">**Crédito:** responsabilidade com arrendamento de curto prazo XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-131">**Credit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="a468e-132">**Débito:** responsabilidade com arrendamento de curto prazo XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-132">**Debit:** Short-term lease liability XXX</span></span><br>
<span data-ttu-id="a468e-133">**Crédito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-133">**Credit:** Lease liability XXX</span></span>

## <a name="depreciation-expense"></a><span data-ttu-id="a468e-134">Despesa de Depreciação</span><span class="sxs-lookup"><span data-stu-id="a468e-134">Depreciation expense</span></span>

<span data-ttu-id="a468e-135">A conta é associada à despesa relacionada à depreciação do ativo DDU sob o IFRS 16, ASC 842 e os arrendamentos mercantis sob o IAS 17 e ASC 840.</span><span class="sxs-lookup"><span data-stu-id="a468e-135">The account is associated with the expense that is related to the depreciation of the ROU asset under IFRS 16, ASC 842, and finance leases under IAS 17 and ASC 840.</span></span> <span data-ttu-id="a468e-136">Essa conta é debitada quando um ativo DDU é depreciado a cada mês.</span><span class="sxs-lookup"><span data-stu-id="a468e-136">This account is debited when an ROU asset is depreciated each month.</span></span>

<span data-ttu-id="a468e-137">**Exemplo de entradas de diário:** acúmulo de depreciação</span><span class="sxs-lookup"><span data-stu-id="a468e-137">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="a468e-138">**Débito:** despesa de depreciação XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-138">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="a468e-139">**Crédito:** depreciação acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-139">**Credit:** Accumulated Depreciation XXX</span></span>

## <a name="gainloss-on-lease-modification"></a><span data-ttu-id="a468e-140">Ganho/perda na modificação de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-140">Gain/loss on lease modification</span></span>

<span data-ttu-id="a468e-141">A conta é associada a quaisquer ganhos ou perdas que surjam das modificações de arrendamento.</span><span class="sxs-lookup"><span data-stu-id="a468e-141">The account is associated with any gains or losses that arise from lease modifications.</span></span> <span data-ttu-id="a468e-142">Um ganho pode surgir durante uma modificação de arrendamento se a modificação diminuir a responsabilidade com arrendamento por um valor que exceda o valor de carregamento do ativo DDU.</span><span class="sxs-lookup"><span data-stu-id="a468e-142">A gain might arise during a lease modification if the modification decreases the lease liability by an amount that exceeds the carrying value of the ROU asset.</span></span>

<span data-ttu-id="a468e-143">Por exemplo, um arrendamento tem um valor de carregamento atual da responsabilidade com arrendamento de US$ 150.000 e um valor de carregamento do ativo DDU de US$ 100.000.</span><span class="sxs-lookup"><span data-stu-id="a468e-143">For example, a lease has a current carrying value of the lease liability of $150,000 and a carrying value of the ROU asset of $100,000.</span></span> <span data-ttu-id="a468e-144">O arrendamento é modificado, e essa modificação gera um novo valor presente dos PVFMLP (pagamentos do arrendamento mínimos futuros) de US$ 40.000.</span><span class="sxs-lookup"><span data-stu-id="a468e-144">The lease is modified, and this modification produces a new present value of the future minimum lease payments (PVFMLP) of $40,000.</span></span> <span data-ttu-id="a468e-145">Portanto, a responsabilidade com arrendamento será debitada por US$ 110.000 (US$ 150.000 – US$ 40.000).</span><span class="sxs-lookup"><span data-stu-id="a468e-145">Therefore, the lease liability will be debited by $110,000 ($150,000 – $40,000).</span></span> <span data-ttu-id="a468e-146">Como o ativo DDU é de apenas US$ 100.000, a redução de US$ 110.000 diminuirá o ativo após 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="a468e-146">Because the ROU asset is only $100,000, the decrease of $110,000 will decrease the asset past 0 (zero).</span></span> <span data-ttu-id="a468e-147">Portanto, as diretrizes contábeis declaram que o restante deve ser registrado em uma conta de ganho.</span><span class="sxs-lookup"><span data-stu-id="a468e-147">Therefore, the accounting guidance states that the remainder should be booked to a gain account.</span></span> <span data-ttu-id="a468e-148">Nesse caso, a entrada de diário final será um débito para a responsabilidade com arrendamento para US$ 110.000, um crédito ao ativo de arrendamento para US$ 100.000 e um crédito na conta de ganho para US$ 10.000.</span><span class="sxs-lookup"><span data-stu-id="a468e-148">In this case, the final journal entry will be a debit to the lease liability for $110,000, a credit to the lease asset for $100,000, and a credit to the gain account for $10,000.</span></span>

<span data-ttu-id="a468e-149">**Exemplo de entradas de diário:** modificação do arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-149">**Example journal entries:** Lease modification</span></span><br>
<span data-ttu-id="a468e-150">**Débito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-150">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="a468e-151">**Crédito:** ativo de arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-151">**Credit:** Lease Asset XXX</span></span><br>
<span data-ttu-id="a468e-152">**Crédito:** ganho XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-152">**Credit:** Gain XXX</span></span>

## <a name="accumulated-depreciation"></a><span data-ttu-id="a468e-153">Depreciação Acumulada</span><span class="sxs-lookup"><span data-stu-id="a468e-153">Accumulated depreciation</span></span>

<span data-ttu-id="a468e-154">A conta é associada à conta de contra-ativo do ativo DDU.</span><span class="sxs-lookup"><span data-stu-id="a468e-154">The account is associated with the contra-asset account of the ROU asset.</span></span> <span data-ttu-id="a468e-155">Essa conta é creditada quando uma despesa de depreciação o é lançada.</span><span class="sxs-lookup"><span data-stu-id="a468e-155">This account is credited when a depreciation expense is posted.</span></span>

<span data-ttu-id="a468e-156">**Exemplo de entradas de diário:** acúmulo de depreciação</span><span class="sxs-lookup"><span data-stu-id="a468e-156">**Example journal entries:** Depreciation accrual</span></span><br>
<span data-ttu-id="a468e-157">**Débito:** despesa de depreciação XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-157">**Debit:** Depreciation expense XXX</span></span><br>
<span data-ttu-id="a468e-158">**Crédito:** depreciação acumulada XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-158">**Credit:** Accumulated depreciation XXX</span></span>

## <a name="variable-payment"></a><span data-ttu-id="a468e-159">Pagamento variável</span><span class="sxs-lookup"><span data-stu-id="a468e-159">Variable payment</span></span>

<span data-ttu-id="a468e-160">A conta está associada a pagamentos do arrendamento variáveis produzidos por uma reavaliação de índice sob os arrendamentos ASC 842, ASC 840 e IAS 17.</span><span class="sxs-lookup"><span data-stu-id="a468e-160">The account is associated with variable lease payments that are produced by an index revaluation under ASC 842, ASC 840, and IAS 17 leases.</span></span> <span data-ttu-id="a468e-161">Na agenda do pagamento do arrendamento, os pagamentos variáveis são incluídos na coluna **Pagamento variável**.</span><span class="sxs-lookup"><span data-stu-id="a468e-161">In the lease payment schedule, variable payments are included in the **Variable payment** column.</span></span> <span data-ttu-id="a468e-162">Essa conta é debitada quando uma fatura é criada em uma linha da agenda de pagamento que contém um pagamento variável.</span><span class="sxs-lookup"><span data-stu-id="a468e-162">This account is debited when an invoice is created against a payment schedule line that contains a variable payment.</span></span>

<span data-ttu-id="a468e-163">**Exemplo de entradas de diário:** pagamento do arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-163">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="a468e-164">**Débito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-164">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="a468e-165">**Débito:** pagamento variável XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-165">**Debit:** Variable payment XXX</span></span><br>
<span data-ttu-id="a468e-166">**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-166">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="deferred-rent-asset-liability"></a><span data-ttu-id="a468e-167">Ativo de arrendamento diferido (passivo)</span><span class="sxs-lookup"><span data-stu-id="a468e-167">Deferred rent asset (liability)</span></span>

<span data-ttu-id="a468e-168">A conta está associada ao ativo ou passivo de arrendamento diferido produzido por um arrendamento de tratamento de arrendamento diferido.</span><span class="sxs-lookup"><span data-stu-id="a468e-168">The account is associated with the deferred rent asset or liability that is produced by a deferred rent treatment lease.</span></span> <span data-ttu-id="a468e-169">Essa conta é debitada quando uma fatura é lançada em relação a um arrendamento de tratamento de arrendamento diferido, se o valor do pagamento do arrendamento for maior do que a despesa de arrendamento linear do período.</span><span class="sxs-lookup"><span data-stu-id="a468e-169">This account is debited when an invoice is posted against a deferred rent treatment lease, if the lease payment amount is more than the period's straight-line rent expense.</span></span> <span data-ttu-id="a468e-170">Será creditado se o pagamento do arrendamento for menor do que a despesa do arrendamento linear do período.</span><span class="sxs-lookup"><span data-stu-id="a468e-170">It's credited if the lease payment is less than the period's straight-line rent expense.</span></span>

<span data-ttu-id="a468e-171">**Exemplo de entradas de diário:** pagamento do arrendamento (arrendamento de tratamento de arrendamento diferido)</span><span class="sxs-lookup"><span data-stu-id="a468e-171">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="a468e-172">**Débito:** despesa de arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-172">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="a468e-173">**Crédito:** passivo de arrendamento deferido XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-173">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="a468e-174">**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-174">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="lease-expense"></a><span data-ttu-id="a468e-175">Despesa de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-175">Lease expense</span></span>

<span data-ttu-id="a468e-176">A conta será associada à despesa de arrendamento se o arrendamento for classificado como um arrendamento de tratamento de arrendamento diferido.</span><span class="sxs-lookup"><span data-stu-id="a468e-176">The account is associated with the lease expense if the lease is classified as a deferred rent treatment lease.</span></span> <span data-ttu-id="a468e-177">Essa conta é debitada quando uma fatura é lançada em relação a um arrendamento de tratamento de arrendamento diferido.</span><span class="sxs-lookup"><span data-stu-id="a468e-177">This account is debited when an invoice is posted against a deferred rent treatment lease.</span></span>

<span data-ttu-id="a468e-178">**Exemplo de entradas de diário:** pagamento do arrendamento (arrendamento de tratamento de arrendamento diferido)</span><span class="sxs-lookup"><span data-stu-id="a468e-178">**Example journal entries:** Lease payment (deferred rent treatment lease)</span></span><br>
<span data-ttu-id="a468e-179">**Débito:** despesa de arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-179">**Debit:** Lease expense XXX</span></span><br>
<span data-ttu-id="a468e-180">**Crédito:** passivo de arrendamento deferido XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-180">**Credit:** Deferred rent liability XXX</span></span><br>
<span data-ttu-id="a468e-181">**Crédito:** fornecedor a pagar/pagamento do arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-181">**Credit:** Vendor payable/lease payment XXX</span></span>

## <a name="impairment-expense"></a><span data-ttu-id="a468e-182">Despesa de redução ao valor recuperável</span><span class="sxs-lookup"><span data-stu-id="a468e-182">Impairment expense</span></span>

<span data-ttu-id="a468e-183">A conta é lançada em relação ao momento em que um arrendamento tem redução ao valor recuperável.</span><span class="sxs-lookup"><span data-stu-id="a468e-183">The account is posted against when a lease is impaired.</span></span> <span data-ttu-id="a468e-184">Essa conta é debitada, enquanto a conta de ativo DDU é creditada diretamente.</span><span class="sxs-lookup"><span data-stu-id="a468e-184">This account is debited, whereas the ROU asset account is directly credited.</span></span>

<span data-ttu-id="a468e-185">**Exemplo de entradas de diário:** pagamento do arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-185">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="a468e-186">**Débito:** despesa de redução ao valor recuperável XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-186">**Debit:** Impairment expense XXX</span></span><br>
<span data-ttu-id="a468e-187">**Crédito:** ativo DDU XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-187">**Credit:** ROU asset XXX</span></span>

## <a name="lease-payment"></a><span data-ttu-id="a468e-188">Pagamento de arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-188">Lease payment</span></span>

<span data-ttu-id="a468e-189">A conta será lançada se o parâmetro **Pagar ao Fornecedor** estiver desativado.</span><span class="sxs-lookup"><span data-stu-id="a468e-189">The account is posted against if the **Pay to Vendor** parameter is turned off.</span></span> <span data-ttu-id="a468e-190">Essa conta será creditada no lugar do fornecedor a pagar se o parâmetro for desativado.</span><span class="sxs-lookup"><span data-stu-id="a468e-190">This account is credited instead of the vendor payable if the parameter is turned off.</span></span>

<span data-ttu-id="a468e-191">**Exemplo de entradas de diário:** pagamento do arrendamento</span><span class="sxs-lookup"><span data-stu-id="a468e-191">**Example journal entries:** Lease payment</span></span><br>
<span data-ttu-id="a468e-192">**Débito:** responsabilidade com arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-192">**Debit:** Lease liability XXX</span></span><br>
<span data-ttu-id="a468e-193">**Crédito:** pagamento do arrendamento XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-193">**Credit:** Lease payment XXX</span></span>

## <a name="expense-type-postings"></a><span data-ttu-id="a468e-194">Lançamentos de tipo de despesa</span><span class="sxs-lookup"><span data-stu-id="a468e-194">Expense type postings</span></span>

<span data-ttu-id="a468e-195">A conta selecionada para cada tipo de despesa é debitada quando um pagamento para aquele tipo de despesa é gerado.</span><span class="sxs-lookup"><span data-stu-id="a468e-195">The account that is selected for each expense type is debited when a payment for that expense type is generated.</span></span> <span data-ttu-id="a468e-196">Por exemplo, a conta especificada para o tipo de despesa **Seguro** é debitada sempre que uma entrada de diário de fatura ou de pagamento é criada do plano de custo de execução para despesas de seguro.</span><span class="sxs-lookup"><span data-stu-id="a468e-196">For example, the account that is specified for the **Insurance** expense type is debited whenever an invoice or payment journal entry is created from the executory cost schedule for insurance expense.</span></span>

<span data-ttu-id="a468e-197">**Exemplo de entradas de diário:** pagamento do seguro</span><span class="sxs-lookup"><span data-stu-id="a468e-197">**Example journal entries:** Insurance payment</span></span><br>
<span data-ttu-id="a468e-198">**Débito:** conta do tipo de despesa de seguro XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-198">**Debit:** Insurance expense type account XXX</span></span><br>
<span data-ttu-id="a468e-199">**Crédito:** contrapartida XXX</span><span class="sxs-lookup"><span data-stu-id="a468e-199">**Credit:** Offset account XXX</span></span>

> [!NOTE]
> <span data-ttu-id="a468e-200">A contrapartida é selecionada no nível do arrendamento nas linhas da agenda de pagamento de custo de execução.</span><span class="sxs-lookup"><span data-stu-id="a468e-200">The offset account is selected at the lease level on the lines for the executory cost payment schedule.</span></span> <span data-ttu-id="a468e-201">Essa contrapartida pode ser associada ao fornecedor ou a uma conta contábil.</span><span class="sxs-lookup"><span data-stu-id="a468e-201">This offset account can associated with the vendor, or with a ledger account.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
