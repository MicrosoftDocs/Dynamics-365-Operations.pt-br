---
title: Classificação de saída
description: Este tópico contém informações sobre classificação de saída. Esta funcionalidade facilita a manipulação de pequenos contêineres e ajuda os trabalhadores do depósito a planejar e organizar melhor a capacidade dos paletes no caminhão.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: e72249e26fb8f291f804cf5f2e4ce98bf88cd5bf
ms.sourcegitcommit: 70d0b4e6bdacc15ec75935550ae55fc02cb79624
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "3596200"
---
# <a name="outbound-sorting"></a><span data-ttu-id="5e265-104">Classificação de saída</span><span class="sxs-lookup"><span data-stu-id="5e265-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e265-105">Esta funcionalidade facilita a manipulação de pequenos contêineres e ajuda os trabalhadores do depósito a planejar e organizar melhor a capacidade dos paletes no caminhão.</span><span class="sxs-lookup"><span data-stu-id="5e265-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="5e265-106">Quando você usa a classificação de saída, pode classificar os contêineres embalados no palete correto depois que eles tiverem estado em uma estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="5e265-107">Você também pode criar uma hierarquia de embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="5e265-108">Esta funcionalidade permite criar paletes de contêineres que são embalados por meio da funcionalidade de embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="5e265-109">O contêiner não é enviado para o local da remessa final porque está no fluxo de embalagem original.</span><span class="sxs-lookup"><span data-stu-id="5e265-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="5e265-110">Em vez disso, os funcionários podem fechar o contêiner e movê-lo para um local do tipo classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="5e265-111">Eles podem então classificar os contêineres em posições, e cada uma tem uma placa de licença (LP).</span><span class="sxs-lookup"><span data-stu-id="5e265-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="5e265-112">Depois que os contêineres forem classificados, poderá ser criado um trabalho para enviar a LP inteira à doca de remessa final ou para locais de preparação com base nas diretivas de localização ou nas suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="5e265-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="5e265-113">Além disso, a ação de fechamento da posição de classificação pode mover o estoque imediatamente para o local de remessa final e separá-lo para a ordem.</span><span class="sxs-lookup"><span data-stu-id="5e265-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="5e265-114">Ativar o recurso Classificação de saída</span><span class="sxs-lookup"><span data-stu-id="5e265-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="5e265-115">Para que você possa usar o recurso, ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="5e265-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="5e265-116">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="5e265-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="5e265-117">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="5e265-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5e265-118">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="5e265-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5e265-119">**Nome do recurso:** *classificação de saída*</span><span class="sxs-lookup"><span data-stu-id="5e265-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="5e265-120">Instalação</span><span class="sxs-lookup"><span data-stu-id="5e265-120">Setup</span></span>

<span data-ttu-id="5e265-121">Para este cenário, você deve usar dados de demonstração **USMF** padrão e o depósito *62*.</span><span class="sxs-lookup"><span data-stu-id="5e265-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="5e265-122">Você também deve concluir a configuração descrita nas subseções a seguir.</span><span class="sxs-lookup"><span data-stu-id="5e265-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="5e265-123">Configurar um modelo de onda</span><span class="sxs-lookup"><span data-stu-id="5e265-123">Set up a wave template</span></span>

<span data-ttu-id="5e265-124">Esta configuração processa a onda automaticamente e cria um trabalho quando uma linha é liberada para o depósito.</span><span class="sxs-lookup"><span data-stu-id="5e265-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="5e265-125">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="5e265-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="5e265-126">Na lista de modelos, selecione **Depósito 62**.</span><span class="sxs-lookup"><span data-stu-id="5e265-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="5e265-127">Na FastTab **Geral**, verifique se a opção **Processar onda na liberação para o depósito** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="5e265-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="5e265-128">Configurar um trabalhador</span><span class="sxs-lookup"><span data-stu-id="5e265-128">Set up a worker</span></span>

<span data-ttu-id="5e265-129">A estação de embalagem é considerada um local.</span><span class="sxs-lookup"><span data-stu-id="5e265-129">The packing station is considered a location.</span></span> <span data-ttu-id="5e265-130">Os trabalhadores do depósito que se conectam na estação de embalagem veem e trabalham somente em remessas e contêineres planejados nessa localização de embalagem específica.</span><span class="sxs-lookup"><span data-stu-id="5e265-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="5e265-131">Um usuário que entra no Microsoft Dynamics 365 deve estar configurado como trabalhador no Gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="5e265-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="5e265-132">Se o nome do usuário não está na lista de usuários de trabalho, use o procedimento a seguir para adicioná-lo.</span><span class="sxs-lookup"><span data-stu-id="5e265-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="5e265-133">Essas etapas supõem que o usuário já existe no sistema e que foi associado a um funcionário ou trabalhador no módulo **Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="5e265-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="5e265-134">Vá para **Gerenciamento de depósito \> Configuração \> Trabalhador**.</span><span class="sxs-lookup"><span data-stu-id="5e265-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="5e265-135">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-135">Select **New**.</span></span>
1. <span data-ttu-id="5e265-136">No campo **Trabalhador**, selecione o usuário de destino na lista de funcionários.</span><span class="sxs-lookup"><span data-stu-id="5e265-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="5e265-137">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-137">Select **Select**.</span></span>
1. <span data-ttu-id="5e265-138">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="5e265-139">Na FastTab **Usuários**, selecione **Novo** para criar uma conta de dispositivo móvel e defina os seguintes valores para ela:</span><span class="sxs-lookup"><span data-stu-id="5e265-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="5e265-140">**ID do Usuário:** insira uma ID exclusiva.</span><span class="sxs-lookup"><span data-stu-id="5e265-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="5e265-141">**Nome de usuário:** insira um nome para a ID.</span><span class="sxs-lookup"><span data-stu-id="5e265-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="5e265-142">**Depósito padrão:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-143">**Nome do menu:** *Principal*</span><span class="sxs-lookup"><span data-stu-id="5e265-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="5e265-144">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="5e265-145">A caixa de diálogo **Definir senha** é exibida e nela você pode criar uma senha simples que o usuário pode usar para entrar no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="5e265-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="5e265-146">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-146">Set the following values:</span></span>

    - <span data-ttu-id="5e265-147">**Senha:** insira uma senha simples.</span><span class="sxs-lookup"><span data-stu-id="5e265-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="5e265-148">**Confirmar senha:** insira a mesma senha novamente.</span><span class="sxs-lookup"><span data-stu-id="5e265-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="5e265-149">Selecione **Definir senha**.</span><span class="sxs-lookup"><span data-stu-id="5e265-149">Select **Set password**.</span></span>

    <span data-ttu-id="5e265-150">Uma notificação na Central de Ações informa que a senha foi definida para o usuário que você criou.</span><span class="sxs-lookup"><span data-stu-id="5e265-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="5e265-151">Criar um tipo de localização</span><span class="sxs-lookup"><span data-stu-id="5e265-151">Create a location type</span></span>

1. <span data-ttu-id="5e265-152">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Tipos de localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="5e265-153">No Painel de Ação, selecione **Novo** para criar um tipo de localização e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="5e265-154">**Tipo de localização:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="5e265-155">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="5e265-156">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="5e265-157">Configurar parâmetros de Gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="5e265-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="5e265-158">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="5e265-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="5e265-159">Na guia **Geral**, na FastTab **Tipos de localização**, defina o campo **Tipo de localização de classificação** como *CLASSIFICAR*.</span><span class="sxs-lookup"><span data-stu-id="5e265-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="5e265-160">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="5e265-161">Configurar um perfil de localização</span><span class="sxs-lookup"><span data-stu-id="5e265-161">Set up a location profile</span></span>

1. <span data-ttu-id="5e265-162">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="5e265-163">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-164">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e265-165">**ID do perfil de localização:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="5e265-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="5e265-166">**Nome:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="5e265-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="5e265-167">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-168">**Formato de localização:** *ASRB* (Corredor-Rack-Prateleira-Compartimento)</span><span class="sxs-lookup"><span data-stu-id="5e265-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="5e265-169">**Tipo de localização:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="5e265-170">**Usar rastreamento da placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="5e265-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="5e265-171">**Permitir itens mistos:** *Sim* (Quando você define esta opção como *Sim*, a opção **Permitir lotes de estoque mistos** é definida automaticamente como *Sim* e não pode ser alterada de modo independente.)</span><span class="sxs-lookup"><span data-stu-id="5e265-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="5e265-172">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="5e265-173">Configurar uma localização</span><span class="sxs-lookup"><span data-stu-id="5e265-173">Set up a location</span></span>

1. <span data-ttu-id="5e265-174">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.</span><span class="sxs-lookup"><span data-stu-id="5e265-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="5e265-175">No cabeçalho, desmarque a caixa de seleção **Gerar dígitos de verificação para localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="5e265-176">No Painel de Ação, selecione **Novo** para criar uma localização e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="5e265-177">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-178">**Localização:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="5e265-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="5e265-179">**ID do perfil de localização:** *CLASSIFICAÇÃO*</span><span class="sxs-lookup"><span data-stu-id="5e265-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="5e265-180">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="5e265-181">Configurar um modelo de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="5e265-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="5e265-182">O modelo de classificação de saída determina se o trabalho é criado fora da localização de classificação e se a classificação é feita manual ou automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5e265-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="5e265-183">Para este cenário, você criará um modelo de classificação de saída para criar paletes após a estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="5e265-184">Vá para **Gerenciamento de Depósito \> Configuração \> Embalagem \> Modelo de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="5e265-185">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-186">No cabeçalho do novo modelo, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="5e265-187">**ID do modelo de classificação de saída:** *Trabalho Automático*</span><span class="sxs-lookup"><span data-stu-id="5e265-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="5e265-188">**Descrição:** *Criação de Trabalho Automático*</span><span class="sxs-lookup"><span data-stu-id="5e265-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="5e265-189">**Tipo de modelo de classificação de saída:** *Contêiner*</span><span class="sxs-lookup"><span data-stu-id="5e265-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="5e265-190">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-191">**Localização:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="5e265-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="5e265-192">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-193">**Verificação de classificação:** *Verificação da posição*</span><span class="sxs-lookup"><span data-stu-id="5e265-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="5e265-194">**Criar trabalho no fechamento da posição:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="5e265-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="5e265-195">Se esta opção for definida como *Sim*, quando a posição for fechada, será criado um trabalho para mover o estoque para a localização da remessa final.</span><span class="sxs-lookup"><span data-stu-id="5e265-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="5e265-196">Se ela for definida como *Não*, o estoque será separado imediatamente para a ordem quando a posição for fechada.</span><span class="sxs-lookup"><span data-stu-id="5e265-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="5e265-197">**Atribuição da posição:** *Automática*</span><span class="sxs-lookup"><span data-stu-id="5e265-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="5e265-198">Se este campo for definido como *Manual*, o usuário sempre deverá indicar a posição para classificar o estoque.</span><span class="sxs-lookup"><span data-stu-id="5e265-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="5e265-199">Se ele for definido como *Automática*, o sistema guiará o estoque automaticamente para uma posição sempre que possível, com base nas divisões do modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="5e265-200">Selecione **Salvar** para tornar o botão **Editar consulta** disponível no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="5e265-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="5e265-201">No Painel de Ações, selecione **Editar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="5e265-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="5e265-202">No editor de consultas, na guia **Classificação**, adicione uma linha com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="5e265-203">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="5e265-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="5e265-204">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="5e265-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="5e265-205">**Campo:** *Serviço da operadora*</span><span class="sxs-lookup"><span data-stu-id="5e265-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="5e265-206">Quando selecionar esse valor, você poderá receber a seguinte mensagem: "O campo Serviço da transportadora não é um campo de índice.</span><span class="sxs-lookup"><span data-stu-id="5e265-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="5e265-207">Deseja adicionar classificação a ele?"</span><span class="sxs-lookup"><span data-stu-id="5e265-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="5e265-208">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5e265-208">Select **Yes**.</span></span>

    - <span data-ttu-id="5e265-209">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="5e265-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="5e265-210">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-210">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-211">Você poderá receber a seguinte mensagem: "O agrupamento será redefinido, continuar?"</span><span class="sxs-lookup"><span data-stu-id="5e265-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="5e265-212">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="5e265-212">Select **Yes**.</span></span>

    <span data-ttu-id="5e265-213">O botão **Divisões do modelo de classificação de saída** no Painel de Ação ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="5e265-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="5e265-214">No Painel de Ação, selecione **Divisões do modelo de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="5e265-215">Na caixa de diálogo **Critérios de classificação de saída**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5e265-216">**Nome da tabela de referência:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="5e265-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="5e265-217">**Nome do campo de referência:** *Serviço da transportadora*</span><span class="sxs-lookup"><span data-stu-id="5e265-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="5e265-218">**Agrupar por campo:** marque essa caixa de seleção para agrupar as remessas por serviço da transportadora.</span><span class="sxs-lookup"><span data-stu-id="5e265-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="5e265-219">Selecione **OK** para salvar suas configurações e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e265-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="5e265-220">Configurar políticas de embalagem de contêiner</span><span class="sxs-lookup"><span data-stu-id="5e265-220">Set up container packing policies</span></span>

1. <span data-ttu-id="5e265-221">Vá para **Gerenciamento de depósito \> Configuração \> Contêineres \> Políticas de embalagem de contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="5e265-222">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-223">No cabeçalho da nova política, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="5e265-224">**Política de embalagem de contêiner:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="5e265-225">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="5e265-226">Na FastTab **Visão geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-227">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-228">**Local padrão para classificação:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="5e265-229">**Unidade de peso:** *kg*</span><span class="sxs-lookup"><span data-stu-id="5e265-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="5e265-230">**Política de fechamento de contêiner:** *Liberação automática*</span><span class="sxs-lookup"><span data-stu-id="5e265-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="5e265-231">**Política de liberação de contêiner:** *Atribuir contêiner a posição de classificação de saída*</span><span class="sxs-lookup"><span data-stu-id="5e265-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="5e265-232">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="5e265-233">Configurar perfis de embalagem</span><span class="sxs-lookup"><span data-stu-id="5e265-233">Set up packing profiles</span></span>

<span data-ttu-id="5e265-234">Crie um novo perfil de embalagem que será usado junto com a funcionalidade de classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="5e265-235">Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.</span><span class="sxs-lookup"><span data-stu-id="5e265-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="5e265-236">No Painel de Ação, selecione **Novo** para criar uma linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="5e265-237">**ID do perfil de embalagem:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="5e265-238">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="5e265-239">**Política de embalagem de contêiner:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="5e265-240">**Modo de ID do Contêiner:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="5e265-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="5e265-241">**Tipo de contêiner:** *Caixa-Grande*</span><span class="sxs-lookup"><span data-stu-id="5e265-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="5e265-242">**Criar automaticamente contêiner no fechamento do contêiner:** desmarcada (= *Não*)</span><span class="sxs-lookup"><span data-stu-id="5e265-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="5e265-243">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="5e265-244">Configurar classes de trabalho</span><span class="sxs-lookup"><span data-stu-id="5e265-244">Set up work classes</span></span>

<span data-ttu-id="5e265-245">Configure uma classe de trabalho que será usada junto com a classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="5e265-246">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5e265-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="5e265-247">No Painel de Ação, selecione **Novo** para criar uma classe de trabalho e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="5e265-248">**ID da classe de trabalho:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="5e265-249">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="5e265-250">**Tipo de ordem de serviço:** *Separação do estoque classificado*</span><span class="sxs-lookup"><span data-stu-id="5e265-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="5e265-251">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="5e265-252">Configurar itens de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="5e265-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="5e265-253">Configurar um item de menu de novo palete</span><span class="sxs-lookup"><span data-stu-id="5e265-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="5e265-254">Crie um item de menu de dispositivo móvel para criar paletes durante a classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="5e265-255">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="5e265-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="5e265-256">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-257">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e265-258">**Nome do item de menu:** *Criação do palete*</span><span class="sxs-lookup"><span data-stu-id="5e265-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="5e265-259">**Título:** *Criação do palete*</span><span class="sxs-lookup"><span data-stu-id="5e265-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="5e265-260">**Modo:** *Indireto*</span><span class="sxs-lookup"><span data-stu-id="5e265-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="5e265-261">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="5e265-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="5e265-262">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-263">**Código de atividade:** *Classificação de saída*</span><span class="sxs-lookup"><span data-stu-id="5e265-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="5e265-264">Quando esse campo é definido como *Classificação de saída*, é exibido o campo **ID do modelo de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="5e265-265">**Usar guia de processo:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="5e265-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="5e265-266">Quando o campo **Código de atividade** está definido como *Classificação de saída*, esta opção é definida automaticamente como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="5e265-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="5e265-267">**ID do modelo de classificação de saída:** *Trabalho Automático*</span><span class="sxs-lookup"><span data-stu-id="5e265-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="5e265-268">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="5e265-269">Configurar um item de menu de nova carga</span><span class="sxs-lookup"><span data-stu-id="5e265-269">Set up a new loading menu item</span></span>

<span data-ttu-id="5e265-270">Em seguida, crie um item de menu que permita aos usuários mover os itens de estoque classificados para a localização de remessa.</span><span class="sxs-lookup"><span data-stu-id="5e265-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="5e265-271">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="5e265-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="5e265-272">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-273">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e265-274">**Nome do item de menu:** *Carregar da Classificação*</span><span class="sxs-lookup"><span data-stu-id="5e265-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="5e265-275">**Título:** *Carregar da Classificação*</span><span class="sxs-lookup"><span data-stu-id="5e265-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="5e265-276">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="5e265-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="5e265-277">**Usar trabalho existente:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="5e265-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="5e265-278">Na FastTab **Geral**, defina o campo **Direcionado por** como *Dirigido pelo usuário*.</span><span class="sxs-lookup"><span data-stu-id="5e265-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="5e265-279">Na FastTab **Classes de trabalho**, selecione **Novo** e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="5e265-280">**ID da classe de trabalho:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="5e265-281">**Tipo de ordem de serviço:** *Separação do estoque classificado*</span><span class="sxs-lookup"><span data-stu-id="5e265-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="5e265-282">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="5e265-283">Configura o menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="5e265-283">Set up the mobile device menu</span></span>

<span data-ttu-id="5e265-284">Agora, você deve adicionar os novos itens de menu ao menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5e265-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="5e265-285">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="5e265-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="5e265-286">Selecione o menu **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="5e265-287">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="5e265-288">Na coluna **Menus e itens de menu disponíveis**, localize e selecione **Criação do palete**.</span><span class="sxs-lookup"><span data-stu-id="5e265-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="5e265-289">Selecione o botão de seta para a direita para mover **Criação do palete** para a coluna **Estrutura de menu**.</span><span class="sxs-lookup"><span data-stu-id="5e265-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="5e265-290">Use os botões de seta para cima e seta para baixo para colocar o item de menu **Criação do palete** na posição desejada no menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="5e265-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="5e265-291">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-291">Select **Save**.</span></span>
1. <span data-ttu-id="5e265-292">Repita este procedimento para adicionar o item de menu **Carregar da Classificação** ao menu **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="5e265-293">Configurar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="5e265-293">Set up location directives</span></span>

<span data-ttu-id="5e265-294">As *diretivas de localização* são regras que ajudam a identificar localizações de separação e armazenamento para o movimento do estoque.</span><span class="sxs-lookup"><span data-stu-id="5e265-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="5e265-295">Agora, você deve criar uma regra para gerenciar o trabalho de classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="5e265-296">Configurar uma diretiva de SKU única</span><span class="sxs-lookup"><span data-stu-id="5e265-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="5e265-297">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="5e265-298">No painel esquerdo, altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.</span><span class="sxs-lookup"><span data-stu-id="5e265-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="5e265-299">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-300">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e265-301">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-302">**Nome:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="5e265-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="5e265-303">Na FastTab **Diretivas de localização**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-304">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="5e265-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="5e265-305">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="5e265-305">**Site:** *6*</span></span>
    - <span data-ttu-id="5e265-306">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-307">**Várias SKUs:** *Não*</span><span class="sxs-lookup"><span data-stu-id="5e265-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="5e265-308">Selecione **Salvar** para disponibilizar a barra de tarefas na FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="5e265-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="5e265-309">Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir na nova linha.</span><span class="sxs-lookup"><span data-stu-id="5e265-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="5e265-310">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="5e265-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="5e265-311">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-312">**De:** *0*</span><span class="sxs-lookup"><span data-stu-id="5e265-312">**From:** *0*</span></span>
    - <span data-ttu-id="5e265-313">**Até:** *1.000.000*</span><span class="sxs-lookup"><span data-stu-id="5e265-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="5e265-314">Selecione **Salvar** para disponibilizar a barra de ferramentas na FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="5e265-315">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir na nova linha.</span><span class="sxs-lookup"><span data-stu-id="5e265-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="5e265-316">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="5e265-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="5e265-317">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-318">**Nome:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="5e265-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="5e265-319">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-319">Select **Save**.</span></span>
1. <span data-ttu-id="5e265-320">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="5e265-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="5e265-321">Na guia **Intervalo** do editor de consultas, localize a linha na qual o campo **Campo** está definido como *Local*.</span><span class="sxs-lookup"><span data-stu-id="5e265-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="5e265-322">Defina o campo **Critérios** dessa linha como *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="5e265-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="5e265-323">Selecione **OK** para salvar as configurações e fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="5e265-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="5e265-324">Configurar uma diretiva de várias SKUs</span><span class="sxs-lookup"><span data-stu-id="5e265-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="5e265-325">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="5e265-326">No painel esquerdo, altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.</span><span class="sxs-lookup"><span data-stu-id="5e265-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="5e265-327">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-328">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="5e265-329">**Sequência:** *2*</span><span class="sxs-lookup"><span data-stu-id="5e265-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="5e265-330">**Nome:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="5e265-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="5e265-331">Na FastTab **Diretivas de localização**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-332">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="5e265-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="5e265-333">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="5e265-333">**Site:** *6*</span></span>
    - <span data-ttu-id="5e265-334">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-335">**Várias SKUs:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="5e265-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="5e265-336">Selecione **Salvar** para disponibilizar a barra de tarefas na FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="5e265-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="5e265-337">Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir na nova linha.</span><span class="sxs-lookup"><span data-stu-id="5e265-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="5e265-338">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="5e265-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="5e265-339">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-340">**De:** *0*</span><span class="sxs-lookup"><span data-stu-id="5e265-340">**From:** *0*</span></span>
    - <span data-ttu-id="5e265-341">**Até:** *1.000.000*</span><span class="sxs-lookup"><span data-stu-id="5e265-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="5e265-342">Selecione **Salvar** para disponibilizar a barra de ferramentas na FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="5e265-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="5e265-343">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir na nova linha.</span><span class="sxs-lookup"><span data-stu-id="5e265-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="5e265-344">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="5e265-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="5e265-345">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-346">**Nome:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="5e265-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="5e265-347">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-347">Select **Save**.</span></span>
1. <span data-ttu-id="5e265-348">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="5e265-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="5e265-349">Na guia **Intervalo** do editor de consultas, localize a linha na qual o campo **Campo** está definido como *Local*.</span><span class="sxs-lookup"><span data-stu-id="5e265-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="5e265-350">Defina o campo **Critérios** dessa linha como *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="5e265-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="5e265-351">Selecione **OK** para salvar as configurações e fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="5e265-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="5e265-352">Configurar modelos de trabalho</span><span class="sxs-lookup"><span data-stu-id="5e265-352">Set up work templates</span></span>

1. <span data-ttu-id="5e265-353">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5e265-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="5e265-354">Altere o valor do campo **Tipo de ordem de serviço** para *Separação do estoque classificado*.</span><span class="sxs-lookup"><span data-stu-id="5e265-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="5e265-355">No Painel de Ação, selecione **Novo** para criar um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5e265-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="5e265-356">Na guia **Visão geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="5e265-357">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="5e265-358">**Modelo de trabalho:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="5e265-359">**Descrição do modelo de trabalho:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="5e265-360">Selecione **Salvar** para disponibilizar a FastTab **Detalhes do Modelo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5e265-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="5e265-361">Na FastTab **Detalhes do modelo de trabalho**, selecione **Novo** para adicionar uma linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="5e265-362">**Tipo de trabalho:** *Separar*</span><span class="sxs-lookup"><span data-stu-id="5e265-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="5e265-363">**ID da classe de trabalho:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="5e265-364">Selecione **Novo** novamente para adicionar uma segunda linha e defina os seguintes valores para ela:</span><span class="sxs-lookup"><span data-stu-id="5e265-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="5e265-365">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="5e265-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="5e265-366">**ID da classe de trabalho:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="5e265-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="5e265-367">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="5e265-368">Cenário</span><span class="sxs-lookup"><span data-stu-id="5e265-368">Scenario</span></span>

<span data-ttu-id="5e265-369">Este cenário simula uma situação em que os contêineres embalados devem ser classificados automaticamente em diferentes posições (paletes) após a estação de embalagem, dependendo do serviço de transportadora.</span><span class="sxs-lookup"><span data-stu-id="5e265-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="5e265-370">Depois que todos os itens da carga forem embalados e classificados por endereço, os paletes serão movidos para a porta do compartimento.</span><span class="sxs-lookup"><span data-stu-id="5e265-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="5e265-371">Criar ordens de venda e trabalho de separação</span><span class="sxs-lookup"><span data-stu-id="5e265-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="5e265-372">Criar ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="5e265-372">Create sales order 1</span></span>

1. <span data-ttu-id="5e265-373">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="5e265-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5e265-374">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-375">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5e265-376">**Conta de cliente:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="5e265-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="5e265-377">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="5e265-378">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e265-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="5e265-379">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="5e265-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="5e265-380">Alterne para a exibição do **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="5e265-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="5e265-381">Na guia **Remessa**, na seção **Transporte**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="5e265-382">**Transportadora:** *Carga aérea*</span><span class="sxs-lookup"><span data-stu-id="5e265-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="5e265-383">**Serviço da transportadora:** *Aéreo*</span><span class="sxs-lookup"><span data-stu-id="5e265-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="5e265-384">Alterne para a exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="5e265-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="5e265-385">Se uma nova linha vazia não for adicionada automaticamente à grade na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="5e265-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="5e265-386">Na nova linha de ordem, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="5e265-387">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e265-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="5e265-388">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="5e265-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="5e265-389">Com a nova linha de ordem ainda selecionada na FastTab **Linhas de ordem de venda**, no menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5e265-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="5e265-390">Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="5e265-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="5e265-391">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="5e265-392">No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="5e265-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="5e265-393">Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="5e265-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="5e265-394">Anote os números da ID da onda e da ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="5e265-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="5e265-395">Ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="5e265-395">Sales order 2</span></span>

1. <span data-ttu-id="5e265-396">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="5e265-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5e265-397">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="5e265-398">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5e265-399">**Conta de cliente:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="5e265-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="5e265-400">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="5e265-401">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e265-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="5e265-402">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="5e265-402">The new sales order is opened.</span></span> <span data-ttu-id="5e265-403">Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="5e265-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="5e265-404">Defina os seguintes valores na linha de ordem:</span><span class="sxs-lookup"><span data-stu-id="5e265-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="5e265-405">**Item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e265-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="5e265-406">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="5e265-407">Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Modo de entrega** como *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="5e265-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="5e265-408">Na FastTab **Linhas de ordem de venda**, selecione **Adicionar linha** e defina os seguintes valores na segunda linha da ordem:</span><span class="sxs-lookup"><span data-stu-id="5e265-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="5e265-409">**Item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="5e265-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="5e265-410">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="5e265-411">Na FastTab **Detalhes da linha**, na guia **Entrega**, mude o valor do campo **Modo de entrega** para *Air C - Via Aérea*.</span><span class="sxs-lookup"><span data-stu-id="5e265-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="5e265-412">Na FastTab **Linhas de ordem de venda**, selecione a primeira linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="5e265-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="5e265-413">Depois, no menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5e265-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="5e265-414">Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="5e265-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="5e265-415">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="5e265-416">Na FastTab **Linhas de ordem de venda**, selecione a segunda linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="5e265-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="5e265-417">Depois, no menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5e265-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="5e265-418">Na página **Reserva**, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="5e265-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="5e265-419">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="5e265-420">No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="5e265-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="5e265-421">Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="5e265-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="5e265-422">Observe que são criados dois números de ID de onda e dois números de ID de remessa, um para cada modo de entrega das linhas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="5e265-423">Obter as IDs de trabalho nos detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="5e265-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="5e265-424">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="5e265-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="5e265-425">A página mostra as IDs de trabalho que foram criadas com base nas ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="5e265-426">Use as IDs de onda e as IDs de remessa das ordens de venda que você criou para encontrar a ID de trabalho de cada onda e remessa.</span><span class="sxs-lookup"><span data-stu-id="5e265-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="5e265-427">Anote essas IDs de trabalho, pois elas serão necessárias nas próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="5e265-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="5e265-428">Observe que duas IDs de trabalho foram criadas para a segunda ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="5e265-429">Se forem separados itens diferentes de locais diferentes, serão geradas IDs de trabalho separadas.</span><span class="sxs-lookup"><span data-stu-id="5e265-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="5e265-430">Separar itens para as ordens de venda</span><span class="sxs-lookup"><span data-stu-id="5e265-430">Pick items for the sales orders</span></span>

<span data-ttu-id="5e265-431">Conclua o trabalho criado usando o dispositivo móvel para mover os itens à estação de embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="5e265-432">No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).</span><span class="sxs-lookup"><span data-stu-id="5e265-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="5e265-433">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="5e265-434">No menu **Saída**, selecione **Separação de Venda**.</span><span class="sxs-lookup"><span data-stu-id="5e265-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="5e265-435">No campo **ID**, insira a ID de trabalho criada para a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="5e265-436">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-436">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-437">Na página **Ordens de venda - Separar**, insira uma LP de destino criada para a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="5e265-438">Observe que são exibidos o local de separação (*bulk-001*), o item (*A0001*) e a quantidade (*2 pacotes*).</span><span class="sxs-lookup"><span data-stu-id="5e265-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="5e265-439">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-439">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-440">Examine as informações na página **Ordens de venda - Colocar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="5e265-441">O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.</span><span class="sxs-lookup"><span data-stu-id="5e265-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="5e265-442">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-442">Select **OK**.</span></span>

    <span data-ttu-id="5e265-443">Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído", que indica que a ID de trabalho da ordem de venda 1 foi preenchida.</span><span class="sxs-lookup"><span data-stu-id="5e265-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="5e265-444">Agora, você vai separar a ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="5e265-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="5e265-445">No campo **ID**, insira a ID de trabalho criada para a ordem de venda 2, onde a linha 1 tem o item *A0001*.</span><span class="sxs-lookup"><span data-stu-id="5e265-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="5e265-446">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-446">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-447">Na página **Ordens de venda - Separar**, insira uma LP de destino.</span><span class="sxs-lookup"><span data-stu-id="5e265-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="5e265-448">Observe que são exibidos o local de separação (*bulk-001*), o item (*A0001*) e a quantidade (*1 pacotes*).</span><span class="sxs-lookup"><span data-stu-id="5e265-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="5e265-449">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-449">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-450">Examine as informações na página **Ordens de venda - Colocar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="5e265-451">O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.</span><span class="sxs-lookup"><span data-stu-id="5e265-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="5e265-452">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-452">Select **OK**.</span></span>

    <span data-ttu-id="5e265-453">Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="5e265-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="5e265-454">Esta mensagem indica que a ID de trabalho da linha 1 da ordem de venda 2 foi preenchida.</span><span class="sxs-lookup"><span data-stu-id="5e265-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="5e265-455">No campo **ID**, insira a ID de trabalho criada para a ordem de venda 2, onde a linha 2 tem o item *A0002*.</span><span class="sxs-lookup"><span data-stu-id="5e265-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="5e265-456">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-456">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-457">Na página **Ordens de venda - Separar**, insira uma LP de destino.</span><span class="sxs-lookup"><span data-stu-id="5e265-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="5e265-458">Observe que são exibidos o local de separação (*bulk-002*), o item (*A0001*) e a quantidade (*1 pacotes*).</span><span class="sxs-lookup"><span data-stu-id="5e265-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="5e265-459">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-459">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-460">Examine as informações na página **Ordens de venda - Colocar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="5e265-461">O campo **Loc** deve indicar que os itens separados vão para o local de *Embalagem*.</span><span class="sxs-lookup"><span data-stu-id="5e265-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="5e265-462">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-462">Select **OK**.</span></span>

    <span data-ttu-id="5e265-463">Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, você receberá a mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="5e265-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="5e265-464">Esta mensagem indica que a ID de trabalho da linha 2 da ordem de venda 2 foi preenchida.</span><span class="sxs-lookup"><span data-stu-id="5e265-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="5e265-465">Embalar ordens de venda em contêineres</span><span class="sxs-lookup"><span data-stu-id="5e265-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="5e265-466">Embalar a ordem de venda 1 em contêineres</span><span class="sxs-lookup"><span data-stu-id="5e265-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="5e265-467">Vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Embalar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="5e265-468">É exibida a caixa de diálogo **Selecionar estação de embalagem**.</span><span class="sxs-lookup"><span data-stu-id="5e265-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="5e265-469">Por padrão, o campo **Trabalhador** deve ser definido com o nome do trabalhador configurado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="5e265-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="5e265-470">Defina os valores a seguir para exibir e trabalhar em remessas e contêineres planejados no local de embalagem específico:</span><span class="sxs-lookup"><span data-stu-id="5e265-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="5e265-471">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="5e265-471">**Site:** *6*</span></span>
    - <span data-ttu-id="5e265-472">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="5e265-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="5e265-473">**Local:** *Embalar*</span><span class="sxs-lookup"><span data-stu-id="5e265-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="5e265-474">**ID do perfil de embalagem:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="5e265-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="5e265-475">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5e265-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="5e265-476">Na página **Embalar**, no campo **Placa de licença ou remessa**, insira a LP de destino da ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="5e265-477">Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.</span><span class="sxs-lookup"><span data-stu-id="5e265-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="5e265-478">No Painel de Ação, selecione **Novo contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="5e265-479">Aceite todas as configurações padrão e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="5e265-480">Anote a ID do contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="5e265-481">Na FastTab **Embalagem de item**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-482">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="5e265-483">**Identificador:** Item *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e265-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="5e265-484">No Painel de Ação, selecione **Fechar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="5e265-485">Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="5e265-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="5e265-486">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-486">Select **OK**.</span></span> <span data-ttu-id="5e265-487">O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="5e265-488">Crie um segundo contêiner para adicionar o segundo item da LP da ordem de venda 1 a um novo contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="5e265-489">No Painel de Ação, selecione **Novo contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="5e265-490">Aceite todas as configurações padrão e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="5e265-491">Anote a ID do contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="5e265-492">Na FastTab **Embalagem de item**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-493">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="5e265-494">**Identificador:** Item *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e265-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="5e265-495">No Painel de Ação, selecione **Fechar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="5e265-496">Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="5e265-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="5e265-497">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-497">Select **OK**.</span></span> <span data-ttu-id="5e265-498">O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="5e265-499">Embalar a ordem de venda 2 em contêineres</span><span class="sxs-lookup"><span data-stu-id="5e265-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="5e265-500">Na página **Embalar**, no campo **Placa de licença ou remessa**, insira a LP de destino da linha 1 da ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="5e265-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="5e265-501">Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.</span><span class="sxs-lookup"><span data-stu-id="5e265-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="5e265-502">No Painel de Ação, selecione **Novo contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="5e265-503">Aceite todas as configurações padrão e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="5e265-504">Anote a ID do contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="5e265-505">Na FastTab **Embalagem de item**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-506">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="5e265-507">**Identificador:** Item *A0001*</span><span class="sxs-lookup"><span data-stu-id="5e265-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="5e265-508">No Painel de Ação, selecione **Fechar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="5e265-509">Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="5e265-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="5e265-510">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-510">Select **OK**.</span></span> <span data-ttu-id="5e265-511">O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="5e265-512">No campo **Placa de licença ou remessa**, insira a LP de destino da linha 2 da ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="5e265-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="5e265-513">Depois, selecione a tecla **Tab** ou **Enter** no teclado para sair do campo.</span><span class="sxs-lookup"><span data-stu-id="5e265-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="5e265-514">No Painel de Ação, selecione **Novo contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="5e265-515">Aceite todas as configurações padrão e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="5e265-516">Anote a ID do contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="5e265-517">Na FastTab **Embalagem de item**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="5e265-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5e265-518">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="5e265-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="5e265-519">**Campo identificador:** Item *A0002*</span><span class="sxs-lookup"><span data-stu-id="5e265-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="5e265-520">No Painel de Ação, selecione **Fechar contêiner**.</span><span class="sxs-lookup"><span data-stu-id="5e265-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="5e265-521">Na caixa de diálogo **Fechar contêiner**, selecione **Obter peso do sistema** para o sistema atualizar o campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="5e265-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="5e265-522">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-522">Select **OK**.</span></span> <span data-ttu-id="5e265-523">O contêiner muda para o local *CLASSIFICAR* e está pronto para classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="5e265-524">Para ver os detalhes do contêiner, vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Contêineres** e procure as IDs de contêiner criadas durante a embalagem.</span><span class="sxs-lookup"><span data-stu-id="5e265-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="5e265-525">Classificar os contêineres</span><span class="sxs-lookup"><span data-stu-id="5e265-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e265-526">Ao acessar o item de menu **Criação do palete** no aplicativo móvel para fazer a classificação de saída, você verá um botão **Completo**.</span><span class="sxs-lookup"><span data-stu-id="5e265-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="5e265-527">*Não use o botão **Completo** para classificar ou fechar a posição.*</span><span class="sxs-lookup"><span data-stu-id="5e265-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="5e265-528">O botão **Completo** é fornecido por padrão e não pode ser desabilitado nem removido da página.</span><span class="sxs-lookup"><span data-stu-id="5e265-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="5e265-529">Ele não é usado para o recurso *Classificação de saída*.</span><span class="sxs-lookup"><span data-stu-id="5e265-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="5e265-530">Classificar o primeiro contêiner</span><span class="sxs-lookup"><span data-stu-id="5e265-530">Sort the first container</span></span>

1. <span data-ttu-id="5e265-531">No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).</span><span class="sxs-lookup"><span data-stu-id="5e265-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="5e265-532">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="5e265-533">No menu **Saída**, selecione **Criação do palete**.</span><span class="sxs-lookup"><span data-stu-id="5e265-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="5e265-534">No campo **LP/Con**, insira a primeira ID de contêiner associada à ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="5e265-535">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-535">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-536">Como não existem posições de classificação no momento, você deve especificar uma.</span><span class="sxs-lookup"><span data-stu-id="5e265-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="5e265-537">No campo **ID da posição de classificação**, insira *SP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="5e265-538">Como no momento não há nenhuma LP associada à posição de classificação *SP01*, você deve especificar uma.</span><span class="sxs-lookup"><span data-stu-id="5e265-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="5e265-539">No campo **LP**, insira *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="5e265-540">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-540">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-541">Como a validação da posição de classificação está ativada, você deve inserir a ID da posição de classificação novamente.</span><span class="sxs-lookup"><span data-stu-id="5e265-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="5e265-542">No campo **ID da Posição de Classificação**, insira *SP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="5e265-543">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-543">Select **OK**.</span></span>

    <span data-ttu-id="5e265-544">Você receberá uma mensagem "Trabalho concluído".</span><span class="sxs-lookup"><span data-stu-id="5e265-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="5e265-545">Para exibir a posição de classificação e a LP nela, vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="5e265-546">A página **Atribuições de posição de classificação de saída** mostra todas as posições de classificação que estão ativas.</span><span class="sxs-lookup"><span data-stu-id="5e265-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="5e265-547">O campo **Classificar transações de posição** mostra a LP associada a cada posição de classificação e os contêineres que estão na posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="5e265-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="5e265-548">Observe que no momento existe uma posição de classificação e que a FastTab **Classificar critérios de posição** mostra um critério de **Remessa – Serviço da transportadora – Via Aérea**.</span><span class="sxs-lookup"><span data-stu-id="5e265-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="5e265-549">Classificar os contêineres restantes</span><span class="sxs-lookup"><span data-stu-id="5e265-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="5e265-550">No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).</span><span class="sxs-lookup"><span data-stu-id="5e265-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="5e265-551">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="5e265-552">No menu **Saída**, selecione **Criação do palete**.</span><span class="sxs-lookup"><span data-stu-id="5e265-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="5e265-553">No campo **LP/Con**, insira a segunda ID de contêiner associada à ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="5e265-554">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-554">Select **OK**.</span></span> <span data-ttu-id="5e265-555">Como o modelo de classificação está configurado para classificar automaticamente e já existe uma posição de classificação com critérios correspondentes, você será direcionado automaticamente para a posição de classificação correta.</span><span class="sxs-lookup"><span data-stu-id="5e265-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="5e265-556">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-556">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-557">Confirme a ID da posição da classificação para indicar que o estoque está no local correto.</span><span class="sxs-lookup"><span data-stu-id="5e265-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="5e265-558">No campo **ID da Posição de Classificação**, insira *SP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="5e265-559">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-559">Select **OK**.</span></span>

    <span data-ttu-id="5e265-560">O trabalho foi concluído no segundo contêiner da ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="5e265-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="5e265-561">Agora, você classificará os contêineres restantes da ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="5e265-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="5e265-562">No campo **LP/Con**, insira a ID de contêiner do contêiner da ordem de venda 2 que contém o item *A0001*.</span><span class="sxs-lookup"><span data-stu-id="5e265-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="5e265-563">Como o serviço da transportadora é diferente, você deverá inserir uma nova posição de classificação e atribuir uma LP a ela.</span><span class="sxs-lookup"><span data-stu-id="5e265-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="5e265-564">Use a posição de classificação *SP02* e a LP *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="5e265-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="5e265-565">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-565">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-566">Confirme a posição de classificação inserindo *SP02* no campo **ID da Posição de Classificação**.</span><span class="sxs-lookup"><span data-stu-id="5e265-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="5e265-567">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-567">Select **OK**.</span></span>

    <span data-ttu-id="5e265-568">O trabalho foi concluído no contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="5e265-569">No campo **LP/Con**, insira a ID de contêiner do contêiner restante da ordem de venda 2 que contém o item *A0002*.</span><span class="sxs-lookup"><span data-stu-id="5e265-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="5e265-570">Como o serviço de transportadora é o mesmo que o da ordem de venda 1, o sistema mostra a posição de classificação existente que tem os critérios correspondentes.</span><span class="sxs-lookup"><span data-stu-id="5e265-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="5e265-571">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-571">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-572">Confirme a posição de classificação inserindo *SP01* no campo **ID da Posição de Classificação**.</span><span class="sxs-lookup"><span data-stu-id="5e265-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="5e265-573">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-573">Select **OK**.</span></span>

    <span data-ttu-id="5e265-574">O trabalho foi concluído no contêiner.</span><span class="sxs-lookup"><span data-stu-id="5e265-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="5e265-575">Fechar as posições de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="5e265-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="5e265-576">Quando todo o estoque for classificado, a posição deverá ser fechada para que o trabalho possa ser criado.</span><span class="sxs-lookup"><span data-stu-id="5e265-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="5e265-577">O trabalho de separação do estoque classificado será criado para levar o estoque para a porta do compartimento.</span><span class="sxs-lookup"><span data-stu-id="5e265-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="5e265-578">Fechar uma posição no dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="5e265-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="5e265-579">No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).</span><span class="sxs-lookup"><span data-stu-id="5e265-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="5e265-580">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="5e265-581">No menu **Saída**, selecione **Criação do palete**.</span><span class="sxs-lookup"><span data-stu-id="5e265-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="5e265-582">No campo **LP/Con**, insira uma ID de contêiner classificada para a posição de classificação *SP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="5e265-583">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-583">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-584">Você receberá a seguinte mensagem: "O contêiner já está classificado para a posição SP01.</span><span class="sxs-lookup"><span data-stu-id="5e265-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="5e265-585">Fechar esta posição?"</span><span class="sxs-lookup"><span data-stu-id="5e265-585">Close the position?"</span></span> <span data-ttu-id="5e265-586">Selecione **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="5e265-586">Select **Close**.</span></span>

    <span data-ttu-id="5e265-587">O trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="5e265-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="5e265-588">Fechar uma posição nas atribuições de posição de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="5e265-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="5e265-589">Vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="5e265-590">Na coluna esquerda, selecione **SP02**.</span><span class="sxs-lookup"><span data-stu-id="5e265-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="5e265-591">Essa linha da posição de classificação de saída é a que você fechará.</span><span class="sxs-lookup"><span data-stu-id="5e265-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="5e265-592">No Painel de Ação, selecione **Fechar posição**.</span><span class="sxs-lookup"><span data-stu-id="5e265-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="5e265-593">O registro da posição de classificação é fechado e não é mais exibido.</span><span class="sxs-lookup"><span data-stu-id="5e265-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="5e265-594">Para mostrar todos os registros de posição fechados, marque a caixa de seleção **Mostrar fechado**.</span><span class="sxs-lookup"><span data-stu-id="5e265-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="5e265-595">Separação de estoque classificado</span><span class="sxs-lookup"><span data-stu-id="5e265-595">Sorted inventory picking</span></span>

<span data-ttu-id="5e265-596">Você deve concluir o trabalho de separação do estoque classificado.</span><span class="sxs-lookup"><span data-stu-id="5e265-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="5e265-597">Quando ele for concluído, o estoque será separado para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="5e265-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="5e265-598">Nesse ponto, todos os demais processos de depósito se aplicam.</span><span class="sxs-lookup"><span data-stu-id="5e265-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="5e265-599">No dispositivo móvel, entre no depósito *62* usando a ID de usuário criada para este cenário (ou a ID de usuário de um usuário de dados de demonstração existente).</span><span class="sxs-lookup"><span data-stu-id="5e265-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="5e265-600">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="5e265-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="5e265-601">No menu **Saída**, selecione **Carregar da Classificação**.</span><span class="sxs-lookup"><span data-stu-id="5e265-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="5e265-602">Insira a ID da LP de destino da primeira posição de classificação, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="5e265-603">Defina o campo **ID** como *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="5e265-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="5e265-604">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-604">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-605">A página **Separação do estoque classificado: Separar** mostra o trabalho de separação que deve ser feito.</span><span class="sxs-lookup"><span data-stu-id="5e265-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="5e265-606">Separe do local *CLASSIFICAR* e da LP de destino *PLP01*, que tem vários itens e uma quantidade de *3*.</span><span class="sxs-lookup"><span data-stu-id="5e265-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="5e265-607">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-607">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-608">A página **Separação do estoque classificado: Colocar** mostra o trabalho de colocação que deve ser feito.</span><span class="sxs-lookup"><span data-stu-id="5e265-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="5e265-609">Coloque no local *Baydoor* e na LP de destino *PLP01*, que tem vários itens e uma quantidade de *3*.</span><span class="sxs-lookup"><span data-stu-id="5e265-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="5e265-610">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-610">Select **OK**.</span></span>

    <span data-ttu-id="5e265-611">O trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="5e265-611">Work is completed.</span></span>

1. <span data-ttu-id="5e265-612">Insira a ID da placa de licença de destino da segunda posição de classificação, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="5e265-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="5e265-613">Defina o campo **ID** como *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="5e265-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="5e265-614">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-614">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-615">A página **Separação do estoque classificado: Separar** mostra o trabalho de separação que deve ser feito.</span><span class="sxs-lookup"><span data-stu-id="5e265-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="5e265-616">Separe do local *CLASSIFICAR* e da LP de destino *PLP02*, que tem vários itens e uma quantidade de *1*.</span><span class="sxs-lookup"><span data-stu-id="5e265-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="5e265-617">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-617">Select **OK**.</span></span>
1. <span data-ttu-id="5e265-618">A página **Separação do estoque classificado: Colocar** mostra o trabalho de colocação que deve ser feito.</span><span class="sxs-lookup"><span data-stu-id="5e265-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="5e265-619">Coloque no local *Baydoor* e na LP de destino *PLP02*, que tem vários itens e uma quantidade de *1*.</span><span class="sxs-lookup"><span data-stu-id="5e265-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="5e265-620">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e265-620">Select **OK**.</span></span>

    <span data-ttu-id="5e265-621">O trabalho foi concluído.</span><span class="sxs-lookup"><span data-stu-id="5e265-621">Work is completed.</span></span>

<span data-ttu-id="5e265-622">Desse ponto para a frente, todos os demais processos de depósito se aplicam.</span><span class="sxs-lookup"><span data-stu-id="5e265-622">From this point forward, all other warehouse processes apply.</span></span>