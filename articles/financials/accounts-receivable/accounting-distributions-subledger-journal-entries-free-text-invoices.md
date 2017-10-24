---
title: "Distribuições contábeis e entradas no diário-razão auxiliar para faturas de texto livre"
description: "As distribuições contábeis são usadas para definir como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre. Cada valor que deve ser contabilizado terá uma ou mais distribuições contábeis quando a fatura de texto livre for lançada no diário."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3141
ms.assetid: fecd17a2-d7b4-4a20-ac81-eb71abbfa9d1
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6485642d27156dfb37f9e30335369e3287f92148
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="accounting-distributions-and-subledger-journal-entries-for-free-text-invoices"></a><span data-ttu-id="ea507-104">Distribuições contábeis e entradas no diário-razão auxiliar para faturas de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-104">Accounting distributions and subledger journal entries for free text invoices</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ea507-105">As distribuições contábeis são usadas para definir como um valor será contabilizado, assim como a receita, os impostos ou os encargos serão contabilizados em uma fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-105">Accounting distributions are used to define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span> <span data-ttu-id="ea507-106">Cada valor que deve ser contabilizado terá uma ou mais distribuições contábeis quando a fatura de texto livre for lançada no diário.</span><span class="sxs-lookup"><span data-stu-id="ea507-106">Every amount that must be accounted for when the free text invoice is journalized will have one or more accounting distributions.</span></span>

<a name="accounting-distributions"></a><span data-ttu-id="ea507-107">Distribuições contábeis</span><span class="sxs-lookup"><span data-stu-id="ea507-107">Accounting distributions</span></span>
------------------------

<span data-ttu-id="ea507-108">Você pode usar os botões a seguir na página Fatura de texto livre para exibir e, possivelmente, alterar as distribuições contábeis de cada valor da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-108">You can use the following buttons in the Free text invoice page to view, and possibly change, the accounting distributions for each amount on the free text invoice.</span></span>

-   <span data-ttu-id="ea507-109">**Distribuir valores**—Exibir e modificar as distribuições contábeis para uma linha individual e todas as linhas filho, como impostos ou encargos.</span><span class="sxs-lookup"><span data-stu-id="ea507-109">**Distribute amounts**—View and change the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="ea507-110">Também é possível exibir e modificar as distribuições contábeis para a linha filho diretamente da página Transações de imposto ou Transações de encargos.</span><span class="sxs-lookup"><span data-stu-id="ea507-110">You can also view and change the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="ea507-111">Modifique os valores do cabeçalho da fatura de texto livre, como encargos ou valores de arredondamento de moeda.</span><span class="sxs-lookup"><span data-stu-id="ea507-111">Change free text invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="ea507-112">Modifique os valores da linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-112">Change free text invoice line amounts.</span></span>
-   <span data-ttu-id="ea507-113">**Exibir distribuições** - Exibir as distribuições contábeis para todas as linhas do documento.</span><span class="sxs-lookup"><span data-stu-id="ea507-113">**View distributions**—View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="ea507-114">Você não pode alterar as distribuições contábeis nesse modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="ea507-114">You can't change the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="ea507-115">Exibir valores de cabeçalho e de linha.</span><span class="sxs-lookup"><span data-stu-id="ea507-115">View header and line amounts.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="ea507-116">Valores de distribuição</span><span class="sxs-lookup"><span data-stu-id="ea507-116">Distributing amounts</span></span>
<span data-ttu-id="ea507-117">Quando você insere uma fatura de texto livre, cada valor será distribuído como a seguir.</span><span class="sxs-lookup"><span data-stu-id="ea507-117">When you enter a free text invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea507-118">Digite o valor monetário</span><span class="sxs-lookup"><span data-stu-id="ea507-118">Type of monetary amount</span></span></th>
<th><span data-ttu-id="ea507-119">Da onde a conta principal é exibida</span><span class="sxs-lookup"><span data-stu-id="ea507-119">Where the main account is displayed from</span></span></th>
<th><span data-ttu-id="ea507-120">Ordem de prioridade que determina qual dimensão financeira padrão será exibida</span><span class="sxs-lookup"><span data-stu-id="ea507-120">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ea507-121">Linha da fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-121">Free text invoice line</span></span></td>
<td><span data-ttu-id="ea507-122">A conta contábil na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-122">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="ea507-123">Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</span><span class="sxs-lookup"><span data-stu-id="ea507-123">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="ea507-124">Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-124">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-125">Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-125">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-126">Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="ea507-126">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea507-127">Linha da fatura de texto livre de uma combinação do número ativo fixo e o método de depreciação</span><span class="sxs-lookup"><span data-stu-id="ea507-127">Free text invoice line for a fixed asset number and value model combination</span></span>
<div class="alert">
<table>
<thead>
<tr class="header">
<th><span data-ttu-id="ea507-128"><strong>Nota </strong></span><span class="sxs-lookup"><span data-stu-id="ea507-128"><strong>Note</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="ea507-129">A conta principal na linha da fatura de texto livre será uma conta de alienação de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="ea507-129">The main account on the free text invoice line will be the fixed asset disposal account.</span></span></td>
</tr>
</tbody>
</table>
</div></td>
<td><span data-ttu-id="ea507-130">A conta contábil na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-130">The ledger account on the free text invoice line.</span></span></td>
<td><ol>
<li><span data-ttu-id="ea507-131">Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-131">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-132">Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="ea507-132">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea507-133">Valor do desconto da fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-133">Free text invoice discount amount</span></span></td>
<td><span data-ttu-id="ea507-134">A conta principal para descontos do cliente na página Descontos à vista.</span><span class="sxs-lookup"><span data-stu-id="ea507-134">The Main account for customer discounts field in the Cash discounts page.</span></span></td>
<td><ol>
<li><span data-ttu-id="ea507-135">Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</span><span class="sxs-lookup"><span data-stu-id="ea507-135">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="ea507-136">Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-136">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-137">Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-137">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-138">Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="ea507-138">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="ea507-139">Valor do imposto da fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-139">Free text invoice sales tax amount</span></span></td>
<td><span data-ttu-id="ea507-140">O campo Imposto a pagar na página Grupos de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="ea507-140">The Sales tax payable field in the Ledger posting groups page.</span></span></td>
<td><ol>
<li><span data-ttu-id="ea507-141">Use as dimensões financeiras definidas no valor da linha da fatura de texto livre ou em distribuições do valor da linha do encargo.</span><span class="sxs-lookup"><span data-stu-id="ea507-141">Use the financial dimensions that are defined on the free text invoice line amount or the distributions for the charge line amount.</span></span></li>
<li><span data-ttu-id="ea507-142">Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-142">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-143">Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="ea507-143">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="ea507-144">Valor da linha de encargos da fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-144">Free text invoice charge line amount</span></span></td>
<td><span data-ttu-id="ea507-145">O campo Conta de crédito na página Código de encargos.</span><span class="sxs-lookup"><span data-stu-id="ea507-145">The Credit account field in the Charges code page.</span></span></td>
<td><ol>
<li><span data-ttu-id="ea507-146">Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</span><span class="sxs-lookup"><span data-stu-id="ea507-146">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="ea507-147">Se a conta principal não é uma conta de alocação, use o modelo padrão de dimensão financeira na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-147">If the main account is not an allocation account, use the financial dimension default template on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-148">Use os valores de dimensão financeira padrão na linha da fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-148">Use the default financial dimension values on the free text invoice line.</span></span></li>
<li><span data-ttu-id="ea507-149">Use os valores de dimensão financeira padrão da conta contábil na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="ea507-149">Use the default financial dimension values from the ledger account in the Chart of accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>

## <a name="distributing-taxes"></a><span data-ttu-id="ea507-150">Impostos de distribuição</span><span class="sxs-lookup"><span data-stu-id="ea507-150">Distributing taxes</span></span>
<span data-ttu-id="ea507-151">As distribuições contábeis de impostos não podem ser criadas até que os impostos sejam calculados.</span><span class="sxs-lookup"><span data-stu-id="ea507-151">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="ea507-152">Para calcular impostos, você deve concluir uma das seguintes tarefas no formulário Fatura de texto livre:</span><span class="sxs-lookup"><span data-stu-id="ea507-152">To calculate sales taxes, you must complete one of the following tasks in the Free text invoice form:</span></span>
-   <span data-ttu-id="ea507-153">Exibir imposto.</span><span class="sxs-lookup"><span data-stu-id="ea507-153">View the sales tax.</span></span>
-   <span data-ttu-id="ea507-154">Exibir total da fatura.</span><span class="sxs-lookup"><span data-stu-id="ea507-154">View the invoice total.</span></span>
-   <span data-ttu-id="ea507-155">Exibir caixa registradora.</span><span class="sxs-lookup"><span data-stu-id="ea507-155">View the cash flow.</span></span>
-   <span data-ttu-id="ea507-156">Exibir distribuições contábeis de toda a fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="ea507-156">View accounting distributions for the whole free text invoice.</span></span>
-   <span data-ttu-id="ea507-157">Exibir o diário-razão auxiliar</span><span class="sxs-lookup"><span data-stu-id="ea507-157">View the subledger journal.</span></span>

## <a name="subledger-journals-for-free-text-invoices"></a><span data-ttu-id="ea507-158">Diário-razão auxiliar de faturas de texto livre</span><span class="sxs-lookup"><span data-stu-id="ea507-158">Subledger journals for free text invoices</span></span>
<span data-ttu-id="ea507-159">Você pode exibir a entrada contábil total da fatura antes de lançar uma fatura de texto livre, incluindo débitos e créditos, para verificar se a fatura está sendo lançada nas contas corretas.</span><span class="sxs-lookup"><span data-stu-id="ea507-159">Before you post a free text invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="ea507-160">Esta exibição de entrada contábil total é chamada de diário-razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="ea507-160">This view of the full accounting entry is called a subledger journal.</span></span> <span data-ttu-id="ea507-161">Se a entrada no diário-razão auxiliar estiver incorreta quando você exibi-la antes de lançar em diário a fatura de texto livre, não será possível alterar a entrada no diário-razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="ea507-161">If the subledger journal entry is incorrect when you preview it before you journalize the free text invoice, you can't change the subledger journal entry.</span></span> <span data-ttu-id="ea507-162">Em vez de isso, você deve alterar as distribuições contábeis ou o perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="ea507-162">Instead, you must change the accounting distributions or the posting profile.</span></span> <span data-ttu-id="ea507-163">As distribuições contábeis são usadas para definir um lado de entrada contábil, de débito ou de crédito.</span><span class="sxs-lookup"><span data-stu-id="ea507-163">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="ea507-164">A entrada de conta no diário-razão auxiliar de compensação é criada a partir dos perfis de lançamento, como a conta de cliente ou imposto.</span><span class="sxs-lookup"><span data-stu-id="ea507-164">The offsetting subledger journal account entry is created from the posting profiles, such as from the customer account or the tax.</span></span>




