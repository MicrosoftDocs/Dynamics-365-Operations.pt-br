---
title: Reconciliar frete manualmente
description: Este procedimento mostra como reconciliar manualmente o frete.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 386c035fb84b1f88cf53837a1e875eb2aa8ba910
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3146298"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="708ed-103">Reconciliar frete manualmente</span><span class="sxs-lookup"><span data-stu-id="708ed-103">Reconcile freight manually</span></span>

<span data-ttu-id="708ed-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="708ed-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="708ed-105">Este procedimento mostra como reconciliar manualmente o frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="708ed-106">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="708ed-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="708ed-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="708ed-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="708ed-108">Selecione uma carga para reconciliar</span><span class="sxs-lookup"><span data-stu-id="708ed-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="708ed-109">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="708ed-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="708ed-110">Desmarque a caixa de seleção Esconder envio e recebido.</span><span class="sxs-lookup"><span data-stu-id="708ed-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="708ed-111">Na lista, selecione custo indireto que tem a identificação ID 00006 de carga.</span><span class="sxs-lookup"><span data-stu-id="708ed-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="708ed-112">Criar uma fatura da transportadora</span><span class="sxs-lookup"><span data-stu-id="708ed-112">Create a carrier invoice</span></span>
<span data-ttu-id="708ed-113">Quando você reconciliar o frete manualmente e não receber notas fiscais da transportadora automaticamente, você pode criar uma nota fiscal com base na conta de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="708ed-114">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="708ed-114">Click Related information.</span></span>
2. <span data-ttu-id="708ed-115">Clique em Detalhes da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="708ed-116">Clique em gerar fatura da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="708ed-117">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="708ed-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="708ed-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="708ed-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="708ed-119">Reconciliar a fatura</span><span class="sxs-lookup"><span data-stu-id="708ed-119">Reconcile the invoice</span></span>
<span data-ttu-id="708ed-120">Quando você reconciliar uma nota fiscal da transportadora e uma conta de frete, isso é feito linha por linha.</span><span class="sxs-lookup"><span data-stu-id="708ed-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="708ed-121">Clique em Fazer correspondência de faturas e notas de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="708ed-122">Expanda a seção Detalhes de fatura.</span><span class="sxs-lookup"><span data-stu-id="708ed-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="708ed-123">Expanda a seção não correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="708ed-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="708ed-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="708ed-125">Clique em Corresponder.</span><span class="sxs-lookup"><span data-stu-id="708ed-125">Click Match.</span></span>
6. <span data-ttu-id="708ed-126">Expanda a seção correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="708ed-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="708ed-127">Enviar a fatura para aprovação</span><span class="sxs-lookup"><span data-stu-id="708ed-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="708ed-128">Clique em Enviar para aprovação.</span><span class="sxs-lookup"><span data-stu-id="708ed-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="708ed-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="708ed-129">Close the page.</span></span>
3. <span data-ttu-id="708ed-130">Desmarque a caixa de seleção Ocultar aprovado.</span><span class="sxs-lookup"><span data-stu-id="708ed-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="708ed-131">Clique em Diários de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="708ed-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="708ed-132">Clique para seguir o link no campo Número de referência do diário.</span><span class="sxs-lookup"><span data-stu-id="708ed-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="708ed-133">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="708ed-133">Click Lines.</span></span>

