---
title: Gerenciar estoque de armazenamento
description: "Este artigo descreve os tipos de documentos que você pode usar para gerenciar inventário."
author: rubencdelgado
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 21391
ms.assetid: bfef3717-d0e0-491d-8466-d8a9c995177d
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6245d37ace9f46ecce83a0cf80a014d5de898bbc
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="manage-store-inventory"></a><span data-ttu-id="38c17-103">Gerenciar estoque de armazenamento</span><span class="sxs-lookup"><span data-stu-id="38c17-103">Manage store inventory</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="38c17-104">Este artigo descreve os tipos de documentos que você pode usar para gerenciar inventário.</span><span class="sxs-lookup"><span data-stu-id="38c17-104">This article describes the types of documents that you can use to manage inventory.</span></span>

<span data-ttu-id="38c17-105">Você pode usar os tipos de documentos a seguir para gerenciar o estoque da sua organização.</span><span class="sxs-lookup"><span data-stu-id="38c17-105">You can use the following types of documents to manage your organization's inventory.</span></span>

## <a name="purchase-orders"></a><span data-ttu-id="38c17-106">Ordens de compra</span><span class="sxs-lookup"><span data-stu-id="38c17-106">Purchase orders</span></span>
<span data-ttu-id="38c17-107">As ordens de compra são criadas na matriz.</span><span class="sxs-lookup"><span data-stu-id="38c17-107">Purchase orders are created at the head office.</span></span> <span data-ttu-id="38c17-108">Se um armazém de varejo estiver incluído no cabeçalho da ordem de compra, a ordem poderá ser recebida na loja usando o Modern POS (MPOS) ou PDV em Nuvem no Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="38c17-108">If a retail warehouse is included in the purchase order header, the order can be received at the store by using Modern POS (MPOS) or Cloud POS in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="38c17-109">Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional.</span><span class="sxs-lookup"><span data-stu-id="38c17-109">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="38c17-110">Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz.</span><span class="sxs-lookup"><span data-stu-id="38c17-110">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="38c17-111">Na sede, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="38c17-111">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the purchase order.</span></span>

## <a name="transfer-orders"></a><span data-ttu-id="38c17-112">Ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="38c17-112">Transfer orders</span></span>
<span data-ttu-id="38c17-113">Uma ordem de transferência pode especificar que uma loja específica é um local de onde os itens podem ser enviados.</span><span class="sxs-lookup"><span data-stu-id="38c17-113">A transfer order can specify that a particular store is a location that items can be shipped from.</span></span> <span data-ttu-id="38c17-114">Nesse caso, a ordem de transferência aparece na loja como solicitação de separação no MPOS ou PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="38c17-114">In this case, the transfer order appears at the store as a picking request in MPOS or Cloud POS.</span></span> <span data-ttu-id="38c17-115">Após a separação das quantidades solicitadas, elas são confirmadas e enviadas à matriz.</span><span class="sxs-lookup"><span data-stu-id="38c17-115">After the quantities that are requested are picked, they are committed and sent to the head office.</span></span> <span data-ttu-id="38c17-116">Na matriz, as quantidades recebidas e separadas na loja são exibidas no Dynamics 365 for Retail, no campo **Remeter agora** da ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="38c17-116">At the head office, the quantities that were picked at the store are displayed in Dynamics 365 for Retail, in the **Ship now** field on the transfer order.</span></span> <span data-ttu-id="38c17-117">Uma ordem de transferência pode especificar que uma loja específica é um local para onde os itens podem ser enviados.</span><span class="sxs-lookup"><span data-stu-id="38c17-117">A transfer order may specify that a particular store is a location that items can be shipped to.</span></span> <span data-ttu-id="38c17-118">Nesse caso, a ordem de transferência aparece na loja como solicitação de recebimento no MPOS ou PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="38c17-118">In this case, the transfer order appears at the store as a receiving request in MPOS or Cloud POS.</span></span> <span data-ttu-id="38c17-119">Após a especificação das quantidades recebidas na loja, é possível salvá-las localmente para a modificação adicional.</span><span class="sxs-lookup"><span data-stu-id="38c17-119">After the quantities that are received at the store are entered, they can be saved locally for additional modification.</span></span> <span data-ttu-id="38c17-120">Como alternativa, as quantidades podem ser confirmadas e enviadas para a matriz.</span><span class="sxs-lookup"><span data-stu-id="38c17-120">Alternatively, the quantities can be committed and sent to the head office.</span></span> <span data-ttu-id="38c17-121">Na sede, as quantidades recebidas na loja são exibidas no Dynamics 365 for Retail, no campo **Receber agora** na ordem de transferência.</span><span class="sxs-lookup"><span data-stu-id="38c17-121">At the head office, the quantities that were received at the store are displayed in Dynamics 365 for Retail, in the **Receive now** field on the transfer order.</span></span>

## <a name="stock-counts"></a><span data-ttu-id="38c17-122">Contagens de estoque</span><span class="sxs-lookup"><span data-stu-id="38c17-122">Stock counts</span></span>
<span data-ttu-id="38c17-123">Contagens de estoque podem ser agendadas ou não agendadas.</span><span class="sxs-lookup"><span data-stu-id="38c17-123">Stock counts can be either scheduled or unscheduled.</span></span> <span data-ttu-id="38c17-124">As contagens de estoque agendadas são iniciadas na matriz, que especifica os itens que devem ser contados.</span><span class="sxs-lookup"><span data-stu-id="38c17-124">Scheduled stock counts are initiated at the head office, which specifies the items that must be counted.</span></span> <span data-ttu-id="38c17-125">A matriz cria um documento de contagem que pode ser recebido na loja, onde as quantidades disponíveis em estoque reais são inseridas no MPOS ou PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="38c17-125">The head office creates a counting document that can be received at the store, where the quantities of actual on-hand stock are entered in MPOS or Cloud POS.</span></span> <span data-ttu-id="38c17-126">Contagens de estoque não agendadas são iniciadas em uma loja, e as quantidades disponíveis em estoque reais são atualizadas no MPOS ou PDV em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="38c17-126">Unscheduled stock counts are initiated at a store, and the quantities of actual on-hand stock are updated in either MPOS or Cloud POS.</span></span> <span data-ttu-id="38c17-127">Diferente das contagens de estoque agendadas, as contagens de estoque não agendadas não têm uma lista predefinida de itens.</span><span class="sxs-lookup"><span data-stu-id="38c17-127">Unlike scheduled stock counts, unscheduled stock counts do not have a predefined list of items.</span></span> <span data-ttu-id="38c17-128">Quando uma contagem de estoque de qualquer tipo é concluída, ela é confirmada e enviada para a matriz.</span><span class="sxs-lookup"><span data-stu-id="38c17-128">When a stock count of either type is completed, it is committed and sent to the head office.</span></span> <span data-ttu-id="38c17-129">Na matriz, a contagem é validada e lançada.</span><span class="sxs-lookup"><span data-stu-id="38c17-129">At the head office, the count is validated and posted.</span></span>

## <a name="inventory-lookup"></a><span data-ttu-id="38c17-130">Pesquisa de estoque</span><span class="sxs-lookup"><span data-stu-id="38c17-130">Inventory lookup</span></span>
<span data-ttu-id="38c17-131">A quantidade de produtos atual disponível para várias lojas e depósitos pode ser exibida na página de pesquisa Estoque.</span><span class="sxs-lookup"><span data-stu-id="38c17-131">The current product quantity on hand for multiple stores and warehouses can be viewed on the Inventory lookup page.</span></span> <span data-ttu-id="38c17-132">Além da quantidade atual disponível, as quantidades futuras disponíveis para promessa (ATP) podem ser exibidas para cada loja individual.</span><span class="sxs-lookup"><span data-stu-id="38c17-132">In addition to the current quantity on hand, the future available to promise (ATP) quantities can be viewed for each individual store.</span></span> <span data-ttu-id="38c17-133">Para fazê-lo, selecione a loja em que deseja exibir o ATP e clique em **Mostrar disponibilidade da loja**.</span><span class="sxs-lookup"><span data-stu-id="38c17-133">To do so, select the store that you want to view the ATP for and then click **Show store availability**.</span></span>





