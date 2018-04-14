--- 
title: "Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens"
description: "Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando “depósito básico“ no módulo de gerenciamento de estoque."
author: BibiSp
manager: AnnBe
ms.date: 11/14/2016
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
ms.openlocfilehash: ab824bd99347cbd090e99435217f9ce8ae992b3d
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-arrival-journal"></a><span data-ttu-id="b8888-103">Registrar itens para um item básico com armazenamento habilitado usando um diário de entrada de itens</span><span class="sxs-lookup"><span data-stu-id="b8888-103">Register items for a basic warehousing enabled item using an item arrival journal</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8888-104">Este procedimento mostra como registrar itens usando o diário de entrada de itens quando estiver usando “depósito básico“ no módulo de gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="b8888-104">This procedure shows you how to register items using the item arrival journal when you are using “basic warehousing” in the Inventory management module.</span></span> <span data-ttu-id="b8888-105">Normalmente isso é feito por um vendedor de remessa.</span><span class="sxs-lookup"><span data-stu-id="b8888-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="b8888-106">Você pode executar oeste procedimento na empresa USMF com dados de demonstração usando os valores de exemplo mostrados.</span><span class="sxs-lookup"><span data-stu-id="b8888-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="b8888-107">Se você não estiver usando USMF, você precisa ter uma ordem de compra confirmada com uma linha de ordem de compra aberta antes de dar início a este guia.</span><span class="sxs-lookup"><span data-stu-id="b8888-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="b8888-108">O item da linha deve ser armazenado, e não deve usar grades de produto, e não deve ter dimensões de rastreamento.</span><span class="sxs-lookup"><span data-stu-id="b8888-108">The item on the line must be stocked, and it must not use product variants, and must not have tracking dimensions.</span></span> <span data-ttu-id="b8888-109">E o item precisa estar associado a um grupo de dimensões de armazenamento, onde o site e o depósito estão ativos.</span><span class="sxs-lookup"><span data-stu-id="b8888-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="b8888-110">Criar cabeçalho de diário de entrada de itens.</span><span class="sxs-lookup"><span data-stu-id="b8888-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="b8888-111">Vá para Gerenciamento de estoque > Entradas de diário > Chegada de item > Chegada de item.</span><span class="sxs-lookup"><span data-stu-id="b8888-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="b8888-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b8888-112">Click New.</span></span>
3. <span data-ttu-id="b8888-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8888-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="b8888-114">Se você estiver usando USMF, você pode digitar WHS.</span><span class="sxs-lookup"><span data-stu-id="b8888-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="b8888-115">Se você estiver usando outros dados, o diário cujo nome você escolheu precisará ter as seguintes propriedades: o local de separação de verificação deve ser definido como Não, e o gerenciamento de quarentena deve ser definido como Não.</span><span class="sxs-lookup"><span data-stu-id="b8888-115">If you’re using other data, the journal whose name you choose has to have the following properties: check picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="b8888-116">No campo Guia de remessa, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b8888-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="b8888-117">Este é o ID da guia de remessa da guia de remessa emitido pelo fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b8888-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="b8888-118">Adicionar um número único.</span><span class="sxs-lookup"><span data-stu-id="b8888-118">Add a unique number.</span></span>  
5. <span data-ttu-id="b8888-119">No campo Número, selecione a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b8888-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="b8888-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8888-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="b8888-121">Adicionar linhas ao diário de chegada de item</span><span class="sxs-lookup"><span data-stu-id="b8888-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="b8888-122">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="b8888-122">Click Functions.</span></span>
2. <span data-ttu-id="b8888-123">Clique em Criar linhas.</span><span class="sxs-lookup"><span data-stu-id="b8888-123">Click Create lines.</span></span>
    * <span data-ttu-id="b8888-124">As linhas podem ser inseridas manualmente no diário ou ser criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b8888-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="b8888-125">Isso mostrará como criar essas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b8888-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="b8888-126">Marcar ou desmarcar a caixa de seleção Iniciar quantidade.</span><span class="sxs-lookup"><span data-stu-id="b8888-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="b8888-127">Isso inicializará a quantidade nas linhas do diário com a quantidade não registrada da linha da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b8888-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="b8888-128">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8888-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="b8888-129">Lançar o diário</span><span class="sxs-lookup"><span data-stu-id="b8888-129">Post the journal</span></span>
1. <span data-ttu-id="b8888-130">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="b8888-130">Click Post.</span></span>
2. <span data-ttu-id="b8888-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8888-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="b8888-132">Gerar o recebimento de produtos</span><span class="sxs-lookup"><span data-stu-id="b8888-132">Generate the product receipt</span></span>
1. <span data-ttu-id="b8888-133">Clique em Funções.</span><span class="sxs-lookup"><span data-stu-id="b8888-133">Click Functions.</span></span>
2. <span data-ttu-id="b8888-134">Clique em Recebimento de produtos.</span><span class="sxs-lookup"><span data-stu-id="b8888-134">Click Product receipt.</span></span>
3. <span data-ttu-id="b8888-135">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b8888-135">Click OK.</span></span>


