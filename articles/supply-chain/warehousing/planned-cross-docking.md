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
ms.openlocfilehash: 49807c90c145eee55fae2d515fd19925eb2d944c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810405"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="b4871-104">Distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="b4871-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4871-105">Este tópico descreve a distribuição integrada planejada avançada.</span><span class="sxs-lookup"><span data-stu-id="b4871-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="b4871-106">A distribuição integrada é um processo de depósito no qual a quantidade de estoque necessária para uma ordem é direcionada diretamente do recebimento ou da criação para a área de preparo ou doca de saída correta.</span><span class="sxs-lookup"><span data-stu-id="b4871-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="b4871-107">Todo o estoque restante da origem de entrada é direcionado para o local de armazenamento correto por meio do processo normal de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b4871-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="b4871-108">A distribuição integrada permite aos trabalhadores ignorar o armazenamento de entrada e a separação de saída de um estoque que já esteja marcado para uma ordem de saída.</span><span class="sxs-lookup"><span data-stu-id="b4871-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="b4871-109">Portanto, o número de vezes que o estoque é tocado é minimizado, sempre que possível.</span><span class="sxs-lookup"><span data-stu-id="b4871-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="b4871-110">Além disso, como há menos interação com o sistema, a economia de tempo e espaço no chão de fábrica do depósito aumenta.</span><span class="sxs-lookup"><span data-stu-id="b4871-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="b4871-111">Para que a distribuição integrada possa ser executada, o usuário deve configurar um novo modelo de distribuição integrada, no qual a fonte de fornecimento e outros conjuntos de requisitos para distribuição integrada sejam especificados.</span><span class="sxs-lookup"><span data-stu-id="b4871-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="b4871-112">Conforme a ordem de saída é criada, a linha deve ser marcada em relação a uma ordem de entrada que contenha o mesmo item.</span><span class="sxs-lookup"><span data-stu-id="b4871-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="b4871-113">No momento do recebimento da ordem de entrada, a configuração da distribuição integrada identifica automaticamente a necessidade de distribuição integrada e cria o trabalho de movimento para a quantidade necessária, com base na configuração da diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="b4871-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="b4871-114">As transações de estoque **não** têm seu registro cancelado quando o trabalho de distribuição integrada é cancelado, mesmo que a configuração para esse recurso esteja ativada nos Parâmetros de gerenciamento de depósito.</span><span class="sxs-lookup"><span data-stu-id="b4871-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="b4871-115">Ativar os recursos de distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="b4871-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="b4871-116">Se o sistema ainda não incluir os recursos descritos neste tópico, acesse [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e ative os seguintes recursos nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="b4871-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="b4871-117">*Distribuição integrada planejada*</span><span class="sxs-lookup"><span data-stu-id="b4871-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="b4871-118">*Modelos de distribuição integrada com diretivas de localização*</span><span class="sxs-lookup"><span data-stu-id="b4871-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="b4871-119">Configurar</span><span class="sxs-lookup"><span data-stu-id="b4871-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="b4871-120">Regenerar métodos de lançamento da carga</span><span class="sxs-lookup"><span data-stu-id="b4871-120">Regenerate load posting methods</span></span>

<span data-ttu-id="b4871-121">A distribuição integrada planejada é implementada como um método de lançamento da carga.</span><span class="sxs-lookup"><span data-stu-id="b4871-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="b4871-122">Depois de ativar o recurso, você deve regenerar os métodos.</span><span class="sxs-lookup"><span data-stu-id="b4871-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="b4871-123">Vá para **Gerenciamento de depósito \> Configuração \> Métodos de lançamento da carga**.</span><span class="sxs-lookup"><span data-stu-id="b4871-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="b4871-124">No Painel de Ação, selecione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="b4871-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="b4871-125">Após a conclusão da regeneração, você deverá ver um método com um valor *planCrossDocking* em **Nome do método**.</span><span class="sxs-lookup"><span data-stu-id="b4871-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="b4871-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b4871-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="b4871-127">Criar um modelo de distribuição integrada</span><span class="sxs-lookup"><span data-stu-id="b4871-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="b4871-128">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelos de distribuição integrada**.</span><span class="sxs-lookup"><span data-stu-id="b4871-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="b4871-129">No Painel de Ação, selecione **Novo** para criar um modelo.</span><span class="sxs-lookup"><span data-stu-id="b4871-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="b4871-130">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="b4871-131">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="b4871-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="b4871-132">Este campo define a ordem em que os modelos são avaliados.</span><span class="sxs-lookup"><span data-stu-id="b4871-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="b4871-133">**ID do modelo de distribuição integrada:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="b4871-134">**Descrição:** *Depósito 51*</span><span class="sxs-lookup"><span data-stu-id="b4871-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="b4871-135">**Política de liberação de demanda:** *Antes do recebimento de fornecimento*</span><span class="sxs-lookup"><span data-stu-id="b4871-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="b4871-136">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b4871-137">A configuração na FastTab **Planejamento** controla como o modelo funciona.</span><span class="sxs-lookup"><span data-stu-id="b4871-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="b4871-138">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-138">Set the following values:</span></span>

    - <span data-ttu-id="b4871-139">**Requisitos de demanda:** *Nenhum*</span><span class="sxs-lookup"><span data-stu-id="b4871-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="b4871-140">Este campo define os requisitos do estoque de demanda.</span><span class="sxs-lookup"><span data-stu-id="b4871-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="b4871-141">Se a demanda precisar ser vinculada ao fornecimento antes da liberação, selecione *Marcação*.</span><span class="sxs-lookup"><span data-stu-id="b4871-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="b4871-142">Se a demanda tiver que ser reservada para a ordem em relação ao fornecimento antes da liberação, selecione *Reserva da ordem*.</span><span class="sxs-lookup"><span data-stu-id="b4871-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="b4871-143">**Tipo de localização:** *Locais de remessa*</span><span class="sxs-lookup"><span data-stu-id="b4871-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="b4871-144">Este campo define se o trabalho de distribuição integrada deve usar os locais de preparo/carga da remessa ou se deve usar diretivas de localização para localizar seus próprios locais de preparo/carga.</span><span class="sxs-lookup"><span data-stu-id="b4871-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="b4871-145">**Modelo de trabalho:** Deixar este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="b4871-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="b4871-146">Este campo define o modelo de trabalho que deve ser usado quando o trabalho de distribuição integrada é criado.</span><span class="sxs-lookup"><span data-stu-id="b4871-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="b4871-147">**Revalidar no recebimento de fornecimento:** *Não*</span><span class="sxs-lookup"><span data-stu-id="b4871-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="b4871-148">Esta opção define se o fornecimento deve ser revalidado durante o recebimento.</span><span class="sxs-lookup"><span data-stu-id="b4871-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="b4871-149">Se essa opção estiver definida como *Sim*, a janela de tempo máximo e o intervalo de dias para o vencimento serão verificados.</span><span class="sxs-lookup"><span data-stu-id="b4871-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="b4871-150">**Código de diretiva:** deixe este campo em branco</span><span class="sxs-lookup"><span data-stu-id="b4871-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="b4871-151">Esta opção permite que o sistema use diretivas de localização para ajudar a determinar o melhor local de destino para o estoque de distribuição integrada.</span><span class="sxs-lookup"><span data-stu-id="b4871-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="b4871-152">Você pode configurá-la atribuindo um código de diretiva a cada modelo de distribuição integrada relevante.</span><span class="sxs-lookup"><span data-stu-id="b4871-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="b4871-153">Cada código de diretiva identifica uma diretiva de local exclusiva.</span><span class="sxs-lookup"><span data-stu-id="b4871-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="b4871-154">**Validar janela de tempo:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="b4871-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="b4871-155">Esta opção define se a janela de tempo máximo deve ser avaliada quando uma fonte de fornecimento é selecionada.</span><span class="sxs-lookup"><span data-stu-id="b4871-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="b4871-156">Se essa opção estiver definida como *Sim*, os campos relacionados às janelas de tempo máximo e mínimo serão disponibilizados.</span><span class="sxs-lookup"><span data-stu-id="b4871-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="b4871-157">**Janela de tempo máximo:** *5*</span><span class="sxs-lookup"><span data-stu-id="b4871-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="b4871-158">Este campo define o período máximo permitido entre a chegada do fornecimento e a saída da demanda.</span><span class="sxs-lookup"><span data-stu-id="b4871-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b4871-159">**Unidade da janela de tempo máximo:** *Dias*</span><span class="sxs-lookup"><span data-stu-id="b4871-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b4871-160">**Janela de tempo mínimo:** *0*</span><span class="sxs-lookup"><span data-stu-id="b4871-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="b4871-161">Este campo define o período mínimo permitido entre a chegada do fornecimento e a saída da demanda.</span><span class="sxs-lookup"><span data-stu-id="b4871-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="b4871-162">**Unidade da janela de tempo mínimo:** *Dias*</span><span class="sxs-lookup"><span data-stu-id="b4871-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="b4871-163">**Intervalo de dias para o vencimento:** *0*</span><span class="sxs-lookup"><span data-stu-id="b4871-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="b4871-164">*Critérios de FEFO (primeiro a vencer, primeiro a sair):* Este campo define o número máximo de dias entre a data de vencimento do primeiro lote a vencer atualmente no depósito e do lote que está sendo recebido.</span><span class="sxs-lookup"><span data-stu-id="b4871-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="b4871-165">Na FastTab **Fontes de fornecimento**, especifique os tipos de fornecimento válidos para o modelo.</span><span class="sxs-lookup"><span data-stu-id="b4871-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="b4871-166">Selecione **Novo** e defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="b4871-167">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="b4871-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b4871-168">**Fonte de fornecimento:** *Ordem de compra*</span><span class="sxs-lookup"><span data-stu-id="b4871-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="b4871-169">Criar uma classe de trabalho</span><span class="sxs-lookup"><span data-stu-id="b4871-169">Create a work class</span></span>

1. <span data-ttu-id="b4871-170">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4871-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="b4871-171">No Painel de Ação, selecione **Novo** para criar uma classe de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4871-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="b4871-172">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-172">Set the following values:</span></span>

    - <span data-ttu-id="b4871-173">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b4871-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b4871-174">**Descrição:** *Distribuição Integrada*</span><span class="sxs-lookup"><span data-stu-id="b4871-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="b4871-175">**Tipo de ordem de serviço:** *Distribuição integrada*</span><span class="sxs-lookup"><span data-stu-id="b4871-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="b4871-176">Criar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="b4871-176">Create a work template</span></span>

1. <span data-ttu-id="b4871-177">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4871-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b4871-178">Defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.</span><span class="sxs-lookup"><span data-stu-id="b4871-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b4871-179">No Painel de Ação, selecione **Novo** para adicionar uma linha à guia **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="b4871-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="b4871-180">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4871-181">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="b4871-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b4871-182">**Modelo de trabalho:** *Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="b4871-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="b4871-183">**Descrição do modelo de trabalho:** *Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="b4871-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="b4871-184">Selecione **Salvar** para disponibilizar a FastTab **Detalhes do Modelo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b4871-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="b4871-185">Na FastTab **Detalhes do Modelo de Trabalho**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b4871-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4871-186">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4871-187">**Tipo de trabalho:** *Separar*</span><span class="sxs-lookup"><span data-stu-id="b4871-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="b4871-188">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b4871-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b4871-189">Selecione **Novo** para adicionar outra linha e defina os seguintes valores nela:</span><span class="sxs-lookup"><span data-stu-id="b4871-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="b4871-190">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="b4871-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b4871-191">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b4871-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="b4871-192">Selecione **Salvar** e confirme se a caixa de seleção **Válido** está marcada para o modelo *Distribuição Integrada 51*.</span><span class="sxs-lookup"><span data-stu-id="b4871-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="b4871-193">As IDs de classe de trabalho dos tipos de trabalho *Separar* e *Colocar* devem ser as mesmas.</span><span class="sxs-lookup"><span data-stu-id="b4871-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="b4871-194">Criar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="b4871-194">Create location directives</span></span>

1. <span data-ttu-id="b4871-195">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="b4871-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="b4871-196">No painel esquerdo, defina o campo **Tipo de ordem de serviço** como *Distribuição integrada*.</span><span class="sxs-lookup"><span data-stu-id="b4871-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="b4871-197">No Painel de Ação, selecione **Novo** e defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="b4871-198">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="b4871-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="b4871-199">**Nome:** *Colocar Distribuição Integrada 51*</span><span class="sxs-lookup"><span data-stu-id="b4871-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="b4871-200">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="b4871-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="b4871-201">**Local:** *5*</span><span class="sxs-lookup"><span data-stu-id="b4871-201">**Site:** *5*</span></span>
    - <span data-ttu-id="b4871-202">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b4871-203">Selecione **Salvar** para disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="b4871-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="b4871-204">Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b4871-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4871-205">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4871-206">**Quantidade inicial:** *1*</span><span class="sxs-lookup"><span data-stu-id="b4871-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="b4871-207">**Quantidade final:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="b4871-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="b4871-208">Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="b4871-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="b4871-209">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b4871-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4871-210">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4871-211">**Nome:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="b4871-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="b4871-212">**Uso de localização fixa:** *Localizações fixas e não fixas*</span><span class="sxs-lookup"><span data-stu-id="b4871-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="b4871-213">Selecione **Salvar** para disponibilizar o botão **Editar consulta** na barra de ferramentas **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="b4871-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="b4871-214">Selecione **Editar consulta** para abrir o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b4871-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="b4871-215">Na guia **Intervalo**, verifique se as duas linhas a seguir foram configuradas:</span><span class="sxs-lookup"><span data-stu-id="b4871-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="b4871-216">Linha 1:</span><span class="sxs-lookup"><span data-stu-id="b4871-216">Line 1:</span></span>

        - <span data-ttu-id="b4871-217">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="b4871-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b4871-218">**Tabela Derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="b4871-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b4871-219">**Campo:** *Depósito*</span><span class="sxs-lookup"><span data-stu-id="b4871-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="b4871-220">**Critérios:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="b4871-221">Linha 2:</span><span class="sxs-lookup"><span data-stu-id="b4871-221">Line 2:</span></span>

        - <span data-ttu-id="b4871-222">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="b4871-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="b4871-223">**Tabela Derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="b4871-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="b4871-224">**Campo:** *Localização*</span><span class="sxs-lookup"><span data-stu-id="b4871-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="b4871-225">**Critérios:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="b4871-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="b4871-226">Selecione **OK** para fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="b4871-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="b4871-227">Criar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="b4871-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="b4871-228">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="b4871-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="b4871-229">Na lista de itens de menu no painel esquerdo, selecione **Armazenamento de compra**.</span><span class="sxs-lookup"><span data-stu-id="b4871-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="b4871-230">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="b4871-230">Select **Edit**.</span></span>
1. <span data-ttu-id="b4871-231">Na FastTab **Classes de trabalho**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="b4871-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="b4871-232">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="b4871-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="b4871-233">**ID da classe de trabalho:** *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="b4871-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="b4871-234">**Tipo de ordem de serviço:** *Distribuição integrada*</span><span class="sxs-lookup"><span data-stu-id="b4871-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="b4871-235">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b4871-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="b4871-236">Cenário</span><span class="sxs-lookup"><span data-stu-id="b4871-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="b4871-237">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="b4871-237">Create a purchase order</span></span>

<span data-ttu-id="b4871-238">Siga estas etapas para criar uma ordem de compra como fonte de fornecimento.</span><span class="sxs-lookup"><span data-stu-id="b4871-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="b4871-239">Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="b4871-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="b4871-240">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b4871-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b4871-241">Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b4871-242">**Conta do fornecedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="b4871-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="b4871-243">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b4871-244">Selecione **OK** e anote o número da ordem.</span><span class="sxs-lookup"><span data-stu-id="b4871-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="b4871-245">Uma nova linha é adicionada à FastTab **Linhas da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="b4871-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="b4871-246">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="b4871-247">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b4871-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b4871-248">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="b4871-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="b4871-249">Criar uma ordem de venda</span><span class="sxs-lookup"><span data-stu-id="b4871-249">Create a sales order</span></span>

<span data-ttu-id="b4871-250">Siga estas etapas para criar uma ordem de venda como origem de demanda.</span><span class="sxs-lookup"><span data-stu-id="b4871-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="b4871-251">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="b4871-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b4871-252">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b4871-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b4871-253">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b4871-254">**Conta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="b4871-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="b4871-255">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="b4871-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="b4871-256">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-256">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-257">Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="b4871-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b4871-258">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b4871-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="b4871-259">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b4871-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b4871-260">**Quantidade:** *3*</span><span class="sxs-lookup"><span data-stu-id="b4871-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="b4871-261">Criar distribuição integrada planejada</span><span class="sxs-lookup"><span data-stu-id="b4871-261">Create planned cross-docking</span></span>

<span data-ttu-id="b4871-262">Siga estas etapas para criar a distribuição integrada planejada com base na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b4871-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="b4871-263">Na página **Detalhes da ordem de venda** referente à ordem de venda que você acabou de criar, no Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="b4871-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="b4871-264">A ação de liberação para o depósito cria uma linha de remessa e carga para a linha da ordem de venda e tenta alocar o estoque.</span><span class="sxs-lookup"><span data-stu-id="b4871-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="b4871-265">Você receberá uma mensagem informativa.</span><span class="sxs-lookup"><span data-stu-id="b4871-265">You receive an informational message.</span></span> <span data-ttu-id="b4871-266">Você também receberá a seguinte mensagem de aviso: "Nenhum trabalho foi criado para a onda XXXX.</span><span class="sxs-lookup"><span data-stu-id="b4871-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="b4871-267">Consulte o log de histórico de criação de trabalho para obter detalhes."</span><span class="sxs-lookup"><span data-stu-id="b4871-267">See the work creation history log for details."</span></span> <span data-ttu-id="b4871-268">Esse comportamento é esperado, pois não há estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="b4871-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="b4871-269">Na FastTab **Linhas da ordem de venda**, no menu **Depósito**, selecione **Detalhes da remessa**.</span><span class="sxs-lookup"><span data-stu-id="b4871-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="b4871-270">A página **Detalhes da remessa** é exibida e mostra a remessa que foi criada para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b4871-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="b4871-271">Na FastTab **Linhas de carga**, observe que o campo **Quantidade da Distribuição integrada planejada** está definido como *3*.</span><span class="sxs-lookup"><span data-stu-id="b4871-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="b4871-272">Como não havia estoque disponível no depósito, mas uma fonte de fornecimento válida será recebida na janela de tempo definida no modelo de distribuição integrada, a quantidade de distribuição integrada foi criada.</span><span class="sxs-lookup"><span data-stu-id="b4871-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="b4871-273">Na FastTab **Linhas de carga**, selecione **Distribuição integrada planejada** para exibir os detalhes da distribuição integrada que foi criada.</span><span class="sxs-lookup"><span data-stu-id="b4871-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="b4871-274">Processar a distribuição integrada</span><span class="sxs-lookup"><span data-stu-id="b4871-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="b4871-275">Recebimento de ordem de compra no aplicativo móvel de depósito</span><span class="sxs-lookup"><span data-stu-id="b4871-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="b4871-276">O sistema receberá a quantidade de 5 da ordem de compra no local de recebimento e criará dois itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4871-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="b4871-277">Na primeira ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Distribuição integrada* e está vinculado à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b4871-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="b4871-278">Ela tem uma quantidade de 3 e é direcionada para o local de remessa final de modo que possa ser remetida imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b4871-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="b4871-279">Na segunda ID de trabalho criada, o **Tipo de ordem de serviço** tem o valor *Ordens de compra* e está vinculado à ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b4871-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="b4871-280">Ela tem a quantidade restante de 2 que não passou por distribuição integrada e é direcionada para o armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b4871-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="b4871-281">Entre no dispositivo móvel como um usuário no depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="b4871-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="b4871-282">Vá para **Entrada \> Recebimento de Compra**.</span><span class="sxs-lookup"><span data-stu-id="b4871-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="b4871-283">No campo **PONum**, insira o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="b4871-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="b4871-284">No campo **Qtd.**, insira *5*.</span><span class="sxs-lookup"><span data-stu-id="b4871-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="b4871-285">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-285">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-286">Na página seguinte, defina o campo **Item** como *A0001*.</span><span class="sxs-lookup"><span data-stu-id="b4871-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="b4871-287">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-287">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-288">Na página seguinte, confirme os valores de **PONum**, **Item** e **Qtd.** selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="b4871-289">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="b4871-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b4871-290">Selecione **Cancelar** para sair.</span><span class="sxs-lookup"><span data-stu-id="b4871-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="b4871-291">Armazenamento para distribuição integrada e em massa</span><span class="sxs-lookup"><span data-stu-id="b4871-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="b4871-292">No momento, ambas as IDs de trabalho têm a mesma placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="b4871-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="b4871-293">Para concluir as próximas etapas, você deve obter a ID de trabalho e a ID da placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="b4871-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="b4871-294">É possível obter essas informações nos detalhes do trabalho da linha de ordem de compra e da linha de ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b4871-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="b4871-295">Como alternativa, você pode acessar **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho** e filtrar trabalhos em que o valor de **Depósito** seja *51*.</span><span class="sxs-lookup"><span data-stu-id="b4871-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="b4871-296">No dispositivo móvel, vá para **Entrada \> Armazenamento de compra** e insira a placa de licença de destino do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4871-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="b4871-297">No campo **ID**, insira a ID da placa de licença de destino nos detalhes do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b4871-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="b4871-298">A página de separação da distribuição integrada mostra o local de separação (*RECV*), a placa de licença de destino (*placa de licença*), o item (*A0001*) e a quantidade (*3*).</span><span class="sxs-lookup"><span data-stu-id="b4871-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="b4871-299">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-299">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-300">No campo **LP de destino**, insira uma placa de licença de destino para a ID da placa de licença que deve ser colocada (passar por distribuição integrada) no local de remessa.</span><span class="sxs-lookup"><span data-stu-id="b4871-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="b4871-301">Você pode selecionar qualquer ID de placa de licença.</span><span class="sxs-lookup"><span data-stu-id="b4871-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="b4871-302">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-302">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-303">Na página seguinte, no campo **ID**, insira a ID da placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="b4871-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="b4871-304">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-304">Select **OK**.</span></span>
1. <span data-ttu-id="b4871-305">Confirme o trabalho para separar a quantidade restante de 2 e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="b4871-306">Na página seguinte, selecione **Concluído** para finalizar o processo de separação e iniciar o processo de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="b4871-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="b4871-307">O aplicativo móvel apresenta a localização e a placa de licença onde colocar o item.</span><span class="sxs-lookup"><span data-stu-id="b4871-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="b4871-308">Confirme o armazenamento em massa **Colocar** selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="b4871-309">Na página seguinte, confirme **Colocar** da distribuição integrada selecionando **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4871-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="b4871-310">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="b4871-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="b4871-311">Selecione **Cancelar** para sair.</span><span class="sxs-lookup"><span data-stu-id="b4871-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="b4871-312">A ilustração a seguir mostra como o trabalho de distribuição integrada concluído pode aparecer no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b4871-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="b4871-313">![Trabalho de distribuição integrada concluído](media/PlannedCrossDockingWork.png "Trabalho de distribuição integrada concluído")</span><span class="sxs-lookup"><span data-stu-id="b4871-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]