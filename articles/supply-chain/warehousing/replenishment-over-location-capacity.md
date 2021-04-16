---
title: Reabastecimento sobre a capacidade do local
description: Este tópico fornece informações sobre o recurso Reabastecimento sobre a capacidade do local. Este recurso habilita a criação de todo o trabalho de reabastecimento que será necessário para o dia e gerencia a disponibilidade desse trabalho de reabastecimento para garantir que o local de separação não fique sem estoque nem acima da capacidade.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 309df56671bf258e1669ae6d5393de01e2b500f0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823230"
---
# <a name="replenishment-over-location-capacity"></a><span data-ttu-id="94477-104">Reabastecimento sobre a capacidade do local</span><span class="sxs-lookup"><span data-stu-id="94477-104">Replenishment over location capacity</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94477-105">Alguns depósitos de alto volume ou de espaço restrito devem enviar mais quantidade de um item em um dia do que caiba no local de separação.</span><span class="sxs-lookup"><span data-stu-id="94477-105">Some high-volume or space-constrained warehouses must ship more quantity of an item in a day than will fit in the picking location.</span></span> <span data-ttu-id="94477-106">O recurso *Reabastecimento sobre a capacidade do local* habilita a criação de todo o trabalho de reabastecimento que será necessário para o dia e gerencia a disponibilidade desse trabalho de reabastecimento para garantir que o local de separação não fique sem estoque nem acima da capacidade.</span><span class="sxs-lookup"><span data-stu-id="94477-106">The *Replenishment over location capacity* feature enables all replenishment work that will be required for the day to be created and manages availability of that replenishment work to ensure that the picking location neither runs out of inventory nor goes above capacity.</span></span>

<span data-ttu-id="94477-107">O recurso permite que mais trabalho de reabastecimento seja criado do que caberá em um local e bloqueia a conclusão do trabalho de reabastecimento quando o local está cheio.</span><span class="sxs-lookup"><span data-stu-id="94477-107">The feature enables more replenishment work to be created than will fit in a location, and it blocks replenishment work from being completed when the location is full.</span></span> <span data-ttu-id="94477-108">À medida que o estoque no local de separação fica abaixo de um limite configurável, mais trabalho de reabastecimento é disponibilizado.</span><span class="sxs-lookup"><span data-stu-id="94477-108">As inventory in the picking location drops below a configurable threshold, more replenishment work is made available.</span></span>

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a><span data-ttu-id="94477-109">Ativar o recurso Reabastecimento sobre a capacidade do local</span><span class="sxs-lookup"><span data-stu-id="94477-109">Turn on the Replenishment over location capacity feature</span></span>

<span data-ttu-id="94477-110">Para disponibilizar este recurso, ative os seguintes recursos no [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (nesta ordem):</span><span class="sxs-lookup"><span data-stu-id="94477-110">To make this feature available, turn on the following features in [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) (in this order):</span></span>

1. <span data-ttu-id="94477-111">Bloqueio de trabalho em toda a organização</span><span class="sxs-lookup"><span data-stu-id="94477-111">Organization-wide work blocking</span></span>
1. <span data-ttu-id="94477-112">Reabastecimento sobre a capacidade do local</span><span class="sxs-lookup"><span data-stu-id="94477-112">Replenishment over location capacity</span></span>

## <a name="set-up-the-feature-for-the-example-scenario"></a><span data-ttu-id="94477-113">Configurar o recurso para o cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="94477-113">Set up the feature for the example scenario</span></span>

<span data-ttu-id="94477-114">Esta seção fornece diretrizes e um exemplo que mostra como configurar este recurso e preparar dados de exemplo para o cenário de exemplo fornecido mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="94477-114">This section provides guidelines and an example that shows how to set up this feature and prepare sample data for the example scenario that is provided later in this topic.</span></span>

### <a name="enable-sample-data"></a><span data-ttu-id="94477-115">Habilitar dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="94477-115">Enable sample data</span></span>

<span data-ttu-id="94477-116">Para trabalhar com o [cenário de exemplo](#example-scenario) usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="94477-116">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="94477-117">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="94477-117">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

### <a name="location-profile"></a><span data-ttu-id="94477-118">Perfil de localização</span><span class="sxs-lookup"><span data-stu-id="94477-118">Location profile</span></span>

<span data-ttu-id="94477-119">Habilite a funcionalidade de reabastecimento sobre capacidade no perfil de localização.</span><span class="sxs-lookup"><span data-stu-id="94477-119">Enable the replenish over capacity functionality on the location profile.</span></span>

1. <span data-ttu-id="94477-120">Vá para **Gerenciamento de depósito \> Configuração \> Depósito \> Perfis de localizações**.</span><span class="sxs-lookup"><span data-stu-id="94477-120">Go to **Warehouse management \> Setup \> Warehouse \> Locations profiles**.</span></span>
1. <span data-ttu-id="94477-121">No painel esquerdo, selecione **PICK-06**.</span><span class="sxs-lookup"><span data-stu-id="94477-121">In the left pane, select **PICK-06**.</span></span>
1. <span data-ttu-id="94477-122">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="94477-122">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="94477-123">Na FastTab **Reabastecimento**, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-123">On the **Replenishment** FastTab, set the following values:</span></span>

    - <span data-ttu-id="94477-124">**Exceder Capacidade de Localização:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="94477-124">**Exceed Location Capacity:** *Yes*</span></span>

        <span data-ttu-id="94477-125">Quando esta opção estiver habilitada, a capacidade máxima do local será permitida a ser excedida por trabalhos de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-125">When enabled, the maximum capacity of the location will be allowed to be exceeded by replenishment work.</span></span> <span data-ttu-id="94477-126">Isso também habilita outros campos na FastTab **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="94477-126">This also enables other fields on the **Replenishment** FastTab.</span></span>

    - <span data-ttu-id="94477-127">**Tipo de limite de disponibilidade de trabalho:** *Quantidade*</span><span class="sxs-lookup"><span data-stu-id="94477-127">**Work availability threshold type:** *Quantity*</span></span>

        <span data-ttu-id="94477-128">Este campo define o método usado para determinar quando mais trabalho deve ser liberado.</span><span class="sxs-lookup"><span data-stu-id="94477-128">This field defines the method that is used to determine when more work should be released.</span></span> <span data-ttu-id="94477-129">Você pode liberar por quantidade ou uma porcentagem:</span><span class="sxs-lookup"><span data-stu-id="94477-129">You can release by either quantity or a percentage:</span></span>

        - <span data-ttu-id="94477-130">*Porcentagem* – selecione esta opção para usar a capacidade de porcentagem baseada em limites de estoque ou de volumetria.</span><span class="sxs-lookup"><span data-stu-id="94477-130">*Percent* – Select this option to use percentage capacity that is based on stocking limits or volumetrics.</span></span> <span data-ttu-id="94477-131">A seleção desta opção habilita o campo **Porcentagem de excesso** e desabilita os dois campos relacionados à quantidade, **Quantidade de excesso** e **Unidade de excesso**.</span><span class="sxs-lookup"><span data-stu-id="94477-131">Selecting this option enables the **Overflow percentage** field, and disables the two quantity related fields,  **Overflow quantity** and **Overflow unit**.</span></span>

            <span data-ttu-id="94477-132">Você poderá usar esta opção se os locais de separação usarem volumetria.</span><span class="sxs-lookup"><span data-stu-id="94477-132">You can use this option if the picking locations use volumetrics.</span></span>

            <span data-ttu-id="94477-133">Se esta opção estiver selecionada, defina o campo **Porcentagem de excesso** com a porcentagem na qual mais trabalho de reabastecimento será disponibilizado.</span><span class="sxs-lookup"><span data-stu-id="94477-133">If this option is selected, set the **Overflow percentage** field to the percentage at which more replenishment work will be made available.</span></span>

        - <span data-ttu-id="94477-134">*Quantidade* – selecione esta opção para usar um valor de quantidade específico.</span><span class="sxs-lookup"><span data-stu-id="94477-134">*Quantity* – Select this option to use a specific quantity value.</span></span> <span data-ttu-id="94477-135">A seleção desta opção desabilita o campo **Porcentagem de excesso** e habilita os campos **Quantidade de excesso** e **Unidade de excesso**.</span><span class="sxs-lookup"><span data-stu-id="94477-135">Selecting this option disables the **Overflow percentage** field and enables **Overflow quantity** and **Overflow unit** fields.</span></span>

            <span data-ttu-id="94477-136">Use esta opção quando não estiver usando volumetria para os locais reabastecidos ou quando houver quantidades consistentes em que você deseja que mais estoque seja trazido para o local.</span><span class="sxs-lookup"><span data-stu-id="94477-136">Use this option when you aren't using volumetrics for the locations that are being replenished, or when you have consistent quantities at which you want more inventory to be brought to the location.</span></span>

           <span data-ttu-id="94477-137">Se esta opção estiver selecionada, defina os campos **Quantidade de excesso** e **Unidade de excesso** para a quantidade e a unidade em que mais trabalho de reabastecimento será disponibilizado.</span><span class="sxs-lookup"><span data-stu-id="94477-137">If this option is selected, set the **Overflow quantity** and **Overflow unit** fields to the quantity and unit at which more replenishment work will be made available.</span></span>

    - <span data-ttu-id="94477-138">**Quantidade de excesso:** *0,65*</span><span class="sxs-lookup"><span data-stu-id="94477-138">**Overflow quantity:** *0.65*</span></span>

        <span data-ttu-id="94477-139">Este campo define a quantidade em que ocorre o excesso de localização.</span><span class="sxs-lookup"><span data-stu-id="94477-139">This field defines the quantity at which the location overflows.</span></span>

        <span data-ttu-id="94477-140">O trabalho será disponibilizado sempre que a soma da quantidade disponível no local e da quantidade de trabalho estiver abaixo desse valor.</span><span class="sxs-lookup"><span data-stu-id="94477-140">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this value.</span></span> <span data-ttu-id="94477-141">Qualquer trabalho de reabastecimento acima desse valor será bloqueado e deverá ser desbloqueado manualmente.</span><span class="sxs-lookup"><span data-stu-id="94477-141">Any replenishment work above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="94477-142">Os limites do estoque de localização são considerados quando a quantidade do trabalho é calculada.</span><span class="sxs-lookup"><span data-stu-id="94477-142">Location stocking limits are considered when the work quantity is calculated.</span></span>

    - <span data-ttu-id="94477-143">**Unidade de excesso:** *PL*</span><span class="sxs-lookup"><span data-stu-id="94477-143">**Overflow unit:** *PL*</span></span>

        <span data-ttu-id="94477-144">Este campo define a unidade associada à quantidade de excesso.</span><span class="sxs-lookup"><span data-stu-id="94477-144">This field defines the unit that is associated with the overflow quantity.</span></span>

        <span data-ttu-id="94477-145">Nesse caso, mais trabalho de reabastecimento será disponibilizado quando o local for reduzido a 0,65 palete (PL).</span><span class="sxs-lookup"><span data-stu-id="94477-145">In this case, more replenishment work will be made available when the location gets down to 0.65 pallet (PL).</span></span>

    - <span data-ttu-id="94477-146">**Porcentagem de excesso**</span><span class="sxs-lookup"><span data-stu-id="94477-146">**Overflow percentage**</span></span>

        <span data-ttu-id="94477-147">Este campo define a porcentagem em que ocorre o excesso de localização.</span><span class="sxs-lookup"><span data-stu-id="94477-147">This field defines the percentage at which the location overflows.</span></span>

        <span data-ttu-id="94477-148">O trabalho será disponibilizado sempre que a soma da quantidade disponível no local e da quantidade de trabalho estiver abaixo dessa porcentagem.</span><span class="sxs-lookup"><span data-stu-id="94477-148">Work will be available whenever the sum of the on-hand quantity in the location and the work quantity is below this percentage.</span></span> <span data-ttu-id="94477-149">Qualquer porcentagem de quantidade de trabalho de reabastecimento acima desse valor será bloqueada e deverá ser desbloqueada manualmente.</span><span class="sxs-lookup"><span data-stu-id="94477-149">Any replenishment work quantity percentage above this value will be blocked and must be manually unblocked.</span></span>

        <span data-ttu-id="94477-150">Os limites do estoque de localização são considerados quando a porcentagem da quantidade de trabalho é calculada.</span><span class="sxs-lookup"><span data-stu-id="94477-150">Location stocking limits are considered when the work quantity percentage is calculated.</span></span> <span data-ttu-id="94477-151">Se nenhum limite de estoque de localização for definido, a porcentagem da quantidade de trabalho será calculada por volume se as restrições de volume forem definidas para o perfil do local.</span><span class="sxs-lookup"><span data-stu-id="94477-151">If no location stocking limits are defined, the work quantity percentage is calculated by volume if volume constraints are defined for the location profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94477-152">Se você estiver usando os dados de demonstração da entidade legal **USMF** e previamente ativou o recurso *Posicionamento da placa de licença de localização*, desative a configuração **Habilitar posicionamento da placa de licença** para o perfil de localização **BULK-06** para concluir as etapas móveis no cenário de exemplo.</span><span class="sxs-lookup"><span data-stu-id="94477-152">If you're using the demo data for the **USMF** legal entity and previously turned on the *Location license plate positioning* feature, you must turn off the **Enable license plate positioning** setting for the **BULK-06** location profile to complete the mobile steps in the example scenario.</span></span>

### <a name="wave-step-code"></a><span data-ttu-id="94477-153">Código da etapa da onda</span><span class="sxs-lookup"><span data-stu-id="94477-153">Wave step code</span></span>

> [!NOTE]
> <span data-ttu-id="94477-154">Para configurar um código de etapa de onda, conforme descrito aqui, você deve primeiro usar o [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para ativar o recurso denominado *Código da etapa da onda em toda a organização*.</span><span class="sxs-lookup"><span data-stu-id="94477-154">To set up a wave step code as described here, you might first have to use [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn on the feature that is named *Organization wide wave step code*.</span></span>

1. <span data-ttu-id="94477-155">Vá para **Gerenciamento de Depósito \> Configuração \> Ondas \> Códigos da etapa da onda**.</span><span class="sxs-lookup"><span data-stu-id="94477-155">Go to **Warehouse Management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="94477-156">Selecione **Novo** e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-156">Select **New**, and set the following values:</span></span>

    - <span data-ttu-id="94477-157">**Código da etapa da onda:** *Reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-157">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="94477-158">**Descrição da etapa da onda:** *Reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-158">**Wave step description:** *Replenishment*</span></span>
    - <span data-ttu-id="94477-159">**Tipo de etapa de onda:** *Reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-159">**Wave step type:** *Replenishment*</span></span>

1. <span data-ttu-id="94477-160">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94477-160">Select **Save**.</span></span>

### <a name="replenishment-template"></a><span data-ttu-id="94477-161">Modelo de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="94477-161">Replenishment template</span></span>

<span data-ttu-id="94477-162">Modelos de reabastecimento são um conjunto de regras que controlam como e quando um local é reabastecido.</span><span class="sxs-lookup"><span data-stu-id="94477-162">Replenishment templates are a set of rules that control when and how a location is replenished.</span></span>

1. <span data-ttu-id="94477-163">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="94477-163">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="94477-164">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="94477-164">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="94477-165">Na seção **Visão geral**, selecione a linha em que o campo **Modelo de reabastecimento** está definido como *Reabastecimento de demanda*.</span><span class="sxs-lookup"><span data-stu-id="94477-165">In the **Overview** section, select the line where the **Replenish template** field is set to *Demand replenish*.</span></span>
1. <span data-ttu-id="94477-166">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-166">Set the following values:</span></span>

    - <span data-ttu-id="94477-167">**Código da etapa da onda:** *Reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-167">**Wave step code:** *Replen*</span></span>
    - <span data-ttu-id="94477-168">**Permitir que a demanda de onda use quantidades não reservadas:** *Sim*</span><span class="sxs-lookup"><span data-stu-id="94477-168">**Allow wave demand to use unreserved quantities:** *Yes*</span></span>

1. <span data-ttu-id="94477-169">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94477-169">Select **Save**.</span></span>

### <a name="wave-template"></a><span data-ttu-id="94477-170">Modelo da onda</span><span class="sxs-lookup"><span data-stu-id="94477-170">Wave template</span></span>

1. <span data-ttu-id="94477-171">Vá para **Gerenciamento de depósito \> Configuração \> Ondas \> Modelos de onda**.</span><span class="sxs-lookup"><span data-stu-id="94477-171">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="94477-172">No painel esquerdo, defina o campo **Tipo de modelo de onda** como *Remessa*.</span><span class="sxs-lookup"><span data-stu-id="94477-172">In the left pane, set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="94477-173">Selecione o modelo **Remessa 61** na lista.</span><span class="sxs-lookup"><span data-stu-id="94477-173">Select template **61 Shipping** in the list.</span></span>
1. <span data-ttu-id="94477-174">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="94477-174">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="94477-175">Na FastTab **Geral**, defina a opção **Automatizar liberação do trabalho de reabastecimento** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="94477-175">On the **General** FastTab, set the **Automate replenishment work release** option to *Yes*.</span></span>

    <span data-ttu-id="94477-176">Defina esta opção como *Sim* para criar o trabalho de reabastecimento baseado em demanda e liberá-lo automaticamente.</span><span class="sxs-lookup"><span data-stu-id="94477-176">Set this option to *Yes* to create demand-based replenishment work and release it automatically.</span></span> <span data-ttu-id="94477-177">Você deve adicionar o método de onda de reabastecimento ao modelo de onda e criar um modelo de reabastecimento do tipo **Demanda da onda**.</span><span class="sxs-lookup"><span data-stu-id="94477-177">You must add the replenishment wave method to the wave template and create a replenishment template of the **Wave demand** type.</span></span> <span data-ttu-id="94477-178">Configure um modelo de reabastecimento na página **Modelos de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="94477-178">Set up a replenishment template on the **Replenishment templates** page.</span></span> <span data-ttu-id="94477-179">Para configurar um modelo de reabastecimento, você deve adicionar o método de reabastecimento ao modelo de onda.</span><span class="sxs-lookup"><span data-stu-id="94477-179">To set up a replenishment template, you must add the replenish method to the wave template.</span></span>

1. <span data-ttu-id="94477-180">Na FastTab **Métodos**, na coluna **Métodos selecionados**, localize a seguinte linha:</span><span class="sxs-lookup"><span data-stu-id="94477-180">On the **Methods** FastTab, in the **Selected methods** column, find the following line:</span></span>

    - <span data-ttu-id="94477-181">**Nome do método:** *reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-181">**Method name:** *replenish*</span></span>
    - <span data-ttu-id="94477-182">**Nome:** *Reabastecimento*</span><span class="sxs-lookup"><span data-stu-id="94477-182">**Name:** *Replenishment*</span></span>

1. <span data-ttu-id="94477-183">Defina o campo **Código da etapa da onda** para esta linha como *Reabastecimento*.</span><span class="sxs-lookup"><span data-stu-id="94477-183">Set the **Wave step code** field for this line to *Replen*.</span></span>
1. <span data-ttu-id="94477-184">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="94477-184">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="94477-185">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="94477-185">Example scenario</span></span>

<span data-ttu-id="94477-186">Após disponibilizar todos os dados de exemplo descritos anteriormente e configurá-los, você poderá trabalhar neste cenário para testar o recurso *Reabastecimento sobre a capacidade do local*.</span><span class="sxs-lookup"><span data-stu-id="94477-186">After you've made all the previously described sample data available and set it up, you can work through this scenario to try out the *Replenishment over location capacity* feature.</span></span> <span data-ttu-id="94477-187">Os valores que são mostrados neste cenário pressupõem que você está trabalhando com os dados de demonstração padrão, que você selecionou a entidade legal **USMF** e preparou os registros de exemplo descritos anteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="94477-187">The values that are shown in this scenario assume that you're working with the standard demo data, that you selected the **USMF** legal entity, and that you prepared the sample records that are described earlier in this topic.</span></span> <span data-ttu-id="94477-188">Esse cenário também serve como exemplo para mostrar como o recurso pode ser usado em uma configuração de produção.</span><span class="sxs-lookup"><span data-stu-id="94477-188">This scenario also serves as an example that shows how the feature can be used in a production setting.</span></span>

### <a name="create-replenishment-work"></a><span data-ttu-id="94477-189">Criar trabalho de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="94477-189">Create replenishment work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="94477-190">Criar ordem de venda 1</span><span class="sxs-lookup"><span data-stu-id="94477-190">Create sales order 1</span></span>

1. <span data-ttu-id="94477-191">Vá para **Vendas e marketing \> Ordens de venda \> Todas as ordens de venda**.</span><span class="sxs-lookup"><span data-stu-id="94477-191">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="94477-192">No Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="94477-192">On the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="94477-193">Na caixa de diálogo , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-193">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="94477-194">**Conta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="94477-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="94477-195">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="94477-195">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="94477-196">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94477-196">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="94477-197">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="94477-197">The new sales order is opened.</span></span> <span data-ttu-id="94477-198">Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="94477-198">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="94477-199">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-199">On this line, set the following values:</span></span>

    - <span data-ttu-id="94477-200">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="94477-200">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="94477-201">**Quantidade:** *40*</span><span class="sxs-lookup"><span data-stu-id="94477-201">**Quantity:** *40*</span></span>

1. <span data-ttu-id="94477-202">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="94477-202">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="94477-203">Na página **Reserva**, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="94477-203">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="94477-204">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="94477-204">Close the page.</span></span>
1. <span data-ttu-id="94477-205">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="94477-205">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="94477-206">Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="94477-206">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="94477-207">Uma onda de reabastecimento também é criada.</span><span class="sxs-lookup"><span data-stu-id="94477-207">A replenishment wave is also created.</span></span>

    <span data-ttu-id="94477-208">Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-208">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="94477-209">Criar ordem de venda 2</span><span class="sxs-lookup"><span data-stu-id="94477-209">Create sales order 2</span></span>

1. <span data-ttu-id="94477-210">Na página **Todas as ordens de venda**, no Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="94477-210">On the **All sales orders**, page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="94477-211">Na caixa de diálogo , defina o seguinte valor:</span><span class="sxs-lookup"><span data-stu-id="94477-211">In the dialog box, set the following value:</span></span>

    - <span data-ttu-id="94477-212">**Conta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="94477-212">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="94477-213">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="94477-213">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="94477-214">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94477-214">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="94477-215">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="94477-215">The new sales order is opened.</span></span> <span data-ttu-id="94477-216">Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="94477-216">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="94477-217">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-217">On this line, set the following values:</span></span>

    - <span data-ttu-id="94477-218">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="94477-218">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="94477-219">**Quantidade:** *60*</span><span class="sxs-lookup"><span data-stu-id="94477-219">**Quantity:** *60*</span></span>

1. <span data-ttu-id="94477-220">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="94477-220">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="94477-221">Na página **Reserva**, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="94477-221">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="94477-222">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="94477-222">Close the page.</span></span>
1. <span data-ttu-id="94477-223">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="94477-223">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="94477-224">Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="94477-224">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="94477-225">Uma onda de reabastecimento também é criada.</span><span class="sxs-lookup"><span data-stu-id="94477-225">A replenishment wave is also created.</span></span>

    <span data-ttu-id="94477-226">Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-226">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="94477-227">Criar ordem de venda 3</span><span class="sxs-lookup"><span data-stu-id="94477-227">Create sales order 3</span></span>

1. <span data-ttu-id="94477-228">Na página **Todas as ordens de venda**, no Painel de Ações, selecione **Novo** para abrir uma caixa de diálogo para criar uma nova ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="94477-228">On the **All sales orders** page, on the Action Pane, select **New** to open a dialog box for creating a new sales order.</span></span>
1. <span data-ttu-id="94477-229">Na caixa de diálogo , defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-229">In the dialog box, set the following values:</span></span>

    - <span data-ttu-id="94477-230">**Conta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="94477-230">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="94477-231">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="94477-231">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="94477-232">Selecione **OK** para criar a ordem de venda e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94477-232">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="94477-233">A nova ordem de venda é aberta.</span><span class="sxs-lookup"><span data-stu-id="94477-233">The new sales order is opened.</span></span> <span data-ttu-id="94477-234">Ela inclui uma nova linha vazia na FastTab **Linhas da ordem de venda**.</span><span class="sxs-lookup"><span data-stu-id="94477-234">It includes a new, empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="94477-235">Nessa linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="94477-235">On this line, set the following values:</span></span>

    - <span data-ttu-id="94477-236">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="94477-236">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="94477-237">**Quantidade:** *30*</span><span class="sxs-lookup"><span data-stu-id="94477-237">**Quantity:** *30*</span></span>

1. <span data-ttu-id="94477-238">Na FastTab **Linhas da ordem de venda**, selecione **Estoque \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="94477-238">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
1. <span data-ttu-id="94477-239">Na página **Reserva**, selecione **Reservar lote**.</span><span class="sxs-lookup"><span data-stu-id="94477-239">On the **Reservation** page, select **Reserve lot**.</span></span>
1. <span data-ttu-id="94477-240">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="94477-240">Close the page.</span></span>
1. <span data-ttu-id="94477-241">No Painel de Ações, na guia **Depósito**, selecione **Liberar para o depósito**.</span><span class="sxs-lookup"><span data-stu-id="94477-241">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="94477-242">Você recebe mensagens informativas que mostram IDs da onda e da remessa que foram criadas.</span><span class="sxs-lookup"><span data-stu-id="94477-242">You receive informational messages that show the wave and shipment IDs that were created.</span></span> <span data-ttu-id="94477-243">Uma onda de reabastecimento também é criada.</span><span class="sxs-lookup"><span data-stu-id="94477-243">A replenishment wave is also created.</span></span>

    <span data-ttu-id="94477-244">Você também receberá uma mensagem de aviso afirmando "não é possível desbloquear a ID de trabalho XXXX porque existe trabalho de reabastecimento não concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-244">You also receive a warning message that states, "Work ID XXXX cannot be unblocked because it has unfinished replenishment work."</span></span>

#### <a name="view-work-details"></a><span data-ttu-id="94477-245">Exibir detalhes do trabalho</span><span class="sxs-lookup"><span data-stu-id="94477-245">View work details</span></span>

1. <span data-ttu-id="94477-246">Vá para **Gerenciamento de depósito \> Trabalho \> Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="94477-246">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="94477-247">Na seção **Visão geral**, filtre a coluna **Depósito** para o depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="94477-247">In the **Overview** section, filter the **Warehouse** column for warehouse *61*.</span></span>
1. <span data-ttu-id="94477-248">Note que foram criadas sete IDs de trabalho para as três ordens de venda de demanda.</span><span class="sxs-lookup"><span data-stu-id="94477-248">You should see that seven work IDs were created for the three demand sales orders.</span></span>

    - <span data-ttu-id="94477-249">Três das sete IDs de trabalho têm um **Tipo de ordem de trabalho** com valor de *Reabastecimento* e quatro têm um **Tipo de ordem de trabalho** com valor de *Ordens de venda*.</span><span class="sxs-lookup"><span data-stu-id="94477-249">Three of the seven work IDs have a **Work order type** value of *Replenishment*, and four have a **Work order type** value of *Sales orders*.</span></span>
    - <span data-ttu-id="94477-250">Todas as três IDs de trabalho com **Tipo de ordem de trabalho** com valor de *Reabastecimento* têm as mesmas localizações de *Separação* e *Colocação* na seção **Linhas**:</span><span class="sxs-lookup"><span data-stu-id="94477-250">All three work IDs that have a **Work order type** value of *Replenishment* have the same *Pick* and *Put* locations in the **Lines** section:</span></span>

        - <span data-ttu-id="94477-251">**Separar:** *02A01R5S1B*</span><span class="sxs-lookup"><span data-stu-id="94477-251">**Pick:** *02A01R5S1B*</span></span>
        - <span data-ttu-id="94477-252">**Colocar:** *06A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="94477-252">**Put:** *06A01R2S1B*</span></span>

    - <span data-ttu-id="94477-253">Duas IDs de trabalho foram criadas para a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="94477-253">Two work IDs were created for sales order 1.</span></span>

1. <span data-ttu-id="94477-254">Anote as IDs de trabalho das ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="94477-254">Make a note of the work IDs for the sales orders.</span></span>

<span data-ttu-id="94477-255">Dependendo das quantidades disponíveis, as quantidades de trabalho criadas podem variar um pouco.</span><span class="sxs-lookup"><span data-stu-id="94477-255">Depending on your on-hand quantities, the work quantities that are created might vary slightly.</span></span> <span data-ttu-id="94477-256">No entanto, em geral, os cabeçalhos de trabalho criados devem corresponder a este exemplo de cenário.</span><span class="sxs-lookup"><span data-stu-id="94477-256">However, overall, the work headers that are created should match this scenario example.</span></span>

#### <a name="on-hand-inventory-license-plate-id"></a><span data-ttu-id="94477-257">ID da placa de licença de estoque disponível</span><span class="sxs-lookup"><span data-stu-id="94477-257">On-hand inventory license plate ID</span></span>

<span data-ttu-id="94477-258">Posteriormente neste cenário, você usará o aplicativo móvel de gerenciamento de depósito (ou um emulador), em que deve identificar a placa de licença para concluir os cenários de separação e reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-258">Later in this scenario, you will use the Warehouse Management mobile app (or an emulator), where you must identify the license plate to complete the picking and replenishment scenarios.</span></span>

<span data-ttu-id="94477-259">Para localizar as IDs de placa de licença que serão necessárias posteriormente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="94477-259">To find the license plate IDs that you will need later, follow these steps.</span></span>

1. <span data-ttu-id="94477-260">Vá para **Gerenciamento de estoque \> Consultas e relatórios \> Lista disponível**.</span><span class="sxs-lookup"><span data-stu-id="94477-260">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="94477-261">Selecione o botão **Mostrar filtros** para abrir o painel de filtros.</span><span class="sxs-lookup"><span data-stu-id="94477-261">Select the **Show filters** button to open the filter pane.</span></span>
1. <span data-ttu-id="94477-262">Insira os critérios de filtragem a seguir para obter as placas de licença do cenário.</span><span class="sxs-lookup"><span data-stu-id="94477-262">Enter the following filtering criteria to get the license plates for the scenario.</span></span> <span data-ttu-id="94477-263">Use o filtro *começa com*.</span><span class="sxs-lookup"><span data-stu-id="94477-263">Use the *begins with* filter.</span></span>

    - <span data-ttu-id="94477-264">**Número de item:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="94477-264">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="94477-265">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="94477-265">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="94477-266">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="94477-266">Select **Apply**.</span></span>
1. <span data-ttu-id="94477-267">No Painel de Ação, selecione **Dimensões**.</span><span class="sxs-lookup"><span data-stu-id="94477-267">On the Action Pane, select **Dimensions**.</span></span>
1. <span data-ttu-id="94477-268">Na caixa de diálogo **Exibição de dimensões**, na seção **Dimensões de Armazenamento**, selecione todos os valores.</span><span class="sxs-lookup"><span data-stu-id="94477-268">In the **Dimensions display** dialog box, in the **Storage Dimensions** section, select all the values.</span></span>
1. <span data-ttu-id="94477-269">Na seção **Transações**, selecione **Número do item** e **Quantidade \<\> 0**.</span><span class="sxs-lookup"><span data-stu-id="94477-269">In the **Transactions** section, select **Item number** and **Quantity \<\> 0**.</span></span>
1. <span data-ttu-id="94477-270">Quando terminar, selecione **OK** para fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="94477-270">When you've finished, select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="94477-271">A grade **Disponível** mostra os números das placas de licença para o item *T0100* em cada local.</span><span class="sxs-lookup"><span data-stu-id="94477-271">The **On-hand** grid shows the license plate numbers for item *T0100* in each location.</span></span> <span data-ttu-id="94477-272">Anote a placa da licença que está em cada local, pois essas informações serão necessárias posteriormente.</span><span class="sxs-lookup"><span data-stu-id="94477-272">Make a note of the license plate that is in each location, because you will need this information later.</span></span>
1. <span data-ttu-id="94477-273">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="94477-273">Close the page.</span></span>

### <a name="process-steps"></a><span data-ttu-id="94477-274">Etapa do processo</span><span class="sxs-lookup"><span data-stu-id="94477-274">Process steps</span></span>

<span data-ttu-id="94477-275">Você executará o reabastecimento de localização de depósito para as duas primeiras IDs de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-275">You will perform the warehouse location replenishment for the first two work IDs.</span></span> <span data-ttu-id="94477-276">O trabalho no terceiro trabalho de reabastecimento será bloqueado até que o nível de estoque no local de separação fique abaixo do limite.</span><span class="sxs-lookup"><span data-stu-id="94477-276">Work on the third replenishment work will be blocked until the inventory level in the picking location falls below the threshold.</span></span>

#### <a name="replenishment"></a><span data-ttu-id="94477-277">Reabastecimento</span><span class="sxs-lookup"><span data-stu-id="94477-277">Replenishment</span></span>

1. <span data-ttu-id="94477-278">Entre no aplicativo móvel do Gerenciamento de Depósito como um usuário no depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="94477-278">Sign in to the Warehouse Management mobile app as a user in warehouse *61*.</span></span> <span data-ttu-id="94477-279">(Insira *61* como a ID do usuário e *1* como a senha.)</span><span class="sxs-lookup"><span data-stu-id="94477-279">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="94477-280">Vá para **Estoque \> Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="94477-280">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="94477-281">Você será solicitado a concluir o primeiro trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-281">You're prompted to complete the first replenishment work.</span></span> <span data-ttu-id="94477-282">O número do item, a quantidade e o local de separação são mostrados.</span><span class="sxs-lookup"><span data-stu-id="94477-282">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="94477-283">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-283">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="94477-284">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-284">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="94477-285">O sistema gera um número de placa de licença de destino para a nova placa de licença para o item separado.</span><span class="sxs-lookup"><span data-stu-id="94477-285">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="94477-286">Selecione **OK** para confirmar o valor.</span><span class="sxs-lookup"><span data-stu-id="94477-286">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="94477-287">O trabalho de colocação mostrado orienta o usuário a colocar a placa de licença de destino no local de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-287">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="94477-288">O local de *colocação* deve ser **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="94477-288">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="94477-289">Confirme os detalhes de colocação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-289">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="94477-290">Você recebe uma mensagem "Trabalho Concluído" e os detalhes da próxima tarefa de separação de reabastecimento são mostrados: número do item, quantidade e local de separação.</span><span class="sxs-lookup"><span data-stu-id="94477-290">You receive a "Work Completed" message, and the details of the next replenishment pick task are shown: the item number, quantity, and location to pick from.</span></span> <span data-ttu-id="94477-291">O local de separação será o mesmo que o primeiro local de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-291">The picking location will be the same as the first replenishment location.</span></span> <span data-ttu-id="94477-292">Portanto, a placa de licença terá a mesma ID da placa de licença usada para a primeira tarefa de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-292">Therefore, the license plate will have the same license plate ID that was used for the first replenishment work task.</span></span>

1. <span data-ttu-id="94477-293">Repita as etapas anteriores para concluir o trabalho de reabastecimento para a segunda tarefa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-293">Repeat the preceding steps to complete the replenishment work for the second work task.</span></span> <span data-ttu-id="94477-294">A quantidade e a placa de licença de destino serão diferentes da quantidade e da placa da licença de destino para a primeira tarefa de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-294">The quantity and target license plate will differ from the quantity and target license plate for the first work task.</span></span>

<span data-ttu-id="94477-295">Depois que o segundo trabalho de reabastecimento for concluído, você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-295">After the second replenishment work is completed, you receive a "Work Completed" message.</span></span> <span data-ttu-id="94477-296">O dispositivo móvel também informa que não há trabalho disponível, embora algum trabalho de reabastecimento permaneça.</span><span class="sxs-lookup"><span data-stu-id="94477-296">The mobile device also informs you that there is no work available, even though some replenishment work remains.</span></span> <span data-ttu-id="94477-297">Esse comportamento ocorre porque o trabalho de reabastecimento tem um status de disponibilidade *Retido* e, portanto, é marcado como **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="94477-297">This behavior occurs because the replenishment work has an availability status of *Held* and is therefore marked as **Blocked**.</span></span>

<span data-ttu-id="94477-298">O status *Retido* foi disparado porque o perfil de localização do local de separação ao qual o trabalho é atribuído tem um valor **Quantidade de excesso** de *0,65 PL*.</span><span class="sxs-lookup"><span data-stu-id="94477-298">The *Held* status was triggered because the location profile for the picking location that the work is being assigned to has an **Overflow quantity** value of *0.65 PL*.</span></span> <span data-ttu-id="94477-299">As duas tarefas de trabalho de reabastecimento anteriores preencheram o local quase no limite de excesso do item *T0100*.</span><span class="sxs-lookup"><span data-stu-id="94477-299">The two previous replenishment work tasks filled the location almost to its overflow limit for item *T0100*.</span></span> <span data-ttu-id="94477-300">(A conversão de unidades do item é *1 PL = 100 cada*.) Portanto, o trabalho de reabastecimento restante levaria o local a ultrapassar o limite de excesso.</span><span class="sxs-lookup"><span data-stu-id="94477-300">(The unit conversion for the item is *1 PL = 100 ea*.) Therefore, the remaining replenishment work would cause the location to exceed its overflow limit.</span></span>

<span data-ttu-id="94477-301">Até que o estoque suficiente seja separado do local para deixá-lo abaixo do limite de liberação de trabalho no item de menu do dispositivo móvel, este trabalho de reabastecimento permanecerá bloqueado.</span><span class="sxs-lookup"><span data-stu-id="94477-301">Until enough inventory is picked from the location to bring it below the work release threshold on the mobile device menu item, this replenishment work will remain blocked.</span></span>

#### <a name="sales-order-pick"></a><span data-ttu-id="94477-302">Separação da ordem de venda</span><span class="sxs-lookup"><span data-stu-id="94477-302">Sales order pick</span></span>

<span data-ttu-id="94477-303">Antes da conclusão da tarefa de trabalho de reabastecimento restante, o estoque do local de separação deve ser esgotado até um nível em que o trabalho de reabastecimento restante possa ser desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="94477-303">Before the remaining replenishment work task can be completed, the picking location must be depleted of inventory to a level where the remaining replenishment work can be unblocked.</span></span> <span data-ttu-id="94477-304">Em outras palavras, a soma da quantidade de estoque disponível no local e a quantidade de reabastecimento não pode exceder o valor **Quantidade de excesso**.</span><span class="sxs-lookup"><span data-stu-id="94477-304">In other words, the sum of the quantity of on-hand inventory in the location and the replenishment quantity can't exceed the **Overflow quantity** value.</span></span> <span data-ttu-id="94477-305">Quando essa soma for menor do que a quantidade de excesso, o trabalho de reabastecimento restante será desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="94477-305">When this sum is less than the overflow quantity, the remaining replenishment work will be unblocked.</span></span>

1. <span data-ttu-id="94477-306">Entre no aplicativo móvel do Gerenciamento de Depósito como um usuário no depósito *61*.</span><span class="sxs-lookup"><span data-stu-id="94477-306">Sign in to the Warehouse Management mobile app as a user in warehouse *61*.</span></span> <span data-ttu-id="94477-307">(Insira *61* como a ID do usuário e *1* como a senha.)</span><span class="sxs-lookup"><span data-stu-id="94477-307">(Enter *61* as the user ID and *1* as the password.)</span></span>
1. <span data-ttu-id="94477-308">Vá para **Saída \> Separação de Venda**.</span><span class="sxs-lookup"><span data-stu-id="94477-308">Go to **Outbound \> Sales Picking**.</span></span>
1. <span data-ttu-id="94477-309">Insira a primeira ID de trabalho para a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="94477-309">Enter the first work ID for sales order 1.</span></span>

    <span data-ttu-id="94477-310">Consulte as IDs de trabalho para ordens de venda que você anotou, anteriormente, na página **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="94477-310">Refer to the work IDs for sales orders that you made a note of earlier, on the **Work details** page.</span></span> <span data-ttu-id="94477-311">A ID de trabalho inserida aqui gerará um trabalho de separação para uma quantidade de 10 cada de dois locais separados.</span><span class="sxs-lookup"><span data-stu-id="94477-311">The work ID that you enter here will generate pick work for a quantity of 10 ea from two separate locations.</span></span>

1. <span data-ttu-id="94477-312">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-312">Select **OK**.</span></span>

    <span data-ttu-id="94477-313">A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção para a primeira localização.</span><span class="sxs-lookup"><span data-stu-id="94477-313">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the first location.</span></span>

1. <span data-ttu-id="94477-314">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-314">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="94477-315">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-315">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="94477-316">A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção para a próxima localização.</span><span class="sxs-lookup"><span data-stu-id="94477-316">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from for the next location.</span></span>

1. <span data-ttu-id="94477-317">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-317">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="94477-318">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-318">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="94477-319">A página **Ordens de venda: colocar** orienta a armazenar os trabalhos de separação concluídos no local de preparo de saída.</span><span class="sxs-lookup"><span data-stu-id="94477-319">The **Sales orders: Put** page instructs you to put away both the completed picking works to the outbound staging location.</span></span>

1. <span data-ttu-id="94477-320">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-320">Select **OK**.</span></span>

    <span data-ttu-id="94477-321">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-321">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="94477-322">Insira a segunda ID de trabalho para a ordem de venda 1.</span><span class="sxs-lookup"><span data-stu-id="94477-322">Enter the second work ID for sales order 1.</span></span>

    <span data-ttu-id="94477-323">Há apenas uma tarefa de seleção para esta ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-323">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="94477-324">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-324">Select **OK**.</span></span>

    <span data-ttu-id="94477-325">A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.</span><span class="sxs-lookup"><span data-stu-id="94477-325">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="94477-326">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-326">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="94477-327">A placa de licença especificada será uma das placas de licença geradas pelo sistema das tarefas de trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-327">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="94477-328">Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.</span><span class="sxs-lookup"><span data-stu-id="94477-328">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="94477-329">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-329">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="94477-330">Confirme as instruções da tarefa de colocação para o local de preparo de saída.</span><span class="sxs-lookup"><span data-stu-id="94477-330">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="94477-331">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-331">Select **OK**.</span></span>

    <span data-ttu-id="94477-332">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-332">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="94477-333">A ordem de venda 2 é bloqueada para separação porque a tarefa de reabastecimento à qual ela está vinculada não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="94477-333">Sales order 2 is blocked from picking because the replenishment task that it's linked to isn't completed.</span></span> <span data-ttu-id="94477-334">No momento, ainda há uma quantidade de 30 cada no local de separação e a quantidade de reabastecimento para a ordem de venda 2 é de 60 cada.</span><span class="sxs-lookup"><span data-stu-id="94477-334">Currently, there is still a quantity of 30 ea in the picking location, and the replenishment quantity for sales order 2 is 60 ea.</span></span> <span data-ttu-id="94477-335">A soma do estoque disponível e do estoque de reabastecimento (90 cada) excede a quantidade de excesso de 0,65 PL (ou 65 cada).</span><span class="sxs-lookup"><span data-stu-id="94477-335">The sum of the on-hand inventory and the replenishment inventory (90 ea) exceeds the overflow quantity of 0.65 PL (or 65 ea).</span></span> <span data-ttu-id="94477-336">Para que o trabalho de reabastecimento possa ser concluído, a ordem de venda 3 deve ser separada.</span><span class="sxs-lookup"><span data-stu-id="94477-336">Before the replenishment work can be completed, sales order 3 must be picked.</span></span>

1. <span data-ttu-id="94477-337">Insira a ID de trabalho da ordem de venda 3.</span><span class="sxs-lookup"><span data-stu-id="94477-337">Enter the work ID for sales order 3.</span></span>

    <span data-ttu-id="94477-338">Há apenas uma tarefa de seleção para esta ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-338">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="94477-339">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-339">Select **OK**.</span></span>

    <span data-ttu-id="94477-340">A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.</span><span class="sxs-lookup"><span data-stu-id="94477-340">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="94477-341">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-341">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="94477-342">A placa de licença especificada será uma das placas de licença geradas pelo sistema das tarefas de trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-342">The license plate that you specify will be one of the system-generated license plates from the replenishment work tasks.</span></span> <span data-ttu-id="94477-343">Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.</span><span class="sxs-lookup"><span data-stu-id="94477-343">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="94477-344">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-344">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="94477-345">Confirme as instruções da tarefa de colocação para o local de preparo de saída.</span><span class="sxs-lookup"><span data-stu-id="94477-345">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="94477-346">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-346">Select **OK**.</span></span>

    <span data-ttu-id="94477-347">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-347">You receive a "Work Completed" message.</span></span>

<span data-ttu-id="94477-348">Assim que a soma da quantidade disponível no local de separação e a quantidade de reabastecimento estiver abaixo do limite, você poderá processar o trabalho de reabastecimento restante.</span><span class="sxs-lookup"><span data-stu-id="94477-348">As soon as the sum of the on-hand quantity in the picking location and the replenishment quantity is below the threshold, you will be able to process the remaining replenishment work.</span></span>

<span data-ttu-id="94477-349">Retorne à página **Detalhes do trabalho** e observe que a disponibilidade do trabalho de reabastecimento para a parte final do reabastecimento (para a ordem de venda 2) está *Aberta*, pois há espaço suficiente no local para aceitar o reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-349">Return to the **Work details** page, and notice that the replenishment work availability for the final piece of replenishment (for sales order 2) is *Open*, because there is now enough space in the location to accept the replenishment.</span></span>

<span data-ttu-id="94477-350">Agora você pode processar este trabalho de reabastecimento por meio do dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="94477-350">You can now process this replenishment work via the mobile device.</span></span>

1. <span data-ttu-id="94477-351">Vá para **Estoque \> Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="94477-351">Go to **Inventory \> Replenishment**.</span></span>

    <span data-ttu-id="94477-352">Você será solicitado a concluir o trabalho restante de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-352">You're prompted to complete the remaining replenishment work.</span></span> <span data-ttu-id="94477-353">O número do item, a quantidade e o local de separação são mostrados.</span><span class="sxs-lookup"><span data-stu-id="94477-353">The item number, quantity, and location to pick from are shown.</span></span>

1. <span data-ttu-id="94477-354">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-354">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>
1. <span data-ttu-id="94477-355">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-355">Select the **OK** button (check mark symbol).</span></span>

    <span data-ttu-id="94477-356">O sistema gera um número de placa de licença de destino para a nova placa de licença para o item separado.</span><span class="sxs-lookup"><span data-stu-id="94477-356">The system generates a target license plate number for the new license plate for the picked item.</span></span>

1. <span data-ttu-id="94477-357">Selecione **OK** para confirmar o valor.</span><span class="sxs-lookup"><span data-stu-id="94477-357">Select **OK** to confirm the value.</span></span>

    <span data-ttu-id="94477-358">O trabalho de colocação mostrado orienta o usuário a colocar a placa de licença de destino no local de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-358">Put work is shown that instructs the user to put the target license plate into the replenishment location.</span></span> <span data-ttu-id="94477-359">O local de *colocação* deve ser **06A01R2S1B**.</span><span class="sxs-lookup"><span data-stu-id="94477-359">The *Put* location should be **06A01R2S1B**.</span></span>

1. <span data-ttu-id="94477-360">Confirme os detalhes de colocação e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-360">Confirm the put details, and select **OK**.</span></span>

    <span data-ttu-id="94477-361">Você recebe mensagens "Trabalho Concluído" e "Nenhum Trabalho Disponível".</span><span class="sxs-lookup"><span data-stu-id="94477-361">You receive "Work Completed" and "No Work Available" messages.</span></span>

<span data-ttu-id="94477-362">Agora, você pode separar a ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="94477-362">You can now pick sales order 2.</span></span> <span data-ttu-id="94477-363">Ele se tornou desbloqueada quando o trabalho de reabastecimento vinculado à ordem de venda foi concluído.</span><span class="sxs-lookup"><span data-stu-id="94477-363">It became unblocked when the replenishment work that is linked to the sales order was completed.</span></span>

1. <span data-ttu-id="94477-364">Insira a ID de trabalho da ordem de venda 2.</span><span class="sxs-lookup"><span data-stu-id="94477-364">Enter the work ID for sales order 2.</span></span>

    <span data-ttu-id="94477-365">Há apenas uma tarefa de seleção para esta ID de trabalho.</span><span class="sxs-lookup"><span data-stu-id="94477-365">There is only one pick task for this work ID.</span></span>

1. <span data-ttu-id="94477-366">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-366">Select **OK**.</span></span>

    <span data-ttu-id="94477-367">A página de tarefa **Ordens de venda: separar** mostra o número do item, a quantidade e o local para seleção.</span><span class="sxs-lookup"><span data-stu-id="94477-367">The **Sales orders: Pick** task page shows the item number, quantity, and location to pick from.</span></span>

1. <span data-ttu-id="94477-368">No campo **LP**, insira o número da placa de licença para o item na localização que é mostrada.</span><span class="sxs-lookup"><span data-stu-id="94477-368">In the **LP** field, enter the license plate number for the item in the location that is shown.</span></span>

    <span data-ttu-id="94477-369">A placa de licença especificada será a placa de licença gerada pelo sistema da tarefa de trabalho de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="94477-369">The license plate that you specify will be the system-generated license plate from the replenishment work task.</span></span> <span data-ttu-id="94477-370">Para verificar se você captura a ID da placa de licença correta, verifique o estoque na página **Lista disponível** para o item, o local e a quantidade.</span><span class="sxs-lookup"><span data-stu-id="94477-370">To make sure that you capture the correct license plate ID, check the inventory on the **On-hand list** page for the item, location, and quantity.</span></span>

1. <span data-ttu-id="94477-371">Selecione o botão **OK** (símbolo de marca de seleção).</span><span class="sxs-lookup"><span data-stu-id="94477-371">Select the **OK** button (check mark symbol).</span></span>
1. <span data-ttu-id="94477-372">Confirme as instruções da tarefa de colocação para o local de preparo de saída.</span><span class="sxs-lookup"><span data-stu-id="94477-372">Confirm the instructions for the put task to the outbound staging location.</span></span>
1. <span data-ttu-id="94477-373">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="94477-373">Select **OK**.</span></span>

    <span data-ttu-id="94477-374">Você receberá uma mensagem "Trabalho Concluído".</span><span class="sxs-lookup"><span data-stu-id="94477-374">You receive a "Work Completed" message.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="94477-375">Observações e dicas</span><span class="sxs-lookup"><span data-stu-id="94477-375">Notes and tips</span></span>

- <span data-ttu-id="94477-376">Essa funcionalidade funciona com todos os tipos de reabastecimento: demanda de onda, mín./máx., demanda de carga e slots.</span><span class="sxs-lookup"><span data-stu-id="94477-376">This functionality works with all types of replenishment: wave demand, min/max, load demand, and slotting.</span></span>
- <span data-ttu-id="94477-377">Se desejar, você poderá substituir manualmente a disponibilidade de trabalho de reabastecimento para cada cabeçalho de trabalho da página **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="94477-377">You can manually override the replenishment work availability for each work header from the **Work details** page if you want.</span></span>
- <span data-ttu-id="94477-378">Quando o sistema define a disponibilidade do trabalho de reabastecimento, ele considera qualquer estoque que já esteja no local antes da conclusão de qualquer trabalho</span><span class="sxs-lookup"><span data-stu-id="94477-378">When the system sets the replenishment work availability, it considers any inventory that is already in the location before any work is completed</span></span>
- <span data-ttu-id="94477-379">Cada item de trabalho da ordem de venda é vinculado a um trabalho de reabastecimento específico.</span><span class="sxs-lookup"><span data-stu-id="94477-379">Each piece of sales order work is linked to a specific replenishment work.</span></span> <span data-ttu-id="94477-380">Não há funcionalidade de disponibilidade de trabalho de vendas correspondente.</span><span class="sxs-lookup"><span data-stu-id="94477-380">There is no corresponding sales work availability functionality.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]