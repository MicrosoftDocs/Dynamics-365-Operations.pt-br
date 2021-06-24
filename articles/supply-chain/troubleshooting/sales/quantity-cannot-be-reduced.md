---
title: A quantidade não pode ser reduzida quando uma ordem de venda for cancelada
description: A quantidade não pode ser reduzida quando uma ordem de venda for cancelada.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230827"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="71482-103">A quantidade não pode ser reduzida quando uma ordem de venda for cancelada</span><span class="sxs-lookup"><span data-stu-id="71482-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="71482-104">Código de erro: SYS138831</span><span class="sxs-lookup"><span data-stu-id="71482-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="71482-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="71482-105">Symptoms</span></span>

<span data-ttu-id="71482-106">O sistema mostra a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="71482-106">The system shows the following error message:</span></span>

> <span data-ttu-id="71482-107">A quantidade não pode ser reduzida.</span><span class="sxs-lookup"><span data-stu-id="71482-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="71482-108">O número de transações de inventário na ordem é baixo demais porque a quantidade ou parte dela é referenciada por uma ordem de saída ou uma ordem de produção ou é marcada contra outras transações.</span><span class="sxs-lookup"><span data-stu-id="71482-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="71482-109">Causa</span><span class="sxs-lookup"><span data-stu-id="71482-109">Cause</span></span>

<span data-ttu-id="71482-110">Se o trabalho estiver associado a uma ordem de venda, não será possível cancelar a ordem de venda até que o trabalho seja cancelado e revertido.</span><span class="sxs-lookup"><span data-stu-id="71482-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="71482-111">Esse requisito se aplica mesmo que o trabalho associado à ordem de venda seja fechado.</span><span class="sxs-lookup"><span data-stu-id="71482-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="71482-112">Resolução</span><span class="sxs-lookup"><span data-stu-id="71482-112">Resolution</span></span>

<span data-ttu-id="71482-113">Para solucionar esse problema, conclua as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="71482-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="71482-114">Cancele o trabalho aberto.</span><span class="sxs-lookup"><span data-stu-id="71482-114">Cancel open work.</span></span>
1. <span data-ttu-id="71482-115">Excluir a carga.</span><span class="sxs-lookup"><span data-stu-id="71482-115">Delete the load.</span></span>
1. <span data-ttu-id="71482-116">Reduza a quantidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="71482-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="71482-117">Cancelar o trabalho aberto</span><span class="sxs-lookup"><span data-stu-id="71482-117">Cancel open work</span></span>

<span data-ttu-id="71482-118">Siga estas etapas para cancelar o trabalho aberto.</span><span class="sxs-lookup"><span data-stu-id="71482-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="71482-119">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Limpar \> Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="71482-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="71482-120">No campo **ID do trabalho**, especifique a ID do trabalho que deseja cancelar e que, atualmente, tem um valor **Status do trabalho** de *Aberto*, *Em andamento*, *Cancelado*, *Combinado* ou *Fechado*.</span><span class="sxs-lookup"><span data-stu-id="71482-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="71482-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="71482-121">Select **OK**.</span></span>
1. <span data-ttu-id="71482-122">Selecione **Sim** para confirmar que você deseja cancelar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="71482-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="71482-123">Excluir a carga</span><span class="sxs-lookup"><span data-stu-id="71482-123">Delete the load</span></span>

<span data-ttu-id="71482-124">Para excluir uma carga, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="71482-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="71482-125">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="71482-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71482-126">Abra a ordem de venda relevante.</span><span class="sxs-lookup"><span data-stu-id="71482-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="71482-127">Na FastTab **Linhas da ordem de venda**, selecione **Armazém \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="71482-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="71482-128">Na página **Trabalho**, no Painel de Ações, na guia **Trabalho**, no grupo **Trabalho**, selecione **Cancelar trabalho**.</span><span class="sxs-lookup"><span data-stu-id="71482-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="71482-129">Certifique-se de que o campo **Status do trabalho** está definido como *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="71482-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="71482-130">Feche a página **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="71482-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="71482-131">Na página de detalhes da ordem de venda, na FastTab **Linhas da ordem de venda**, selecione **Armazém \> Detalhes da carga**.</span><span class="sxs-lookup"><span data-stu-id="71482-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="71482-132">No Painel de Ações, selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="71482-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="71482-133">Selecione **Sim** para confirmar que você deseja excluir a carga.</span><span class="sxs-lookup"><span data-stu-id="71482-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="71482-134">Feche a página **Carga**.</span><span class="sxs-lookup"><span data-stu-id="71482-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="71482-135">Reduzir a quantidade selecionada</span><span class="sxs-lookup"><span data-stu-id="71482-135">Reduce the picked quantity</span></span>

<span data-ttu-id="71482-136">Após todo o trabalho ter sido cancelado, siga estas etapas para reduzir a quantidade selecionada.</span><span class="sxs-lookup"><span data-stu-id="71482-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="71482-137">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="71482-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71482-138">Abra a ordem de venda relevante.</span><span class="sxs-lookup"><span data-stu-id="71482-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="71482-139">Na FastTab **Linhas da ordem de venda**, selecione **Atualizar linha \> Selecionar** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="71482-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="71482-140">Na página **Selecionar**, na seção **Transações**, selecione a linha em que o campo **Status da emissão** está definido como *Selecionado*.</span><span class="sxs-lookup"><span data-stu-id="71482-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="71482-141">Na seção **Transações**, selecione **Adicionar linha de seleção** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="71482-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="71482-142">Na seção **Linhas de seleção**, selecione **Confirmar seleção de todos** na barra de ferramentas.</span><span class="sxs-lookup"><span data-stu-id="71482-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="71482-143">Feche a página **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="71482-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="71482-144">Na página de detalhes de ordem de venda, no Painel de Ações, na guia **Ordem de vendas**, no grupo **Manter**, selecione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="71482-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="71482-145">Selecione **Sim** para confirmar que você deseja cancelar a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="71482-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
