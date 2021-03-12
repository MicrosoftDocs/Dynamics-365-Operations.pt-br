---
title: Colocar no mural - colocar na loja
description: Este tópico fornece informações sobre a funcionalidade Colocar no mural - colocar na loja. Essa funcionalidade permite trabalhar com cenários onde você deve consolidar um produto em uma área de preparo do pacote com base em critérios configuráveis. Ela ajuda a diminuir o tempo de separação porque permite separar em uma única placa de licença de destino e pode usar mais posições de colocação do que a separação de cluster.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationType, WHSLocationProfile, WHSLocation, WHSPackProfile, WHSWaveStepCode, WHSOutboundSortTemplate, WHSPostMethod, WHSWaveTemplateTable, WHSLocDirTable, WHSWorkClass, WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 3f2ae63758fcb6247c5e56433645d9252576c755
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996263"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="fd31e-105">Colocar no mural - colocar na loja</span><span class="sxs-lookup"><span data-stu-id="fd31e-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd31e-106">A funcionalidade *Colocar no mural - colocar na loja* permite trabalhar com cenários onde você deve consolidar um produto em uma área de preparo do pacote com base em critérios configuráveis.</span><span class="sxs-lookup"><span data-stu-id="fd31e-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="fd31e-107">Como essa funcionalidade permite separar em uma única placa de licença de destino e pode usar mais posições de colocação do que a separação de cluster, as empresas que enviam para lojas ou processam itens pequenos se beneficiarão com a redução do tempo de separação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="fd31e-108">O fluxo de trabalho dessa funcionalidade direciona o produto separado para uma localização de classificação para distribuição em vários tipos de contêineres.</span><span class="sxs-lookup"><span data-stu-id="fd31e-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="fd31e-109">Geralmente, cada localização de classificação inclui várias posições de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="fd31e-110">Cada posição de classificação é atribuída de acordo com os critérios definidos pelo processo empresarial.</span><span class="sxs-lookup"><span data-stu-id="fd31e-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="fd31e-111">Os critérios típicos são destino final, remessa ou carga.</span><span class="sxs-lookup"><span data-stu-id="fd31e-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="fd31e-112">Depois que um produto chega, ele é distribuído para cada posição de classificação com base na quantidade associada à ordem, ao destino, à remessa ou à carga.</span><span class="sxs-lookup"><span data-stu-id="fd31e-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="fd31e-113">Quando um contêiner está cheio ou completo, ele passa para um local de preparo ou um local de remessa para processamento extra, dependendo do processo empresarial.</span><span class="sxs-lookup"><span data-stu-id="fd31e-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="fd31e-114">Essa funcionalidade de depósito também é conhecida por outros nomes, como put-to-light e break opens.</span><span class="sxs-lookup"><span data-stu-id="fd31e-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="fd31e-115">Ativar o recurso Classificação de saída</span><span class="sxs-lookup"><span data-stu-id="fd31e-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="fd31e-116">Para que você possa usar a funcionalidade *Colocar no mural - colocar na loja*, o recurso *Classificação de saída* deve estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="fd31e-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="fd31e-117">Os administradores podem usar o espaço de trabalho [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário.</span><span class="sxs-lookup"><span data-stu-id="fd31e-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="fd31e-118">Nesse caso, o recurso é listado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="fd31e-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="fd31e-119">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="fd31e-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fd31e-120">**Nome do recurso:** *classificação de saída*</span><span class="sxs-lookup"><span data-stu-id="fd31e-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="fd31e-121">O recurso *Classificação de saída* pode ser usado junto com o recurso *Código da etapa da onda em toda a organização* se estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="fd31e-122">Você também deve ativar esse recurso se for usar códigos predefinidos configurados nos códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="fd31e-123">No espaço de trabalho **Gerenciamento de recursos**, este recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="fd31e-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="fd31e-124">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="fd31e-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="fd31e-125">**Nome do recurso:** *Código da etapa da onda em toda a organização*</span><span class="sxs-lookup"><span data-stu-id="fd31e-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="fd31e-126">Instalação</span><span class="sxs-lookup"><span data-stu-id="fd31e-126">Setup</span></span>

<span data-ttu-id="fd31e-127">Para esta demonstração, são usados os dados da Contoso e o depósito *62* como padrão.</span><span class="sxs-lookup"><span data-stu-id="fd31e-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="fd31e-128">Alguns acréscimos observados posteriormente também são usados.</span><span class="sxs-lookup"><span data-stu-id="fd31e-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="fd31e-129">Tipo de localização</span><span class="sxs-lookup"><span data-stu-id="fd31e-129">Location type</span></span>

1. <span data-ttu-id="fd31e-130">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Tipos de localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="fd31e-131">No Painel de Ação, selecione **Novo** para criar um tipo de localização para classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="fd31e-132">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-132">Set the following values:</span></span>

    - <span data-ttu-id="fd31e-133">**Tipo de localização:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="fd31e-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="fd31e-134">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="fd31e-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="fd31e-136">Parâmetros de gerenciamento de depósito</span><span class="sxs-lookup"><span data-stu-id="fd31e-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="fd31e-137">Vá para **Gerenciamento de depósito \> Configuração \> Parâmetros de gerenciamento de depósito**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="fd31e-138">Na guia **Geral**, na FastTab **Tipos de localização**, no campo **Tipo de localização de classificação**, insira *CLASSIFICAR*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="fd31e-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="fd31e-140">Perfil de localização</span><span class="sxs-lookup"><span data-stu-id="fd31e-140">Location profile</span></span>

1. <span data-ttu-id="fd31e-141">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="fd31e-142">No Painel de Ação, selecione **Novo** para criar um perfil de localização para a localização de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="fd31e-143">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="fd31e-144">**ID do perfil de localização:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-145">**Nome:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="fd31e-146">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fd31e-147">**Formato de localização:** *EMBALAR*</span><span class="sxs-lookup"><span data-stu-id="fd31e-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="fd31e-148">**Tipo de localização:** *CLASSIFICAR*</span><span class="sxs-lookup"><span data-stu-id="fd31e-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="fd31e-149">**Usar rastreamento da placa de licença:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="fd31e-150">**Permitir itens mistos:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="fd31e-151">**Permitir status de estoque mistos:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="fd31e-152">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="fd31e-153">Localizações</span><span class="sxs-lookup"><span data-stu-id="fd31e-153">Locations</span></span>

1. <span data-ttu-id="fd31e-154">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Localizações**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="fd31e-155">Desmarque a caixa de seleção **Gerar dígitos de verificação para localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="fd31e-156">No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="fd31e-157">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="fd31e-158">**Localização:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-159">**ID do perfil de localização:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="fd31e-160">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="fd31e-161">Perfis de embalagem</span><span class="sxs-lookup"><span data-stu-id="fd31e-161">Packing profiles</span></span>

1. <span data-ttu-id="fd31e-162">Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Perfis de embalagem**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="fd31e-163">No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="fd31e-164">**ID do perfil de embalagem:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-165">**Descrição:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-166">**Diretiva de embalagem de contêiner:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="fd31e-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="fd31e-167">**Modo de ID do Contêiner:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="fd31e-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="fd31e-168">**Tipo de contêiner:** *PALETE 48X48*</span><span class="sxs-lookup"><span data-stu-id="fd31e-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="fd31e-169">**Criar automaticamente contêiner no fechamento do contêiner:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="fd31e-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="fd31e-170">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="fd31e-171">Códigos da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="fd31e-171">Wave step codes</span></span>

<span data-ttu-id="fd31e-172">Se você ativou o recurso *Código da etapa da onda em toda a organização*, configure o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd31e-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="fd31e-173">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Códigos da etapa da onda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="fd31e-174">No Painel de Ação, selecione **Novo** e, depois, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="fd31e-175">**Código da etapa da onda:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-176">**Descrição da etapa da onda:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-177">**Tipo de etapa de onda:** *Modelo de classificação*</span><span class="sxs-lookup"><span data-stu-id="fd31e-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="fd31e-178">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="fd31e-179">Modelo de classificação de saída</span><span class="sxs-lookup"><span data-stu-id="fd31e-179">Outbound sorting template</span></span>

<span data-ttu-id="fd31e-180">O modelo de classificação controla se as posições de classificação são criadas, quais critérios são usados e outros atributos do processo de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="fd31e-181">Vá para **Gerenciamento de depósito \> Configuração \> Embalagem \> Modelo de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="fd31e-182">No Painel de Ação, selecione **Novo** para criar um modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="fd31e-183">No cabeçalho do novo modelo, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="fd31e-184">**ID do modelo de classificação de saída:** *Classificação de Onda*</span><span class="sxs-lookup"><span data-stu-id="fd31e-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="fd31e-185">**Descrição:** *Classificação de onda*</span><span class="sxs-lookup"><span data-stu-id="fd31e-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="fd31e-186">**Tipo de modelo de classificação:** *Demanda da onda*</span><span class="sxs-lookup"><span data-stu-id="fd31e-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="fd31e-187">Este campo define o processo para o qual o modelo de classificação é usado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="fd31e-188">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fd31e-188">The following values are available:</span></span>

        - <span data-ttu-id="fd31e-189">**Demanda da onda** – O modelo de classificação é usado para o processo *Colocar no mural*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="fd31e-190">Este tipo de modelo é usado para ignorar a estação de embalagem e processar o estoque diretamente da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="fd31e-191">Você só poderá usá-lo se o método do processo de onda **classificação** estiver incluído no modelo da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="fd31e-192">**Contêiner** – O modelo de classificação é usado para o processo *Criação do palete após embalagem*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="fd31e-193">Este tipo de modelo é usado para processar os contêineres que estão fechados na estação de embalagem e que devem ser classificados em paletes.</span><span class="sxs-lookup"><span data-stu-id="fd31e-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="fd31e-194">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="fd31e-195">**Localização:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="fd31e-196">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fd31e-197">**Verificação de classificação:** *Verificação da posição*</span><span class="sxs-lookup"><span data-stu-id="fd31e-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="fd31e-198">Este campo define a verificação necessária durante a classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="fd31e-199">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fd31e-199">The following values are available:</span></span>

        - <span data-ttu-id="fd31e-200">Nemhum(a)</span><span class="sxs-lookup"><span data-stu-id="fd31e-200">None</span></span>
        - <span data-ttu-id="fd31e-201">Verificação da placa de licença</span><span class="sxs-lookup"><span data-stu-id="fd31e-201">License plate scan</span></span>
        - <span data-ttu-id="fd31e-202">Verificação da posição</span><span class="sxs-lookup"><span data-stu-id="fd31e-202">Position scan</span></span>

    - <span data-ttu-id="fd31e-203">**Criar trabalho no fechamento da posição:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="fd31e-204">Se esta opção for definida como *Sim*, quando a posição for fechada, será criado um trabalho para mover o estoque para a localização da remessa final.</span><span class="sxs-lookup"><span data-stu-id="fd31e-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="fd31e-205">Se ela for definida como *Não*, o estoque será separado imediatamente para a ordem quando a posição for fechada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="fd31e-206">**Atribuição da posição:** *Manual*</span><span class="sxs-lookup"><span data-stu-id="fd31e-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="fd31e-207">Este campo define o tipo de atribuição de posição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="fd31e-208">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fd31e-208">The following values are available:</span></span>

        - <span data-ttu-id="fd31e-209">**Manual** – O usuário sempre deve indicar a posição para classificar o estoque.</span><span class="sxs-lookup"><span data-stu-id="fd31e-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="fd31e-210">**Automática** – O sistema guiará o estoque automaticamente para uma posição sempre que possível, com base nas divisões do modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="fd31e-211">**Atribuir critérios de posição de classificação:** *Usar apenas a posição vazia*</span><span class="sxs-lookup"><span data-stu-id="fd31e-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="fd31e-212">Este campo controla se o estoque já presente nas posições de classificação é considerado quando uma posição é atribuída para a demanda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="fd31e-213">Os valores a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="fd31e-213">The following values are available:</span></span>

        - <span data-ttu-id="fd31e-214">**Usar apenas a posição vazia** – As posições que já têm estoque associado serão levadas em consideração</span><span class="sxs-lookup"><span data-stu-id="fd31e-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="fd31e-215">**Assumir posição vazia** – Qualquer estoque que já esteja na posição será ignorado durante a atribuição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="fd31e-216">Todas as posições disponíveis serão usadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-216">All available positions will be used.</span></span>

    - <span data-ttu-id="fd31e-217">**Código da etapa da onda:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="fd31e-218">Se o recurso *Código da etapa da onda em toda a organização* estiver ativado, o código da etapa da onda *Classificar* também deverá ser configurado em códigos da etapa da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="fd31e-219">**Posição de classificação de fechamento automático:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="fd31e-220">Se essa opção for definida como *Sim*, a posição de classificação será fechada automaticamente quando todo o trabalho recebido na posição for concluído.</span><span class="sxs-lookup"><span data-stu-id="fd31e-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="fd31e-221">**Número de posições de classificação:** *3*</span><span class="sxs-lookup"><span data-stu-id="fd31e-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="fd31e-222">Este campo define o número máximo de posições de classificação que o sistema irá criar.</span><span class="sxs-lookup"><span data-stu-id="fd31e-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="fd31e-223">**Prefixo da posição de classificação:** *SP-*</span><span class="sxs-lookup"><span data-stu-id="fd31e-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="fd31e-224">Este campo define o prefixo que o sistema atribui antes do número da posição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="fd31e-225">**Posição de classificação com embalagem automática:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="fd31e-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="fd31e-226">Se esta opção for definida como *Sim*, o estoque na posição de classificação será embalado em um contêiner quando a posição for fechada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="fd31e-227">**ID do perfil de embalagem:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="fd31e-228">O campo define o perfil de embalagem que será usado quando a posição de classificação for embalada em um contêiner.</span><span class="sxs-lookup"><span data-stu-id="fd31e-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="fd31e-229">No Painel de Ação, selecione **Editar consulta** para especificar os critérios usados para esse modelo de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="fd31e-230">Na caixa de diálogo de consulta, na guia **Classificação**, selecione **Novo** para adicionar uma linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="fd31e-231">**Tabela:** *Detalhes da carga*</span><span class="sxs-lookup"><span data-stu-id="fd31e-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="fd31e-232">**Tabela derivada:** *Detalhes da carga*</span><span class="sxs-lookup"><span data-stu-id="fd31e-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="fd31e-233">**Campo:** *ID da Remessa*</span><span class="sxs-lookup"><span data-stu-id="fd31e-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="fd31e-234">**Direção da pesquisa:** *Crescente*</span><span class="sxs-lookup"><span data-stu-id="fd31e-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="fd31e-235">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-235">Select **OK**.</span></span>
1. <span data-ttu-id="fd31e-236">Você poderá receber a seguinte mensagem: "O agrupamento será redefinido, continuar?"</span><span class="sxs-lookup"><span data-stu-id="fd31e-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="fd31e-237">Selecione **Sim**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-237">Select **Yes**.</span></span>

    <span data-ttu-id="fd31e-238">O botão **Divisões do modelo de classificação de saída** no Painel de Ação ficará disponível.</span><span class="sxs-lookup"><span data-stu-id="fd31e-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="fd31e-239">No Painel de Ação, selecione **Divisões do modelo de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="fd31e-240">Selecione a caixa de diálogo **Agrupar por campo** para agrupar por ID da remessa.</span><span class="sxs-lookup"><span data-stu-id="fd31e-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="fd31e-241">Esta configuração criará uma posição de classificação por remessa que é um contêiner na onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="fd31e-242">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="fd31e-243">Métodos de processo de onda</span><span class="sxs-lookup"><span data-stu-id="fd31e-243">Wave process methods</span></span>

1. <span data-ttu-id="fd31e-244">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Métodos de processo de onda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="fd31e-245">No Painel de Ação, selecione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="fd31e-246">O método de **classificação** é adicionado à lista de métodos disponíveis e o tipo de modelo de onda *Remessa* é selecionado para ele.</span><span class="sxs-lookup"><span data-stu-id="fd31e-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="fd31e-247">Modelos de onda</span><span class="sxs-lookup"><span data-stu-id="fd31e-247">Wave templates</span></span>

<span data-ttu-id="fd31e-248">Edite o modelo de onda usado para classificação de demanda da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="fd31e-249">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="fd31e-250">No campo **Tipo de modelo de onda**, selecione *Remessa*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="fd31e-251">Selecione o modelo **Padrão de remessa 62** existente.</span><span class="sxs-lookup"><span data-stu-id="fd31e-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="fd31e-252">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fd31e-253">Na FastTab **Geral**, faça as seguintes alterações:</span><span class="sxs-lookup"><span data-stu-id="fd31e-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="fd31e-254">Defina a opção **Processar onda na liberação para o depósito** como *Não*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="fd31e-255">Defina a opção **Atribuir às ondas abertas** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="fd31e-256">Na FastTab **Métodos**, configure o método de **classificação**:</span><span class="sxs-lookup"><span data-stu-id="fd31e-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="fd31e-257">Na grade **Métodos Restantes**, selecione **classificação**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="fd31e-258">Selecione o botão de seta para a direita para mover **classificação** para a grade **Métodos Selecionados**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="fd31e-259">Na grade **Métodos Selecionados**, selecione **classificação**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="fd31e-260">Defina o campo **Código da etapa da onda** como *Classificar*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="fd31e-261">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="fd31e-262">Itens de menu do dispositivo móvel</span><span class="sxs-lookup"><span data-stu-id="fd31e-262">Mobile device menu items</span></span>

1. <span data-ttu-id="fd31e-263">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Itens de menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fd31e-264">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fd31e-265">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="fd31e-266">**Nome do item de menu:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-267">**Título:** *Classificar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="fd31e-268">**Modo:** *Indireto*</span><span class="sxs-lookup"><span data-stu-id="fd31e-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="fd31e-269">**Usar trabalho existente:** *Não*</span><span class="sxs-lookup"><span data-stu-id="fd31e-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="fd31e-270">Na FastTab **Geral**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fd31e-271">**Código de atividade:** *Classificação de saída*</span><span class="sxs-lookup"><span data-stu-id="fd31e-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="fd31e-272">**Usar guia de processo:** *Sim* (valor padrão)</span><span class="sxs-lookup"><span data-stu-id="fd31e-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="fd31e-273">**ID do modelo de classificação de saída:** *Classificação de Onda*</span><span class="sxs-lookup"><span data-stu-id="fd31e-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="fd31e-274">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="fd31e-275">Menu de dispositivos móveis</span><span class="sxs-lookup"><span data-stu-id="fd31e-275">Mobile device menu</span></span>

1. <span data-ttu-id="fd31e-276">Vá para **Gerenciamento de depósito \> Configuração \> Dispositivo móvel \> Menu do dispositivo móvel**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="fd31e-277">Na lista de menus, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="fd31e-278">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fd31e-279">Na grade **Menus e Itens de Menu Disponíveis**, localize e selecione o item de menu **Classificar** que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="fd31e-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="fd31e-280">Selecione o botão de seta para a direita para mover **Classificar** para a grade **Estrutura de Menu**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="fd31e-281">Dessa forma, você adiciona o item de menu ao menu **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="fd31e-282">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="fd31e-283">Diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="fd31e-283">Location directives</span></span>

<span data-ttu-id="fd31e-284">Você deve criar diretivas de localização para orientar o trabalho criado depois que a classificação for concluída.</span><span class="sxs-lookup"><span data-stu-id="fd31e-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="fd31e-285">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="fd31e-286">No campo **Tipo de ordem de trabalho**, selecione *Separação do estoque classificado*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="fd31e-287">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fd31e-288">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="fd31e-289">**Sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="fd31e-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="fd31e-290">**Nome:** *Colocar em Baydoor*</span><span class="sxs-lookup"><span data-stu-id="fd31e-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="fd31e-291">Na FastTab **Diretivas de localização**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fd31e-292">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="fd31e-293">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="fd31e-293">**Site:** *6*</span></span>
    - <span data-ttu-id="fd31e-294">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="fd31e-295">**Código de diretiva:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="fd31e-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="fd31e-296">**Várias SKUs:** *Não*</span><span class="sxs-lookup"><span data-stu-id="fd31e-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="fd31e-297">Selecione **Salvar** para disponibilizar a FastTab **Linhas**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="fd31e-298">Na FastTab **Linhas**, selecione **Novo** e defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd31e-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="fd31e-299">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="fd31e-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="fd31e-300">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="fd31e-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="fd31e-301">**Quantidade inicial:** *0*</span><span class="sxs-lookup"><span data-stu-id="fd31e-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="fd31e-302">**Quantidade final:** *1000000*</span><span class="sxs-lookup"><span data-stu-id="fd31e-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="fd31e-303">Selecione **Salvar** para disponibilizar a FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="fd31e-304">Na FastTab **Ações de Diretiva de Localização**, selecione **Novo** e defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd31e-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="fd31e-305">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="fd31e-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="fd31e-306">**Número de sequência:** *1*</span><span class="sxs-lookup"><span data-stu-id="fd31e-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="fd31e-307">**Nome:** *Porta da baía*</span><span class="sxs-lookup"><span data-stu-id="fd31e-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="fd31e-308">Selecione **Salvar** para disponibilizar o botão **Editar consulta** na FastTab **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="fd31e-309">Na FastTab **Ações de Diretiva de Localização**, selecione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="fd31e-310">Na caixa de diálogo de consulta, na guia **Intervalo**, localize a linha na qual o campo **Campo** está definido como *Local*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="fd31e-311">Defina o campo **Critérios** dessa linha como *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="fd31e-312">Selecione **OK** para confirmar a edição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="fd31e-313">Classes de trabalho</span><span class="sxs-lookup"><span data-stu-id="fd31e-313">Work classes</span></span>

1. <span data-ttu-id="fd31e-314">Vá para **Gerenciamento de depósito \> Configuração \> Trabalho \> Classes de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="fd31e-315">No Painel de Ações, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fd31e-316">No cabeçalho, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="fd31e-317">**ID da classe de trabalho:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="fd31e-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="fd31e-318">**Descrição:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="fd31e-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="fd31e-319">**Tipo de ordem de serviço:** *Separação do estoque classificado*</span><span class="sxs-lookup"><span data-stu-id="fd31e-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="fd31e-320">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="fd31e-321">Modelos do trabalho</span><span class="sxs-lookup"><span data-stu-id="fd31e-321">Work templates</span></span>

1. <span data-ttu-id="fd31e-322">Vá para **Gerenciamento de depósito \> Trabalho \> Modelos de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="fd31e-323">No campo **Tipo de ordem de trabalho**, selecione *Ordens de compra*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="fd31e-324">Na grade, selecione o modelo de trabalho **62 Separar para embalar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="fd31e-325">No Painel de Ação, selecione **Quebras de cabeçalho de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="fd31e-326">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fd31e-327">Na linha em que o campo **Nome do campo** está definido como *ID da Remessa*, desmarque a caixa de seleção **Agrupar por este campo**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="fd31e-328">Selecione **Salvar** e feche a caixa de diálogo **Quebras de cabeçalho de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="fd31e-329">No campo **Tipo de ordem de trabalho**, selecione *Separação do estoque classificado*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="fd31e-330">Selecione **Novo** para criar um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fd31e-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="fd31e-331">Na seção **Visão geral**, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="fd31e-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="fd31e-332">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="fd31e-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="fd31e-333">**Modelo de trabalho:** *Separação classificada*</span><span class="sxs-lookup"><span data-stu-id="fd31e-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="fd31e-334">**Descrição do modelo de trabalho:** *Separação classificada*</span><span class="sxs-lookup"><span data-stu-id="fd31e-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="fd31e-335">Selecione **Salvar** para disponibilizar a seção **Detalhes do Modelo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="fd31e-336">Na seção **Detalhes do Modelo de Trabalho**, você criará duas linhas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="fd31e-337">Selecione **Novo** e defina os seguintes valores para a linha 1:</span><span class="sxs-lookup"><span data-stu-id="fd31e-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="fd31e-338">**Tipo de trabalho:** *Separar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="fd31e-339">**Obrigatório:** selecionado (= *Sim*)</span><span class="sxs-lookup"><span data-stu-id="fd31e-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="fd31e-340">**ID da classe de trabalho:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="fd31e-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="fd31e-341">Selecione **Novo** novamente e defina os seguintes valores para a linha 2:</span><span class="sxs-lookup"><span data-stu-id="fd31e-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="fd31e-342">**Tipo de trabalho:** *Colocar*</span><span class="sxs-lookup"><span data-stu-id="fd31e-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="fd31e-343">**Obrigatório:** selecionado (= *Sim*)</span><span class="sxs-lookup"><span data-stu-id="fd31e-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="fd31e-344">**ID da classe de trabalho:** *Classificação*</span><span class="sxs-lookup"><span data-stu-id="fd31e-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="fd31e-345">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="fd31e-346">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="fd31e-346">Example scenario</span></span>

<span data-ttu-id="fd31e-347">Este cenário simula uma situação em que o depósito armazena itens pequenos em locais e deve embalá-los em caixas antes de eles serem remetidos e na qual a funcionalidade de estação de embalagem não é adequada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="fd31e-348">Os trabalhadores separam ordens de vários clientes e diferentes endereços ao mesmo tempo para aumentar a velocidade de separação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="fd31e-349">Depois de concluída a separação, os trabalhadores chegam à localização de classificação, onde os itens separados podem ser classificados na caixa correta com base em critérios exigidos.</span><span class="sxs-lookup"><span data-stu-id="fd31e-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="fd31e-350">Neste exemplo, a ID de remessa será usada para determinar a caixa correta, pois cada remessa tem um endereço diferente.</span><span class="sxs-lookup"><span data-stu-id="fd31e-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="fd31e-351">Depois que todos os itens da carga são embalados e classificados por remessa, as caixas serão movidas para a área de preparação e carregadas em um caminhão.</span><span class="sxs-lookup"><span data-stu-id="fd31e-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="fd31e-352">Antes de iniciar o cenário, verifique se toda a funcionalidade de depósito padrão está configurada corretamente para seu depósito.</span><span class="sxs-lookup"><span data-stu-id="fd31e-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="fd31e-353">O depósito *62* padrão da Contoso é usado para essa finalidade.</span><span class="sxs-lookup"><span data-stu-id="fd31e-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="fd31e-354">As configurações padrão não foram alteradas, além do que está descrito na configuração.</span><span class="sxs-lookup"><span data-stu-id="fd31e-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="fd31e-355">Criar demanda</span><span class="sxs-lookup"><span data-stu-id="fd31e-355">Create demand</span></span>

<span data-ttu-id="fd31e-356">Para que a funcionalidade possa ser demonstrada, você deve criar alguma demanda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="fd31e-357">Para este cenário, você criará três ordens de venda para três clientes diferentes a fim de simular endereços de entrega diferentes.</span><span class="sxs-lookup"><span data-stu-id="fd31e-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="fd31e-358">Dessa forma, você criará três remessas separadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="fd31e-359">Antes de criar as ordens de venda e remessas, certifique-se de que os locais de separação têm estoque suficiente para todos os itens nas ordens.</span><span class="sxs-lookup"><span data-stu-id="fd31e-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="fd31e-360">Examine as configuração de diretiva de localização para confirmar os locais de separação que são usados para separação de ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="fd31e-361">Se precisar ajustar o estoque, você poderá criar movimentações manuais, usar o reabastecimento ou utilizar qualquer outro fluxo.</span><span class="sxs-lookup"><span data-stu-id="fd31e-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="fd31e-362">Em seguida, reserve o estoque.</span><span class="sxs-lookup"><span data-stu-id="fd31e-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="fd31e-363">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fd31e-364">Selecione **Novo** para criar uma ordem de venda para a ordem 1.</span><span class="sxs-lookup"><span data-stu-id="fd31e-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="fd31e-365">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fd31e-366">**Cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="fd31e-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="fd31e-367">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fd31e-368">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-368">Select **OK**.</span></span>
1. <span data-ttu-id="fd31e-369">Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="fd31e-370">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-370">Set the following values:</span></span>

    - <span data-ttu-id="fd31e-371">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fd31e-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="fd31e-372">**Quantidade:** *5*</span><span class="sxs-lookup"><span data-stu-id="fd31e-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="fd31e-373">Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="fd31e-374">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fd31e-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="fd31e-375">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="fd31e-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="fd31e-376">Repita as seguintes etapas para cada linha de venda na ordem a fim de reservar estoque para ela:</span><span class="sxs-lookup"><span data-stu-id="fd31e-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="fd31e-377">Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="fd31e-378">Na página **Reserva**, selecione **Reservar lote** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd31e-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="fd31e-379">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-379">Select **Save**.</span></span>

1. <span data-ttu-id="fd31e-380">Selecione **Novo** para criar uma ordem de venda para a ordem 2.</span><span class="sxs-lookup"><span data-stu-id="fd31e-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="fd31e-381">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fd31e-382">**Cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="fd31e-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="fd31e-383">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fd31e-384">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-384">Select **OK**.</span></span>
1. <span data-ttu-id="fd31e-385">Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="fd31e-386">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-386">Set the following values:</span></span>

    - <span data-ttu-id="fd31e-387">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fd31e-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="fd31e-388">**Quantidade:** *7*</span><span class="sxs-lookup"><span data-stu-id="fd31e-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="fd31e-389">Selecione **Adicionar linha** para adicionar uma segunda linha e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="fd31e-390">**Número de item:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="fd31e-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="fd31e-391">**Quantidade:** *3*</span><span class="sxs-lookup"><span data-stu-id="fd31e-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="fd31e-392">Repita as seguintes etapas para cada linha de venda na ordem a fim de reservar estoque para ela:</span><span class="sxs-lookup"><span data-stu-id="fd31e-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="fd31e-393">Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="fd31e-394">Na página **Reserva**, selecione **Reservar lote** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd31e-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="fd31e-395">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-395">Select **Save**.</span></span>

1. <span data-ttu-id="fd31e-396">Selecione **Novo** para criar uma ordem de venda para a ordem 3.</span><span class="sxs-lookup"><span data-stu-id="fd31e-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="fd31e-397">Na caixa de diálogo **Criar ordem de venda**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fd31e-398">**Cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="fd31e-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="fd31e-399">**Depósito:** *62*</span><span class="sxs-lookup"><span data-stu-id="fd31e-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="fd31e-400">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-400">Select **OK**.</span></span>
1. <span data-ttu-id="fd31e-401">Uma nova linha é adicionada à FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="fd31e-402">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="fd31e-402">Set the following values:</span></span>

    - <span data-ttu-id="fd31e-403">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="fd31e-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="fd31e-404">**Quantidade:** *8*</span><span class="sxs-lookup"><span data-stu-id="fd31e-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="fd31e-405">Siga estas etapas para reservar o estoque para a linha de venda:</span><span class="sxs-lookup"><span data-stu-id="fd31e-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="fd31e-406">Na FastTab **Linhas da ordem de venda**, no menu **Estoque**, selecione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="fd31e-407">Na página **Reserva**, selecione **Reservar lote** e feche a página.</span><span class="sxs-lookup"><span data-stu-id="fd31e-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="fd31e-408">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-408">Select **Save**.</span></span>

<span data-ttu-id="fd31e-409">Execute o procedimento a seguir para liberar cada ordem de venda para o depósito.</span><span class="sxs-lookup"><span data-stu-id="fd31e-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="fd31e-410">Serão criadas três remessas diferentes.</span><span class="sxs-lookup"><span data-stu-id="fd31e-410">Three different shipments will be created.</span></span> <span data-ttu-id="fd31e-411">Em seguida, você adicionará todas as três remessas a uma nova onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="fd31e-412">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="fd31e-413">Na grade, selecione a primeira ordem de venda que você criou.</span><span class="sxs-lookup"><span data-stu-id="fd31e-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="fd31e-414">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="fd31e-415">Você recebe uma mensagem informativa que mostra a ID da onda e a ID da remessa que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="fd31e-416">Repita as etapas anteriores para liberar as ordens de venda 2 e 3 para o depósito.</span><span class="sxs-lookup"><span data-stu-id="fd31e-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="fd31e-417">Observe que a mensagem informativa recebida indica que uma remessa foi adicionada ao onda que foi criada quando você liberou a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="fd31e-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="fd31e-418">Vá para **Gerenciamento de depósito \> Ondas de saída \> Ondas de remessa \> Todas as ondas**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="fd31e-419">Selecione a ID da onda que foi criada na liberação das ordens de venda para abrir a página **Ondas**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="fd31e-420">Essa página mostra os detalhes da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-420">This page shows the wave details.</span></span> <span data-ttu-id="fd31e-421">A FastTab **Linhas da onda** mostra as remessas criadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="fd31e-422">Agora, você deve criar um trabalho para trazer itens dos locais de separação para a localização de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="fd31e-423">No Painel de Ação, selecione **Processo**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="fd31e-424">Durante o processamento da onda, o método de classificação usará o modelo de classificação para atribuir o estoque a posições de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="fd31e-425">Quando o processamento da onda for concluído, você receberá uma mensagem informativa indicando que a onda foi lançada e o trabalho foi criado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="fd31e-426">No Painel de Ação, na guia **Onda**, no grupo **Informações relacionadas**, selecione **Trabalho** para ver o trabalho que foi criado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="fd31e-427">Anote a ID do trabalho.</span><span class="sxs-lookup"><span data-stu-id="fd31e-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="fd31e-428">Vá para **Gerenciamento de depósito \> Remessa e transporte em contêineres \> Atribuições de posição de classificação de saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="fd31e-429">Na coluna esquerda, você pode ver a posição de classificação de saída criada para cada remessa.</span><span class="sxs-lookup"><span data-stu-id="fd31e-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="fd31e-430">Na FastTab **Classificar critérios de posição**, você pode ver a ID da remessa dessa posição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="fd31e-431">Uma ID de trabalho foi criada para trazer estoque dos locais de separação para a localização de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="fd31e-432">Para concluir o trabalho, você precisará da ID de trabalho criada durante o processamento da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="fd31e-433">Separação da ordem de venda para a localização de classificação</span><span class="sxs-lookup"><span data-stu-id="fd31e-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="fd31e-434">Entre no aplicativo móvel como um trabalhador do depósito *62*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="fd31e-435">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="fd31e-436">No menu **Saída**, selecione **Separação de Venda**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="fd31e-437">Selecione o campo **ID** e insira a ID de trabalho do processamento da onda.</span><span class="sxs-lookup"><span data-stu-id="fd31e-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="fd31e-438">Confirme a entrada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-438">Confirm your entry.</span></span>

    <span data-ttu-id="fd31e-439">Em seguida, você deverá inserir uma placa de licença de destino (LP).</span><span class="sxs-lookup"><span data-stu-id="fd31e-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="fd31e-440">Observe que a linha 1 da ordem de venda 1 é o que deve ser separado e adicionado à placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="fd31e-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="fd31e-441">O número do item, a quantidade, a descrição do item e o local de separação são mostrados.</span><span class="sxs-lookup"><span data-stu-id="fd31e-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="fd31e-442">No campo **LP de destino**, insira um número de placa de licença.</span><span class="sxs-lookup"><span data-stu-id="fd31e-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="fd31e-443">Você separará todas as linhas criadas da onda processada para a mesma placa de licença de destino.</span><span class="sxs-lookup"><span data-stu-id="fd31e-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="fd31e-444">Confirme a entrada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-444">Confirm your entry.</span></span>

    <span data-ttu-id="fd31e-445">Agora, o aplicativo móvel apresenta uma série de páginas **Separar** que levam à localização de separação e também ao item e à quantidade que devem ser separados.</span><span class="sxs-lookup"><span data-stu-id="fd31e-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="fd31e-446">Depois que o item separado for adicionado à placa de licença, você confirmará o trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="fd31e-447">A última página será o trabalho de colocar os itens separados na localização de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="fd31e-448">Confirme o primeiro trabalho de separação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="fd31e-449">O próximo trabalho de separação é mostrado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-449">The next pick work is shown.</span></span> <span data-ttu-id="fd31e-450">Confirme a separação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-450">Confirm the pick.</span></span>
1. <span data-ttu-id="fd31e-451">Continue confirmando o trabalho de separação restante.</span><span class="sxs-lookup"><span data-stu-id="fd31e-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="fd31e-452">A última etapa é concluir o trabalho de colocação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-452">The last step is to complete the put work.</span></span> <span data-ttu-id="fd31e-453">Confirme o armazenamento para a localização de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="fd31e-454">Você receberá uma mensagem "Trabalho concluído".</span><span class="sxs-lookup"><span data-stu-id="fd31e-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="fd31e-455">Saia de **Separação de Venda** no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="fd31e-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="fd31e-456">Classificação/colocar no mural</span><span class="sxs-lookup"><span data-stu-id="fd31e-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="fd31e-457">Agora que todo o estoque foi colocado na localização de classificação, ele deve ser classificado para a posição de classificação correta.</span><span class="sxs-lookup"><span data-stu-id="fd31e-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="fd31e-458">Entre no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="fd31e-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="fd31e-459">No menu principal, selecione **Saída**.</span><span class="sxs-lookup"><span data-stu-id="fd31e-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="fd31e-460">No menu **Saída**, selecione **Classificar** para começar a classificar os itens.</span><span class="sxs-lookup"><span data-stu-id="fd31e-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="fd31e-461">No campo **LP/CON**, insira a placa de licença de destino do trabalho da ordem de venda separada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="fd31e-462">Confirme a entrada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-462">Confirm your entry.</span></span>
1. <span data-ttu-id="fd31e-463">Insira o número do item a ser classificado primeiro.</span><span class="sxs-lookup"><span data-stu-id="fd31e-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="fd31e-464">O sistema determina a primeira posição de classificação que deve ser mostrada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="fd31e-465">Confirme a posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="fd31e-466">Você deverá atribuir uma placa de licença à posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="fd31e-467">Selecione o campo **LP**, insira um número de placa de licença e confirme a entrada.</span><span class="sxs-lookup"><span data-stu-id="fd31e-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="fd31e-468">Como a posição de classificação está relacionada à ID da remessa, você classificará os itens separados em uma chapa de licença que seja específica da remessa e da ordem de venda de saída.</span><span class="sxs-lookup"><span data-stu-id="fd31e-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="fd31e-469">A próxima página mostra a ID do item, a quantidade, a ID da posição de classificação e as IDs da placa de licença "de" (separação) e "para" (classificação).</span><span class="sxs-lookup"><span data-stu-id="fd31e-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="fd31e-470">As informações nessa página o orientam a classificar o item e as quantidades especificados da placa de licença de separação na placa de licença de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="fd31e-471">Confirme a posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="fd31e-472">Classifique os itens na primeira posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="fd31e-473">Quando você terminar, o sistema o levará à próxima posição de classificação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="fd31e-474">Repita o processo para todas as linhas separadas da ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="fd31e-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="fd31e-475">Você também deve usar esse processo quando houver várias linhas de separação com o mesmo número de itens.</span><span class="sxs-lookup"><span data-stu-id="fd31e-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="fd31e-476">À medida que você repetir esse processo para todos os itens, o sistema avaliará os critérios do próximo item verificado (linha de trabalho) e determinará em qual posição de classificação ele deve ser colocado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="fd31e-477">Você é direcionado automaticamente para colocar o item na posição de classificação correta.</span><span class="sxs-lookup"><span data-stu-id="fd31e-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="fd31e-478">Dependendo da configuração de confirmação, você também deverá confirmar essa ação inserindo o número da posição ou a ID da placa de licença.</span><span class="sxs-lookup"><span data-stu-id="fd31e-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd31e-479">Se a classificação automática estiver ativada, a substituição manual não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="fd31e-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="fd31e-480">Quando terminar, no Microsoft Dynamics 365 Supply Chain Management, abra a página **Atribuições de posição de classificação de saída** para analisar o status das posições.</span><span class="sxs-lookup"><span data-stu-id="fd31e-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="fd31e-481">Se as posições forem fechadas automaticamente, selecione **Mostrar fechado** para mostrar as posições fechadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="fd31e-482">As transações de posição de classificação são mostradas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="fd31e-483">O item e a quantidade processados por meio da posição são exibidos.</span><span class="sxs-lookup"><span data-stu-id="fd31e-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="fd31e-484">Ao configurar o modelo de classificação de saída, você define a opção **Posição de classificação de fechamento automático** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="fd31e-485">Portanto, a posição é fechada automaticamente depois que o último estoque previsto é colocado nela.</span><span class="sxs-lookup"><span data-stu-id="fd31e-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="fd31e-486">As posições de classificação têm o status **Fechado**, e foi criado um trabalho para mover o estoque classificado para o local *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="fd31e-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="fd31e-487">Conclua o trabalho de separação do estoque classificado para mover o estoque para o local da remessa.</span><span class="sxs-lookup"><span data-stu-id="fd31e-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="fd31e-488">Quando o estoque estiver pronto, confirme-o para a remessa.</span><span class="sxs-lookup"><span data-stu-id="fd31e-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="fd31e-489">Para que o trabalho de separação de estoque classificado seja processado corretamente, um item de menu do dispositivo móvel que tem uma ID de classe de trabalho na qual o campo **Tipo de ordem de trabalho** está definido como *Separação do estoque classificado* deve ser usado para o processo de movimentação e carga.</span><span class="sxs-lookup"><span data-stu-id="fd31e-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="fd31e-490">Fechar uma posição manualmente (opcional)</span><span class="sxs-lookup"><span data-stu-id="fd31e-490">Manually close a position (optional)</span></span>

<span data-ttu-id="fd31e-491">Se as posições de classificação tiverem que ser fechadas manualmente, a opção **Posição de classificação de fechamento automático** do modelo de classificação de saída deverá ser definida como *Não* e o fechamento deverá ser feito antes que o estoque possa ser movido para a área da porta da baía.</span><span class="sxs-lookup"><span data-stu-id="fd31e-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="fd31e-492">As posições podem ser fechadas de várias maneiras:</span><span class="sxs-lookup"><span data-stu-id="fd31e-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="fd31e-493">Por meio do aplicativo de depósito:</span><span class="sxs-lookup"><span data-stu-id="fd31e-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="fd31e-494">O usuário pode examinar um dos itens que já estão na posição e selecionar **Fechar** para fechar a posição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="fd31e-495">Se o usuário examinar um contêiner que já foi classificado, será exibida uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="fd31e-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="fd31e-496">No entanto, o usuário ainda poderá continuar para fechar a posição.</span><span class="sxs-lookup"><span data-stu-id="fd31e-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="fd31e-497">Na página **Atribuições de posição de classificação de saída** do Microsoft Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="fd31e-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="fd31e-498">O usuário pode selecionar o registro da posição de classificação de saída e selecionar **Fechar posição** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="fd31e-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="fd31e-499">Dicas</span><span class="sxs-lookup"><span data-stu-id="fd31e-499">Tips</span></span>

- <span data-ttu-id="fd31e-500">Os itens não podem ser movidos entre posições depois de terem sido atribuídos a uma.</span><span class="sxs-lookup"><span data-stu-id="fd31e-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="fd31e-501">O sistema avalia a quantidade de cada item que deve ir para uma posição específica.</span><span class="sxs-lookup"><span data-stu-id="fd31e-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="fd31e-502">O modelo de classificação pode ser configurados para criar contêineres automaticamente quando posições forem fechadas.</span><span class="sxs-lookup"><span data-stu-id="fd31e-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="fd31e-503">Essa abordagem criará a estrutura de ID de contêiner padrão com base no perfil de embalagem especificado.</span><span class="sxs-lookup"><span data-stu-id="fd31e-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd31e-504">Depois que o trabalho de movimentação tiver sido criado com base na localização de classificação, você não deverá cancelá-lo.</span><span class="sxs-lookup"><span data-stu-id="fd31e-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="fd31e-505">Caso contrário, a posição e os contêineres nela serão excluídos do sistema e ficarão indisponíveis para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="fd31e-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="fd31e-506">O estoque também será removido.</span><span class="sxs-lookup"><span data-stu-id="fd31e-506">The inventory will also be removed.</span></span>
