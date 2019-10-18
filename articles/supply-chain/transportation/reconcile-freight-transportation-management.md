---
title: Reconciliar frete no gerenciamento de transporte
description: Este tópico descreve o processo de reconciliação de frete.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: eb3ba06f4fa8cc4af952619d06a58e605ff87e2a
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251560"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="a21e4-103">Reconciliar frete no gerenciamento de transporte</span><span class="sxs-lookup"><span data-stu-id="a21e4-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a21e4-104">Este tópico descreve o processo de reconciliação de frete.</span><span class="sxs-lookup"><span data-stu-id="a21e4-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="a21e4-105">Reconciliação de frete pode ser feita manualmente, ou pode ser configurada para ocorrer automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a21e4-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="a21e4-106">Para usar a reconciliação automática de frete, você deve configurar um mestre de auditoria em que você possa definir os critérios que determinam quais listas de frete são comparadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a21e4-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="a21e4-107">O processo de reconciliação de frete</span><span class="sxs-lookup"><span data-stu-id="a21e4-107">The freight reconciliation process</span></span>
<span data-ttu-id="a21e4-108">Taxas de frete são calculadas pelo mecanismo de taxa que está associado com o carro de entrega relevante.</span><span class="sxs-lookup"><span data-stu-id="a21e4-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="a21e4-109">Quando uma carga é confirmada, é gerada uma lista de frete e as taxas de frete são transferidas para ela.</span><span class="sxs-lookup"><span data-stu-id="a21e4-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="a21e4-110">As taxas de frete são particionadas como encargos diversos para o documento de origem relevante (ordem de compra, ordem de venda e ordem de transferência), dependendo da configuração que é usada para o processo normal de cobrança.</span><span class="sxs-lookup"><span data-stu-id="a21e4-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="a21e4-111">O processo de reconciliação de frete (que também é conhecido como o processo de correspondência) pode começar assim que a fatura de frete for recebida da transportadora.</span><span class="sxs-lookup"><span data-stu-id="a21e4-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="a21e4-112">A fatura pode ser recebida de forma eletrônica ou em papel.</span><span class="sxs-lookup"><span data-stu-id="a21e4-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="a21e4-113">Se a fatura for recebida no papel, você pode gerar uma fatura eletrônica usando a cobrança de frete como um modelo.</span><span class="sxs-lookup"><span data-stu-id="a21e4-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="a21e4-114">[![Processo de reconciliação de frete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="a21e4-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="a21e4-115">Reconciliação manual</span><span class="sxs-lookup"><span data-stu-id="a21e4-115">Manual reconciliation</span></span>
<span data-ttu-id="a21e4-116">Se você estiver reconciliando o frete manualmente, você deve corresponder cada linha da fatura com a linha de cobrança de frete ou linhas para a carga que está sendo faturada.</span><span class="sxs-lookup"><span data-stu-id="a21e4-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="a21e4-117">Você faz essa correspondência na página **Conciliação de faturas e notas de frete**.</span><span class="sxs-lookup"><span data-stu-id="a21e4-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="a21e4-118">Se a quantidade na linha da fatura não coincidir com o valor de cobrança de frete, você deve selecionar um motivo de reconciliação para a diferença.</span><span class="sxs-lookup"><span data-stu-id="a21e4-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="a21e4-119">Se existirem vários motivos para reconciliação, você pode dividir o valor incomparável entre elas.</span><span class="sxs-lookup"><span data-stu-id="a21e4-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="a21e4-120">O motivo da reconciliação determina como os valores de diferença são lançados na contabilidade.</span><span class="sxs-lookup"><span data-stu-id="a21e4-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="a21e4-121">Quando a reconciliação do valor da fatura inteira é contabilizada, ela é enviada para aprovação e o diário é lançado.</span><span class="sxs-lookup"><span data-stu-id="a21e4-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="a21e4-122">A ilustração a seguir mostra como gerar uma fatura de frete e executar a reconciliação de frete.</span><span class="sxs-lookup"><span data-stu-id="a21e4-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span> 
<span data-ttu-id="a21e4-123">[![Tarefas de reconciliação de frete](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="a21e4-123">[![Freight reconcilation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="a21e4-124">Reconciliação automática</span><span class="sxs-lookup"><span data-stu-id="a21e4-124">Automatic reconciliation</span></span>
<span data-ttu-id="a21e4-125">Para usar a reconciliação automática, você deve especificar a agenda de reconciliação e as faturas e transportadoras a serem usadas.</span><span class="sxs-lookup"><span data-stu-id="a21e4-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="a21e4-126">A correspondência das linhas da fatura e listas de frete é feita de acordo com a configuração de tipo de cobrança de frete e mestre de auditoria.</span><span class="sxs-lookup"><span data-stu-id="a21e4-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="a21e4-127">Depois de executar a reconciliação automática, você deve lidar com todas as faturas que não são compatíveis com o sistema.</span><span class="sxs-lookup"><span data-stu-id="a21e4-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="a21e4-128">Você deve processar essas faturas manualmente antes de lançar as faturas para pagamento.</span><span class="sxs-lookup"><span data-stu-id="a21e4-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



