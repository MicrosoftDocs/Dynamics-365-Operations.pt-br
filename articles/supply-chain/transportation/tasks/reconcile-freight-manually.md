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
ms.openlocfilehash: ec17fc31df1daed943f9bc3f4cbe25a683c8ac7e
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026305"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="4e053-103">Reconciliar frete manualmente</span><span class="sxs-lookup"><span data-stu-id="4e053-103">Reconcile freight manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e053-104">Este procedimento mostra como reconciliar manualmente o frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="4e053-105">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="4e053-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="4e053-106">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="4e053-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="4e053-107">Selecione uma carga para reconciliar</span><span class="sxs-lookup"><span data-stu-id="4e053-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="4e053-108">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="4e053-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="4e053-109">Desmarque a caixa de seleção Esconder envio e recebido.</span><span class="sxs-lookup"><span data-stu-id="4e053-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="4e053-110">Na lista, selecione custo indireto que tem a identificação ID 00006 de carga.</span><span class="sxs-lookup"><span data-stu-id="4e053-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="4e053-111">Criar uma fatura da transportadora</span><span class="sxs-lookup"><span data-stu-id="4e053-111">Create a carrier invoice</span></span>
<span data-ttu-id="4e053-112">Quando você reconciliar o frete manualmente e não receber notas fiscais da transportadora automaticamente, você pode criar uma nota fiscal com base na conta de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="4e053-113">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="4e053-113">Click Related information.</span></span>
2. <span data-ttu-id="4e053-114">Clique em Detalhes da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="4e053-115">Clique em gerar fatura da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="4e053-116">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="4e053-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="4e053-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="4e053-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="4e053-118">Reconciliar a fatura</span><span class="sxs-lookup"><span data-stu-id="4e053-118">Reconcile the invoice</span></span>
<span data-ttu-id="4e053-119">Quando você reconciliar uma nota fiscal da transportadora e uma conta de frete, isso é feito linha por linha.</span><span class="sxs-lookup"><span data-stu-id="4e053-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="4e053-120">Clique em Fazer correspondência de faturas e notas de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="4e053-121">Expanda a seção Detalhes de fatura.</span><span class="sxs-lookup"><span data-stu-id="4e053-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="4e053-122">Expanda a seção não correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="4e053-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="4e053-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="4e053-124">Clique em Corresponder.</span><span class="sxs-lookup"><span data-stu-id="4e053-124">Click Match.</span></span>
6. <span data-ttu-id="4e053-125">Expanda a seção correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="4e053-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="4e053-126">Enviar a fatura para aprovação</span><span class="sxs-lookup"><span data-stu-id="4e053-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="4e053-127">Clique em Enviar para aprovação.</span><span class="sxs-lookup"><span data-stu-id="4e053-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="4e053-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="4e053-128">Close the page.</span></span>
3. <span data-ttu-id="4e053-129">Desmarque a caixa de seleção Ocultar aprovado.</span><span class="sxs-lookup"><span data-stu-id="4e053-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="4e053-130">Clique em Diários de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4e053-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="4e053-131">Clique para seguir o link no campo Número de referência do diário.</span><span class="sxs-lookup"><span data-stu-id="4e053-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="4e053-132">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="4e053-132">Click Lines.</span></span>

