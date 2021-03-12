---
title: Posição de cluster completa
description: Este tópico fornece informações sobre o recurso Posição de cluster completa. Este recurso oferece uma alternativa a uma aplicação mais rígida de regras de intervalo de trabalho quando a separação de cluster é usada, pois permite uma maior margem de erro nas restrições volumétricas de contêineres ou totes.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9c90380cb5d109e331a2552ba779525b66d10fa6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001090"
---
# <a name="cluster-position-full"></a><span data-ttu-id="25ba3-104">Posição de cluster completa</span><span class="sxs-lookup"><span data-stu-id="25ba3-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25ba3-105">O recurso *Posição de cluster completa* oferece uma alternativa a uma aplicação mais rígida de regras de intervalo de trabalho quando a separação de cluster é usada, pois permite uma maior margem de erro nas restrições volumétricas de contêineres ou totes.</span><span class="sxs-lookup"><span data-stu-id="25ba3-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="25ba3-106">Em um cenário comum, nem todos os itens de uma ordem de serviço cabem em um contêiner selecionado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="25ba3-107">Os trabalhadores de depósito que são a separação de cluster têm algumas opções neste cenário: eles devem alterar para um tamanho de contêiner maior ou trabalhar com seu supervisor para apresentar uma solução diferente.</span><span class="sxs-lookup"><span data-stu-id="25ba3-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="25ba3-108">Este recurso introduz a capacidade de executar o botão **Completo** em uma das unidades de trabalho em um cluster.</span><span class="sxs-lookup"><span data-stu-id="25ba3-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="25ba3-109">Em versões anteriores, essa opção estava disponível apenas para a separação de ordem normal, não para a separação de cluster.</span><span class="sxs-lookup"><span data-stu-id="25ba3-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="25ba3-110">No entanto, este recurso difere do botão **Completo** padrão, pois cancela o trabalho restante.</span><span class="sxs-lookup"><span data-stu-id="25ba3-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="25ba3-111">Ele não sugere que o usuário adicione outro compartimento ao mesmo cluster e não cria um novo trabalho automaticamente.</span><span class="sxs-lookup"><span data-stu-id="25ba3-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="25ba3-112">Ativar o recurso Posição de cluster completa</span><span class="sxs-lookup"><span data-stu-id="25ba3-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="25ba3-113">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="25ba3-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="25ba3-114">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="25ba3-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="25ba3-115">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="25ba3-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="25ba3-116">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="25ba3-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="25ba3-117">**Nome do recurso:** *Posição de cluster completa*</span><span class="sxs-lookup"><span data-stu-id="25ba3-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="25ba3-118">Configurar</span><span class="sxs-lookup"><span data-stu-id="25ba3-118">Setup</span></span>

<span data-ttu-id="25ba3-119">Esta seção fornece diretrizes e um exemplo que mostra como configurar e usar o recurso *Posição de cluster completa*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="25ba3-120">Disponibilizar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="25ba3-120">Make sample data available</span></span>

<span data-ttu-id="25ba3-121">Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="25ba3-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="25ba3-122">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="25ba3-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="25ba3-123">Você também pode usar o cenário de exemplo como orientação para trabalhar com esse recurso em um sistema de produção.</span><span class="sxs-lookup"><span data-stu-id="25ba3-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="25ba3-124">No entanto, nesse caso, você deve substituir seus valores pelas configurações descritas aqui.</span><span class="sxs-lookup"><span data-stu-id="25ba3-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="25ba3-125">Perfis de cluster</span><span class="sxs-lookup"><span data-stu-id="25ba3-125">Cluster profiles</span></span>

<span data-ttu-id="25ba3-126">Você deve especificar se as IDs de cluster são geradas automaticamente, quantas posições são usadas, quando os clusters são divididos e como o trabalho de separação é sequenciado e verificado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="25ba3-127">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Perfis de cluster**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="25ba3-128">No painel de lista, selecione o registro **Criar Cluster**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="25ba3-129">Na FastTab **Geral**, verifique os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="25ba3-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="25ba3-130">**Gerar ID do cluster:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="25ba3-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="25ba3-131">**Ativar posições:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="25ba3-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="25ba3-132">**Número de posições:** *2*</span><span class="sxs-lookup"><span data-stu-id="25ba3-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="25ba3-133">**Nome da posição:** *Numérica*</span><span class="sxs-lookup"><span data-stu-id="25ba3-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="25ba3-134">**Dividir cluster em:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="25ba3-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="25ba3-135">**Tipo de verificação de classificação:** *Verificação da posição*</span><span class="sxs-lookup"><span data-stu-id="25ba3-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="25ba3-136">Na FastTab **Classificação de cluster**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="25ba3-137">A grade deve estar em branco (isto é, ela não deve conter linhas).</span><span class="sxs-lookup"><span data-stu-id="25ba3-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="25ba3-138">Modelos do trabalho</span><span class="sxs-lookup"><span data-stu-id="25ba3-138">Work templates</span></span>

<span data-ttu-id="25ba3-139">Você deve definir como o trabalho de separação para a separação de cluster é criado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="25ba3-140">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="25ba3-141">Na parte superior da página, defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="25ba3-142">Verifique se os seguintes modelos de trabalho dos dados de demonstração estão listados.</span><span class="sxs-lookup"><span data-stu-id="25ba3-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="25ba3-143">Se eles não estiverem disponíveis, não será possível concluir o cenário.</span><span class="sxs-lookup"><span data-stu-id="25ba3-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="25ba3-144">Preparação de OV 61</span><span class="sxs-lookup"><span data-stu-id="25ba3-144">61 SO Stage</span></span>
    - <span data-ttu-id="25ba3-145">Separação de cluster de OV 61</span><span class="sxs-lookup"><span data-stu-id="25ba3-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="25ba3-146">Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="25ba3-146">Location directives</span></span>

<span data-ttu-id="25ba3-147">Você deve especificar de onde os itens são separados e onde eles são colocados.</span><span class="sxs-lookup"><span data-stu-id="25ba3-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="25ba3-148">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="25ba3-149">No cabeçalho da lista, defina o campo **Tipo de ordem de serviço** como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="25ba3-150">Verifique se as seguintes diretivas de ordens de venda dos dados de demonstração estão listadas.</span><span class="sxs-lookup"><span data-stu-id="25ba3-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="25ba3-151">Se eles não estiverem disponíveis, não será possível concluir o cenário.</span><span class="sxs-lookup"><span data-stu-id="25ba3-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="25ba3-152">Separação de cluster de 61</span><span class="sxs-lookup"><span data-stu-id="25ba3-152">61 Cluster pick</span></span>
    - <span data-ttu-id="25ba3-153">Ordem de separação de OV 61</span><span class="sxs-lookup"><span data-stu-id="25ba3-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="25ba3-154">Itens de menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="25ba3-154">Mobile device menu items</span></span>

<span data-ttu-id="25ba3-155">Você deve configurar um item de menu do dispositivo móvel para usar o trabalho existente que é direcionado pela separação de cluster.</span><span class="sxs-lookup"><span data-stu-id="25ba3-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="25ba3-156">No item de menu do dispositivo móvel para separação de cluster, o parâmetro **Permitir divisão de trabalho** deve ser ativado e a classe de trabalho *Separação de OV* deve ser adicionada.</span><span class="sxs-lookup"><span data-stu-id="25ba3-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="25ba3-157">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="25ba3-158">No painel de lista, selecione o registro **Criar Separação de Cluster**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="25ba3-159">Selecione **Editar** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="25ba3-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="25ba3-160">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="25ba3-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="25ba3-161">**Direcionado por:** *Separação de cluster*</span><span class="sxs-lookup"><span data-stu-id="25ba3-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="25ba3-162">**Gerar placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="25ba3-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="25ba3-163">**Permitir divisão de trabalho:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="25ba3-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="25ba3-164">**ID do perfil do cluster:** *Criar Cluster*</span><span class="sxs-lookup"><span data-stu-id="25ba3-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="25ba3-165">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="25ba3-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="25ba3-166">Na FastTab **Classes de trabalho**, adicione as duas linhas a seguir, conforme necessário:</span><span class="sxs-lookup"><span data-stu-id="25ba3-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="25ba3-167">Linha 1 (normalmente presente em dados de demonstração):</span><span class="sxs-lookup"><span data-stu-id="25ba3-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="25ba3-168">**ID da classe de trabalho:** *Vendas*</span><span class="sxs-lookup"><span data-stu-id="25ba3-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="25ba3-169">**Tipo de ordem de serviço:** *Ordens de venda*</span><span class="sxs-lookup"><span data-stu-id="25ba3-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="25ba3-170">Linha 2 (provavelmente ausente em dados de demonstração):</span><span class="sxs-lookup"><span data-stu-id="25ba3-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="25ba3-171">**ID da classe de trabalho:** *Separação de OV*</span><span class="sxs-lookup"><span data-stu-id="25ba3-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="25ba3-172">**Tipo de ordem de serviço:** *Ordens de venda*</span><span class="sxs-lookup"><span data-stu-id="25ba3-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="25ba3-173">Vá para **Configuração de confirmação de trabalho** no Painel de Ações.</span><span class="sxs-lookup"><span data-stu-id="25ba3-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="25ba3-174">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-174">Select **Edit**.</span></span>
1. <span data-ttu-id="25ba3-175">Insira os seguintes valores na linha da grade.</span><span class="sxs-lookup"><span data-stu-id="25ba3-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="25ba3-176">**Tipo de trabalho** - *Separar*</span><span class="sxs-lookup"><span data-stu-id="25ba3-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="25ba3-177">**Confirmação do produto** - *Marque a caixa de seleção*</span><span class="sxs-lookup"><span data-stu-id="25ba3-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="25ba3-178">Selecione **Salvar** no Painel de Ações e feche a página.</span><span class="sxs-lookup"><span data-stu-id="25ba3-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="25ba3-179">Criar trabalho de separação</span><span class="sxs-lookup"><span data-stu-id="25ba3-179">Create picking work</span></span>

<span data-ttu-id="25ba3-180">Antes de iniciar a separação de cluster, você deve criar um trabalho de saída.</span><span class="sxs-lookup"><span data-stu-id="25ba3-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="25ba3-181">O perfil de cluster criado anteriormente especifica duas posições de cluster.</span><span class="sxs-lookup"><span data-stu-id="25ba3-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="25ba3-182">Portanto, pelo menos duas IDs de trabalho devem ser criadas para a separação de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="25ba3-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="25ba3-183">Neste cenário, as transações ocorrerão no depósito *61* e usarão os itens *L0101* e *T0100*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="25ba3-184">Os dados de demonstração devem ter um estoque disponível suficiente desses itens.</span><span class="sxs-lookup"><span data-stu-id="25ba3-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="25ba3-185">Verifique se você tem estoque suficiente para concluir as transações.</span><span class="sxs-lookup"><span data-stu-id="25ba3-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="25ba3-186">Criar ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="25ba3-186">Create sales order 1</span></span>

1. <span data-ttu-id="25ba3-187">Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="25ba3-188">Selecione **Novo** para criar a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="25ba3-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="25ba3-189">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="25ba3-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="25ba3-190">**Conta de cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="25ba3-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="25ba3-191">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="25ba3-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="25ba3-192">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-192">Select **OK**.</span></span>
1. <span data-ttu-id="25ba3-193">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="25ba3-193">The new sales order is opened.</span></span> <span data-ttu-id="25ba3-194">Na guia rápida **Linhas da ordem de venda**, adicione uma linha que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25ba3-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="25ba3-195">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="25ba3-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="25ba3-196">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="25ba3-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="25ba3-197">Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="25ba3-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="25ba3-198">Na FastTab **Linhas da ordem de venda**, adicione uma segunda linha que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25ba3-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="25ba3-199">**Número de item:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="25ba3-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="25ba3-200">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="25ba3-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="25ba3-201">Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="25ba3-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="25ba3-202">Para cada linha que você acabou de adicionar, siga estas etapas para reservar o estoque:</span><span class="sxs-lookup"><span data-stu-id="25ba3-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="25ba3-203">Selecione a linha a ser reservada.</span><span class="sxs-lookup"><span data-stu-id="25ba3-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="25ba3-204">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="25ba3-205">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="25ba3-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="25ba3-206">Feche a página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="25ba3-207">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="25ba3-208">Quando a liberação é concluída, você recebe mensagens informativas que mostram as IDs do ciclo e da carga que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="25ba3-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="25ba3-209">Criar ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="25ba3-209">Create sales order 2</span></span>

1. <span data-ttu-id="25ba3-210">Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="25ba3-211">Selecione **Novo** para criar a ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="25ba3-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="25ba3-212">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="25ba3-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="25ba3-213">**Conta de cliente:** *US-011*</span><span class="sxs-lookup"><span data-stu-id="25ba3-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="25ba3-214">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="25ba3-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="25ba3-215">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-215">Select **OK**.</span></span>
1. <span data-ttu-id="25ba3-216">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="25ba3-216">The new sales order is opened.</span></span> <span data-ttu-id="25ba3-217">Na guia rápida **Linhas da ordem de venda**, adicione uma linha que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25ba3-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="25ba3-218">**Número de item:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="25ba3-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="25ba3-219">**Quantidade:** *20*</span><span class="sxs-lookup"><span data-stu-id="25ba3-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="25ba3-220">Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="25ba3-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="25ba3-221">Na FastTab **Linhas da ordem de venda**, adicione uma segunda linha que tenha as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="25ba3-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="25ba3-222">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="25ba3-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="25ba3-223">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="25ba3-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="25ba3-224">Na FastTab **Detalhes da linha**, na guia **Entrega**, defina o campo **Data de remessa confirmada** como a data de hoje.</span><span class="sxs-lookup"><span data-stu-id="25ba3-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="25ba3-225">Para cada linha que você acabou de adicionar, siga estas etapas para reservar o estoque:</span><span class="sxs-lookup"><span data-stu-id="25ba3-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="25ba3-226">Selecione a linha a ser reservada.</span><span class="sxs-lookup"><span data-stu-id="25ba3-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="25ba3-227">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="25ba3-228">Na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar o estoque.</span><span class="sxs-lookup"><span data-stu-id="25ba3-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="25ba3-229">Feche a página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="25ba3-230">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="25ba3-231">Quando a liberação é concluída, você recebe mensagens informativas que mostram as IDs do ciclo e da carga que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="25ba3-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="25ba3-232">Obter IDs de trabalho e números das placas de licença</span><span class="sxs-lookup"><span data-stu-id="25ba3-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="25ba3-233">Duas IDs de trabalho devem ter sido criadas, cada uma com duas linhas de separação.</span><span class="sxs-lookup"><span data-stu-id="25ba3-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="25ba3-234">Siga estas etapas para localizar as IDs de trabalho e as atribuições das placas de licença.</span><span class="sxs-lookup"><span data-stu-id="25ba3-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="25ba3-235">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="25ba3-236">Na grade **Visão geral**, procure na coluna **Número da ordem** as duas ordens de venda recém-criadas.</span><span class="sxs-lookup"><span data-stu-id="25ba3-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="25ba3-237">Para cada ordem de venda, anote a ID de trabalho correspondente.</span><span class="sxs-lookup"><span data-stu-id="25ba3-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="25ba3-238">Selecione a linha de cada ordem de venda para mostrar as informações relacionadas na grade **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="25ba3-239">Anote o local de onde cada item será separado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="25ba3-240">Vá para **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="25ba3-241">No Painel de Ações, selecione **Dimensões** para abrir a caixa de diálogo **Exibição de dimensão**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="25ba3-242">Verifique se as caixas de seleção **Placa de licença**, **Depósito** e **Número do item** estão marcadas e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="25ba3-243">No painel **Filtro**, defina os seguintes filtros:</span><span class="sxs-lookup"><span data-stu-id="25ba3-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="25ba3-244">**Número do item** – **é um de** – *L0101* e *T100*</span><span class="sxs-lookup"><span data-stu-id="25ba3-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="25ba3-245">**Depósito** – **começa com** – *61*</span><span class="sxs-lookup"><span data-stu-id="25ba3-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="25ba3-246">Anote os valores da **Placa de licença** que são exibidos.</span><span class="sxs-lookup"><span data-stu-id="25ba3-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="25ba3-247">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="25ba3-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="25ba3-248">Execução do fluxo do dispositivo móvel – Configuração de confirmação de trabalho para o produto</span><span class="sxs-lookup"><span data-stu-id="25ba3-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="25ba3-249">Entre no aplicativo do depósito como um usuário no depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="25ba3-250">Vá para **Saída \> Criar separação de cluster**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="25ba3-251">A página **TAREFA: Atribuir Trabalho ao Cluster** será exibida.</span><span class="sxs-lookup"><span data-stu-id="25ba3-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="25ba3-252">Insira a ID de trabalho da ordem de venda 1 para atribuí-la à posição de cluster 1.</span><span class="sxs-lookup"><span data-stu-id="25ba3-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="25ba3-253">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-254">Insira a ID de trabalho da ordem de venda 2 para atribuí-la à posição de cluster 2.</span><span class="sxs-lookup"><span data-stu-id="25ba3-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="25ba3-255">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="25ba3-256">A página **TAREFA: Criar Separação de Cluster: Separar** será exibida e mostrará *Item L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="25ba3-257">Como o perfil do cluster definiu o número de posições como 2, o sistema automaticamente direciona você para a primeira separação consolidada: dois paletes (PL) do item *L0101*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="25ba3-258">A qualquer momento durante as etapas a seguir, você pode selecionar a guia **Detalhes** para exibir informações adicionais sobre a tarefa, como o local de separação.</span><span class="sxs-lookup"><span data-stu-id="25ba3-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="25ba3-259">Defina o campo **ITEM** como *L0101*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="25ba3-260">Isso confirma o número do item, que é necessário para este item de menu (você configurou isso anteriormente selecionando **Configuração de confirmação de trabalho** na página **Item de menu do dispositivo móvel** quando criou esse item de menu).</span><span class="sxs-lookup"><span data-stu-id="25ba3-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="25ba3-261">Insira o número da placa de licença associado ao item no local que está sendo separado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="25ba3-262">Você separará dois paletes.</span><span class="sxs-lookup"><span data-stu-id="25ba3-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="25ba3-263">Defina o campo **LP** como *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="25ba3-264">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="25ba3-265">A página **TAREFA: Classificar: Criar Separação de Cluster** será exibida.</span><span class="sxs-lookup"><span data-stu-id="25ba3-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="25ba3-266">Aqui, você classificará os dois paletes separados em uma posição de separação.</span><span class="sxs-lookup"><span data-stu-id="25ba3-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="25ba3-267">Essa posição pode ser um tote ou contêiner usado para separar o estoque separado por ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="25ba3-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="25ba3-268">Veja os detalhes mostrados para o item (*L0101*) e a quantidade (*20* ea) que serão classificados na posição 1 (para a ordem de venda 1).</span><span class="sxs-lookup"><span data-stu-id="25ba3-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="25ba3-269">Defina o campo **POSITION NA** como *1*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="25ba3-270">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-271">Veja os detalhes mostrados para o item (*L0101*) e a quantidade (*20* ea) que serão classificados na posição 2 (para a ordem de venda 2).</span><span class="sxs-lookup"><span data-stu-id="25ba3-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="25ba3-272">Defina o campo **POSITION NA** como *2*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="25ba3-273">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="25ba3-274">A página **TAREFA: Criar Separação de Cluster: Separar** será exibida e mostrará *Item T0100 7 ea*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="25ba3-275">Neste cenário, a posição 1 não pode aceitar a quantidade total de itens que devem ser separados para atender à ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="25ba3-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="25ba3-276">Uma posição deve ser marcada como completa.</span><span class="sxs-lookup"><span data-stu-id="25ba3-276">A position must be marked as full.</span></span> <span data-ttu-id="25ba3-277">Neste cenário, você fará uma separação parcial do segundo item.</span><span class="sxs-lookup"><span data-stu-id="25ba3-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="25ba3-278">O segundo item será parcialmente separado para a posição 1 e um novo trabalho será criado para separar a quantidade restante a fim de atender à ordem.</span><span class="sxs-lookup"><span data-stu-id="25ba3-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="25ba3-279">Selecione o botão de menu (também chamado de hambúrguer ou botão de hambúrguer) e, em seguida, selecione **Posição completa**.</span><span class="sxs-lookup"><span data-stu-id="25ba3-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="25ba3-280">Identifique a posição completa e selecione *1*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="25ba3-281">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-282">Insira a quantidade de separação que ainda pode ser separada na posição 1.</span><span class="sxs-lookup"><span data-stu-id="25ba3-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="25ba3-283">O sistema pode determinar qual número de item está sendo separado.</span><span class="sxs-lookup"><span data-stu-id="25ba3-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="25ba3-284">Insira *2*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-284">Enter *2*.</span></span>
1. <span data-ttu-id="25ba3-285">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-286">Confirme o número do item para concluir a separação do item restante na posição 2.</span><span class="sxs-lookup"><span data-stu-id="25ba3-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="25ba3-287">Defina o campo **ITEM** como *T0100*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="25ba3-288">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-289">Insira a placa de licença da qual o item está sendo separado, definindo o campo **LP** como *LPREPL04*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="25ba3-290">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-291">Veja os detalhes mostrados para o item (*T0100*) e a quantidade (*2* ea) que serão classificados na posição 2 (para a ordem de venda 2).</span><span class="sxs-lookup"><span data-stu-id="25ba3-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="25ba3-292">Defina o campo **POSITION NA** como *2*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="25ba3-293">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="25ba3-294">Veja os detalhes mostrados para o item (*T0100*) e a quantidade (*2* ea) que serão classificados na posição 1 (para a ordem de venda 1).</span><span class="sxs-lookup"><span data-stu-id="25ba3-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="25ba3-295">Defina o campo **POSITION NA** como *1*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="25ba3-296">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="25ba3-297">A página **TAREFA: Criar Separação de Cluster: Colocar** será exibida.</span><span class="sxs-lookup"><span data-stu-id="25ba3-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="25ba3-298">Neste cenário, a separação de cluster foi concluída e o usuário é direcionado para armazenar os itens separados da posição 1 e da posição 2 no local de preparo *STAGE01*.</span><span class="sxs-lookup"><span data-stu-id="25ba3-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="25ba3-299">Revise as informações na página.</span><span class="sxs-lookup"><span data-stu-id="25ba3-299">Review the information on the page.</span></span> <span data-ttu-id="25ba3-300">Ela mostra que uma quantidade total de *44* será colocada no local de preparo.</span><span class="sxs-lookup"><span data-stu-id="25ba3-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="25ba3-301">Selecione **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="25ba3-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="25ba3-302">Você recebe uma mensagem "Cluster Concluído".</span><span class="sxs-lookup"><span data-stu-id="25ba3-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="25ba3-303">Agora você pode usar o item de menu **Separação de Venda** para separar a quantidade restante.</span><span class="sxs-lookup"><span data-stu-id="25ba3-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="25ba3-304">Em seguida, você pode usar o item de menu **Carregamento de venda** para mover os itens do local de preparo para a doca de carga.</span><span class="sxs-lookup"><span data-stu-id="25ba3-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>
