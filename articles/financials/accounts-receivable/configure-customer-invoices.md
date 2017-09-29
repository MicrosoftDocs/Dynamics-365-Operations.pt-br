---
title: Criar uma fatura de cliente
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2a668e390935e157d9fc7f0ef597f25c2a7b9950
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---

# <a name="create-a-customer-invoice"></a><span data-ttu-id="4aff8-102">Criar uma fatura de cliente</span><span class="sxs-lookup"><span data-stu-id="4aff8-102">Create a customer invoice</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4aff8-103">Uma **fatura de cliente para uma ordem de venda** é uma nota que está relacionada a uma venda, e que uma organização fornece a um cliente.</span><span class="sxs-lookup"><span data-stu-id="4aff8-103">A **customer invoice for a sales order** is a bill that is related to a sale, and that an organization gives to a customer.</span></span> <span data-ttu-id="4aff8-104">Esse tipo de fatura de cliente é criado com base em uma ordem de venda, que inclui linhas de ordem e números de item.</span><span class="sxs-lookup"><span data-stu-id="4aff8-104">This type of customer invoice is created based on a sales order, which includes order lines and item numbers.</span></span> <span data-ttu-id="4aff8-105">Os números de item são especificados e lançados no razão.</span><span class="sxs-lookup"><span data-stu-id="4aff8-105">Item numbers are specified and posted in the ledger.</span></span> <span data-ttu-id="4aff8-106">As entradas no diário-razão auxiliar não estão disponíveis para uma fatura de cliente de uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-106">Subledger journal entries aren't available for a customer invoice for a sales order.</span></span> <span data-ttu-id="4aff8-107">Para obter mais informações, consulte [Criar faturas de ordem de venda](tasks/create-sales-order-invoices.md).</span><span class="sxs-lookup"><span data-stu-id="4aff8-107">For more information, see [Create sales order invoices](tasks/create-sales-order-invoices.md).</span></span>

<span data-ttu-id="4aff8-108">Uma **fatura de texto livre** não está relacionada a uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-108">A **free text invoice** isn't related to a sales order.</span></span> <span data-ttu-id="4aff8-109">Ela contém linhas de ordem que incluem contas contábeis, descrições de texto livre e um valor de venda que você insere.</span><span class="sxs-lookup"><span data-stu-id="4aff8-109">It contains order lines that include ledger accounts, free-text descriptions, and a sales amount that you enter.</span></span> <span data-ttu-id="4aff8-110">Não é possível inserir um número de item neste tipo de fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-110">You can't enter an item number on this kind of invoice.</span></span> <span data-ttu-id="4aff8-111">Você deverá inserir as informações apropriadas de impostos sobre vendas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-111">You must enter the appropriate sales tax information.</span></span> <span data-ttu-id="4aff8-112">Uma conta principal para a venda é indicada em cada linha da fatura, que você pode distribuir para diversas contas contáveis clicando em **Distribuir valores** na página **Fatura de texto livre**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-112">A main account for the sale is indicated on each invoice line, which you can distribute to multiple ledger accounts by clicking **Distribute amounts** on the **Free text invoice** page.</span></span> <span data-ttu-id="4aff8-113">Além disso, o saldo do cliente é lançado na conta resumo do perfil de lançamento usado para a fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="4aff8-113">Additionally, the customer balance is posted to the summary account from the posting profile that is used for the free text invoice.</span></span>

<span data-ttu-id="4aff8-114">Para obter mais informações, consulte: </span><span class="sxs-lookup"><span data-stu-id="4aff8-114">For more information see:</span></span>

[<span data-ttu-id="4aff8-115">Criar uma fatura de texto livre</span><span class="sxs-lookup"><span data-stu-id="4aff8-115">Create a free text invoice</span></span>](tasks/create-free-text-invoice.md)

[<span data-ttu-id="4aff8-116">Criar um modelo de texto livre</span><span class="sxs-lookup"><span data-stu-id="4aff8-116">Create a free text template</span></span>](tasks/create-free-text-invoice-template.md)

[<span data-ttu-id="4aff8-117">Atribuir um modelo de fatura de texto livre a um cliente</span><span class="sxs-lookup"><span data-stu-id="4aff8-117">Assign a free text invoice tempate to a customer</span></span>](tasks/assign-free-text-invoice-template-customer.md)

[<span data-ttu-id="4aff8-118">Gerar e lançar faturas de texto livre recorrentes</span><span class="sxs-lookup"><span data-stu-id="4aff8-118">Generate and post recurring free text invoices</span></span>](tasks/post-recurring-free-text-invoices.md)


<span data-ttu-id="4aff8-119">Uma **fatura pro forma** é uma fatura preparada como uma previsão dos valores da fatura real antes de a fatura ser lançada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-119">A **pro forma invoice** is an invoice that is prepared as an estimate of the actual invoice amounts before the invoice is posted.</span></span> <span data-ttu-id="4aff8-120">Você pode imprimir uma fatura pro forma de uma fatura de cliente de uma ordem de venda ou de uma fatura de texto livre.</span><span class="sxs-lookup"><span data-stu-id="4aff8-120">You can print a pro forma invoice either for a customer invoice for a sales order or for a free text invoice.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a><span data-ttu-id="4aff8-121">Lançar e imprimir faturas de clientes individuais com base em ordens de venda</span><span class="sxs-lookup"><span data-stu-id="4aff8-121">Post and print individual customer invoices that are based on sales orders</span></span>
<span data-ttu-id="4aff8-122">Use este processo para criar uma fatura com base em uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-122">Use this process to create an invoice that is based on a sales order.</span></span> <span data-ttu-id="4aff8-123">É possível fazer isso se você decidir faturar o cliente antes de entregar as mercadorias ou os serviços.</span><span class="sxs-lookup"><span data-stu-id="4aff8-123">You might do this if you decide to invoice the customer before you deliver the goods or services.</span></span> 

<span data-ttu-id="4aff8-124">Quando você lança uma fatura, a quantidade **A faturar** de cada item é atualizada com o total das quantidades faturadas da ordem de venda selecionada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-124">When you post an invoice, the **Invoice remainder** quantity for each item is updated with the total of the invoiced quantities from the selected sales order.</span></span> <span data-ttu-id="4aff8-125">Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-125">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="4aff8-126">Se a quantidade **A faturar** for diferente de 0 (zero), o status da ordem de venda permanece inalterado, e faturas adicionais podem ser inseridas para ela.</span><span class="sxs-lookup"><span data-stu-id="4aff8-126">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span>

<span data-ttu-id="4aff8-127">Você pode exibir o status da ordem de venda na página de listagem **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-127">You can view the status of the sales orders on the **All sales orders** list page.</span></span> <span data-ttu-id="4aff8-128">Use a página de listagem **Abrir faturas de cliente** para exibir as faturas lançadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-128">Use the **Open customer invoices** list page to view the invoices that you posted.</span></span>

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a><span data-ttu-id="4aff8-129">Lançar e imprimir faturas de cliente individuais com base em guias de remessa e data</span><span class="sxs-lookup"><span data-stu-id="4aff8-129">Post and print individual customer invoices that are based on packing slips and the date</span></span>
<span data-ttu-id="4aff8-130">Use este processo quando uma ou mais guias de remessa tiverem sido lançadas para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-130">Use this process when one or more packing slips have been posted for the sales order.</span></span> <span data-ttu-id="4aff8-131">A fatura de cliente baseia-se nessas guias de remessa e reflete as quantidades nelas indicadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-131">The customer invoice is based on these packing slips and reflects the quantities from them.</span></span> <span data-ttu-id="4aff8-132">As informações financeiras da fatura baseiam-se nas que são inseridas quando você lança essa nota.</span><span class="sxs-lookup"><span data-stu-id="4aff8-132">The financial information for the invoice is based on the information that is entered when you post the invoice.</span></span> 

<span data-ttu-id="4aff8-133">Você pode criar uma fatura de cliente com base nos itens de linha da guia de remessa que foram remetidos até a data, mesmo que todos os itens de determinada ordem de venda ainda não tenham sido remetidos.</span><span class="sxs-lookup"><span data-stu-id="4aff8-133">You can create a customer invoice that is based on the packing slip line items that have been shipped to date, even if all the items for a particular sales order haven't yet been shipped.</span></span> <span data-ttu-id="4aff8-134">Você poderá fazer isso, por exemplo, se a sua entidade legal emitir uma fatura por cliente por mês cobrindo todas as entregas remetidas durante esse mês.</span><span class="sxs-lookup"><span data-stu-id="4aff8-134">You might do this if, for example, your legal entity issues one invoice per customer per month that covers all the deliveries that you ship during that month.</span></span> <span data-ttu-id="4aff8-135">Cada guia de remessa representa uma entrega parcial ou completa dos itens da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-135">Each packing slip represents a partial or complete delivery of the items on the sales order.</span></span> 

<span data-ttu-id="4aff8-136">Quando você lança a fatura, a quantidade **A faturar** de cada item é atualizada com o total das quantidades entregues das guias de remessa selecionadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-136">When you post the invoice, the **Invoice remainder** quantity for each item is updated with the total of the delivered quantities from the selected packing slips.</span></span> <span data-ttu-id="4aff8-137">Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-137">If both the **Invoice remainder** quantity and the **Deliver remainder** quantity for all items on the sales order are 0 (zero), the status of the sales order is changed to **Invoiced**.</span></span> <span data-ttu-id="4aff8-138">Se a quantidade **A faturar** for diferente de 0 (zero), o status da ordem de venda permanece inalterado, e faturas adicionais podem ser inseridas para ela.</span><span class="sxs-lookup"><span data-stu-id="4aff8-138">If the **Invoice remainder** quantity isn't 0 (zero), the status of the sales order remains unchanged, and additional invoices can be entered for it.</span></span> 

<span data-ttu-id="4aff8-139">As transações de estoque são atualizadas com o número da fatura, e o status no campo **Status da linha** na ordem de venda é alterado para **Faturado**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-139">Inventory transactions are updated with the invoice number, and the status in the **Line status** field on the sales order is changed to **Invoiced**.</span></span> 

<span data-ttu-id="4aff8-140">Exiba o status da ordem de venda na página de listagem **Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-140">View the status of the sales orders in the **All sales orders** list page.</span></span>

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a><span data-ttu-id="4aff8-141">Consolidar ordens de venda ou guias de remessa para lançamento</span><span class="sxs-lookup"><span data-stu-id="4aff8-141">Consolidate sales orders or packing slips for posting</span></span>
<span data-ttu-id="4aff8-142">Use este processo quando uma ou mais ordens de venda estiverem prontas para serem faturadas, e você desejar consolidá-las em uma única fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-142">Use this process when one or more sales orders are ready to be invoiced, and you want to consolidate them into a single invoice.</span></span> 

<span data-ttu-id="4aff8-143">Você pode selecionar várias faturas na página de listagem **Ordem de venda** e, em seguida, usar a função **Gerar faturas** para consolidá-las.</span><span class="sxs-lookup"><span data-stu-id="4aff8-143">You can select multiple invoices on the **Sales order** list page and then use **Generate invoices** to consolidate them.</span></span> <span data-ttu-id="4aff8-144">Na página **Lançamento de fatura**, você pode alterar a configuração **Ordem resumida** para resumir por número de ordem (onde houver diversas guias de remessa para uma única ordem de venda) ou por valor de fatura (onde houver diversas ordens de venda para uma única conta de fatura).</span><span class="sxs-lookup"><span data-stu-id="4aff8-144">On the **Posting invoice** page, you can change the **Summary order** setting to summarize by order number (where there are multiple packing slips for a single sales order) or by invoice account (where there are multiple sales orders for a single invoice account).</span></span> <span data-ttu-id="4aff8-145">Use o botão **Organizar** para consolidar as ordens de venda em faturas únicas, com base nas configurações de **Ordem resumida**.</span><span class="sxs-lookup"><span data-stu-id="4aff8-145">Use the **Arrange** button to consolidate sales orders into single invoices, based on the **Summary order** settings.</span></span>

## <a name="additional-settings-that-change-the-posting-behavior"></a><span data-ttu-id="4aff8-146">Configurações adicionais que alteram o comportamento dos lançamentos</span><span class="sxs-lookup"><span data-stu-id="4aff8-146">Additional settings that change the posting behavior</span></span>
<span data-ttu-id="4aff8-147">Os seguintes campos alteram o comportamento do processo de lançamento.</span><span class="sxs-lookup"><span data-stu-id="4aff8-147">The following fields change the behavior of the posting process.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4aff8-148">Campo</span><span class="sxs-lookup"><span data-stu-id="4aff8-148">Field</span></span></th>
<th><span data-ttu-id="4aff8-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="4aff8-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="4aff8-150">Quantidade</span><span class="sxs-lookup"><span data-stu-id="4aff8-150">Quantity</span></span></td>
<td><span data-ttu-id="4aff8-151">Selecione as quantidades nas quais o lançamento do documento irá se basear.</span><span class="sxs-lookup"><span data-stu-id="4aff8-151">Select the quantities to base the posting of the document on.</span></span> <span data-ttu-id="4aff8-152">As opções que estão disponíveis variam dependendo do tipo de documento que você está lançando, como uma guia de remessa ou uma fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-152">The options that are available vary, depending on the type of document that you are posting, such as a packing slip or an invoice.</span></span>
<ul>
<li><span data-ttu-id="4aff8-153"><strong>Entregar agora</strong> – Selecione todas as quantidades inseridas no campo <strong>Entregar agora</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-153"><strong>Deliver now</strong> – Select all quantities that are entered in the <strong>Deliver now</strong> field.</span></span> <span data-ttu-id="4aff8-154">Use esta opção para confirmar ou entregar uma ordem parcial.</span><span class="sxs-lookup"><span data-stu-id="4aff8-154">Use this option to confirm or deliver a partial order.</span></span></li>
<li><span data-ttu-id="4aff8-155"><strong>Separado</strong> – Selecione todas as quantidades que foram separadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-155"><strong>Picked</strong> – Select all quantities that have been picked.</span></span></li>
<li><span data-ttu-id="4aff8-156"><strong>Todas</strong> – Selecione todas quantidades na ordem de venda que ainda não foram atualizadas pelo tipo de documento atual.</span><span class="sxs-lookup"><span data-stu-id="4aff8-156"><strong>All</strong> – Select all quantities on the sales order that haven't yet been updated by the current document type.</span></span></li>
<li><span data-ttu-id="4aff8-157"><strong>Guia de remessa</strong> – Selecione todas as quantidades que foram atualizadas por uma guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="4aff8-157"><strong>Packing slip</strong> – Select all quantities that have been updated by a packing slip.</span></span></li>
<li><span data-ttu-id="4aff8-158"><strong>Quantidade separada e produtos que não estão armazenados</strong> – Selecione todas as quantidades que foram separadas e todas as quantidades de produto que não são armazenadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-158"><strong>Picked quantity and not stocked products</strong> – Select all quantities that have been picked and all product quantities that aren't stocked.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-159">Lançamento</span><span class="sxs-lookup"><span data-stu-id="4aff8-159">Posting</span></span></td>
<td><ul>
<li><span data-ttu-id="4aff8-160">Selecione esta opção para lançar em diário a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-160">Select this option to journalize the sales order.</span></span></li>
<li><span data-ttu-id="4aff8-161">Desmarque esta opção para imprimir uma ordem de venda pro forma.</span><span class="sxs-lookup"><span data-stu-id="4aff8-161">Clear this option to print a pro forma sales order.</span></span> <span data-ttu-id="4aff8-162"><strong>Observação:</strong> Se você tiver feito um acordo para um plano de pagamento, o plano de pagamento não será exibido na ordem de venda pro forma.</span><span class="sxs-lookup"><span data-stu-id="4aff8-162"><strong>Note:</strong> If you made an agreement for a payment schedule, the payment schedule isn't shown on the pro forma sales order.</span></span> <span data-ttu-id="4aff8-163">Os planos de pagamento serão mostrados apenas nas ordens de venda reais.</span><span class="sxs-lookup"><span data-stu-id="4aff8-163">Payment schedules are shown only on actual sales orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4aff8-164">Seleção posterior</span><span class="sxs-lookup"><span data-stu-id="4aff8-164">Late selection</span></span></td>
<td><span data-ttu-id="4aff8-165">Selecione esta opção para aplicar a consulta selecionada mais tarde.</span><span class="sxs-lookup"><span data-stu-id="4aff8-165">Select this option to apply the selected query later.</span></span> <span data-ttu-id="4aff8-166">Essa opção é usada para trabalhos em lotes.</span><span class="sxs-lookup"><span data-stu-id="4aff8-166">This option is used for batch jobs.</span></span> <span data-ttu-id="4aff8-167">A consulta será executada quando o trabalho em lotes for executado.</span><span class="sxs-lookup"><span data-stu-id="4aff8-167">The query is run when the batch job is run.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-168">Reduzir quantidade</span><span class="sxs-lookup"><span data-stu-id="4aff8-168">Reduce quantity</span></span></td>
<td><span data-ttu-id="4aff8-169">Selecione esta opção para reduzir automaticamente a quantidade entregue quando o documento for lançado, de tal modo que a quantidade entregue seja igual ao estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="4aff8-169">Select this option to automatically reduce the delivered quantity when the document is posted, so that the delivered quantity equals the available inventory.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4aff8-170">Imprimir</span><span class="sxs-lookup"><span data-stu-id="4aff8-170">Print</span></span></td>
<td><span data-ttu-id="4aff8-171">Selecione quando imprimir documentos:</span><span class="sxs-lookup"><span data-stu-id="4aff8-171">Select when to print documents:</span></span>
<ul>
<li><span data-ttu-id="4aff8-172"><strong>Atual</strong> – Imprimir documentos após cada fatura ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-172"><strong>Current</strong> – Print documents after each invoice has been updated.</span></span></li>
<li><span data-ttu-id="4aff8-173"><strong>Após</strong> – Imprimir documentos depois que todas as faturas estiverem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-173"><strong>After</strong> – Print documents after all the invoices have been updated.</span></span></li>
</ul><span data-ttu-id="4aff8-174">
<strong>Observação:</strong> O campo <strong>Imprimir</strong> só ficará disponível se você selecionar a opção <strong>Imprimir fatura</strong>, <strong>Imprimir confirmação</strong>, <strong>Imprimir lista de separação</strong>, ou <strong>Imprimir guia de remessa</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-174">
<strong>Note:</strong> The <strong>Print</strong> field is available only if you select the <strong>Print invoice</strong>, <strong>Print confirmation</strong>, <strong>Print picking list</strong>, or <strong>Print packing slip</strong> option.</span></span> <span data-ttu-id="4aff8-175">Por exemplo, na página <strong>Classificação de formulário</strong>, você configurou o sistema para classificar as informações por conta de fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-175">For example, on the <strong>Form sorting</strong> page, you have set up the system to sort the information by invoice account.</span></span> <span data-ttu-id="4aff8-176">Você pode então selecionar <strong>Depois</strong> para imprimir documentos em um lote que seja classificado por conta de fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-176">You can then select <strong>After</strong> to print the documents in a batch that is sorted by invoice account.</span></span> <span data-ttu-id="4aff8-177">Caso contrário, os documentos são impressos antes que o processamento esteja completo, e os documentos não são classificados na ordem que é especificada na página <strong>Classificação do formulário</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-177">Otherwise, the documents are printed before processing is completed, and the documents aren't sorted in the order that is specified on the <strong>Form sorting</strong> page.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-178">Imprimir fatura</span><span class="sxs-lookup"><span data-stu-id="4aff8-178">Print invoice</span></span></td>
<td><span data-ttu-id="4aff8-179">Selecionar essa opção para imprimir a fatura.</span><span class="sxs-lookup"><span data-stu-id="4aff8-179">Select this option to print the invoice.</span></span> <span data-ttu-id="4aff8-180">Se esta opção for desativada, você pode lançar uma fatura sem imprimi-la.</span><span class="sxs-lookup"><span data-stu-id="4aff8-180">If this option is turned off, you can post an invoice without printing it.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4aff8-181">Enviar email</span><span class="sxs-lookup"><span data-stu-id="4aff8-181">Send e-mail</span></span></td>
<td><span data-ttu-id="4aff8-182">Selecione esta opção para enviar a fatura para uma ordem de venda para o cliente como um anexo de email após a fatura ser lançada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-182">Select this option to send the invoice for a sales order to the customer as an email attachment after the invoice is posted.</span></span> <span data-ttu-id="4aff8-183">Os anexos são enviados como arquivos PDF e XML.</span><span class="sxs-lookup"><span data-stu-id="4aff8-183">Attachments are sent as PDF and XML files.</span></span> <span data-ttu-id="4aff8-184">Esta opção está disponível somente se você selecionar a opção <strong>Habilitar CFD (faturas eletrônicas)</strong> na página <strong>Parâmetros de fatura eletrônica</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-184">This option is available only if you select the <strong>Enable CFD (electronic invoices)</strong> option on the <strong>Electronic invoice parameters</strong> page.</span></span> <span data-ttu-id="4aff8-185"><strong>Observação:</strong> (MEX) Esse controle está disponível somente para entidades legais cujo endereço principal está localizado no México.</span><span class="sxs-lookup"><span data-stu-id="4aff8-185"><strong>Note:</strong> (MEX) This control is available only to legal entities whose primary address is in Mexico.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-186">Usar o destino do gerenciamento de impressão</span><span class="sxs-lookup"><span data-stu-id="4aff8-186">Use print management destination</span></span></td>
<td><span data-ttu-id="4aff8-187">Selecione esta opção para usar as configurações de impressão especificadas para a transação, documento, ou módulo na página <strong>Configuração do gerenciamento de impressão</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-187">Select this option to use the print settings that are specified for the transaction, document, or module on the <strong>Print management setup</strong> page.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4aff8-188">Verificar limite de crédito</span><span class="sxs-lookup"><span data-stu-id="4aff8-188">Check credit limit</span></span></td>
<td><span data-ttu-id="4aff8-189">Selecione as informações que devem ser analisadas quando uma verificação de limite de crédito for realizada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-189">Select the information that should be analyzed when a credit limit check is performed.</span></span>
<ul>
<li><span data-ttu-id="4aff8-190"><strong>Nenhum</strong> – não existem requisitos para a verificação do limite de crédito.</span><span class="sxs-lookup"><span data-stu-id="4aff8-190"><strong>None</strong> – There is no requirement for the credit limit check.</span></span></li>
<li><span data-ttu-id="4aff8-191"><strong>Saldo</strong> – o limite de crédito é comparado ao saldo do cliente.</span><span class="sxs-lookup"><span data-stu-id="4aff8-191"><strong>Balance</strong> – The credit limit is checked against the customer balance.</span></span></li>
<li><span data-ttu-id="4aff8-192"><strong>Saldo + guia de remessa ou recebimento de produtos</strong> – O limite de crédito é verificado em relação ao saldo do cliente e entregas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-192"><strong>Balance + packing slip or product receipt</strong> – The credit limit is checked against the customer balance and deliveries.</span></span></li>
<li><span data-ttu-id="4aff8-193"><strong>Saldo+tudo</strong> – o limite de crédito é verificado em relação ao saldo do cliente, entregas e ordens abertas.</span><span class="sxs-lookup"><span data-stu-id="4aff8-193"><strong>Balance+All</strong> – The credit limit is checked against the customer balance, deliveries, and open orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-194">Correção de crédito</span><span class="sxs-lookup"><span data-stu-id="4aff8-194">Credit correction</span></span></td>
<td><span data-ttu-id="4aff8-195">Marque esta opção para exibir a nota de crédito como débito nas transações de comprovante.</span><span class="sxs-lookup"><span data-stu-id="4aff8-195">Select this option to display the credit note as a debit in the voucher transactions.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="4aff8-196">Quantidade pendente de crédito</span><span class="sxs-lookup"><span data-stu-id="4aff8-196">Credit remaining quantity</span></span></td>
<td><span data-ttu-id="4aff8-197">Se você estiver lançando uma nota de crédito, escolha essa opção para manter a quantidade restante na ordem.</span><span class="sxs-lookup"><span data-stu-id="4aff8-197">If you're posting a credit note, select this option to keep the remaining quantity on order.</span></span> <span data-ttu-id="4aff8-198">Se a opção estiver desmarcada, a quantidade restante será definida como 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="4aff8-198">If this option is cleared, the remaining quantity is set to 0 (zero).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="4aff8-199">Atualização resumida de</span><span class="sxs-lookup"><span data-stu-id="4aff8-199">Summary update for</span></span></td>
<td><span data-ttu-id="4aff8-200">Selecione como várias ordens de venda devem ser resumidas:</span><span class="sxs-lookup"><span data-stu-id="4aff8-200">Select how multiple sales orders should be summarized:</span></span>
<ul>
<li><span data-ttu-id="4aff8-201"><strong>Nenhum</strong> – Não resuma ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-201"><strong>None</strong> – Don't summarize sales orders.</span></span> <span data-ttu-id="4aff8-202">Por exemplo, uma fatura separada será criada para cada ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="4aff8-202">For example, a separate invoice will be created for each sales order.</span></span></li>
<li><span data-ttu-id="4aff8-203"><strong>Conta de fatura</strong> – Resumir todas as ordens selecionadas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-203"><strong>Invoice account</strong> – Summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span></li>
<li><span data-ttu-id="4aff8-204"><strong>Ordem</strong> – resume um intervalo selecionado de ordens em uma ordem especificada.</span><span class="sxs-lookup"><span data-stu-id="4aff8-204"><strong>Order</strong> – Summarize a selected range of orders into one order that you specify.</span></span> <span data-ttu-id="4aff8-205">As ordens são resumidas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-205">The orders are summarized based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="4aff8-206">Se você selecionar esta opção, será necessário selecionar um valor no campo <strong>Ordem de venda</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-206">If you select this option, you must select a value in the <strong>Sales order</strong> field.</span></span></li>
<li><span data-ttu-id="4aff8-207"><strong>Resumo automático</strong> – Se as atualizações de resumo tiverem sido especificadas na página <strong>Atualizações de resumo</strong>, resuma todas as ordens selecionadas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-207"><strong>Automatic summary</strong> – If summary updates have been specified on the <strong>Summary update</strong> page, summarize all selected orders, based on the criteria that are set up on the <strong>Summary update parameters</strong> page.</span></span> <span data-ttu-id="4aff8-208">Se as atualizações resumidas não tiverem sido especificadas, a ordem será lançada separadamente.</span><span class="sxs-lookup"><span data-stu-id="4aff8-208">If summary updates haven't been specified, the order is posted separately.</span></span></li>
<li><span data-ttu-id="4aff8-209"><strong>Guia de remessa</strong> – resume um intervalo selecionado em uma fatura para cada guia de remessa.</span><span class="sxs-lookup"><span data-stu-id="4aff8-209"><strong>Packing slip</strong> – Summarize a selected range of orders into one invoice for each packing slip.</span></span> <span data-ttu-id="4aff8-210">Esse botão está disponível apenas se <strong>Guia de remessa</strong> estiver selecionada no campo <strong>Quantidade</strong>.</span><span class="sxs-lookup"><span data-stu-id="4aff8-210">This option is available only if <strong>Packing slip</strong> is selected in the <strong>Quantity</strong> field.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






