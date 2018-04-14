---
title: "Visão geral de ordens de cliente"
description: "Este tópico fornece informações sobre ordens de cliente no Retail Modern POS (MPOS). Ordens de cliente também são conhecidas como ordens especiais O tópico inclui uma discussão sobre parâmetros relacionados e fluxos de transação."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: c3e774cd8e63d55729b67719bdaf2594b41d718a
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="customer-orders-overview"></a><span data-ttu-id="caf8f-105">Visão geral de ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf8f-105">Customer orders overview</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="caf8f-106">Este tópico fornece informações sobre ordens de cliente no Retail Modern POS (MPOS).</span><span class="sxs-lookup"><span data-stu-id="caf8f-106">This topic provides information about customer orders in Retail Modern POS (MPOS).</span></span> <span data-ttu-id="caf8f-107">Ordens de cliente também são conhecidas como ordens especiais</span><span class="sxs-lookup"><span data-stu-id="caf8f-107">Customer orders are also known as special orders.</span></span> <span data-ttu-id="caf8f-108">O tópico inclui uma discussão sobre parâmetros relacionados e fluxos de transação.</span><span class="sxs-lookup"><span data-stu-id="caf8f-108">The topic includes a discussion of related parameters and transaction flows.</span></span>

<span data-ttu-id="caf8f-109">Em um mundo de canal omni de varejo, muitos revendedores fornecem a opção de ordens de cliente ou ordens especiais para atender a vários requisitos de produto e atendimento.</span><span class="sxs-lookup"><span data-stu-id="caf8f-109">In an omni-channel retail world, many retailers provide the option of customer orders, or special orders, to meet various product and fulfillment requirements.</span></span> <span data-ttu-id="caf8f-110">Estes são alguns dos cenários típicos:</span><span class="sxs-lookup"><span data-stu-id="caf8f-110">Here are some typical scenarios:</span></span>

-   <span data-ttu-id="caf8f-111">Um cliente deseja que produtos sejam entregues a um endereço específico em uma determinada data.</span><span class="sxs-lookup"><span data-stu-id="caf8f-111">A customer wants products to be delivered to a specific address on a specific date.</span></span>
-   <span data-ttu-id="caf8f-112">Um cliente deseja retirar produtos de uma loja ou local que é diferente da loja ou local no qual ele comprou esses produtos.</span><span class="sxs-lookup"><span data-stu-id="caf8f-112">A customer wants to pick up products from a store or location that differs from the store or location where the customer purchased those products.</span></span>
-   <span data-ttu-id="caf8f-113">Um cliente deseja que outra pessoa retire o produto que ele comprou.</span><span class="sxs-lookup"><span data-stu-id="caf8f-113">A customer wants someone else to pick up products that the customer purchased.</span></span>

<span data-ttu-id="caf8f-114">Varejistas também usam ordens de cliente para minimizar perdas de venda que, de outra forma, poderiam ser causadas por faltas de estoque, já que a mercadoria pode ser entregue ou retirada em um horário ou local diferentes.</span><span class="sxs-lookup"><span data-stu-id="caf8f-114">Retailers also use customer orders to minimize lost sales that stock outages might otherwise cause, because the merchandise can be delivered or picked up at a different time or place.</span></span>

## <a name="set-up-customer-orders"></a><span data-ttu-id="caf8f-115">Configurar ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf8f-115">Set up customer orders</span></span>
<span data-ttu-id="caf8f-116">Estes são alguns dos parâmetros que podem ser definidos na página **Parâmetros de varejo** para definir como as ordens de cliente são atendidas:</span><span class="sxs-lookup"><span data-stu-id="caf8f-116">Here are some of the parameters that can be set on the **Retail parameters** page to define how customer orders are fulfilled:</span></span>

-   <span data-ttu-id="caf8f-117">**Percentual de depósito padrão** – Especifique o valor que o cliente deve pagar como depósito antes que uma ordem possa ser confirmada.</span><span class="sxs-lookup"><span data-stu-id="caf8f-117">**Default deposit percentage** – Specify the amount that the customer must pay as a deposit before an order can be confirmed.</span></span> <span data-ttu-id="caf8f-118">O valor de depósito padrão é calculado como porcentagem do valor da ordem.</span><span class="sxs-lookup"><span data-stu-id="caf8f-118">The default deposit amount is calculated as a percentage of the order value.</span></span> <span data-ttu-id="caf8f-119">Dependendo dos privilégios, um associado da loja talvez consiga substituir o valor usando **Substituição de depósito**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-119">Depending on privileges, a store associate might be able to override the amount by using **Deposit override**.</span></span>
-   <span data-ttu-id="caf8f-120">**Percentual de encargo de cancelamento** – Se um encargo for aplicado quando uma ordem de cliente é cancelada, especifique o valor desse encargo.</span><span class="sxs-lookup"><span data-stu-id="caf8f-120">**Cancellation charge percentage** – If a charge will be applied when a customer order is canceled, specify the amount of that charge.</span></span>
-   <span data-ttu-id="caf8f-121">**Código do encargo de cancelamento** – Se um encargo for aplicado quando uma ordem de cliente é cancelada, esse encargo será refletido em um código de encargo na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="caf8f-121">**Cancellation charge code** – If a charge will be applied when a customer order is canceled, that charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="caf8f-122">Use esse parâmetro para definir o código de encargo de cancelamento.</span><span class="sxs-lookup"><span data-stu-id="caf8f-122">Use this parameter to define the cancellation charge code.</span></span>
-   <span data-ttu-id="caf8f-123">**Código do encargo de remessa** – Varejistas podem cobrar uma taxa adicional por enviar mercadoria a um cliente.</span><span class="sxs-lookup"><span data-stu-id="caf8f-123">**Shipping charge code** – Retailers can charge an extra fee for shipping merchandise to a customer.</span></span> <span data-ttu-id="caf8f-124">O valor desse encargo de remessa será refletido em código de encargo na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="caf8f-124">The amount of that shipping charge will be reflected under a charge code on the sales order.</span></span> <span data-ttu-id="caf8f-125">Use esse parâmetro para mapear o código de encargo de remessa com os encargos de remessa na ordem de cliente.</span><span class="sxs-lookup"><span data-stu-id="caf8f-125">Use this parameter to map the shipping charge code to shipping charges on the customer order.</span></span>
-   <span data-ttu-id="caf8f-126">**Reembolsar encargos de remessa** – Especifique se os encargos de remessa associados a uma ordem de cliente são reembolsáveis.</span><span class="sxs-lookup"><span data-stu-id="caf8f-126">**Refund shipping charges** – Specify whether shipping charges that are associated with a customer order are refundable.</span></span>
-   <span data-ttu-id="caf8f-127">**Valor máximo sem aprovação** – Se os encargos de remessa forem reembolsáveis, especifique o valor máximo dos reembolsos de encargo de envio em ordens de reembolso.</span><span class="sxs-lookup"><span data-stu-id="caf8f-127">**Maximum amount without approval** – If shipping charges are refundable, specify the maximum amount of shipping charge refunds across return orders.</span></span> <span data-ttu-id="caf8f-128">Se esse valor for excedido, a substituição do gerente é necessária para continuar com o reembolso.</span><span class="sxs-lookup"><span data-stu-id="caf8f-128">If this amount is exceeded, manager override is required in order to continue with the refund.</span></span> <span data-ttu-id="caf8f-129">Para acomodar os seguintes cenários, um reembolso de encargos de remessa pode exceder o valor originalmente pago:</span><span class="sxs-lookup"><span data-stu-id="caf8f-129">To accommodate the following scenarios, a refund of shipping charges can exceed the amount that was originally paid:</span></span>
    -   <span data-ttu-id="caf8f-130">Encargos são aplicados no nível do cabeçalho das ordens de venda e, quando algum valor de uma linha de produto é devolvido, o reembolso máximo de encargos de remessa permitido para os produtos e o valor não pode ser determinado de forma que funcione para os clientes de varejo.</span><span class="sxs-lookup"><span data-stu-id="caf8f-130">Charges are applied at the level of the sales order header, and when some quantity of a product line is returned, the maximum refund of shipping charges that is allowed for the products and the quantity can't be determined in way that works for all retail customers.</span></span>
    -   <span data-ttu-id="caf8f-131">Encargos de remessa são utilizados para todas as instâncias de remessa.</span><span class="sxs-lookup"><span data-stu-id="caf8f-131">Shipping charges are incurred for every instance of shipping.</span></span> <span data-ttu-id="caf8f-132">Se um cliente devolver produtos várias vezes e a política do revendedor especificar que o revendedor arcará com o custo de reembolso de encargo de remessa, esse reembolso de encargo de remessa será superior aos encargos reais de remessa.</span><span class="sxs-lookup"><span data-stu-id="caf8f-132">If a customer returns products multiple times, and the retailer’s policy specifies that the retailer will bear the cost of return shipping charges, the return shipping charges will be more than the actual shipping charges.</span></span>

## <a name="transaction-flow-for-customer-orders"></a><span data-ttu-id="caf8f-133">Fluxo de transações para ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf8f-133">Transaction flow for customer orders</span></span>
### <a name="create-a-customer-order-in-retail-modern-pos"></a><span data-ttu-id="caf8f-134">Criar uma ordem de cliente no Retail Modern POS</span><span class="sxs-lookup"><span data-stu-id="caf8f-134">Create a customer order in Retail Modern POS</span></span>

1.  <span data-ttu-id="caf8f-135">Adicione um cliente à transação.</span><span class="sxs-lookup"><span data-stu-id="caf8f-135">Add a customer to the transaction.</span></span>
2.  <span data-ttu-id="caf8f-136">Adicione produtos ao carrinho.</span><span class="sxs-lookup"><span data-stu-id="caf8f-136">Add products to the cart.</span></span>
3.  <span data-ttu-id="caf8f-137">Clique em **Criar ordem do cliente** e depois selecione o tipo de ordem.</span><span class="sxs-lookup"><span data-stu-id="caf8f-137">Click **Create customer order**, and then select the order type.</span></span> <span data-ttu-id="caf8f-138">O tipo de ordem pode ser **Ordem de cliente** ou **Cotação**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-138">The order type can be either **Customer order** or **Quote**.</span></span>
4.  <span data-ttu-id="caf8f-139">Clique em **Remeter selecionado** ou **Remeter tudo** para enviar os produtos a um endereço na conta do cliente, especifique a data de remessa solicitada e especifique os encargos de remessa.</span><span class="sxs-lookup"><span data-stu-id="caf8f-139">Click **Ship selected** or **Ship all** to ship the products to an address on the customer account, specify the requested shipping date, and specify shipping charges.</span></span>
5.  <span data-ttu-id="caf8f-140">Clique em **Retirar selecionado** ou **Retirar tudo** para selecionar produtos que serão retirados da loja atual ou de uma loja diferente em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="caf8f-140">Click **Pick up selected** or **Pick-up all** to select products that will be picked up from the current store or a different store on a specific date.</span></span>
6.  <span data-ttu-id="caf8f-141">Cobre o valor de depósito, se um depósito for necessário.</span><span class="sxs-lookup"><span data-stu-id="caf8f-141">Collect the deposit amount, if a deposit is required.</span></span>

### <a name="edit-an-existing-customer-order"></a><span data-ttu-id="caf8f-142">Editar uma ordem de cliente existente</span><span class="sxs-lookup"><span data-stu-id="caf8f-142">Edit an existing customer order</span></span>

1.  <span data-ttu-id="caf8f-143">Na página inicial, clique em **Encontrar uma ordem**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-143">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="caf8f-144">Encontre e selecione a ordem a ser editada.</span><span class="sxs-lookup"><span data-stu-id="caf8f-144">Find and select the order to edit.</span></span> <span data-ttu-id="caf8f-145">Na parte inferior da página, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-145">At the bottom of the page, click the **Edit**.</span></span>

### <a name="pick-up-an-order"></a><span data-ttu-id="caf8f-146">Retirar uma ordem</span><span class="sxs-lookup"><span data-stu-id="caf8f-146">Pick up an order</span></span>

1.  <span data-ttu-id="caf8f-147">Na página inicial, clique em **Encontrar uma ordem**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-147">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="caf8f-148">Selecione a ordem a ser retirada.</span><span class="sxs-lookup"><span data-stu-id="caf8f-148">Select the order to pick up.</span></span> <span data-ttu-id="caf8f-149">Na parte inferior da página, clique em **Separação e embalagem**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-149">At the bottom of the page, click **Picking and packing**.</span></span>
3.  <span data-ttu-id="caf8f-150">Clique em **Retirar**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-150">Click **Pick up**.</span></span>

### <a name="cancel-an-order"></a><span data-ttu-id="caf8f-151">Cancelar uma ordem</span><span class="sxs-lookup"><span data-stu-id="caf8f-151">Cancel an order</span></span>

1.  <span data-ttu-id="caf8f-152">Na página inicial, clique em **Encontrar uma ordem**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-152">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="caf8f-153">Selecione a ordem a ser cancelada.</span><span class="sxs-lookup"><span data-stu-id="caf8f-153">Select the order to cancel.</span></span> <span data-ttu-id="caf8f-154">Na parte inferior da página, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-154">At the bottom of the page, click **Cancel**.</span></span>

#### <a name="create-a-return-order"></a><span data-ttu-id="caf8f-155">Criar uma ordem de devolução</span><span class="sxs-lookup"><span data-stu-id="caf8f-155">Create a return order</span></span>

1.  <span data-ttu-id="caf8f-156">Na página inicial, clique em **Encontrar uma ordem**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-156">On the home page, click **Find an order**.</span></span>
2.  <span data-ttu-id="caf8f-157">Selecione a ordem a ser devolvida, selecione a fatura para a ordem e depois selecione uma linha de produto para a mercadoria a ser devolvida.</span><span class="sxs-lookup"><span data-stu-id="caf8f-157">Select the order to return, select the invoice for the order, and then select the product line for the merchandise to return.</span></span>
3.  <span data-ttu-id="caf8f-158">Na parte inferior da página, clique em **Ordem de devolução**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-158">At the bottom of the page, click the **Return order**.</span></span>

## <a name="asynchronous-transaction-flow-for-customer-orders"></a><span data-ttu-id="caf8f-159">Fluxo de transações assíncronas para ordens de cliente</span><span class="sxs-lookup"><span data-stu-id="caf8f-159">Asynchronous transaction flow for customer orders</span></span>
<span data-ttu-id="caf8f-160">Ordens de cliente podem ser criadas do cliente do ponto de venda (PDV) em modo síncrono ou assíncrono.</span><span class="sxs-lookup"><span data-stu-id="caf8f-160">Customer orders can be created from the point of sale (POS) client in either synchronous mode or asynchronous mode.</span></span>

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a><span data-ttu-id="caf8f-161">Habilitar ordens de cliente para serem criadas em modo assíncrono</span><span class="sxs-lookup"><span data-stu-id="caf8f-161">Enable customer orders to be created in asynchronous mode</span></span>

1.  <span data-ttu-id="caf8f-162">Clique em **Varejo** &gt; **Configuração de canal** &gt; **Configuração de PDV** &gt; **Perfil de PDV** &gt; **Perfis de funcionalidade**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-162">Click **Retail** &gt; **Channel setup** &gt; **POS setup** &gt; **POS profile** &gt; **Functionality profiles**.</span></span>
2.  <span data-ttu-id="caf8f-163">Na Guia Rápida **Geral**, defina a opção **Criar ordem do cliente no modo assíncrono** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="caf8f-163">On the **General** FastTab, set the **Create customer order in async mode** option to **Yes**.</span></span>

<span data-ttu-id="caf8f-164">Quando a opção **Criar ordem do cliente no modo assíncrono** for definida como **Sim**, as ordens de cliente sempre serão criadas em modo assíncrono, mesmo se o Retail Transaction Service (RTS) estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="caf8f-164">When the **Create customer order in async mode** option is set to **Yes**, customer orders are always created in asynchronous mode, even if Retail Transaction Service (RTS) is available.</span></span> <span data-ttu-id="caf8f-165">Se você definir essa opção como **Não**, as ordens de cliente sempre serão criadas em modo síncrono por meio de RTS.</span><span class="sxs-lookup"><span data-stu-id="caf8f-165">If you set this option to **No**, customer orders are always created in synchronous mode by using RTS.</span></span> <span data-ttu-id="caf8f-166">Quando ordens de cliente são criadas em modo assíncrono, elas são retiradas e inseridas no Retail por trabalhos de pull (P).</span><span class="sxs-lookup"><span data-stu-id="caf8f-166">When customer orders are created in asynchronous mode, they are pulled and inserted into Retail by Pull (P) jobs.</span></span> <span data-ttu-id="caf8f-167">As ordens de venda correspondentes são criadas no Retail quando **Sincronizar ordens** é executado manualmente ou por meio de um processo de lote.</span><span class="sxs-lookup"><span data-stu-id="caf8f-167">The corresponding sales orders are created in Retail when **Synchronize orders** is run either manually or through a batch process.</span></span>

<a name="see-also"></a><span data-ttu-id="caf8f-168">Consulte também</span><span class="sxs-lookup"><span data-stu-id="caf8f-168">See also</span></span>
--------

[<span data-ttu-id="caf8f-169">Ordens de cliente híbrido</span><span class="sxs-lookup"><span data-stu-id="caf8f-169">Hybrid customer orders</span></span>](hybrid-customer-orders.md)




