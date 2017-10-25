---
title: "Processo de saída"
description: "Este tópico fornece uma visão geral do processo de saída no gerenciamento de estoque."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 9c09a7bd314bb9005eb0b6c69d7cccad1c30cfdb
ms.openlocfilehash: 7b395cab2184f8f9f3f50a7a595c6ed782645323
ms.contentlocale: pt-br
ms.lasthandoff: 10/04/2017

---

# <a name="outbound-process"></a><span data-ttu-id="09c20-103">Processo de saída</span><span class="sxs-lookup"><span data-stu-id="09c20-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="09c20-104">Este tópico fornece uma visão geral do processo de saída no gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="09c20-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="09c20-105">Ordens de saída</span><span class="sxs-lookup"><span data-stu-id="09c20-105">Output orders</span></span>

<span data-ttu-id="09c20-106">As ordens de saída são usadas para vincular linhas de ordem de venda e linhas de ordem de transferência aos processos de separação de saída que usam as listas de separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="09c20-107">Quando as listas de separação são geradas de ordens de venda ou de ordens de transferência, as ordens de saídas e remessas são criadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="09c20-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="09c20-108">Uma lista de separação tem um relacionamento um para um com uma remessa.</span><span class="sxs-lookup"><span data-stu-id="09c20-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="09c20-109">A remessa de ordem de transferência ou guia de remessa de ordem de venda pode ser processada da remessa.</span><span class="sxs-lookup"><span data-stu-id="09c20-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="09c20-110">O diagrama a seguir exibe uma visão geral do processo de ordens de saída.</span><span class="sxs-lookup"><span data-stu-id="09c20-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="09c20-111">[![Visão geral do processo da ordem de saída.](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="09c20-112">Você pode configurar regras de saída para definir como o programa deve tratar o processo de saída.</span><span class="sxs-lookup"><span data-stu-id="09c20-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="09c20-113">Você pode usar essas regras para controlar o processo de remessa.</span><span class="sxs-lookup"><span data-stu-id="09c20-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="09c20-114">Particularmente, você pode usar as regras para controlar em qual estágio do processo uma remessa pode ser enviada.</span><span class="sxs-lookup"><span data-stu-id="09c20-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="09c20-115">As seguintes definições determinam como os processos de saída são tratados.</span><span class="sxs-lookup"><span data-stu-id="09c20-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="09c20-116">Seleção do status do roteiro para vendas e ordens de transferência</span><span class="sxs-lookup"><span data-stu-id="09c20-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="09c20-117">Vá para **Contas a receber** \> **Configuração** \> **Parâmetros de contas a receber** e, em seguida, na guia **Atualizações**, selecione um valor no campo **Status do roteiro de separação**.</span><span class="sxs-lookup"><span data-stu-id="09c20-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="09c20-118">[![Seleção do campo de status de roteiro para ordens de venda](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="09c20-119">Se o campo **Status do roteiro de separação** for definido como **Concluído**, o processo de separação ocorre automaticamente como parte do processo de geração das listas de separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="09c20-120">Se o campo for definido como **Ativado**, as linhas da lista de separação devem ser atualizadas manualmente.</span><span class="sxs-lookup"><span data-stu-id="09c20-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="09c20-121">A mesma configuração se aplica a ordens de transferência.</span><span class="sxs-lookup"><span data-stu-id="09c20-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="09c20-122">Vá para **Gerenciamento de estoque** \> **Configuração** \> **Parâmetros de gerenciamento de estoque e depósito** e, em seguida, na guia **Transporte**, selecione um valor no campo **Status do roteiro de separação**.</span><span class="sxs-lookup"><span data-stu-id="09c20-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="09c20-123">[![Seleção do campo de status de roteiro para ordens de transferência](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="09c20-124">Finalizar ordens de estoque de saída</span><span class="sxs-lookup"><span data-stu-id="09c20-124">End output inventory orders</span></span>

<span data-ttu-id="09c20-125">Vá para **Gerenciamento de estoque** \> **Configuração** \> **Parâmetros de gerenciamento de estoque e depósito** e na guia **Geral**, defina a opção **Finalizar ordem de estoque de saída**.</span><span class="sxs-lookup"><span data-stu-id="09c20-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="09c20-126">[![Opção Finalizar ordem de estoque de saída](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="09c20-127">Às vezes, alguns itens em estoque não podem ser separados como parte do processo de lista de separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-127">Sometimes, some items in inventory can't be picked as part of the picking list process.</span></span> <span data-ttu-id="09c20-128">Por exemplo, essa situação pode ocorrer se o trabalhador de depósito reduzir as quantidades nas linhas de separação e processar a lista de separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-128">For example, this situation might occur if a warehouse worker reduces the quantities on picking lines and processes the picking list.</span></span> <span data-ttu-id="09c20-129">Se a opção **Finalizar ordem de estoque de saída** for definida como **Sim**, as quantidades não selecionadas restantes são reportadas novamente para o nível da ordem.</span><span class="sxs-lookup"><span data-stu-id="09c20-129">If the **End output inventory order** option is set to **Yes**, the remaining unpicked quantities are reported back to the order level.</span></span> <span data-ttu-id="09c20-130">Se a opção for definida como **Não**, as quantidades não selecionadas restantes serão mantidas como uma quantidade de ordem de saída aberta.</span><span class="sxs-lookup"><span data-stu-id="09c20-130">If the option is set to **No**, the remaining unpicked quantities are kept as an open output order quantity.</span></span> <span data-ttu-id="09c20-131">Nesse caso, as quantidades permanecem liberadas para o depósito devem ser adicionadas a uma nova lista de separação como parte da funcionalidade **Abrir ordens de saída**.</span><span class="sxs-lookup"><span data-stu-id="09c20-131">In this case, the quantities remain released to the warehouse and must be added to a new picking list as part of the **Open output orders** functionality.</span></span>

<span data-ttu-id="09c20-132">[![Comando Abrir ordens de saída no menu Funções](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-132">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="09c20-133">[![Menu de funções na página Abrir ordens de saída](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-133">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="09c20-134">Reduzir quantidade</span><span class="sxs-lookup"><span data-stu-id="09c20-134">Reduce quantity</span></span>

<span data-ttu-id="09c20-135">O terceiro parâmetro que você pode usar como parte do processo de geração de listas de separação no parâmetro **Reduzir quantidade**.</span><span class="sxs-lookup"><span data-stu-id="09c20-135">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="09c20-136">A configuração deste parâmetro trabalha junto com a configuração **Reserva** que aciona um processo de reserva como parte da liberação ao depósito.</span><span class="sxs-lookup"><span data-stu-id="09c20-136">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="09c20-137">[![Parâmetro Reduzir quantidade](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-137">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="09c20-138">Exemplo de um processo de saída para uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="09c20-138">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="09c20-139">Por exemplo, há uma ordem de venda para dois itens.</span><span class="sxs-lookup"><span data-stu-id="09c20-139">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="09c20-140">Durante a geração de listas de separação, selecione o parâmetro **Reduzir quantidade**.</span><span class="sxs-lookup"><span data-stu-id="09c20-140">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="09c20-141">Portanto, você libera e cria linhas de separação somente para estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="09c20-141">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="09c20-142">A separação deve ser reportada por meio de um processo de registro para listas de separação (**Status do roteiro de separação** = **Ativado**).</span><span class="sxs-lookup"><span data-stu-id="09c20-142">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="09c20-143">O estoque que ainda não foi reservado é reservado durante a geração da lista de separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-143">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="09c20-144">O estoque indisponível pode ser removido da ordem de venda ou liberado para o depósito para processamento de saída posteriormente, quando o estoque estiver disponível para separação.</span><span class="sxs-lookup"><span data-stu-id="09c20-144">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="09c20-145">[![Atualizar a lista de separação](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-145">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="09c20-146">Assim que todas as linhas de separação forem separadas na página **Registro de lista de separação**, a remessa associada será concluída.</span><span class="sxs-lookup"><span data-stu-id="09c20-146">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="09c20-147">O processo para guias de remessa de ordem de venda pode ser inicializado com base em estoque separado.</span><span class="sxs-lookup"><span data-stu-id="09c20-147">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="09c20-148">[![Atualizar remessas de saída](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="09c20-148">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>
