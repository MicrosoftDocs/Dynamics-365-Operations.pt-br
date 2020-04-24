---
title: Reconciliar frete manualmente
description: Este procedimento mostra como reconciliar manualmente o frete.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a0ff9aa1070272dd2cee357fb4fc001ffff8df1
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206164"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="88f33-103">Reconciliar frete manualmente</span><span class="sxs-lookup"><span data-stu-id="88f33-103">Reconcile freight manually</span></span>

<span data-ttu-id="88f33-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="88f33-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="88f33-105">Este procedimento mostra como reconciliar manualmente o frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="88f33-106">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="88f33-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="88f33-107">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="88f33-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="88f33-108">Selecione uma carga para reconciliar</span><span class="sxs-lookup"><span data-stu-id="88f33-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="88f33-109">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="88f33-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="88f33-110">Desmarque a caixa de seleção Esconder envio e recebido.</span><span class="sxs-lookup"><span data-stu-id="88f33-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="88f33-111">Na lista, selecione custo indireto que tem a identificação ID 00006 de carga.</span><span class="sxs-lookup"><span data-stu-id="88f33-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="88f33-112">Criar uma fatura da transportadora</span><span class="sxs-lookup"><span data-stu-id="88f33-112">Create a carrier invoice</span></span>
<span data-ttu-id="88f33-113">Quando você reconciliar o frete manualmente e não receber notas fiscais da transportadora automaticamente, você pode criar uma nota fiscal com base na conta de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="88f33-114">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="88f33-114">Click Related information.</span></span>
2. <span data-ttu-id="88f33-115">Clique em Detalhes da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="88f33-116">Clique em gerar fatura da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="88f33-117">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="88f33-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="88f33-118">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="88f33-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="88f33-119">Reconciliar a fatura</span><span class="sxs-lookup"><span data-stu-id="88f33-119">Reconcile the invoice</span></span>
<span data-ttu-id="88f33-120">Quando você reconciliar uma nota fiscal da transportadora e uma conta de frete, isso é feito linha por linha.</span><span class="sxs-lookup"><span data-stu-id="88f33-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="88f33-121">Clique em Fazer correspondência de faturas e notas de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="88f33-122">Expanda a seção Detalhes de fatura.</span><span class="sxs-lookup"><span data-stu-id="88f33-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="88f33-123">Expanda a seção não correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="88f33-124">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="88f33-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="88f33-125">Clique em Corresponder.</span><span class="sxs-lookup"><span data-stu-id="88f33-125">Click Match.</span></span>
6. <span data-ttu-id="88f33-126">Expanda a seção correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="88f33-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="88f33-127">Enviar a fatura para aprovação</span><span class="sxs-lookup"><span data-stu-id="88f33-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="88f33-128">Clique em Enviar para aprovação.</span><span class="sxs-lookup"><span data-stu-id="88f33-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="88f33-129">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="88f33-129">Close the page.</span></span>
3. <span data-ttu-id="88f33-130">Desmarque a caixa de seleção Ocultar aprovado.</span><span class="sxs-lookup"><span data-stu-id="88f33-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="88f33-131">Clique em Diários de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="88f33-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="88f33-132">Clique para seguir o link no campo Número de referência do diário.</span><span class="sxs-lookup"><span data-stu-id="88f33-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="88f33-133">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="88f33-133">Click Lines.</span></span>

