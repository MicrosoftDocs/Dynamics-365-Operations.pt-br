---
title: Posicionamento da placa de licença de localização
description: O posicionamento da placa de licença de localização permite ver onde há uma placa de licença em uma localização com vários paletes, como um que usa um rack de paletes com profundidade dupla.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6d94d37368b8fc3ff7dbe4c1845acd52bf2a64ee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5004668"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="c4f25-103">Posicionamento da placa de licença de localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c4f25-104">O posicionamento da placa de licença de localização permite ver onde há uma placa de licença em uma localização com vários paletes, como um que usa um rack de paletes com profundidade dupla.</span><span class="sxs-lookup"><span data-stu-id="c4f25-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="c4f25-105">O recurso adiciona um número de sequência a cada placa de licença colocada em um local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c4f25-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="c4f25-106">Esse número de sequência é usado para ordenar as placas de licença no local de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="c4f25-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="c4f25-107">Por isso, o recurso oferece suporte de modo inteligente a cenários em que os clientes usam um sistema de rack de gravidade e devem saber qual placa de licença está virada para a frente, para fins de separação.</span><span class="sxs-lookup"><span data-stu-id="c4f25-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="c4f25-108">Este tópico apresenta um cenário que mostra como configurar e usar o recurso.</span><span class="sxs-lookup"><span data-stu-id="c4f25-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="c4f25-109">Ativar o recurso de posicionamento da placa de licença de localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="c4f25-110">Para que você possa usar o posicionamento da placa de licença de localização, o recurso deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="c4f25-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="c4f25-111">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="c4f25-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="c4f25-112">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="c4f25-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="c4f25-113">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="c4f25-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="c4f25-114">**Nome do recurso:** *Posicionamento da placa de licença de localização*</span><span class="sxs-lookup"><span data-stu-id="c4f25-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="c4f25-115">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="c4f25-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="c4f25-116">Disponibilizar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="c4f25-116">Make sample data available</span></span>

<span data-ttu-id="c4f25-117">Para trabalhar nesse cenário usando os valores aqui sugeridos, você deve trabalhar em um sistema no qual os dados de exemplo estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="c4f25-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="c4f25-118">Além disso, você deve selecionar a entidade legal **USMF** antes de iniciar.</span><span class="sxs-lookup"><span data-stu-id="c4f25-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="c4f25-119">Configurar o recurso para o cenário</span><span class="sxs-lookup"><span data-stu-id="c4f25-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="c4f25-120">Execute os procedimentos a seguir para configurar o recurso *Posicionamento da placa de licença de localização* para o cenário apresentado neste tópico.</span><span class="sxs-lookup"><span data-stu-id="c4f25-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="c4f25-121">Perfis de localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-121">Location profiles</span></span>

<span data-ttu-id="c4f25-122">O recurso deve estar ativado no perfil de localização de cada localização onde ele será usado.</span><span class="sxs-lookup"><span data-stu-id="c4f25-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="c4f25-123">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="c4f25-124">Na lista de perfis de localização no painel esquerdo, selecione **MASSA-06**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="c4f25-125">Na FastTab **Geral**, duas novas opções foram adicionadas pelo recurso.</span><span class="sxs-lookup"><span data-stu-id="c4f25-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="c4f25-126">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c4f25-126">Set the following values:</span></span>

    - <span data-ttu-id="c4f25-127">**Habilitar posição da placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="c4f25-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="c4f25-128">Quando a opção for definida como *Sim*, a posição será mantida para as placas de licença no local.</span><span class="sxs-lookup"><span data-stu-id="c4f25-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="c4f25-129">**Exibir posição da LP do dispositivo móvel:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="c4f25-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="c4f25-130">Quando a opção for definida como *Sim*, a posição da placa de licença será mostrada para os usuários do dispositivo móvel durante o ajuste e a contagem.</span><span class="sxs-lookup"><span data-stu-id="c4f25-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="c4f25-131">Você só poderá alterar a configuração da opção quando o recurso estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="c4f25-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="c4f25-132">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="c4f25-133">Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-133">Location directives</span></span>

1. <span data-ttu-id="c4f25-134">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="c4f25-135">No painel esquerdo, verifique se o campo **Tipo de ordem de trabalho** está definido como *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="c4f25-136">Na lista de diretivas de localização, selecione **Ordem de separação de OV 61**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="c4f25-137">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="c4f25-138">Na FastTab **Linhas**, selecione a linha que tem um valor **Número de sequência** de *2*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="c4f25-139">Na FastTab **Ações de Diretiva de Localização**, selecione a linha que tem um valor **Nome** de *Separar para menos que palete* (deve ser a única linha) e mude o valor **Número de sequência** para *2*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="c4f25-140">Selecione **Novo** acima da grade para adicionar uma linha para uma nova ação de diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="c4f25-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="c4f25-141">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c4f25-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4f25-142">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="c4f25-143">**Nome:** *Posição de separação 1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="c4f25-144">Com a nova linha ainda selecionada, selecione **Editar consulta** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="c4f25-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="c4f25-145">No editor de consultas, selecione a guia **Junções**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="c4f25-146">Expanda junção de tabela **Localizações** para mostrar a junção na tabela **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="c4f25-147">Expanda a junção de tabela **Dimensões de estoque** para mostrar a junção na tabela **Estoque disponível**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="c4f25-148">Selecione **Dimensões de estoque** e, depois, **Adicionar tabela de junção**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="c4f25-149">Na lista de tabelas exibida, na coluna **Relação**, selecione **Placa de licença (Placa de licença)**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="c4f25-150">Depois, clique em **Selecionar** para adicionar **Placa de licença** à junção de tabela **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="c4f25-151">Com **Placa de licença** ainda selecionada, selecione **Adicionar junção de tabela**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="c4f25-152">Na lista de tabelas exibida, na coluna **Relação**, selecione **Posicionamento da placa de licença de localização (Placa de licença)**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="c4f25-153">Depois, clique em **Selecionar** para adicionar **Posicionamento da placa de licença de localização** à junção de tabela **Dimensões de estoque**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="c4f25-154">![Junções de tabela](media/LpTableJoin.png "Junções de tabela")</span><span class="sxs-lookup"><span data-stu-id="c4f25-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="c4f25-155">Selecione **OK** para confirmar as tabelas associadas atualizadas e fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="c4f25-156">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta** novamente para reabrir o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="c4f25-157">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="c4f25-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="c4f25-158">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="c4f25-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="c4f25-159">**Tabela:** *Posicionamento da placa de licença de localização*</span><span class="sxs-lookup"><span data-stu-id="c4f25-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="c4f25-160">**Tabela derivada:** *Posicionamento da placa de licença de localização*</span><span class="sxs-lookup"><span data-stu-id="c4f25-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="c4f25-161">**Campo:** *Posição da LP*</span><span class="sxs-lookup"><span data-stu-id="c4f25-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="c4f25-162">**Critérios:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="c4f25-163">![Novo intervalo](media/LpPositionCriteria.png "Novo intervalo")</span><span class="sxs-lookup"><span data-stu-id="c4f25-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="c4f25-164">Selecione **OK** para confirmar as alterações e fechar o editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="c4f25-165">Configurar dados de exemplo para o cenário</span><span class="sxs-lookup"><span data-stu-id="c4f25-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="c4f25-166">Para este cenário, o usuário deve entrar no aplicativo móvel de depósito usando um trabalhador configurado para o depósito *61* para executar o trabalho.</span><span class="sxs-lookup"><span data-stu-id="c4f25-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="c4f25-167">O usuário também deve concluir as transações.</span><span class="sxs-lookup"><span data-stu-id="c4f25-167">The user must also complete transactions.</span></span>

<span data-ttu-id="c4f25-168">Como o recurso *Posicionamento da placa de licença de localização* adiciona um novo identificador para as posições de placa de licença em uma localização, primeiro você deve criar alguns dados para dar suporte ao cenário.</span><span class="sxs-lookup"><span data-stu-id="c4f25-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="c4f25-169">Contagem pontual da primeira localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-169">Spot-count the first location</span></span>

1. <span data-ttu-id="c4f25-170">Abra o aplicativo móvel de depósito e entre no depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="c4f25-171">Vá para **Estoque \> Contagem Pontual**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="c4f25-172">Na página **Contagem Pontual**, defina o campo **Localização** como *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="c4f25-173">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-173">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-174">A página mostra a localização que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="c4f25-174">The page shows the location that you entered.</span></span> <span data-ttu-id="c4f25-175">Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"</span><span class="sxs-lookup"><span data-stu-id="c4f25-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="c4f25-176">Selecione **Atualizar** para adicionar uma contagem na localização.</span><span class="sxs-lookup"><span data-stu-id="c4f25-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="c4f25-177">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **Item** e insira o valor *A0001*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="c4f25-178">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-178">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-179">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **LP** e insira o valor *LP1001* (ou qualquer outro número de placa de licença de sua escolha).</span><span class="sxs-lookup"><span data-stu-id="c4f25-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="c4f25-180">A página **Contagem Cíclica: Adicionar um Novo LP ou Item** mostra **Posição 1 da Placa de Licença**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="c4f25-181">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-181">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-182">Agora, você deve especificar a quantidade do item contada na placa de licença.</span><span class="sxs-lookup"><span data-stu-id="c4f25-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="c4f25-183">Defina o campo **Qtd.** como *10*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="c4f25-184">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-184">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-185">A página mostra a localização que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="c4f25-185">The page shows the location that you entered.</span></span> <span data-ttu-id="c4f25-186">Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"</span><span class="sxs-lookup"><span data-stu-id="c4f25-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="c4f25-187">Selecione **Atualizar** para adicionar outra contagem na localização.</span><span class="sxs-lookup"><span data-stu-id="c4f25-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="c4f25-188">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **Item** e insira o valor *A0002*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="c4f25-189">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-189">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-190">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **LP** e insira o valor *LP1002* (ou qualquer outro número de placa de licença de sua escolha, desde que seja diferente do número da placa de licença especificado anteriormente).</span><span class="sxs-lookup"><span data-stu-id="c4f25-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="c4f25-191">Mude a posição da placa de licença definindo o campo **Posição da LP** como *2*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="c4f25-192">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-192">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-193">Especifique a quantidade do item contada na placa de licença definindo o campo **Qtd.** como *10*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="c4f25-194">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-194">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-195">A página mostra a localização que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="c4f25-195">The page shows the location that you entered.</span></span> <span data-ttu-id="c4f25-196">Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"</span><span class="sxs-lookup"><span data-stu-id="c4f25-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="c4f25-197">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-197">Select **OK**.</span></span>

<span data-ttu-id="c4f25-198">Agora o trabalho está concluído.</span><span class="sxs-lookup"><span data-stu-id="c4f25-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="c4f25-199">Contagem pontual da segunda localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-199">Spot-count the second location</span></span>

1. <span data-ttu-id="c4f25-200">Na página **Contagem Pontual**, defina o campo **Localização** como *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="c4f25-201">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-201">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-202">A página mostra a localização que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="c4f25-202">The page shows the location that you entered.</span></span> <span data-ttu-id="c4f25-203">Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"</span><span class="sxs-lookup"><span data-stu-id="c4f25-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="c4f25-204">Selecione **Atualizar** para adicionar uma contagem na localização.</span><span class="sxs-lookup"><span data-stu-id="c4f25-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="c4f25-205">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **Item** e insira o valor *A0002*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="c4f25-206">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-206">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-207">Na página **Contagem Cíclica: Adicionar um Novo LP ou Item**, selecione o campo **LP** e insira o valor *LP1003* (ou qualquer outro número de placa de licença de sua escolha, desde que seja diferente dos dois números de placa de licença especificados no procedimento anterior).</span><span class="sxs-lookup"><span data-stu-id="c4f25-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="c4f25-208">A página **Contagem Cíclica: Adicionar um Novo LP ou Item** mostra **Posição 1 da Placa de Licença**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="c4f25-209">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-209">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-210">Especifique a quantidade do item contada na placa de licença definindo o campo **Qtd.** como *10*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="c4f25-211">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-211">Select **OK**.</span></span>

    <span data-ttu-id="c4f25-212">A página mostra a localização que você inseriu.</span><span class="sxs-lookup"><span data-stu-id="c4f25-212">The page shows the location that you entered.</span></span> <span data-ttu-id="c4f25-213">Ela também mostra a seguinte mensagem: "Localização concluída, adicionar nova LP ou item?"</span><span class="sxs-lookup"><span data-stu-id="c4f25-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="c4f25-214">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-214">Select **OK**.</span></span>

<span data-ttu-id="c4f25-215">Agora o trabalho está concluído.</span><span class="sxs-lookup"><span data-stu-id="c4f25-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="c4f25-216">Detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="c4f25-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="c4f25-217">As contagens pontuais do aplicativo móvel criam um trabalho de contagem cíclica no Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c4f25-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="c4f25-218">O trabalho exige que as contagens sejam aceitas antes de serem lançadas no estoque.</span><span class="sxs-lookup"><span data-stu-id="c4f25-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="c4f25-219">Entre no Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c4f25-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="c4f25-220">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="c4f25-221">Na guia **Visão geral**, procure as linhas com os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c4f25-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="c4f25-222">**Tipo de ordem de trabalho:** *Contagem cíclica*</span><span class="sxs-lookup"><span data-stu-id="c4f25-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="c4f25-223">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="c4f25-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c4f25-224">**Status do trabalho:** *Revisão pendente*</span><span class="sxs-lookup"><span data-stu-id="c4f25-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="c4f25-225">Duas IDs de trabalho devem ter sido criadas para essas linhas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="c4f25-226">As contagens para essas duas IDs de trabalho devem ser aceitas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="c4f25-227">Na grade, selecione a primeira ID de trabalho para o tipo de ordem de trabalho *Contagem Cíclica*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="c4f25-228">No Painel de Ação, na guia **Trabalho**, no grupo **Trabalho**, selecione **Contagem cíclica**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="c4f25-229">Duas linhas são mostradas, uma para cada item e placa de licença.</span><span class="sxs-lookup"><span data-stu-id="c4f25-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="c4f25-230">Os valores nos campos **Quantidade contada**, **Localização**, **Placa de licença** e **Item** devem coincidir com as entradas de contagem criadas no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="c4f25-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="c4f25-231">Se algum desses campos não estiver visível, selecione **Exibir dimensões** no Painel de Ação para adicioná-los à grade.</span><span class="sxs-lookup"><span data-stu-id="c4f25-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="c4f25-232">Selecione as duas linhas.</span><span class="sxs-lookup"><span data-stu-id="c4f25-232">Select both lines.</span></span>
1. <span data-ttu-id="c4f25-233">No Painel de Ação, selecione **Aceitar contagem**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="c4f25-234">Você receberá uma mensagem "Lançamento - Diário".</span><span class="sxs-lookup"><span data-stu-id="c4f25-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="c4f25-235">Selecione **Detalhes da mensagem** para exibir o número de diário lançado.</span><span class="sxs-lookup"><span data-stu-id="c4f25-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="c4f25-236">Feche os detalhes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4f25-236">Close the message details.</span></span>
1. <span data-ttu-id="c4f25-237">Atualize a página **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="c4f25-238">A primeira ID de trabalho foi fechada e não é mais mostrada.</span><span class="sxs-lookup"><span data-stu-id="c4f25-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="c4f25-239">Para ver o trabalho fechado, marque a caixa de seleção **Mostrar fechado** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="c4f25-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="c4f25-240">Agora você aceitará o trabalho referente à placa de licença na localização *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="c4f25-241">Na guia **Visão geral**, selecione a segunda ID de trabalho para o tipo de ordem de trabalho *Contagem Cíclica*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="c4f25-242">No Painel de Ação, na guia **Trabalho**, no grupo **Trabalho**, selecione **Contagem cíclica**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="c4f25-243">É mostrada uma linha relativa ao item e à placa de licença.</span><span class="sxs-lookup"><span data-stu-id="c4f25-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="c4f25-244">Os valores nos campos **Quantidade contada**, **Localização**, **Placa de licença** e **Item** devem coincidir com as entradas de contagem criadas no dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="c4f25-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="c4f25-245">Selecione a linha.</span><span class="sxs-lookup"><span data-stu-id="c4f25-245">Select the line.</span></span>
1. <span data-ttu-id="c4f25-246">No Painel de Ação, selecione **Aceitar contagem**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="c4f25-247">Você receberá uma mensagem "Lançamento - Diário".</span><span class="sxs-lookup"><span data-stu-id="c4f25-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="c4f25-248">Selecione **Detalhes da mensagem** para exibir o número de diário lançado.</span><span class="sxs-lookup"><span data-stu-id="c4f25-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="c4f25-249">Feche os detalhes da mensagem.</span><span class="sxs-lookup"><span data-stu-id="c4f25-249">Close the message details.</span></span>
1. <span data-ttu-id="c4f25-250">Atualize a página **Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="c4f25-251">A segunda ID de trabalho foi fechada e não é mais mostrada.</span><span class="sxs-lookup"><span data-stu-id="c4f25-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="c4f25-252">Para ver o trabalho fechado, marque a caixa de seleção **Mostrar fechado** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="c4f25-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="c4f25-253">Disponibilidade por localização</span><span class="sxs-lookup"><span data-stu-id="c4f25-253">On-hand by location</span></span>

1. <span data-ttu-id="c4f25-254">Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Disponível por local**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="c4f25-255">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c4f25-255">Set the following values:</span></span>

    - <span data-ttu-id="c4f25-256">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="c4f25-256">**Site:** *6*</span></span>
    - <span data-ttu-id="c4f25-257">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="c4f25-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="c4f25-258">**Atualizar entre localizações:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="c4f25-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="c4f25-259">Observe que a localização *01A01R1S1B* tem duas placas de licença:</span><span class="sxs-lookup"><span data-stu-id="c4f25-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="c4f25-260">**A0001**, na qual o campo **Posição da LP** está definido como *1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="c4f25-261">**A0002**, na qual o campo **Posição da LP** está definido como *2*</span><span class="sxs-lookup"><span data-stu-id="c4f25-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="c4f25-262">Observe que a localização *01A01R1S2B* tem uma placa de licença:</span><span class="sxs-lookup"><span data-stu-id="c4f25-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="c4f25-263">**A0002**, na qual o campo **Posição da LP** está definido como *1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="c4f25-264">Cenário de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="c4f25-264">Sales order scenario</span></span>

<span data-ttu-id="c4f25-265">Agora que o recurso *Posicionamento da placa de licença de localização* foi configurado e o estoque foi preparado, você deve criar uma ordem de venda para gerar um trabalho de separação que orientará o trabalhador do depósito a separar o item *A0002* da localização de estoque em que a ID do palete está na posição *1*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="c4f25-266">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="c4f25-267">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="c4f25-268">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c4f25-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="c4f25-269">**Conta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="c4f25-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="c4f25-270">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="c4f25-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="c4f25-271">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-271">Select **OK**.</span></span>
1. <span data-ttu-id="c4f25-272">Uma nova linha é adicionada à grade na FastTab **Linhas de ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="c4f25-273">Nessa nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="c4f25-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="c4f25-274">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="c4f25-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="c4f25-275">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="c4f25-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="c4f25-276">No menu **Estoque** acima da grade, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="c4f25-277">na página **Reserva**, no Painel de Ação, selecione **Reservar lote** para reservar estoque para a linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="c4f25-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="c4f25-278">Feche a página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="c4f25-279">No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="c4f25-280">Você receberá uma mensagem informativa que indica a ID da onda e a ID de remessa criadas para a ordem.</span><span class="sxs-lookup"><span data-stu-id="c4f25-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="c4f25-281">Na FastTab **Linhas de ordem de venda**, no menu **Depósito** acima da grade, selecione **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="c4f25-282">A página **Trabalho** é exibida e mostra o trabalho que foi criado para a linha de venda.</span><span class="sxs-lookup"><span data-stu-id="c4f25-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="c4f25-283">Anote a ID de trabalho mostrada.</span><span class="sxs-lookup"><span data-stu-id="c4f25-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="c4f25-284">Cenário de separação de venda</span><span class="sxs-lookup"><span data-stu-id="c4f25-284">Sales picking scenario</span></span>

1. <span data-ttu-id="c4f25-285">Abra o aplicativo móvel e entre no depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="c4f25-286">Vá para **Saída \> Separação de venda**.</span><span class="sxs-lookup"><span data-stu-id="c4f25-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="c4f25-287">Na página **Digitalizar uma ID de trabalho/ID de placa de licença**, selecione o campo **ID** e insira a ID de trabalho na linha de venda.</span><span class="sxs-lookup"><span data-stu-id="c4f25-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="c4f25-288">Observe que o trabalho de separação leva você a selecionar o item *A0002* da localização *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="c4f25-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="c4f25-289">Você recebe essa instrução porque o item *A0002* está em uma placa de licença na posição *1* dessa localização.</span><span class="sxs-lookup"><span data-stu-id="c4f25-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="c4f25-290">![Localização da posição 1](media/LocationLicensePlatePositioning.png "Localização da posição 1")</span><span class="sxs-lookup"><span data-stu-id="c4f25-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="c4f25-291">Insira a ID da placa de licença que você criou para a localização e siga os prompts para separar a ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="c4f25-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>
