---
title: Ordens de quarentena
description: "Este tópico descreve como as ordens de quarentena são usadas para bloquear o estoque."
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 515f14e72137f7299093cc6e75cb8e6eec2893fb
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="quarantine-orders"></a><span data-ttu-id="c6b43-103">Ordens de quarentena</span><span class="sxs-lookup"><span data-stu-id="c6b43-103">Quarantine orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c6b43-104">Este tópico descreve como as ordens de quarentena são usadas para bloquear o estoque.</span><span class="sxs-lookup"><span data-stu-id="c6b43-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="c6b43-105">As ordens de quarentena podem ser usadas para bloquear o estoque.</span><span class="sxs-lookup"><span data-stu-id="c6b43-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="c6b43-106">Por exemplo, talvez você deseje quarentena itens por motivos de controle de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c6b43-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="c6b43-107">Estoque que ficou em quarentena transferido para um depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="c6b43-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="c6b43-108">**Observação:** se você estiver usando processos avançados de gerenciamento de depósito (em Gerenciamento de depósito), o processamento da ordem de quarentena será usado somente para devolver ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="c6b43-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="c6b43-109">Itens de estoque disponíveis em quarentena</span><span class="sxs-lookup"><span data-stu-id="c6b43-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="c6b43-110">Ao colocar itens em quarentena, você pode criar ordens de quarentena manualmente ou configurar o sistema para criar automaticamente ordens de quarentena durante o processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="c6b43-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="c6b43-111">Para criar automaticamente ordens de quarentena, selecione a opção **Gerenciamento de quarentena** na guia **Políticas de estoque** na página **Grupos de modelos de item**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="c6b43-112">Você também deve especificar um depósito de quarentena padrão no campo **Depósito de quarentena** para os depósitos de recebimento.</span><span class="sxs-lookup"><span data-stu-id="c6b43-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="c6b43-113">Quando o estoque fisicamente disponível for registrado em uma ordem de compra ou em uma ordem de produção, os itens em quarentena serão automaticamente movidos para um depósito de quarentena no Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c6b43-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="c6b43-114">Esse movimento ocorre porque o status da ordem de quarentena é alterado para **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="c6b43-115">Quando você cria ordens de quarentena manualmente, o item não precisa ser configurado para gerenciamento de quarentena no grupo de modelos do item associado.</span><span class="sxs-lookup"><span data-stu-id="c6b43-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="c6b43-116">Para esse processo, você deve especificar o estoque disponível que deve estar em quarentena e o depósito de quarentena que deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="c6b43-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="c6b43-117">Você pode usar os status da ordem de quarentena para ajudar a planejar o processo.</span><span class="sxs-lookup"><span data-stu-id="c6b43-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="c6b43-118">Status da ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="c6b43-118">Quarantine order statuses</span></span>
<span data-ttu-id="c6b43-119">As ordens de quarentena podem ter os seguintes status:</span><span class="sxs-lookup"><span data-stu-id="c6b43-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="c6b43-120">Criado em</span><span class="sxs-lookup"><span data-stu-id="c6b43-120">Created</span></span>
-   <span data-ttu-id="c6b43-121">Iniciado</span><span class="sxs-lookup"><span data-stu-id="c6b43-121">Started</span></span>
-   <span data-ttu-id="c6b43-122">Relatado como concluído</span><span class="sxs-lookup"><span data-stu-id="c6b43-122">Reported as finished</span></span>
-   <span data-ttu-id="c6b43-123">Concluído</span><span class="sxs-lookup"><span data-stu-id="c6b43-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="c6b43-124">Criado em</span><span class="sxs-lookup"><span data-stu-id="c6b43-124">Created</span></span>

<span data-ttu-id="c6b43-125">Quando uma ordem de quarentena tiver sido criada manualmente, mas o item ainda não estiver colocado no depósito de quarentena, a ordem de quarentena fica com o status **Criado**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="c6b43-126">Duas transações de estoque são geradas.</span><span class="sxs-lookup"><span data-stu-id="c6b43-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="c6b43-127">Uma transação é uma transação de saída que pode ter um status **Na ordem**, **Qtd. reservada** ou **Separado**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="c6b43-128">A outra transação é uma transação de de recebimento que pode ter o status **Encomendado** ou **Registrado** no depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="c6b43-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="c6b43-129">Você pode reservar, separar e registrar atualizações no estoque usando os processos normais.</span><span class="sxs-lookup"><span data-stu-id="c6b43-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="c6b43-130">Iniciado</span><span class="sxs-lookup"><span data-stu-id="c6b43-130">Started</span></span>

<span data-ttu-id="c6b43-131">Quando uma ordem de quarentena tem o status **Iniciado**, o estoque é transferido do depósito normal para o depósito de quarentena, e duas transações de estoque são geradas.</span><span class="sxs-lookup"><span data-stu-id="c6b43-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="c6b43-132">Uma transação tem o status **Deduzido** e a outra transação, o status **Recebido**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="c6b43-133">Ao mesmo tempo, duas transações de estoque são criadas para tratar da transferência de retorno.</span><span class="sxs-lookup"><span data-stu-id="c6b43-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="c6b43-134">Essas transações não são datadas.</span><span class="sxs-lookup"><span data-stu-id="c6b43-134">These transactions aren't dated.</span></span> <span data-ttu-id="c6b43-135">Uma transação tem o status **Qtd. reservada** e a outra transação, o status **Encomendado**.</span><span class="sxs-lookup"><span data-stu-id="c6b43-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="c6b43-136">Relatado como concluído</span><span class="sxs-lookup"><span data-stu-id="c6b43-136">Reported as finished</span></span>

<span data-ttu-id="c6b43-137">Ao clicar em **Relatar como concluído**, você poderá relatar uma ordem de quarentena iniciada como concluída.</span><span class="sxs-lookup"><span data-stu-id="c6b43-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="c6b43-138">O item é liberado da quarentena, mas ainda não é retornado para o depósito normal.</span><span class="sxs-lookup"><span data-stu-id="c6b43-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="c6b43-139">O movimento de volta ao depósito normal pode ser processado por meio de um diário de entrada de item que pode ser inicializado durante o processo Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="c6b43-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="c6b43-140">Concluído</span><span class="sxs-lookup"><span data-stu-id="c6b43-140">Ended</span></span>

<span data-ttu-id="c6b43-141">Quando uma ordem de quarentena é finalizada, o item é movido do depósito de quarentena para o depósito normal novamente.</span><span class="sxs-lookup"><span data-stu-id="c6b43-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="c6b43-142">O status da transação de item é definido como **Vendido** no depósito de quarentena e como **Comprado** no depósito normal.</span><span class="sxs-lookup"><span data-stu-id="c6b43-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="c6b43-143">Sucata da ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="c6b43-143">Quarantine order scrap</span></span>
<span data-ttu-id="c6b43-144">Como parte do processo da ordem de quarentena, você pode sucatear o estoque.</span><span class="sxs-lookup"><span data-stu-id="c6b43-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="c6b43-145">Ao processar a sucata, o status do estoque será definido como **Vendido** por uma transação de saída no depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="c6b43-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="see-also"></a><span data-ttu-id="c6b43-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c6b43-146">See also</span></span>
--------

[<span data-ttu-id="c6b43-147">Bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="c6b43-147">Inventory blocking</span></span>](inventory-blocking.md)

