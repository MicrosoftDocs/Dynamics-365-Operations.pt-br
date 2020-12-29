---
title: Sequenciamento do trabalho direcionado pelo sistema
description: Este tópico fornece informações sobre o sequenciamento de trabalho direcionado pelo sistema. Essa funcionalidade permite classificar e filtrar as ordens de serviço que o sistema apresenta a usuários para execução. Ela é útil em cenários que exigem critérios adicionais para direcionar o processo de separação de depósito.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 86d396b069a354b8fa7e15793372a8293273d238
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "4422572"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="214bb-105">Sequenciamento do trabalho direcionado pelo sistema</span><span class="sxs-lookup"><span data-stu-id="214bb-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="214bb-106">O sequenciamento direcionado pelo sistema permite classificar e filtrar as ordens de serviço que o sistema apresenta a usuários para execução.</span><span class="sxs-lookup"><span data-stu-id="214bb-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="214bb-107">Ela é útil em cenários que exigem critérios adicionais (como o tempo de remessa, a zona de separação, o perfil de local ou uma combinação de vários critérios) para direcionar o processo de separação de depósito.</span><span class="sxs-lookup"><span data-stu-id="214bb-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="214bb-108">Essa funcionalidade estende a funcionalidade atual de separação direcionada pelo sistema, adicionando uma ordem de consulta direcionada pelo sistema, na qual os usuários podem configurar uma sequência e uma ou mais consultas que avaliarão todas as ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="214bb-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="214bb-109">Somente as ordens de serviço que atendem aos critérios especificados na configuração do item de menu do dispositivo móvel serão capturadas e apresentadas.</span><span class="sxs-lookup"><span data-stu-id="214bb-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="214bb-110">Portanto, essa funcionalidade permite maior otimização de processos de separação de depósito, já que identifica as ordens de serviço que correspondem aos critérios especificados, atribuindo-as ao item de menu de dispositivo móvel correto e apresentando-as a um trabalhador, com base em um conjunto de habilidades específico, um equipamento de separação ou outro requisito.</span><span class="sxs-lookup"><span data-stu-id="214bb-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="214bb-111">Se forem necessários critérios diferentes, vários itens de menu de dispositivo móvel deverão ser usados.</span><span class="sxs-lookup"><span data-stu-id="214bb-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="214bb-112">Ative o recurso de sequenciamento de trabalho direcionado pelo sistema em toda a organização</span><span class="sxs-lookup"><span data-stu-id="214bb-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="214bb-113">Para que você possa usar o sequenciamento de trabalho direcionado pelo sistema, o recurso deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="214bb-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="214bb-114">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="214bb-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="214bb-115">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="214bb-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="214bb-116">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="214bb-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="214bb-117">**Nome do recurso:** *sequenciamento de trabalho direcionado pelo sistema em toda a organização*</span><span class="sxs-lookup"><span data-stu-id="214bb-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="214bb-118">Instalação</span><span class="sxs-lookup"><span data-stu-id="214bb-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="214bb-119">Disponibilizar dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="214bb-119">Make demo data available</span></span>

<span data-ttu-id="214bb-120">Para trabalhar com o cenário usando os valores apresentados neste tópico, você deve trabalhar em um sistema em que os dados de demonstração padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="214bb-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="214bb-121">Além disso, você deve selecionar a entidade legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="214bb-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="214bb-122">O cenário usa o depósito *51* dos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="214bb-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="214bb-123">Antes de liberar as ordens para o depósito, verifique se os locais de separação têm estoque suficiente para todos os itens nas ordens.</span><span class="sxs-lookup"><span data-stu-id="214bb-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="214bb-124">Os dados USMF padrão devem oferecer suporte a esse cenário.</span><span class="sxs-lookup"><span data-stu-id="214bb-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="214bb-125">Se não estiver usando dados de demonstração, revise a configuração **Diretiva de localização** para saber quais locais de separação são usados para separação da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="214bb-126">Se precisar ajustar o estoque, você poderá criar movimentações manuais, usar o reabastecimento ou utilizar qualquer outro fluxo.</span><span class="sxs-lookup"><span data-stu-id="214bb-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="214bb-127">Configurar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="214bb-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="214bb-128">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="214bb-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="214bb-129">Na lista de itens de menu de dispositivo móvel, selecione **Separação de Vendas – Sistema**.</span><span class="sxs-lookup"><span data-stu-id="214bb-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="214bb-130">O item de menu necessário já deve existir.</span><span class="sxs-lookup"><span data-stu-id="214bb-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="214bb-131">Confirme as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="214bb-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="214bb-132">Na FastTab **Geral**, o campo **Direcionado por** deve ser definido como *Dirigido pelo sistema*.</span><span class="sxs-lookup"><span data-stu-id="214bb-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="214bb-133">A FastTab **Classes de trabalho** deve mostrar as seguintes configurações.</span><span class="sxs-lookup"><span data-stu-id="214bb-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="214bb-134">ID da classe de trabalho</span><span class="sxs-lookup"><span data-stu-id="214bb-134">Work class ID</span></span> | <span data-ttu-id="214bb-135">Tipo de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="214bb-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="214bb-136">Sales</span><span class="sxs-lookup"><span data-stu-id="214bb-136">Sales</span></span> | <span data-ttu-id="214bb-137">Ordens de Venda</span><span class="sxs-lookup"><span data-stu-id="214bb-137">Sales orders</span></span> |
        | <span data-ttu-id="214bb-138">Separação de OV</span><span class="sxs-lookup"><span data-stu-id="214bb-138">SO Pick</span></span> | <span data-ttu-id="214bb-139">Ordens de Venda</span><span class="sxs-lookup"><span data-stu-id="214bb-139">Sales orders</span></span> |

1. <span data-ttu-id="214bb-140">No Painel de Ações, selecione **Consultas de sequência de trabalho direcionadas pelo sistema**.</span><span class="sxs-lookup"><span data-stu-id="214bb-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="214bb-141">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="214bb-141">Select **Edit**.</span></span>
1. <span data-ttu-id="214bb-142">Exclua a linha existente e confirme a ação selecionando **Sim**.</span><span class="sxs-lookup"><span data-stu-id="214bb-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="214bb-143">No Painel de Ações, selecione **Novo** para criar uma linha.</span><span class="sxs-lookup"><span data-stu-id="214bb-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="214bb-144">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="214bb-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="214bb-145">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="214bb-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="214bb-146">**Campo de descrição:** *Quantidade de trabalho inferior a 20 e decrescente*</span><span class="sxs-lookup"><span data-stu-id="214bb-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="214bb-147">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="214bb-147">Select **Save**.</span></span>
1. <span data-ttu-id="214bb-148">No Painel de Ações, selecione **Editar Consulta**.</span><span class="sxs-lookup"><span data-stu-id="214bb-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="214bb-149">Na guia **Junções**, expanda a hierarquia de junções para mostrar a tabela **Linhas de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="214bb-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="214bb-150">Selecione a junção de tabela **Linhas de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="214bb-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="214bb-151">Selecione **Adicionar junção de tabela**.</span><span class="sxs-lookup"><span data-stu-id="214bb-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="214bb-152">Na lista exibida, localize e selecione a linha que tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="214bb-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="214bb-153">**Modo de junção:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="214bb-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="214bb-154">**Relação:** *Locais (local)*</span><span class="sxs-lookup"><span data-stu-id="214bb-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="214bb-155">Escolha **Selecionar**.</span><span class="sxs-lookup"><span data-stu-id="214bb-155">Select **Select**.</span></span>

    <span data-ttu-id="214bb-156">Os locais são adicionados à junção da tabela.</span><span class="sxs-lookup"><span data-stu-id="214bb-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="214bb-157">Na guia **Classificação**, selecione **Adicionar** para adicionar uma linha.</span><span class="sxs-lookup"><span data-stu-id="214bb-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="214bb-158">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="214bb-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="214bb-159">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-160">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-161">**Campo:** *Quantidade de trabalho* (na caixa de mensagem que aparecer, selecione **Sim** para adicionar classificação a este campo.)</span><span class="sxs-lookup"><span data-stu-id="214bb-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="214bb-162">**Direção da pesquisa:** *Decrescente*</span><span class="sxs-lookup"><span data-stu-id="214bb-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="214bb-163">Selecione a guia **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="214bb-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="214bb-164">Se somente critérios de trabalho específicos devem ser incluídos no sequenciamento, você pode especificá-los na guia **Intervalo**. Neste exemplo, você deseja incluir somente o trabalho em que a quantidade é inferior a 20 ea (a menor unidade de medida).</span><span class="sxs-lookup"><span data-stu-id="214bb-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="214bb-165">Observe que algumas linhas já foram incluídas.</span><span class="sxs-lookup"><span data-stu-id="214bb-165">Notice that some lines are already included.</span></span> <span data-ttu-id="214bb-166">Essas linhas não devem ser removidas.</span><span class="sxs-lookup"><span data-stu-id="214bb-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="214bb-167">Selecione **Adicionar** para adicionar uma linha.</span><span class="sxs-lookup"><span data-stu-id="214bb-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="214bb-168">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="214bb-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="214bb-169">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-170">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-171">**Campo:** *Quantidade de trabalho de estoque*</span><span class="sxs-lookup"><span data-stu-id="214bb-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="214bb-172">**Critérios:** *\<20* (menos de 20)</span><span class="sxs-lookup"><span data-stu-id="214bb-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="214bb-173">Selecione **Adicionar** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="214bb-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="214bb-174">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="214bb-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="214bb-175">**Tabela:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-176">**Tabela derivada:** *Linhas de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="214bb-177">**Campo:** *Tipo de trabalho*</span><span class="sxs-lookup"><span data-stu-id="214bb-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="214bb-178">**Critérios:** *Separação*</span><span class="sxs-lookup"><span data-stu-id="214bb-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="214bb-179">Selecione **Adicionar** para adicionar outra linha.</span><span class="sxs-lookup"><span data-stu-id="214bb-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="214bb-180">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="214bb-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="214bb-181">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="214bb-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="214bb-182">**Tabela derivada:** *Locais*</span><span class="sxs-lookup"><span data-stu-id="214bb-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="214bb-183">**Campo:** *ID de perfil da localização*</span><span class="sxs-lookup"><span data-stu-id="214bb-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="214bb-184">**Critérios:** *!ESTÁGIO*</span><span class="sxs-lookup"><span data-stu-id="214bb-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="214bb-185">Inclua o ponto de exclamação (*!*) antes de *ESTÁGIO*.</span><span class="sxs-lookup"><span data-stu-id="214bb-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="214bb-186">Selecione **OK** para salvar e fechar a consulta.</span><span class="sxs-lookup"><span data-stu-id="214bb-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="214bb-187">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="214bb-187">Select **Save**.</span></span>
1. <span data-ttu-id="214bb-188">Feche a página para retornar à página **Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="214bb-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="214bb-189">Essa configuração define os critérios que serão usados para alimentar o trabalho elegível para o item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="214bb-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="214bb-190">Se você adicionar mais linhas de critérios à consulta, o sistema usará primeiro a linha de consulta com o menor número de sequência.</span><span class="sxs-lookup"><span data-stu-id="214bb-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="214bb-191">Em outras palavras, todo o trabalho elegível para a sequência número 1 será apresentado primeiro ao usuário e, em seguida, todo o trabalho para a sequência número 2.</span><span class="sxs-lookup"><span data-stu-id="214bb-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="214bb-192">Portanto, se um intervalo e classificação específicos precisam ser usados juntos, eles devem ser especificados na mesma consulta de sequência de trabalho direcionada pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="214bb-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="214bb-193">Esta configuração capturará trabalhos que tenham pelo menos uma linha em que a quantidade seja inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="214bb-194">Portanto, se o trabalho tiver uma linha em que a quantidade seja exatamente 20 ea ou mais de 20 ea, ela será válida, desde que também tenha pelo menos uma linha em que a quantidade seja inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="214bb-195">Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="214bb-195">Location directives</span></span>

<span data-ttu-id="214bb-196">Se você estiver usando dados padrão da Contoso, a consulta para a ação diretiva de localização não exigirá alterações.</span><span class="sxs-lookup"><span data-stu-id="214bb-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="214bb-197">No entanto, para verificar se as diretivas de localização capturarão os itens nas ordens de venda quando você aplicar o recurso em um ambiente que não seja da Contoso, crie uma nova diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="214bb-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="214bb-198">Para verificar as configurações no ambiente de demonstração, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="214bb-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="214bb-199">Vá para **Gerenciamento de depósito** \> **Configuração** \> **Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="214bb-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="214bb-200">No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="214bb-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="214bb-201">Selecione a diretiva de localização chamada *Separação 51*.</span><span class="sxs-lookup"><span data-stu-id="214bb-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="214bb-202">Na guia **Ações de Diretiva de Localização**, selecione a linha para a ação **Separação**.</span><span class="sxs-lookup"><span data-stu-id="214bb-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="214bb-203">Selecione **Editar consulta** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="214bb-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="214bb-204">Analise a consulta **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="214bb-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="214bb-205">Localize a linha em que o campo **Campo** está definido como *Local*.</span><span class="sxs-lookup"><span data-stu-id="214bb-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="214bb-206">Verifique se o campo **Critérios** está em branco (isto é, se não há restrições).</span><span class="sxs-lookup"><span data-stu-id="214bb-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="214bb-207">Cenário</span><span class="sxs-lookup"><span data-stu-id="214bb-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="214bb-208">Criar trabalho de separação de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="214bb-208">Create sales order picking work</span></span>

<span data-ttu-id="214bb-209">Antes da execução da separação direcionada pelo sistema, deve ser criado um trabalho de saída.</span><span class="sxs-lookup"><span data-stu-id="214bb-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="214bb-210">Para esse cenário, você criará quatro ordens de venda com base nas consultas de sequência de trabalho direcionadas pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="214bb-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="214bb-211">Você reservará quantidades de estoque para cada ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="214bb-212">Portanto, o estoque reservado não pode ser retirado do depósito para outras ordens, a menos que a reserva do estoque, ou parte dela, seja cancelada.</span><span class="sxs-lookup"><span data-stu-id="214bb-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="214bb-213">Você liberará cada ordem de venda para o depósito a fim de criar o trabalho de saída.</span><span class="sxs-lookup"><span data-stu-id="214bb-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="214bb-214">Ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="214bb-214">Sales order 1</span></span>

1. <span data-ttu-id="214bb-215">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="214bb-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="214bb-216">No Painel de Ações, selecione **Novo** para criar a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="214bb-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="214bb-217">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="214bb-218">Na seção **Cliente**, defina o campo **Conta do cliente** como *US-004*.</span><span class="sxs-lookup"><span data-stu-id="214bb-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="214bb-219">Na seção **Geral**, defina o campo **Depósito** como *51*.</span><span class="sxs-lookup"><span data-stu-id="214bb-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="214bb-220">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="214bb-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="214bb-221">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="214bb-222">Adicione uma linha à nova ordem de venda e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="214bb-223">**Número de item:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="214bb-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="214bb-224">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="214bb-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="214bb-225">No menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="214bb-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="214bb-226">Na página **Reserva**, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="214bb-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="214bb-227">Feche a página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="214bb-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="214bb-228">No Painel de Ações, na guia **Depósito**, selecione **Liberar para depósito** para criar trabalho para o depósito.</span><span class="sxs-lookup"><span data-stu-id="214bb-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="214bb-229">Você recebe mensagens informativas que mostram a ID da onda e as IDs de remessa que foram criadas para a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="214bb-230">Ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="214bb-230">Sales order 2</span></span>

1. <span data-ttu-id="214bb-231">No Painel de Ações, selecione **Novo** para criar a ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="214bb-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="214bb-232">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="214bb-233">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="214bb-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="214bb-234">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="214bb-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="214bb-235">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="214bb-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="214bb-236">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="214bb-237">Adicione uma linha à nova ordem de venda e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="214bb-238">**Número de item:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="214bb-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="214bb-239">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="214bb-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="214bb-240">Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="214bb-241">**Número de item:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="214bb-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="214bb-242">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="214bb-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="214bb-243">Reservar estoque para ambas as linhas.</span><span class="sxs-lookup"><span data-stu-id="214bb-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="214bb-244">Libere a ordem para o depósito.</span><span class="sxs-lookup"><span data-stu-id="214bb-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="214bb-245">Ordem de venda 3</span><span class="sxs-lookup"><span data-stu-id="214bb-245">Sales order 3</span></span>

1. <span data-ttu-id="214bb-246">No Painel de Ações, selecione **Novo** para criar a ordem de venda 3.</span><span class="sxs-lookup"><span data-stu-id="214bb-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="214bb-247">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="214bb-248">**Conta de cliente:** *US-009*</span><span class="sxs-lookup"><span data-stu-id="214bb-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="214bb-249">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="214bb-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="214bb-250">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="214bb-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="214bb-251">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="214bb-252">Adicione uma linha à nova ordem de venda e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="214bb-253">**Número de item:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="214bb-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="214bb-254">**Quantidade:** *7*</span><span class="sxs-lookup"><span data-stu-id="214bb-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="214bb-255">Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="214bb-256">**Número de item:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="214bb-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="214bb-257">**Quantidade:** *8*</span><span class="sxs-lookup"><span data-stu-id="214bb-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="214bb-258">Reservar estoque para ambas as linhas.</span><span class="sxs-lookup"><span data-stu-id="214bb-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="214bb-259">Libere a ordem para o depósito.</span><span class="sxs-lookup"><span data-stu-id="214bb-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="214bb-260">Ordem de venda 4</span><span class="sxs-lookup"><span data-stu-id="214bb-260">Sales order 4</span></span>

1. <span data-ttu-id="214bb-261">No Painel de Ações, selecione **Novo** para criar a ordem de venda 4.</span><span class="sxs-lookup"><span data-stu-id="214bb-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="214bb-262">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="214bb-263">**Conta de cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="214bb-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="214bb-264">**Depósito:** *51*</span><span class="sxs-lookup"><span data-stu-id="214bb-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="214bb-265">Selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="214bb-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="214bb-266">Anote o número da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="214bb-267">Adicione uma linha à nova ordem de venda e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="214bb-268">**Número de item:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="214bb-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="214bb-269">**Quantidade:** *25*</span><span class="sxs-lookup"><span data-stu-id="214bb-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="214bb-270">Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="214bb-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="214bb-271">**Número de item:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="214bb-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="214bb-272">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="214bb-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="214bb-273">Reservar estoque para ambas as linhas.</span><span class="sxs-lookup"><span data-stu-id="214bb-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="214bb-274">Libere a ordem para o depósito.</span><span class="sxs-lookup"><span data-stu-id="214bb-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="214bb-275">Obter IDs de trabalho para o trabalho que foi criado</span><span class="sxs-lookup"><span data-stu-id="214bb-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="214bb-276">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="214bb-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="214bb-277">Filtre o campo **Depósito** para que somente o trabalho do depósito *51* seja exibido.</span><span class="sxs-lookup"><span data-stu-id="214bb-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="214bb-278">Quatro IDs de trabalho devem ter sido criadas.</span><span class="sxs-lookup"><span data-stu-id="214bb-278">Four work IDs should have been created.</span></span> <span data-ttu-id="214bb-279">Anote a ID de trabalho de cada ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="214bb-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="214bb-280">ID da Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="214bb-280">Sales order ID</span></span> | <span data-ttu-id="214bb-281">ID do Trabalho</span><span class="sxs-lookup"><span data-stu-id="214bb-281">Work ID</span></span> | <span data-ttu-id="214bb-282">Quantidade de trabalho</span><span class="sxs-lookup"><span data-stu-id="214bb-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="214bb-283">Ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="214bb-283">Sales Order 1</span></span> | <span data-ttu-id="214bb-284">ID de trabalho 1</span><span class="sxs-lookup"><span data-stu-id="214bb-284">Work ID 1</span></span> | <span data-ttu-id="214bb-285">20 ea</span><span class="sxs-lookup"><span data-stu-id="214bb-285">20 ea</span></span> |
    | <span data-ttu-id="214bb-286">Ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="214bb-286">Sales Order 2</span></span> | <span data-ttu-id="214bb-287">ID de trabalho 2</span><span class="sxs-lookup"><span data-stu-id="214bb-287">Work ID 2</span></span> | <span data-ttu-id="214bb-288">6 ea (soma das duas linhas)</span><span class="sxs-lookup"><span data-stu-id="214bb-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="214bb-289">Ordem de venda 3</span><span class="sxs-lookup"><span data-stu-id="214bb-289">Sales Order 3</span></span> | <span data-ttu-id="214bb-290">ID de trabalho 3</span><span class="sxs-lookup"><span data-stu-id="214bb-290">Work ID 3</span></span> | <span data-ttu-id="214bb-291">15 ea (soma das duas linhas)</span><span class="sxs-lookup"><span data-stu-id="214bb-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="214bb-292">Ordem de venda 4</span><span class="sxs-lookup"><span data-stu-id="214bb-292">Sales Order 4</span></span> | <span data-ttu-id="214bb-293">ID de trabalho 4</span><span class="sxs-lookup"><span data-stu-id="214bb-293">Work ID 4</span></span> | <span data-ttu-id="214bb-294">35 ea (soma das duas linhas)</span><span class="sxs-lookup"><span data-stu-id="214bb-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="214bb-295">Antes de executar o fluxo no dispositivo móvel, verifique se somente o trabalho recém-criado está com o status *Aberto* para o depósito *51* e o tipo de ordem de trabalho de *Ordem de venda*.</span><span class="sxs-lookup"><span data-stu-id="214bb-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="214bb-296">Caso contrário, os resultados do teste podem variar, pois a separação direta do sistema incluirá todo o trabalho elegível.</span><span class="sxs-lookup"><span data-stu-id="214bb-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="214bb-297">Vá para **Gerenciamento de depósito \> Trabalho \> Saída \> Trabalho de venda aberto**.</span><span class="sxs-lookup"><span data-stu-id="214bb-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="214bb-298">Na grade **Trabalho de venda aberto**, filtre o campo **Depósito** para que somente o trabalho do depósito *51* seja exibido.</span><span class="sxs-lookup"><span data-stu-id="214bb-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="214bb-299">Confirme se aparecem apenas as quatro IDs de trabalho criadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="214bb-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="214bb-300">Feche a página **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="214bb-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="214bb-301">Execução do fluxo do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="214bb-301">Mobile device flow execution</span></span>

<span data-ttu-id="214bb-302">Com base na configuração, o sistema alimentará o trabalho do usuário que é classificado da quantidade da linha de trabalho superior à inferior.</span><span class="sxs-lookup"><span data-stu-id="214bb-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="214bb-303">A quantidade em cada linha será inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="214bb-304">Lembre-se de que esta configuração capturará trabalhos com pelo menos uma linha em que a quantidade seja inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="214bb-305">Portanto, se o trabalho tiver outra linha em que a quantidade seja exatamente 20 ea ou superior a 20 ea, ela também será válida.</span><span class="sxs-lookup"><span data-stu-id="214bb-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="214bb-306">Aplicativo móvel</span><span class="sxs-lookup"><span data-stu-id="214bb-306">Mobile app</span></span>

1. <span data-ttu-id="214bb-307">Entre no aplicativo do depósito como um usuário no depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="214bb-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="214bb-308">Vá para **Saída \> Separação de Venda - Sistema**.</span><span class="sxs-lookup"><span data-stu-id="214bb-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="214bb-309">A etapa de separação para a ID de trabalho *4* é apresentada.</span><span class="sxs-lookup"><span data-stu-id="214bb-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="214bb-310">Essa ID de trabalho é apresentada primeiro por causa da configuração da ordem de consulta direcionada pelo sistema, na qual você especificou que o trabalho deve ser sequenciado com base na quantidade de linha de trabalho decrescente.</span><span class="sxs-lookup"><span data-stu-id="214bb-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="214bb-311">Conclua a separação necessária e coloque-a para fechar a ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="214bb-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="214bb-312">Em seguida, a ID de trabalho *3* é apresentada.</span><span class="sxs-lookup"><span data-stu-id="214bb-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="214bb-313">Uma das linhas de trabalho é a próxima na sequência, com base na quantidade da linha de trabalho.</span><span class="sxs-lookup"><span data-stu-id="214bb-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="214bb-314">Conclua a separação e coloque-a para fechar a ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="214bb-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="214bb-315">Em seguida, a ID de trabalho *2* é apresentada.</span><span class="sxs-lookup"><span data-stu-id="214bb-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="214bb-316">A linha de separação deste trabalho é a próxima na sequência.</span><span class="sxs-lookup"><span data-stu-id="214bb-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="214bb-317">Conclua a separação e coloque-a para fechar a ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="214bb-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="214bb-318">Nenhum trabalho adicional deve ser apresentado a você.</span><span class="sxs-lookup"><span data-stu-id="214bb-318">No further work should be presented to you.</span></span> <span data-ttu-id="214bb-319">A ID de trabalho *1* não está qualificada para este item de menu de dispositivo móvel, pois a consulta especifica que os cabeçalhos de trabalho serão considerados somente se a quantidade nas linhas de trabalho for inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="214bb-320">Dicas</span><span class="sxs-lookup"><span data-stu-id="214bb-320">Tips</span></span>

<span data-ttu-id="214bb-321">As consultas de sequência de trabalho direcionadas pelo sistema são *inclusivas*.</span><span class="sxs-lookup"><span data-stu-id="214bb-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="214bb-322">É importante lembrar desse fato para algumas configurações.</span><span class="sxs-lookup"><span data-stu-id="214bb-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="214bb-323">Por exemplo, você deseja que um item de menu específico processe apenas o trabalho em que a unidade de trabalho seja *ea* e especifica essa restrição na guia **Intervalo** da consulta.</span><span class="sxs-lookup"><span data-stu-id="214bb-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="214bb-324">Nesse caso, todos os trabalhos em que pelo menos uma linha de trabalho tenha a unidade de trabalho definida como *ea* serão alimentados para o trabalhador.</span><span class="sxs-lookup"><span data-stu-id="214bb-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="214bb-325">Portanto, esse trabalho também podem incluir trabalho em que as linhas de trabalho tenham uma unidade de trabalho diferente de *ea* (como *caixa* ou *palete*).</span><span class="sxs-lookup"><span data-stu-id="214bb-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="214bb-326">A consulta excluirá o trabalho apenas quando nenhuma linha de trabalho tiver a unidade de trabalho definida como *ea*.</span><span class="sxs-lookup"><span data-stu-id="214bb-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="214bb-327">Portanto, no exemplo desse cenário, a ID de trabalho *4* também foi capturada pela consulta.</span><span class="sxs-lookup"><span data-stu-id="214bb-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="214bb-328">Quando ela foi criada, duas linhas foram adicionadas: uma para 25 ea e outra para 10 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="214bb-329">O trabalho ainda foi apresentado ao usuário porque pelo menos uma linha de trabalho tem uma quantidade inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="214bb-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="214bb-330">Dependendo do cenário, você pode evitar esse comportamento usando pausas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="214bb-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>
