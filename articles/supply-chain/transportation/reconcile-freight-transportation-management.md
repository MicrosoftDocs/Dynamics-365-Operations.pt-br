---
title: Reconciliar frete no gerenciamento de transporte
description: Este tópico descreve o processo de reconciliação de frete.
author: MarkusFogelberg
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d523af235d645bd282af07d6a1f617bca5fba2dc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809077"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="23fd1-103">Reconciliar frete no gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="23fd1-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23fd1-104">Este tópico descreve o processo de reconciliação de frete.</span><span class="sxs-lookup"><span data-stu-id="23fd1-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="23fd1-105">Reconciliação de frete pode ser feita manualmente, ou pode ser configurada para ocorrer automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23fd1-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="23fd1-106">Para usar a reconciliação automática de frete, você deve configurar um mestre de auditoria em que você possa definir os critérios que determinam quais listas de frete são comparadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="23fd1-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="23fd1-107">O processo de reconciliação de frete</span><span class="sxs-lookup"><span data-stu-id="23fd1-107">The freight reconciliation process</span></span>

<span data-ttu-id="23fd1-108">Taxas de frete são calculadas pelo mecanismo de taxa que está associado com o carro de entrega relevante.</span><span class="sxs-lookup"><span data-stu-id="23fd1-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="23fd1-109">Quando uma carga é confirmada, é gerada uma lista de frete e as taxas de frete são transferidas para ela.</span><span class="sxs-lookup"><span data-stu-id="23fd1-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="23fd1-110">As taxas de frete são particionadas como encargos diversos para o documento de origem relevante (ordem de compra, ordem de venda e ordem de transferência), dependendo da configuração que é usada para o processo normal de cobrança.</span><span class="sxs-lookup"><span data-stu-id="23fd1-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="23fd1-111">O processo de reconciliação de frete (que também é conhecido como o processo de correspondência) pode começar assim que a fatura de frete for recebida da transportadora.</span><span class="sxs-lookup"><span data-stu-id="23fd1-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="23fd1-112">A fatura pode ser recebida de forma eletrônica ou em papel.</span><span class="sxs-lookup"><span data-stu-id="23fd1-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="23fd1-113">Se a fatura for recebida no papel, você pode gerar uma fatura eletrônica usando a cobrança de frete como um modelo.</span><span class="sxs-lookup"><span data-stu-id="23fd1-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span>

<span data-ttu-id="23fd1-114">[![Processo de reconciliação de frete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="23fd1-114">[![Freight reconciliation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="23fd1-115">Reconciliação manual</span><span class="sxs-lookup"><span data-stu-id="23fd1-115">Manual reconciliation</span></span>

<span data-ttu-id="23fd1-116">Se você estiver reconciliando o frete manualmente, você deve corresponder cada linha da fatura com a linha de cobrança de frete ou linhas para a carga que está sendo faturada.</span><span class="sxs-lookup"><span data-stu-id="23fd1-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="23fd1-117">Você faz essa correspondência na página **Conciliação de faturas e notas de frete**.</span><span class="sxs-lookup"><span data-stu-id="23fd1-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="23fd1-118">Se a quantidade na linha da fatura não coincidir com o valor de cobrança de frete, você deve selecionar um motivo de reconciliação para a diferença.</span><span class="sxs-lookup"><span data-stu-id="23fd1-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="23fd1-119">Se existirem vários motivos para reconciliação, você pode dividir o valor incomparável entre elas.</span><span class="sxs-lookup"><span data-stu-id="23fd1-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="23fd1-120">O motivo da reconciliação determina como os valores de diferença são lançados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="23fd1-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="23fd1-121">Quando a reconciliação do valor da fatura inteira é contabilizada, ela é enviada para aprovação e o diário é lançado.</span><span class="sxs-lookup"><span data-stu-id="23fd1-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="23fd1-122">A ilustração a seguir mostra como gerar uma fatura de frete e executar a reconciliação de frete.</span><span class="sxs-lookup"><span data-stu-id="23fd1-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span>

<span data-ttu-id="23fd1-123">[![Tarefas de reconciliação de frete](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="23fd1-123">[![Freight reconciliation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>

## <a name="automatic-reconciliation"></a><span data-ttu-id="23fd1-124">Reconciliação automática</span><span class="sxs-lookup"><span data-stu-id="23fd1-124">Automatic reconciliation</span></span>

<span data-ttu-id="23fd1-125">Para usar a reconciliação automática, você deve especificar a agenda de reconciliação e as faturas e transportadoras a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="23fd1-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="23fd1-126">A correspondência das linhas da fatura e listas de frete é feita de acordo com a configuração de tipo de cobrança de frete e mestre de auditoria.</span><span class="sxs-lookup"><span data-stu-id="23fd1-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="23fd1-127">Depois de executar a reconciliação automática, você deve lidar com todas as faturas que não são compatíveis com o sistema.</span><span class="sxs-lookup"><span data-stu-id="23fd1-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="23fd1-128">Você deve processar essas faturas manualmente antes de lançar as faturas para pagamento.</span><span class="sxs-lookup"><span data-stu-id="23fd1-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a><span data-ttu-id="23fd1-129">Corresponder as notas de frete às faturas de frete usando reconciliação automática ou manual</span><span class="sxs-lookup"><span data-stu-id="23fd1-129">Match freight bills with freight invoices using automatic or manual reconciliation</span></span>

<span data-ttu-id="23fd1-130">A *correspondência* é o processo de localização das notas de frete que correspondem a cada fatura de frete.</span><span class="sxs-lookup"><span data-stu-id="23fd1-130">*Matching* is the process of finding the freight bills that correspond to each freight invoice.</span></span> <span data-ttu-id="23fd1-131">Isso pode ser feito por meio da correspondência das linhas de fatura uma a uma (correspondência manual) ou por meio da correspondência de todas as faturas disponíveis de uma só vez (correspondência automática).</span><span class="sxs-lookup"><span data-stu-id="23fd1-131">This can be done by matching the invoice lines one-by-one (manual matching), or by matching all available invoices at once (auto matching).</span></span>

### <a name="auto-matching"></a><span data-ttu-id="23fd1-132">Correspondência automática</span><span class="sxs-lookup"><span data-stu-id="23fd1-132">Auto matching</span></span>

<span data-ttu-id="23fd1-133">Ao corresponder várias faturas de frete à mesma nota de frete, o processo de correspondência automática funciona da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="23fd1-133">When matching multiple freight invoices to the same freight bill, the process for auto matching works as follows:</span></span>

1. <span data-ttu-id="23fd1-134">Todas as faturas de frete não correspondidas são classificadas por valor, com o maior valor primeiro.</span><span class="sxs-lookup"><span data-stu-id="23fd1-134">All freight invoices not matched are sorted by amount, with largest amount first.</span></span>
1. <span data-ttu-id="23fd1-135">As faturas de frete são correspondidas uma a uma, até que a nota de frete não tenha nenhum valor positivo restante.</span><span class="sxs-lookup"><span data-stu-id="23fd1-135">The freight invoices are matched one-by-one, until the freight bill has no positive amount remaining.</span></span>
1. <span data-ttu-id="23fd1-136">Dependendo da configuração do mestre de auditoria e do valor restante nas faturas de frete, o valor restante é definido.</span><span class="sxs-lookup"><span data-stu-id="23fd1-136">Depending on the setup of the audit master and the remaining amount on the freight invoices, the remaining amount is set.</span></span>

### <a name="manual-matching"></a><span data-ttu-id="23fd1-137">Correspondência manual</span><span class="sxs-lookup"><span data-stu-id="23fd1-137">Manual matching</span></span>

<span data-ttu-id="23fd1-138">Todas as notas de frete com valores positivos estarão disponíveis para correspondência.</span><span class="sxs-lookup"><span data-stu-id="23fd1-138">All freight bills with positive amounts will be available for matching.</span></span> <span data-ttu-id="23fd1-139">De forma semelhante à correspondência automática, o usuário só poderá fazer a correspondência entre faturas de frete com valores negativos e notas de frete não correspondidas totalmente.</span><span class="sxs-lookup"><span data-stu-id="23fd1-139">Similar to auto matching, the user will only be able to match freight invoices with negative amounts to freight bills not fully matched.</span></span>

### <a name="example"></a><span data-ttu-id="23fd1-140">Exemplo</span><span class="sxs-lookup"><span data-stu-id="23fd1-140">Example</span></span>

<span data-ttu-id="23fd1-141">Suponha que você tenha uma nota de frete (FB) para um valor de 1500 e que tenha criado três faturas de frete para a nota de frete com uma linha de fatura para cada fatura com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="23fd1-141">Suppose that you have a freight bill (FB) for an amount of 1500 and you have created three freight invoices for the freight bill with one invoice line for each invoice with following settings:</span></span>

- <span data-ttu-id="23fd1-142">Nota de frete original (FB): valor 1500</span><span class="sxs-lookup"><span data-stu-id="23fd1-142">Original freight bill (FB): Amount 1500</span></span>
- <span data-ttu-id="23fd1-143">Fatura 1 (Inv1): valor 1000</span><span class="sxs-lookup"><span data-stu-id="23fd1-143">Invoice 1 (Inv1): Amount 1000</span></span>
- <span data-ttu-id="23fd1-144">Fatura 2 (Inv2): valor 600</span><span class="sxs-lookup"><span data-stu-id="23fd1-144">Invoice 2 (Inv2): Amount 600</span></span>
- <span data-ttu-id="23fd1-145">Fatura 3 (Inv3): valor -100</span><span class="sxs-lookup"><span data-stu-id="23fd1-145">Invoice 3 (Inv3): Amount -100</span></span>

#### <a name="automatic-matching-result"></a><span data-ttu-id="23fd1-146">Resultado da correspondência automática</span><span class="sxs-lookup"><span data-stu-id="23fd1-146">Automatic matching result</span></span>

<span data-ttu-id="23fd1-147">A correspondência automática será executada na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="23fd1-147">Auto matching will execute in following order:</span></span>

1. <span data-ttu-id="23fd1-148">Classificar todas as faturas de frete em ordem decrescente por valor: Inv1 -> Inv2 -> Inv3.</span><span class="sxs-lookup"><span data-stu-id="23fd1-148">Sort all freight invoices descending by amount: Inv1 -> Inv2 -> Inv3.</span></span>
1. <span data-ttu-id="23fd1-149">Corresponder Inv1 com FB.</span><span class="sxs-lookup"><span data-stu-id="23fd1-149">Match Inv1 with FB.</span></span> <span data-ttu-id="23fd1-150">Inv1 tem 1000 correspondido e FB tem um valor restante de 500, portanto, o status é definido como *Parcialmente correspondido*.</span><span class="sxs-lookup"><span data-stu-id="23fd1-150">Inv1 has 1000 matched and FB has 500 amount remaining, so the status is set to *Partially matched*.</span></span>
1. <span data-ttu-id="23fd1-151">Corresponder Inv2 com FB.</span><span class="sxs-lookup"><span data-stu-id="23fd1-151">Match Inv2 with FB.</span></span> <span data-ttu-id="23fd1-152">Inv2 tem 500 correspondido e FB tem um valor restante de 0, portanto, o status é definido como *Totalmente correspondido*.</span><span class="sxs-lookup"><span data-stu-id="23fd1-152">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="23fd1-153">Como FB agora foi totalmente correspondida, Inv3 não será processada.</span><span class="sxs-lookup"><span data-stu-id="23fd1-153">Because FB is now fully matched, Inv3 won't be processed.</span></span>

#### <a name="manual-matching-result"></a><span data-ttu-id="23fd1-154">Resultado da correspondência manual</span><span class="sxs-lookup"><span data-stu-id="23fd1-154">Manual matching result</span></span>

<span data-ttu-id="23fd1-155">Para a correspondência manual, os resultados variam de acordo com a ordem da correspondência, conforme ilustrado nos casos de exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="23fd1-155">For manual matching, the results vary depending on the order of the matching, as illustrated in the following example cases.</span></span>

##### <a name="manual-matching-case-1"></a><span data-ttu-id="23fd1-156">Caso de correspondência manual 1</span><span class="sxs-lookup"><span data-stu-id="23fd1-156">Manual matching case 1</span></span>

<span data-ttu-id="23fd1-157">Uma forma de fazer a correspondência manual para esse exemplo é proceder da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="23fd1-157">One way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="23fd1-158">Corresponder FB com Inv1.</span><span class="sxs-lookup"><span data-stu-id="23fd1-158">Match FB with Inv1.</span></span> <span data-ttu-id="23fd1-159">FB tem um valor restante de 500, portanto, o status é definido como *Parcialmente correspondido*.</span><span class="sxs-lookup"><span data-stu-id="23fd1-159">FB has 500 amount remaining, so the status set to *Partially matched*.</span></span>
1. <span data-ttu-id="23fd1-160">Corresponder Inv2 com FB.</span><span class="sxs-lookup"><span data-stu-id="23fd1-160">Match Inv2 with FB.</span></span> <span data-ttu-id="23fd1-161">Inv2 tem 500 correspondido e FB tem um valor restante de 0, portanto, o status é definido como *Totalmente correspondido*.</span><span class="sxs-lookup"><span data-stu-id="23fd1-161">Inv2 has 500 matched and FB has 0 remaining, so the status is set to *Fully matched*.</span></span>
1. <span data-ttu-id="23fd1-162">Ao fazer a correspondência manual de Inv3, você não encontrará nenhuma nota de frete não correspondida.</span><span class="sxs-lookup"><span data-stu-id="23fd1-162">When manually matching Inv3, you won't find any unmatched freight bills.</span></span>

<span data-ttu-id="23fd1-163">Esse caso é essencialmente igual à correspondência automática</span><span class="sxs-lookup"><span data-stu-id="23fd1-163">This case is essentially the same as auto matching</span></span>

##### <a name="manual-matching-case-2"></a><span data-ttu-id="23fd1-164">Caso de correspondência manual 2</span><span class="sxs-lookup"><span data-stu-id="23fd1-164">Manual matching case 2</span></span>

<span data-ttu-id="23fd1-165">Outra forma de fazer a correspondência manual para esse exemplo é proceder da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="23fd1-165">Another way to do manual matching for this example is to proceed as follows:</span></span>

1. <span data-ttu-id="23fd1-166">Corresponder Inv3 com FB.</span><span class="sxs-lookup"><span data-stu-id="23fd1-166">Match Inv3 with FB.</span></span> <span data-ttu-id="23fd1-167">Agora, FB tem um valor restante de 1600, que é o mesmo que subtrair 100 negativo de 1500.</span><span class="sxs-lookup"><span data-stu-id="23fd1-167">Now FB has amount remaining 1600, which is the same as subtracting negative 100 on top of 1500.</span></span> <span data-ttu-id="23fd1-168">FB e Inv3 têm uma quantidade correspondida de -100.</span><span class="sxs-lookup"><span data-stu-id="23fd1-168">Both FB and Inv3 have a matched quantity of -100.</span></span>
1. <span data-ttu-id="23fd1-169">Corresponder Inv1 e Inv2 com FB uma após a outra.</span><span class="sxs-lookup"><span data-stu-id="23fd1-169">Match Inv1 and Inv 2 with FB one after another.</span></span> <span data-ttu-id="23fd1-170">FB é totalmente correspondida.</span><span class="sxs-lookup"><span data-stu-id="23fd1-170">FB is fully matched.</span></span>

<span data-ttu-id="23fd1-171">Como mostra esse exemplo, a correspondência de faturas de frete com valores negativos só deve ser feita manualmente.</span><span class="sxs-lookup"><span data-stu-id="23fd1-171">As this example shows, matching freight invoices with negative amounts should only be done manually.</span></span> <span data-ttu-id="23fd1-172">Isso garantirá que sempre seja possível corresponder as faturas de frete com valores negativos a uma nota de frete não correspondida totalmente porque isso permite controlar a sequência de correspondência.</span><span class="sxs-lookup"><span data-stu-id="23fd1-172">This will ensure that it is always possible to match the freight invoices with negative amounts to a freight bill not fully matched because that enables you to control the matching sequence.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]