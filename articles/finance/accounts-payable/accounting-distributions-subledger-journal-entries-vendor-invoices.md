---
title: Distribuições contábeis e entradas no diário para faturas de fornecedor
description: As distribuições contábeis são usadas para definir como um valor será contabilizado, por exemplo, como a receita, os impostos ou os encargos serão contabilizados em uma fatura de fornecedor. Cada valor a ser contabilizado quando a fatura de fornecedor é lançada no diário terá uma ou várias distribuições contábeis.
author: abruer
ms.date: 08/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendEditInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 26891
ms.assetid: 93dc608a-b5b4-4ec3-83c2-618e3d80a583
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 953069dfd39843d39cc92d99318f02819dc31ed0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820975"
---
# <a name="accounting-distributions-and-journal-entries-for-vendor-invoices"></a><span data-ttu-id="5f7eb-104">Distribuições contábeis e entradas no diário para faturas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5f7eb-104">Accounting distributions and journal entries for vendor invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5f7eb-105">As distribuições contábeis são usadas para definir como um valor será contabilizado, por exemplo, como a receita, os impostos ou os encargos serão contabilizados em uma fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-105">Accounting distributions are used to define how an amount will be accounted for, such as how the expense, tax, or charges will be accounted for on a vendor invoice.</span></span> <span data-ttu-id="5f7eb-106">Cada valor a ser contabilizado quando a fatura de fornecedor é lançada no diário terá uma ou várias distribuições contábeis.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-106">Every amount that must be accounted for when the vendor invoice is journalized will have one or more accounting distributions.</span></span> 

<a name="accounting-distributions"></a><span data-ttu-id="5f7eb-107">Distribuições contábeis</span><span class="sxs-lookup"><span data-stu-id="5f7eb-107">Accounting distributions</span></span> 
-------------------------

<span data-ttu-id="5f7eb-108">Você pode usar os botões a seguir na página Fatura de fornecedor para exibir e, possivelmente, modificar as distribuições contábeis para cada valor da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-108">You can use the following buttons in the Vendor invoice page to view, and possibly modify, the accounting distributions for each amount on the vendor invoice.</span></span>
-   <span data-ttu-id="5f7eb-109">**Distribuir valores** – Exibir e modificar as distribuições contábeis para uma linha individual e todas as linhas filho, como impostos ou encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-109">**Distribute amounts** – View and modify the accounting distributions for an individual line and any child lines, such as taxes or charges.</span></span> <span data-ttu-id="5f7eb-110">Também é possível exibir e modificar as distribuições contábeis para a linha filho diretamente da página Transações de imposto ou Transações de encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-110">You can also view and modify the accounting distributions for the child line directly from the Sales tax transactions page or the Charges transactions page.</span></span>
    -   <span data-ttu-id="5f7eb-111">Modifique valores do cabeçalho da fatura de fornecedor, como encargos ou valores de arredondamento de moeda.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-111">Modify vendor invoice header amounts, such as charges or currency rounding amounts.</span></span>
    -   <span data-ttu-id="5f7eb-112">Modifique valores da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-112">Modify vendor invoice line amounts.</span></span>
-   <span data-ttu-id="5f7eb-113">**Exibir distribuições** – Exibir as distribuições contábeis para todas as linhas do documento.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-113">**View distributions** – View the accounting distributions for all lines on the document.</span></span> <span data-ttu-id="5f7eb-114">Você não pode alterar as distribuições contábeis nesse modo de exibição.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-114">You cannot modify the accounting distributions from this view.</span></span>
    -   <span data-ttu-id="5f7eb-115">Exibir valores de cabeçalho e de linha.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-115">View header and line amounts.</span></span>

<span data-ttu-id="5f7eb-116">Se a fatura de fornecedor fizer referência a uma ordem de compra, você poderá dividir e alterar as distribuições contábeis para as linhas que contenham um item que não esteja em estoque.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-116">If the vendor invoice references a purchase order, you can split and modify the accounting distributions for lines that contain an item that is not stocked.</span></span> <span data-ttu-id="5f7eb-117">Se a linha da fatura de fornecedor não fizer referência a uma linha da ordem de compra, também será possível excluir uma distribuição contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-117">If the vendor invoice line does not reference a purchase order line, you can also delete an accounting distribution.</span></span> <span data-ttu-id="5f7eb-118">Não é possível dividir nem excluir linhas de encargos, impostos e descontos de linha.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-118">You cannot split or delete lines for charges, taxes, and line discounts.</span></span> <span data-ttu-id="5f7eb-119">Você pode alterar a conta contábil, mas não pode alterar os valores nem as porcentagens.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-119">You can modify the ledger account, but you cannot change the amounts or percentages.</span></span>
> [!NOTE]                                                                                                                                 
> <span data-ttu-id="5f7eb-120">Se a linha pai contém um item que não está em estoque e as distribuições contábeis são divididas, a linha filho será dividida automaticamente para corresponder às dimensões financeiras da linha pai.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-120">If the parent line contains an item that is not stocked and the accounting distributions are split, the child line will be split automatically to match the financial dimensions of the parent line.</span></span> <span data-ttu-id="5f7eb-121">As distribuições contábeis para a linha filho não podem ser divididas ou excluídas, mas dependendo da configuração da linha filho, é possível modificar a conta contábil das distribuições contábeis da linha filho.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-121">The accounting distributions for the child line cannot be additionally split or deleted, but depending on the setup of the child line, you might be able to modify the ledger account for the accounting distributions of the child line.</span></span>

## <a name="distributing-amounts"></a><span data-ttu-id="5f7eb-122">Valores de distribuição</span><span class="sxs-lookup"><span data-stu-id="5f7eb-122">Distributing amounts</span></span>
<span data-ttu-id="5f7eb-123">Quando você insere uma fatura de fornecedor, cada valor é distribuído da forma a seguir.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-123">When you enter a vendor invoice, each amount will be distributed as follows.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f7eb-124">Tipo da linha da fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5f7eb-124">Type of vendor invoice line</span></span></th>
<th><span data-ttu-id="5f7eb-125">Ordem de prioridade que determina de onde a conta principal é exibida</span><span class="sxs-lookup"><span data-stu-id="5f7eb-125">Order of priority that determines where the main account is displayed from</span></span></th>
<th><span data-ttu-id="5f7eb-126">Ordem de prioridade que determina qual dimensão financeira padrão será exibida</span><span class="sxs-lookup"><span data-stu-id="5f7eb-126">Order of priority that determines which default financial dimension is displayed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5f7eb-127">Produto em estoque.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-127">Stocked product</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-128">A distribuição contábil para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-128">The accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-129">O campo Conta principal quando Despesa de compra para produto for selecionada na página Lançamento.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-129">The Main account field when Purchase expenditure for product is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-130">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-130">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-131">Use os valores de dimensão financeira padrão na fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-131">Use the default financial dimension values on the vendor invoice.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-132">Uma categoria de compras ou um produto que não está em estoque</span><span class="sxs-lookup"><span data-stu-id="5f7eb-132">A procurement category or a product that is not stocked</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-133">A distribuição contábil da linha da ordem de compra, se a linha da fatura de fornecedor fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-133">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-134">O campo Conta principal quando Despesas de compra para despesa for selecionada na página Lançamento.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-134">The Main account field when Purchase expenditure for expense is selected in the Posting page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-135">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-135">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-136">Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-136">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="5f7eb-137">Use os valores de dimensão financeira padrão na fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-137">Use the default financial dimension values on the vendor invoice.</span></span></li>
<li><span data-ttu-id="5f7eb-138">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-138">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-139">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-139">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5f7eb-140">Ativo fixo</span><span class="sxs-lookup"><span data-stu-id="5f7eb-140">Fixed asset</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-141">A distribuição contábil da linha da ordem de compra, se a linha da fatura de fornecedor fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-141">The accounting distribution for the purchase order line, if the vendor invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-142">Se Aquisição for selecionada no campo Tipo de transação no formulário Fatura de fornecedor, no campo Conta principal, quando Aquisição for selecionada na página Perfis de lançamentos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-142">If Acquisition is selected in the Transaction type field in the Vendor invoice form, the Main account field when Acquisition is selected in the Fixed asset posting profiles page.</span></span></li>
<li><span data-ttu-id="5f7eb-143">Se Ajuste de aquisição for selecionado no campo Tipo de transação, no campo Conta principal, quando ajuste de Aquisição for selecionado na página Perfis de lançamentos de ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-143">If Acquisition adjustment is selected in the Transaction type field, the Main account field when Acquisition adjustment is selected in the Fixed asset posting profiles page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-144">Use a distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-144">Use the account distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-145">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-145">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-146">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-146">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-147">Projeto definido na linha da fatura de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5f7eb-147">Project defined on the vendor invoice line</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-148">A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-148">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-149">Se o Saldo for selecionado no campo Lançar custos - Item na página Grupos de projeto, no campo Conta principal, quando Custo for selecionado na página Configuração de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-149">If Balance is selected in the Post costs - item field in the Project groups page, the Main account field when Cost is selected in the Ledger posting setup page.</span></span></li>
<li><span data-ttu-id="5f7eb-150">Se Lucros e perdas for selecionado no campo Lançar custos - Item na página Grupos de projeto, no campo Conta principal quando Custo - item for selecionado na página Configuração de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-150">If Profit and loss is selected in the Post costs - item field in the Project groups page, the Main account field when Cost - item is selected in the Ledger posting setup page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-151">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-151">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5f7eb-152">Desconto de linha</span><span class="sxs-lookup"><span data-stu-id="5f7eb-152">Line discount</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-153">A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-153">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-154">O campo Conta principal quando Desconto for selecionado na página Lançamento.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-154">The Main account field when Discount is selected in the Posting page.</span></span></li>
<li><span data-ttu-id="5f7eb-155">Se uma conta principal para um desconto não for definida no perfil de lançamentos, a distribuição contábil do preço bruto da linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-155">If a main account for a discount is not defined on the posting profile, the accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-156">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição contábil para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-156">If the invoice line references a purchase order line, use the accounting distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-157">Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-157">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-158">Use os valores de dimensões financeiras para a linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-158">Use the financial dimension values for the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-159">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-159">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-160">Encargo de compra, que é inserido na guia Preço e desconto da linha da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="5f7eb-160">Purchase charge, which is entered on the Price and discount tab of the purchase order line</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-161">A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-161">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-162">A distribuição contábil de preço bruto da linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-162">The accounting distribution of the extended price on the purchase order line.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-163">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-163">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-164">Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-164">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5f7eb-165">Encargo da linha</span><span class="sxs-lookup"><span data-stu-id="5f7eb-165">Line charge</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-166">A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-166">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-167">Se a conta contábil for selecionada no campo Tipo de débito no formulário Código de encargos, no campo da Conta de débito na página Código de encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-167">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="5f7eb-168">Se Item estiver selecionado no campo Tipo de débito no formulário Código de encargos, a distribuição contábil para o preço bruto na linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-168">If Item is selected in the debit Type field in the Charges code form, the accounting distribution for the extended price on the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-169">Se Cliente/Fornecedor for selecionado no campo Tipo de débito no formulário Código de encargos, no campo da Conta de crédito na página Código de encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-169">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-170">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-170">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-171">Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-171">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-172">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-172">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-173">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-173">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-174">Impostos, com a seguinte condição:</span><span class="sxs-lookup"><span data-stu-id="5f7eb-174">Tax, with the following condition:</span></span>
<ul>
<li><span data-ttu-id="5f7eb-175">A opção de regras de tributação dos EUA é selecionada na página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-175">The Apply U.S. taxation rules option is selected in the General ledger parameters page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="5f7eb-176">A distribuição contábil para a linha da ordem de compra, se a linha da fatura fizer referência a uma linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-176">The accounting distribution for the purchase order line, if the invoice line references a purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-177">A distribuição contábil do preço bruto ou encargo.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-177">The accounting distribution of the extended price or charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-178">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-178">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-179">Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-179">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-180">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-180">Use the financial dimension values from the vendor invoice line.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5f7eb-181">Impostos, com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="5f7eb-181">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="5f7eb-182">A opção de regras de tributação dos EUA é desmarcada na página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-182">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="5f7eb-183">O campo Imposto sobre o uso para o grupo de impostos está desmarcado na página dos Grupos de impostos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-183">The Use tax field for the sales tax group is cleared in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="5f7eb-184">Se o valor do imposto é recuperável, o campo Imposto a receber na página Grupos de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-184">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="5f7eb-185">Se o valor do imposto não for recuperável, o preço bruto ou a distribuição contábil do encargo.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-185">If the tax amount is not recoverable, the extended price or the accounting distribution for the charge.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-186">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-186">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-187">Use as dimensões financeiras do preço bruto ou as distribuições contábeis para o encargo na linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-187">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-188">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-188">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-189">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-189">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-190">Impostos, com as seguintes condições:</span><span class="sxs-lookup"><span data-stu-id="5f7eb-190">Tax, with the following conditions:</span></span>
<ul>
<li><span data-ttu-id="5f7eb-191">A opção de regras de tributação dos EUA é desmarcada na página Parâmetros da contabilidade.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-191">The Apply U.S. taxation rules option is cleared in the General ledger parameters page.</span></span></li>
<li><span data-ttu-id="5f7eb-192">O campo Imposto sobre o uso para o grupo de impostos é selecionado na página Grupos de impostos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-192">The Use tax field for the sales tax group is selected in the Sales tax groups page.</span></span></li>
</ul></td>
<td><ol>
<li><span data-ttu-id="5f7eb-193">Se o valor do imposto é recuperável, o campo Imposto a receber na página Grupos de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-193">If the tax amount is recoverable, the Sales tax receivable field in the Ledger posting groups page.</span></span></li>
<li><span data-ttu-id="5f7eb-194">Se o valor do imposto não for recuperável, o campo Despesas de imposto sobre o uso na página Grupos de lançamento contábil.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-194">If the tax amount is not recoverable, the Use tax expense field in the Ledger posting groups page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-195">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-195">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-196">Use as dimensões financeiras do preço bruto ou as distribuições contábeis para o encargo na linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-196">Use the financial dimensions from the extended price or the accounting distributions for the charge on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-197">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-197">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-198">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-198">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5f7eb-199">Encargo de cabeçalho</span><span class="sxs-lookup"><span data-stu-id="5f7eb-199">Header charge</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-200">Se a conta contábil for selecionada no campo Tipo de débito no formulário Código de encargos, no campo da Conta de débito na página Código de encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-200">If Ledger account is selected in the debit Type field in the Charges code form, the debit Account field in the Charges code page.</span></span></li>
<li><span data-ttu-id="5f7eb-201">Se Cliente/Fornecedor for selecionado no campo Tipo de débito no formulário Código de encargos, no campo da Conta de crédito na página Código de encargos.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-201">If Customer/Vendor is selected in the debit Type field in the Charges code form, the credit Account field in the Charges code page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-202">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-202">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-203">Se a conta principal é uma conta de alocação, use o valor padrão de definição da conta de alocação.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-203">If the main account is an allocation account, use the default value from the allocation account definition.</span></span></li>
<li><span data-ttu-id="5f7eb-204">Use os valores do modelo padrão de dimensão financeira do cabeçalho da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-204">Use the financial dimension default template values from the vendor invoice header.</span></span></li>
<li><span data-ttu-id="5f7eb-205">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-205">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-206">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-206">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5f7eb-207">Desconto do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="5f7eb-207">Header discount</span></span></td>
<td><ol>
<li><span data-ttu-id="5f7eb-208">O campo Conta principal para o Tipo de lançamento do desconto da fatura de fornecedor na página Contas para transações automáticas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-208">The Main account field for the Vendor invoice discount posting type in the Accounts for automatic transactions page.</span></span></li>
</ol></td>
<td><ol>
<li><span data-ttu-id="5f7eb-209">Se a linha da fatura fizer referência a uma linha da ordem de compra, use a distribuição da conta para a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-209">If the invoice line references a purchase order line, use the account distribution for the purchase order line.</span></span></li>
<li><span data-ttu-id="5f7eb-210">Use as dimensões financeiras das distribuições contábeis para o preço bruto da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-210">Use the financial dimensions from the accounting distributions for the extended price on the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-211">Use os valores de dimensões financeiras da linha da fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-211">Use the financial dimension values from the vendor invoice line.</span></span></li>
<li><span data-ttu-id="5f7eb-212">Use os valores de dimensão financeira padrão da conta principal na página Plano de contas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-212">Use the default financial dimension values from the main account in the Chart of Accounts page.</span></span></li>
</ol></td>
</tr>
</tbody>
</table>


<a name="distributing-taxes"></a><span data-ttu-id="5f7eb-213">Impostos de distribuição</span><span class="sxs-lookup"><span data-stu-id="5f7eb-213">Distributing taxes</span></span>
------------------

<span data-ttu-id="5f7eb-214">As distribuições contábeis de impostos não podem ser criadas até que os impostos sejam calculados.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-214">Accounting distributions for taxes cannot be created until taxes are calculated.</span></span> <span data-ttu-id="5f7eb-215">Para calcular impostos, você deve concluir uma das seguintes tarefas na página Fatura de fornecedor:</span><span class="sxs-lookup"><span data-stu-id="5f7eb-215">To calculate sales taxes, you must complete one of the following tasks in the Vendor invoice page:</span></span>
-   <span data-ttu-id="5f7eb-216">Exibir total da fatura.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-216">View the invoice total.</span></span>
-   <span data-ttu-id="5f7eb-217">Exibir imposto.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-217">View the sales tax.</span></span>
-   <span data-ttu-id="5f7eb-218">Exibir o diário-razão auxiliar</span><span class="sxs-lookup"><span data-stu-id="5f7eb-218">View the subledger journal.</span></span>
-   <span data-ttu-id="5f7eb-219">Exiba as distribuições contábeis para a fatura de fornecedor completa.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-219">View accounting distributions for the complete vendor invoice.</span></span>
-   <span data-ttu-id="5f7eb-220">Coloque a fatura de fornecedor em espera.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-220">Place the vendor invoice on hold.</span></span>
-   <span data-ttu-id="5f7eb-221">Lance a fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-221">Post the vendor invoice.</span></span>

## <a name="subledger-journals-for-vendor-invoices"></a><span data-ttu-id="5f7eb-222">Diários-razão auxiliares para faturas de fornecedor</span><span class="sxs-lookup"><span data-stu-id="5f7eb-222">Subledger journals for vendor invoices</span></span>
<span data-ttu-id="5f7eb-223">Antes de lançar uma fatura de fornecedor, você pode exibir a entrada contábil total da fatura, incluindo débitos e créditos, para verificar se a fatura está sendo lançada nas contas corretas.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-223">Before you post a vendor invoice, you can view the full accounting entry of the invoice, which includes debits and credits, to verify that the invoice is being posted to the correct accounts.</span></span> <span data-ttu-id="5f7eb-224">Esta exibição de entrada contábil total é chamada de diário-razão auxiliar.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-224">This view of the full accounting entry is called a subledger journal.</span></span> 

<span data-ttu-id="5f7eb-225">Se a entrada no diário-razão auxiliar estiver incorreta quando você a visualizar antes de lançar a fatura de fornecedor no diário, não será possível alterá-la.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-225">If the subledger journal entry is incorrect when you preview it before you journalize the vendor invoice, you cannot modify the subledger journal entry.</span></span> <span data-ttu-id="5f7eb-226">Em vez de isso, você deve alterar as distribuições contábeis ou o perfil de lançamento.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-226">Instead, you must modify the accounting distributions or the posting profile.</span></span> <span data-ttu-id="5f7eb-227">As distribuições contábeis são usadas para definir um lado de entrada contábil, de débito ou de crédito.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-227">The accounting distributions are used to define one side of the accounting entry, the debit or the credit.</span></span> <span data-ttu-id="5f7eb-228">A entrada de conta no diário-razão auxiliar de compensação é criada por perfis de lançamento, como a conta de fornecedor ou imposto.</span><span class="sxs-lookup"><span data-stu-id="5f7eb-228">The offsetting subledger journal account entry is created by using the posting profiles, such as from the vendor account or tax.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]