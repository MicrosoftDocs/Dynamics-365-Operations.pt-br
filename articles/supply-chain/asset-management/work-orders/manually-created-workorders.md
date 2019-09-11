---
title: Ordens de serviço criadas manualmente
description: Este tópico explica como criar ordens de serviço manualmente no Gerenciamento de Ativos.
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
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875503"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="63bdb-103">Ordens de serviço criadas manualmente</span><span class="sxs-lookup"><span data-stu-id="63bdb-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="63bdb-104">É possível criar ordens de serviço manualmente de duas formas:</span><span class="sxs-lookup"><span data-stu-id="63bdb-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="63bdb-105">em **Todas as ordens de serviço** ou em **Ordens de serviço ativas**</span><span class="sxs-lookup"><span data-stu-id="63bdb-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="63bdb-106">em **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção de local funcional**</span><span class="sxs-lookup"><span data-stu-id="63bdb-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="63bdb-107">Criar ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="63bdb-107">Create work order</span></span>

1. <span data-ttu-id="63bdb-108">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="63bdb-109">Clique no botão **Novo**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-109">Click the **New** button.</span></span>

3. <span data-ttu-id="63bdb-110">Na lista suspensa **Criar ordem de serviço**, selecione um tipo de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="63bdb-111">Se necessário, selecione uma descrição.</span><span class="sxs-lookup"><span data-stu-id="63bdb-111">If required, select a description.</span></span>

5. <span data-ttu-id="63bdb-112">Selecione o ativo para a ordem de serviço e também como um tipo de trabalho de manutenção.</span><span class="sxs-lookup"><span data-stu-id="63bdb-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="63bdb-113">Quando você seleciona um ativo, três guias podem estar disponíveis: A guia **Meus ativos** contém ativos relacionados aos locais funcionais para os quais você (o funcionário que está conectado no sistema) pode estar alocado (configurar em [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="63bdb-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="63bdb-114">Se nenhum local funcional for configurado em um funcionário na guia [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md), a guia **Meus ativos** não ficará visível.</span><span class="sxs-lookup"><span data-stu-id="63bdb-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="63bdb-115">A guia **Ativos ativos** contém uma lista de todos os ativos com o estado de ciclo de vida do ativo "Ativo".</span><span class="sxs-lookup"><span data-stu-id="63bdb-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="63bdb-116">A guia **Exibição de ativo** exibe um modo de exibição de árvore dos locais funcionais e ativos instalados nesses locais.</span><span class="sxs-lookup"><span data-stu-id="63bdb-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="63bdb-117">Se necessário, selecione **Grade do tipo de trabalho de manutenção** e **Ofício**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="63bdb-118">Se necessário, você pode alterar o nível de serviço da ordem de serviço no campo **Nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="63bdb-119">Selecione as datas de início e de término nos campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="63bdb-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="63bdb-120">Clique em **OK** para criar uma nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="63bdb-121">Edite a ordem de serviço em **Todas ordens de serviço**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="63bdb-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="63bdb-122">Em **Todas ordens de serviço**, você pode adicionar vários ativos para uma ordem de serviço na exibição Detalhes, adicionando linhas na Guia Rápida **Trabalhos de manutenção da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="63bdb-123">Em um ativo você só poderá selecionar os tipos de trabalho de manutenção definidos no tipo de ativo selecionado para o ativo.</span><span class="sxs-lookup"><span data-stu-id="63bdb-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="63bdb-124">Se tiver alterado um nível de serviço do ativo ou uma severidade do ativo após ter usado-o em uma ordem de serviço (consulte [Níveis de serviço do ativo](../setup-for-objects/object-priorities.md) e [Severidade do ativo](../setup-for-objects/object-criticalities.md)), o nível de serviço ou a severidade da ordem de serviço será atualizada adequadamente.</span><span class="sxs-lookup"><span data-stu-id="63bdb-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="63bdb-125">A severidade em uma ordem de serviço é recalculada sempre que uma linha da ordem de serviço for adicionada ou excluída da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="63bdb-126">Na exibição **Todas as ordens de serviço** Exibição de detalhes > **Cabeçalho** > Guia Rápida **Agendar**, você pode selecionar um grupo de funcionários de manutenção responsáveis ou um funcionário de manutenção responsável nos campos **Grupo responsável** ou **Responsável**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="63bdb-127">Essas configurações podem ser alteradas desde que a ordem de serviço esteja ativa, por exemplo, quando o estado do ciclo de vida da ordem de trabalho for alterado.</span><span class="sxs-lookup"><span data-stu-id="63bdb-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="63bdb-128">A seleção automática criada durante a criação da ordem de serviço é baseada na configuração de **Funcionários de manutenção responsáveis**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="63bdb-129">Se você adicionar ou remover trabalhos da ordem de serviço após ter criado uma ordem de serviço e os campos **Grupo responsável** e **Responsável** estiverem em branco quando você atualizar a ordem de serviço, o Gerenciamento de Ativos pesquisará uma possível correspondência no formulário de configuração de um grupo de funcionários de manutenção ou de um funcionário de manutenção responsável.</span><span class="sxs-lookup"><span data-stu-id="63bdb-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="63bdb-130">Se o campo **Grupo responsável** ou o campo **Responsável** já estiver preenchido quando você atualizar a ordem de serviço, nenhuma alteração será feita.</span><span class="sxs-lookup"><span data-stu-id="63bdb-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="63bdb-131">No **Status de manutenção**, você pode fazer um cálculo para obter uma visão geral da carga de trabalho referente às ordens de serviço recebidas e concluídas.</span><span class="sxs-lookup"><span data-stu-id="63bdb-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="63bdb-132">Na Guia Rápida **Detalhes da linha**, use os campos **Latitude** e **Longitude** para adicionar coordenadas geográficas para o ativo selecionado no trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="63bdb-133">Criar ordem de serviço relacionada</span><span class="sxs-lookup"><span data-stu-id="63bdb-133">Create related work order</span></span>

<span data-ttu-id="63bdb-134">Você pode criar uma ordem de serviço relacionada para uma ordem de serviço existente se, por exemplo, quiser trabalhar com ordens de serviço principais e secundárias.</span><span class="sxs-lookup"><span data-stu-id="63bdb-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="63bdb-135">Uma nova ordem de serviço é baseada em um trabalho da ordem de serviço de uma ordem de serviço existente.</span><span class="sxs-lookup"><span data-stu-id="63bdb-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="63bdb-136">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="63bdb-137">Selecione a ordem de serviço para a qual você deseja criar uma ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="63bdb-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="63bdb-138">Clique em **Ordem de serviço relacionada**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="63bdb-139">Na caixa de diálogo suspensa **Criar ordem de serviço relacionada**, selecione o trabalho da ordem de serviço para o qual você deseja criar uma ordem de serviço relacionada no campo **Trabalho da ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="63bdb-140">Selecione um tipo de trabalho de manutenção no campo **Tipo de trabalho de manutenção** e, se necessário, uma grade e ofício do tipo de trabalho de manutenção relacionado nos campos **Grade do tipo de trabalho de manutenção** e **Ofício**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="63bdb-141">Se esta for a primeira ordem de serviço relacionada que você cria, clique no botão de opção **Nova ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="63bdb-142">Selecione um **Tipo de ordem de serviço** e uma **Descrição** nos campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="63bdb-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="63bdb-143">Se necessário, altere o nível de serviço da ordem de serviço no campo **Nível de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="63bdb-144">Insira as datas de início e de término esperadas nos campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="63bdb-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="63bdb-145">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-145">Click **OK**.</span></span> <span data-ttu-id="63bdb-146">A nova ordem de serviço relacionada é mostrada na lista **Todas as ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="63bdb-147">Se criar uma ordem de serviço relacionada em uma ordem que já tem ordens de serviços, você poderá adicionar o trabalho da ordem de serviço em um já relacionada.</span><span class="sxs-lookup"><span data-stu-id="63bdb-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="63bdb-148">Isso é feito clicando no botão de opção **Adicionar à ordem de serviço relacionada** na etapa 6.</span><span class="sxs-lookup"><span data-stu-id="63bdb-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="63bdb-149">Em seguida, você seleciona a ordem de serviço relacionada para a qual você deseja adicionar um novo trabalho da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="63bdb-150">Edite os campos **Nível de serviço**, **Início esperado** e **Término esperado**, conforme necessário e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="63bdb-151">O trabalho da ordem de serviço é adicionado à ordem de serviço relacionada.</span><span class="sxs-lookup"><span data-stu-id="63bdb-151">The work order job is added to the existing related work order.</span></span>


![Figura 1](media/03-work-orders.png)

<span data-ttu-id="63bdb-153">**Observação:** Se você configurou uma máscara da ordem de serviço relacionada no link **Parâmetros de gerenciamento de ativos** > **Ordens de serviço** > campo **Máscara da ordem de serviço relacionada**, as IDs da ordem de serviço serão criadas de acordo com a configuração da máscara.</span><span class="sxs-lookup"><span data-stu-id="63bdb-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="63bdb-154">Se nenhuma máscara da ordem de serviço relacionada for configurada, a próxima ID da ordem de serviço disponível será usada para ordens de serviço relacionadas.</span><span class="sxs-lookup"><span data-stu-id="63bdb-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="63bdb-155">Copiar ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="63bdb-155">Copy work order</span></span>

<span data-ttu-id="63bdb-156">É possível criar uma nova ordem de serviço rapidamente usando uma existente.</span><span class="sxs-lookup"><span data-stu-id="63bdb-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="63bdb-157">Esta forma de trabalhar com ordens de serviço é diferente de criar ordens de serviço com base em planos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="63bdb-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="63bdb-158">É útil se, por exemplo, você tiver uma ordem de serviço que contém vários trabalhos da ordem de serviço com vários trabalhos em ativos diferentes que devem ser concluídos em intervalos regulares.</span><span class="sxs-lookup"><span data-stu-id="63bdb-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="63bdb-159">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="63bdb-160">Selecione a ordem de serviço da qual você deseja copiar o conteúdo.</span><span class="sxs-lookup"><span data-stu-id="63bdb-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="63bdb-161">Clique em **Copiar ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-161">Click **Copy work order**.</span></span> <span data-ttu-id="63bdb-162">A configuração da ordem de serviço selecionada é mostrada.</span><span class="sxs-lookup"><span data-stu-id="63bdb-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="63bdb-163">Se necessário, você pode editar alguns campos.</span><span class="sxs-lookup"><span data-stu-id="63bdb-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="63bdb-164">Clique em **OK** para criar a nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="63bdb-165">Edite a ordem de serviço em **Todas ordens de serviço**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="63bdb-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="63bdb-166">Quando a nova ordem de serviço for criada, algumas informações serão copiadas diretamente da existente.</span><span class="sxs-lookup"><span data-stu-id="63bdb-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="63bdb-167">Informações relacionadas às previsões, às ferramentas, às listas de verificação da manutenção, ao local funcional, aos endereços e ao agendamento não serão copiadas, mas inicializadas da configuração atual no Gerenciamento de Ativos.</span><span class="sxs-lookup"><span data-stu-id="63bdb-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="63bdb-168">Isso significa que, se forem feitas alterações nesses dados desde o momento da criação da primeira ordem de serviço até o momento em que você fez uma cópia da ordem de serviço, essas alterações serão incluídas na nova ordem de serviço que você criou.</span><span class="sxs-lookup"><span data-stu-id="63bdb-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="63bdb-169">Os exemplos são alterações nas previsões ou em listas de verificação de manutenção atualizadas.</span><span class="sxs-lookup"><span data-stu-id="63bdb-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="63bdb-171">Criar uma ordem de serviço com base em uma solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="63bdb-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="63bdb-172">Clique em **Gerenciamento de ativos** > **Comum** > **Solicitações de manutenção** > **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="63bdb-173">Selecione a solicitação de manutenção para a qual você deseja criar uma ordem de serviço e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="63bdb-174">Em **Todas as solicitações**, clique em **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="63bdb-175">Preencha a lista suspensa **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="63bdb-176">Se um tipo de trabalho de manutenção tiver sido selecionado na solicitação de manutenção, você poderá selecionar outro tipo de trabalho de manutenção, se necessário, ao criar a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63bdb-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="63bdb-177">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-177">Click **OK**.</span></span> <span data-ttu-id="63bdb-178">Você verá uma mensagem informando que a ordem de serviço foi criada.</span><span class="sxs-lookup"><span data-stu-id="63bdb-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="63bdb-179">Se quiser ver quais ordens de serviços estão conectadas a uma solicitação de manutenção, selecione a solicitação de manutenção nas listas **Todas as solicitações de manutenção** ou **Solicitações de manutenção ativas** e clique no botão **Ordens de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63bdb-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="63bdb-181">As ordens de serviço também podem ser criadas automaticamente através do agendamento de trabalhos do plano de manutenção, ou pela configuração de planos de manutenção ou rounds de manutenção de "Criação automática" em um ativo.</span><span class="sxs-lookup"><span data-stu-id="63bdb-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="63bdb-182">As ordens de serviço criadas das solicitações de manutenção no **Agendamento de manutenção** são criadas com os tipos de trabalho de manutenção selecionados nas solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="63bdb-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

