---
title: Clusters de armazenamento
description: Os clusters de armazenamento oferecem uma forma de separar várias chapas de licença ao mesmo tempo e, depois, levá-las para armazenamento em locais diferentes. Elas podem ser muito úteis para empresas de varejo, nas quais as chapas de licença normalmente não são paletes completos de estoque.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 297792e90b3d2da0d738f5cbaa14779bc17ea3c8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996189"
---
# <a name="putaway-clusters"></a><span data-ttu-id="7834d-104">Clusters de armazenamento</span><span class="sxs-lookup"><span data-stu-id="7834d-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7834d-105">Os clusters de armazenamento oferecem uma forma de separar várias chapas de licença ao mesmo tempo e, depois, levá-las para armazenamento em locais diferentes.</span><span class="sxs-lookup"><span data-stu-id="7834d-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="7834d-106">Esse processo geralmente é conhecido como *entrega programada*.</span><span class="sxs-lookup"><span data-stu-id="7834d-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="7834d-107">Os clusters de armazenamento podem ser muito úteis para empresas de varejo, nas quais as chapas de licença normalmente não são paletes completos de estoque.</span><span class="sxs-lookup"><span data-stu-id="7834d-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="7834d-108">Ativar o recurso de cluster de armazenamento</span><span class="sxs-lookup"><span data-stu-id="7834d-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="7834d-109">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="7834d-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="7834d-110">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="7834d-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="7834d-111">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="7834d-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="7834d-112">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="7834d-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="7834d-113">**Nome do recurso:** *Recurso de cluster de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="7834d-114">Configuração do cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="7834d-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="7834d-115">Perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-115">Cluster profiles</span></span>

<span data-ttu-id="7834d-116">O perfil de cluster de armazenamento determina para onde um item irá, com base na localização atribuída ao item no momento do recebimento.</span><span class="sxs-lookup"><span data-stu-id="7834d-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="7834d-117">Se forem necessários diferentes clusters, clusters de armazenamento diferentes deverão ser criados, um para cada item de menu de dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="7834d-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="7834d-118">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.</span><span class="sxs-lookup"><span data-stu-id="7834d-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="7834d-119">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7834d-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7834d-120">Na exibição do **Cabeçalho**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="7834d-121">**ID do perfil de cluster de armazenamento:** *Cluster de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="7834d-122">**Nome da ID do perfil de cluster de armazenamento:** *Cluster de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="7834d-123">**Tipo de cluster:** *Armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="7834d-124">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7834d-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="7834d-125">Selecione **Salvar** para disponibilizar os campos necessários na Guia rápida **Geral**.</span><span class="sxs-lookup"><span data-stu-id="7834d-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="7834d-126">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="7834d-127">**Tempo de atribuição do cluster:** *No recebimento*</span><span class="sxs-lookup"><span data-stu-id="7834d-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="7834d-128">Este campo define se o cluster de armazenamento deve ser atribuído imediatamente quando o estoque é recebido ou se deve ser classificado posteriormente.</span><span class="sxs-lookup"><span data-stu-id="7834d-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="7834d-129">**Regra de atribuição de cluster:** *Manual*</span><span class="sxs-lookup"><span data-stu-id="7834d-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="7834d-130">Esse campo define se a atribuição do cluster deve ser determinada automaticamente pelo sistema ou manualmente pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="7834d-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="7834d-131">**Código de diretiva:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="7834d-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="7834d-132">**Localização do cluster de armazenamento:** *Recebimento*</span><span class="sxs-lookup"><span data-stu-id="7834d-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="7834d-133">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7834d-133">The following values are available:</span></span>

        - <span data-ttu-id="7834d-134">**Recebimento** – Um local encontrado imediatamente durante o recebimento.</span><span class="sxs-lookup"><span data-stu-id="7834d-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="7834d-135">**Cluster fechado** – Um local encontrado quando o cluster é fechado.</span><span class="sxs-lookup"><span data-stu-id="7834d-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="7834d-136">**Direcionado pelo usuário** – Um local é encontrado quando a placa de licença é separada do cluster para armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7834d-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="7834d-137">Nesse caso, nenhuma localização é especificada quando o trabalho de armazenamento é criado.</span><span class="sxs-lookup"><span data-stu-id="7834d-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="7834d-138">Durante o armazenamento, o usuário deve verificar a placa de licença ou a ID de trabalho para iniciar a etapa put.</span><span class="sxs-lookup"><span data-stu-id="7834d-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="7834d-139">O sistema encontra o local de put novamente e informa ao usuário onde colocar a quantidade separada.</span><span class="sxs-lookup"><span data-stu-id="7834d-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="7834d-140">**Cluster de armazenamento por usuário:** *Não*</span><span class="sxs-lookup"><span data-stu-id="7834d-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="7834d-141">Este campo define se cada cluster deve ser exclusivo por usuário quando os clusters são atribuídos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7834d-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="7834d-142">Ele está disponível somente quando o campo **Regra de atribuição de cluster** está definido como *Automático*.</span><span class="sxs-lookup"><span data-stu-id="7834d-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="7834d-143">**Restrição de unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="7834d-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="7834d-144">Este campo define a unidade que deve ser recebida para o perfil ser válido.</span><span class="sxs-lookup"><span data-stu-id="7834d-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="7834d-145">Se estiver em branco, todas as unidades serão válidas.</span><span class="sxs-lookup"><span data-stu-id="7834d-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="7834d-146">**Quebra de unidade de trabalho:** *Individual*</span><span class="sxs-lookup"><span data-stu-id="7834d-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="7834d-147">Este campo define se todo o estoque deve ser consolidado (usando a ID do cluster e a placa de licença) em uma chapa de licença quando um cluster é fechado e se deve ser retirado como uma única placa de licença ou separadamente nas placas de licença recebidas.</span><span class="sxs-lookup"><span data-stu-id="7834d-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="7834d-148">Este campo não estará disponível quando o campo **Localizar cluster de armazenamento** estiver definido como *Recebido*.</span><span class="sxs-lookup"><span data-stu-id="7834d-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="7834d-149">**O cluster persiste como placa de licença pai:** *Não*</span><span class="sxs-lookup"><span data-stu-id="7834d-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="7834d-150">Se esta opção estiver definida como *Sim*, quando a etapa put for concluída, a ID do cluster se tornará uma placa de licença pai e todos os itens na ID do cluster serão vinculados à placa da licença pai.</span><span class="sxs-lookup"><span data-stu-id="7834d-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="7834d-151">Na Guia rápida **Classificação de cluster**, você pode definir critérios de classificação de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7834d-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="7834d-152">Selecione **Novo** na barra de ferramentas para adicionar uma linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="7834d-153">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="7834d-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="7834d-154">**Nome do campo:** *WMSLocationId*</span><span class="sxs-lookup"><span data-stu-id="7834d-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="7834d-155">Este campo define o campo que essa linha deve usar como um critério de classificação.</span><span class="sxs-lookup"><span data-stu-id="7834d-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="7834d-156">**Classificação:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="7834d-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="7834d-157">Este campo define se a classificação deve ser feita em ordem crescente ou decrescente.</span><span class="sxs-lookup"><span data-stu-id="7834d-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="7834d-158">Na Guia rápida **Modelo de trabalho do cluster**, selecione **Novo** na barra de ferramentas para adicionar uma linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="7834d-159">**Tipo de ordem de trabalho:** *Ordens de compra*</span><span class="sxs-lookup"><span data-stu-id="7834d-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="7834d-160">**Modelo de trabalho:** *Direto de OC 61*</span><span class="sxs-lookup"><span data-stu-id="7834d-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="7834d-161">No Painel de ações, selecione **Salvar** e, em seguida, **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="7834d-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="7834d-162">Na caixa de diálogo **Cluster de armazenamento**, na guia **Intervalo**, selecione **Adicionar** para adicionar uma segunda linha à consulta.</span><span class="sxs-lookup"><span data-stu-id="7834d-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="7834d-163">Em seguida, atualize as linhas da consulta conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="7834d-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="7834d-164">Tabela</span><span class="sxs-lookup"><span data-stu-id="7834d-164">Table</span></span> | <span data-ttu-id="7834d-165">Tabela derivada</span><span class="sxs-lookup"><span data-stu-id="7834d-165">Derived table</span></span> | <span data-ttu-id="7834d-166">Campo</span><span class="sxs-lookup"><span data-stu-id="7834d-166">Field</span></span> | <span data-ttu-id="7834d-167">Critérios</span><span class="sxs-lookup"><span data-stu-id="7834d-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="7834d-168">Trabalho</span><span class="sxs-lookup"><span data-stu-id="7834d-168">Work</span></span> | <span data-ttu-id="7834d-169">Trabalho</span><span class="sxs-lookup"><span data-stu-id="7834d-169">Work</span></span> | <span data-ttu-id="7834d-170">Depósito</span><span class="sxs-lookup"><span data-stu-id="7834d-170">Warehouse</span></span> | <span data-ttu-id="7834d-171">*61*</span><span class="sxs-lookup"><span data-stu-id="7834d-171">*61*</span></span> |
    | <span data-ttu-id="7834d-172">Trabalho</span><span class="sxs-lookup"><span data-stu-id="7834d-172">Work</span></span> | <span data-ttu-id="7834d-173">Trabalho</span><span class="sxs-lookup"><span data-stu-id="7834d-173">Work</span></span> | <span data-ttu-id="7834d-174">ID do Trabalho</span><span class="sxs-lookup"><span data-stu-id="7834d-174">Work ID</span></span> | <span data-ttu-id="7834d-175">Deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="7834d-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="7834d-176">Selecione **OK** para salvar a consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="7834d-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="7834d-177">No Painel de ações, selecione **Salvar**, e feche a página.</span><span class="sxs-lookup"><span data-stu-id="7834d-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7834d-178">Os campos no perfil de cluster que aparecem esmaecidos quando **Gerar ID do cluster** está definido como *Sim* não estão disponíveis e não são considerados quando esse recurso é usado.</span><span class="sxs-lookup"><span data-stu-id="7834d-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="7834d-179">Itens de menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="7834d-179">Mobile device menu items</span></span>

<span data-ttu-id="7834d-180">Dois novos itens de menu de dispositivo móvel estão disponíveis para esse recurso.</span><span class="sxs-lookup"><span data-stu-id="7834d-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="7834d-181">O item de menu **Receber e classificar cluster** é usado para classificar o estoque recebido em um cluster de armazenamento no recebimento.</span><span class="sxs-lookup"><span data-stu-id="7834d-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="7834d-182">O item de menu **Cluster de armazenamento** é usado para colocar o cluster fora depois de atribuído.</span><span class="sxs-lookup"><span data-stu-id="7834d-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="7834d-183">Receber e classificar cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-183">Receive and sort cluster</span></span>

<span data-ttu-id="7834d-184">Criar um novo item de menu de dispositivo móvel para receber estoque e classificar em um cluster.</span><span class="sxs-lookup"><span data-stu-id="7834d-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="7834d-185">Este item de menu criará trabalho de entrada depois que o estoque for recebido, o que indica que o item de menu a receber será usado para os clusters de putaway.</span><span class="sxs-lookup"><span data-stu-id="7834d-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="7834d-186">O item de menu **Receber e classificar cluster** pode ser usado com os seguintes itens de menu de recebimento:</span><span class="sxs-lookup"><span data-stu-id="7834d-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="7834d-187">Recebimento da linha da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="7834d-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="7834d-188">Recebimento do item da ordem de compra</span><span class="sxs-lookup"><span data-stu-id="7834d-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="7834d-189">Recebimento do item de carga</span><span class="sxs-lookup"><span data-stu-id="7834d-189">Load item receiving</span></span>

1. <span data-ttu-id="7834d-190">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="7834d-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="7834d-191">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7834d-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7834d-192">Na exibição do **Cabeçalho**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="7834d-193">**Nome do item de menu:** *Receber e classificar cluster*</span><span class="sxs-lookup"><span data-stu-id="7834d-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="7834d-194">**Título:** *Receber e classificar cluster*</span><span class="sxs-lookup"><span data-stu-id="7834d-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="7834d-195">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="7834d-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="7834d-196">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="7834d-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="7834d-197">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="7834d-198">**Processo de criação de trabalho:** *Recebimento de item da ordem de compra*</span><span class="sxs-lookup"><span data-stu-id="7834d-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="7834d-199">**Gerar placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="7834d-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="7834d-200">**Atribuir cluster de armazenamento:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="7834d-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="7834d-201">A opção **Atribuir cluster de armazenamento** está disponível apenas para a atividade *Processo de criação de trabalho* em uma etapa para recebimento.</span><span class="sxs-lookup"><span data-stu-id="7834d-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="7834d-202">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="7834d-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="7834d-203">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7834d-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="7834d-204">Armazenamento de cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-204">Cluster putaway</span></span>

<span data-ttu-id="7834d-205">Crie um novo item de menu de dispositivo móvel para colocar o cluster fora depois que ele tiver sido atribuído.</span><span class="sxs-lookup"><span data-stu-id="7834d-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="7834d-206">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="7834d-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="7834d-207">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7834d-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7834d-208">Na exibição do **Cabeçalho**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="7834d-209">**Nome do item de menu:** *Cluster de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="7834d-210">**Título:** *Cluster de armazenamento*</span><span class="sxs-lookup"><span data-stu-id="7834d-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="7834d-211">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="7834d-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="7834d-212">**Usar trabalho existente:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="7834d-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="7834d-213">Na FastTab **Geral**, defina o campo **Direcionado por** como *Cluster de armazenamento*.</span><span class="sxs-lookup"><span data-stu-id="7834d-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="7834d-214">Aceite os valores padrão para os campos restantes.</span><span class="sxs-lookup"><span data-stu-id="7834d-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="7834d-215">Na Guia rápida **Classes de trabalho**, configure a classe de trabalho válida para este item de menu de dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="7834d-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="7834d-216">**ID da classe de trabalho:** *Compra*</span><span class="sxs-lookup"><span data-stu-id="7834d-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="7834d-217">**Tipo de ordem de trabalho:** *Ordens de compra*</span><span class="sxs-lookup"><span data-stu-id="7834d-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="7834d-218">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7834d-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="7834d-219">Menu de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="7834d-219">Mobile device menu</span></span>

<span data-ttu-id="7834d-220">Adicione os itens de menu que acabou de criar ao menu de entrada do aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="7834d-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="7834d-221">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="7834d-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="7834d-222">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="7834d-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="7834d-223">Na lista de menus, selecione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="7834d-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="7834d-224">Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione **Receber e classificar cluster**.</span><span class="sxs-lookup"><span data-stu-id="7834d-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="7834d-225">Selecione o botão de seta para a direita a fim de mover o item de menu selecionado para a lista **Estrutura de Menu**.</span><span class="sxs-lookup"><span data-stu-id="7834d-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="7834d-226">Use o botão seta para cima ou seta para baixo para mover o item de menu para a posição desejada no menu.</span><span class="sxs-lookup"><span data-stu-id="7834d-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="7834d-227">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7834d-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="7834d-228">Repita as etapas 4 a 7 para adicionar os itens de menu restantes:</span><span class="sxs-lookup"><span data-stu-id="7834d-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="7834d-229">Atribuir cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-229">Assign cluster</span></span>
    - <span data-ttu-id="7834d-230">Armazenamento de cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="7834d-231">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="7834d-231">Example scenario</span></span>

<span data-ttu-id="7834d-232">Esse cenário simula o processamento de cluster de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="7834d-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="7834d-233">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="7834d-233">Create a purchase order</span></span>

1. <span data-ttu-id="7834d-234">Vá para **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="7834d-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="7834d-235">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="7834d-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="7834d-236">Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="7834d-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="7834d-237">**Conta do fornecedor:** *1001*</span><span class="sxs-lookup"><span data-stu-id="7834d-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="7834d-238">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="7834d-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="7834d-239">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7834d-239">Select **OK**.</span></span>

    <span data-ttu-id="7834d-240">A página **Todas as ordens de compra** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7834d-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="7834d-241">Na página **Todas as ordens de compra**, na Guia rápida **Linhas da ordem de compra**, use o botão **Adicionar linha** para adicionar as seguintes linhas:</span><span class="sxs-lookup"><span data-stu-id="7834d-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="7834d-242">Linha de ordem de compra 1:</span><span class="sxs-lookup"><span data-stu-id="7834d-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="7834d-243">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="7834d-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="7834d-244">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="7834d-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="7834d-245">Linha de ordem de compra 2:</span><span class="sxs-lookup"><span data-stu-id="7834d-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="7834d-246">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="7834d-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="7834d-247">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="7834d-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="7834d-248">Linha de ordem de compra 3:</span><span class="sxs-lookup"><span data-stu-id="7834d-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="7834d-249">**Número de item:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="7834d-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="7834d-250">**Quantidade:** *30*</span><span class="sxs-lookup"><span data-stu-id="7834d-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="7834d-251">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="7834d-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="7834d-252">Anote o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7834d-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="7834d-253">Receber estoque e armazená-lo longe do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="7834d-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="7834d-254">Receber e classificar o estoque em um cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="7834d-255">Entre no aplicativo de depósito como um usuário definido para o depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="7834d-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="7834d-256">No menu principal, selecione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="7834d-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="7834d-257">No menu **Entrada**, selecione **Receber e classificar cluster**.</span><span class="sxs-lookup"><span data-stu-id="7834d-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="7834d-258">No campo **Ponum**, insira o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="7834d-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="7834d-259">Selecione o botão **OK** (o botão de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="7834d-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="7834d-260">Selecione o campo **Item**, insira o número de item *A0001* e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7834d-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="7834d-261">Selecione o campo **Qtd**, insira *10* usando o teclado numérico e, em seguida, selecione o botão de marca de seleção.</span><span class="sxs-lookup"><span data-stu-id="7834d-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="7834d-262">Na página de tarefas **Qtd**, selecione **OK** (o botão marca de seleção) para confirmar a quantidade inserida.</span><span class="sxs-lookup"><span data-stu-id="7834d-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="7834d-263">Na página de tarefas **Item**, selecione **OK** para confirmar que o item *A0001* foi inserido.</span><span class="sxs-lookup"><span data-stu-id="7834d-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="7834d-264">Selecione o campo **ID do cluster** e insira um valor para atribuir uma ID para o cluster que está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="7834d-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="7834d-265">A ID inserida aqui será usada quando os dois itens restantes da ordem de compra forem recebidos.</span><span class="sxs-lookup"><span data-stu-id="7834d-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="7834d-266">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7834d-266">Select **OK**.</span></span>

    <span data-ttu-id="7834d-267">A página de tarefa **Ponum** será exibida e mostrará uma mensagem "Trabalho concluído".</span><span class="sxs-lookup"><span data-stu-id="7834d-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="7834d-268">O item *A0001* foi recebido no local *RECV* e atribuído à ID do cluster que você inseriu na etapa 10.</span><span class="sxs-lookup"><span data-stu-id="7834d-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="7834d-269">Repita as etapas 4 a 11 para receber os dois itens restantes da ordem de compra e atribuí-los à ID do cluster:</span><span class="sxs-lookup"><span data-stu-id="7834d-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="7834d-270">Uma quantidade de *20* para o item *A0002*</span><span class="sxs-lookup"><span data-stu-id="7834d-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="7834d-271">Uma quantidade de *30* para o item *M9215*</span><span class="sxs-lookup"><span data-stu-id="7834d-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="7834d-272">Fechar o cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-272">Close the cluster</span></span>

<span data-ttu-id="7834d-273">Antes que os itens no cluster possam ser descartados, o cluster deve ser fechado.</span><span class="sxs-lookup"><span data-stu-id="7834d-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="7834d-274">No Supply Chain Management, vá para **Gerenciamento de depósito \> Trabalho \> Saída \> Clusters de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="7834d-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="7834d-275">Na página **Clusters de trabalho**, na seção **Cluster de trabalho**, pesquise o campo **ID do cluster** para a ID do cluster inserida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7834d-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="7834d-276">Se o cluster não for exibido, talvez ele já tenha sido fechado.</span><span class="sxs-lookup"><span data-stu-id="7834d-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="7834d-277">Para determinar se o cluster foi fechado, marque a caixa de seleção **Mostrar trabalho fechado** e procure a ID do cluster inserida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7834d-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="7834d-278">E então, siga uma destas etapas:</span><span class="sxs-lookup"><span data-stu-id="7834d-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="7834d-279">Se o cluster tiver sido fechado, pule as etapas restantes deste procedimento e vá para o próximo procedimento, [Armazenar o cluster](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="7834d-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="7834d-280">Se o cluster não tiver sido fechado, siga as etapas restantes deste procedimento para fechar o cluster manualmente.</span><span class="sxs-lookup"><span data-stu-id="7834d-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="7834d-281">Em seguida, vá para o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="7834d-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="7834d-282">Na seção **Cluster de trabalho**, selecione a ID de cluster inserida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="7834d-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="7834d-283">No Painel de Ação, selecione **Fechar cluster**.</span><span class="sxs-lookup"><span data-stu-id="7834d-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="7834d-284">Depois que o cluster for fechado, ele não será mais exibido na seção **Cluster de trabalho** (a menos que a caixa de seleção **Mostrar trabalho fechado** esteja marcada).</span><span class="sxs-lookup"><span data-stu-id="7834d-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="7834d-285">Armazenar o cluster</span><span class="sxs-lookup"><span data-stu-id="7834d-285">Put the cluster away</span></span>

1. <span data-ttu-id="7834d-286">Entre no aplicativo de depósito como um usuário definido para o depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="7834d-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="7834d-287">No menu principal, selecione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="7834d-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="7834d-288">No menu **Entrada**, selecione **Cluster de armazenamento**.</span><span class="sxs-lookup"><span data-stu-id="7834d-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="7834d-289">Selecione **ID do cluster** e digite a ID do cluster que você inseriu anteriormente para o cluster fechado.</span><span class="sxs-lookup"><span data-stu-id="7834d-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="7834d-290">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7834d-290">Select **OK**.</span></span>

    <span data-ttu-id="7834d-291">A página **Cluster de armazenamento: Pegar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7834d-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="7834d-292">Ele mostra a ID do cluster, o local de separação, os itens (o valor *Múltiplo* será mostrado) e a quantidade total no cluster que deve ser separada.</span><span class="sxs-lookup"><span data-stu-id="7834d-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="7834d-293">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="7834d-293">Select **OK**.</span></span>

    <span data-ttu-id="7834d-294">A página **Cluster de armazenamento: Colocar** é exibida.</span><span class="sxs-lookup"><span data-stu-id="7834d-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="7834d-295">As instruções **Put** identificam a ID do cluster, o local de remessa, os itens, a quantidade total e as IDs da placa de licença para os itens que foram recebidos no cluster.</span><span class="sxs-lookup"><span data-stu-id="7834d-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="7834d-296">Você tem as opções padrão para substituir ou passar nesta etapa.</span><span class="sxs-lookup"><span data-stu-id="7834d-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="7834d-297">![Cluster de armazenamento: Página put](media/Cluster_putaway-Put.png "Cluster de armazenamento: Página put")</span><span class="sxs-lookup"><span data-stu-id="7834d-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="7834d-298">Selecione **OK** para confirmar o armazenamento do cluster.</span><span class="sxs-lookup"><span data-stu-id="7834d-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="7834d-299">Uma mensagem "Cluster Concluído" é exibida.</span><span class="sxs-lookup"><span data-stu-id="7834d-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="7834d-300">Observações e dicas</span><span class="sxs-lookup"><span data-stu-id="7834d-300">Notes and tips</span></span>

<span data-ttu-id="7834d-301">Nos casos em que a ID do cluster se torna a placa de licença pai de um palete aninhado, a posição de put é automaticamente fornecida quando a ID do cluster é verificada.</span><span class="sxs-lookup"><span data-stu-id="7834d-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="7834d-302">Nenhuma placa de licença adicional deverá ser verificada, mesmo se a geração da placa de licenças estiver definida como manual.</span><span class="sxs-lookup"><span data-stu-id="7834d-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>