---
title: Agrupamento de linhas de separação
description: Este tópico oferece uma visão geral de agrupamento de linhas de separação.
author: Mirzaab
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: fe0e63ef742b7bfd09684a94d273a1841d24599c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828261"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="fe1ae-103">Agrupamento de linhas de separação</span><span class="sxs-lookup"><span data-stu-id="fe1ae-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fe1ae-104">O agrupamento de linhas de separação permite que várias linhas de trabalho que têm o mesmo item e local podem ser combinadas em uma única separação que é apresentada ao usuário em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="fe1ae-105">Portanto, os trabalhadores de depósito podem receber as instruções mais eficientes possíveis, mas a separação necessária de linhas de trabalho (para diferentes contêineres, ordens etc.) ainda pode ser mantida no sistema.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="fe1ae-106">Ativar o recurso de agrupamento de linhas de separação</span><span class="sxs-lookup"><span data-stu-id="fe1ae-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="fe1ae-107">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="fe1ae-108">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fe1ae-109">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fe1ae-110">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="fe1ae-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fe1ae-111">**Nome do recurso:** *Agrupamento de linhas de separação*</span><span class="sxs-lookup"><span data-stu-id="fe1ae-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="fe1ae-112">Configurar agrupamento de linhas de separação</span><span class="sxs-lookup"><span data-stu-id="fe1ae-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="fe1ae-113">Criar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="fe1ae-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="fe1ae-114">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fe1ae-115">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fe1ae-116">No campo **Nome do item de menu** digite *Separação de linhas do grupo de vendas*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="fe1ae-117">No campo **Título**, digite *Separação de linhas do grupo de vendas*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="fe1ae-118">Esse título será exibido no menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="fe1ae-119">No campo **Modo**, selecione *Trabalho*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="fe1ae-120">Defina a opção **Usar trabalho existente** para *Sim*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="fe1ae-121">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fe1ae-122">No campo **Direcionado por**, selecione *Direcionado pelo usuário*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="fe1ae-123">Defina a opção **Gerar placa de licença** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="fe1ae-124">Defina a opção **Separação por grupo** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="fe1ae-125">Aceite os valores padrão para as opções restantes.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="fe1ae-126">Siga estas etapas para configurar as classes de trabalho válidas para o item de menu do dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="fe1ae-127">Na FastTab **Classes de trabalho**, escolha **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="fe1ae-128">No campo **ID da classe de trabalho**, você pode selecionar *Vendas* ou *Separação de OV*, dependendo do depósito que você usará.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="fe1ae-129">Para esse cenário, selecione *Separação de OV*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="fe1ae-130">O campo **Tipo de ordem de serviço** é automaticamente definido como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="fe1ae-131">Configura um menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="fe1ae-131">Set up a mobile device menu</span></span>

<span data-ttu-id="fe1ae-132">Siga estas etapas para adicionar o item de menu recém-criado ao menu **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="fe1ae-133">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="fe1ae-134">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fe1ae-135">O painel de lista mostra todos os menus de dispositivos móveis existentes.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="fe1ae-136">Selecione *Saída* na lista.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="fe1ae-137">Na lista **Menus e itens de menu disponíveis**, localize e selecione o item de menu *Separação de linhas do grupo de vendas* que você criou.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="fe1ae-138">Selecione o botão de seta para a direita a fim de mover o item de menu *Separação de linhas do grupo de vendas* para a lista **Estrutura de menu**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="fe1ae-139">Use os botões de seta para cima e para baixo para mover o item de menu para a posição desejada na estrutura de menu.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="fe1ae-140">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="fe1ae-141">Configurar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="fe1ae-141">Set up a work template</span></span>

1. <span data-ttu-id="fe1ae-142">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="fe1ae-143">No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="fe1ae-144">Na grade **Visão geral**, localize e selecione o modelo de trabalho que deve ser usado com essa função.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="fe1ae-145">Para esse cenário, selecione o modelo *51 Estágio de separação*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="fe1ae-146">No Painel de Ações, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="fe1ae-147">Na caixa de diálogo do editor, na guia **Classificação**, selecione **Adicionar** e defina os seguintes valores para a nova linha:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="fe1ae-148">No campo **Tabela** coluna, selecione *Transações de trabalho temporário*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="fe1ae-149">Na coluna **Tabela derivada**, selecione *Transações de trabalho temporário*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="fe1ae-150">Na coluna **Campo**, selecione *Número do item*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="fe1ae-151">Na coluna **Direção da pesquisa**, selecione *Crescente*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="fe1ae-152">Selecione **OK** para fechar a caixa de diálogo e salvar a seleção.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="fe1ae-153">Você receberá a seguinte mensagem: "O agrupamento será redefinido. Deseja continuar?"</span><span class="sxs-lookup"><span data-stu-id="fe1ae-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="fe1ae-154">Selecione **Sim** para continuar.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe1ae-155">Para que a funcionalidade agrupamento de linhas de separação funcione, as linhas de trabalho devem ser classificadas por ID do item.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="fe1ae-156">Se as linhas que têm os mesmos itens não forem sequenciadas uma após a outra, elas não serão agrupadas.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="fe1ae-157">Exemplo</span><span class="sxs-lookup"><span data-stu-id="fe1ae-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="fe1ae-158">Criar trabalho de separação</span><span class="sxs-lookup"><span data-stu-id="fe1ae-158">Create picking work</span></span>

<span data-ttu-id="fe1ae-159">Antes de configurar o agrupamento de linhas de separação, você deve criar algum trabalho de saída qualificado.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="fe1ae-160">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fe1ae-161">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="fe1ae-162">No campo **Conta do cliente**, selecione *US-004*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="fe1ae-163">Na Guia Rápida **Geral**, no campo **Depósito**, selecione *51*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="fe1ae-164">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-164">Select **OK**.</span></span>
1. <span data-ttu-id="fe1ae-165">Na FastTab **Linhas de ordem de venda**, adicione as seguintes seis linhas:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="fe1ae-166">**Linha 1:** No campo **Número do item**, selecione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="fe1ae-167">No campo **Quantidade**, insira *3*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="fe1ae-168">**Linha 2:** No campo **Número do item**, selecione *M9201*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="fe1ae-169">No campo **Quantidade**, insira *3*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="fe1ae-170">**Linha 3:** No campo **Número do item**, selecione *M9202*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="fe1ae-171">No campo **Quantidade**, insira *2*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="fe1ae-172">**Linha 4:** No campo **Número do item**, selecione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="fe1ae-173">No campo **Quantidade**, insira *1*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="fe1ae-174">**Linha 5:** No campo **Número do item**, selecione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="fe1ae-175">No campo **Quantidade**, insira *3*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="fe1ae-176">**Linha 6:** No campo **Número do item**, selecione *M9202*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="fe1ae-177">No campo **Quantidade**, insira *7*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="fe1ae-178">Aqui está um resumo das quantidades totais de cada item:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="fe1ae-179">**Item M9200:** *7* cada</span><span class="sxs-lookup"><span data-stu-id="fe1ae-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="fe1ae-180">**Item M9201:** *3* cada</span><span class="sxs-lookup"><span data-stu-id="fe1ae-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="fe1ae-181">**Item M9202:** *9* cada</span><span class="sxs-lookup"><span data-stu-id="fe1ae-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="fe1ae-182">Antes de liberar as ordens para o depósito, você deve verificar se os locais de separação têm estoque suficiente para todos os itens em todas as ordens.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="fe1ae-183">Revise a configuração **Diretiva de localização** para determinar quais locais de separação são usadas para separação da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="fe1ae-184">Se estiver usando o ambiente de dados de demonstração da Contoso para o depósito *51*, confirme se há estoque disponível.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="fe1ae-185">Agora reserve o estoque para cada linha.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="fe1ae-186">Na FastTab **Linhas de ordem de venda**, selecione uma das linhas que devem ser reservadas.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="fe1ae-187">No menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="fe1ae-188">Na página **Reserva**, no Painel de Ações, selecione **Reservar lote** para aplicar a reserva.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="fe1ae-189">Depois feche a página.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-189">Then close the page.</span></span>
1. <span data-ttu-id="fe1ae-190">Repita as etapas 8 a 10 para as linhas restantes que devem ser reservadas.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="fe1ae-191">Agora é necessário liberar a ordem de venda para o depósito.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="fe1ae-192">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fe1ae-193">Você receberá uma mensagem informando que uma remessa e um ciclo foram criados e que o ciclo foi enviado para execução em lote.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="fe1ae-194">Quando o ciclo e todos os trabalhos downstream tiverem sido concluídos, uma ID de trabalho será criada para o trabalho com seis linhas.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="fe1ae-195">As linhas são classificadas por número de item.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="fe1ae-196">Acesse **Gerenciamento de depósito \> Trabalho \> Todos os trabalhos** para exibir o trabalho criado.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="fe1ae-197">Anote o valor da **ID do Trabalho**, pois precisará usá-lo no próximo procedimento.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="fe1ae-198">Iniciar a separação no dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="fe1ae-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="fe1ae-199">Entre no dispositivo móvel como um usuário configurado para o depósito *51*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="fe1ae-200">No dispositivo móvel, selecione o menu que inclui o novo item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="fe1ae-201">Para esse cenário, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="fe1ae-202">Selecione o item de menu **Separação de linhas do grupo de vendas** para iniciar a separação.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="fe1ae-203">Insira o valor **ID do Trabalho** que anotou no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="fe1ae-204">Você verá uma etapa de separação em que todas as linhas de separação do item *M9200* são agrupadas e será instruído a separar *7* de cada item *M9200*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fe1ae-205">No dispositivo móvel, o trabalho de separação para as três linhas de trabalho de separação foi agregado em uma etapa de separação para o usuário.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="fe1ae-206">Confirme a etapa de separação.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="fe1ae-207">Vá para a página do trabalho para obter a ID do trabalho e observe que todas as três linhas de separação do item *M9200* foram fechadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="fe1ae-208">Volte para o dispositivo móvel e continue separando.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="fe1ae-209">A linha de trabalho 4 do item *M9201* deve ser apresentada.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="fe1ae-210">Como havia apenas uma linha de trabalho na ordem, não há nada a ser agregado.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="fe1ae-211">Confirme a etapa de separação.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="fe1ae-212">A última etapa de separação no dispositivo móvel agrega as duas últimas linhas de separação da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="fe1ae-213">Conclua a etapa para separar *9* de cada um dos itens *M9202*.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="fe1ae-214">Confirme a etapa Put e os pares Separar/Colocar adicionais para concluir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="fe1ae-215">As linhas de trabalho podem ser agrupadas somente se estiverem em sequência.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="fe1ae-216">A seguinte funcionalidade não é suportada:</span><span class="sxs-lookup"><span data-stu-id="fe1ae-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="fe1ae-217">Itens de peso variável</span><span class="sxs-lookup"><span data-stu-id="fe1ae-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="fe1ae-218">Se houver itens de peso variável no trabalho, você receberá uma mensagem de erro antes de começar a separar.</span><span class="sxs-lookup"><span data-stu-id="fe1ae-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="fe1ae-219">Separação de peças</span><span class="sxs-lookup"><span data-stu-id="fe1ae-219">Piece picking</span></span>
>   - <span data-ttu-id="fe1ae-220">Linhas de trabalho que têm trabalho de reabastecimento não concluído</span><span class="sxs-lookup"><span data-stu-id="fe1ae-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="fe1ae-221">Separação em excesso</span><span class="sxs-lookup"><span data-stu-id="fe1ae-221">Over-picking</span></span>
>   - <span data-ttu-id="fe1ae-222">Separação insuficiente com realocação de item</span><span class="sxs-lookup"><span data-stu-id="fe1ae-222">Short picking with item reallocation</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]