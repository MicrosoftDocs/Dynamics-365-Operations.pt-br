---
title: Ordens de serviço criadas manualmente
description: Este tópico explica como criar ordens de serviço manualmente no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 4a4b148d9ac5d032d2caa5fcea0398a5a3726f0e
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888968"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="e1178-103">Ordens de serviço criadas manualmente</span><span class="sxs-lookup"><span data-stu-id="e1178-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="e1178-104">É possível criar ordens de serviço manualmente de duas formas:</span><span class="sxs-lookup"><span data-stu-id="e1178-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="e1178-105">Na página **Todas as ordens de serviço** ou **Ordens de serviço ativas**</span><span class="sxs-lookup"><span data-stu-id="e1178-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="e1178-106">Na página **Todas as solicitações de manutenção**, **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**</span><span class="sxs-lookup"><span data-stu-id="e1178-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="e1178-107">Criar ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="e1178-107">Create work order</span></span>

1. <span data-ttu-id="e1178-108">Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="e1178-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e1178-109">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e1178-109">Select **New**.</span></span>

3. <span data-ttu-id="e1178-110">Na caixa de diálogo **Criar ordem de serviço**, selecione um tipo de ordem de serviço no campo **Tipo de ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="e1178-111">Se necessário, selecione uma **Descrição**.</span><span class="sxs-lookup"><span data-stu-id="e1178-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="e1178-112">Selecione o ativo no campo **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="e1178-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="e1178-113">Quando você seleciona um ativo, três guias podem ficar disponíveis no menu suspenso **Ativo**:</span><span class="sxs-lookup"><span data-stu-id="e1178-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="e1178-114">**Ativos ativos** - Esta guia contém uma lista de todos os ativos com o estado de ciclo de vida do ativo "Ativo".</span><span class="sxs-lookup"><span data-stu-id="e1178-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="e1178-115">**Exibição de ativo** - Esta guia apresenta um modo de exibição de árvore dos locais funcionais e dos ativos instalados nesses locais.</span><span class="sxs-lookup"><span data-stu-id="e1178-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="e1178-116">**Meus ativos** - Esta guia contém os ativos relacionados aos locais funcionais aos quais você (o trabalhador conectado ao sistema) pode ser atribuído.</span><span class="sxs-lookup"><span data-stu-id="e1178-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="e1178-117">(Para obter informações sobre a configuração, consulte [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).) Se nenhum local funcional estiver configurado em um trabalhador em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md), a guia **Meus ativos** não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="e1178-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="e1178-118">No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho de manutenção para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="e1178-119">Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício**.</span><span class="sxs-lookup"><span data-stu-id="e1178-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="e1178-120">Se necessário, você pode alterar o nível de serviço da ordem de serviço no campo **Nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="e1178-121">Selecione a **Data de início esperada** e a **Data de término esperada** nos campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="e1178-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="e1178-122">Clique em **OK** para criar a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="e1178-123">Na página de listagem **Todas as ordens de serviço**, é possível editar a ordem de serviço conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="e1178-124">Observe os seguintes pontos:</span><span class="sxs-lookup"><span data-stu-id="e1178-124">Note the following points:</span></span>

- <span data-ttu-id="e1178-125">Na exibição de detalhes da página de listagem **Todas ordens de serviço**, você pode incluir vários ativos para uma ordem de serviço, adicionando linhas na Guia Rápida **Trabalhos de manutenção da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="e1178-126">Em um ativo, você pode selecionar apenas os tipos de trabalho de manutenção definidos no tipo de ativo selecionado no ativo.</span><span class="sxs-lookup"><span data-stu-id="e1178-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="e1178-127">Se você alterar o nível de serviço ou a severidade de um ativo depois de já ter usado o ativo em uma ordem de serviço, o nível de serviço ou a severidade na ordem de serviço não será atualizada de forma correspondente.</span><span class="sxs-lookup"><span data-stu-id="e1178-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="e1178-128">Para obter mais informações sobre níveis de serviço e severidades, consulte [Níveis de serviço do ativo](../setup-for-objects/object-priorities.md) e [Tipos de severidade do ativo](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="e1178-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="e1178-129">A severidade em uma ordem de serviço é recalculada sempre que um trabalho da ordem de serviço é adicionado ou excluído da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="e1178-130">Na exibição de detalhes **Todas as ordens de serviço** > guia **Cabeçalho** > Guia Rápida **Agendar**, você pode selecionar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável nos campos **Grupo responsável** ou **Responsável**.</span><span class="sxs-lookup"><span data-stu-id="e1178-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="e1178-131">Essas configurações podem ser alteradas enquanto a ordem de serviço está ativa.</span><span class="sxs-lookup"><span data-stu-id="e1178-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="e1178-132">Por exemplo, elas podem ser alteradas quando o estado de ciclo de vida da ordem de serviço é alterado.</span><span class="sxs-lookup"><span data-stu-id="e1178-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="e1178-133">A seleção automática feita durante a criação da ordem de serviço é baseada na configuração na página **Funcionários de manutenção responsáveis**.</span><span class="sxs-lookup"><span data-stu-id="e1178-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="e1178-134">Se você adicionar ou remover trabalhos da ordem de serviço após ter criado uma ordem de serviço e os campos **Grupo responsável** e **Responsável** estiverem em branco quando você atualizar a ordem de serviço, o Gerenciamento de Ativos tentará encontrar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável para obter uma possível correspondência na página de configuração.</span><span class="sxs-lookup"><span data-stu-id="e1178-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="e1178-135">Se o campo **Grupo responsável** ou **Responsável** já estiver definido quando você atualizar a ordem de serviço, nenhuma alteração será feita.</span><span class="sxs-lookup"><span data-stu-id="e1178-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="e1178-136">Para obter informações sobre funcionários de manutenção responsáveis e grupos de funcionários, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="e1178-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="e1178-137">Na página [Status de manutenção](../controlling-and-reporting/maintenance-status.md), você pode fazer um cálculo para obter uma visão geral da carga de trabalho de ordens de serviço recebidas e concluídas.</span><span class="sxs-lookup"><span data-stu-id="e1178-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="e1178-138">Na exibição de detalhes da página **Todas as ordens de serviço**, na Guia Rápida **Detalhes da linha**, você pode usar os campos **Latitude** e **Longitude** para adicionar coordenadas geográficas para o ativo selecionado no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="e1178-139">Criar ordem de serviço relacionada</span><span class="sxs-lookup"><span data-stu-id="e1178-139">Create related work order</span></span>

<span data-ttu-id="e1178-140">Você pode criar uma ordem de serviço relacionada a uma ordem de serviço existente.</span><span class="sxs-lookup"><span data-stu-id="e1178-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="e1178-141">Esse recurso é útil se você, por exemplo, quiser trabalhar com ordens de serviço primárias e secundárias.</span><span class="sxs-lookup"><span data-stu-id="e1178-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="e1178-142">Uma nova ordem de serviço é baseada em um trabalho da ordem de serviço de uma ordem de serviço existente.</span><span class="sxs-lookup"><span data-stu-id="e1178-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="e1178-143">Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="e1178-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e1178-144">Selecione a ordem de serviço para criar uma ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="e1178-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="e1178-145">No Painel de Ação, na guia **Ordem de serviço**, no grupo **Novo**, selecione **Ordem de serviço relacionada**.</span><span class="sxs-lookup"><span data-stu-id="e1178-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="e1178-146">Na caixa de diálogo **Criar ordem de serviço relacionada**, no campo **Trabalho da ordem de serviço**, selecione o trabalho da ordem de serviço para o qual criar uma ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="e1178-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="e1178-147">No campo **Tipo de trabalho de manutenção**, selecione o tipo de trabalho de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e1178-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="e1178-148">Nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**, selecione um tipo de trabalho de manutenção e um ofício relacionados, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="e1178-149">Se essa for a primeira ordem de serviço relacionada criada para a ordem de serviço selecionada, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="e1178-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="e1178-150">Selecione a opção **Nova ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="e1178-151">No campo **Tipo de ordem de serviço**, selecione um tipo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="e1178-152">Em **Descrição**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="e1178-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="e1178-153">Altere o nível de serviço da ordem de serviço no campo **Nível de serviço**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="e1178-154">Nos campos **Data de início esperada** e **Data de término esperada**, selecione as datas de início e término esperadas.</span><span class="sxs-lookup"><span data-stu-id="e1178-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="e1178-155">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1178-155">Select **OK**.</span></span> <span data-ttu-id="e1178-156">A nova ordem de serviço relacionada é exibida na página de listagem **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="e1178-157">Se a ordem de serviço para a qual você está criando essa ordem de serviço relacionada já tiver ordens de serviço relacionadas, siga estas etapas para adicionar um novo trabalho de ordem de serviço a uma ordem de serviço relacionada existente:</span><span class="sxs-lookup"><span data-stu-id="e1178-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="e1178-158">Selecione a opção **Adicionar à ordem de serviço relacionada**.</span><span class="sxs-lookup"><span data-stu-id="e1178-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="e1178-159">No campo **Ordem de serviço**, selecione a ordem de serviço relacionada à qual adicionar um novo trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="e1178-160">Altere o nível de serviço da ordem de serviço no campo **Nível de serviço**, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="e1178-161">Nos campos **Data de início esperada** e **Data de término esperada**, altere as datas de início e término esperadas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="e1178-162">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1178-162">Select **OK**.</span></span> <span data-ttu-id="e1178-163">O trabalho da ordem de serviço é adicionado à ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="e1178-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="e1178-164">A ilustração a seguir mostra um exemplo da caixa de diálogo **Criar ordem de serviço relacionada**.</span><span class="sxs-lookup"><span data-stu-id="e1178-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Figura 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="e1178-166">Se você configurou uma máscara da ordem de serviço relacionada em **Parâmetros de gerenciamento de ativos** > guia **Ordens de serviço** > campo **Máscara da ordem de serviço relacionada**, as IDs da ordem de serviço serão criadas de acordo com a configuração da máscara.</span><span class="sxs-lookup"><span data-stu-id="e1178-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="e1178-167">Se nenhuma máscara da ordem de serviço relacionada estiver configurada, a próxima ID da ordem de serviço disponível será usada para ordens de serviço relacionadas.</span><span class="sxs-lookup"><span data-stu-id="e1178-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="e1178-168">Copiar uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="e1178-168">Copy a work order</span></span>

<span data-ttu-id="e1178-169">É possível criar uma nova ordem de serviço rapidamente por meio de uma ordem de serviço existente.</span><span class="sxs-lookup"><span data-stu-id="e1178-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="e1178-170">Essa forma de trabalhar com ordens de serviço é diferente de criar ordens de serviço com base em [planos de manutenção](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e1178-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="e1178-171">É útil se, por exemplo, uma ordem de serviço tiver vários trabalhos de ordem de serviço, e esses vários trabalhos tiverem de ser concluídos em ativos diferentes em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="e1178-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="e1178-172">Selecione **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="e1178-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="e1178-173">Selecione a ordem de serviço da qual copiar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e1178-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="e1178-174">No Painel de Ação > guia **Ordem de serviço** > grupo **Novo**, selecione **Copiar ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="e1178-175">A configuração da ordem de serviço selecionada é mostrada.</span><span class="sxs-lookup"><span data-stu-id="e1178-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="e1178-176">Você pode editar alguns campos, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="e1178-177">Selecione **OK** para criar a nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="e1178-178">Na página de listagem **Todas as ordens de serviço**, é possível editar a ordem de serviço conforme o necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="e1178-179">Quando a nova ordem de serviço for criada, algumas informações serão copiadas diretamente da existente.</span><span class="sxs-lookup"><span data-stu-id="e1178-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="e1178-180">Informações sobre previsões, ferramentas, listas de verificação de manutenção, local funcional, endereços e agendamentos não são copiados.</span><span class="sxs-lookup"><span data-stu-id="e1178-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="e1178-181">Em vez disso, são inicializados na configuração atual no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="e1178-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="e1178-182">Portanto, se essas informações tiverem sido alteradas entre o momento em que a primeira ordem de serviço foi criada e o momento em que você fez uma cópia da ordem de serviço, as alterações serão incluídas na nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="e1178-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="e1178-183">Os exemplos incluem alterações nas previsões e atualizações de listas de verificação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e1178-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="e1178-184">A ilustração a seguir mostra um exemplo da caixa de diálogo **Copiar ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Figura 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="e1178-186">Criar uma ordem de serviço com base em uma solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="e1178-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="e1178-187">Selecione **Gerenciamento de ativos** > **Comum** > **Solicitações de manutenção** > **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**.</span><span class="sxs-lookup"><span data-stu-id="e1178-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="e1178-188">Selecione a solicitação de manutenção para a qual criar uma ordem de serviço e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1178-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="e1178-189">No Painel de Ação > guia **Solicitação de manutenção** > grupo **Novo**, selecione **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="e1178-190">Na caixa de diálogo **Ordem de serviço**, defina os campos.</span><span class="sxs-lookup"><span data-stu-id="e1178-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="e1178-191">Se um tipo de trabalho de manutenção tiver sido selecionado na solicitação de manutenção, você poderá selecionar outro tipo de trabalho de manutenção ao criar a ordem de serviço, se necessário.</span><span class="sxs-lookup"><span data-stu-id="e1178-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="e1178-192">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1178-192">Select **OK**.</span></span> <span data-ttu-id="e1178-193">Uma mensagem informa que a ordem de serviço foi criada.</span><span class="sxs-lookup"><span data-stu-id="e1178-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="e1178-194">Para exibir as ordens de serviço vinculadas a uma solicitação de manutenção, na página de listagem **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**, selecione a solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e1178-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="e1178-195">Em seguida, no Painel de Ação, na guia **Solicitação de manutenção**, no grupo **Novo**, selecione **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="e1178-196">A ilustração a seguir mostra um exemplo da caixa de diálogo **Criar ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="e1178-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="e1178-198">Se quiser que as ordens de serviço sejam criadas automaticamente, você pode agendar trabalhos de plano de manutenção ou pode configurar a opção de criação automática de [planos de manutenção](../preventive-and-reactive-maintenance/maintenance-plans.md) ou [rounds de manutenção](../preventive-and-reactive-maintenance/maintenance-rounds.md) em um ativo.</span><span class="sxs-lookup"><span data-stu-id="e1178-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="e1178-199">As ordens de serviço criadas com base em solicitações de manutenção na página de listagem **Todos os agendamentos de manutenção** possuem os tipos de trabalho de manutenção selecionados nas solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="e1178-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>

