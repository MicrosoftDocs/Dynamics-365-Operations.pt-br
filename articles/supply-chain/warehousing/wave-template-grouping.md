---
title: Agrupamento de modelos de onda
description: O agrupamento de modelos de onda permite que o sistema use configurações de modelo de onda para determinar, com base em critérios definidos por você, como ele deve dividir linhas liberadas e atribuí-las a ondas novas ou existentes. Esse recurso pode ser útil em depósitos nos quais as ondas são criadas com base em critérios específicos, mas em que os gerentes preferem criar ondas de forma automática e não manual.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWaveTableListPage, WHSWaveTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9cbc0b6655de740628bcf3709d250ac02238038b
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4015817"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="67aab-104">Agrupamento de modelos de onda</span><span class="sxs-lookup"><span data-stu-id="67aab-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="67aab-105">O agrupamento de modelos de onda permite que o sistema use configurações de [modelo de onda](tasks/configure-wave-processing.md) para determinar, com base em critérios definidos por você, como ele deve dividir linhas liberadas e atribuí-las a ondas novas ou existentes.</span><span class="sxs-lookup"><span data-stu-id="67aab-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="67aab-106">Esse recurso pode ser útil em depósitos nos quais as ondas são criadas com base em critérios específicos, mas em que os gerentes preferem criar ondas de forma automática e não manual.</span><span class="sxs-lookup"><span data-stu-id="67aab-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="67aab-107">Ele permite que o sistema adicione cada remessa recém-liberada à primeira onda encontrada com valores de campo de agrupamento correspondente.</span><span class="sxs-lookup"><span data-stu-id="67aab-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="67aab-108">Se não houver correspondência, o sistema criará uma nova onda para a nova remessa.</span><span class="sxs-lookup"><span data-stu-id="67aab-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67aab-109">O agrupamento de modelos de onda não tem suporte para os tipos de trabalho *separação de matéria-prima de produção* ou *separação de Kanban*.</span><span class="sxs-lookup"><span data-stu-id="67aab-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="67aab-110">Isso ocorre porque o agrupamento de onda se baseia em remessas e esses tipos de trabalho não usam remessas.</span><span class="sxs-lookup"><span data-stu-id="67aab-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="67aab-111">Ativar o recurso Agrupamento de modelos de onda</span><span class="sxs-lookup"><span data-stu-id="67aab-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="67aab-112">Para você usar o recurso *Agrupamento de modelos de onda* , ele deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="67aab-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="67aab-113">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="67aab-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="67aab-114">No espaço de trabalho **Gerenciamento de recursos** , o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="67aab-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="67aab-115">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="67aab-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="67aab-116">**Nome do recurso:** *Agrupamento de modelos de onda*</span><span class="sxs-lookup"><span data-stu-id="67aab-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="67aab-117">Definir um modelo de onda para usar o agrupamento de modelos de onda</span><span class="sxs-lookup"><span data-stu-id="67aab-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="67aab-118">Para disponibilizar o agrupamento de modelos de onda, siga estas etapas para configurar o [modelo de onda](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="67aab-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="67aab-119">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="67aab-120">No painel esquerdo, selecione o modelo de onda a ser configurado.</span><span class="sxs-lookup"><span data-stu-id="67aab-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="67aab-121">Se você estiver se preparando para trabalhar no cenário mais adiante neste tópico usando dados de demonstração, selecione o modelo **Padrão de remessa 62**.</span><span class="sxs-lookup"><span data-stu-id="67aab-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="67aab-122">Selecione **Editar** para colocar a página no modo de edição.</span><span class="sxs-lookup"><span data-stu-id="67aab-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="67aab-123">Na FastTab **Geral** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="67aab-124">**Automatizar criação da onda:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="67aab-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="67aab-125">**Atribuir a ondas abertas:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="67aab-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="67aab-126">**Processar onda na liberação para o depósito** *Não*</span><span class="sxs-lookup"><span data-stu-id="67aab-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="67aab-127">No Painel de Ações, selecione **Editar consulta** para abrir a caixa de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="67aab-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="67aab-128">Na caixa de diálogo de consulta, na guia **Classificação** , analise os critérios de classificação e verifique se há uma regra que inclua o campo que você deseja usar para agrupar suas ondas.</span><span class="sxs-lookup"><span data-stu-id="67aab-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="67aab-129">Se você estiver se preparando para trabalhar no cenário usando dados de demonstração, adicione uma linha com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="67aab-130">**Tabela:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="67aab-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="67aab-131">**Tabela derivada:** *Remessas*</span><span class="sxs-lookup"><span data-stu-id="67aab-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="67aab-132">**Campo:** *Serviço da operadora*</span><span class="sxs-lookup"><span data-stu-id="67aab-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="67aab-133">Depois de selecionar este valor, você receberá a seguinte mensagem: "O serviço da operadora de campo não é um campo de índice.</span><span class="sxs-lookup"><span data-stu-id="67aab-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="67aab-134">Deseja adicionar classificação a ele?"</span><span class="sxs-lookup"><span data-stu-id="67aab-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="67aab-135">Selecione **Sim** para adicionar classificação.</span><span class="sxs-lookup"><span data-stu-id="67aab-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="67aab-136">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="67aab-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="67aab-137">Selecione **OK** para salvar as alterações e fechar a caixa de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="67aab-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="67aab-138">No Painel de Ações, selecione **Agrupamento de modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="67aab-139">Na página **Agrupamento de modelos de onda** , marque a caixa de seleção **Agrupar por** para cada linha que você deseja usar para agrupar linhas de ordem em ondas, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="67aab-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="67aab-140">Se você estiver se preparando para trabalhar no cenário usando dados de demonstração, marque a caixa de seleção **Agrupar por** para a linha *Serviço da operadora*.</span><span class="sxs-lookup"><span data-stu-id="67aab-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="67aab-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="67aab-141">Select **Save**.</span></span>
1. <span data-ttu-id="67aab-142">Feche a página **Agrupamento de modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="67aab-143">Selecione **Salvar** para salvar o seu modelo.</span><span class="sxs-lookup"><span data-stu-id="67aab-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="67aab-144">Cenário</span><span class="sxs-lookup"><span data-stu-id="67aab-144">Scenario</span></span>

<span data-ttu-id="67aab-145">Esta seção fornece um script saber o que esse recurso faz e como trabalhar com ele.</span><span class="sxs-lookup"><span data-stu-id="67aab-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="67aab-146">Disponibilizar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="67aab-146">Make sample data available</span></span>

<span data-ttu-id="67aab-147">Para trabalhar nesse cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="67aab-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="67aab-148">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="67aab-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="67aab-149">Você também pode usar este cenário como orientação para usar o recurso ao trabalhar em um sistema de produção.</span><span class="sxs-lookup"><span data-stu-id="67aab-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="67aab-150">No entanto, nesse caso, você deve substituir seus próprios valores e talvez não tenha alguns tipos de registros necessários fornecidos pelos dados de demonstração padrão.</span><span class="sxs-lookup"><span data-stu-id="67aab-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="67aab-151">Cenário: agrupamento de modelos de onda</span><span class="sxs-lookup"><span data-stu-id="67aab-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="67aab-152">Este cenário mostra como usar o agrupamento de modelos de onda para criar automaticamente várias ondas, com base em critérios de agrupamento definidos em um modelo de onda.</span><span class="sxs-lookup"><span data-stu-id="67aab-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="67aab-153">Neste cenário, o modelo de onda é configurado no sistema para criar uma onda por serviço de operadora.</span><span class="sxs-lookup"><span data-stu-id="67aab-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="67aab-154">Antes de começar, prepare o modelo de onda, conforme descrito na seção [Definir um modelo de onda para usar o agrupamento de modelos de onda](#set-up-template) anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="67aab-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="67aab-155">Se você estiver trabalhando com dados de demonstração para esse cenário, utilize os valores de dados de demonstração sugeridos no procedimento.</span><span class="sxs-lookup"><span data-stu-id="67aab-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="67aab-156">Essa configuração agrupará suas ondas de acordo com o serviço da operadora definido para cada ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="67aab-157">Criar ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="67aab-157">Create sales order 1</span></span>

1. <span data-ttu-id="67aab-158">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="67aab-159">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="67aab-160">Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="67aab-161">Na FastTab **Cliente** , defina o campo **Conta do cliente** como *US-004*.</span><span class="sxs-lookup"><span data-stu-id="67aab-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="67aab-162">Na FastTab **Geral** , defina o campo **Depósito** , como *62*.</span><span class="sxs-lookup"><span data-stu-id="67aab-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="67aab-163">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="67aab-164">A nova ordem de venda é aberta na exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="67aab-165">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="67aab-166">Alterne para a exibição do **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="67aab-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="67aab-167">Na guia **Remessa** , na seção **Transporte** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="67aab-168">**Transportadora:** *Carga aérea*</span><span class="sxs-lookup"><span data-stu-id="67aab-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="67aab-169">**Serviço da transportadora:** *Aéreo*</span><span class="sxs-lookup"><span data-stu-id="67aab-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="67aab-170">Alterne novamente para a exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="67aab-171">Na seção **Linhas da ordem de venda** , selecione **Adicionar linha** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="67aab-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="67aab-172">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="67aab-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="67aab-173">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="67aab-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="67aab-174">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="67aab-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="67aab-175">Selecione a nova linha da ordem e, no menu **Estoque** , acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="67aab-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="67aab-176">Na página **Reserva** , no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="67aab-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="67aab-177">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="67aab-178">No Painel de Ação, na guia **Depósito** , no grupo **Ações** , selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="67aab-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="67aab-179">Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="67aab-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="67aab-180">Anote o número da ID da onda e os números de ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="67aab-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="67aab-181">Exibir a onda que foi criada com base na ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="67aab-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="67aab-182">Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="67aab-183">Selecione a ID da onda que foi criada com base na ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="67aab-184">Selecione o link da ID da onda para abrir a página detalhes da onda.</span><span class="sxs-lookup"><span data-stu-id="67aab-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="67aab-185">Observe que a remessa foi adicionada à FastTab **Linhas da onda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="67aab-186">Criar ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="67aab-186">Create sales order 2</span></span>

1. <span data-ttu-id="67aab-187">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="67aab-188">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="67aab-189">Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="67aab-190">Na FastTab **Cliente** , defina o campo **Conta do cliente** como *US-005*.</span><span class="sxs-lookup"><span data-stu-id="67aab-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="67aab-191">Na FastTab **Geral** , defina o campo **Depósito** , como *62*.</span><span class="sxs-lookup"><span data-stu-id="67aab-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="67aab-192">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="67aab-193">A nova ordem de venda é aberta na exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="67aab-194">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="67aab-195">Alterne para a exibição do **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="67aab-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="67aab-196">Na guia **Remessa** , na seção **Transporte** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="67aab-197">**Transportadora:** *Movimento de flores*</span><span class="sxs-lookup"><span data-stu-id="67aab-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="67aab-198">**Serviço da operadora:** *Padrão*</span><span class="sxs-lookup"><span data-stu-id="67aab-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="67aab-199">Alterne novamente para a exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="67aab-200">Na seção **Linhas da ordem de venda** , selecione **Adicionar linha** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="67aab-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="67aab-201">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="67aab-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="67aab-202">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="67aab-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="67aab-203">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="67aab-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="67aab-204">Selecione a nova linha da ordem e, no menu **Estoque** , acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="67aab-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="67aab-205">Na página **Reserva** , no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="67aab-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="67aab-206">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="67aab-207">No Painel de Ação, na guia **Depósito** , no grupo **Ações** , selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="67aab-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="67aab-208">Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="67aab-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="67aab-209">Anote o número da ID da onda e os números de ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="67aab-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="67aab-210">Observe que a ID da onda difere da ID da onda da primeira ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="67aab-211">Exibir a onda que foi criada com base na ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="67aab-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="67aab-212">Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="67aab-213">Selecione a ID da onda que foi criada com base na segunda ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="67aab-214">Selecione o link da ID da onda para abrir a página detalhes da onda.</span><span class="sxs-lookup"><span data-stu-id="67aab-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="67aab-215">Observe que a remessa foi adicionada à FastTab **Linhas da onda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="67aab-216">Uma nova onda foi criada para essa remessa, pois ela usa um serviço de operadora diferente da primeira ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="67aab-217">Criar ordem de venda 3</span><span class="sxs-lookup"><span data-stu-id="67aab-217">Create sales order 3</span></span>

1. <span data-ttu-id="67aab-218">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="67aab-219">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="67aab-220">Na caixa de diálogo **Criar ordem de venda** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="67aab-221">Na FastTab **Cliente** , defina o campo **Conta do cliente** como *US-006*.</span><span class="sxs-lookup"><span data-stu-id="67aab-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="67aab-222">Na FastTab **Geral** , defina o campo **Depósito** , como *62*.</span><span class="sxs-lookup"><span data-stu-id="67aab-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="67aab-223">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo **Criar ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="67aab-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="67aab-224">A nova ordem de venda é aberta na exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="67aab-225">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="67aab-226">Alterne para a exibição do **Cabeçalho**.</span><span class="sxs-lookup"><span data-stu-id="67aab-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="67aab-227">Na guia **Remessa** , na seção **Transporte** , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="67aab-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="67aab-228">**Transportadora:** *Carga Aérea*</span><span class="sxs-lookup"><span data-stu-id="67aab-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="67aab-229">**Serviço da transportadora:** *Aéreo*</span><span class="sxs-lookup"><span data-stu-id="67aab-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="67aab-230">Alterne novamente para a exibição **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="67aab-231">Na seção **Linhas da ordem de venda** , selecione **Adicionar linha** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="67aab-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="67aab-232">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="67aab-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="67aab-233">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="67aab-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="67aab-234">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="67aab-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="67aab-235">Selecione a nova linha da ordem e, no menu **Estoque** , acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="67aab-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="67aab-236">Na página **Reserva** , no Painel de Ações, selecione **Reservar lote** para reservar a quantidade total da linha selecionada no depósito.</span><span class="sxs-lookup"><span data-stu-id="67aab-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="67aab-237">Feche a página **Reserva** para retornar à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="67aab-238">No Painel de Ação, na guia **Depósito** , no grupo **Ações** , selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="67aab-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="67aab-239">Você recebe uma mensagem informativa que mostra a remessa e a onda dessa ordem.</span><span class="sxs-lookup"><span data-stu-id="67aab-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="67aab-240">Anote o número da ID da onda e os números de ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="67aab-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="67aab-241">A remessa foi atribuída à onda existente com base na primeira ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="67aab-242">Exibir a onda para as ordens de venda 1 e 3</span><span class="sxs-lookup"><span data-stu-id="67aab-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="67aab-243">Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="67aab-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="67aab-244">Selecione a ID da onda que foi criada com base na terceira ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="67aab-245">Selecione o link da ID da onda para abrir a página detalhes da onda.</span><span class="sxs-lookup"><span data-stu-id="67aab-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="67aab-246">Observe que a remessa foi adicionada à FastTab **Linhas da onda** , junto com a remessa da primeira ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="67aab-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>
