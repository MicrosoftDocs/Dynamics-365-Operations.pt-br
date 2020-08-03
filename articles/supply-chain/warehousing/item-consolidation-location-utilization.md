---
title: Consolidação de itens - utilização do local
description: Este tópico fornece informações sobre a funcionalidade que facilita para os gerentes de depósito exibir e filtrar a utilização volumétrica de locais no depósito. Os gerentes podem selecionar locais e criar um trabalho de movimentação de estoque diretamente na página Consolidação de Itens para consolidar itens e, assim, fazer melhor uso do espaço do depósito.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 5e4172a8d3f82e6eeb8868aac87abd183a94c088
ms.sourcegitcommit: 14b554b43b9d86152ef27fdde6141589bcaf1161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3598776"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="2be9b-104">Consolidação de itens - utilização do local</span><span class="sxs-lookup"><span data-stu-id="2be9b-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2be9b-105">Este tópico fornece informações sobre a funcionalidade que facilita para os gerentes de depósito exibir e filtrar a utilização volumétrica de locais no depósito.</span><span class="sxs-lookup"><span data-stu-id="2be9b-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="2be9b-106">Os gerentes podem selecionar locais e criar um trabalho de movimentação de estoque diretamente na página **Consolidação de Itens** para consolidar itens e, assim, fazer melhor uso do espaço do depósito.</span><span class="sxs-lookup"><span data-stu-id="2be9b-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="2be9b-107">Ativar os recursos</span><span class="sxs-lookup"><span data-stu-id="2be9b-107">Turn on the features</span></span>

<span data-ttu-id="2be9b-108">Para poder usar os recursos descritos neste tópico, você deve ativá-los no sistema.</span><span class="sxs-lookup"><span data-stu-id="2be9b-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="2be9b-109">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status dos recursos e ativá-los se necessário.</span><span class="sxs-lookup"><span data-stu-id="2be9b-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="2be9b-110">Ative os dois recursos a seguir, na ordem em que aparecem listados.</span><span class="sxs-lookup"><span data-stu-id="2be9b-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="2be9b-111">(Os dois recursos são para o módulo **Gerenciamento de depósito**.)</span><span class="sxs-lookup"><span data-stu-id="2be9b-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="2be9b-112">Status da localização do depósito</span><span class="sxs-lookup"><span data-stu-id="2be9b-112">Warehouse location status</span></span>
2. <span data-ttu-id="2be9b-113">Utilização do local de consolidação do item</span><span class="sxs-lookup"><span data-stu-id="2be9b-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="2be9b-114">Status da localização do depósito</span><span class="sxs-lookup"><span data-stu-id="2be9b-114">Warehouse location status</span></span>

<span data-ttu-id="2be9b-115">O recurso *Status da localização do depósito* adiciona quatro novos campos à página **Locais** para rastrear mais informações sobre o estado atual do local:</span><span class="sxs-lookup"><span data-stu-id="2be9b-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="2be9b-116">**Número do item** — o item que está no local no momento.</span><span class="sxs-lookup"><span data-stu-id="2be9b-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="2be9b-117">Se o local contiver vários itens, este campo ficará em branco.</span><span class="sxs-lookup"><span data-stu-id="2be9b-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="2be9b-118">**Data e hora da última atividade** — o carimbo de data/hora da última transação de depósito executada no local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="2be9b-119">**Data de classificação por vencimento** — a data em que o estoque no local foi trazido para o depósito.</span><span class="sxs-lookup"><span data-stu-id="2be9b-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="2be9b-120">Essa data é calculada com base na data de classificação por vencimento da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="2be9b-121">Embora essa data seja precisa para locais rastreados por placa de licença, ela pode não ser precisa em locais que não são rastreados por placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="2be9b-122">**Status do local** – o status do local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="2be9b-123">Há quatro valores disponíveis:</span><span class="sxs-lookup"><span data-stu-id="2be9b-123">Four values are available:</span></span>

    - <span data-ttu-id="2be9b-124">**Indeterminado** – O perfil de localização não rastreia o status.</span><span class="sxs-lookup"><span data-stu-id="2be9b-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="2be9b-125">Portanto, o status atual é desconhecido.</span><span class="sxs-lookup"><span data-stu-id="2be9b-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="2be9b-126">**Vazio** – Não há estoque no local no momento.</span><span class="sxs-lookup"><span data-stu-id="2be9b-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="2be9b-127">**Separação** – Transações de saída foram executadas no local depois do último esvaziamento.</span><span class="sxs-lookup"><span data-stu-id="2be9b-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="2be9b-128">**Armazenamento** – Apenas transações de entrada foram executadas desde o último esvaziamento do local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="2be9b-129">Esses campos permitem que os gerentes de depósito tenham uma visão geral melhor do status dos locais no depósito.</span><span class="sxs-lookup"><span data-stu-id="2be9b-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="2be9b-130">Eles também permitem relatórios e filtragem mais avançados.</span><span class="sxs-lookup"><span data-stu-id="2be9b-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="2be9b-131">Configurar a consolidação de itens e a utilização do local</span><span class="sxs-lookup"><span data-stu-id="2be9b-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="2be9b-132">Esta seção descreve como preparar o sistema para usar a consolidação de itens e a utilização do local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="2be9b-133">Os procedimentos usam valores de exemplo dos dados de demonstração padrão.</span><span class="sxs-lookup"><span data-stu-id="2be9b-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="2be9b-134">Se você pretende trabalhar no cenário de exemplo fornecido mais adiante neste tópico, selecione a entidade legal **USMF** (que contém os dados de demonstração padrão) e crie cada registro descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="2be9b-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="2be9b-135">Se você não planeja trabalhar no cenário de exemplo, os valores fornecidos aqui podem ser considerados exemplos dos tipos de configuração que você deve executar para usar os recursos.</span><span class="sxs-lookup"><span data-stu-id="2be9b-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="2be9b-136">Produto liberado</span><span class="sxs-lookup"><span data-stu-id="2be9b-136">Released product</span></span>

1. <span data-ttu-id="2be9b-137">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="2be9b-138">No campo **Número do item**, selecione *M9201* e abra a página de detalhes.</span><span class="sxs-lookup"><span data-stu-id="2be9b-138">In the **Item number** field, select *M9201*, and open the details page.</span></span>
1. <span data-ttu-id="2be9b-139">No Painel de Ação, na guia **Gerenciar estoque**, no grupo **Depósito**, selecione **Dimensões físicas**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="2be9b-140">Na página **Dimensão Física**, no Painel de Ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="2be9b-141">Uma nova linha é adicionada à grade.</span><span class="sxs-lookup"><span data-stu-id="2be9b-141">A new line is added to the grid.</span></span> <span data-ttu-id="2be9b-142">O campo **Nº de itens** é predefinido.</span><span class="sxs-lookup"><span data-stu-id="2be9b-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="2be9b-143">No campo **Unidade**, selecione *unidade*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="2be9b-144">Os demais campos na linha são definidos automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2be9b-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="2be9b-145">Selecione **Salvar** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="2be9b-145">Select **Save**, and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="2be9b-146">Perfil de localização</span><span class="sxs-lookup"><span data-stu-id="2be9b-146">Location profile</span></span>

1. <span data-ttu-id="2be9b-147">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="2be9b-148">Na lista de perfis de localização, selecione **FLOOR-05**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="2be9b-149">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2be9b-150">Na FastTab **Geral**, verifique se as duas opções a seguir estão definidas como *Sim*:</span><span class="sxs-lookup"><span data-stu-id="2be9b-150">On the **General** FastTab, make sure that both the following options are set to *Yes*:</span></span>

    - <span data-ttu-id="2be9b-151">Habilitar o item no local</span><span class="sxs-lookup"><span data-stu-id="2be9b-151">Enable item in location</span></span>
    - <span data-ttu-id="2be9b-152">Habilitar o status local</span><span class="sxs-lookup"><span data-stu-id="2be9b-152">Enable location status</span></span>

1. <span data-ttu-id="2be9b-153">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2be9b-154">Se as opções **Habilitar o item no local** e **Habilitar o status do local** já tiverem sido definidas como *Sim*, vá para as instruções para configurar a FastTab **Dimensões** na etapa 10.</span><span class="sxs-lookup"><span data-stu-id="2be9b-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes*, skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="2be9b-155">Se as opções ainda não estiverem definidas como *Sim*, você deverá executar uma verificação de consistência do módulo **Gerenciamento de depósito** depois de defini-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="2be9b-155">If the options weren't already set to *Yes*, you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="2be9b-156">Nesse caso, vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="2be9b-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="2be9b-157">Para executar a verificação de consistência, vá para **Administração do sistema \> Tarefas periódicas \> Banco de dados \> Verificação de consistência**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="2be9b-158">Na caixa de diálogo **Verificação de consistência**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="2be9b-159">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="2be9b-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="2be9b-160">**Verificar/Corrigir:** *Corrigir*</span><span class="sxs-lookup"><span data-stu-id="2be9b-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="2be9b-161">**Data inicial:** deixe esse campo em branco.</span><span class="sxs-lookup"><span data-stu-id="2be9b-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="2be9b-162">**Verificação de consistência do status local do depósito:** marque essa caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="2be9b-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="2be9b-163">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="2be9b-164">Você receberá uma notificação quando a verificação de consistência for concluída.</span><span class="sxs-lookup"><span data-stu-id="2be9b-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="2be9b-165">Abra a [Central de Ações](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) para ver a mensagem.</span><span class="sxs-lookup"><span data-stu-id="2be9b-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="2be9b-166">Selecione **Detalhes da mensagem** para exibir os detalhes.</span><span class="sxs-lookup"><span data-stu-id="2be9b-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="2be9b-167">Se a mensagem da verificação de consistência afirmar "Informações de status local incorretas encontradas para local XXXX no depósito XX", você deverá executar a verificação novamente.</span><span class="sxs-lookup"><span data-stu-id="2be9b-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="2be9b-168">Desta vez, defina o campo **Verificar/Corrigir** como *Corrigir erro*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="2be9b-169">Veja as mensagens para ter certeza de que nenhum erro foi encontrado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="2be9b-170">Agora você deve terminar de configurar o perfil de localização.</span><span class="sxs-lookup"><span data-stu-id="2be9b-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="2be9b-171">Volte para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de locação**, selecione o perfil de localização **FLOOR-05** e, no Painel de Ação, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles**, select location profile **FLOOR-05**, and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2be9b-172">Na FastTab **Dimensões**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2be9b-173">**Porcentagem de utilização de volume:** *100*</span><span class="sxs-lookup"><span data-stu-id="2be9b-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="2be9b-174">**Método volumétrico usado para a localização de estoque:** *Usar volume da localização*</span><span class="sxs-lookup"><span data-stu-id="2be9b-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="2be9b-175">**Altura real da localização:** *10*</span><span class="sxs-lookup"><span data-stu-id="2be9b-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="2be9b-176">**Largura real da localização:** *10*</span><span class="sxs-lookup"><span data-stu-id="2be9b-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="2be9b-177">**Profundidade real da localização:** *10*</span><span class="sxs-lookup"><span data-stu-id="2be9b-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="2be9b-178">**Peso máximo:** *100*</span><span class="sxs-lookup"><span data-stu-id="2be9b-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="2be9b-179">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="2be9b-180">Itens de menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="2be9b-180">Mobile device menu items</span></span>

1. <span data-ttu-id="2be9b-181">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="2be9b-182">No Painel de Ação, selecione **Novo** para criar um item de menu para classificação.</span><span class="sxs-lookup"><span data-stu-id="2be9b-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="2be9b-183">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="2be9b-184">**Nome do item de menu:** *Ajustar em*</span><span class="sxs-lookup"><span data-stu-id="2be9b-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="2be9b-185">**Título:** *Ajustar em*</span><span class="sxs-lookup"><span data-stu-id="2be9b-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="2be9b-186">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="2be9b-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="2be9b-187">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="2be9b-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="2be9b-188">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="2be9b-189">**Processo de criação de trabalho:** *Ajuste em*</span><span class="sxs-lookup"><span data-stu-id="2be9b-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="2be9b-190">**Tipos de ajuste de estoque:** *Ajustar em*</span><span class="sxs-lookup"><span data-stu-id="2be9b-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="2be9b-191">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="2be9b-192">Menu de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="2be9b-192">Mobile device menu</span></span>

1. <span data-ttu-id="2be9b-193">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="2be9b-194">Na lista de menus, selecione **Estoque**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="2be9b-195">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="2be9b-196">Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Ajustar em**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="2be9b-197">Selecione o botão de seta para a direita para mover **Ajustar em** para a lista **Estrutura de menu**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="2be9b-198">Dessa forma, você adiciona o novo item de menu ao menu selecionado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="2be9b-199">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="2be9b-200">Tipos de movimento</span><span class="sxs-lookup"><span data-stu-id="2be9b-200">Movement types</span></span>

1. <span data-ttu-id="2be9b-201">Vá para **Gerenciamento de depósito \> Configuração \> Estoque \> Tipos de movimento**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="2be9b-202">No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-202">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="2be9b-203">**Código do tipo de movimento:** *CONSOLIDAR*</span><span class="sxs-lookup"><span data-stu-id="2be9b-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="2be9b-204">**Descrição:** *Consolidar locais*</span><span class="sxs-lookup"><span data-stu-id="2be9b-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="2be9b-205">**ID da classe de trabalho:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="2be9b-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="2be9b-206">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="2be9b-207">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="2be9b-207">Example scenario</span></span>

<span data-ttu-id="2be9b-208">O cenário a seguir usa o aplicativo de depósito em um dispositivo móvel para fazer um *ajuste em* estoque em dois locais no depósito.</span><span class="sxs-lookup"><span data-stu-id="2be9b-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="2be9b-209">Adicionar estoque a locais</span><span class="sxs-lookup"><span data-stu-id="2be9b-209">Add inventory to locations</span></span>

1. <span data-ttu-id="2be9b-210">Entre no dispositivo móvel como um usuário configurado para o depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="2be9b-211">Vá para **Estoque \> Ajustar em**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="2be9b-212">Agora você vai inserir o primeiro ajuste de local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="2be9b-213">Na tarefa **Ajuste em**, selecione o local para fazer o ajuste de estoque.</span><span class="sxs-lookup"><span data-stu-id="2be9b-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="2be9b-214">No campo **LOC**, selecione *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="2be9b-215">Confirme o local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-215">Confirm the location.</span></span>
1. <span data-ttu-id="2be9b-216">Crie uma ID de placa de licença para o item que será adicionado ao local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="2be9b-217">No campo **LP**, insira *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="2be9b-218">Confirme a placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="2be9b-219">Insira o item que será adicionado à placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="2be9b-220">No campo **ITEM**, insira *M9201*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="2be9b-221">Confirme o item.</span><span class="sxs-lookup"><span data-stu-id="2be9b-221">Confirm the item.</span></span>
1. <span data-ttu-id="2be9b-222">Insira a quantidade do item que será adicionado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="2be9b-223">No campo **QTD**, insira *10*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="2be9b-224">Confirme a quantidade.</span><span class="sxs-lookup"><span data-stu-id="2be9b-224">Confirm the quantity.</span></span>

    <span data-ttu-id="2be9b-225">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="2be9b-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="2be9b-226">Agora você vai inserir o segundo ajuste de local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="2be9b-227">Na tarefa **Ajuste em**, selecione o local para fazer o ajuste de estoque.</span><span class="sxs-lookup"><span data-stu-id="2be9b-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="2be9b-228">No campo **LOC**, selecione *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="2be9b-229">Confirme o local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-229">Confirm the location.</span></span>
1. <span data-ttu-id="2be9b-230">Crie uma ID de placa de licença para o item que será adicionado ao local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="2be9b-231">No campo **LP**, insira *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="2be9b-232">Confirme a placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="2be9b-233">Insira o item que será adicionado à placa de licença.</span><span class="sxs-lookup"><span data-stu-id="2be9b-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="2be9b-234">No campo **ITEM**, insira *M9201*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="2be9b-235">Confirme o item.</span><span class="sxs-lookup"><span data-stu-id="2be9b-235">Confirm the item.</span></span>
1. <span data-ttu-id="2be9b-236">Insira a quantidade do item que será adicionado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="2be9b-237">No campo **QTD**, insira *15*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="2be9b-238">Confirme a quantidade.</span><span class="sxs-lookup"><span data-stu-id="2be9b-238">Confirm the quantity.</span></span>

    <span data-ttu-id="2be9b-239">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="2be9b-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="2be9b-240">Selecione o botão Menu (também chamado de hambúrguer ou botão de hambúrguer) e clique em **Cancelar** para sair da tarefa **Ajuste em**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="2be9b-241">Consolidar locais</span><span class="sxs-lookup"><span data-stu-id="2be9b-241">Consolidate locations</span></span>

1. <span data-ttu-id="2be9b-242">Vá para **Gerenciamento de depósito \> Tarefas periódicas \> Consolidação de itens**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="2be9b-243">No cabeçalho, selecione um depósito para fazer a consolidação.</span><span class="sxs-lookup"><span data-stu-id="2be9b-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="2be9b-244">No campo **Depósito**, insira *51*.</span><span class="sxs-lookup"><span data-stu-id="2be9b-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="2be9b-245">É mostrado um registro para cada local onde o item *M9201* foi ajustado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="2be9b-246">A coluna **Porcentagem de utilização** mostra a utilização volumétrica de cada local.</span><span class="sxs-lookup"><span data-stu-id="2be9b-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="2be9b-247">Para consolidar o estoque, selecione todos os locais que devem ser consolidados e, no Painel de Ação, selecione **Consolidar Estoque**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="2be9b-248">Na caixa de diálogo **Consolidar estoque**, especifique o tipo de local e movimento que deve ser usado para criar o trabalho de movimento de estoque.</span><span class="sxs-lookup"><span data-stu-id="2be9b-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="2be9b-249">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="2be9b-249">Set the following values:</span></span>

    - <span data-ttu-id="2be9b-250">**Local:** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="2be9b-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="2be9b-251">**Código do tipo de movimento:** *CONSOLIDAR*</span><span class="sxs-lookup"><span data-stu-id="2be9b-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="2be9b-252">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-252">Select **OK**.</span></span>
1. <span data-ttu-id="2be9b-253">Você receberá uma mensagem informativa que mostra o trabalho de movimento criado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="2be9b-254">Anote a ID do trabalho de movimento.</span><span class="sxs-lookup"><span data-stu-id="2be9b-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="2be9b-255">Exibir trabalho de movimento</span><span class="sxs-lookup"><span data-stu-id="2be9b-255">View movement work</span></span>

1. <span data-ttu-id="2be9b-256">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="2be9b-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="2be9b-257">Exiba o trabalho que foi criado.</span><span class="sxs-lookup"><span data-stu-id="2be9b-257">View the work that was created.</span></span> <span data-ttu-id="2be9b-258">Use a ID do trabalho de movimento da consolidação do estoque para filtrar ou pesquisar a grade de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2be9b-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="2be9b-259">Nesse cenário, um local existente que tinha estoque foi usado como local da consolidação de estoque.</span><span class="sxs-lookup"><span data-stu-id="2be9b-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="2be9b-260">Por isso apenas uma ID de trabalho foi criada.</span><span class="sxs-lookup"><span data-stu-id="2be9b-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="2be9b-261">O sistema cria uma ID de trabalho para cada movimento a ser concluído.</span><span class="sxs-lookup"><span data-stu-id="2be9b-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="2be9b-262">Se você especificar um local que já contém estoque, somente uma ID de trabalho será criada.</span><span class="sxs-lookup"><span data-stu-id="2be9b-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="2be9b-263">Se especificar um novo local, duas IDs de trabalho serão criadas.</span><span class="sxs-lookup"><span data-stu-id="2be9b-263">If you specify a new location, two work IDs are created.</span></span>
