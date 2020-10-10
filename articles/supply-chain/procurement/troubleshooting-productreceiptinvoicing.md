---
title: Solucionar problemas de recebimentos e faturamento de produtos
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com recebimentos e faturamento de produtos.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: d86fa3df1de13cc0e0fb94449207a326069da25b
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834316"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="3a502-103">Solucionar problemas de recebimentos e faturamento de produtos</span><span class="sxs-lookup"><span data-stu-id="3a502-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="3a502-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com recebimentos e faturamento de produtos.</span><span class="sxs-lookup"><span data-stu-id="3a502-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="3a502-105">Não consigo lançar mais de uma fatura para uma linha da ordem de compra que tem itens baseados em categoria.</span><span class="sxs-lookup"><span data-stu-id="3a502-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="3a502-106">Uma quantidade será obrigatória se você quiser lançar faturas.</span><span class="sxs-lookup"><span data-stu-id="3a502-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="3a502-107">Portanto, se a quantidade total de uma linha for faturada apenas por um valor parcial, não será possível faturar o valor restante em outra fatura.</span><span class="sxs-lookup"><span data-stu-id="3a502-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="3a502-108">Recebo uma mensagem de erro "Referência de objeto não definida" durante a confirmação da ordem de compra ou uma "Exceção lançada pelo destino de uma chamada" ocorre durante o lançamento da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="3a502-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="3a502-109">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="3a502-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="3a502-110">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="3a502-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="3a502-111">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="3a502-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="3a502-112">Não consigo consolidar vários recebimentos de produtos em uma única ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="3a502-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="3a502-113">Não é possível consolidar vários recebimentos de produtos em uma única ordem de compra, se as diferentes linhas de recebimento de produtos tiverem datas contábeis diferentes.</span><span class="sxs-lookup"><span data-stu-id="3a502-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="3a502-114">Em versões anteriores do Microsoft Dynamics 365 Supply Chain Management, a consolidação foi permitida nessa situação.</span><span class="sxs-lookup"><span data-stu-id="3a502-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="3a502-115">No entanto, a prática está sujeita a erros.</span><span class="sxs-lookup"><span data-stu-id="3a502-115">However, the practice is prone to error.</span></span> <span data-ttu-id="3a502-116">A data contábil nas linhas da ordem de compra criadas não deve diferir da data contábil nas linhas de recebimento de produtos das quais as linhas da ordem de compra foram criadas.</span><span class="sxs-lookup"><span data-stu-id="3a502-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="3a502-117">(A data contábil nas linhas da ordem de compra corresponde à data contábil no cabeçalho da ordem de compra.) Portanto, a consolidação de vários recebimentos de produtos em uma única ordem de compra não é mais permitida.</span><span class="sxs-lookup"><span data-stu-id="3a502-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="3a502-118">A data contábil é usada, por exemplo, para reservas e ônus de orçamento.</span><span class="sxs-lookup"><span data-stu-id="3a502-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="3a502-119">Portanto, ele deve ser mantido durante a transição do recebimento de produtos para a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="3a502-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="3a502-120">Quando os recebimentos de produtos são cancelados, as transações podem ser lançadas em uma conta contábil suspensa.</span><span class="sxs-lookup"><span data-stu-id="3a502-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a502-121">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a502-121">Issue description</span></span>

<span data-ttu-id="3a502-122">Se um recebimento de produtos for cancelado, o sistema permitirá que as transações sejam lançadas nas contas contábeis suspensas, mesmo que as contas principais sejam suspensas.</span><span class="sxs-lookup"><span data-stu-id="3a502-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="3a502-123">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="3a502-123">Reproduce the issue</span></span>

<span data-ttu-id="3a502-124">O seguinte procedimento mostra uma forma de reproduzir o problema.</span><span class="sxs-lookup"><span data-stu-id="3a502-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="3a502-125">Na página **Parâmetros de contas a pagar**, na guia **Geral**, verifique se a opção **Lançar o recebimento de produtos no razão** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="3a502-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="3a502-126">Crie uma ordem de compra e adicione uma linha de ordem que tenha uma quantidade de *1.000* para um produto.</span><span class="sxs-lookup"><span data-stu-id="3a502-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="3a502-127">Confirme uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="3a502-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="3a502-128">Lance o recebimento de produtos e verifique os comprovantes.</span><span class="sxs-lookup"><span data-stu-id="3a502-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="3a502-129">Suspenda as contas principais, *200140* e *140200* relevantes.</span><span class="sxs-lookup"><span data-stu-id="3a502-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="3a502-130">Cancele o recebimento de produtos lançados.</span><span class="sxs-lookup"><span data-stu-id="3a502-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="3a502-131">Observe que as transações podem ser lançadas nas contas contábeis suspensas.</span><span class="sxs-lookup"><span data-stu-id="3a502-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a502-132">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a502-132">Issue resolution</span></span>

<span data-ttu-id="3a502-133">As transações podem ser lançadas nas contas contábeis suspensas quando os recebimentos de produtos forem cancelados, pois esse comportamento permite lançamentos corretos.</span><span class="sxs-lookup"><span data-stu-id="3a502-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="3a502-134">Um número de comprovante de recebimento de produtos será consumido mesmo que nenhum comprovante financeiro seja gerado durante o recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="3a502-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="3a502-135">Se a opção **Acumular passivo no recebimento de produtos** estiver definida como *Não* para o grupo de modelos de item, não ocorrerá lançamentos na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="3a502-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="3a502-136">No entanto, um evento físico será registrado para a finalidade de contabilização em um diário-razão e esse evento exigirá um número de comprovante.</span><span class="sxs-lookup"><span data-stu-id="3a502-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="3a502-137">Esse número de comprovante é o número de comprovante referido nas transações de estoque.</span><span class="sxs-lookup"><span data-stu-id="3a502-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="3a502-138">Recomendamos definir a opção **Acumular passivo no recebimento de produtos** como *Sim*, conforme descrito na seguinte postagem no blog: [Lançar encargos diversos no momento do recebimento do produto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="3a502-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="3a502-139">A configuração Lançar na conta de encargos não está ativada.</span><span class="sxs-lookup"><span data-stu-id="3a502-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="3a502-140">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="3a502-140">Issue description</span></span>

<span data-ttu-id="3a502-141">Esse problema ocorre quando uma ordem de compra é faturada, se a opção **Lançar na conta de encargos do razão** estiver definida como *Sim* na guia **Fatura** da página **Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="3a502-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="3a502-142">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="3a502-142">Reproduce the issue</span></span>

<span data-ttu-id="3a502-143">O seguinte procedimento mostra uma forma de reproduzir o problema.</span><span class="sxs-lookup"><span data-stu-id="3a502-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="3a502-144">Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.</span><span class="sxs-lookup"><span data-stu-id="3a502-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="3a502-145">Na guia **Fatura**, configure a opção **Lançar na conta de encargos do razão** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="3a502-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="3a502-146">Vá para **Gerenciamento de estoque \> Configurar \> Lançamento \> Lançamento**.</span><span class="sxs-lookup"><span data-stu-id="3a502-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="3a502-147">Na guia **Ordem de compra**, certifique-se de ter excluído todas as linhas nas despesas de compra do produto.</span><span class="sxs-lookup"><span data-stu-id="3a502-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="3a502-148">Vá para **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="3a502-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="3a502-149">Criar uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="3a502-149">Create a purchase order.</span></span> <span data-ttu-id="3a502-150">No campo **Conta de fornecedor**, selecione *1001 Suprimentos de Escritórios Acme*.</span><span class="sxs-lookup"><span data-stu-id="3a502-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="3a502-151">Adicione uma linha da ordem de compra com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="3a502-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="3a502-152">**Nº do item:** *Projetor Laser D0011*</span><span class="sxs-lookup"><span data-stu-id="3a502-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="3a502-153">**Local:** *1*</span><span class="sxs-lookup"><span data-stu-id="3a502-153">**Site:** *1*</span></span>
    - <span data-ttu-id="3a502-154">**Depósito:** *11*</span><span class="sxs-lookup"><span data-stu-id="3a502-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="3a502-155">**Quantidade:** *4*</span><span class="sxs-lookup"><span data-stu-id="3a502-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="3a502-156">No Painel de Ação, na guia **Compra**, no grupo **Ação**, selecione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3a502-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="3a502-157">No Painel de Ação, na guia **Receber**, no grupo **Gerar**, selecione **Recebimento de produtos**.</span><span class="sxs-lookup"><span data-stu-id="3a502-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="3a502-158">Na caixa de diálogo **Lançamento de recebimento de produtos**, no campo **Recebimento de produtos**, insira um número arbitrário e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a502-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="3a502-159">No Painel de Ação, na guia **Fatura**, no grupo **Gerar**, selecione **Fatura**.</span><span class="sxs-lookup"><span data-stu-id="3a502-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="3a502-160">No campo **Número**, insira um número arbitrário como o número da fatura.</span><span class="sxs-lookup"><span data-stu-id="3a502-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="3a502-161">Atualizar o status de conciliação e lançar.</span><span class="sxs-lookup"><span data-stu-id="3a502-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="3a502-162">Observe que agora você recebe o seguinte erro ao gerar uma fatura de uma ordem de compra: "O número da conta para o tipo de transação Despesas de compra para o produto não existe."</span><span class="sxs-lookup"><span data-stu-id="3a502-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="3a502-163">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="3a502-163">Issue resolution</span></span>

<span data-ttu-id="3a502-164">Isso depende das configurações de parâmetro para faturas e grupos de faturas.</span><span class="sxs-lookup"><span data-stu-id="3a502-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="3a502-165">Para obter mais informações, consulte a seguinte postagem no blog: [Contabilização de encargo de compra e variação de estoque](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="3a502-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>
