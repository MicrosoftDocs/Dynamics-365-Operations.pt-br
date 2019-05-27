---
title: Pagamentos de imposto e regras de arredondamento
description: Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.
author: ShylaThompson
manager: AnnBe
ms.date: 05/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: yijialuan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1e1c1bb1c792eb79888a1df209f2eebaf14a38dd
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "1531848"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="d8e54-103">Pagamentos de imposto e regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="d8e54-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8e54-104">Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="d8e54-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="d8e54-105">Periodicamente, o imposto deve ser informado e pago às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="d8e54-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="d8e54-106">Isso pode ser feito executando o processo de pagamento de liquidação e pós-venda na página de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="d8e54-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="d8e54-107">O imposto sobre vendas de um período será liquidado contra as contas de imposto sobre vendas e o saldo do imposto sobre vendas será lançado na conta de liquidação de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="d8e54-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="d8e54-108">O saldo do imposto, que é lançado na conta de liquidação do imposto, pode ser arredondado conforme exigido pelas autoridades fiscais para configurar uma regra de arredondamento na página Impostos.</span><span class="sxs-lookup"><span data-stu-id="d8e54-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="d8e54-109">A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="d8e54-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="d8e54-110">O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.</span><span class="sxs-lookup"><span data-stu-id="d8e54-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="d8e54-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d8e54-111">Examples</span></span>

<span data-ttu-id="d8e54-112">O imposto total para um período mostra um saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="d8e54-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="d8e54-113">A entidade legal coletou mais imposto do que pagou.</span><span class="sxs-lookup"><span data-stu-id="d8e54-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="d8e54-114">Portanto, a entidade legal deve dinheiro à autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="d8e54-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="d8e54-115">A entidade legal quer usar um método de arredondamento que arredonda para o valor mais perto de 1,00.</span><span class="sxs-lookup"><span data-stu-id="d8e54-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="d8e54-116">O usuário responsável pela contabilização do imposto conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d8e54-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1.  <span data-ttu-id="d8e54-117">Clique em Imposto &gt; Impostos indiretos &gt; Imposto &gt; Autoridades do imposto</span><span class="sxs-lookup"><span data-stu-id="d8e54-117">Click Tax &gt; Indirect taxes &gt; Sales tax &gt; Sales tax authorities</span></span>
2.  <span data-ttu-id="d8e54-118">Na Guia Rápida Geral, selecione Normal no campo Forma de arredondamento.</span><span class="sxs-lookup"><span data-stu-id="d8e54-118">On the General FastTab, select Normal in the Rounding form field.</span></span>
3.  <span data-ttu-id="d8e54-119">No campo Arredondamento, digite 1,00.</span><span class="sxs-lookup"><span data-stu-id="d8e54-119">In the Round-off field, enter 1.00.</span></span>
4.  <span data-ttu-id="d8e54-120">Na época de pagar os impostos à autoridade fiscal, abra a página Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="d8e54-120">When it is time to pay the sales taxes to the tax authority, open the Settle and post sales tax page.</span></span> <span data-ttu-id="d8e54-121">(Clique em Imposto &gt; Declarações &gt; Imposto &gt; Liquidar e lançar imposto.)</span><span class="sxs-lookup"><span data-stu-id="d8e54-121">(Click Tax &gt; Declarations &gt; Sales tax &gt; Settle and post sales tax.)</span></span>
5.  <span data-ttu-id="d8e54-122">Na conta de liquidação do imposto, o valor da obrigação fiscal de 98.765.43 foi arredondado para 98.765.</span><span class="sxs-lookup"><span data-stu-id="d8e54-122">On the sales tax settlement account, the tax liability amount of 98,765.43 is rounded to 98,765.</span></span>

<span data-ttu-id="d8e54-123">A tabela a seguir mostra como um valor 98.765,43 é arredondado usando cada método de arredondamento que está disponível no campo Forma de arredondamento na página Autoridades do imposto.</span><span class="sxs-lookup"><span data-stu-id="d8e54-123">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the Rounding form field in the Sales tax authorities page.</span></span>

| <span data-ttu-id="d8e54-124">Opção da forma de arredondamento</span><span class="sxs-lookup"><span data-stu-id="d8e54-124">Rounding form option</span></span>                | <span data-ttu-id="d8e54-125">Valor de arredondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="d8e54-125">Round-off value = 0.01</span></span> | <span data-ttu-id="d8e54-126">Valor de arredondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="d8e54-126">Round-off value = 0.10</span></span> | <span data-ttu-id="d8e54-127">Valor de arredondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="d8e54-127">Round-off value = 1.00</span></span> | <span data-ttu-id="d8e54-128">Valor de arredondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="d8e54-128">Round-off value = 100.00</span></span> |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|
| <span data-ttu-id="d8e54-129">Normal</span><span class="sxs-lookup"><span data-stu-id="d8e54-129">Normal</span></span>                              | <span data-ttu-id="d8e54-130">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d8e54-130">98,765.43</span></span>              | <span data-ttu-id="d8e54-131">98,765.40</span><span class="sxs-lookup"><span data-stu-id="d8e54-131">98,765.40</span></span>              | <span data-ttu-id="d8e54-132">98,765.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-132">98,765.00</span></span>              | <span data-ttu-id="d8e54-133">98,800.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-133">98,800.00</span></span>                |
| <span data-ttu-id="d8e54-134">Para baixo</span><span class="sxs-lookup"><span data-stu-id="d8e54-134">Downward</span></span>                            | <span data-ttu-id="d8e54-135">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d8e54-135">98,765.43</span></span>              | <span data-ttu-id="d8e54-136">98,765.40</span><span class="sxs-lookup"><span data-stu-id="d8e54-136">98,765.40</span></span>              | <span data-ttu-id="d8e54-137">98,765.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-137">98,765.00</span></span>              | <span data-ttu-id="d8e54-138">98,700.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-138">98,700.00</span></span>                |
| <span data-ttu-id="d8e54-139">Arredondamento</span><span class="sxs-lookup"><span data-stu-id="d8e54-139">Rounding-up</span></span>                         | <span data-ttu-id="d8e54-140">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d8e54-140">98,765.43</span></span>              | <span data-ttu-id="d8e54-141">98,765.50</span><span class="sxs-lookup"><span data-stu-id="d8e54-141">98,765.50</span></span>              | <span data-ttu-id="d8e54-142">98,766.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-142">98,766.00</span></span>              | <span data-ttu-id="d8e54-143">98,800.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-143">98,800.00</span></span>                |
| <span data-ttu-id="d8e54-144">Vantagem própria, para um saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="d8e54-144">Own advantage, for a credit balance</span></span> | <span data-ttu-id="d8e54-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d8e54-145">98,765.43</span></span>              | <span data-ttu-id="d8e54-146">98,765.40</span><span class="sxs-lookup"><span data-stu-id="d8e54-146">98,765.40</span></span>              | <span data-ttu-id="d8e54-147">98,765.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-147">98,765.00</span></span>              | <span data-ttu-id="d8e54-148">98,700.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-148">98,700.00</span></span>                |
| <span data-ttu-id="d8e54-149">Vantagem própria, para um saldo de débito</span><span class="sxs-lookup"><span data-stu-id="d8e54-149">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="d8e54-150">98,765.43</span><span class="sxs-lookup"><span data-stu-id="d8e54-150">98,765.43</span></span>              | <span data-ttu-id="d8e54-151">98,765.50</span><span class="sxs-lookup"><span data-stu-id="d8e54-151">98,765.50</span></span>              | <span data-ttu-id="d8e54-152">98,766.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-152">98,766.00</span></span>              | <span data-ttu-id="d8e54-153">98,800.00</span><span class="sxs-lookup"><span data-stu-id="d8e54-153">98,800.00</span></span>                |


### <a name="no-rounding-at-all-since-the-round-off-is-000"></a><span data-ttu-id="d8e54-154">Sem arredondamento, pois o arredondamento é 0,00</span><span class="sxs-lookup"><span data-stu-id="d8e54-154">No rounding at all, since the round-off is 0.00</span></span>

<span data-ttu-id="d8e54-155">arredondar (1,0151, 0,00) = 1,0151 (1,0149, 0,00) = 1,0149</span><span class="sxs-lookup"><span data-stu-id="d8e54-155">round(1.0151, 0.00) = 1.0151 round(1.0149, 0.00) = 1.0149</span></span>

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="d8e54-156">Arredondamento normal, e a precisão do arredondamento é de 0,01</span><span class="sxs-lookup"><span data-stu-id="d8e54-156">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="d8e54-157">Arredondamento</span><span class="sxs-lookup"><span data-stu-id="d8e54-157">Rounding</span></span>
    </td>
    <td><span data-ttu-id="d8e54-158">Processo de cálculo</span><span class="sxs-lookup"><span data-stu-id="d8e54-158">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d8e54-159">arredondar (1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d8e54-159">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="d8e54-160">arredondar (1,015 / 0,01, 0) = arredondar (101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="d8e54-160">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="d8e54-161">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d8e54-161">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d8e54-162">arredondar (1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="d8e54-162">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d8e54-163">arredondar (1,014 / 0,01, 0) = arredondar (101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="d8e54-163">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="d8e54-164">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="d8e54-164">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d8e54-165">arredondar (1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="d8e54-165">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d8e54-166">arredondar (1,011 / 0,02, 0) = arredondar (50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="d8e54-166">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="d8e54-167">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="d8e54-167">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="d8e54-168">arredondar (1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="d8e54-168">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="d8e54-169">arredondar (1,009 / 0,02, 0) = arredondar (50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="d8e54-169">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="d8e54-170">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="d8e54-170">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="d8e54-171">Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="d8e54-171">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="d8e54-172">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d8e54-172">For more information, see the following topics:</span></span>
- [<span data-ttu-id="d8e54-173">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="d8e54-173">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="d8e54-174">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="d8e54-174">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="d8e54-175">Criar transações de vendas em documentos</span><span class="sxs-lookup"><span data-stu-id="d8e54-175">Create sales transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="d8e54-176">Exibir transações de imposto lançadas</span><span class="sxs-lookup"><span data-stu-id="d8e54-176">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="d8e54-177">Função round</span><span class="sxs-lookup"><span data-stu-id="d8e54-177">round Function</span></span>](https://msdn.microsoft.com/en-us/library/aa850656.aspx)


