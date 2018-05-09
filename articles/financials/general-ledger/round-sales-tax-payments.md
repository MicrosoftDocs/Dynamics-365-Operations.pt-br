---
title: Pagamentos de imposto e regras de arredondamento
description: "Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto."
author: twheeloc
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 6b910a1e9ea6fe5f0f9e24677175cd88948cec26
ms.contentlocale: pt-br
ms.lasthandoff: 05/08/2018

---

# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="43c06-103">Pagamentos de imposto e regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="43c06-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="43c06-104">Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="43c06-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="43c06-105">Periodicamente, o imposto deve ser informado e pago às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="43c06-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="43c06-106">Isso pode ser feito executando o processo de pagamento de liquidação e pós-venda na página de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="43c06-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="43c06-107">O imposto sobre vendas de um período será liquidado contra as contas de imposto sobre vendas e o saldo do imposto sobre vendas será lançado na conta de liquidação de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="43c06-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="43c06-108">O saldo do imposto, que é lançado na conta de liquidação do imposto, pode ser arredondado conforme exigido pelas autoridades fiscais para configurar uma regra de arredondamento na página Impostos.</span><span class="sxs-lookup"><span data-stu-id="43c06-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="43c06-109">A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="43c06-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="43c06-110">O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.</span><span class="sxs-lookup"><span data-stu-id="43c06-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

### <a name="example"></a><span data-ttu-id="43c06-111">Exemplo:</span><span class="sxs-lookup"><span data-stu-id="43c06-111">Example:</span></span>

<span data-ttu-id="43c06-112">O imposto total para um período mostra um saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="43c06-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="43c06-113">A entidade legal coletou mais imposto do que pagou.</span><span class="sxs-lookup"><span data-stu-id="43c06-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="43c06-114">Portanto, a entidade legal deve dinheiro à autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="43c06-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="43c06-115">A entidade legal quer usar um método de arredondamento que arredonda para o valor mais perto de 1,00.</span><span class="sxs-lookup"><span data-stu-id="43c06-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="43c06-116">O usuário responsável pela contabilização do imposto conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="43c06-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="43c06-117">Clique em Imposto &gt; Impostos indiretos &gt; Imposto &gt; Autoridades do imposto</span><span class="sxs-lookup"><span data-stu-id="43c06-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="43c06-118">Na Guia Rápida Geral, selecione Normal no campo Forma de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="43c06-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="43c06-119">No campo Arredondamento, digite 1,00.</span><span class="sxs-lookup"><span data-stu-id="43c06-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="43c06-120">Na época de pagar os impostos à autoridade fiscal, abra a página Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="43c06-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="43c06-121">(Clique em Imposto &gt; Declarações &gt; Imposto &gt; Liquidar e lançar imposto.)</span><span class="sxs-lookup"><span data-stu-id="43c06-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="43c06-122">Na conta de liquidação do imposto, o valor da obrigação fiscal de 98.765.43 foi arredondado para 98.765.</span><span class="sxs-lookup"><span data-stu-id="43c06-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="43c06-123">A tabela a seguir mostra como um valor 98.765,43 é arredondado usando cada método de arredondamento que está disponível no campo Forma de arredondamento na página Autoridades do imposto.</span><span class="sxs-lookup"><span data-stu-id="43c06-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="43c06-124">Opção da forma de arredondamento</span><span class="sxs-lookup"><span data-stu-id="43c06-124">Rounding form option</span></span>                | <span data-ttu-id="43c06-125">Valor de arredondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="43c06-125">Round-off value = 0.01</span></span> | <span data-ttu-id="43c06-126">Valor de arredondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="43c06-126">Round-off value = 0.10</span></span> | <span data-ttu-id="43c06-127">Valor de arredondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="43c06-127">Round-off value = 1.00</span></span> | <span data-ttu-id="43c06-128">Valor de arredondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="43c06-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="43c06-129">Normal</span><span class="sxs-lookup"><span data-stu-id="43c06-129">Normal</span></span>                              | <span data-ttu-id="43c06-130">98,765.43</span><span class="sxs-lookup"><span data-stu-id="43c06-130">98,765.43</span></span>              | <span data-ttu-id="43c06-131">98,765.40</span><span class="sxs-lookup"><span data-stu-id="43c06-131">98,765.40</span></span>              | <span data-ttu-id="43c06-132">98,765.00</span><span class="sxs-lookup"><span data-stu-id="43c06-132">98,765.00</span></span>              | <span data-ttu-id="43c06-133">98,800.00</span><span class="sxs-lookup"><span data-stu-id="43c06-133">98,800.00</span></span>                |
| <span data-ttu-id="43c06-134">Para baixo</span><span class="sxs-lookup"><span data-stu-id="43c06-134">Downward</span></span>                            | <span data-ttu-id="43c06-135">98,765.43</span><span class="sxs-lookup"><span data-stu-id="43c06-135">98,765.43</span></span>              | <span data-ttu-id="43c06-136">98,765.40</span><span class="sxs-lookup"><span data-stu-id="43c06-136">98,765.40</span></span>              | <span data-ttu-id="43c06-137">98,765.00</span><span class="sxs-lookup"><span data-stu-id="43c06-137">98,765.00</span></span>              | <span data-ttu-id="43c06-138">98,700.00</span><span class="sxs-lookup"><span data-stu-id="43c06-138">98,700.00</span></span>                |
| <span data-ttu-id="43c06-139">Arredondamento</span><span class="sxs-lookup"><span data-stu-id="43c06-139">Rounding-up</span></span>                         | <span data-ttu-id="43c06-140">98,765.43</span><span class="sxs-lookup"><span data-stu-id="43c06-140">98,765.43</span></span>              | <span data-ttu-id="43c06-141">98,765.50</span><span class="sxs-lookup"><span data-stu-id="43c06-141">98,765.50</span></span>              | <span data-ttu-id="43c06-142">98,766.00</span><span class="sxs-lookup"><span data-stu-id="43c06-142">98,766.00</span></span>              | <span data-ttu-id="43c06-143">98,800.00</span><span class="sxs-lookup"><span data-stu-id="43c06-143">98,800.00</span></span>                |
| <span data-ttu-id="43c06-144">Vantagem própria, para um saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="43c06-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="43c06-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="43c06-145">98,765.43</span></span>              | <span data-ttu-id="43c06-146">98,765.40</span><span class="sxs-lookup"><span data-stu-id="43c06-146">98,765.40</span></span>              | <span data-ttu-id="43c06-147">98,765.00</span><span class="sxs-lookup"><span data-stu-id="43c06-147">98,765.00</span></span>              | <span data-ttu-id="43c06-148">98,700.00</span><span class="sxs-lookup"><span data-stu-id="43c06-148">98,700.00</span></span>                |
| <span data-ttu-id="43c06-149">Vantagem própria, para um saldo de débito</span><span class="sxs-lookup"><span data-stu-id="43c06-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="43c06-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="43c06-150">98,765.43</span></span>              | <span data-ttu-id="43c06-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="43c06-151">98,765.50</span></span>              | <span data-ttu-id="43c06-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="43c06-152">98,766.00</span></span>              | <span data-ttu-id="43c06-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="43c06-153">98,800.00</span></span>                |

> [!NOTE]                                                                                  
> <span data-ttu-id="43c06-154">Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="43c06-154">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="43c06-155">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="43c06-155">For more information, see the following topics:</span></span>
- [<span data-ttu-id="43c06-156">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="43c06-156">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="43c06-157">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="43c06-157">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="43c06-158">Criar transações de vendas em documentos</span><span class="sxs-lookup"><span data-stu-id="43c06-158">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="43c06-159">Exibir transações de imposto lançadas</span><span class="sxs-lookup"><span data-stu-id="43c06-159">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)



