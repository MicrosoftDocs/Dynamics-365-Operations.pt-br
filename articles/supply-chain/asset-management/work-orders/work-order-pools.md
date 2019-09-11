---
title: Grupos de ordens de serviço
description: Este tópico descreve como trabalhar com grupos de ordens de serviço no Gerenciamento de ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875505"
---
# <a name="work-order-pools"></a><span data-ttu-id="9d47e-103">Grupos de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="9d47e-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="9d47e-104">Você pode usar grupos de ordens de serviço para ordens de serviço de grupo com algo em comum.</span><span class="sxs-lookup"><span data-stu-id="9d47e-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="9d47e-105">Por exemplo, você pode criar grupos de ordens de serviço para</span><span class="sxs-lookup"><span data-stu-id="9d47e-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="9d47e-106">equipes de trabalho, por exemplo, Equipe de Manutenção A, Equipe de Manutenção B</span><span class="sxs-lookup"><span data-stu-id="9d47e-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="9d47e-107">habilidades profissionais, por exemplo, eletricistas ou encanadores</span><span class="sxs-lookup"><span data-stu-id="9d47e-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="9d47e-108">locais físicos</span><span class="sxs-lookup"><span data-stu-id="9d47e-108">physical locations</span></span>  

- <span data-ttu-id="9d47e-109">cronogramas, por exemplo, semanas ou outros períodos</span><span class="sxs-lookup"><span data-stu-id="9d47e-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="9d47e-110">Se necessário, uma ordem de serviço pode ser colocada em vários grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="9d47e-111">Criar grupo de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="9d47e-111">Create work order pool</span></span>

<span data-ttu-id="9d47e-112">Em **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**, você obterá uma visão geral dos grupos de serviço e criará novos grupos.</span><span class="sxs-lookup"><span data-stu-id="9d47e-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="9d47e-113">Clique em **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="9d47e-114">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-114">Click **New**.</span></span>

3. <span data-ttu-id="9d47e-115">Insira uma ID de grupo de ordens de serviço no campo **Grupo** e um nome no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="9d47e-116">Selecione "Sim" no botão de alternância **Ativo** para indicar que o grupo de ordens de serviço está ativo.</span><span class="sxs-lookup"><span data-stu-id="9d47e-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="9d47e-117">Selecione "Sim" no botão de alternância **Excluir relações de ordem de serviço** se desejar que as ordens de serviço sejam automaticamente removidas do grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="9d47e-118">No campo **Excluir estado de ciclo de vida**, selecione o estado de ciclo de vida da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="9d47e-119">Por exemplo, o estado de ciclo de vida da ordem de serviço para concluir uma ordem de serviço pode ser definido para excluir automaticamente as relações com grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="9d47e-120">Você pode começar a adicionar ordens de serviço ao seu grupo de ordens de serviço imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9d47e-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="9d47e-121">Na Guia Rápida **Ordens de serviço**, clique em **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="9d47e-122">Selecione uma ordem de serviço no campo **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="9d47e-123">Os campos relacionados são automaticamente atualizados.</span><span class="sxs-lookup"><span data-stu-id="9d47e-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="9d47e-124">Repita as etapas 7 e 8 se desejar adicionar mais ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="9d47e-125">No campo **Ordem de classificação**, você pode indicar se as ordens de serviço devem ser realizadas em qualquer ordem.</span><span class="sxs-lookup"><span data-stu-id="9d47e-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="9d47e-126">Insira os números 1, 2, 3 e assim por diante para indicar uma sequência específica para as ordens de serviço selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9d47e-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="9d47e-127">Clique no botão **Ordens de serviço** para ver uma lista de todas as ordens de serviço incluídas no grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="9d47e-128">Clique no botão **Capacidade máxima** para abrir **Capacidade máxima** para calcular e exibir a capacidade máxima para o agendamento de manutenção, as ordens de serviço não agendadas e as ordens de serviço agendadas.</span><span class="sxs-lookup"><span data-stu-id="9d47e-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="9d47e-129">Clique no botão **Previsão de itens** para abrir **Previsão de itens** para calcular e exibir previsões para itens (partes sobressalentes e outros itens obrigatórios) relacionados ao agendamento de manutenção, às ordens de serviço não agendadas e às ordens de serviço agendadas.</span><span class="sxs-lookup"><span data-stu-id="9d47e-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="9d47e-130">Clique no botão **Requisição de compra da ordem de serviço** para abrir a lista **Requisição de compra da ordem de serviço** para ver uma lista de requisições de compra relacionadas às ordens de serviço no grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="9d47e-131">Clique no botão **Requisição de compra da ordem de serviço** para abrir a lista **Requisição de compra da ordem de serviço** para ver uma lista de ordens de compra relacionadas às ordens de serviço no grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="9d47e-132">Quando um grupo de ordens de serviço não for mais relevante para seu planejamento de trabalho, defina a caixa de seleção **Ativo** do grupo como "Não" na exibição de lista **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="9d47e-133">Marque a caixa de seleção **Excluir relações de ordem de serviço** se quiser excluir todas as linhas da ordem de serviço, por exemplo, para criar um grupo vazio que poderá ser usado posteriormente para outras ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="9d47e-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="9d47e-134">Lembre-se de desmarcar a caixa de seleção **Excluir relações de ordem de serviço** se quiser usar o grupo de ordens de serviço para criar novas relações de ordem de serviço posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9d47e-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="9d47e-136">Adicionar a ordem de serviço em um grupo de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="9d47e-136">Add work order to a work order pool</span></span>

<span data-ttu-id="9d47e-137">Conforme descrito na seção acima, você poderá adicionar ordens de serviço a um grupo de ordens de serviço ao criá-lo.</span><span class="sxs-lookup"><span data-stu-id="9d47e-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="9d47e-138">Você também pode adicionar uma ordem de serviço a um grupo de ordens de serviço de uma da lista **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="9d47e-139">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="9d47e-140">Selecione a ordem de serviço na lista e clique em **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="9d47e-141">Selecione "Adicionar" no campo **Adicionar/remover**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="9d47e-142">Selecione o grupo de ordens de serviço no campo **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="9d47e-143">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-143">Click **OK**.</span></span>

6. <span data-ttu-id="9d47e-144">Depois de adicionar uma ordem de serviço a um grupo de ordens de serviço, se você quiser colocar a ordem de serviço em uma sequência específica no grupo: abra uma das páginas de listagem de grupos de ordens de serviço, selecione o grupo e clique em **Editar**, ajuste a ordem de classificação das ordens de serviço incluídas no grupo em formulário **Grupo de ordens de serviço** > Guia Rápida **Ordens de serviço** > campo **Ordem de classificação**.</span><span class="sxs-lookup"><span data-stu-id="9d47e-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="9d47e-145">Se quiser remover a ordem de serviço selecionada em um grupo de ordens de serviço, selecione "Remover" na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="9d47e-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

