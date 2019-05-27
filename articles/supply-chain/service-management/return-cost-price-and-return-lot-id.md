---
title: Devolução do preço de custo e do ID do lote
description: Talvez você queira que o custo dos produtos devolvidos seja igual ao custo dos produtos no momento em que você os vende ao cliente. Você pode fazer isso usando **Retornar a ID de lote**.
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33cd3d50fe342ba12a17419f4e759c243a60b3e0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565525"
---
# <a name="return-cost-price-and-return-lot-id"></a><span data-ttu-id="1cc25-104">Devolução do preço de custo e do ID do lote</span><span class="sxs-lookup"><span data-stu-id="1cc25-104">Return cost price and return lot ID</span></span>        

[!include [banner](../includes/banner.md)]



<span data-ttu-id="1cc25-105">O custo dos produtos que foram devolvidos ao estoque é calculado usando o custo atual dos produtos.</span><span class="sxs-lookup"><span data-stu-id="1cc25-105">The cost of products that are returned to inventory is calculated by using the current cost of the products.</span></span> <span data-ttu-id="1cc25-106">No entanto, talvez você queira que o custo dos produtos devolvidos seja igual ao custo dos produtos no momento em que você os vende ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc25-106">However, you might want the cost of the returned products to equal the cost of the products at the time when you sold the products to the customer.</span></span> <span data-ttu-id="1cc25-107">Você pode fazer isso usando o campo **Devolver ID de lote** na Guia Rápida **Detalhes da linha** no formulário **Ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-107">You can do this by using the **Return lot ID** field on the **Line details** FastTab in the **Sales order** form.</span></span>

<span data-ttu-id="1cc25-108">Por exemplo, considere o cenário a seguir.</span><span class="sxs-lookup"><span data-stu-id="1cc25-108">For example, consider the following scenario.</span></span> <span data-ttu-id="1cc25-109">Você fatura um cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc25-109">You invoice a customer.</span></span> <span data-ttu-id="1cc25-110">Em seguida, o cliente lhe devolve os produtos entregues.</span><span class="sxs-lookup"><span data-stu-id="1cc25-110">Then, the customer returns the delivered products to you.</span></span> <span data-ttu-id="1cc25-111">Você devolve os produtos ao estoque.</span><span class="sxs-lookup"><span data-stu-id="1cc25-111">You return the products to stock.</span></span> <span data-ttu-id="1cc25-112">Nesse caso, quando você credita o cliente pelos produtos devolvidos, o custo desses produtos é calculado usando o custo atual dos produtos.</span><span class="sxs-lookup"><span data-stu-id="1cc25-112">In this case, when you credit the customer for the returned products, the cost of those products is calculated by using the current cost of the products.</span></span> <span data-ttu-id="1cc25-113">No entanto, se você usar o campo **ID do lote devolvido**, o custo dos produtos devolvidos é calculado usando o custo na fatura da venda original ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc25-113">However, if you use the **Return lot ID** field, the cost of the returned products is calculated by using the cost on the invoice of the original sale to the customer.</span></span>

<span data-ttu-id="1cc25-114">Para usar um custo diferente do custo atual para devoluções de um cliente, use um dos métodos a seguir.</span><span class="sxs-lookup"><span data-stu-id="1cc25-114">To use a cost other than the current cost for returns from a customer, use one of the following methods.</span></span>

## <a name="method-1-manually-enter-the-return-cost-price"></a><span data-ttu-id="1cc25-115">Método 1: Inserir manualmente o preço de custo de devolução</span><span class="sxs-lookup"><span data-stu-id="1cc25-115">Method 1: Manually enter the return cost price</span></span>

<span data-ttu-id="1cc25-116">Por padrão, quando você adiciona itens a uma ordem de devolução, os itens foram devolvidos ao estoque no preço de custo atual.</span><span class="sxs-lookup"><span data-stu-id="1cc25-116">By default, when you add items to a return order, the items are returned to inventory at the current cost price.</span></span> <span data-ttu-id="1cc25-117">Para especificar outro preço de custo de devolução, sigas estas etapas.</span><span class="sxs-lookup"><span data-stu-id="1cc25-117">To specify a different return cost price, follow these steps.</span></span>

1.  <span data-ttu-id="1cc25-118">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-118">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="1cc25-119">No **Painel de Ação**, no grupo **Novo**, clique em **Ordem de retorno**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-119">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="1cc25-120">No formulário **Criar ordem de devolução**, selecione uma conta de cliente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-120">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="1cc25-121">No formulário **Ordem de devolução - Número RMA: %1, %2**, selecione um item e insira uma quantidade negativa no campo **Quantidade**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-121">In the **Return order - RMA number: %1, %2** form, select an item, and then enter a negative quantity in the **Quantity** field.</span></span>

5.  <span data-ttu-id="1cc25-122">Clique na Guia Rápida **Detalhes da linha**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-122">Click the **Line details** FastTab.</span></span>

6.  <span data-ttu-id="1cc25-123">Na guia **Geral**, insira um valor no campo **Preço de custo de devolução**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-123">On the **General** tab, enter a value in the **Return cost price** field.</span></span> <span data-ttu-id="1cc25-124">Esse valor é usado quando os bens forem devolvidos para o estoque.</span><span class="sxs-lookup"><span data-stu-id="1cc25-124">This value is used when the goods are returned to inventory.</span></span> <span data-ttu-id="1cc25-125">Se você não inserir um valor, o preço de custo atual será usado quando os bens forem devolvidos ao estoque.</span><span class="sxs-lookup"><span data-stu-id="1cc25-125">If you do not enter a value, the current cost price is used when the goods are returned to inventory.</span></span>

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a><span data-ttu-id="1cc25-126">Método 2: Gerar automaticamente o preço de custo com base na linha da fatura do cliente</span><span class="sxs-lookup"><span data-stu-id="1cc25-126">Method 2: Automatically generate the cost price based on the customer invoice line</span></span>

<span data-ttu-id="1cc25-127">Esse é o método preferido a ser usado para criar linhas de devolução.</span><span class="sxs-lookup"><span data-stu-id="1cc25-127">This is the preferred method to use to create return lines.</span></span> <span data-ttu-id="1cc25-128">Para usar o custo dos produtos no momento em que você vendeu os produtos ao cliente, crie uma ordem de devolução e especifique uma linha de venda para devolução.</span><span class="sxs-lookup"><span data-stu-id="1cc25-128">To use the cost of the products at the time when you sold the products to the customer, create a return order and specify a sales line to return.</span></span>

1.  <span data-ttu-id="1cc25-129">Clique em **Vendas e marketing** \> **Comum** \> **Ordens de devolução** \> **Todas as ordens de devolução**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-129">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="1cc25-130">No **Painel de Ação**, no grupo **Novo**, clique em **Ordem de retorno**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-130">On the **Action Pane**, in the **New** group, click **Return order**.</span></span>

3.  <span data-ttu-id="1cc25-131">No formulário **Criar ordem de devolução**, selecione uma conta de cliente e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-131">In the **Create return order** form, select a customer account, and then click **OK**.</span></span>

4.  <span data-ttu-id="1cc25-132">No formulário **Ordem de devolução - Número RMA: %1, %2**, no **Painel de Ação**, clique em **Encontrar ordem de vendas**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-132">In the **Return order - RMA number: %1, %2** form, on the **Action Pane**, click **Find sales order**.</span></span>

5.  <span data-ttu-id="1cc25-133">No formulário **Localizar ordem de venda**, selecione a linha de fatura para devolução e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-133">In the **Find sales order** form, select the invoice line to return, and then click **OK**.</span></span>
    
    <span data-ttu-id="1cc25-134">Na Guia Rápida **Detalhes de linha**, na guia **Geral**, o campo **Devolver ID de lote** exibe o valor da linha de venda original.</span><span class="sxs-lookup"><span data-stu-id="1cc25-134">On the **Line details** FastTab, on the **General** tab, the **Return lot ID** field displays the value from the original sales line.</span></span> <span data-ttu-id="1cc25-135">Além disso, o campo **Preço de custo de devolução** exibe o valor do custo da linha de venda original.</span><span class="sxs-lookup"><span data-stu-id="1cc25-135">Additionally, the **Return cost price** field displays the cost value from the original sales line.</span></span>

## <a name="cost-calculation-example"></a><span data-ttu-id="1cc25-136">Exemplo de cálculo de custo</span><span class="sxs-lookup"><span data-stu-id="1cc25-136">Cost calculation example</span></span>

<span data-ttu-id="1cc25-137">Quando você usa o campo **ID do lote devolvido** em uma linha da ordem de devolução para especificar o preço de custo da devolução, o custo na linha da ordem de devolução será usado.</span><span class="sxs-lookup"><span data-stu-id="1cc25-137">When you use the **Return lot ID** field on a return order line to specify the return cost price, the cost on the return order line is used.</span></span> <span data-ttu-id="1cc25-138">Se você executar a funcionalidade de fechamento ou recálculo do estoque, os custos serão ajustados na linha de venda original.</span><span class="sxs-lookup"><span data-stu-id="1cc25-138">If you run the inventory close or recalculation functionality, the cost is adjusted on the original sales line.</span></span> <span data-ttu-id="1cc25-139">Os custos na linha da ordem de devolução são ajustados automaticamente para refletir o mesmo custo por peça.</span><span class="sxs-lookup"><span data-stu-id="1cc25-139">The cost on the return order line is automatically adjusted to reflect the same cost per piece.</span></span>

1.  <span data-ttu-id="1cc25-140">Crie e libere um produto denominado Teste.</span><span class="sxs-lookup"><span data-stu-id="1cc25-140">Create and release a product that is named Test.</span></span> <span data-ttu-id="1cc25-141">No formulário **Detalhes do produto liberado**, especifique as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="1cc25-141">In the **Released product details** form, specify the following information:</span></span>
    
    1.  <span data-ttu-id="1cc25-142">Na Guia Rápida **Gerenciar custos**, no campo **Grupo de item**, selecione o grupo **Peças**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-142">On the **Manage costs** FastTab, in the **Item group** field, select the **Parts** group.</span></span>
    
    2.  <span data-ttu-id="1cc25-143">Na Guia Rápida **Geral**, no campo **Grupo de modelo do item**, selecione **DEF**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-143">On the **General** FastTab, in the **Item model group** field, select **DEF**.</span></span>
    
    3.  <span data-ttu-id="1cc25-144">Na Guia Rápida **Compra**, no campo **Preço**, digite 10,00 como o preço de custo do item.</span><span class="sxs-lookup"><span data-stu-id="1cc25-144">On the **Purchase** FastTab, in the **Price** field, type 10.00 as the cost price of the item.</span></span>
    
    4.  <span data-ttu-id="1cc25-145">No **Painel de Ação**, clique em **Grupos de dimensões**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-145">On the **Action Pane**, click **Dimension groups**.</span></span> <span data-ttu-id="1cc25-146">No campo **Grupo de dimensões de armazenamento**, selecione **Apenas site e depósito**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-146">In the **Storage dimension group** field, select **Site and Warehouse only**.</span></span> <span data-ttu-id="1cc25-147">No campo **Grupo de dimensões de rastreamento**, selecione **Nenhuma dimensão de rastreamento ativa**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-147">In the **Tracking dimension group** field, select **No active tracking dimensions**.</span></span>

2.  <span data-ttu-id="1cc25-148">Crie uma ordem de compra para 10 peças do item Teste a 6,00 cada peça e lance uma fatura para a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="1cc25-148">Create a purchase order for 10 pieces of the Test item at 6.00 per piece, and then post an invoice for the purchase order.</span></span>
    
    <span data-ttu-id="1cc25-149">Crie uma segunda ordem de compra para 10 peças do item Teste a 8,00 cada peça e lance uma fatura para a ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="1cc25-149">Create a second purchase order for 10 pieces of the Test item at 8.00 per piece, and then post an invoice for the purchase order.</span></span>

3.  <span data-ttu-id="1cc25-150">Lance uma fatura para uma ordem de venda para vender cinco peças do item Teste.</span><span class="sxs-lookup"><span data-stu-id="1cc25-150">Post an invoice for a sales order to sell five pieces of the Test item.</span></span>
    
    <span data-ttu-id="1cc25-151">Nesse caso, a linha da ordem de venda é orçada a 35,00 (5 peças \* custo médio por peça de 7,00).</span><span class="sxs-lookup"><span data-stu-id="1cc25-151">In this case, the sales order line is costed at 35.00 (5 pieces \* 7.00 average cost per piece).</span></span>

4.  <span data-ttu-id="1cc25-152">Crie uma ordem de devolução para o cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc25-152">Create a return order for the customer.</span></span> <span data-ttu-id="1cc25-153">No formulário **Localizar ordem de venda**, selecione a linha de fatura para devolução e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-153">In the **Find sales order** form, select the invoice line, and then click **OK**.</span></span>

5.  <span data-ttu-id="1cc25-154">No formulário **Ordem de devolução - Número RMA: %1, %2**, verifique se uma ordem de devolução foi gerada para devolução do item Teste.</span><span class="sxs-lookup"><span data-stu-id="1cc25-154">In the **Return order - RMA number: %1, %2** form, verify that a return order is generated to return the Test item.</span></span> <span data-ttu-id="1cc25-155">A quantidade da ordem de devolução é definida como -5,00.</span><span class="sxs-lookup"><span data-stu-id="1cc25-155">The quantity of the return order is set to -5.00.</span></span>
    
    <span data-ttu-id="1cc25-156">O campo **Devolver ID de lote** exibe um ID de lote.</span><span class="sxs-lookup"><span data-stu-id="1cc25-156">The **Return lot ID** field displays a lot ID.</span></span> <span data-ttu-id="1cc25-157">Essa ID de lote é extraída da ordem de venda original do item que foi vendido ao cliente.</span><span class="sxs-lookup"><span data-stu-id="1cc25-157">This lot ID is taken from the original sales order of the item that was sold to the customer.</span></span> <span data-ttu-id="1cc25-158">O campo **Preço de custo de devolução** exibe o preço do custo da linha de venda original.</span><span class="sxs-lookup"><span data-stu-id="1cc25-158">The **Return cost price** field displays the cost price from the original sales line.</span></span>

6.  <span data-ttu-id="1cc25-159">Registre o recebimento dos itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="1cc25-159">Register the receipt of the returned items.</span></span>

7.  <span data-ttu-id="1cc25-160">Lance uma guia de remessa para os itens devolvidos.</span><span class="sxs-lookup"><span data-stu-id="1cc25-160">Post a packing slip for the returned items.</span></span>

8.  <span data-ttu-id="1cc25-161">Lance uma fatura para a ordem de devolução.</span><span class="sxs-lookup"><span data-stu-id="1cc25-161">Post an invoice for the return order.</span></span> <span data-ttu-id="1cc25-162">Na página de listagem **Todas as ordens de venda**, selecione uma ordem de venda para a qual **Ordem devolvida** é o tipo de ordem.</span><span class="sxs-lookup"><span data-stu-id="1cc25-162">On the **All sales orders** list page, select a sales order for which **Returned order** is the order type.</span></span>

9.  <span data-ttu-id="1cc25-163">Abra o formulário **Transações de estoque**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-163">Open the **Inventory transactions** form.</span></span> <span data-ttu-id="1cc25-164">Verifique se a devolução foi orçada a 7,00 por peça usando o valor no campo **Preço de custo de devolução**, para um total de 35,00 no campo **Valor de custo**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-164">Verify that the return is costed at 7.00 per piece by using the value in the **Return cost price** field, for a total of 35.00 in the **Cost amount** field.</span></span> <span data-ttu-id="1cc25-165">Você pode abrir o formulário **Transações de estoque** a partir do formulário **Ordem de devolução - Número RMA: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-165">You can open the **Inventory transactions** form from the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="1cc25-166">Na grade **Linhas**, clique em **Estoque** \> **Transações**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-166">In the **Lines** grid, click **Inventory** \> **Transactions**.</span></span>

10. <span data-ttu-id="1cc25-167">No Gerenciamento de estoque e depósito, use o formulário **Fechamento e ajuste** para executar o procedimento **3. Fechar**.</span><span class="sxs-lookup"><span data-stu-id="1cc25-167">In Inventory and warehouse management, use the **Closing and adjustment** form to run the **3. Close** procedure.</span></span>
    
    <span data-ttu-id="1cc25-168">Essa ação ajusta o custo na linha de venda original que foi orçado a -35,00 (5 peças \* 7,00) para -30,00 (5 peças \* 6,00).</span><span class="sxs-lookup"><span data-stu-id="1cc25-168">This action adjusts the cost on the original sales line that was costed at -35.00 (5 pieces \* 7.00) to -30.00 (5 pieces \* 6.00).</span></span> <span data-ttu-id="1cc25-169">Isso porque o grupo de modelos de estoque usa o processo FIFO (primeiro a entrar, primeiro a sair) e 6,00 por peça é o custo FIFO a partir da primeira ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="1cc25-169">This is because the inventory model group uses First in, First out (FIFO), and 6.00 per piece is the FIFO cost from the first purchase order.</span></span> <span data-ttu-id="1cc25-170">Além disso, a ação ajusta o custo na linha de venda de devolução para corresponder ao custo por peça na linha de venda original.</span><span class="sxs-lookup"><span data-stu-id="1cc25-170">Additionally, the action adjusts the cost on the return sales line to match the cost per piece on the original sales line.</span></span> <span data-ttu-id="1cc25-171">Portanto, o custo da linha de devolução é ajustado de 35,00 para 30,00.</span><span class="sxs-lookup"><span data-stu-id="1cc25-171">Therefore, the cost of the return line is adjusted from 35.00 to 30.00.</span></span>




