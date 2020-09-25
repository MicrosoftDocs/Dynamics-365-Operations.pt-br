---
title: Combinação de dimensões do produto de localização
description: Este tópico fornece informações sobre a combinação de dimensões do produto de localização. Essa funcionalidade do perfil de localização ajuda a melhorar o gerenciamento de localização quando grades de produtos ou produtos que têm dimensões são usados, como na indústria da moda. Ela permite decidir se configurações, cores, estilos e tamanhos podem ser combinados para um perfil de localização específico ou se apenas uma dessas dimensões ou uma combinação delas podem ser colocadas no mesmo local.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 968777b918d59b810a189139fbf4d6fee1b5d3f5
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "3529974"
---
# <a name="location-product-dimension-mixing"></a><span data-ttu-id="816b1-105">Combinação de dimensões do produto de localização</span><span class="sxs-lookup"><span data-stu-id="816b1-105">Location product dimension mixing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="816b1-106">A combinação de dimensões do produto de localização é uma funcionalidade do perfil de localização que ajuda a melhorar o gerenciamento de localização quando grades de produtos ou produtos que têm dimensões são usados, como na indústria da moda.</span><span class="sxs-lookup"><span data-stu-id="816b1-106">Location product dimension mixing is location profile functionality that helps improve location management when product variants or products that have dimensions are used, such as in the fashion industry.</span></span> <span data-ttu-id="816b1-107">Ela permite decidir se configurações, cores, estilos e tamanhos podem ser combinados para um perfil de localização específico ou se apenas uma dessas dimensões ou uma combinação delas podem ser colocadas no mesmo local.</span><span class="sxs-lookup"><span data-stu-id="816b1-107">It lets you decide whether configurations, colors, styles, and sizes can be mixed for a specific location profile, or whether just one of these dimensions or a combination of them can be put to the same location.</span></span>

## <a name="turn-on-the-location-product-dimension-mixing-feature"></a><span data-ttu-id="816b1-108">Ativar o recurso Combinação de dimensões do produto de localização</span><span class="sxs-lookup"><span data-stu-id="816b1-108">Turn on the Location product dimension mixing feature</span></span>

<span data-ttu-id="816b1-109">Para que você possa usar a combinação de dimensões do produto de localização, o recurso deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="816b1-109">Before you can use location product dimension mixing, the feature must be turned on in your system.</span></span> <span data-ttu-id="816b1-110">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="816b1-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="816b1-111">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="816b1-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="816b1-112">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="816b1-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="816b1-113">**Nome do recurso:** *Combinação de dimensões do produto de localização*</span><span class="sxs-lookup"><span data-stu-id="816b1-113">**Feature name:** *Location product dimension mixing*</span></span>

## <a name="setup"></a><span data-ttu-id="816b1-114">Instalação</span><span class="sxs-lookup"><span data-stu-id="816b1-114">Setup</span></span>

<span data-ttu-id="816b1-115">Cada local no depósito precisa ter um perfil de localização associado a ele que descreva suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="816b1-115">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location.</span></span> <span data-ttu-id="816b1-116">Portanto, todos os locais que usam o mesmo perfil de localização poderão permitir a combinação de dimensões do produto após sua configuração.</span><span class="sxs-lookup"><span data-stu-id="816b1-116">Therefore, all locations that use the same location profile will be able to allow product dimension mixing after it has been set up.</span></span>

### <a name="configure-location-profiles-to-allow-product-dimension-mixing"></a><span data-ttu-id="816b1-117">Configurar perfis de localização para permitir a combinação de dimensões do produto</span><span class="sxs-lookup"><span data-stu-id="816b1-117">Configure location profiles to allow product dimension mixing</span></span>

1. <span data-ttu-id="816b1-118">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="816b1-118">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="816b1-119">Na lista de perfis de localização, selecione **MASSA**.</span><span class="sxs-lookup"><span data-stu-id="816b1-119">In the list of location profiles, select **BULK**.</span></span>
1. <span data-ttu-id="816b1-120">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-120">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="816b1-121">Na FastTab **Geral**, defina a opção **Habilitar a combinação específica de dimensões do produto de localização** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="816b1-121">On the **General** FastTab, set the **Enable location product dimension specific mixing** option to *Yes*.</span></span>

    > [!NOTE]
    > <span data-ttu-id="816b1-122">Você só poderá definir essa opção como *Sim* se a opção **Permitir itens mistos** estiver definida como *Não*.</span><span class="sxs-lookup"><span data-stu-id="816b1-122">You can set this option to *Yes* only if the **Allow mixed items** option is set to *No*.</span></span>

1. <span data-ttu-id="816b1-123">Na FastTab **Combinação de dimensões do produto permitida**, defina a opção **Tamanho** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="816b1-123">On the **Allowed product dimension mixing** FastTab, set the **Size** option to *Yes*.</span></span> <span data-ttu-id="816b1-124">No cenário descrito neste tópico, a combinação pode ser feita somente para produtos com dimensões de **Tamanho** diferentes.</span><span class="sxs-lookup"><span data-stu-id="816b1-124">In the scenario that is described in this topic, mixing can be done only for products that have different **Size** dimensions.</span></span> <span data-ttu-id="816b1-125">No entanto, outras opções também estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="816b1-125">However, other options are also available.</span></span>
1. <span data-ttu-id="816b1-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-126">Select **Save**.</span></span>

### <a name="create-a-new-product-master-and-product-variants"></a><span data-ttu-id="816b1-127">Criar um novo produto mestre e grades de produtos</span><span class="sxs-lookup"><span data-stu-id="816b1-127">Create a new product master and product variants</span></span>

1. <span data-ttu-id="816b1-128">Vá para **Gerenciamento de informações sobre produtos \> Produtos \> Produtos mestre**.</span><span class="sxs-lookup"><span data-stu-id="816b1-128">Go to **Product information management \> Products \> Product masters**.</span></span>
1. <span data-ttu-id="816b1-129">No Painel de Ação, selecione **Novo** para criar um produto mestre.</span><span class="sxs-lookup"><span data-stu-id="816b1-129">On the Action Pane, select **New** to create a product master.</span></span>
1. <span data-ttu-id="816b1-130">Na caixa de diálogo **Novo produto**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-130">In the **New product** dialog box, set the following values:</span></span>

    - <span data-ttu-id="816b1-131">**Tipo de produto:** *Item*</span><span class="sxs-lookup"><span data-stu-id="816b1-131">**Product type:** *Item*</span></span>
    - <span data-ttu-id="816b1-132">**Subtipo de produto:** *Produto mestre*</span><span class="sxs-lookup"><span data-stu-id="816b1-132">**Product subtype:** *Product master*</span></span>
    - <span data-ttu-id="816b1-133">**Número do produto:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="816b1-133">**Product number:** *B0001*</span></span>
    - <span data-ttu-id="816b1-134">**Nome do produto:** *Tamanho B0001*</span><span class="sxs-lookup"><span data-stu-id="816b1-134">**Product name:** *B0001 Size*</span></span>
    - <span data-ttu-id="816b1-135">**Grupo de dimensões do produto:** *Tamanho*</span><span class="sxs-lookup"><span data-stu-id="816b1-135">**Product dimension group:** *Size*</span></span>
    - <span data-ttu-id="816b1-136">**Tecnologia de configuração:** *Grade predefinida*</span><span class="sxs-lookup"><span data-stu-id="816b1-136">**Configuration technology:** *Predefined variant*</span></span>

1. <span data-ttu-id="816b1-137">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b1-137">Select **OK**.</span></span>
1. <span data-ttu-id="816b1-138">Na página **Detalhes do produto**, na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-138">On the **Product details** page, on the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="816b1-139">**Gerar grades automaticamente:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="816b1-139">**Generate variants automatically:** *Yes*</span></span>
    - <span data-ttu-id="816b1-140">**Grupo de tamanhos:** *CASUALDHIR*</span><span class="sxs-lookup"><span data-stu-id="816b1-140">**Size group:** *CASUALDHIR*</span></span>

1. <span data-ttu-id="816b1-141">Para exibir as grades predefinidas, no Painel de Ação, selecione **Grades de produtos**.</span><span class="sxs-lookup"><span data-stu-id="816b1-141">To view the predefined variants, on the Action Pane, select **Product variants**.</span></span>

    <span data-ttu-id="816b1-142">A página **Grades de produtos** é exibida e mostra uma lista de grades da configuração do grupo de tamanhos.</span><span class="sxs-lookup"><span data-stu-id="816b1-142">The **Product variants** page appears and shows a list of variants from the configuration of the size group.</span></span>

### <a name="release-products-to-the-usmf-company"></a><span data-ttu-id="816b1-143">Liberar produtos para a empresa USMF</span><span class="sxs-lookup"><span data-stu-id="816b1-143">Release products to the USMF company</span></span>

1. <span data-ttu-id="816b1-144">No Painel de Ação, selecione **Liberar produtos**.</span><span class="sxs-lookup"><span data-stu-id="816b1-144">On the Action Pane, select **Release products**.</span></span>
1. <span data-ttu-id="816b1-145">Na página **Selecionar produtos para liberação**, confirme que o produto de número *B0001* está na lista e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-145">On the **Select products to release** page, confirm that product number *B0001* is in the list, and then select **Next**.</span></span>
1. <span data-ttu-id="816b1-146">Selecione **Avançar** para confirmar as grades de produtos a serem liberadas.</span><span class="sxs-lookup"><span data-stu-id="816b1-146">Select **Next** to confirm the product variants to release.</span></span>
1. <span data-ttu-id="816b1-147">Na página **Selecionar empresas para as quais os produtos serão liberados**, selecione *USMF* e, em seguida, selecione **Avançar** para confirmar a seleção.</span><span class="sxs-lookup"><span data-stu-id="816b1-147">On the **Select companies to release to** page, select *USMF*, and then select **Next** to confirm the selection.</span></span>
1. <span data-ttu-id="816b1-148">Na página **Confirmar seleção**, selecione **Concluir** para concluir a liberação.</span><span class="sxs-lookup"><span data-stu-id="816b1-148">On the **Confirm selection** page, select **Finish** to complete the release.</span></span>

    <span data-ttu-id="816b1-149">Você receberá uma mensagem "Operação concluída".</span><span class="sxs-lookup"><span data-stu-id="816b1-149">You receive an "Operation completed" message.</span></span>

### <a name="update-a-released-product-in-the-usmf-company"></a><span data-ttu-id="816b1-150">Atualizar um produto liberado na empresa USMF</span><span class="sxs-lookup"><span data-stu-id="816b1-150">Update a released product in the USMF company</span></span>

1. <span data-ttu-id="816b1-151">Entre na empresa **USMF**.</span><span class="sxs-lookup"><span data-stu-id="816b1-151">Make sure that you're signed in to the **USMF** company.</span></span>
1. <span data-ttu-id="816b1-152">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados** para concluir a criação do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="816b1-152">Go to **Product information management \> Products \> Released products** to finish creating the released product.</span></span>
1. <span data-ttu-id="816b1-153">Localize e selecione o item de número *B0001* para abrir a página **Detalhes do produto liberado**.</span><span class="sxs-lookup"><span data-stu-id="816b1-153">Find and select item number *B0001* to open the **Released product details** page.</span></span>
1. <span data-ttu-id="816b1-154">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-154">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="816b1-155">Na FastTab **Geral**, verifique se o campo **Grupo de modelo do item** está definido como *PEPS*.</span><span class="sxs-lookup"><span data-stu-id="816b1-155">On the **General** FastTab, make sure that the **Item model group** field is set to *FIFO*.</span></span>
1. <span data-ttu-id="816b1-156">No Painel de Ação, na guia **Produto**, no grupo **Configuração**, selecione **Grupos de dimensões**.</span><span class="sxs-lookup"><span data-stu-id="816b1-156">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Dimension groups**.</span></span>
1. <span data-ttu-id="816b1-157">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-157">Set the following values:</span></span>

    - <span data-ttu-id="816b1-158">**Grupo de dimensões de armazenamento:** *Ware*</span><span class="sxs-lookup"><span data-stu-id="816b1-158">**Storage dimension group:** *Ware*</span></span>
    - <span data-ttu-id="816b1-159">**Grupo de dimensões de rastreamento:** *Nenhum*</span><span class="sxs-lookup"><span data-stu-id="816b1-159">**Tracking dimension group:** *None*</span></span>

1. <span data-ttu-id="816b1-160">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b1-160">Select **OK**.</span></span>
1. <span data-ttu-id="816b1-161">No Painel de Ação, na guia **Produto**, no grupo **Configuração**, selecione **Hierarquia de reservas**.</span><span class="sxs-lookup"><span data-stu-id="816b1-161">On the Action Pane, on the **Product** tab, in the **Set up** group, select **Reservation hierarchy**.</span></span>
1. <span data-ttu-id="816b1-162">Defina o campo **Hierarquia de reservas** como *Padrão* e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b1-162">Set the **Reservation hierarchy** field to *Default*, and then select **OK**.</span></span>
1. <span data-ttu-id="816b1-163">Na FastTab **Geral**, na seção **Administração**, observe que suas seleções foram atualizadas.</span><span class="sxs-lookup"><span data-stu-id="816b1-163">On the **General** FastTab, in the **Administration** section, notice that your selections have been updated.</span></span>
1. <span data-ttu-id="816b1-164">Na FastTab **Compra**, no campo **Preço**, insira *10*.</span><span class="sxs-lookup"><span data-stu-id="816b1-164">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="816b1-165">Na FastTab **Gerenciar custos**, no campo **Grupo de itens**, insira *Áudio*.</span><span class="sxs-lookup"><span data-stu-id="816b1-165">On the **Manage costs** FastTab, in the **Item group** field, enter *Audio*.</span></span>
1. <span data-ttu-id="816b1-166">Na FastTab **Compra**, no campo **Preço**, insira *10*.</span><span class="sxs-lookup"><span data-stu-id="816b1-166">On the **Purchase** FastTab, in the **Price** field, enter *10*.</span></span>
1. <span data-ttu-id="816b1-167">Na FastTab **Depósito**, no campo **ID do grupo de sequências de unidade**, insira *ea*.</span><span class="sxs-lookup"><span data-stu-id="816b1-167">On the **Warehouse** FastTab, in the **Unit sequence group ID** field, enter *ea*.</span></span>
1. <span data-ttu-id="816b1-168">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-168">Select **Save**.</span></span>

### <a name="create-a-location-directive"></a><span data-ttu-id="816b1-169">Criar uma diretiva de localização</span><span class="sxs-lookup"><span data-stu-id="816b1-169">Create a location directive</span></span>

1. <span data-ttu-id="816b1-170">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="816b1-170">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="816b1-171">No painel esquerdo, no campo **Tipo de ordem de serviço**, selecione *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="816b1-171">In the left pane, in the **Work order type** field, select *Purchase orders*.</span></span>
1. <span data-ttu-id="816b1-172">Na lista, selecione a diretiva de localização chamada *24 PO Direct*.</span><span class="sxs-lookup"><span data-stu-id="816b1-172">In the list, select the location directive that is named *24 PO Direct*.</span></span>
1. <span data-ttu-id="816b1-173">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="816b1-173">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="816b1-174">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="816b1-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="816b1-175">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="816b1-175">**Sequence number:** *1*</span></span>

        <span data-ttu-id="816b1-176">A nova linha deve estar na frente da linha previamente existente.</span><span class="sxs-lookup"><span data-stu-id="816b1-176">The new line should be in front of the previously existing line.</span></span> <span data-ttu-id="816b1-177">Para fazer a alteração, use os botões **Mover para cima** e **Mover para baixo** na barra de ferramentas ou altere o valor do **Número de sequência** da linha existente para *2*.</span><span class="sxs-lookup"><span data-stu-id="816b1-177">To make the change, use the **Move up** and **Move down** buttons on the toolbar, or change the existing line's **Sequence number** value to *2*.</span></span>

    - <span data-ttu-id="816b1-178">**Nome:** *Colocar no Perfil de localização MASSA*</span><span class="sxs-lookup"><span data-stu-id="816b1-178">**Name:** *Put to BULK Location profile*</span></span>
    - <span data-ttu-id="816b1-179">**Uso de localização fixa:** *Localizações fixas e não fixas*</span><span class="sxs-lookup"><span data-stu-id="816b1-179">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>
    - <span data-ttu-id="816b1-180">**Permitir estoque negativo:** *Desmarcar esta caixa de seleção (=Não)*</span><span class="sxs-lookup"><span data-stu-id="816b1-180">**Allow negative inventory:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="816b1-181">**Lote habilitado:** *Desmarcar esta caixa de seleção (=Não)*</span><span class="sxs-lookup"><span data-stu-id="816b1-181">**Batch enabled:** *Clear this check box (=No)*</span></span>
    - <span data-ttu-id="816b1-182">**Estratégia:** *Nenhuma*</span><span class="sxs-lookup"><span data-stu-id="816b1-182">**Strategy:** *None*</span></span>

1. <span data-ttu-id="816b1-183">Com a nova linha ainda selecionada, selecione **Editar consulta** acima da grade.</span><span class="sxs-lookup"><span data-stu-id="816b1-183">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="816b1-184">Na caixa de diálogo de consulta, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="816b1-184">In the query dialog box, on the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="816b1-185">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="816b1-185">On the new line, set the following values:</span></span>

    - <span data-ttu-id="816b1-186">**Tabela:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="816b1-186">**Table:** *Locations*</span></span>
    - <span data-ttu-id="816b1-187">**Tabela derivada:** *Localizações*</span><span class="sxs-lookup"><span data-stu-id="816b1-187">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="816b1-188">**Campo:** *ID de perfil da localização*</span><span class="sxs-lookup"><span data-stu-id="816b1-188">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="816b1-189">**Critérios:** *MASSA*</span><span class="sxs-lookup"><span data-stu-id="816b1-189">**Criteria:** *BULK*</span></span>

1. <span data-ttu-id="816b1-190">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b1-190">Select **OK**.</span></span>
1. <span data-ttu-id="816b1-191">Na página **Diretivas de localização**, no Painel de Ação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-191">On the **Location directives** page, on the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="816b1-192">No campo **Estratégia** da FastTab **Ações de Diretiva de Localização**, se você usar a estratégia de localização *Consolidar*, a configuração da FastTab **Combinação de dimensões do produto permitida** nos **Perfis de localização** será substituída, e os itens serão colocados no mesmo local, mesmo que esse comportamento não seja permitido pela configuração.</span><span class="sxs-lookup"><span data-stu-id="816b1-192">On the **Location Directive Actions** FastTab **Strategy** field, if you use the *Consolidate* location strategy, the setup of the **Allowed product dimension mixing** FastTab on the **Location profiles** will be overridden, and items will be put to the same location even if this behavior isn't allowed by the setup.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="816b1-193">Criar um item de menu de dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="816b1-193">Create a mobile device menu item</span></span>

1. <span data-ttu-id="816b1-194">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="816b1-194">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="816b1-195">No Painel de Ação, selecione **Novo** para criar um item de menu a ser usado para classificação.</span><span class="sxs-lookup"><span data-stu-id="816b1-195">On the Action Pane, select **New** to create a menu item to use for sorting.</span></span>
1. <span data-ttu-id="816b1-196">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-196">In the header, set the following values:</span></span>

    - <span data-ttu-id="816b1-197">**Nome do item de menu:** *Recebimento da linha da OC*</span><span class="sxs-lookup"><span data-stu-id="816b1-197">**Menu item name:** *PO line receiving*</span></span>
    - <span data-ttu-id="816b1-198">**Título:** *Recebimento da linha da OC*</span><span class="sxs-lookup"><span data-stu-id="816b1-198">**Title:** *PO line receiving*</span></span>
    - <span data-ttu-id="816b1-199">**Modo:** *Trabalho*</span><span class="sxs-lookup"><span data-stu-id="816b1-199">**Mode:** *Work*</span></span>
    - <span data-ttu-id="816b1-200">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="816b1-200">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="816b1-201">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-201">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="816b1-202">**Processo de criação de trabalho:** *Recebimento e armazenamento da linha da ordem de compra*</span><span class="sxs-lookup"><span data-stu-id="816b1-202">**Work creation process:** *Purchase order line receiving and putaway*</span></span>
    - <span data-ttu-id="816b1-203">**Gerar placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="816b1-203">**Generate license plate:** *Yes*</span></span>

1. <span data-ttu-id="816b1-204">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-204">Select **Save**.</span></span>

### <a name="configure-the-mobile-device-menu"></a><span data-ttu-id="816b1-205">Configurar o menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="816b1-205">Configure the mobile device menu</span></span>

1. <span data-ttu-id="816b1-206">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="816b1-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="816b1-207">Na lista de menus, selecione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="816b1-207">In the list of menus, select **Inbound**.</span></span>
1. <span data-ttu-id="816b1-208">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-208">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="816b1-209">Na lista **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Recebimento da linha da OC**.</span><span class="sxs-lookup"><span data-stu-id="816b1-209">In the **Available Menus And Menu Items** list, find and select the **PO line receiving** menu item.</span></span>
1. <span data-ttu-id="816b1-210">Selecione o botão de seta para a direita a fim de mover o item de menu **Recebimento da linha da OC** para a lista **Estrutura de Menu**.</span><span class="sxs-lookup"><span data-stu-id="816b1-210">Select the right arrow button to move the **PO line receiving** menu item to the **Menu Structure** list.</span></span> <span data-ttu-id="816b1-211">Dessa forma, você adiciona o novo item de menu ao menu selecionado.</span><span class="sxs-lookup"><span data-stu-id="816b1-211">In this way, you add your new menu item to the selected menu.</span></span>
1. <span data-ttu-id="816b1-212">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-212">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="816b1-213">Cenário</span><span class="sxs-lookup"><span data-stu-id="816b1-213">Scenario</span></span>

<span data-ttu-id="816b1-214">Este cenário de demonstração mostra como duas grades de produtos diferentes podem ser colocadas no mesmo local quando o perfil de localização não permite itens mistos, mas o recurso *Combinação de dimensões do produto de localização* está habilitado.</span><span class="sxs-lookup"><span data-stu-id="816b1-214">This demo scenario shows how two different product variants can be put to the same location when the location profile doesn't allow for mixed items, but the *Location product dimension mixing* feature is enabled.</span></span> <span data-ttu-id="816b1-215">Nesse caso, você usará a grade **Tamanho** como o critério.</span><span class="sxs-lookup"><span data-stu-id="816b1-215">In this case, you will use the **Size** variant as the criterion.</span></span>

<span data-ttu-id="816b1-216">Antes de começar, verifique se há locais vazios no depósito *24* que usem o perfil de localização *MASSA*.</span><span class="sxs-lookup"><span data-stu-id="816b1-216">Before you begin, make sure that there are empty locations in warehouse *24* that use the *BULK* location profile.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="816b1-217">Criar uma ordem de compra</span><span class="sxs-lookup"><span data-stu-id="816b1-217">Create a purchase order</span></span>

<span data-ttu-id="816b1-218">Você criará uma ordem de compra com três linhas: duas linhas para o mesmo número de produto, mas diferentes grades de **Tamanho**, e uma terceira linha para um produto diferente que não tem grades.</span><span class="sxs-lookup"><span data-stu-id="816b1-218">You will create a purchase order that has three lines: two lines for the same product number but different **Size** variants, and a third line for a different product that has no variants.</span></span>

1. <span data-ttu-id="816b1-219">Vá para **Contas a pagar \> Ordens de compra \> Todas as ordens de compra**.</span><span class="sxs-lookup"><span data-stu-id="816b1-219">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="816b1-220">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="816b1-220">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="816b1-221">Na caixa de diálogo **Criar ordem de compra**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-221">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="816b1-222">**Conta do fornecedor:** *1001*</span><span class="sxs-lookup"><span data-stu-id="816b1-222">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="816b1-223">**Depósito:** *24*</span><span class="sxs-lookup"><span data-stu-id="816b1-223">**Warehouse:** *24*</span></span>

1. <span data-ttu-id="816b1-224">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="816b1-224">Select **OK**.</span></span>
1. <span data-ttu-id="816b1-225">A ordem de compra é criada e uma nova linha é adicionada à FastTab **Linhas da ordem de compra**.</span><span class="sxs-lookup"><span data-stu-id="816b1-225">The purchase order is created, and a new line is added on the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="816b1-226">Anote o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-226">Make a note of the purchase order number.</span></span>
1. <span data-ttu-id="816b1-227">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="816b1-227">On the new line, set the following values:</span></span>

    - <span data-ttu-id="816b1-228">**Número de item:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="816b1-228">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="816b1-229">**Tamanho** *G*</span><span class="sxs-lookup"><span data-stu-id="816b1-229">**Size** *L*</span></span>
    - <span data-ttu-id="816b1-230">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="816b1-230">**Quantity:** *2*</span></span>

1. <span data-ttu-id="816b1-231">Selecione **Adicionar linha** acima da grade para adicionar uma segunda linha da ordem de compra e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-231">Select **Add line** above the grid to add a second purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="816b1-232">**Número de item:** *B0001*</span><span class="sxs-lookup"><span data-stu-id="816b1-232">**Item number:** *B0001*</span></span>
    - <span data-ttu-id="816b1-233">**Tamanho** *GG*</span><span class="sxs-lookup"><span data-stu-id="816b1-233">**Size** *XL*</span></span>
    - <span data-ttu-id="816b1-234">**Quantidade:** *2*</span><span class="sxs-lookup"><span data-stu-id="816b1-234">**Quantity:** *2*</span></span>

1. <span data-ttu-id="816b1-235">Selecione **Adicionar linha** para adicionar uma terceira linha da ordem de compra e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="816b1-235">Select **Add line** to add a third purchase order line, and set the following values:</span></span>

    - <span data-ttu-id="816b1-236">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="816b1-236">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="816b1-237">**Quantidade:** *1*</span><span class="sxs-lookup"><span data-stu-id="816b1-237">**Quantity:** *1*</span></span>

<span data-ttu-id="816b1-238">1.Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-238">1.Select **Save**.</span></span>

### <a name="receive-purchase-order-lines-in-the-warehouse-app"></a><span data-ttu-id="816b1-239">Receber linhas da ordem de compra no aplicativo de depósito</span><span class="sxs-lookup"><span data-stu-id="816b1-239">Receive purchase order lines in the warehouse app</span></span>

1. <span data-ttu-id="816b1-240">Entre no aplicativo de depósito como um usuário habilitado para o depósito *24*.</span><span class="sxs-lookup"><span data-stu-id="816b1-240">Sign in to the warehouse app as a user who is enabled for warehouse *24*.</span></span>
1. <span data-ttu-id="816b1-241">Selecione o menu **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="816b1-241">Select the **Inbound** menu.</span></span>
1. <span data-ttu-id="816b1-242">Selecione **Recebimento da Linha da OC**.</span><span class="sxs-lookup"><span data-stu-id="816b1-242">Select **PO Line receiving**.</span></span>
1. <span data-ttu-id="816b1-243">Selecione o campo **PONUM** e insira o número da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-243">Select the **PONUM** field, and then enter the purchase order number.</span></span>
1. <span data-ttu-id="816b1-244">Confirme a entrada selecionando o botão de confirmação ( ✔ ) na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="816b1-244">Confirm your entry by selecting the confirm button ( ✔ ) at the bottom of the page.</span></span>
1. <span data-ttu-id="816b1-245">Insira o número da linha da ordem de compra que está sendo recebida.</span><span class="sxs-lookup"><span data-stu-id="816b1-245">Enter the line number from the purchase order that is being received.</span></span> <span data-ttu-id="816b1-246">Selecione o campo **LINENUM** e use o teclado numérico para inserir *1*.</span><span class="sxs-lookup"><span data-stu-id="816b1-246">Select the **LINENUM** field, and then use the number pad to enter *1*.</span></span>
1. <span data-ttu-id="816b1-247">Confirme a entrada.</span><span class="sxs-lookup"><span data-stu-id="816b1-247">Confirm your entry.</span></span>
1. <span data-ttu-id="816b1-248">Insira a quantidade a ser recebida.</span><span class="sxs-lookup"><span data-stu-id="816b1-248">Enter the quantity to receive.</span></span> <span data-ttu-id="816b1-249">Selecione o botão de sinal de adição (**+**) duas vezes para aumentar o valor no campo **Qtd.** para *2*.</span><span class="sxs-lookup"><span data-stu-id="816b1-249">Select the plus sign (**+**) button two times to increase the value in the **Qty** field to *2*.</span></span>
1. <span data-ttu-id="816b1-250">Registre a entrada selecionando o botão ( ✔ ) na parte inferior da página e, em seguida, confirme a entrada selecionando o botão ( ✔ ) novamente.</span><span class="sxs-lookup"><span data-stu-id="816b1-250">Register your entry by selecting the button ( ✔ ) at the bottom of the page, and then confirm your entry by selecting the button ( ✔ ) again.</span></span>
1. <span data-ttu-id="816b1-251">Veja as informações na página **Ordens de compra: colocar**.</span><span class="sxs-lookup"><span data-stu-id="816b1-251">View the information on the **Purchase orders: Put** page.</span></span> <span data-ttu-id="816b1-252">Essa página mostra o trabalho criado para o armazenamento (Trabalho 1).</span><span class="sxs-lookup"><span data-stu-id="816b1-252">This page shows the work that has been created for the put-away (Work 1).</span></span>

    <span data-ttu-id="816b1-253">O local onde o item recebido será armazenado, a placa de licença​, o item, o tamanho e a quantidade da tarefa **Recebimento da Linha da OC** que você acabou de concluir são exibidos.</span><span class="sxs-lookup"><span data-stu-id="816b1-253">The location where the received item will be put away, the license plate, the item, the size, and the quantity of the **PO Line receiving** task that you just completed are shown.</span></span>

1. <span data-ttu-id="816b1-254">Confirme o trabalho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="816b1-254">Confirm the put-away work.</span></span>
1. <span data-ttu-id="816b1-255">Repita as etapas 4 a 11 para a linha 2 da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-255">Repeat the steps 4 through 11 for the purchase order line 2.</span></span> <span data-ttu-id="816b1-256">No entanto, na etapa 8, especifique uma quantidade de *1*.</span><span class="sxs-lookup"><span data-stu-id="816b1-256">However, in step 8, specify a quantity of *1*.</span></span>

    <span data-ttu-id="816b1-257">Um novo trabalho de armazenamento (Trabalho 2) é criado para o mesmo local que o Trabalho 1.</span><span class="sxs-lookup"><span data-stu-id="816b1-257">New put-away work (Work 2) is created for the same location as Work 1.</span></span>

1. <span data-ttu-id="816b1-258">Repita as etapas 4 a 11 novamente para a linha 2 da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-258">Repeat the steps 4 through 11 again for purchase order line 2.</span></span> <span data-ttu-id="816b1-259">Na etapa 8, especifique a quantidade restante de *1*.</span><span class="sxs-lookup"><span data-stu-id="816b1-259">In step 8, specify the remaining quantity of *1*.</span></span>

    <span data-ttu-id="816b1-260">Um novo trabalho de armazenamento (Trabalho 3) é criado para o mesmo local que o Trabalho 1 e o Trabalho 2.</span><span class="sxs-lookup"><span data-stu-id="816b1-260">New put-away work (Work 3) is created for the same location as Work 1 and Work 2.</span></span> <span data-ttu-id="816b1-261">Esse comportamento ocorre porque a estratégia da diretiva de localização *Consolidar* é usada, e a FastTab **Combinação de dimensões do produto permitida** na configuração de **Perfis de localização** *Massa* permite que a grade **Tamanho** seja combinada em um local.</span><span class="sxs-lookup"><span data-stu-id="816b1-261">This behavior occurs because the *Consolidate* location directive strategy is used, and the **Allowed product dimension mixing** FastTab on the *Bulk* **Location profiles** setup allows the **Size** variant to be mixed on a location.</span></span>

1. <span data-ttu-id="816b1-262">Repita as etapas 4 a 11 para a linha 3 da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-262">Repeat the steps 4 through 11 for purchase order line 3.</span></span> <span data-ttu-id="816b1-263">Na etapa 8, especifique uma quantidade de *1* para o item de número *A0001*.</span><span class="sxs-lookup"><span data-stu-id="816b1-263">In step 8, specify a quantity of *1* for item number *A0001*.</span></span>

    <span data-ttu-id="816b1-264">Um novo trabalho de armazenamento (Trabalho 4) é criado para um local diferente do local usado para as linhas 1 e 2 da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="816b1-264">New put-away work (Work 4) is created for a different location than the location that is used for purchase order lines 1 and 2.</span></span> <span data-ttu-id="816b1-265">Esse comportamento ocorre porque o perfil de localização não permite produtos mistos, mas permite dimensões mistas do mesmo produto mestre.</span><span class="sxs-lookup"><span data-stu-id="816b1-265">This behavior occurs because the location profile doesn't allow for mixed products, but it does allow for mixed dimensions of the same product master.</span></span>

1. <span data-ttu-id="816b1-266">Selecione o botão Menu na parte superior da página (às vezes chamado de hambúrguer ou botão de hambúrguer) e, em seguida, selecione **Cancelar** para sair do **Recebimento da Linha da OC**.</span><span class="sxs-lookup"><span data-stu-id="816b1-266">Select the Menu button at the top of the page (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit **PO Line receiving**.</span></span>

> [!TIP]
> <span data-ttu-id="816b1-267">Você pode repetir esse cenário, mas desta vez, defina **Tamanho** - *Não* na FastTab **Permitir combinação de dimensões do produto** nos **Perfis de localização** *MASSA*, para que nenhuma dimensão do produto seja combinada.</span><span class="sxs-lookup"><span data-stu-id="816b1-267">You can repeat this scenario, but this time, set **Size** - *No* under the **Allow product dimension mixing** FastTab on the *BULK* **Location profiles**, so that none of the product dimensions can be mixed.</span></span> <span data-ttu-id="816b1-268">Nesse caso, quando você receber a ordem de compra, cada grade de produto será colocada em um novo local.</span><span class="sxs-lookup"><span data-stu-id="816b1-268">In this case, when you receive the purchase order, each product variant will be put to a new location.</span></span>