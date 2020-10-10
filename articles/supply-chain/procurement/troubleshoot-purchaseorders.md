---
title: Solucionar problemas de ordens de compra
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de compra.
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
ms.openlocfilehash: e55974f65577170880e60095f1ba74ea7366e592
ms.sourcegitcommit: 91e101d7a51a8b63bd196ec80e9224e5e6e6fc95
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "3834314"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="e35e1-103">Solucionar problemas de ordens de compra</span><span class="sxs-lookup"><span data-stu-id="e35e1-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="e35e1-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="e35e1-105">Uma ação pode ser concluída somente após o número da linha ser totalmente distribuído.</span><span class="sxs-lookup"><span data-stu-id="e35e1-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="e35e1-106">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="e35e1-107">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e35e1-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="e35e1-108">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="e35e1-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="e35e1-109">Quando as ordens de compra são importadas por meio do gerenciamento de dados, os números de linha da ordem de compra não seguem o incremento definido nos parâmetros do sistema.</span><span class="sxs-lookup"><span data-stu-id="e35e1-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-110">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-110">Issue description</span></span>

<span data-ttu-id="e35e1-111">Por padrão, os números de linha gerados automaticamente para linhas de ordem de compra que são importadas por meio da entidade de dados *Linhas da ordem de compra V2* não usam o incremento de número de linha do sistema especificado nos parâmetros do sistema.</span><span class="sxs-lookup"><span data-stu-id="e35e1-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="e35e1-112">Se você criar manualmente uma ordem de compra e adicionar linhas por meio da interface do usuário (IU), os números de linha serão incrementados corretamente.</span><span class="sxs-lookup"><span data-stu-id="e35e1-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="e35e1-113">No entanto, se você usar a DMF (Estrutura de gerenciamento de dados), elas não serão incrementadas corretamente.</span><span class="sxs-lookup"><span data-stu-id="e35e1-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="e35e1-114">Esse problema ocorre porque, quando você importa linhas via DMF, se os números de linha ainda não estiverem atribuídos na entidade importada, o sistema usará o método de DMF para atribuí-los.</span><span class="sxs-lookup"><span data-stu-id="e35e1-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="e35e1-115">Esse método sempre incrementa os números de linha em um.</span><span class="sxs-lookup"><span data-stu-id="e35e1-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="e35e1-116">Solução alternativa do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-116">Issue workaround</span></span>

<span data-ttu-id="e35e1-117">Certifique-se de que os números de linha desejados já tenham sido fornecidos nos campos de número de linha da entidade de dados quando você importar as linhas da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="e35e1-118">Nesse caso, a DMF não substituirá os números de linha.</span><span class="sxs-lookup"><span data-stu-id="e35e1-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="e35e1-119">Um grupo de impostos padrão e um desconto à vista padrão não são preenchidos a partir da conta da fatura.</span><span class="sxs-lookup"><span data-stu-id="e35e1-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="e35e1-120">Se você estiver usando uma conta da fatura diferente da conta do cliente, um grupo de impostos padrão e um desconto à vista padrão não serão preenchidos a partir da conta da fatura quando uma ordem de compra for criada.</span><span class="sxs-lookup"><span data-stu-id="e35e1-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="e35e1-121">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="e35e1-121">This behavior is by design.</span></span> <span data-ttu-id="e35e1-122">Os valores padrão para o grupo de impostos, descontos à vista e outras informações de preço são baseados na conta do cliente, não na conta da fatura.</span><span class="sxs-lookup"><span data-stu-id="e35e1-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="e35e1-123">Recebo uma mensagem de erro "Referência de objeto não definida" durante a confirmação da ordem de compra ou uma "Exceção lançada pelo destino de uma chamada" ocorre durante o lançamento da fatura do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="e35e1-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="e35e1-124">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="e35e1-125">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e35e1-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="e35e1-126">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="e35e1-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="e35e1-127">Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas.</span><span class="sxs-lookup"><span data-stu-id="e35e1-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-128">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-128">Issue description</span></span>

<span data-ttu-id="e35e1-129">Você recebe o seguinte erro: "Uma ou mais distribuições contábeis são superdistribuídas ou subdistribuídas".</span><span class="sxs-lookup"><span data-stu-id="e35e1-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e35e1-130">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-130">Issue resolution</span></span>

<span data-ttu-id="e35e1-131">Esse problema pode ocorrer devido a inconsistências nas distribuições da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="e35e1-132">Para desbloquear esse problema e redefinir a ordem de compra para um estado *Rascunho*, vá para **Compras e fornecimento \> Tarefas periódicas \> Limpar \> Redefinição de distribuição da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e35e1-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="e35e1-133">Para obter mais informações, consulte a seguinte postagem de blog: [Resolver erros de distribuição de OC no Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="e35e1-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="e35e1-134">É possível mostrar somente as ordens de compra que criei?</span><span class="sxs-lookup"><span data-stu-id="e35e1-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="e35e1-135">Essa funcionalidade não está disponível no momento.</span><span class="sxs-lookup"><span data-stu-id="e35e1-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="e35e1-136">Posso reservar estoque e criar transações em relação ao estoque registrado em uma ordem de compra?</span><span class="sxs-lookup"><span data-stu-id="e35e1-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-137">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-137">Issue description</span></span>

<span data-ttu-id="e35e1-138">Mesmo quando os itens estão em um estado *Registrado* em uma ordem de compra, você ainda pode reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="e35e1-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="e35e1-139">Em outras palavras, você pode criar transações no estoque registrado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="e35e1-140">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-140">Reproduce the issue</span></span>

<span data-ttu-id="e35e1-141">O seguinte procedimento mostra uma forma de reproduzir o problema.</span><span class="sxs-lookup"><span data-stu-id="e35e1-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="e35e1-142">Criar uma ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-142">Create a purchase order.</span></span>
2. <span data-ttu-id="e35e1-143">Registre a linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e35e1-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="e35e1-144">Observe que você pode gerar reservas ou transações no estoque registrado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e35e1-145">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-145">Issue resolution</span></span>

<span data-ttu-id="e35e1-146">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="e35e1-146">This behavior is by design.</span></span> <span data-ttu-id="e35e1-147">A expectativa é de que os itens registrados tenham sido entregues fisicamente no depósito ou estoque e que, portanto, estejam disponíveis para reserva.</span><span class="sxs-lookup"><span data-stu-id="e35e1-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="e35e1-148">As ordens de compra não refletem as configurações de idioma da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="e35e1-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-149">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-149">Issue description</span></span>

<span data-ttu-id="e35e1-150">O nome do produto em uma ordem de compra é mostrado no idioma do sistema, e não no idioma definido para a entidade legal na qual a ordem de compra foi criada.</span><span class="sxs-lookup"><span data-stu-id="e35e1-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="e35e1-151">Reproduzir o problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-151">Reproduce the issue</span></span>

<span data-ttu-id="e35e1-152">O seguinte procedimento mostra uma forma de reproduzir o problema.</span><span class="sxs-lookup"><span data-stu-id="e35e1-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="e35e1-153">Defina o idioma do sistema como *EN-US* (Inglês dos EUA).</span><span class="sxs-lookup"><span data-stu-id="e35e1-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="e35e1-154">Verifique se há um produto no qual os idiomas *EN-US* e *DE* (Alemão) são mantidos para traduções do nome do produto.</span><span class="sxs-lookup"><span data-stu-id="e35e1-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="e35e1-155">Altere o idioma de uma entidade legal para *DE*.</span><span class="sxs-lookup"><span data-stu-id="e35e1-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="e35e1-156">Na entidade legal onde *DE* é definido como o idioma, crie uma ordem de compra que inclua o produto.</span><span class="sxs-lookup"><span data-stu-id="e35e1-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="e35e1-157">Observe que o nome do produto ainda é mostrado em inglês dos EUA (o idioma do sistema).</span><span class="sxs-lookup"><span data-stu-id="e35e1-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e35e1-158">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-158">Issue resolution</span></span>

<span data-ttu-id="e35e1-159">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="e35e1-159">This behavior is by design.</span></span> <span data-ttu-id="e35e1-160">Nas ordens de compra, o produto sempre é mostrado no idioma do sistema.</span><span class="sxs-lookup"><span data-stu-id="e35e1-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="e35e1-161">A linguagem da ordem de compra é usada quando um diário de confirmação é criado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="e35e1-162">A lista de Fornecedores aprovados por entidade de produto não permite que a data de efetivação seja alterada.</span><span class="sxs-lookup"><span data-stu-id="e35e1-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-163">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-163">Issue description</span></span>

<span data-ttu-id="e35e1-164">Um produto tem um fornecedor aprovado que tem, por exemplo, uma data de efetivação de 11 de janeiro de 2018 (*11/01/2018*) e uma data de vencimento *Nunca*.</span><span class="sxs-lookup"><span data-stu-id="e35e1-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 (*01/11/2018*), and an expiration date of *Never*.</span></span> <span data-ttu-id="e35e1-165">Se você tentar alterar a data de efetivação para 10 de janeiro de 2018 (*10/01/2018*) ou 12 de janeiro, 2018 (*12/01/2018*), receberá o seguinte erro:</span><span class="sxs-lookup"><span data-stu-id="e35e1-165">If you try to change the effective date to January 10, 2018 (*01/10/2018*), or January 12, 2018 (*01/12/2018*), you receive the following error:</span></span>

> <span data-ttu-id="e35e1-166">Não é possível criar um registro na lista de fornecedores Aprovados (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="e35e1-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="e35e1-167">O valor de 'Vencimento' precisa ser maior ou igual ao valor de 'Efetivo'.</span><span class="sxs-lookup"><span data-stu-id="e35e1-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e35e1-168">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-168">Issue resolution</span></span>

<span data-ttu-id="e35e1-169">Você só pode estender o período para o qual o fornecedor foi aprovado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="e35e1-170">As seguintes regras são aplicadas:</span><span class="sxs-lookup"><span data-stu-id="e35e1-170">The following rules apply:</span></span>

- <span data-ttu-id="e35e1-171">Para alterar a data de efetivação de forma que ela seja anterior a qualquer um dos registros existentes (períodos) para o fornecedor do item, a data de vencimento do novo período deve ser anterior a todas as datas de vencimento nos registros existentes.</span><span class="sxs-lookup"><span data-stu-id="e35e1-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="e35e1-172">Para alterar a data de vencimento para que seja posterior a qualquer um dos períodos existentes, a data de efetivação deve ser posterior à data de vencimento mais recente em qualquer registro existente.</span><span class="sxs-lookup"><span data-stu-id="e35e1-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="e35e1-173">Para reduzir o período geral para o qual o fornecedor foi aprovado, você deve excluir ou modificar os registros existentes.</span><span class="sxs-lookup"><span data-stu-id="e35e1-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="e35e1-174">Como alternativa, você pode usar o alternador **truncar** durante a importação.</span><span class="sxs-lookup"><span data-stu-id="e35e1-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="e35e1-175">Esta opção exclui todos os registros existentes na tabela para fornecedores aprovados por item.</span><span class="sxs-lookup"><span data-stu-id="e35e1-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="e35e1-176">Para o cenário de exemplo descrito na descrição do problema, em que um registro tem uma data de efetivação de *11/01/2018* e uma data de expiração *Nunca*, você pode importar um novo registro que tenha uma data de efetivação de *10/01/2018* e uma data de expiração *Nunca*.</span><span class="sxs-lookup"><span data-stu-id="e35e1-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never*, you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="e35e1-177">No entanto, não é possível reduzir o período para que a data de efetivação seja atualizada para *12/01/2018* por meio do gerenciamento de dados.</span><span class="sxs-lookup"><span data-stu-id="e35e1-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="e35e1-178">Você deve fazer essa alteração por meio da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="e35e1-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-nameisnt-synced"></a><span data-ttu-id="e35e1-179">Depois de alterar o endereço de entrega em um cabeçalho de ordem de compra, o nome da entrega não é sincronizado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="e35e1-180">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-180">Issue description</span></span>

<span data-ttu-id="e35e1-181">O endereço no cabeçalho de uma ordem de compra é atualizado para um endereço que não é um endereço de entrega.</span><span class="sxs-lookup"><span data-stu-id="e35e1-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="e35e1-182">Embora o endereço seja atualizado na ordem de compra, o nome da entrega não é atualizado com base no endereço atualizado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="e35e1-183">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="e35e1-183">Issue resolution</span></span>

<span data-ttu-id="e35e1-184">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="e35e1-184">This behavior is by design.</span></span> <span data-ttu-id="e35e1-185">O endereço selecionado deve ser classificado como um endereço de entrega.</span><span class="sxs-lookup"><span data-stu-id="e35e1-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="e35e1-186">Caso contrário, o nome da entrega não será atualizado com base no endereço selecionado.</span><span class="sxs-lookup"><span data-stu-id="e35e1-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="e35e1-187">É possível encontrar o usuário que cancelou uma ordem de compra?</span><span class="sxs-lookup"><span data-stu-id="e35e1-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="e35e1-188">Essas informações serão rastreadas somente se a ordem de compra estiver sujeita a gerenciamento de alterações.</span><span class="sxs-lookup"><span data-stu-id="e35e1-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="e35e1-189">Se você usar o gerenciamento de alterações, poderá ver quem enviou a alteração (o cancelamento) e quem a aprovou.</span><span class="sxs-lookup"><span data-stu-id="e35e1-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>
