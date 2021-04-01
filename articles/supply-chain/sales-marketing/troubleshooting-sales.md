---
title: Solucionar problemas de ordens de venda
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de venda.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 346ebee598e282abfe01a399793cc259aff3c22d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232221"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="b0074-103">Solucionar problemas de ordens de venda</span><span class="sxs-lookup"><span data-stu-id="b0074-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="b0074-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="b0074-105">As informações sobre impostos não são atualizadas quando altero o local em um cabeçalho de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0074-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-106">Issue description</span></span>

<span data-ttu-id="b0074-107">Se o local, o depósito ou o endereço de entrega for alterado em um cabeçalho de ordem de venda ou no nível de linha, as informações de imposto do caso não serão atualizadas automaticamente para as linhas.</span><span class="sxs-lookup"><span data-stu-id="b0074-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0074-108">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-108">Issue resolution</span></span>

<span data-ttu-id="b0074-109">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="b0074-109">This behavior is by design.</span></span> <span data-ttu-id="b0074-110">O problema ocorre porque o endereço de entrega, o site e o depósito não são alterados automaticamente no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="b0074-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="b0074-111">Você deve atualizá-los manualmente.</span><span class="sxs-lookup"><span data-stu-id="b0074-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="b0074-112">Se houver dois contratos comerciais para o mesmo período ou períodos sobrepostos, a mesma linha de contrato será sempre selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0074-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0074-113">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-113">Issue description</span></span>

<span data-ttu-id="b0074-114">Se dois contratos comerciais forem definidos para o mesmo período ou períodos sobrepostos, o mesmo contrato comercial parecerá ser selecionado toda vez que você criar linhas de ordem de venda que contenham esses itens.</span><span class="sxs-lookup"><span data-stu-id="b0074-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0074-115">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-115">Issue resolution</span></span>

<span data-ttu-id="b0074-116">Se houver mais de um contrato comercial para uma determinada data, o contrato comercial com o menor preço será sempre selecionado.</span><span class="sxs-lookup"><span data-stu-id="b0074-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="b0074-117">Para obter mais informações, baixe o seguinte white paper: [Contratos comerciais no Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="b0074-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="b0074-118">É possível vincular uma ordem de compra a uma ordem de venda para atender a demanda?</span><span class="sxs-lookup"><span data-stu-id="b0074-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="b0074-119">Você pode criar uma ordem de compra de uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="b0074-120">Para obter mais informações, consulte [Criar uma ordem de compra de uma ordem de venda](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="b0074-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="b0074-121">Não consigo cancelar nem excluir uma ordem de devolução, nem uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="b0074-122">Você pode cancelar somente ordens de venda e ordens de devolução que estão em um estado *Criado*.</span><span class="sxs-lookup"><span data-stu-id="b0074-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="b0074-123">Para obter mais informações, consulte [Cancelar uma ordem de devolução](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="b0074-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="b0074-124">Quando tento cancelar uma ordem de venda, recebo uma mensagem de erro "As reservas não podem ser removidas porque há um trabalho criado com base nas reservas".</span><span class="sxs-lookup"><span data-stu-id="b0074-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="b0074-125">Código de erro: WAX4661</span><span class="sxs-lookup"><span data-stu-id="b0074-125">Error code: WAX4661</span></span>

<span data-ttu-id="b0074-126">Se o trabalho estiver associado a uma ordem de venda, não será possível cancelar a ordem de venda até que o trabalho seja cancelado e revertido.</span><span class="sxs-lookup"><span data-stu-id="b0074-126">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="b0074-127">Esse requisito se aplica mesmo que o trabalho associado à ordem de venda seja fechado.</span><span class="sxs-lookup"><span data-stu-id="b0074-127">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="b0074-128">Para corrigir esse problema, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b0074-128">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="b0074-129">Cancele o trabalho e coloque o estoque novamente no local desejado.</span><span class="sxs-lookup"><span data-stu-id="b0074-129">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="b0074-130">Vá para o carregamento relevante da ordem de venda e selecione **Reduzir quantidade separada** na linha de carga ou **Reverter trabalho** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="b0074-130">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="b0074-131">O trabalho agora tem um status *Cancelado* e o novo trabalho de movimentação de estoque é criado automaticamente e processado para colocar o estoque de volta ao local descrito no momento da reversão.</span><span class="sxs-lookup"><span data-stu-id="b0074-131">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="b0074-132">Excluir a carga.</span><span class="sxs-lookup"><span data-stu-id="b0074-132">Delete the load.</span></span> <span data-ttu-id="b0074-133">A remessa também será excluída.</span><span class="sxs-lookup"><span data-stu-id="b0074-133">The shipment is also deleted.</span></span>
3. <span data-ttu-id="b0074-134">Agora, você poderá ir para a ordem de venda e cancelá-la.</span><span class="sxs-lookup"><span data-stu-id="b0074-134">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="b0074-135">Não consigo cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-135">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0074-136">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-136">Issue description</span></span>

<span data-ttu-id="b0074-137">Se você tentar cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda, você poderá receber a seguinte mensagem de erro: "A quantidade não pode ser reduzida porque a quantidade de atualização restante muda o sinal."</span><span class="sxs-lookup"><span data-stu-id="b0074-137">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0074-138">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-138">Issue resolution</span></span>

<span data-ttu-id="b0074-139">Esse problema foi corrigido no Microsoft Dynamics 365 Supply Chain Management, version 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="b0074-139">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="b0074-140">Nessa versão e em versões posteriores, agora você pode cancelar uma ordem de compra intercompanhia vinculada a uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-140">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="b0074-141">É possível restaurar uma ordem de venda faturada que foi excluída?</span><span class="sxs-lookup"><span data-stu-id="b0074-141">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="b0074-142">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-142">Issue description</span></span>

<span data-ttu-id="b0074-143">Uma ordem de venda faturada foi excluída por engano e você deseja restaurá-la ou exibir seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="b0074-143">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="b0074-144">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="b0074-144">Issue resolution</span></span>

<span data-ttu-id="b0074-145">Se a ordem de venda excluída já foi faturada, vá para **Conta do cliente \> Transações \> Documento original \> Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b0074-145">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="b0074-146">Localize a fatura que você está procurando e selecione-a para exibir os detalhes.</span><span class="sxs-lookup"><span data-stu-id="b0074-146">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="b0074-147">Esses detalhes incluem a referência da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-147">These details include the sales order reference.</span></span> <span data-ttu-id="b0074-148">Você também deve ser capaz de acessar os detalhes da ordem de venda nessa página.</span><span class="sxs-lookup"><span data-stu-id="b0074-148">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="b0074-149">O prazo final de um cabeçalho da ordem de venda não pode ser encontrado na entidade de dados SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="b0074-149">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="b0074-150">O campo prazo final não existe na entidade *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="b0074-150">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="b0074-151">É preciso excluir registros órfãos da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b0074-151">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="b0074-152">Para limpar registros de ordem de venda órfãos, execute o trabalho periódico *Exclusão da ordem de venda* indo para um dos seguintes locais:</span><span class="sxs-lookup"><span data-stu-id="b0074-152">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="b0074-153">Vendas e marketing \> Tarefas periódicas \> Limpar \> Excluir ordens de venda</span><span class="sxs-lookup"><span data-stu-id="b0074-153">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="b0074-154">Varejo e comércio \> TI de Varejo e Comércio \> Limpar \> Excluir ordens de venda</span><span class="sxs-lookup"><span data-stu-id="b0074-154">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="b0074-155">Existe alguma forma de calcular comissões sobre faturas que já foram lançadas?</span><span class="sxs-lookup"><span data-stu-id="b0074-155">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="b0074-156">O Supply Chain Management não oferece suporte no momento ao cálculo de comissões para faturas lançadas.</span><span class="sxs-lookup"><span data-stu-id="b0074-156">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="b0074-157">Não há suporte para um item de pacote em um processo intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="b0074-157">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="b0074-158">O item de pacote não está disponível para a ordem de compra porque, se você examinar as linhas da ordem de venda para o item de pacote, verá que a quantidade é *0* (zero) e o status é *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="b0074-158">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Canceled*.</span></span> <span data-ttu-id="b0074-159">Esse comportamento é por design.</span><span class="sxs-lookup"><span data-stu-id="b0074-159">This behavior is by design.</span></span> <span data-ttu-id="b0074-160">A ordem de venda compra somente os componentes do item de pacote.</span><span class="sxs-lookup"><span data-stu-id="b0074-160">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="b0074-161">Ele não compra o próprio item do pacote.</span><span class="sxs-lookup"><span data-stu-id="b0074-161">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="b0074-162">Se você precisar comprar um pacote, considere se é necessário marcá-lo como item de pacote porque essa funcionalidade foi criada para cenários de reconhecimento de receita.</span><span class="sxs-lookup"><span data-stu-id="b0074-162">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is designed for revenue recognition scenarios.</span></span> <span data-ttu-id="b0074-163">Para obter mais informações sobre itens do pacote, consulte [Pacotes](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="b0074-163">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]