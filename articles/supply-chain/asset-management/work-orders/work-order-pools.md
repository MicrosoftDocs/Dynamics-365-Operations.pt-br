---
title: Grupos de ordens de serviço
description: Este tópico descreve como trabalhar com grupos de ordens de serviço no Gerenciamento de ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: afea5b8d0f958c3ab53d6cef8c9a0e9030d7c67b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017507"
---
# <a name="work-order-pools"></a><span data-ttu-id="b0408-103">Grupos de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="b0408-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="b0408-104">Você pode usar grupos de ordens de serviço para ordens de serviço de grupo com algo em comum.</span><span class="sxs-lookup"><span data-stu-id="b0408-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="b0408-105">Veja alguns exemplos de situações para as quais você pode criar grupos de ordem de serviço:</span><span class="sxs-lookup"><span data-stu-id="b0408-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="b0408-106">Equipes de trabalho, por exemplo, Equipe de manutenção A ou Equipe de manutenção B</span><span class="sxs-lookup"><span data-stu-id="b0408-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="b0408-107">Habilidades profissionais, como eletricistas ou encanadores</span><span class="sxs-lookup"><span data-stu-id="b0408-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="b0408-108">Locais físicos</span><span class="sxs-lookup"><span data-stu-id="b0408-108">Physical locations</span></span>  

- <span data-ttu-id="b0408-109">Cronogramas, como semanas ou outros períodos</span><span class="sxs-lookup"><span data-stu-id="b0408-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="b0408-110">De acordo com a sua necessidade, você pode inserir uma ordem de serviço em vários grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="b0408-111">Criar um grupo de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="b0408-111">Create a work order pool</span></span>

<span data-ttu-id="b0408-112">Na página de listagem **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**, você obterá uma visão geral dos grupos de ordens de serviço e criará novos grupos.</span><span class="sxs-lookup"><span data-stu-id="b0408-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="b0408-113">Selecione **Gerenciamento de ativos** > **Comum** > **Grupos de ordens de serviço** > **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativos**.</span><span class="sxs-lookup"><span data-stu-id="b0408-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="b0408-114">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b0408-114">Select **New**.</span></span>

3. <span data-ttu-id="b0408-115">No campo **Grupo**, insira um identificador para o grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="b0408-116">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="b0408-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="b0408-117">Defina a opção **Ativo** como **Sim** para indicar que o grupo de ordens de serviço está ativo.</span><span class="sxs-lookup"><span data-stu-id="b0408-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="b0408-118">Defina a opção **Excluir relações de ordem de serviço** como **Sim** se desejar que as ordens de serviço sejam automaticamente removidas do grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="b0408-119">No campo **Excluir estado de ciclo de vida**, selecione o estado de ciclo de vida da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="b0408-120">Por exemplo, o estado de ciclo de vida da ordem de serviço para concluir uma ordem de serviço pode ser definido para excluir automaticamente as relações com grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="b0408-121">Você pode começar a adicionar ordens de serviço ao seu grupo de ordens de serviço imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b0408-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="b0408-122">Na Guia Rápida **Ordens de serviço**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="b0408-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="b0408-123">No campo **Ordem de serviço**, selecione uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="b0408-124">Os campos relacionados são automaticamente atualizados.</span><span class="sxs-lookup"><span data-stu-id="b0408-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="b0408-125">Repita as etapas 8 a 9 para adicionar mais ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="b0408-126">Se as ordens de serviço adicionadas forem efetuadas em uma ordem específica, no campo **Ordem de classificação**, você pode inserir os números **1**, **2**, **3**, e assim por diante, para especificar a ordem.</span><span class="sxs-lookup"><span data-stu-id="b0408-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="b0408-127">Para visualizar uma lista de todas as ordens de serviço incluídas no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Ordens de serviço** para abrir a página de listagem **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="b0408-128">Para calcular e visualizar a capacidade máxima do agendamento de manutenção, ordens de serviço não agendadas e ordens de serviço agendadas, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Capacidade máxima** para abrir a caixa de diálogo **Calcular capacidade máxima**.</span><span class="sxs-lookup"><span data-stu-id="b0408-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="b0408-129">Para calcular e visualizar previsões de itens (peças sobressalentes e outros itens necessários) relacionadas ao agendamento de manutenção, ordens de serviço não agendadas e ordens de serviço agendadas, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Visualizar grupo de ordens de serviço relacionado**, selecione **Previsão de itens** para abrir a caixa de diálogo **Calcular previsão de itens**.</span><span class="sxs-lookup"><span data-stu-id="b0408-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="b0408-130">Para visualizar uma lista de requisições de compra relacionadas às ordens de serviço no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Compras**, selecione **Requisição de compra da ordem de serviço** para abrir a página de listagem **Requisição de compra da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="b0408-131">Para visualizar uma lista de ordens de compra relacionadas às ordens de serviço no grupo de ordens de serviço, no Painel de ações, na guia **Grupo de ordens de serviço**, no grupo **Compras**, selecione **Compra da ordem de serviço** para abrir a página de listagem **Compra da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="b0408-132">Quando um grupo de ordens de serviço não for mais relevante para seu planejamento de trabalho, defina a opção **Ativo** do grupo como **Não** na exibição de lista da página **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="b0408-133">Para excluir todas as linhas da ordem de serviço, defina a opção **Excluir relações da ordem de serviço** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="b0408-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="b0408-134">Esta opção é útil se, por exemplo, você quiser criar um grupo vazio que poderá usar posteriormente para outras ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="b0408-135">Quando estiver pronto para usar o grupo de ordens de serviço para criar novas relações de ordens de serviço posteriormente, lembre-se de definir a opção **Excluir relações da ordem de serviço** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="b0408-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="b0408-136">A ilustração a seguir mostra um exemplo da página de listagem **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Figura 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="b0408-138">Adicionar uma ordem de serviço a um grupo de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="b0408-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="b0408-139">Conforme descrito na seção anterior, você poderá adicionar ordens de serviço a um grupo de ordens de serviço ao criá-lo.</span><span class="sxs-lookup"><span data-stu-id="b0408-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="b0408-140">Você também pode adicionar ordens de serviço a um grupo de ordens de serviço na página de listagem **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="b0408-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="b0408-141">Selecione a ordem de serviço e, no Painel de Ação, na guia **Ordem de serviço**, no grupo **Manter**, selecione **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="b0408-142">Selecione a ordem de serviço na lista e clique em **Grupo de ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="b0408-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="b0408-143">Na caixa de diálogo **Manter grupo de ordens de serviço**, no campo **Adicionar/remover**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b0408-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="b0408-144">No campo **Grupo**, selecione o grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="b0408-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="b0408-145">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0408-145">Select **OK**.</span></span>

6. <span data-ttu-id="b0408-146">Para colocar a ordem de serviço que você adicionou em uma ordem específica no grupo de ordens de serviço, na página de listagem **Todos os grupos de ordens de serviço** ou **Grupos de ordens de serviço ativas**, selecione o grupo e depois **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b0408-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="b0408-147">Em seguida, na página **Grupo de ordens de serviço** na Guia Rápida **Ordens de serviço**, use o campo **Ordem de classificação** para ajustar a ordem das ordens de serviço incluídas no grupo.</span><span class="sxs-lookup"><span data-stu-id="b0408-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="b0408-148">Para remover uma ordem de serviço de um grupo de ordens de serviço, repita essas etapas, mas selecione **Remover** na etapa 3.</span><span class="sxs-lookup"><span data-stu-id="b0408-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>

