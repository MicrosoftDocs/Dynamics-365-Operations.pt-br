--- 
title: Gerenciar bloqueios de ordens
description: Este procedimento demonstra como colocar as ordens de venda do cliente em espera, como trabalhar com check-outs de bloqueio de ordem e como remover bloqueios de ordem.
author: omulvad
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: ad19ff166c15748b7bbb4b82ef71dbf3e1e8ebd2
ms.contentlocale: pt-br
ms.lasthandoff: 09/14/2018

---
# <a name="manage-order-holds"></a><span data-ttu-id="5a762-103">Gerenciar bloqueios de ordens</span><span class="sxs-lookup"><span data-stu-id="5a762-103">Manage order holds</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5a762-104">Este procedimento demonstra como colocar as ordens de venda do cliente em espera, como trabalhar com check-outs de bloqueio de ordem e como remover bloqueios de ordem.</span><span class="sxs-lookup"><span data-stu-id="5a762-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="5a762-105">Uma ordem pode ser colocada em espera por diversos motivos.</span><span class="sxs-lookup"><span data-stu-id="5a762-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="5a762-106">Por exemplo, você pode bloquear uma ordem até o endereço de um cliente ou o método de pagamento poder ser verificado ou até um gerente poder revisar o limite de crédito do cliente.</span><span class="sxs-lookup"><span data-stu-id="5a762-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="5a762-107">Enquanto a ordem estiver em espera, ela não poderá ser processada pelo depósito para remessa.</span><span class="sxs-lookup"><span data-stu-id="5a762-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="5a762-108">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="5a762-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="5a762-109">Configurar bloqueios de ordem</span><span class="sxs-lookup"><span data-stu-id="5a762-109">Set up order holds</span></span>
1. <span data-ttu-id="5a762-110">Vá para Vendas e marketing > Configuração > Ordens de venda > Códigos de bloqueio de ordem.</span><span class="sxs-lookup"><span data-stu-id="5a762-110">Go to Sales and marketing > Setup > Sales orders > Order hold codes.</span></span>
2. <span data-ttu-id="5a762-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5a762-111">Click New.</span></span>
3. <span data-ttu-id="5a762-112">No campo Código de bloqueio, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a762-112">In the Hold code field, type a value.</span></span>
    * <span data-ttu-id="5a762-113">Por exemplo, digite Retorno de chamada.</span><span class="sxs-lookup"><span data-stu-id="5a762-113">For example, type Call back.</span></span>  
4. <span data-ttu-id="5a762-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="5a762-114">In the Description field, type a value.</span></span>
    * <span data-ttu-id="5a762-115">Por exemplo, ordem bloqueada aguardando retorno de chamada do cliente.</span><span class="sxs-lookup"><span data-stu-id="5a762-115">For example, Order held waiting for customer callback.</span></span>  
    * <span data-ttu-id="5a762-116">Opcionalmente, selecione a caixa de seleção Remover reservas para remover qualquer reserva física da ordem quando esse código de bloqueio for adicionado.</span><span class="sxs-lookup"><span data-stu-id="5a762-116">Optionally, select the Remove reservations check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="5a762-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5a762-117">Click Save.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="5a762-118">Colocar ordem em espera</span><span class="sxs-lookup"><span data-stu-id="5a762-118">Place order on hold</span></span>
1. <span data-ttu-id="5a762-119">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="5a762-119">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="5a762-120">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5a762-120">Click New.</span></span>
3. <span data-ttu-id="5a762-121">No campo Conta de cliente, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5a762-121">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="5a762-122">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="5a762-122">Click OK.</span></span>
5. <span data-ttu-id="5a762-123">No campo Número do item, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="5a762-123">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="5a762-124">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="5a762-124">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="5a762-125">No Painel de Ação, clique em Ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5a762-125">On the Action Pane, click Sales order.</span></span>
8. <span data-ttu-id="5a762-126">Clique em Bloqueios de ordem.</span><span class="sxs-lookup"><span data-stu-id="5a762-126">Click Order holds.</span></span>
9. <span data-ttu-id="5a762-127">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="5a762-127">Click New.</span></span>
10. <span data-ttu-id="5a762-128">No campo Código de bloqueio, selecione o código que você criou na subtarefa anterior.</span><span class="sxs-lookup"><span data-stu-id="5a762-128">In the Hold code field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="5a762-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="5a762-129">Click Save.</span></span>
12. <span data-ttu-id="5a762-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="5a762-130">Close the page.</span></span>
13. <span data-ttu-id="5a762-131">Vá para Vendas e marketing > Ordens de venda > Todas as ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="5a762-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
14. <span data-ttu-id="5a762-132">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a762-132">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="5a762-133">Ordens que estão atualmente em espera têm os campos "Não processar" e "Em espera" marcados.</span><span class="sxs-lookup"><span data-stu-id="5a762-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>    
15. <span data-ttu-id="5a762-134">No Painel de Ação, clique em Separar e empacotar.</span><span class="sxs-lookup"><span data-stu-id="5a762-134">On the Action Pane, click Pick and pack.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="5a762-135">Gerenciar bloqueios de ordens</span><span class="sxs-lookup"><span data-stu-id="5a762-135">Manage order holds</span></span>
1. <span data-ttu-id="5a762-136">Vá para Vendas e marketing > Ordens de venda > Ordens em aberto > Bloqueios da ordem.</span><span class="sxs-lookup"><span data-stu-id="5a762-136">Go to Sales and marketing > Sales orders > Open orders > Order holds.</span></span>
    * <span data-ttu-id="5a762-137">A página de bloqueio de ordens funciona como uma bancada na qual você pode obter uma visão geral de todas os bloqueios atuais e processados e controlá-los, bem como das ordens de venda associadas.</span><span class="sxs-lookup"><span data-stu-id="5a762-137">Order holds page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>      
2. <span data-ttu-id="5a762-138">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a762-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="5a762-139">No Painel de Ação, clique em Bloquear finalização da compra.</span><span class="sxs-lookup"><span data-stu-id="5a762-139">On the Action Pane, click Hold checkout.</span></span>
4. <span data-ttu-id="5a762-140">Clique em Fazer check-out.</span><span class="sxs-lookup"><span data-stu-id="5a762-140">Click Check out.</span></span>
5. <span data-ttu-id="5a762-141">Na lista, desmarque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="5a762-141">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="5a762-142">O campo Check-out para mostra sua ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="5a762-142">The Checkout out to field now shows your user ID.</span></span>   
6. <span data-ttu-id="5a762-143">Clique em Liberar check-out.</span><span class="sxs-lookup"><span data-stu-id="5a762-143">Click Clear checkout.</span></span>
7. <span data-ttu-id="5a762-144">No Painel de Ação, clique em Liberar bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5a762-144">On the Action Pane, click Clear hold.</span></span>
    * <span data-ttu-id="5a762-145">Quando estiver pronto para remover o bloqueio e permitir que a ordem siga para a próxima etapa de realização, você precisará limpar o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="5a762-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="5a762-146">Se a ordem não exigir qualquer alteração, você poderá executar a ação Liberar bloqueios.</span><span class="sxs-lookup"><span data-stu-id="5a762-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="5a762-147">No entanto, você poderá usar a ação Liberar e modificar se, ao liberar um bloqueio, a ordem precisar ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="5a762-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    * <span data-ttu-id="5a762-148">A ação de limpar e enviar só é aplicável quando você usa a funcionalidade de call center.</span><span class="sxs-lookup"><span data-stu-id="5a762-148">The Clear and submit action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="5a762-149">Clicar em Liberar bloqueios.</span><span class="sxs-lookup"><span data-stu-id="5a762-149">Click Clear holds.</span></span>
    * <span data-ttu-id="5a762-150">Agora o bloqueio está liberado na ordem e removido da lista de bloqueios ativos.</span><span class="sxs-lookup"><span data-stu-id="5a762-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="5a762-151">Para ver todos os bloqueios ou seu subconjunto de acordo com um status específico, mude o valor no campo Mostrar.</span><span class="sxs-lookup"><span data-stu-id="5a762-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     


