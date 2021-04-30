---
title: Distribuição integrada planejada
description: Este tópico descreve a distribuição integrada planejada avançada, na qual a quantidade de estoque necessária para uma ordem é direcionada diretamente do recebimento ou da criação para a área de preparo ou doca de saída correta. Todo o estoque restante da origem de entrada é direcionado para o local de armazenamento correto por meio do processo normal de armazenamento.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911239"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="e1dfa-104">Distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="e1dfa-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1dfa-105">Este tópico descreve a distribuição integrada planejada avançada.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="e1dfa-106">A distribuição integrada é um processo de depósito no qual a quantidade de estoque necessária para uma ordem é direcionada diretamente do recebimento ou da criação para a área de preparo ou doca de saída correta.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="e1dfa-107">Todo o estoque restante da origem de entrada é direcionado para o local de armazenamento correto por meio do processo normal de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="e1dfa-108">A distribuição integrada permite aos trabalhadores ignorar o armazenamento de entrada e a separação de saída de um estoque que já esteja marcado para uma ordem de saída.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="e1dfa-109">Portanto, o número de vezes que o estoque é tocado é minimizado, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="e1dfa-110">Além disso, como há menos interação com o sistema, a economia de tempo e espaço no chão de fábrica do depósito aumenta.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="e1dfa-111">Antes de executar a distribuição integrada, você deve configurar um novo modelo de distribuição integrada, no qual a fonte de fornecimento e outros conjuntos de requisitos para distribuição integrada sejam especificados.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="e1dfa-112">Conforme a ordem de saída é criada, a linha deve ser marcada em relação a uma ordem de entrada que contenha o mesmo item.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="e1dfa-113">Você pode selecionar o campo de código de diretriz no modelo de distribuição integrada, semelhante à forma como configura reabastecimento e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="e1dfa-114">No momento do recebimento da ordem de entrada, a configuração da distribuição integrada identifica automaticamente a necessidade de distribuição integrada e cria o trabalho de movimento para a quantidade necessária, com base na configuração da diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="e1dfa-115">As transações de estoque *não* têm seu registro cancelado quando o trabalho de distribuição integrada é cancelado, mesmo que a configuração para esse recurso esteja ativada nos Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="e1dfa-116">Ativar os recursos de distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="e1dfa-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="e1dfa-117">Se o sistema ainda não incluir os recursos descritos neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="e1dfa-118">*Distribuição integrada planejada*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="e1dfa-119">*Modelos de distribuição integrada com diretivas de localização*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="e1dfa-120">Este recurso permite que o campo **Código de diretriz** seja especificado no modelo de distribuição integrada, semelhante à forma como você configura os modelos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="e1dfa-121">Habilitar esse recurso impedirá que você adicione um código de diretriz nas linhas do modelo de trabalho de distribuição integrada para a última linha *Colocar*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="e1dfa-122">Isso garante que o local colocado final possa ser determinado durante a criação do trabalho antes de considerar os modelos de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="e1dfa-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="e1dfa-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="e1dfa-124">Regenerar métodos de lançamento da carga</span><span class="sxs-lookup"><span data-stu-id="e1dfa-124">Regenerate load posting methods</span></span>

<span data-ttu-id="e1dfa-125">A distribuição integrada planejada é implementada como um método de lançamento da carga.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="e1dfa-126">Depois de ativar o recurso, você deve regenerar os métodos.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="e1dfa-127">Vá para **Gerenciamento de depósito \> Configuração \> Métodos de lançamento da carga**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="e1dfa-128">No Painel de Ação, selecione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="e1dfa-129">Após a conclusão da regeneração, você deverá ver um método com um valor *planCrossDocking* em **Nome do método**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="e1dfa-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="e1dfa-131">Criar um modelo de distribuição integrada</span><span class="sxs-lookup"><span data-stu-id="e1dfa-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="e1dfa-132">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelos de distribuição integrada**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="e1dfa-133">No Painel de Ação, selecione **Novo** para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="e1dfa-134">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-135">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="e1dfa-136">Este campo define a ordem em que os modelos são avaliados.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="e1dfa-137">**ID do modelo de distribuição integrada:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="e1dfa-138">**Descrição:** *Depósito 51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="e1dfa-139">**Política de liberação de demanda:** *Antes do recebimento de fornecimento*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="e1dfa-140">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="e1dfa-141">A configuração na FastTab **Planejamento** controla como o modelo funciona.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="e1dfa-142">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-142">Set the following values:</span></span>

    - <span data-ttu-id="e1dfa-143">**Requisitos de demanda:** *Nenhum*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="e1dfa-144">Este campo define os requisitos do estoque de demanda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="e1dfa-145">Se a demanda precisar ser vinculada ao fornecimento antes da liberação, selecione *Marcação*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="e1dfa-146">Se a demanda tiver que ser reservada para a ordem em relação ao fornecimento antes da liberação, selecione *Reserva da ordem*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="e1dfa-147">**Tipo de localização:** *Locais de remessa*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="e1dfa-148">Este campo define se o trabalho de distribuição integrada deve usar os locais de preparo/carga da remessa ou se deve usar diretivas de localização para localizar seus próprios locais de preparo/carga.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="e1dfa-149">**Modelo de trabalho:** Deixar este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="e1dfa-150">Este campo define o modelo de trabalho que deve ser usado quando o trabalho de distribuição integrada é criado.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="e1dfa-151">**Revalidar no recebimento de fornecimento:** *Não*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="e1dfa-152">Esta opção define se o fornecimento deve ser revalidado durante o recebimento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="e1dfa-153">Se essa opção estiver definida como *Sim*, a janela de tempo máximo e o intervalo de dias para o vencimento serão verificados.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="e1dfa-154">**Código de diretiva:** deixe este campo em branco</span><span class="sxs-lookup"><span data-stu-id="e1dfa-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="e1dfa-155">Esta opção é habilitada pelo recurso *Modelos de distribuição integrada com diretivas de localização*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="e1dfa-156">O sistema usa diretivas de localização para ajudar a determinar o melhor local de destino para o estoque de distribuição integrada.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="e1dfa-157">Você pode configurá-la atribuindo um código de diretiva a cada modelo de distribuição integrada relevante.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="e1dfa-158">Se um código de diretiva estiver definido, o sistema pesquisará diretivas de localização por código de diretiva quando o trabalho for gerado.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="e1dfa-159">Dessa forma, você pode limitar as diretivas de localização usadas para um modelo de distribuição integrada específico.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="e1dfa-160">**Validar janela de tempo:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="e1dfa-161">Esta opção define se a janela de tempo máximo deve ser avaliada quando uma fonte de fornecimento é selecionada.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="e1dfa-162">Se essa opção estiver definida como *Sim*, os campos relacionados às janelas de tempo máximo e mínimo serão disponibilizados.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="e1dfa-163">**Janela de tempo máximo:** *5*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="e1dfa-164">Este campo define o período máximo permitido entre a chegada do fornecimento e a saída da demanda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="e1dfa-165">**Unidade da janela de tempo máximo:** *Dias*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="e1dfa-166">**Janela de tempo mínimo:** *0*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="e1dfa-167">Este campo define o período mínimo permitido entre a chegada do fornecimento e a saída da demanda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="e1dfa-168">**Unidade da janela de tempo mínimo:** *Dias*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="e1dfa-169">**Intervalo de dias para o vencimento:** *0*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="e1dfa-170">*Critérios de FEFO (primeiro a vencer, primeiro a sair):* Este campo define o número máximo de dias entre a data de vencimento do primeiro lote a vencer atualmente no depósito e do lote que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="e1dfa-171">Na FastTab **Fontes de fornecimento**, especifique os tipos de fornecimento válidos para o modelo.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="e1dfa-172">Selecione **Novo** e defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="e1dfa-173">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e1dfa-174">**Fonte de fornecimento:** *Ordem de compra*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="e1dfa-175">Criar uma classe de trabalho</span><span class="sxs-lookup"><span data-stu-id="e1dfa-175">Create a work class</span></span>

1. <span data-ttu-id="e1dfa-176">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="e1dfa-177">No Painel de Ação, selecione **Novo** para criar uma classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="e1dfa-178">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-178">Set the following values:</span></span>

    - <span data-ttu-id="e1dfa-179">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="e1dfa-180">**Descrição:** *Distribuição Integrada*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="e1dfa-181">**Tipo de ordem de serviço:** *Distribuição integrada*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="e1dfa-182">Criar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="e1dfa-182">Create a work template</span></span>

1. <span data-ttu-id="e1dfa-183">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e1dfa-184">Defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="e1dfa-185">No Painel de Ação, selecione **Novo** para adicionar uma linha à guia **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="e1dfa-186">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-187">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e1dfa-188">**Modelo de trabalho:** *Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="e1dfa-189">**Descrição do modelo de trabalho:** *Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="e1dfa-190">Selecione **Salvar** para disponibilizar a FastTab **Detalhes do Modelo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="e1dfa-191">Na FastTab **Detalhes do Modelo de Trabalho**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e1dfa-192">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-193">**Tipo de trabalho:** *Separar*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="e1dfa-194">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="e1dfa-195">Selecione **Novo** para adicionar outra linha e defina os seguintes valores nela:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="e1dfa-196">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="e1dfa-197">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="e1dfa-198">Selecione **Salvar** e confirme se a caixa de seleção **Válido** está marcada para o modelo *Distribuição Integrada 51*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="e1dfa-199">As IDs de classe de trabalho dos tipos de trabalho *Separar* e *Colocar* devem ser as mesmas.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="e1dfa-200">Criar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="e1dfa-200">Create location directives</span></span>

1. <span data-ttu-id="e1dfa-201">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="e1dfa-202">No painel esquerdo, defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="e1dfa-203">No Painel de Ação, selecione **Novo** e defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="e1dfa-204">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="e1dfa-205">**Nome:** *Colocar Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="e1dfa-206">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="e1dfa-207">**Local:** *5*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-207">**Site:** *5*</span></span>
    - <span data-ttu-id="e1dfa-208">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="e1dfa-209">Selecione **Salvar** para disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="e1dfa-210">Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e1dfa-211">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-212">**Quantidade inicial:** *1*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="e1dfa-213">**Quantidade final:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="e1dfa-214">Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="e1dfa-215">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e1dfa-216">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-217">**Nome:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="e1dfa-218">**Uso de localização fixa:** *Localizações fixas e não fixas*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="e1dfa-219">Selecione **Salvar** para disponibilizar o botão **Editar consulta** na barra de ferramentas **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="e1dfa-220">Selecione **Editar consulta** para abrir o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="e1dfa-221">Na guia **Intervalo**, verifique se as duas linhas a seguir foram configuradas:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="e1dfa-222">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-222">Line 1:</span></span>

        - <span data-ttu-id="e1dfa-223">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="e1dfa-224">**Tabela Derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="e1dfa-225">**Campo:** *Depósito*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="e1dfa-226">**Critérios:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="e1dfa-227">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-227">Line 2:</span></span>

        - <span data-ttu-id="e1dfa-228">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="e1dfa-229">**Tabela Derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="e1dfa-230">**Campo:** *Localização*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="e1dfa-231">**Critérios:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="e1dfa-232">Selecione **OK** para fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="e1dfa-233">Criar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e1dfa-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="e1dfa-234">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="e1dfa-235">Na lista de itens de menu no painel esquerdo, selecione **Armazenamento de compra**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="e1dfa-236">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-236">Select **Edit**.</span></span>
1. <span data-ttu-id="e1dfa-237">Na FastTab **Classes de trabalho**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="e1dfa-238">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-239">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="e1dfa-240">**Tipo de ordem de serviço:** *Distribuição integrada*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="e1dfa-241">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="e1dfa-242">Cenário</span><span class="sxs-lookup"><span data-stu-id="e1dfa-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="e1dfa-243">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="e1dfa-243">Create a purchase order</span></span>

<span data-ttu-id="e1dfa-244">Siga estas etapas para criar uma ordem de compra como fonte de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="e1dfa-245">Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="e1dfa-246">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e1dfa-247">Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-248">**Conta do fornecedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="e1dfa-249">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="e1dfa-250">Selecione **OK** e anote o número da ordem.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="e1dfa-251">Uma nova linha é adicionada à FastTab **Linhas da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="e1dfa-252">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-253">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e1dfa-254">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="e1dfa-255">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="e1dfa-255">Create a sales order</span></span>

<span data-ttu-id="e1dfa-256">Siga estas etapas para criar uma ordem de venda como origem de demanda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="e1dfa-257">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="e1dfa-258">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="e1dfa-259">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-260">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="e1dfa-261">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="e1dfa-262">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-262">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-263">Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="e1dfa-264">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e1dfa-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="e1dfa-265">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="e1dfa-266">**Quantidade:** *3*</span><span class="sxs-lookup"><span data-stu-id="e1dfa-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="e1dfa-267">Criar distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="e1dfa-267">Create planned cross-docking</span></span>

<span data-ttu-id="e1dfa-268">Siga estas etapas para criar a distribuição integrada planejada com base na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="e1dfa-269">Na página **Detalhes da ordem de venda** referente à ordem de venda que você acabou de criar, no Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="e1dfa-270">A ação de liberação para o depósito cria uma linha de remessa e carga para a linha da ordem de venda e tenta alocar o estoque.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="e1dfa-271">Você receberá uma mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-271">You receive an informational message.</span></span> <span data-ttu-id="e1dfa-272">Você também receberá a seguinte mensagem de aviso: "Nenhum trabalho foi criado para a onda XXXX.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="e1dfa-273">Consulte o log de histórico de criação de trabalho para obter detalhes."</span><span class="sxs-lookup"><span data-stu-id="e1dfa-273">See the work creation history log for details."</span></span> <span data-ttu-id="e1dfa-274">Esse comportamento é esperado, pois não há estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="e1dfa-275">Na FastTab **Linhas da ordem de venda**, no menu **Depósito**, selecione **Detalhes da remessa**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="e1dfa-276">A página **Detalhes da remessa** é exibida e mostra a remessa que foi criada para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="e1dfa-277">Na FastTab **Linhas de carga**, observe que o campo **Quantidade da Distribuição integrada planejada** está definido como *3*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="e1dfa-278">Como não havia estoque disponível no depósito, mas uma fonte de fornecimento válida será recebida na janela de tempo definida no modelo de distribuição integrada, a quantidade de distribuição integrada foi criada.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="e1dfa-279">Na FastTab **Linhas de carga**, selecione **Distribuição integrada planejada** para exibir os detalhes da distribuição integrada que foi criada.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="e1dfa-280">Processar a distribuição integrada</span><span class="sxs-lookup"><span data-stu-id="e1dfa-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="e1dfa-281">Recebimento de ordem de compra no aplicativo móvel de depósito</span><span class="sxs-lookup"><span data-stu-id="e1dfa-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="e1dfa-282">O sistema receberá a quantidade de 5 da ordem de compra no local de recebimento e criará dois itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="e1dfa-283">Na primeira ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Distribuição integrada* e está vinculado à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="e1dfa-284">Ela tem uma quantidade de 3 e é direcionada para o local de remessa final de modo que possa ser remetida imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="e1dfa-285">Na segunda ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Ordens de compra* e está vinculado à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="e1dfa-286">Ela tem a quantidade restante de 2 que não passou por distribuição integrada e é direcionada para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="e1dfa-287">Entre no dispositivo móvel como um usuário no depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="e1dfa-288">Vá para **Entrada \> Recebimento de Compra**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="e1dfa-289">No campo **PONum**, insira o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="e1dfa-290">No campo **Qtd.**, insira *5*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="e1dfa-291">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-291">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-292">Na página seguinte, defina o campo **Item** como *A0001*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="e1dfa-293">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-293">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-294">Na página seguinte, confirme os valores de **PONum**, **Item** e **Qtd.** selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="e1dfa-295">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="e1dfa-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="e1dfa-296">Selecione **Cancelar** para sair.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="e1dfa-297">Armazenamento para distribuição integrada e em massa</span><span class="sxs-lookup"><span data-stu-id="e1dfa-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="e1dfa-298">No momento, ambas as IDs de trabalho têm a mesma placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="e1dfa-299">Para concluir as próximas etapas, você deve obter a ID de trabalho e a ID da placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="e1dfa-300">É possível obter essas informações nos detalhes do trabalho da linha de ordem de compra e da linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="e1dfa-301">Como alternativa, você pode acessar **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho** e filtrar trabalhos em que o valor de **Depósito** seja *51*.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="e1dfa-302">No dispositivo móvel, vá para **Entrada \> Armazenamento de compra** e insira a placa de licença de destino do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="e1dfa-303">No campo **ID**, insira a ID da placa de licença de destino nos detalhes do trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="e1dfa-304">A página de separação da distribuição integrada mostra o local de separação (*RECV*), a placa de licença de destino (*placa de licença*), o item (*A0001*) e a quantidade (*3*).</span><span class="sxs-lookup"><span data-stu-id="e1dfa-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="e1dfa-305">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-305">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-306">No campo **LP de destino**, insira uma placa de licença de destino para a ID da placa de licença que deve ser colocada (passar por distribuição integrada) no local de remessa.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="e1dfa-307">Você pode selecionar qualquer ID de placa de licença.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="e1dfa-308">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-308">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-309">Na página seguinte, no campo **ID**, insira a ID da placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="e1dfa-310">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-310">Select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-311">Confirme o trabalho para separar a quantidade restante de 2 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="e1dfa-312">Na página seguinte, selecione **Concluído** para finalizar o processo de separação e iniciar o processo de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="e1dfa-313">O aplicativo móvel apresenta a localização e a placa de licença onde colocar o item.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="e1dfa-314">Confirme o armazenamento em massa **Colocar** selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="e1dfa-315">Na página seguinte, confirme **Colocar** da distribuição integrada selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="e1dfa-316">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="e1dfa-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="e1dfa-317">Selecione **Cancelar** para sair.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="e1dfa-318">A ilustração a seguir mostra como o trabalho de distribuição integrada concluído pode aparecer no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="e1dfa-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="e1dfa-319">![Trabalho de distribuição integrada concluído](media/PlannedCrossDockingWork.png "Trabalho de distribuição integrada concluído")</span><span class="sxs-lookup"><span data-stu-id="e1dfa-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]