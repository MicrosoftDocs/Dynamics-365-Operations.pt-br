---
title: Alterar pool de trabalho no trabalho
description: Este tópico explica como você pode usar o botão Alterar pool de trabalho para itens de trabalho a fim de alterar o pool de trabalho do trabalho existente.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 33238b114f0939711163b19ae7af98be7c8d0744
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597524"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="b905c-103">Alterar pool de trabalho no trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b905c-104">É possível usar pools de trabalho para organizar o trabalho em grupos.</span><span class="sxs-lookup"><span data-stu-id="b905c-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="b905c-105">Por exemplo, é possível criar um pool de trabalho para classificar o trabalho que ocorre em uma localização específica do depósito.</span><span class="sxs-lookup"><span data-stu-id="b905c-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="b905c-106">O recurso *Alterar pool de trabalho no trabalho* adiciona um botão **Alterar pool de trabalho** ao Painel de Ação para itens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="b905c-107">Portanto, os gerentes de depósito podem alterar facilmente o pool de trabalho do trabalho existente.</span><span class="sxs-lookup"><span data-stu-id="b905c-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="b905c-108">Este recurso permite aos gerentes reagir rapidamente a alterações no chão de fábrica do depósito e ajuda a melhorar sua capacidade de adaptação a situações mutáveis e a necessidade de transferir trabalho para outro pool de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="b905c-109">Ativar o recurso Alterar pool de trabalho no trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="b905c-110">Antes de começar a configurar ou usar este recurso, você deve verificar se ele está disponível no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="b905c-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="b905c-111">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="b905c-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b905c-112">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b905c-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b905c-113">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="b905c-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b905c-114">**Nome do recurso:** *Alterar pool de trabalho no trabalho*</span><span class="sxs-lookup"><span data-stu-id="b905c-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="b905c-115">Configurar o recurso Alterar pool de trabalho no trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="b905c-116">Para usar este recurso, você deve ter alguns pools de trabalho configurados.</span><span class="sxs-lookup"><span data-stu-id="b905c-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="b905c-117">Você também pode configurar seus modelos de trabalho para que eles atribuam um pool automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b905c-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="b905c-118">Se você quiser trabalhar no cenário de exemplo apresentado mais adiante neste tópico, configure o sistema conforme descrito nesta seção.</span><span class="sxs-lookup"><span data-stu-id="b905c-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="b905c-119">Configurar pools de trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-119">Set up work pools</span></span>

<span data-ttu-id="b905c-120">Os pools de trabalho permitem organizar itens de trabalho por tipo.</span><span class="sxs-lookup"><span data-stu-id="b905c-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="b905c-121">Para trabalhar com o recurso *Alterar pool de trabalho no trabalho*, você deve ter pelo menos dois pools de trabalho disponíveis.</span><span class="sxs-lookup"><span data-stu-id="b905c-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="b905c-122">Para exibir e adicionar pools de trabalho, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b905c-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="b905c-123">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Pools de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b905c-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="b905c-124">Se você estiver trabalhando com dados de demonstração da empresa **USMF** e for trabalhar no cenário de exemplo posteriormente neste tópico, adicione dois pools de trabalho com as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="b905c-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="b905c-125">Pool de trabalho 1:</span><span class="sxs-lookup"><span data-stu-id="b905c-125">Work pool 1:</span></span>

        - <span data-ttu-id="b905c-126">**ID do pool de trabalho:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="b905c-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="b905c-127">**Descrição:** *Web Shop*</span><span class="sxs-lookup"><span data-stu-id="b905c-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="b905c-128">Pool de trabalho 2:</span><span class="sxs-lookup"><span data-stu-id="b905c-128">Work pool 2:</span></span>

        - <span data-ttu-id="b905c-129">**ID do pool de trabalho:** *CallCenter*</span><span class="sxs-lookup"><span data-stu-id="b905c-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="b905c-130">**Descrição:** *Call Center*</span><span class="sxs-lookup"><span data-stu-id="b905c-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="b905c-131">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b905c-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="b905c-132">Configurar modelos de trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-132">Set up work templates</span></span>

<span data-ttu-id="b905c-133">Para cada um dos modelos de trabalho, você pode definir um pool de trabalho padrão, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="b905c-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="b905c-134">Para cada modelo relevante, você atribui um pool de trabalho na coluna **ID do pool de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b905c-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="b905c-135">Nesse caso, todos os itens de trabalho gerados por meio de um determinado modelo herdam automaticamente o pool de trabalho atribuído.</span><span class="sxs-lookup"><span data-stu-id="b905c-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="b905c-136">Se você estiver trabalhando com os dados de demonstração da empresa **USMF** e for trabalhar no cenário de exemplo posteriormente neste tópico, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b905c-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="b905c-137">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b905c-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="b905c-138">No Painel de Ação, selecione **Editar** para colocar a página no modo de edição.</span><span class="sxs-lookup"><span data-stu-id="b905c-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="b905c-139">Edite o modelo definindo os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b905c-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="b905c-140">**Modelo de trabalho:** *62 Separar para embalar*</span><span class="sxs-lookup"><span data-stu-id="b905c-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="b905c-141">**ID do pool de trabalho:** *Webshop*</span><span class="sxs-lookup"><span data-stu-id="b905c-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="b905c-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b905c-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="b905c-143">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="b905c-143">Example scenario</span></span>

<span data-ttu-id="b905c-144">Este cenário mostra como alterar o fluxo de processamento de um item de trabalho existente alterando seu pool de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="b905c-145">Ele usa dados de demonstração da empresa **USMF** e as configurações que foram sugeridas anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="b905c-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="b905c-146">Criar uma ordem de venda e liberá-la para o depósito</span><span class="sxs-lookup"><span data-stu-id="b905c-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="b905c-147">Confirme se há estoque disponível suficiente para os itens *A0001* e *A0002* no depósito *62*.</span><span class="sxs-lookup"><span data-stu-id="b905c-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="b905c-148">Vá para **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível** e edite os filtros, conforme mostrado aqui:</span><span class="sxs-lookup"><span data-stu-id="b905c-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="b905c-149">O valor de **Depósito** começa com *62*.</span><span class="sxs-lookup"><span data-stu-id="b905c-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="b905c-150">O valor de **Número do item** é *A001* ou *A002*.</span><span class="sxs-lookup"><span data-stu-id="b905c-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="b905c-151">Os dados de demonstração devem ter uma quantidade de 10 cada.</span><span class="sxs-lookup"><span data-stu-id="b905c-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="b905c-152">Em seguida, você deve criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b905c-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="b905c-153">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="b905c-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="b905c-154">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="b905c-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="b905c-155">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b905c-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="b905c-156">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="b905c-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="b905c-157">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="b905c-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="b905c-158">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="b905c-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="b905c-159">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="b905c-159">The new sales order is opened.</span></span> <span data-ttu-id="b905c-160">Ele deve incluir uma nova linha vazia na grade da FastTab **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="b905c-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="b905c-161">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b905c-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="b905c-162">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="b905c-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="b905c-163">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="b905c-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b905c-164">No menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="b905c-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b905c-165">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="b905c-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="b905c-166">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b905c-166">Close the page.</span></span>
1. <span data-ttu-id="b905c-167">Na FastTab **Linhas da ordem de venda**, selecione **Adicionar linha** para adicionar outra linha à sua ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b905c-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="b905c-168">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b905c-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="b905c-169">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="b905c-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="b905c-170">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="b905c-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="b905c-171">No menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="b905c-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="b905c-172">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="b905c-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="b905c-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="b905c-173">Close the page.</span></span>
1. <span data-ttu-id="b905c-174">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="b905c-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="b905c-175">Você recebe mensagens informativas que mostram a ID da onda e a ID da remessa que foram criadas com base na liberação.</span><span class="sxs-lookup"><span data-stu-id="b905c-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="b905c-176">Anote a ID da onda.</span><span class="sxs-lookup"><span data-stu-id="b905c-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="b905c-177">Revisar a onda de saída</span><span class="sxs-lookup"><span data-stu-id="b905c-177">Review the outbound wave</span></span>

1. <span data-ttu-id="b905c-178">Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="b905c-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="b905c-179">Na grade, procure a ID da onda que foi criada com base na liberação da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b905c-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="b905c-180">Selecione a ID da onda para exibir os detalhes.</span><span class="sxs-lookup"><span data-stu-id="b905c-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="b905c-181">Na FastTab **Linhas da onda**, verifique se uma ID de remessa é mostrada para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b905c-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="b905c-182">Se a opção **Processar onda na liberação para o depósito** estiver definida como *Não* na configuração do modelo de onda de remessa, você deverá processar manualmente a onda selecionando **Processar** na guia **Onda** no Painel de Ação para criar um trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="b905c-183">Verifique se a onda foi processada.</span><span class="sxs-lookup"><span data-stu-id="b905c-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="b905c-184">Esse processamento cria o trabalho necessário.</span><span class="sxs-lookup"><span data-stu-id="b905c-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="b905c-185">Exibir detalhes do trabalho e alterar o pool de trabalho</span><span class="sxs-lookup"><span data-stu-id="b905c-185">View work details and change the work pool</span></span>

<span data-ttu-id="b905c-186">Você pode usar a página **Detalhes do trabalho** para exibir o trabalho criado e gerenciar o pool de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="b905c-187">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b905c-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="b905c-188">Selecione a linha para o trabalho que acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="b905c-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="b905c-189">A coluna **Número da ordem** mostrará o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="b905c-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="b905c-190">O campo **ID do pool de trabalho** será definido como a ID do pool de trabalho que foi configurado no modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="b905c-191">Se você não vir o campo **ID do pool de trabalho**, adicione a coluna à grade e atualize a página.</span><span class="sxs-lookup"><span data-stu-id="b905c-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="b905c-192">Para alterar o pool de trabalho associado à ID de trabalho, no Painel de Ação, na guia **Trabalho**, selecione **Alterar ID do pool de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="b905c-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="b905c-193">Na caixa de diálogo **Alterar pool de trabalho**, na FastTab **Parâmetros**, no campo **ID do pool de trabalho**, selecione *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="b905c-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="b905c-194">Selecione **OK** para aplicar a alteração.</span><span class="sxs-lookup"><span data-stu-id="b905c-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="b905c-195">Observe que o valor do campo **ID do pool de trabalho** foi alterado para *CallCenter*.</span><span class="sxs-lookup"><span data-stu-id="b905c-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b905c-196">Quando a caixa de diálogo **Alterar pool de trabalho** for exibida, o campo **ID do pool de trabalho** poderá estar em branco por padrão.</span><span class="sxs-lookup"><span data-stu-id="b905c-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="b905c-197">Se o campo estiver em branco quando você selecionar **OK** para aplicar as alterações, o pool de trabalho será completamente removido do trabalho.</span><span class="sxs-lookup"><span data-stu-id="b905c-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="b905c-198">Além de alternar pools de trabalho, você pode usar esse procedimento para adicionar um pool de trabalho a qualquer item de trabalho que não tenha um ou para remover um pool de trabalho de qualquer item de trabalho que tenha um.</span><span class="sxs-lookup"><span data-stu-id="b905c-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>
