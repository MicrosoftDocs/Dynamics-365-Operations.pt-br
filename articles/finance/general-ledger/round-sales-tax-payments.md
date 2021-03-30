---
title: Pagamentos de imposto e regras de arredondamento
description: Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.
author: ShylaThompson
manager: AnnBe
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxAuthority
audience: Application User
ms.reviewer: roschlom
ms.custom: 6134
ms.assetid: 7dcd3cf5-ebdf-4a9f-806c-1296c7da0331
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7be9be728a6515bb1fc1c9bc90938a3d33ea8da8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204945"
---
# <a name="sales-tax-payments-and-rounding-rules"></a><span data-ttu-id="3d1c1-103">Pagamentos de imposto e regras de arredondamento</span><span class="sxs-lookup"><span data-stu-id="3d1c1-103">Sales tax payments and rounding rules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3d1c1-104">Este artigo explica como a configuração de regra de arredondamento funciona em Autoridades de imposto e o arredondamento do saldo de imposto durante o trabalho Liquidar e lançar imposto.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-104">This article explains how the rounding rule setup on the Sales tax authorities works and rounding the sales tax balance during the Settle and post sales tax job.</span></span>

<span data-ttu-id="3d1c1-105">Periodicamente, o imposto deve ser informado e pago às autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-105">Periodically, sales tax needs to be reported and paid to tax authorities.</span></span> <span data-ttu-id="3d1c1-106">Isso pode ser feito executando o processo de pagamento de liquidação e pós-venda na página de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-106">This can be done by running the settle and post sales tax process in the Sales tax page.</span></span> <span data-ttu-id="3d1c1-107">O imposto sobre vendas de um período será liquidado contra as contas de imposto sobre vendas e o saldo do imposto sobre vendas será lançado na conta de liquidação de imposto de vendas.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-107">Sales tax for a period will be settled against the sales tax accounts and the sales tax balance will be posted to the Sales tax settlement account.</span></span> <span data-ttu-id="3d1c1-108">O saldo do imposto, que é lançado na conta de liquidação do imposto, pode ser arredondado conforme exigido pelas autoridades fiscais para configurar uma regra de arredondamento na página Impostos.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-108">The sales tax balance, which is posted on the Sales tax settlement account, can be rounded as required by tax authorities by setting up a rounding rule on the Sales tax page.</span></span> 

<span data-ttu-id="3d1c1-109">A diferença de arredondamento é lançada na conta de arredondamento de Impostos que é selecionada no campo Contas para transações automáticas na Contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-109">The rounding difference is posted to the Sales tax rounding account that is selected in the Accounts for automatic transactions field in the General ledger.</span></span>

<span data-ttu-id="3d1c1-110">O exemplo a seguir ilustra como funciona a regra de arredondamento na autoridade de impostos.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-110">The below example illustrates how the rounding rule on Sales tax authority works.</span></span>

## <a name="examples"></a><span data-ttu-id="3d1c1-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3d1c1-111">Examples</span></span>

<span data-ttu-id="3d1c1-112">O imposto total para um período mostra um saldo de crédito de -98.765,43.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-112">The total sales tax for a period shows a credit balance of -98,765.43.</span></span> <span data-ttu-id="3d1c1-113">A entidade legal coletou mais imposto do que pagou.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-113">The legal entity collected more sales taxes than it paid.</span></span> <span data-ttu-id="3d1c1-114">Portanto, a entidade legal deve dinheiro à autoridade fiscal.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-114">Therefore, the legal entity owes money to the tax authority.</span></span> 

<span data-ttu-id="3d1c1-115">A entidade legal quer usar um método de arredondamento que arredonda para o valor mais perto de 1,00.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-115">The legal entity wants to use a rounding method that rounds the balance to the nearest 1.00.</span></span> <span data-ttu-id="3d1c1-116">O usuário responsável pela contabilização do imposto conclua as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-116">The user who is responsible for sales tax accounting performs the following steps.</span></span>

1. <span data-ttu-id="3d1c1-117">Clique em **Imposto** > **Impostos indiretos** > **Imposto** > **Autoridades do imposto**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-117">Click **Tax** > **Indirect taxes** > **Sales tax** > **Sales tax authorities**.</span></span>
2. <span data-ttu-id="3d1c1-118">Na FastTab **Geral**, no campo **Forma de arredondamento**, selecione **Normal**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-118">On the **General** FastTab, in the **Rounding form** field, select **Normal**.</span></span>
3. <span data-ttu-id="3d1c1-119">No campo **Arredondamento**, digite 1,00.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-119">In the **Round-off** field, enter 1.00.</span></span>
4. <span data-ttu-id="3d1c1-120">Na época de pagar os impostos à autoridade fiscal, acesse **Imposto** > **Declarações** > **Imposto** > **Liquidar e lançar imposto**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-120">When it is time to pay the sales taxes to the tax authority, go to **Tax** > **Declarations** > **Sales tax** > **Settle and post sale tax**.</span></span> <span data-ttu-id="3d1c1-121">Na conta de liquidação do imposto, você pode verificar se o valor da obrigação fiscal de **98.765,43** foi arredondado para **98.765**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-121">On the sales tax settlement account, you can see that the tax liability amount of **98,765.43** is rounded to **98,765**.</span></span>

<span data-ttu-id="3d1c1-122">A tabela a seguir mostra como um valor 98.765,43 é arredondado usando cada método de arredondamento que está disponível no campo **Forma de arredondamento** na página **Autoridades do imposto**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-122">The following table shows how an amount of 98,765.43 is rounded by using each rounding method that is available in the **Rounding form** field in the **Sales tax authorities** page.</span></span>

> [!NOTE]                                                                                  
> <span data-ttu-id="3d1c1-123">Se o valor de arredondamento for definido como 0,00:</span><span class="sxs-lookup"><span data-stu-id="3d1c1-123">If the round-off value is set as 0.00, then:</span></span>
>
> - <span data-ttu-id="3d1c1-124">No arredondamentos normal, o comportamento de arredondamento é o mesmo aplicado em **Arredondamento = 0,01**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-124">For normal rounding, the rounding behavior is the same as for **Round-off = 0.01**.</span></span>
> - <span data-ttu-id="3d1c1-125">Nas **Opções da forma de arredondamento**, **Para baixo**, **Arredondamento** e **Vantagem própria**, o comportamento é o mesmo que o aplicado em **Arredondamento = 1,00**.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-125">For the **Rounding form options**, **Downward**, **Rounding-up**, and **Own advantage**, the behavior is the same as for **Round-off = 1.00**.</span></span>

| <span data-ttu-id="3d1c1-126">Opção da forma de arredondamento</span><span class="sxs-lookup"><span data-stu-id="3d1c1-126">Rounding form option</span></span>                | <span data-ttu-id="3d1c1-127">Valor de arredondamento = 0,01</span><span class="sxs-lookup"><span data-stu-id="3d1c1-127">Round-off value = 0.01</span></span> | <span data-ttu-id="3d1c1-128">Valor de arredondamento = 0,10</span><span class="sxs-lookup"><span data-stu-id="3d1c1-128">Round-off value = 0.10</span></span> | <span data-ttu-id="3d1c1-129">Valor de arredondamento = 1,00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-129">Round-off value = 1.00</span></span> | <span data-ttu-id="3d1c1-130">Valor de arredondamento = 100,00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-130">Round-off value = 100.00</span></span> | <span data-ttu-id="3d1c1-131">Valor de arredondamento = 0,00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-131">Round-off value = 0.00</span></span>   |
|-------------------------------------|------------------------|------------------------|------------------------|--------------------------|--------------------------|
| <span data-ttu-id="3d1c1-132">Normal</span><span class="sxs-lookup"><span data-stu-id="3d1c1-132">Normal</span></span>                              | <span data-ttu-id="3d1c1-133">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-133">98,765.43</span></span>              | <span data-ttu-id="3d1c1-134">98,765.40</span><span class="sxs-lookup"><span data-stu-id="3d1c1-134">98,765.40</span></span>              | <span data-ttu-id="3d1c1-135">98,765.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-135">98,765.00</span></span>              | <span data-ttu-id="3d1c1-136">98,800.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-136">98,800.00</span></span>                | <span data-ttu-id="3d1c1-137">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-137">98,765.43</span></span>                |
| <span data-ttu-id="3d1c1-138">Para baixo</span><span class="sxs-lookup"><span data-stu-id="3d1c1-138">Downward</span></span>                            | <span data-ttu-id="3d1c1-139">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-139">98,765.43</span></span>              | <span data-ttu-id="3d1c1-140">98,765.40</span><span class="sxs-lookup"><span data-stu-id="3d1c1-140">98,765.40</span></span>              | <span data-ttu-id="3d1c1-141">98,765.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-141">98,765.00</span></span>              | <span data-ttu-id="3d1c1-142">98,700.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-142">98,700.00</span></span>                | <span data-ttu-id="3d1c1-143">98,765.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-143">98,765.00</span></span>                |
| <span data-ttu-id="3d1c1-144">Arredondamento</span><span class="sxs-lookup"><span data-stu-id="3d1c1-144">Rounding-up</span></span>                         | <span data-ttu-id="3d1c1-145">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-145">98,765.43</span></span>              | <span data-ttu-id="3d1c1-146">98,765.50</span><span class="sxs-lookup"><span data-stu-id="3d1c1-146">98,765.50</span></span>              | <span data-ttu-id="3d1c1-147">98,766.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-147">98,766.00</span></span>              | <span data-ttu-id="3d1c1-148">98,800.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-148">98,800.00</span></span>                | <span data-ttu-id="3d1c1-149">98,766.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-149">98,766.00</span></span>                |
| <span data-ttu-id="3d1c1-150">Vantagem própria, para um saldo de crédito</span><span class="sxs-lookup"><span data-stu-id="3d1c1-150">Own advantage, for a credit balance</span></span> | <span data-ttu-id="3d1c1-151">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-151">98,765.43</span></span>              | <span data-ttu-id="3d1c1-152">98,765.40</span><span class="sxs-lookup"><span data-stu-id="3d1c1-152">98,765.40</span></span>              | <span data-ttu-id="3d1c1-153">98,765.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-153">98,765.00</span></span>              | <span data-ttu-id="3d1c1-154">98,700.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-154">98,700.00</span></span>                | <span data-ttu-id="3d1c1-155">98,765.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-155">98,765.00</span></span>                |
| <span data-ttu-id="3d1c1-156">Vantagem própria, para um saldo de débito</span><span class="sxs-lookup"><span data-stu-id="3d1c1-156">Own advantage, for a debit balance</span></span>  | <span data-ttu-id="3d1c1-157">98,765.43</span><span class="sxs-lookup"><span data-stu-id="3d1c1-157">98,765.43</span></span>              | <span data-ttu-id="3d1c1-158">98,765.50</span><span class="sxs-lookup"><span data-stu-id="3d1c1-158">98,765.50</span></span>              | <span data-ttu-id="3d1c1-159">98,766.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-159">98,766.00</span></span>              | <span data-ttu-id="3d1c1-160">98,800.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-160">98,800.00</span></span>                | <span data-ttu-id="3d1c1-161">98,766.00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-161">98,766.00</span></span>                |

### <a name="normal-round-and-round-precision-is-001"></a><span data-ttu-id="3d1c1-162">Arredondamento normal, e a precisão do arredondamento é de 0,01</span><span class="sxs-lookup"><span data-stu-id="3d1c1-162">Normal round, and round precision is 0.01</span></span>

<table>
  <tr>
    <td><span data-ttu-id="3d1c1-163">Arredondamento</span><span class="sxs-lookup"><span data-stu-id="3d1c1-163">Rounding</span></span>
    </td>
    <td><span data-ttu-id="3d1c1-164">Processo de cálculo</span><span class="sxs-lookup"><span data-stu-id="3d1c1-164">Calculation process</span></span>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3d1c1-165">arredondar (1,015, 0,01) = 1,02</span><span class="sxs-lookup"><span data-stu-id="3d1c1-165">round(1.015, 0.01) = 1.02</span></span>
    </td>
    <td>
      <ol>
        <li><span data-ttu-id="3d1c1-166">arredondar (1,015 / 0,01, 0) = arredondar (101,5, 0) = 102</span><span class="sxs-lookup"><span data-stu-id="3d1c1-166">round(1.015 / 0.01, 0) = round(101.5, 0) = 102</span></span>
        </li>
        <li><span data-ttu-id="3d1c1-167">102 \* 0,01 = 1,02</span><span class="sxs-lookup"><span data-stu-id="3d1c1-167">102 \* 0.01 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3d1c1-168">arredondar (1,014, 0,01) = 1,01</span><span class="sxs-lookup"><span data-stu-id="3d1c1-168">round(1.014, 0.01) = 1.01</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3d1c1-169">arredondar (1,014 / 0,01, 0) = arredondar (101,4, 0) = 101</span><span class="sxs-lookup"><span data-stu-id="3d1c1-169">round(1.014 / 0.01, 0) = round(101.4, 0) = 101</span></span>
        </li>
        <li><span data-ttu-id="3d1c1-170">101 \* 0,01 = 1,01</span><span class="sxs-lookup"><span data-stu-id="3d1c1-170">101 \* 0.01 = 1.01</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3d1c1-171">arredondar (1,011, 0,02) = 1,02</span><span class="sxs-lookup"><span data-stu-id="3d1c1-171">round(1.011, 0.02) = 1.02</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3d1c1-172">arredondar (1,011 / 0,02, 0) = arredondar (50,55, 0) = 51</span><span class="sxs-lookup"><span data-stu-id="3d1c1-172">round(1.011 / 0.02, 0) = round(50.55, 0) = 51</span></span>
        </li>
        <li><span data-ttu-id="3d1c1-173">51 \* 0,02 = 1,02</span><span class="sxs-lookup"><span data-stu-id="3d1c1-173">51 \* 0.02 = 1.02</span></span>
        </li>
      </ol>
    </td>
  </tr>
    <tr>
    <td><span data-ttu-id="3d1c1-174">arredondar (1,009, 0,02) = 1,00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-174">round(1.009, 0.02) = 1.00</span></span>
    </td>
    <td> <ol>
        <li><span data-ttu-id="3d1c1-175">arredondar (1,009 / 0,02, 0) = arredondar (50,45, 0) = 50</span><span class="sxs-lookup"><span data-stu-id="3d1c1-175">round(1.009 / 0.02, 0) = round(50.45, 0) = 50</span></span>
        </li>
        <li><span data-ttu-id="3d1c1-176">50 \* 0,02 = 1,00</span><span class="sxs-lookup"><span data-stu-id="3d1c1-176">50 \* 0.02 = 1.00</span></span>
        </li>
      </ol>
    </td>
  </tr>
</table>

> [!NOTE]                                                                                  
> <span data-ttu-id="3d1c1-177">Se você selecionar Vantagem própria, o arredondamento será sempre em benefício da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="3d1c1-177">If you select Own advantage, the rounding is always to the advantage of the legal entity.</span></span> 

<span data-ttu-id="3d1c1-178">Para obter mais informações, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="3d1c1-178">For more information, see the following topics:</span></span>
- [<span data-ttu-id="3d1c1-179">Visão geral de imposto</span><span class="sxs-lookup"><span data-stu-id="3d1c1-179">Sales tax overview</span></span>](indirect-taxes-overview.md)
- [<span data-ttu-id="3d1c1-180">Criar um pagamento de imposto</span><span class="sxs-lookup"><span data-stu-id="3d1c1-180">Create a sales tax payment</span></span>](tasks/create-sales-tax-payment.md)
- [<span data-ttu-id="3d1c1-181">Criar transações de imposto em documentos</span><span class="sxs-lookup"><span data-stu-id="3d1c1-181">Create sales tax transactions on documents</span></span>](tasks/create-sales-tax-transactions-documents.md)
- [<span data-ttu-id="3d1c1-182">Exibir transações de imposto lançadas</span><span class="sxs-lookup"><span data-stu-id="3d1c1-182">View posted sales tax transactions</span></span>](tasks/view-posted-sales-tax-transactions.md)
- [<span data-ttu-id="3d1c1-183">Função round</span><span class="sxs-lookup"><span data-stu-id="3d1c1-183">round Function</span></span>](https://msdn.microsoft.com/library/aa850656.aspx)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]