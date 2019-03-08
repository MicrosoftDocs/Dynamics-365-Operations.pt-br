---
title: Efeitos de depreciação em reversões
description: Este artigo discute implicações potenciais para reverter uma transação de ativo fixo.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 2961
ms.assetid: 63a3ac92-c321-4379-a86a-b1b14915f340
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d624fa998329680d9fa471fa325f6fcfd3920c6a
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "320135"
---
# <a name="depreciation-effects-with-reversals"></a><span data-ttu-id="e0b98-103">Efeitos de depreciação em reversões</span><span class="sxs-lookup"><span data-stu-id="e0b98-103">Depreciation effects with reversals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0b98-104">Este artigo discute implicações potenciais para reverter uma transação de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e0b98-104">This article discusses potential implications of reversing a fixed asset transaction.</span></span> 

<span data-ttu-id="e0b98-105">Você pode reverter transações de ativo fixo e transações associadas a um ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="e0b98-105">You can reverse fixed asset transactions, and the transactions that are associated with a fixed asset.</span></span> <span data-ttu-id="e0b98-106">Você também pode revogar uma transação revertida.</span><span class="sxs-lookup"><span data-stu-id="e0b98-106">You can also revoke a reversed transaction.</span></span> 

<span data-ttu-id="e0b98-107">Você pode reverter ou revogar uma transação que não seja a transação lançada mais recentemente nas depreciações para o ativo.</span><span class="sxs-lookup"><span data-stu-id="e0b98-107">You can reverse or revoke a transaction that was not the most recent transaction posted to the book for the asset.</span></span> <span data-ttu-id="e0b98-108">Você deve determinar primeiro se alguma transação de depreciação foi lançada após a transação que está sendo revertida.</span><span class="sxs-lookup"><span data-stu-id="e0b98-108">You should first determine whether any depreciation transactions were posted after the transaction that you are reversing.</span></span> <span data-ttu-id="e0b98-109">Isso ocorre porque a depreciação não é recalculada durante a reversão de uma transação.</span><span class="sxs-lookup"><span data-stu-id="e0b98-109">This is because depreciation is not recalculated when you reverse a transaction.</span></span> <span data-ttu-id="e0b98-110">Portanto, a depreciação normalmente é superestimada ou subestimada após a reversão, como mostram os exemplos.</span><span class="sxs-lookup"><span data-stu-id="e0b98-110">Therefore, depreciation often is overstated or understated after the reversal, as shown in the examples.</span></span> 

<span data-ttu-id="e0b98-111">Para garantir que a depreciação está correta ao reverter uma transação, não continue com a reversão se receber uma mensagem durante esse processo indicando que a depreciação não será recalculada.</span><span class="sxs-lookup"><span data-stu-id="e0b98-111">To make sure that depreciation is correct when you reverse a transaction, do not continue with the reversal if you receive a message that states that depreciation will not be recalculated.</span></span> <span data-ttu-id="e0b98-112">Em vez disso, primeiro estorne a transação de depreciação lançada após a transação que tentou reverter e, depois, continue com a devolução.</span><span class="sxs-lookup"><span data-stu-id="e0b98-112">Instead, first reverse the depreciation transaction that was posted after the transaction you tried to reverse, and then continue with the reversal.</span></span> <span data-ttu-id="e0b98-113">Você não será avisado sobre recálculos da depreciação e poderá continuar com a reversão.</span><span class="sxs-lookup"><span data-stu-id="e0b98-113">You will not be warned about depreciation recalculations, and you can continue with the reversal.</span></span> 

<span data-ttu-id="e0b98-114">Os exemplos a seguir mostram os cálculos feitos se você continuar após a mensagem de aviso, sem primeiro reverter as transações de depreciação.</span><span class="sxs-lookup"><span data-stu-id="e0b98-114">The following examples show the calculations that occur if you continue beyond the message without first reversing the depreciation transactions.</span></span>

## <a name="example-1-depreciation-is-overstated"></a><span data-ttu-id="e0b98-115">Exemplo 1: a depreciação é superestimada</span><span class="sxs-lookup"><span data-stu-id="e0b98-115">Example 1: Depreciation is overstated</span></span>
<span data-ttu-id="e0b98-116">Um ativo é configurado com uma vida útil de 5 anos e uma depreciação linear (60 períodos de depreciação).</span><span class="sxs-lookup"><span data-stu-id="e0b98-116">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="e0b98-117">Neste exemplo, a depreciação é superestimada.</span><span class="sxs-lookup"><span data-stu-id="e0b98-117">In this example, depreciation is overstated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="e0b98-118">Histórico de transações de ativo</span><span class="sxs-lookup"><span data-stu-id="e0b98-118">Asset transaction history</span></span>

| <span data-ttu-id="e0b98-119">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-119">Date</span></span>       | <span data-ttu-id="e0b98-120">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-120">Transaction type</span></span>                                                          | <span data-ttu-id="e0b98-121">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-121">Amount</span></span>                                    |
|------------|---------------------------------------------------------------------------|-------------------------------------------|
| <span data-ttu-id="e0b98-122">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-122">January 1</span></span>  | <span data-ttu-id="e0b98-123">Aquisição</span><span class="sxs-lookup"><span data-stu-id="e0b98-123">Acquisition</span></span>                                                               | <span data-ttu-id="e0b98-124">59.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-124">59,000.00</span></span>                                 |
| <span data-ttu-id="e0b98-125">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-125">January 1</span></span>  | <span data-ttu-id="e0b98-126">Ajuste de aquisição</span><span class="sxs-lookup"><span data-stu-id="e0b98-126">Acquisition adjustment</span></span>                                                    | <span data-ttu-id="e0b98-127">1.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-127">1,000.00</span></span>                                  |
| <span data-ttu-id="e0b98-128">31 de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-128">January 31</span></span> | <span data-ttu-id="e0b98-129">Depreciação (criada usando uma proposta para um período de depreciação)</span><span class="sxs-lookup"><span data-stu-id="e0b98-129">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="e0b98-130">Cálculo de 1.000,00: Valor contábil (59.000 + 1.000)/Número de períodos de depreciação restantes (60)</span><span class="sxs-lookup"><span data-stu-id="e0b98-130">1,000.00Calculation: Book value (59,000 + 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="e0b98-131">Ação de reversão</span><span class="sxs-lookup"><span data-stu-id="e0b98-131">Reversal action</span></span>

| <span data-ttu-id="e0b98-132">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-132">Date</span></span>      | <span data-ttu-id="e0b98-133">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-133">Transaction type</span></span>                | <span data-ttu-id="e0b98-134">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-134">Amount</span></span>    |
|-----------|---------------------------------|-----------|
| <span data-ttu-id="e0b98-135">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-135">January 1</span></span> | <span data-ttu-id="e0b98-136">Reversão do ajuste de aquisição</span><span class="sxs-lookup"><span data-stu-id="e0b98-136">Acquisition adjustment reversal</span></span> | <span data-ttu-id="e0b98-137">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-137">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="e0b98-138">Efeito da depreciação</span><span class="sxs-lookup"><span data-stu-id="e0b98-138">Depreciation effect</span></span>

| <span data-ttu-id="e0b98-139">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-139">Date</span></span>        | <span data-ttu-id="e0b98-140">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-140">Transaction type</span></span>        | <span data-ttu-id="e0b98-141">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-141">Amount</span></span>                                                                                |
|-------------|-------------------------|---------------------------------------------------------------------------------------|
| <span data-ttu-id="e0b98-142">28 de fevereiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-142">February 28</span></span> | <span data-ttu-id="e0b98-143">Depreciação (proposta)</span><span class="sxs-lookup"><span data-stu-id="e0b98-143">Depreciation (proposal)</span></span> | <span data-ttu-id="e0b98-144">Cálculo de 983,05: Valor contábil (59.000 - 1.000 de depreciação)/Número de períodos de depreciação restantes (59)</span><span class="sxs-lookup"><span data-stu-id="e0b98-144">983.05Calculation: Book value (59,000 - 1,000 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="e0b98-145">A depreciação é superestimada em 16,95 (1000 - 983,05).</span><span class="sxs-lookup"><span data-stu-id="e0b98-145">Depreciation is overstated by 16.95 (1,000 - 983.05).</span></span>

## <a name="example-2-depreciation-is-understated"></a><span data-ttu-id="e0b98-146">Exemplo 2: a depreciação é subestimada</span><span class="sxs-lookup"><span data-stu-id="e0b98-146">Example 2: Depreciation is understated</span></span>
<span data-ttu-id="e0b98-147">Um ativo é configurado com uma vida útil de 5 anos e uma depreciação linear (60 períodos de depreciação).</span><span class="sxs-lookup"><span data-stu-id="e0b98-147">An asset is set up with a 5-year useful life and straight line depreciation (60 depreciation periods).</span></span> <span data-ttu-id="e0b98-148">Neste exemplo, a depreciação é subestimada.</span><span class="sxs-lookup"><span data-stu-id="e0b98-148">In this example, depreciation is understated.</span></span>
#### <a name="asset-transaction-history"></a><span data-ttu-id="e0b98-149">Histórico de transações de ativo</span><span class="sxs-lookup"><span data-stu-id="e0b98-149">Asset transaction history</span></span>

| <span data-ttu-id="e0b98-150">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-150">Date</span></span>       | <span data-ttu-id="e0b98-151">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-151">Transaction type</span></span>                                                          | <span data-ttu-id="e0b98-152">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-152">Amount</span></span>                                      |
|------------|---------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="e0b98-153">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-153">January 1</span></span>  | <span data-ttu-id="e0b98-154">Aquisição</span><span class="sxs-lookup"><span data-stu-id="e0b98-154">Acquisition</span></span>                                                               | <span data-ttu-id="e0b98-155">59.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-155">59,000.00</span></span>                                   |
| <span data-ttu-id="e0b98-156">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-156">January 1</span></span>  | <span data-ttu-id="e0b98-157">Ajuste de desvalorização</span><span class="sxs-lookup"><span data-stu-id="e0b98-157">Write-down adjustment</span></span>                                                     | <span data-ttu-id="e0b98-158">1.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-158">1,000.00</span></span>                                    |
| <span data-ttu-id="e0b98-159">31 de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-159">January 31</span></span> | <span data-ttu-id="e0b98-160">Depreciação (criada usando uma proposta para um período de depreciação)</span><span class="sxs-lookup"><span data-stu-id="e0b98-160">Depreciation (created by using a proposal for one period of depreciation)</span></span> | <span data-ttu-id="e0b98-161">Cálculo de 966,67: Valor contábil (59.000 - 1.000)/Número de períodos de depreciação restantes (60)</span><span class="sxs-lookup"><span data-stu-id="e0b98-161">966.67Calculation: Book value (59,000 - 1,000) / Number of depreciation periods remaining (60)</span></span> |

#### <a name="reversal-action"></a><span data-ttu-id="e0b98-162">Ação de reversão</span><span class="sxs-lookup"><span data-stu-id="e0b98-162">Reversal action</span></span>

| <span data-ttu-id="e0b98-163">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-163">Date</span></span>      | <span data-ttu-id="e0b98-164">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-164">Transaction type</span></span>               | <span data-ttu-id="e0b98-165">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-165">Amount</span></span>    |
|-----------|--------------------------------|-----------|
| <span data-ttu-id="e0b98-166">1º de janeiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-166">January 1</span></span> | <span data-ttu-id="e0b98-167">Reversão do ajuste de desvalorização</span><span class="sxs-lookup"><span data-stu-id="e0b98-167">Write-down adjustment reversal</span></span> | <span data-ttu-id="e0b98-168">–1.000,00</span><span class="sxs-lookup"><span data-stu-id="e0b98-168">–1,000.00</span></span> |

#### <a name="depreciation-effect"></a><span data-ttu-id="e0b98-169">Efeito da depreciação</span><span class="sxs-lookup"><span data-stu-id="e0b98-169">Depreciation effect</span></span>

| <span data-ttu-id="e0b98-170">Data</span><span class="sxs-lookup"><span data-stu-id="e0b98-170">Date</span></span>        | <span data-ttu-id="e0b98-171">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="e0b98-171">Transaction type</span></span>        | <span data-ttu-id="e0b98-172">Valor</span><span class="sxs-lookup"><span data-stu-id="e0b98-172">Amount</span></span>                                                                                       |
|-------------|-------------------------|----------------------------------------------------------------------------------------------|
| <span data-ttu-id="e0b98-173">28 de fevereiro</span><span class="sxs-lookup"><span data-stu-id="e0b98-173">February 28</span></span> | <span data-ttu-id="e0b98-174">Depreciação (proposta)</span><span class="sxs-lookup"><span data-stu-id="e0b98-174">Depreciation (proposal)</span></span> | <span data-ttu-id="e0b98-175">Cálculo de 983,62: Valor contábil (59.000 - 966,67 de depreciação)/Número de períodos de depreciação restantes (59)</span><span class="sxs-lookup"><span data-stu-id="e0b98-175">983.62Calculation: Book value (59,000 - 966.67 depreciation) / Number of depreciation periods remaining (59)</span></span> |

<span data-ttu-id="e0b98-176">A depreciação é subestimada em 16,95 (983,62 - 966,67).</span><span class="sxs-lookup"><span data-stu-id="e0b98-176">Depreciation is understated by 16.95 (983.62 - 966.67).</span></span>



<a name="additional-resources"></a><span data-ttu-id="e0b98-177">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="e0b98-177">Additional resources</span></span>
--------

[<span data-ttu-id="e0b98-178">Depreciação de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="e0b98-178">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)



