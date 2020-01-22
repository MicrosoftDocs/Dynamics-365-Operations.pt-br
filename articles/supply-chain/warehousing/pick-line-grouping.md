---
title: Agrupamento de linhas de separação
description: Este tópico oferece uma visão geral de agrupamento de linhas de separação.
author: Mirzaab
manager: AnnBe
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 1b1d0135d450bc9be7b1303240a9ca70f95ae38e
ms.sourcegitcommit: 610d5c3efadbaf11752b46f24680af619bcd70a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "2906259"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="e229c-103">Agrupamento de linhas de separação</span><span class="sxs-lookup"><span data-stu-id="e229c-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e229c-104">No agrupamento de linhas de separação, várias linhas de trabalho que têm o mesmo item e local podem ser combinadas em uma única separação que é apresentada ao usuário em um dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="e229c-104">In pick line grouping, multiple work lines that have the same item and location can be combined into a single pick that is presented to the user on a mobile device.</span></span> <span data-ttu-id="e229c-105">Portanto, os trabalhadores de depósito podem receber as instruções mais eficientes possíveis, mas a separação necessária de linhas de trabalho no sistema também é mantida (por exemplo, para diferentes contêineres e ordens).</span><span class="sxs-lookup"><span data-stu-id="e229c-105">Therefore, warehouse workers can receive the most efficient instructions that are possible, but the required separation of work lines in the system is also maintained (for example, for different containers and orders).</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="e229c-106">Configurar agrupamento de linhas de separação</span><span class="sxs-lookup"><span data-stu-id="e229c-106">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="e229c-107">Criar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e229c-107">Create a mobile device menu item</span></span>

1. <span data-ttu-id="e229c-108">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel** e criar um novo item de menu que é nomeado **Separação de linha do grupo de vendas – Direcionada ao usuário**.</span><span class="sxs-lookup"><span data-stu-id="e229c-108">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**, and create a new menu item that is named **Sales group line picking – User directed**.</span></span>
2. <span data-ttu-id="e229c-109">Em **Itens de menu do dispositivo móvel**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e229c-109">Under **Mobile device menu items**, set the following values:</span></span>

    - <span data-ttu-id="e229c-110">No campo **Nome do item de menu** digite **Separação de Vendas - Linha do grupo**.</span><span class="sxs-lookup"><span data-stu-id="e229c-110">In the **Menu item name** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="e229c-111">No campo **Título**, digite **Separação de Vendas - Linha do grupo**.</span><span class="sxs-lookup"><span data-stu-id="e229c-111">In the **Title** field, enter **Sales Pick - Group line**.</span></span>
    - <span data-ttu-id="e229c-112">No campo **Modo**, selecione **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e229c-112">In the **Mode** field, select **Work**.</span></span>
    - <span data-ttu-id="e229c-113">Defina a opção **Usar trabalho existente** para **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e229c-113">Set the **Use existing work** option to **Yes**.</span></span>

3. <span data-ttu-id="e229c-114">Na Guia Rápida **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e229c-114">On the **General** FastTab, you can set the following values:</span></span>

    - <span data-ttu-id="e229c-115">No campo **Direcionado por**, selecione **Direcionado pelo usuário**.</span><span class="sxs-lookup"><span data-stu-id="e229c-115">In the **Directed by** field, select **User directed**.</span></span>
    - <span data-ttu-id="e229c-116">Defina a opção **Gerar placa de licença** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e229c-116">Set the **Generate license plate** option to **Yes**.</span></span>
    - <span data-ttu-id="e229c-117">Defina a opção **Separação por grupo** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e229c-117">Set the **Group pick** option to **Yes**.</span></span>

4. <span data-ttu-id="e229c-118">Na Guia Rápida **Classes de trabalho**, siga estas etapas para configurar as classes de trabalho válidas para o item de menu do dispositivo móvel:</span><span class="sxs-lookup"><span data-stu-id="e229c-118">On the **Work classes** FastTab, follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="e229c-119">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e229c-119">Select **New**.</span></span>
    2. <span data-ttu-id="e229c-120">No campo **ID da classe de trabalho**, selecione **Vendas** ou **Separação de OV**, dependendo do depósito que você usará.</span><span class="sxs-lookup"><span data-stu-id="e229c-120">In the **Work class ID** field, select **Sales** or **SO Pick**, depending on the warehouse that you will use.</span></span>
    3. <span data-ttu-id="e229c-121">No campo **Tipo de ordem de trabalho**, selecione **Ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="e229c-121">In the **Work order type** field, select **Sales orders**.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="e229c-122">Configura um menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e229c-122">Set up a mobile device menu</span></span>

1. <span data-ttu-id="e229c-123">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="e229c-123">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span> 
1. <span data-ttu-id="e229c-124">Adicione o item de menu que você acabou de criar para o menu desejado.</span><span class="sxs-lookup"><span data-stu-id="e229c-124">Add the menu item that you just created to the desired menu.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="e229c-125">Configurar um modelo de trabalho</span><span class="sxs-lookup"><span data-stu-id="e229c-125">Set up a work template</span></span>

1. <span data-ttu-id="e229c-126">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Modelo de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="e229c-126">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="e229c-127">Localize o modelo de trabalho que deve ser usado com essa função.</span><span class="sxs-lookup"><span data-stu-id="e229c-127">Find the work template that should be used with this function.</span></span> <span data-ttu-id="e229c-128">Para este exemplo, selecione o modelo de trabalho **51 Estágio de separação** Contoso.</span><span class="sxs-lookup"><span data-stu-id="e229c-128">For this example, select the standard **51 Pick to stage** Contoso work template.</span></span>
1. <span data-ttu-id="e229c-129">No menu, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="e229c-129">On the menu, select **Edit query**.</span></span>
1. <span data-ttu-id="e229c-130">Na guia **Classificação**, selecione **Adicionar** e, em seguida, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="e229c-130">On the **Sorting** tab, select **Add**, and then set the following values:</span></span>

    - <span data-ttu-id="e229c-131">No campo **Tabela**, selecione **Transações de trabalho temporário**.</span><span class="sxs-lookup"><span data-stu-id="e229c-131">In the **Table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="e229c-132">No campo **Tabela derivada**, selecione **Transações de trabalho temporário**.</span><span class="sxs-lookup"><span data-stu-id="e229c-132">In the **Derived table** field, select **Temporary work transactions**.</span></span>
    - <span data-ttu-id="e229c-133">No campo **Campo**, selecione **Número do item**.</span><span class="sxs-lookup"><span data-stu-id="e229c-133">In the **Field** field, select **Item number**.</span></span>
    - <span data-ttu-id="e229c-134">No campo **Direção da pesquisa**, selecione **Crescente**.</span><span class="sxs-lookup"><span data-stu-id="e229c-134">In the **Search direction** field, select **Ascending**.</span></span>

> [!NOTE]
> <span data-ttu-id="e229c-135">Para que a funcionalidade agrupamento de linhas de separação funcione, as linhas de trabalho devem ser classificadas por ID do item.</span><span class="sxs-lookup"><span data-stu-id="e229c-135">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="e229c-136">Se as linhas que têm os mesmos itens não forem sequenciadas uma após a outra, elas não serão agrupadas.</span><span class="sxs-lookup"><span data-stu-id="e229c-136">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="e229c-137">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e229c-137">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="e229c-138">Criar trabalho de separação</span><span class="sxs-lookup"><span data-stu-id="e229c-138">Create picking work</span></span>

<span data-ttu-id="e229c-139">Antes de configurar o agrupamento de linhas de separação, você deve criar algum trabalho de saída qualificado.</span><span class="sxs-lookup"><span data-stu-id="e229c-139">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="e229c-140">Vá para **Vendas e Marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="e229c-140">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
2. <span data-ttu-id="e229c-141">Selecione **Novo** para criar uma ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e229c-141">Select **New** to create a sales order.</span></span> 
3. <span data-ttu-id="e229c-142">No campo **Conta de cliente**, selecione qualquer cliente.</span><span class="sxs-lookup"><span data-stu-id="e229c-142">In the **Customer account** field, select any customer.</span></span> 
4. <span data-ttu-id="e229c-143">Na Guia Rápida **Geral**, no campo **Depósito**, selecione **51**.</span><span class="sxs-lookup"><span data-stu-id="e229c-143">On the **General** FastTab, in the **Warehouse** field, select **51**.</span></span> <span data-ttu-id="e229c-144">Em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="e229c-144">Then select **OK**.</span></span>
5. <span data-ttu-id="e229c-145">Nas **Linhas de ordem de venda**, adicione as seguintes seis linhas:</span><span class="sxs-lookup"><span data-stu-id="e229c-145">Under **Sales order lines**, add the following six lines:</span></span>

    - <span data-ttu-id="e229c-146">**Linha 1:** No campo **Número do item**, selecione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="e229c-146">**Line 1:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="e229c-147">No campo **Quantidade**, insira **3**.</span><span class="sxs-lookup"><span data-stu-id="e229c-147">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="e229c-148">**Linha 2:** No campo **Número do item**, selecione **M9201**.</span><span class="sxs-lookup"><span data-stu-id="e229c-148">**Line 2:** In the **Item number** field, select **M9201**.</span></span> <span data-ttu-id="e229c-149">No campo **Quantidade**, insira **3**.</span><span class="sxs-lookup"><span data-stu-id="e229c-149">In the **Quantity** field, enter **3**.</span></span> 
    - <span data-ttu-id="e229c-150">**Linha 3:** No campo **Número do item**, selecione **M9202**.</span><span class="sxs-lookup"><span data-stu-id="e229c-150">**Line 3:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="e229c-151">No campo **Quantidade**, insira **2**.</span><span class="sxs-lookup"><span data-stu-id="e229c-151">In the **Quantity** field, enter **2**.</span></span> 
    - <span data-ttu-id="e229c-152">**Linha 4:** No campo **Número do item**, selecione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="e229c-152">**Line 4:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="e229c-153">No campo **Quantidade**, insira **1**.</span><span class="sxs-lookup"><span data-stu-id="e229c-153">In the **Quantity** field, enter **1**.</span></span> 
    - <span data-ttu-id="e229c-154">**Linha 5:** No campo **Número do item**, selecione **M9200**.</span><span class="sxs-lookup"><span data-stu-id="e229c-154">**Line 5:** In the **Item number** field, select **M9200**.</span></span> <span data-ttu-id="e229c-155">No campo **Quantidade**, insira **3**.</span><span class="sxs-lookup"><span data-stu-id="e229c-155">In the **Quantity** field, enter **3**.</span></span>
    - <span data-ttu-id="e229c-156">**Linha 6:** No campo **Número do item**, selecione **M9202**.</span><span class="sxs-lookup"><span data-stu-id="e229c-156">**Line 6:** In the **Item number** field, select **M9202**.</span></span> <span data-ttu-id="e229c-157">No campo **Quantidade**, insira **7**.</span><span class="sxs-lookup"><span data-stu-id="e229c-157">In the **Quantity** field, enter **7**.</span></span> 

    <span data-ttu-id="e229c-158">Aqui está um resumo das quantidades totais de cada item:</span><span class="sxs-lookup"><span data-stu-id="e229c-158">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="e229c-159">**Item M9200:** 7 cada</span><span class="sxs-lookup"><span data-stu-id="e229c-159">**Item M9200:** 7 each</span></span>
    - <span data-ttu-id="e229c-160">**Item M9201:** 3 cada</span><span class="sxs-lookup"><span data-stu-id="e229c-160">**Item M9201:** 3 each</span></span>
    - <span data-ttu-id="e229c-161">**Item M9202:** 9 cada</span><span class="sxs-lookup"><span data-stu-id="e229c-161">**Item M9202:** 9 each</span></span>

6. <span data-ttu-id="e229c-162">Antes de liberar as ordens para o depósito, você deve verificar se os locais de separação têm estoque suficiente para todos os itens em todas as ordens.</span><span class="sxs-lookup"><span data-stu-id="e229c-162">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="e229c-163">Revise a configuração **Diretiva de localização** para determinar quais locais de separação são usadas para separação da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="e229c-163">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span>
7. <span data-ttu-id="e229c-164">Reserve o estoque e libere-o para o depósito.</span><span class="sxs-lookup"><span data-stu-id="e229c-164">Reserve the inventory, and release it to the warehouse.</span></span> <span data-ttu-id="e229c-165">Uma ID de trabalho que tem seis linhas é criada.</span><span class="sxs-lookup"><span data-stu-id="e229c-165">A work ID that has six lines is created.</span></span> <span data-ttu-id="e229c-166">As linhas são classificadas por número de item.</span><span class="sxs-lookup"><span data-stu-id="e229c-166">The lines are sorted by item number.</span></span>

### <a name="run-the-mobile-device-flow"></a><span data-ttu-id="e229c-167">Execute o fluxo do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="e229c-167">Run the mobile device flow</span></span>

1. <span data-ttu-id="e229c-168">No dispositivo móvel, selecione o menu que inclui o novo item de menu do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="e229c-168">On the mobile device, select the menu that includes the new mobile device menu item.</span></span>
1. <span data-ttu-id="e229c-169">Selecione o item de menu **Separação de Vendas – Linha do grupo** e inicie a separação.</span><span class="sxs-lookup"><span data-stu-id="e229c-169">Select the **Sales Pick – Group line** menu item, and initiate the pick.</span></span>

    <span data-ttu-id="e229c-170">Depois de selecionar o menu e inserir a ID de trabalho, você verá a etapa de seleção em que todas as linhas de separação do item M9200 são agrupadas.</span><span class="sxs-lookup"><span data-stu-id="e229c-170">After you select the menu and enter the work ID, you see the pick step where all pick lines for item M9200 are grouped.</span></span> <span data-ttu-id="e229c-171">Você recebe uma instrução para selecionar 7 a cada M9200 do item.</span><span class="sxs-lookup"><span data-stu-id="e229c-171">You receive an instruction to pick 7 each of item M9200.</span></span>

1. <span data-ttu-id="e229c-172">Confirme a etapa de separação.</span><span class="sxs-lookup"><span data-stu-id="e229c-172">Confirm the pick step.</span></span> 
1. <span data-ttu-id="e229c-173">Vá para a tela do cliente do trabalho em andamento e observe que todas as três linhas de separação do item M9200 foram fechadas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="e229c-173">Go to the client screen of the work in process, and notice that all three pick lines for item M9200 were closed simultaneously.</span></span>

    <span data-ttu-id="e229c-174">A linha de trabalho 4 é apresentada.</span><span class="sxs-lookup"><span data-stu-id="e229c-174">Work line 4 is presented.</span></span>

1. <span data-ttu-id="e229c-175">Confirme a etapa de separação.</span><span class="sxs-lookup"><span data-stu-id="e229c-175">Confirm the pick step.</span></span>

    <span data-ttu-id="e229c-176">A última etapa de separação no dispositivo móvel agrega as duas últimas linhas de separação da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e229c-176">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>

1. <span data-ttu-id="e229c-177">Conclua a etapa de separação para 9 cada um dos itens M9202.</span><span class="sxs-lookup"><span data-stu-id="e229c-177">Complete the pick step for 9 each of item M9202.</span></span>
1. <span data-ttu-id="e229c-178">Confirme a etapa Put e os pares Separar/Colocar adicionais para concluir o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e229c-178">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!NOTE]
> - <span data-ttu-id="e229c-179">As linhas de trabalho podem ser agrupadas somente se estiverem em sequência.</span><span class="sxs-lookup"><span data-stu-id="e229c-179">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="e229c-180">A seguinte funcionalidade não é suportada:</span><span class="sxs-lookup"><span data-stu-id="e229c-180">The following functionality isn't supported:</span></span>
>
>    - <span data-ttu-id="e229c-181">Itens de peso variável.</span><span class="sxs-lookup"><span data-stu-id="e229c-181">Catch-weight items.</span></span> <span data-ttu-id="e229c-182">Se houver itens de peso variável no trabalho, você receberá uma mensagem de erro antes de começar a separar.</span><span class="sxs-lookup"><span data-stu-id="e229c-182">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>    - <span data-ttu-id="e229c-183">Separação de peças.</span><span class="sxs-lookup"><span data-stu-id="e229c-183">Piece picking.</span></span>
>    - <span data-ttu-id="e229c-184">Linhas de trabalho que têm trabalho de reabastecimento não concluído.</span><span class="sxs-lookup"><span data-stu-id="e229c-184">Work lines that have unfinished replenishment work.</span></span>
>    - <span data-ttu-id="e229c-185">Separação de ordens.</span><span class="sxs-lookup"><span data-stu-id="e229c-185">Over-picking.</span></span>
