--- 
title: "Criar uma ordem de produção"
description: "Este procedimento mostra como criar uma ordem de produção."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 730adcea0ac59f683ecae8cbb62025bd7db75c55
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-production-order"></a><span data-ttu-id="d2a1c-103">Criar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d2a1c-103">Create a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d2a1c-104">Este procedimento mostra como criar uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="d2a1c-105">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d2a1c-106">Este é o primeiro procedimento fora de sete que explica o ciclo de vida da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="d2a1c-107">Criar uma ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d2a1c-107">Create a production order</span></span>
1. <span data-ttu-id="d2a1c-108">Vá para Controle de produção > Ordens de produção > Todas as ordens de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="d2a1c-109">Clique em Nova ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-109">Click New production order.</span></span>
3. <span data-ttu-id="d2a1c-110">No campo Número do item, digite 'D0001'.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="d2a1c-111">No campo Entrega, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="d2a1c-112">A data de entrega indica quando a ordem de produção deve terminar a fim de entregar à tempo.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="d2a1c-113">Esta data pode ser usada no processo de agendamento.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="d2a1c-114">Por exemplo, você pode programar o pedido de retrocessão para data de entrega.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="d2a1c-115">Defina a quantidade como '20'.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="d2a1c-116">Observação: O campo número de BOM exibe automaticamente o número de qualquer BOM ativo para o item atual, mas você pode alterar a BOM para a ordem de produção ao selecionar uma BOM ativa na lista de versões da BOM aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="d2a1c-117">O campo número de Rota exibe automaticamente o número de qualquer Rota ativa para o item atual, mas você pode alterar a Rota para a ordem de produção ao selecionar uma Rota ativa na lista de versões da Rota aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="d2a1c-118">Clique em Criar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="d2a1c-119">Validar a ordem de produção</span><span class="sxs-lookup"><span data-stu-id="d2a1c-119">Validate the production order</span></span>
1. <span data-ttu-id="d2a1c-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d2a1c-121">Clique no link para o número da ordem de produção que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="d2a1c-122">Isso abrirá a página de detalhes da ordem.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="d2a1c-123">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-123">Click Edit.</span></span>
3. <span data-ttu-id="d2a1c-124">No campo Entrega, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="d2a1c-125">Por exemplo, você pode alterar a data de entrega da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="d2a1c-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-126">Click Save.</span></span>
5. <span data-ttu-id="d2a1c-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="d2a1c-128">Atualizar BOM</span><span class="sxs-lookup"><span data-stu-id="d2a1c-128">Update the BOM</span></span>
1. <span data-ttu-id="d2a1c-129">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="d2a1c-130">Clicar em BOM.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-130">Click BOM.</span></span>
    * <span data-ttu-id="d2a1c-131">Abra a página BOM para validar os dados da BOM que foram copiados de dados padrão quando a ordem de produção foi criada.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="d2a1c-132">Nesse procedimento, você precisa atualizar a quantidade para uma BOM.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="d2a1c-133">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-133">Click Edit.</span></span>
4. <span data-ttu-id="d2a1c-134">No campo Quantidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="d2a1c-135">Alterar a quantidade na linha de BOM tem previsão de custo de consumo de material para a ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="d2a1c-136">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-136">Click Save.</span></span>
6. <span data-ttu-id="d2a1c-137">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="d2a1c-138">Atualizar os roteiros de produção</span><span class="sxs-lookup"><span data-stu-id="d2a1c-138">Update the production route</span></span>
1. <span data-ttu-id="d2a1c-139">No Painel de Ação, clique em Ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="d2a1c-140">Clique em Rota.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-140">Click Route.</span></span>
    * <span data-ttu-id="d2a1c-141">Abra a página Rota para validar os dados da da rota de produção que foram copiados de dados padrão quando a ordem de produção foi criada.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="d2a1c-142">Nesse procedimento, você precisa atualizar a quantidade de uma das operações no roteiro de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="d2a1c-143">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="d2a1c-144">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-144">Click Edit.</span></span>
5. <span data-ttu-id="d2a1c-145">Em Processar quantidade. insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="d2a1c-146">Alterar o tempo de processo afeta o consumo de roteiro custos previstos e da ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="d2a1c-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-147">Click Save.</span></span>
7. <span data-ttu-id="d2a1c-148">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2a1c-148">Close the page.</span></span>


