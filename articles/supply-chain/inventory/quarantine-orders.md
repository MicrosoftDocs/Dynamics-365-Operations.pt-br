---
title: Ordens de quarentena
description: Este tópico descreve como usar ordens de quarentena para bloquear o estoque.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956173"
---
# <a name="quarantine-orders"></a><span data-ttu-id="f3624-103">Ordens de quarentena</span><span class="sxs-lookup"><span data-stu-id="f3624-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3624-104">Este tópico descreve como usar ordens de quarentena para bloquear o estoque.</span><span class="sxs-lookup"><span data-stu-id="f3624-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="f3624-105">As ordens de quarentena permitem bloquear o estoque.</span><span class="sxs-lookup"><span data-stu-id="f3624-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="f3624-106">Por exemplo, talvez você deseje quarentena itens por motivos de controle de qualidade.</span><span class="sxs-lookup"><span data-stu-id="f3624-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="f3624-107">Estoque que ficou em quarentena transferido para um depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="f3624-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="f3624-108">Se você estiver usando processos avançados de gerenciamento de depósito (em Gerenciamento de depósito), o processamento da ordem de quarentena será usado somente para ordens de venda de devolução.</span><span class="sxs-lookup"><span data-stu-id="f3624-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="f3624-109">Itens de estoque disponíveis em quarentena</span><span class="sxs-lookup"><span data-stu-id="f3624-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="f3624-110">Ao colocar itens em quarentena, você pode criar as ordens de quarentena manualmente ou configurar o sistema para criá-las de forma automática durante o processamento de entrada.</span><span class="sxs-lookup"><span data-stu-id="f3624-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="f3624-111">Para configurar o sistema para gerar ordens de quarentena automaticamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f3624-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="f3624-112">Vá para **Gerenciamento de estoque \> Configuração \> Estoque \> Grupos de modelos de item**.</span><span class="sxs-lookup"><span data-stu-id="f3624-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="f3624-113">Selecione um grupo de modelos relevante no painel de lista ou crie um novo grupo de modelos.</span><span class="sxs-lookup"><span data-stu-id="f3624-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="f3624-114">Na FastTab **Políticas de estoque**, marque a caixa de seleção **Gerenciamento de quarentena**.</span><span class="sxs-lookup"><span data-stu-id="f3624-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="f3624-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f3624-115">Close the page.</span></span>
1. <span data-ttu-id="f3624-116">No campo **Depósito de quarentena** dos depósitos de recebimento, especifique um depósito de quarentena padrão.</span><span class="sxs-lookup"><span data-stu-id="f3624-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="f3624-117">Quando um item registrado como recebido no depósito pertence a um grupo de modelos no qual a caixa de seleção **Gerenciamento de quarentena** está marcada, o sistema gera uma ordem de quarentena para ele.</span><span class="sxs-lookup"><span data-stu-id="f3624-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="f3624-118">A ordem de quarentena instrui os trabalhadores a mover o item para o depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="f3624-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="f3624-119">Quando você cria ordens de quarentena manualmente na página **Ordens de quarentena**, o item não precisa ser configurado para gerenciamento de quarentena no grupo de modelos de item associado.</span><span class="sxs-lookup"><span data-stu-id="f3624-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="f3624-120">Para esse processo, você deve especificar o estoque disponível que deve estar em quarentena e o depósito de quarentena que deve ser usado.</span><span class="sxs-lookup"><span data-stu-id="f3624-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="f3624-121">Você pode usar os status da ordem de quarentena para ajudar a planejar o processo.</span><span class="sxs-lookup"><span data-stu-id="f3624-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="f3624-122">Status da ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="f3624-122">Quarantine order statuses</span></span>

<span data-ttu-id="f3624-123">As ordens de quarentena podem ter os seguintes status:</span><span class="sxs-lookup"><span data-stu-id="f3624-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="f3624-124">Criado em</span><span class="sxs-lookup"><span data-stu-id="f3624-124">Created</span></span>
- <span data-ttu-id="f3624-125">Iniciado</span><span class="sxs-lookup"><span data-stu-id="f3624-125">Started</span></span>
- <span data-ttu-id="f3624-126">Relatado como concluído</span><span class="sxs-lookup"><span data-stu-id="f3624-126">Reported as finished</span></span>
- <span data-ttu-id="f3624-127">Concluído</span><span class="sxs-lookup"><span data-stu-id="f3624-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="f3624-128">Criado em</span><span class="sxs-lookup"><span data-stu-id="f3624-128">Created</span></span>

<span data-ttu-id="f3624-129">Quando uma ordem de quarentena tiver sido criada manualmente, mas o item ainda não estiver colocado no depósito de quarentena, a ordem de quarentena fica com o status **Criado**.</span><span class="sxs-lookup"><span data-stu-id="f3624-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="f3624-130">Duas transações de estoque são geradas.</span><span class="sxs-lookup"><span data-stu-id="f3624-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="f3624-131">Uma transação é uma transação de saída que pode ter um status **Na ordem**, **Qtd. reservada** ou **Separado**.</span><span class="sxs-lookup"><span data-stu-id="f3624-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="f3624-132">A outra transação é uma transação de de recebimento que pode ter o status **Encomendado** ou **Registrado** no depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="f3624-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="f3624-133">Você pode reservar, separar e registrar atualizações no estoque usando os processos normais.</span><span class="sxs-lookup"><span data-stu-id="f3624-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="f3624-134">Iniciado</span><span class="sxs-lookup"><span data-stu-id="f3624-134">Started</span></span>

<span data-ttu-id="f3624-135">Quando uma ordem de quarentena tem o status **Iniciado**, o estoque é transferido do depósito normal para o depósito de quarentena, e duas transações de estoque são geradas.</span><span class="sxs-lookup"><span data-stu-id="f3624-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="f3624-136">Uma transação tem o status **Deduzido** e a outra transação, o status **Recebido**.</span><span class="sxs-lookup"><span data-stu-id="f3624-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="f3624-137">Ao mesmo tempo, duas transações de estoque são criadas para tratar da transferência de retorno.</span><span class="sxs-lookup"><span data-stu-id="f3624-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="f3624-138">Essas transações não são datadas.</span><span class="sxs-lookup"><span data-stu-id="f3624-138">These transactions aren't dated.</span></span> <span data-ttu-id="f3624-139">Uma transação tem o status **Qtd. reservada** e a outra transação, o status **Encomendado**.</span><span class="sxs-lookup"><span data-stu-id="f3624-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="f3624-140">Informado como concluído</span><span class="sxs-lookup"><span data-stu-id="f3624-140">Reported as finished</span></span>

<span data-ttu-id="f3624-141">Para relatar uma ordem de quarentena iniciada como concluída, abra a ordem e selecione **Relatar como concluído** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="f3624-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="f3624-142">O item é liberado da quarentena, mas ainda não é retornado ao depósito normal.</span><span class="sxs-lookup"><span data-stu-id="f3624-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="f3624-143">O retorno ao depósito normal pode ser processado por meio de um diário de entrada de itens que pode ser inicializado durante o processo Relatar como concluído.</span><span class="sxs-lookup"><span data-stu-id="f3624-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="f3624-144">Terminado</span><span class="sxs-lookup"><span data-stu-id="f3624-144">Ended</span></span>

<span data-ttu-id="f3624-145">Quando uma ordem de quarentena é finalizada, o item é movido do depósito de quarentena para o depósito normal novamente.</span><span class="sxs-lookup"><span data-stu-id="f3624-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="f3624-146">O status da transação de item é definido como *Vendido* no depósito de quarentena e como *Comprado* no depósito normal.</span><span class="sxs-lookup"><span data-stu-id="f3624-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="f3624-147">Sucata da ordem de quarentena</span><span class="sxs-lookup"><span data-stu-id="f3624-147">Quarantine order scrap</span></span>

<span data-ttu-id="f3624-148">Como parte do processo da ordem de quarentena, você pode sucatear o estoque.</span><span class="sxs-lookup"><span data-stu-id="f3624-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="f3624-149">Ao processar a sucata, o status do estoque é definido como *Vendido* por uma transação de saída no depósito de quarentena.</span><span class="sxs-lookup"><span data-stu-id="f3624-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3624-150">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f3624-150">Additional resources</span></span>

- [<span data-ttu-id="f3624-151">Bloqueio de estoque</span><span class="sxs-lookup"><span data-stu-id="f3624-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
