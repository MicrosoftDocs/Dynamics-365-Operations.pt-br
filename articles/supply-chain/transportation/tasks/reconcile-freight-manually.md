--- 
title: Reconciliar frete manualmente
description: Este procedimento mostra como reconciliar manualmente o frete.
author: BibiSp
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c347f8bb0dd36ab4a18cbf6ccd16855efb1bc355
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="314a3-103">Reconciliar frete manualmente</span><span class="sxs-lookup"><span data-stu-id="314a3-103">Reconcile freight manually</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="314a3-104">Este procedimento mostra como reconciliar manualmente o frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="314a3-105">Normalmente isso é feito por um coordenador de transporte.</span><span class="sxs-lookup"><span data-stu-id="314a3-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="314a3-106">Você pode usar este procedimento na empresa USMF de dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="314a3-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="314a3-107">Selecione uma carga para reconciliar</span><span class="sxs-lookup"><span data-stu-id="314a3-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="314a3-108">Vá para Gerenciamento de transporte > Planejamento > Bancada de planejamento de carga.</span><span class="sxs-lookup"><span data-stu-id="314a3-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="314a3-109">Desmarque a caixa de seleção Esconder envio e recebido.</span><span class="sxs-lookup"><span data-stu-id="314a3-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="314a3-110">Na lista, selecione custo indireto que tem a identificação ID 00006 de carga.</span><span class="sxs-lookup"><span data-stu-id="314a3-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="314a3-111">Criar uma fatura da transportadora</span><span class="sxs-lookup"><span data-stu-id="314a3-111">Create a carrier invoice</span></span>
    * <span data-ttu-id="314a3-112">Quando você reconciliar o frete manualmente e não receber notas fiscais da transportadora automaticamente, você pode criar uma nota fiscal com base na conta de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="314a3-113">Clique em Informações Relacionadas.</span><span class="sxs-lookup"><span data-stu-id="314a3-113">Click Related information.</span></span>
2. <span data-ttu-id="314a3-114">Clique em Detalhes da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="314a3-115">Clique em gerar fatura da nota de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="314a3-116">No campo Fatura, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="314a3-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="314a3-117">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="314a3-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="314a3-118">Reconciliar a fatura</span><span class="sxs-lookup"><span data-stu-id="314a3-118">Reconcile the invoice</span></span>
    * <span data-ttu-id="314a3-119">Quando você reconciliar uma nota fiscal da transportadora e uma conta de frete, isso é feito linha por linha.</span><span class="sxs-lookup"><span data-stu-id="314a3-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="314a3-120">Clique em Fazer correspondência de faturas e notas de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="314a3-121">Expanda a seção Detalhes de fatura.</span><span class="sxs-lookup"><span data-stu-id="314a3-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="314a3-122">Expanda a seção não correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="314a3-123">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="314a3-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="314a3-124">Clique em Corresponder.</span><span class="sxs-lookup"><span data-stu-id="314a3-124">Click Match.</span></span>
6. <span data-ttu-id="314a3-125">Expanda a seção correspondida de detalhes da conta de frete.</span><span class="sxs-lookup"><span data-stu-id="314a3-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="314a3-126">Enviar a fatura para aprovação</span><span class="sxs-lookup"><span data-stu-id="314a3-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="314a3-127">Clique em Enviar para aprovação.</span><span class="sxs-lookup"><span data-stu-id="314a3-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="314a3-128">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="314a3-128">Close the page.</span></span>
3. <span data-ttu-id="314a3-129">Desmarque a caixa de seleção Ocultar aprovado.</span><span class="sxs-lookup"><span data-stu-id="314a3-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="314a3-130">Clique em Diários de fatura de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="314a3-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="314a3-131">Clique para seguir o link no campo Número de referência do diário.</span><span class="sxs-lookup"><span data-stu-id="314a3-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="314a3-132">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="314a3-132">Click Lines.</span></span>


