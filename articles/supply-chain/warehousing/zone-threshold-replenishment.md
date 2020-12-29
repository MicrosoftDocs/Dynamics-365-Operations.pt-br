---
title: Reabastecimento de limite de zona
description: O reabastecimento baseado em zona usa uma estratégia de reabastecimento mínimo/máximo (mín./máx.), mas ele avalia zonas de depósito inteiras e não apenas locais individuais. Portanto, os gerentes de depósito podem aprender mais rápido quando é necessário um estoque adicional em uma zona de separação.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocDirHint, WHSLocDirTable, WHSRequestType
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 6f4ddd03ec16ac43b007b904eb688563735e0941
ms.sourcegitcommit: d9bffbeae2ba14f06294dd275383077d4d65c4fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/01/2020
ms.locfileid: "4654163"
---
# <a name="zone-threshold-replenishment"></a><span data-ttu-id="ae335-104">Reabastecimento de limite de zona</span><span class="sxs-lookup"><span data-stu-id="ae335-104">Zone threshold replenishment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae335-105">O reabastecimento baseado em zona usa uma estratégia de [reabastecimento](replenishment.md) mínimo/máximo (mín./máx.), mas ele avalia zonas de depósito inteiras e não apenas locais individuais.</span><span class="sxs-lookup"><span data-stu-id="ae335-105">Zone-based replenishment uses a minimum/maximum (min/max) [replenishment](replenishment.md) strategy, but it evaluates whole warehouse zones instead of just individual locations.</span></span> <span data-ttu-id="ae335-106">Portanto, os gerentes de depósito podem aprender mais rápido quando é necessário um estoque adicional em uma zona de separação.</span><span class="sxs-lookup"><span data-stu-id="ae335-106">Therefore, warehouse managers can more quickly learn when additional inventory is required in a picking zone.</span></span>

<span data-ttu-id="ae335-107">A configuração desse recurso é semelhante à configuração de reabastecimento baseada em local.</span><span class="sxs-lookup"><span data-stu-id="ae335-107">The setup for this feature resembles the setup for location-based replenishment.</span></span> <span data-ttu-id="ae335-108">No entanto, ao configurar um modelo para reabastecimento mín./máx., você também pode especificar se o limite deve ser avaliado por local ou por zona.</span><span class="sxs-lookup"><span data-stu-id="ae335-108">However, when you set up a template for min/max replenishment, you can also specify whether the threshold should be evaluated per location or per zone.</span></span> <span data-ttu-id="ae335-109">Se você configurar a avaliação baseada em zonas, deverá adicionar zonas específicas à consulta de seleção de zona.</span><span class="sxs-lookup"><span data-stu-id="ae335-109">If you set up evaluation that is based on zones, you must add specific zones to the zone selection query.</span></span>

<span data-ttu-id="ae335-110">Como o reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona segue a configuração de um limite de estoque mínimo que dispara a criação de trabalho de reabastecimento para os itens selecionados.</span><span class="sxs-lookup"><span data-stu-id="ae335-110">Like location-based min/max replenishment, zone-based min/max replenishment is based the setup of a minimum inventory threshold that triggers the creation of replenishment work for selected items.</span></span> <span data-ttu-id="ae335-111">Esse trabalho de reabastecimento aumentará o estoque até o limite máximo especificado para a zona.</span><span class="sxs-lookup"><span data-stu-id="ae335-111">This replenishment work will increase inventory up to the specified maximum threshold for the zone.</span></span>

> [!NOTE]
> <span data-ttu-id="ae335-112">Não há suporte aos processos de reabastecimento de zona para grades de produtos na versão atual.</span><span class="sxs-lookup"><span data-stu-id="ae335-112">Zone replenishment processes for product variants aren't supported in the current release.</span></span>


<span data-ttu-id="ae335-113">Diferentemente do reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona não exige locais fixos para avaliar se os locais devem armazenar um item específico.</span><span class="sxs-lookup"><span data-stu-id="ae335-113">Unlike location-based min/max replenishment, zone-based min/max replenishment doesn't require fixed locations to evaluate whether locations should store a specific item.</span></span> <span data-ttu-id="ae335-114">Portanto, o reabastecimento baseado em zona permite que você use o reabastecimento mín./máx. mesmo que não tenha locais fixos para cada item ou grade de item no depósito.</span><span class="sxs-lookup"><span data-stu-id="ae335-114">Therefore, zone-based replenishment lets you use min/max replenishment even if you don't have fixed locations for each item or item variant in the warehouse.</span></span> <span data-ttu-id="ae335-115">Quando uma quantidade na zona está abaixo do limite mínimo especificado, o trabalho de reabastecimento é criado.</span><span class="sxs-lookup"><span data-stu-id="ae335-115">When a quantity in the zone falls below the specified minimum threshold, replenishment work is created.</span></span> <span data-ttu-id="ae335-116">As diretivas de localização determinarão o local específico em que o estoque deverá ser inserido.</span><span class="sxs-lookup"><span data-stu-id="ae335-116">Location directives will determine which specific location the inventory should be put into.</span></span>

## <a name="turn-on-the-zone-threshold-replenishment-feature"></a><span data-ttu-id="ae335-117">Ativar o recurso Reabastecimento de limite de zona</span><span class="sxs-lookup"><span data-stu-id="ae335-117">Turn on the Zone threshold replenishment feature</span></span>

<span data-ttu-id="ae335-118">Para que você possa usar o recurso *Reabastecimento de limite de zona*, ele deverá estar ativado no sistema.</span><span class="sxs-lookup"><span data-stu-id="ae335-118">Before you can use the *Zone threshold replenishment* feature, it must be turned on in your system.</span></span> <span data-ttu-id="ae335-119">Os administradores podem usar as configurações de [gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo se necessário.</span><span class="sxs-lookup"><span data-stu-id="ae335-119">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ae335-120">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="ae335-120">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ae335-121">**Módulo:** *Gerenciamento de Depósito*</span><span class="sxs-lookup"><span data-stu-id="ae335-121">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ae335-122">**Nome do recurso** *Reabastecimento de limite de zona*</span><span class="sxs-lookup"><span data-stu-id="ae335-122">**Feature name:** *Zone threshold replenishment*</span></span>

## <a name="set-up-zone-based-replenishment"></a><a name="setup"></a><span data-ttu-id="ae335-123">Configurar reabastecimento baseado em zona</span><span class="sxs-lookup"><span data-stu-id="ae335-123">Set up zone-based replenishment</span></span>

<span data-ttu-id="ae335-124">Para configurar o reabastecimento baseado em zona, você deve configurar várias partes do sistema.</span><span class="sxs-lookup"><span data-stu-id="ae335-124">To set up zone-based replenishment, you must configure several parts of the system.</span></span> <span data-ttu-id="ae335-125">Esta seção apresenta as várias configurações e fornece os valores de dados de demonstração que você poderá inserir se desejar trabalhar no cenário no final deste tópico.</span><span class="sxs-lookup"><span data-stu-id="ae335-125">This section introduces the various settings and provides demo data values that you can enter if you want to work through the scenario at the end of this topic.</span></span>

### <a name="set-up-directive-codes"></a><span data-ttu-id="ae335-126">Configurar códigos de diretiva</span><span class="sxs-lookup"><span data-stu-id="ae335-126">Set up directive codes</span></span>

<span data-ttu-id="ae335-127">Os [códigos de diretiva](control-warehouse-location-directives.md) permitem que você seja mais específico ao definir o modelo de localização usado em um modelo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ae335-127">[Directive codes](control-warehouse-location-directives.md) let you be more specific when you define the location template that is used in a work template.</span></span> <span data-ttu-id="ae335-128">Cada código estabelece um valor comum ao qual você pode se referir ao configurar cada tipo de modelo.</span><span class="sxs-lookup"><span data-stu-id="ae335-128">Each code establishes a common value that you can refer to when you configure each type of template.</span></span>

#### <a name="view-and-edit-directive-codes"></a><span data-ttu-id="ae335-129">Exibir e editar códigos de diretiva</span><span class="sxs-lookup"><span data-stu-id="ae335-129">View and edit directive codes</span></span>

<span data-ttu-id="ae335-130">Para exibir ou editar códigos de diretiva, vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.</span><span class="sxs-lookup"><span data-stu-id="ae335-130">To view or edit your directive codes, go to **Warehouse management \> Setup \> Directive codes**.</span></span>

#### <a name="prepare-demo-data-directive-codes"></a><span data-ttu-id="ae335-131">Preparar códigos de diretiva de dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="ae335-131">Prepare demo data directive codes</span></span>

<span data-ttu-id="ae335-132">Este exemplo mostra como preparar um código de diretiva.</span><span class="sxs-lookup"><span data-stu-id="ae335-132">This example shows how to prepare a directive code.</span></span> <span data-ttu-id="ae335-133">Se pretende trabalhar no cenário no final deste tópico, use os valores de dados de demonstração fornecidos aqui.</span><span class="sxs-lookup"><span data-stu-id="ae335-133">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="ae335-134">Caso contrário, use seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="ae335-134">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="ae335-135">Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ae335-135">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="ae335-136">Vá para **Gerenciamento de depósito \> Configuração \> Códigos de diretiva**.</span><span class="sxs-lookup"><span data-stu-id="ae335-136">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="ae335-137">No Painel de Ação, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-137">On the Action Pane, select **New** to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-138">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-138">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-139">**Código de diretiva:** _Reabastecimento de zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-139">**Directive code:** _Zone replen_</span></span>
    - <span data-ttu-id="ae335-140">**Descrição de diretiva:** _Reabastecimento de zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-140">**Directive description:** _Zone replenishment_</span></span>

1. <span data-ttu-id="ae335-141">Selecione **Salvar** para salvar o novo código.</span><span class="sxs-lookup"><span data-stu-id="ae335-141">Select **Save** to save the new code.</span></span>

### <a name="set-up-replenishment-templates"></a><span data-ttu-id="ae335-142">Configurar modelos de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="ae335-142">Set up replenishment templates</span></span>

<span data-ttu-id="ae335-143">Os [modelos de reabastecimento mín./máx.](tasks/set-up-min-max-replenishment-process.md) são o principal mecanismo para manter níveis ideais em locais de separação.</span><span class="sxs-lookup"><span data-stu-id="ae335-143">[Min/max replenishment templates](tasks/set-up-min-max-replenishment-process.md) are the primary mechanism for maintaining optimal levels in picking locations.</span></span> <span data-ttu-id="ae335-144">Nesses modelos, você deve configurar as regras que serão usadas para reabastecer o estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="ae335-144">In these templates, you must set up the rules that will be used to replenish inventory in the warehouse.</span></span> <span data-ttu-id="ae335-145">O reabastecimento para o qual os modelos podem ser usados inclui o reabastecimento baseado em zona.</span><span class="sxs-lookup"><span data-stu-id="ae335-145">The replenishment that the templates can be used for includes zone-based replenishment.</span></span>

#### <a name="view-and-edit-replenishment-templates"></a><span data-ttu-id="ae335-146">Exibir e editar modelos de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="ae335-146">View and edit replenishment templates</span></span>

<span data-ttu-id="ae335-147">Um modelo de reabastecimento é um conjunto de regras que controlam como e quando um local é reabastecido.</span><span class="sxs-lookup"><span data-stu-id="ae335-147">A replenishment template is a set of rules that control when and how a location is replenished.</span></span> <span data-ttu-id="ae335-148">Selecione um modelo para controlar quando e como o reabastecimento é feito.</span><span class="sxs-lookup"><span data-stu-id="ae335-148">You select a template to control when and how replenishment is done.</span></span> <span data-ttu-id="ae335-149">Para exibir ou editar modelos de reabastecimento, vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="ae335-149">To view or edit your replenishment templates, go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>

#### <a name="prepare-a-demo-data-replenishment-template"></a><span data-ttu-id="ae335-150">Preparar um modelo de reabastecimento de dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="ae335-150">Prepare a demo data replenishment template</span></span>

<span data-ttu-id="ae335-151">Este exemplo mostra como preparar um modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-151">This example shows how to prepare a replenishment template.</span></span> <span data-ttu-id="ae335-152">Se pretende trabalhar no cenário no final deste tópico, use os valores de dados de demonstração fornecidos aqui.</span><span class="sxs-lookup"><span data-stu-id="ae335-152">If you're planning to work through the scenario at the end of this topic, use the demo data values that are provided here.</span></span> <span data-ttu-id="ae335-153">Caso contrário, use seus próprios valores.</span><span class="sxs-lookup"><span data-stu-id="ae335-153">Otherwise, use your own values.</span></span>

1. <span data-ttu-id="ae335-154">Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ae335-154">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="ae335-155">Vá para **Gerenciamento de depósito \> Configuração \> Reabastecimento \> Modelos de reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="ae335-155">Go to **Warehouse management \> Setup \> Replenishment \> Replenishment templates**.</span></span>
1. <span data-ttu-id="ae335-156">Selecione **Editar** para colocar a página no modo de edição.</span><span class="sxs-lookup"><span data-stu-id="ae335-156">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="ae335-157">No Painel de Ações, selecione **Novo** para adicionar uma linha à grade **Visão geral**.</span><span class="sxs-lookup"><span data-stu-id="ae335-157">On the Action Pane, select **New** to add a row to the **Overview** grid.</span></span>
1. <span data-ttu-id="ae335-158">Na nova linha, defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="ae335-158">In the new row, set the following values.</span></span> <span data-ttu-id="ae335-159">Aceite os valores padrão para todos os demais campos.</span><span class="sxs-lookup"><span data-stu-id="ae335-159">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="ae335-160">**Modelo de reabastecimento:** _Reabastecimento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-160">**Replenish template:** _Zone min/max replen_</span></span>
    - <span data-ttu-id="ae335-161">**Descrição:** _Reabastecimento mín./máx. de zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-161">**Description:** _Zone min/max replenishment_</span></span>
    - <span data-ttu-id="ae335-162">**Tipo de reabastecimento:** _Mínimo ou máximo_</span><span class="sxs-lookup"><span data-stu-id="ae335-162">**Replenishment type:** _Minimum or maximum_</span></span>

1. <span data-ttu-id="ae335-163">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae335-163">Select **Save**.</span></span>
1. <span data-ttu-id="ae335-164">Enquanto a nova linha ainda estiver selecionada na grade **Visão geral**, selecione **Novo** acima da grade **Detalhes do Modelo de Reabastecimento** para adicionar uma linha associada ao modelo de reabastecimento *Reabastecimento mín./máx. de zona* que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="ae335-164">While the new row is still selected in the **Overview** grid, select **New** above the **Replenishment Template Details** grid to add a row that is associated with the *Zone Min/Max replen* replenishment template that you just created.</span></span>
1. <span data-ttu-id="ae335-165">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-165">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-166">**Número de sequência:** Insira _1_.</span><span class="sxs-lookup"><span data-stu-id="ae335-166">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="ae335-167">**Descrição:** Insira _Seleção de reabastecimento de zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-167">**Description:** Enter _Pick zone replenishment_.</span></span>
    - <span data-ttu-id="ae335-168">**Unidade de reabastecimento:** Selecione _ea_.</span><span class="sxs-lookup"><span data-stu-id="ae335-168">**Replenishment unit:** Select _ea_.</span></span>
    - <span data-ttu-id="ae335-169">**Tipo de solicitação:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ae335-169">**Request type:** Leave this field blank.</span></span>
    - <span data-ttu-id="ae335-170">**Código de diretiva:** Este campo vincula o modelo de reabastecimento a uma diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="ae335-170">**Directive code:** This field links the replenishment template with a location directive.</span></span> <span data-ttu-id="ae335-171">Selecione o código de diretiva de dados de demonstração criado anteriormente (_Reabastecimento_).</span><span class="sxs-lookup"><span data-stu-id="ae335-171">Select the demo data directive code that you created earlier (_Zone replen_).</span></span>
    - <span data-ttu-id="ae335-172">**Modelo de trabalho:** Deixar este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ae335-172">**Work template:** Leave this field blank.</span></span>
    - <span data-ttu-id="ae335-173">**Quantidade mínima:** Este campo define a quantidade na qual o reabastecimento será disparado.</span><span class="sxs-lookup"><span data-stu-id="ae335-173">**Minimum quantity:** This field sets the quantity that replenishment will be triggered at.</span></span> <span data-ttu-id="ae335-174">Insira _50_.</span><span class="sxs-lookup"><span data-stu-id="ae335-174">Enter _50_.</span></span>
    - <span data-ttu-id="ae335-175">**Quantidade máxima:** Este campo define a quantidade máxima de um item que pode estar presente em uma zona.</span><span class="sxs-lookup"><span data-stu-id="ae335-175">**Maximum quantity:** This field sets the maximum quantity of an item that can be present in a zone.</span></span> <span data-ttu-id="ae335-176">O trabalho de reabastecimento gerado vai aumentar o estoque para essa quantidade.</span><span class="sxs-lookup"><span data-stu-id="ae335-176">Generated replenishment work will increase inventory to this quantity.</span></span> <span data-ttu-id="ae335-177">Insira _150_.</span><span class="sxs-lookup"><span data-stu-id="ae335-177">Enter _150_.</span></span>
    - <span data-ttu-id="ae335-178">**Unidade:** Este campo define a unidade para os valores mínimo e máximo.</span><span class="sxs-lookup"><span data-stu-id="ae335-178">**Unit:** This field sets the unit for the minimum and maximum values.</span></span> <span data-ttu-id="ae335-179">Selecione _ea_.</span><span class="sxs-lookup"><span data-stu-id="ae335-179">Select _ea_.</span></span>
    - <span data-ttu-id="ae335-180">**Incremento de demanda:** Selecione _Arredondar_.</span><span class="sxs-lookup"><span data-stu-id="ae335-180">**Demand increment:** Select _Round up_.</span></span>
    - <span data-ttu-id="ae335-181">**Reabastecer localizações fixas vazias:** Marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-181">**Replenish empty fixed locations:** Select this check box.</span></span>
    - <span data-ttu-id="ae335-182">**Reabastecer apenas localizações fixas:** Desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-182">**Replenish only fixed locations:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-183">**Modo de consulta de produto:** Selecione _Consulta de produto_.</span><span class="sxs-lookup"><span data-stu-id="ae335-183">**Product query mode:** Select _Product query_.</span></span>
    - <span data-ttu-id="ae335-184">**Escopo do limite de reabastecimento:** este campo define se o modelo deve ser avaliado por zona ou por localização específica.</span><span class="sxs-lookup"><span data-stu-id="ae335-184">**Replenishment threshold scope:** This field defines whether the template should evaluate by zone or by specific location.</span></span> <span data-ttu-id="ae335-185">Selecione _Zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-185">Select _Zone_.</span></span>
    - <span data-ttu-id="ae335-186">**Depósito:** Selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="ae335-186">**Warehouse:** Select _61_.</span></span>

1. <span data-ttu-id="ae335-187">Selecione **Selecionar produtos** acima da grade **Detalhes do Modelo de Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="ae335-187">Select **Select products** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="ae335-188">Na caixa de diálogo **Consulta do produto**, na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-188">In the **Product query** dialog box, on the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-189">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-189">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-190">**Tabela:** _Itens_</span><span class="sxs-lookup"><span data-stu-id="ae335-190">**Table:** _Items_</span></span>
    - <span data-ttu-id="ae335-191">**Tabela derivada:** _Itens_</span><span class="sxs-lookup"><span data-stu-id="ae335-191">**Derived table:** _Items_</span></span>
    - <span data-ttu-id="ae335-192">**Campo:** _Número do item_</span><span class="sxs-lookup"><span data-stu-id="ae335-192">**Field:** _Item number_</span></span>
    - <span data-ttu-id="ae335-193">**Critérios:** _A0001_</span><span class="sxs-lookup"><span data-stu-id="ae335-193">**Criteria:** _A0001_</span></span>

1. <span data-ttu-id="ae335-194">Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae335-194">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="ae335-195">Selecione **Selecionar zonas para reabastecimento** acima da grade **Detalhes do Modelo de Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="ae335-195">Select **Select zones to replenish** above the **Replenishment Template Details** grid.</span></span>
1. <span data-ttu-id="ae335-196">Na caixa de diálogo **Consulta de zona**, na guia **Intervalo**, adicione uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-196">In the **Zone query** dialog box, on the **Range** tab, add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-197">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-197">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-198">**Tabela:** _Zona de depósito_</span><span class="sxs-lookup"><span data-stu-id="ae335-198">**Table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="ae335-199">**Tabela derivada:** _Zona de depósito_</span><span class="sxs-lookup"><span data-stu-id="ae335-199">**Derived table:** _Warehouse zone_</span></span>
    - <span data-ttu-id="ae335-200">**Campo:** _ID da zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-200">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="ae335-201">**Critérios:** _CHÃO_</span><span class="sxs-lookup"><span data-stu-id="ae335-201">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="ae335-202">Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae335-202">Select **OK** to save your query and close the dialog box.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="ae335-203">Configurar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="ae335-203">Set up location directives</span></span>

<span data-ttu-id="ae335-204">Diferente do reabastecimento mín./máx. baseado em local, o reabastecimento mín./máx. baseado em zona exige que você configure diretivas de local de seleção e diretivas de local de colocação, pois o sistema avalia a zona inteira e não apenas o local de separação do trabalho de saída.</span><span class="sxs-lookup"><span data-stu-id="ae335-204">Unlike location-based min/max replenishment, zone-based min/max replenishment requires that you set up both pick location directives and put location directives, because the system evaluates the whole zone instead of just the pick location for outbound work.</span></span>

#### <a name="view-and-edit-location-directives"></a><span data-ttu-id="ae335-205">Exibir e editar diretivas de localização</span><span class="sxs-lookup"><span data-stu-id="ae335-205">View and edit location directives</span></span>

<span data-ttu-id="ae335-206">Para exibir ou editar diretivas de localização, vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="ae335-206">To view or edit your location directives, go to **Warehouse management \> Setup \> Location directives**.</span></span>

<span data-ttu-id="ae335-207">Para obter exemplos que mostram como usar as configurações para criar as diretivas de localização de separação e as diretivas de localização de colocação, consulte a próxima seção.</span><span class="sxs-lookup"><span data-stu-id="ae335-207">For examples that show how to use the settings to create the required pick location directives and put location directives, see the next section.</span></span>

#### <a name="prepare-demo-data-location-directives"></a><span data-ttu-id="ae335-208">Preparar diretivas de localização de dados de demonstração</span><span class="sxs-lookup"><span data-stu-id="ae335-208">Prepare demo data location directives</span></span>

<span data-ttu-id="ae335-209">Para preparar dados de demonstração de forma que possam ser usados no cenário no final deste tópico, você deve criar duas diretivas de localização: uma para separação e outra para colocação.</span><span class="sxs-lookup"><span data-stu-id="ae335-209">To prepare demo data so that it can be used in the scenario at the end of this topic, you must create two location directives: one for pick and one for put.</span></span>

##### <a name="create-a-replenishment-pick-directive"></a><span data-ttu-id="ae335-210">Criar uma diretiva de separação de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="ae335-210">Create a replenishment pick directive</span></span>

1. <span data-ttu-id="ae335-211">Selecione a entidade legal **USMF** para trabalhar com os dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="ae335-211">Select the **USMF** legal entity to work with the demo data.</span></span>
1. <span data-ttu-id="ae335-212">Vá para **Gerenciamento de depósito \> Configuração \> Diretivas de localização**.</span><span class="sxs-lookup"><span data-stu-id="ae335-212">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="ae335-213">No painel esquerdo, defina o campo **Tipo de ordem de serviço** como _Reabastecimento_.</span><span class="sxs-lookup"><span data-stu-id="ae335-213">In the left pane, set the **Work order type** field to _Replenishment_.</span></span>
1. <span data-ttu-id="ae335-214">No Painel de Ações, selecione **Novo** para criar uma nova diretiva.</span><span class="sxs-lookup"><span data-stu-id="ae335-214">On the Action Pane, select **New** to create a new directive.</span></span>
1. <span data-ttu-id="ae335-215">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-215">Set the following values:</span></span>

    - <span data-ttu-id="ae335-216">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ae335-216">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="ae335-217">**Nome:** insira _Separação de zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-217">**Name:** Enter _Zone pick_.</span></span>
    - <span data-ttu-id="ae335-218">**Tipo de trabalho:** selecione _Separar_.</span><span class="sxs-lookup"><span data-stu-id="ae335-218">**Work type:** Select _Pick_.</span></span>
    - <span data-ttu-id="ae335-219">**Site:** selecione _6_.</span><span class="sxs-lookup"><span data-stu-id="ae335-219">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="ae335-220">**Depósito:** selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="ae335-220">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="ae335-221">**Código de diretiva:** deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ae335-221">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="ae335-222">**Várias SKUs:** defina esta opção como _Não_.</span><span class="sxs-lookup"><span data-stu-id="ae335-222">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="ae335-223">Selecione **Salvar** para criar uma diretiva com as configurações que você definiu até o momento.</span><span class="sxs-lookup"><span data-stu-id="ae335-223">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="ae335-224">Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-224">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="ae335-225">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="ae335-225">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ae335-226">**Número de sequência:** Insira _1_.</span><span class="sxs-lookup"><span data-stu-id="ae335-226">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="ae335-227">**Quantidade inicial:** insira _0_.</span><span class="sxs-lookup"><span data-stu-id="ae335-227">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="ae335-228">**Quantidade final:** insira _10000000_.</span><span class="sxs-lookup"><span data-stu-id="ae335-228">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="ae335-229">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ae335-229">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="ae335-230">**Localizar quantidade:** selecione _Nenhum_.</span><span class="sxs-lookup"><span data-stu-id="ae335-230">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="ae335-231">**Restringir por unidade:** marque ou desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-231">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-232">**Arredondar para unidade:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-232">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-233">**Localizar quantidade da embalagem:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-233">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-234">**Permitir divisão:** marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-234">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="ae335-235">Selecione **Salvar** para salvar a nova linha.</span><span class="sxs-lookup"><span data-stu-id="ae335-235">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="ae335-236">Embora a nova linha ainda esteja selecionada na grade **Linhas**, selecione **Nova** na FastTab **Ações de Diretiva de Localização** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-236">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-237">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-237">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-238">**Número de sequência:** Insira _1_.</span><span class="sxs-lookup"><span data-stu-id="ae335-238">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="ae335-239">**Nome:** insira _Separação em massa_.</span><span class="sxs-lookup"><span data-stu-id="ae335-239">**Name:** Enter _Pick from bulk_.</span></span>
    - <span data-ttu-id="ae335-240">**Uso de localização fixa:** selecione _Localizações fixas e não fixas_.</span><span class="sxs-lookup"><span data-stu-id="ae335-240">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="ae335-241">**Permitir estoque negativo:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-241">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-242">**Lote habilitado:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-242">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-243">**Estratégia:** selecione _Nenhum_.</span><span class="sxs-lookup"><span data-stu-id="ae335-243">**Strategy:** Select _None_.</span></span>

1. <span data-ttu-id="ae335-244">Selecione **Salvar** para salvar a nova ação.</span><span class="sxs-lookup"><span data-stu-id="ae335-244">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="ae335-245">Com a nova ação ainda selecionada, selecione **Editar consulta** acima da grade **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="ae335-245">While your new action still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="ae335-246">Uma caixa de diálogo de consulta é exibida, na qual você pode selecionar os locais a serem reabastecidos.</span><span class="sxs-lookup"><span data-stu-id="ae335-246">A query dialog box appears, where you can select the locations to replenish from.</span></span> <span data-ttu-id="ae335-247">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-247">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-248">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-248">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-249">**Tabela:** _Localizações_</span><span class="sxs-lookup"><span data-stu-id="ae335-249">**Table:** _Locations_</span></span>
    - <span data-ttu-id="ae335-250">**Tabela derivada:** _Localizações_</span><span class="sxs-lookup"><span data-stu-id="ae335-250">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="ae335-251">**Campo:** _ID da zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-251">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="ae335-252">**Critérios:** _MASSA_</span><span class="sxs-lookup"><span data-stu-id="ae335-252">**Criteria:** _BULK_</span></span>

1. <span data-ttu-id="ae335-253">Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae335-253">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="ae335-254">Selecione **Salvar** para salvar sua diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="ae335-254">Select **Save** to save your location directive.</span></span>

##### <a name="create-a-replenishment-put-directive"></a><span data-ttu-id="ae335-255">Criar uma diretiva de colocação de reabastecimento</span><span class="sxs-lookup"><span data-stu-id="ae335-255">Create a replenishment put directive</span></span>

1. <span data-ttu-id="ae335-256">Na página **Diretivas de localização**, no painel esquerdo, verifique se o campo **Tipo de ordem de serviço** ainda está definido como _Reabastecimento_.</span><span class="sxs-lookup"><span data-stu-id="ae335-256">On the **Location directives** page, in the left pane, make sure that the **Work order type** field is still set to _Replenishment_.</span></span>
1. <span data-ttu-id="ae335-257">No Painel de Ações, selecione **Novo** para criar outra nova diretiva.</span><span class="sxs-lookup"><span data-stu-id="ae335-257">On the Action Pane, select **New** to create another new directive.</span></span>
1. <span data-ttu-id="ae335-258">Defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-258">Set the following values:</span></span>

    - <span data-ttu-id="ae335-259">**Número de sequência:** aceite o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="ae335-259">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="ae335-260">**Nome:** insira _Colocação de zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-260">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="ae335-261">**Tipo de ordem de serviço:** selecione _Colocar_.</span><span class="sxs-lookup"><span data-stu-id="ae335-261">**Work order type:** Select _Put_.</span></span>
    - <span data-ttu-id="ae335-262">**Site:** selecione _6_.</span><span class="sxs-lookup"><span data-stu-id="ae335-262">**Site:** Select _6_.</span></span>
    - <span data-ttu-id="ae335-263">**Depósito:** selecione _61_.</span><span class="sxs-lookup"><span data-stu-id="ae335-263">**Warehouse:** Select _61_.</span></span>
    - <span data-ttu-id="ae335-264">**Código de diretiva:** selecione _Reabastecimento de zona_ para vincular esta diretiva de localização ao modelo de reabastecimento criado anteriormente, usando o código que você já criou.</span><span class="sxs-lookup"><span data-stu-id="ae335-264">**Directive code:** Select _Zone replen_ to link this location directive with the replenishment template that you created earlier by using the code that you created earlier.</span></span>
    - <span data-ttu-id="ae335-265">**Várias SKUs:** defina esta opção como _Não_.</span><span class="sxs-lookup"><span data-stu-id="ae335-265">**Multi SKU:** Set this option to _No_.</span></span>

1. <span data-ttu-id="ae335-266">Selecione **Salvar** para criar uma diretiva com as configurações que você definiu até o momento.</span><span class="sxs-lookup"><span data-stu-id="ae335-266">Select **Save** to create a directive that has the settings that you've configured so far.</span></span>
1. <span data-ttu-id="ae335-267">Na FastTab **Linhas**, selecione **Novo** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-267">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="ae335-268">Na nova linha, defina os valores a seguir:</span><span class="sxs-lookup"><span data-stu-id="ae335-268">On the new line, set the following values:</span></span>

    - <span data-ttu-id="ae335-269">**Número de sequência:** Insira _1_.</span><span class="sxs-lookup"><span data-stu-id="ae335-269">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="ae335-270">**Quantidade inicial:** insira _0_.</span><span class="sxs-lookup"><span data-stu-id="ae335-270">**From quantity:** Enter _0_.</span></span>
    - <span data-ttu-id="ae335-271">**Quantidade final:** insira _10000000_.</span><span class="sxs-lookup"><span data-stu-id="ae335-271">**To quantity:** Enter _10000000_.</span></span>
    - <span data-ttu-id="ae335-272">**Unidade:** Deixe este campo em branco.</span><span class="sxs-lookup"><span data-stu-id="ae335-272">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="ae335-273">**Localizar quantidade:** selecione _Nenhum_.</span><span class="sxs-lookup"><span data-stu-id="ae335-273">**Locate quantity:** Select _None_.</span></span>
    - <span data-ttu-id="ae335-274">**Restringir por unidade:** marque ou desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-274">**Restrict by unit:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-275">**Arredondar para unidade:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-275">**Round up to unit:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-276">**Localizar quantidade da embalagem:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-276">**Locate packing quantity:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-277">**Permitir divisão:** marque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-277">**Allow split:** Select this check box.</span></span>

1. <span data-ttu-id="ae335-278">Selecione **Salvar** para salvar a nova linha.</span><span class="sxs-lookup"><span data-stu-id="ae335-278">Select **Save** to save the new line.</span></span>
1. <span data-ttu-id="ae335-279">Embora a nova linha ainda esteja selecionada na grade **Linhas**, selecione **Nova** na FastTab **Ações de Diretiva de Localização** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-279">While your new line is still selected in the **Lines** grid, select **New** on the **Location Directive Actions** FastTab to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-280">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-280">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-281">**Número de sequência:** Insira _1_.</span><span class="sxs-lookup"><span data-stu-id="ae335-281">**Sequence number:** Enter _1_.</span></span>
    - <span data-ttu-id="ae335-282">**Nome:** insira _Colocação de zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-282">**Name:** Enter _Zone put_.</span></span>
    - <span data-ttu-id="ae335-283">**Uso de localização fixa:** selecione _Localizações fixas e não fixas_.</span><span class="sxs-lookup"><span data-stu-id="ae335-283">**Fixed location usage:** Select _Fixed and non-fixed locations_.</span></span>
    - <span data-ttu-id="ae335-284">**Permitir estoque negativo:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-284">**Allow negative inventory:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-285">**Lote habilitado:** desmarque esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="ae335-285">**Batch enabled:** Clear this check box.</span></span>
    - <span data-ttu-id="ae335-286">**Estratégia:** selecione _Consolidar_.</span><span class="sxs-lookup"><span data-stu-id="ae335-286">**Strategy:** Select _Consolidate_.</span></span>

1. <span data-ttu-id="ae335-287">Selecione **Salvar** para salvar a nova ação.</span><span class="sxs-lookup"><span data-stu-id="ae335-287">Select **Save** to save the new action.</span></span>
1. <span data-ttu-id="ae335-288">Com a nova ação ainda selecionada, selecione **Editar consulta** acima da grade **Ações de Diretiva de Localização**.</span><span class="sxs-lookup"><span data-stu-id="ae335-288">While your new action is still selected, select **Edit query** above the **Location Directive Actions** grid.</span></span>
1. <span data-ttu-id="ae335-289">Uma caixa de diálogo de consulta é exibida, na qual você pode selecionar a zona a ser reabastecida.</span><span class="sxs-lookup"><span data-stu-id="ae335-289">A query dialog box appears, where you can select the zone to replenish to.</span></span> <span data-ttu-id="ae335-290">Essa zona deve ser a mesma zona especificada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-290">This zone should be the same zone that is specified in the replenishment template.</span></span> <span data-ttu-id="ae335-291">Na guia **Intervalo**, selecione **Adicionar** para adicionar uma linha à grade.</span><span class="sxs-lookup"><span data-stu-id="ae335-291">On the **Range** tab, select **Add** to add a row to the grid.</span></span>
1. <span data-ttu-id="ae335-292">Na nova linha, defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="ae335-292">In the new row, set the following values:</span></span>

    - <span data-ttu-id="ae335-293">**Tabela:** _Localizações_</span><span class="sxs-lookup"><span data-stu-id="ae335-293">**Table:** _Locations_</span></span>
    - <span data-ttu-id="ae335-294">**Tabela derivada:** _Localizações_</span><span class="sxs-lookup"><span data-stu-id="ae335-294">**Derived table:** _Locations_</span></span>
    - <span data-ttu-id="ae335-295">**Campo:** _ID da zona_</span><span class="sxs-lookup"><span data-stu-id="ae335-295">**Field:** _Zone ID_</span></span>
    - <span data-ttu-id="ae335-296">**Critérios:** _CHÃO_</span><span class="sxs-lookup"><span data-stu-id="ae335-296">**Criteria:** _FLOOR_</span></span>

1. <span data-ttu-id="ae335-297">Selecione **OK** para salvar sua consulta e fechar a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="ae335-297">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="ae335-298">Selecione **Salvar** para salvar sua diretiva de localização.</span><span class="sxs-lookup"><span data-stu-id="ae335-298">Select **Save** to save your location directive.</span></span>

## <a name="scenario"></a><span data-ttu-id="ae335-299">Cenário</span><span class="sxs-lookup"><span data-stu-id="ae335-299">Scenario</span></span>

<span data-ttu-id="ae335-300">Esta seção fornece um cenário de exemplo que mostra como trabalhar com o recurso.</span><span class="sxs-lookup"><span data-stu-id="ae335-300">This section provides a sample scenario that shows how to work with the feature.</span></span>

### <a name="prepare-the-sample-data-that-is-required-for-the-sample-scenario"></a><span data-ttu-id="ae335-301">Preparar os dados de exemplo necessários para o cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="ae335-301">Prepare the sample data that is required for the sample scenario</span></span>

<span data-ttu-id="ae335-302">Antes de começar a trabalhar no cenário, você deve ativar os dados de exemplo e configurar o recurso conforme descrito nesta seção e na seção anterior deste tópico.</span><span class="sxs-lookup"><span data-stu-id="ae335-302">Before you start to work through the scenario, you must activate sample data and set up the feature as described in this section and in the previous sections of this topic.</span></span>

#### <a name="use-the-usmf-legal-entity"></a><span data-ttu-id="ae335-303">Usar a entidade legal USMF</span><span class="sxs-lookup"><span data-stu-id="ae335-303">Use the USMF legal entity</span></span>

<span data-ttu-id="ae335-304">Para trabalhar no cenário usando os registros e valores de exemplo especificados aqui, você deve usar um sistema em que os [dados de demonstração](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) padrão estejam instalados.</span><span class="sxs-lookup"><span data-stu-id="ae335-304">To work through the scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="ae335-305">Além disso, você deve selecionar a entidade legal **USMF** antes de começar.</span><span class="sxs-lookup"><span data-stu-id="ae335-305">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="prepare-additional-sample-data"></a><span data-ttu-id="ae335-306">Preparar dados de exemplo adicionais</span><span class="sxs-lookup"><span data-stu-id="ae335-306">Prepare additional sample data</span></span>

<span data-ttu-id="ae335-307">Depois de selecionar a entidade legal **USMF**, inclua os dados de exemplo adicionais necessários, conforme descrito na seção [Configurar reabastecimento baseado em zona](#setup) abordada antes neste tópico.</span><span class="sxs-lookup"><span data-stu-id="ae335-307">After you've selected the **USMF** legal entity, add the additional sample data that is required, as described in the [Set up zone-based replenishment](#setup) section earlier in this topic.</span></span>

#### <a name="check-your-on-hand-inventory"></a><span data-ttu-id="ae335-308">Verifique seu estoque disponível</span><span class="sxs-lookup"><span data-stu-id="ae335-308">Check your on-hand inventory</span></span>

<span data-ttu-id="ae335-309">Siga estas etapas para verificar se o sistema inclui estoque suficiente para dar suporte ao cenário de exemplo.</span><span class="sxs-lookup"><span data-stu-id="ae335-309">Follow these steps to make sure that your system includes enough inventory to support the sample scenario.</span></span>

1. <span data-ttu-id="ae335-310">Verifique se há estoque disponível para o item *A0001* em dois locais diferentes na zona de separação (*CHÃO*) especificada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-310">Make sure that there is on-hand inventory for item *A0001* at two different locations in the pick zone (*FLOOR*) that is specified in the replenishment template.</span></span> <span data-ttu-id="ae335-311">No entanto, o estoque total deve ser menor que a quantidade mínima necessária (*50*) que é especificada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-311">However, the total inventory should be less than the required minimum quantity (*50*) that is specified on the replenishment template.</span></span> <span data-ttu-id="ae335-312">Dessa forma, você pode simular como o cálculo ocorre para a zona inteira e não apenas para um único local.</span><span class="sxs-lookup"><span data-stu-id="ae335-312">In this way, you can simulate how the calculation occurs for the whole zone instead of just for a single location.</span></span> <span data-ttu-id="ae335-313">**Use qualquer um dos processos de depósito para ajustar o estoque, conforme necessário.**</span><span class="sxs-lookup"><span data-stu-id="ae335-313">**Use any of the warehouse processes to adjust inventory as required.**</span></span>
1. <span data-ttu-id="ae335-314">Verifique se há estoque suficiente para o item *A0001* em um local de massa especificado na diretiva de localização de seleção de zona na qual o trabalho de reabastecimento deve separar os itens da ID de zona *MASSA*.</span><span class="sxs-lookup"><span data-stu-id="ae335-314">Make sure that there is enough inventory for item *A0001* at a bulk location that is specified in the zone pick location directive where the replenishment work should pick the items from zone ID *BULK*.</span></span> <span data-ttu-id="ae335-315">O estoque total deve ser superior à quantidade máxima necessária (*150*) que é especificada no modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-315">The total inventory must be more than the required maximum quantity (*150*) that is specified in the replenishment template.</span></span>
1. <span data-ttu-id="ae335-316">Opcional, mas recomendado: siga estas etapas para criar um diário de ajuste de estoque:</span><span class="sxs-lookup"><span data-stu-id="ae335-316">Optional but recommended: Follow these steps to create an inventory adjustment journal:</span></span>

    1. <span data-ttu-id="ae335-317">Vá para **Gerenciamento de estoque \> Entradas de diário \> Itens \> Ajuste de estoque**.</span><span class="sxs-lookup"><span data-stu-id="ae335-317">Go to **Inventory management \> Journal entries \> Items \> Inventory adjustment**.</span></span>
    1. <span data-ttu-id="ae335-318">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ae335-318">Select **New**.</span></span>
    1. <span data-ttu-id="ae335-319">Na caixa de diálogo **Criar diário de estoque**, no campo **Depósito**, selecione *61*.</span><span class="sxs-lookup"><span data-stu-id="ae335-319">In the **Create inventory journal** dialog box, in the **Warehouse** field, select *61*.</span></span>
    1. <span data-ttu-id="ae335-320">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="ae335-320">Select **OK**.</span></span>
    1. <span data-ttu-id="ae335-321">Na FastTab **Linhas do diário**, use o botão **Novo** para adicionar três linhas à grade e defina os valores a seguir.</span><span class="sxs-lookup"><span data-stu-id="ae335-321">On the **Journal lines** FastTab, use the **New** button to add three lines to the grid, and set the following values.</span></span> <span data-ttu-id="ae335-322">Ao concluir a configuração de cada linha, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ae335-322">After you've finished setting up each line, select **Save**.</span></span>

        - <span data-ttu-id="ae335-323">**Linha 1:**</span><span class="sxs-lookup"><span data-stu-id="ae335-323">**Line 1:**</span></span>

            - <span data-ttu-id="ae335-324">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ae335-324">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="ae335-325">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="ae335-325">**Site:** *6*</span></span>
            - <span data-ttu-id="ae335-326">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="ae335-326">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="ae335-327">**Localização:** *02A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="ae335-327">**Location:** *02A01R1S1B*</span></span>
            - <span data-ttu-id="ae335-328">**Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ae335-328">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="ae335-329">**Quantidade:** *1000*</span><span class="sxs-lookup"><span data-stu-id="ae335-329">**Quantity:** *1000*</span></span>

        - <span data-ttu-id="ae335-330">**Linha 2:**</span><span class="sxs-lookup"><span data-stu-id="ae335-330">**Line 2:**</span></span>

            - <span data-ttu-id="ae335-331">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ae335-331">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="ae335-332">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="ae335-332">**Site:** *6*</span></span>
            - <span data-ttu-id="ae335-333">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="ae335-333">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="ae335-334">**Localização:** *07A01R2S1B*</span><span class="sxs-lookup"><span data-stu-id="ae335-334">**Location:** *07A01R2S1B*</span></span>
            - <span data-ttu-id="ae335-335">**Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ae335-335">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="ae335-336">**Quantidade:** *15*</span><span class="sxs-lookup"><span data-stu-id="ae335-336">**Quantity:** *15*</span></span>

        - <span data-ttu-id="ae335-337">**Linha 3:**</span><span class="sxs-lookup"><span data-stu-id="ae335-337">**Line 3:**</span></span>

            - <span data-ttu-id="ae335-338">**Número de item:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ae335-338">**Item number:** *A0001*</span></span>
            - <span data-ttu-id="ae335-339">**Local:** *6*</span><span class="sxs-lookup"><span data-stu-id="ae335-339">**Site:** *6*</span></span>
            - <span data-ttu-id="ae335-340">**Depósito:** *61*</span><span class="sxs-lookup"><span data-stu-id="ae335-340">**Warehouse:** *61*</span></span>
            - <span data-ttu-id="ae335-341">**Localização:** *07A01R1S1B*</span><span class="sxs-lookup"><span data-stu-id="ae335-341">**Location:** *07A01R1S1B*</span></span>
            - <span data-ttu-id="ae335-342">**Placa de licença:** selecione uma placa de licença existente na lista ou crie uma nova placa de licença.</span><span class="sxs-lookup"><span data-stu-id="ae335-342">**License plate:** Select an existing license plate in the list, or create a new license plate.</span></span>
            - <span data-ttu-id="ae335-343">**Quantidade:** *10*</span><span class="sxs-lookup"><span data-stu-id="ae335-343">**Quantity:** *10*</span></span>

    1. <span data-ttu-id="ae335-344">No Painel de Ações, selecione **Validar**.</span><span class="sxs-lookup"><span data-stu-id="ae335-344">On the Action Pane, select **Validate**.</span></span> <span data-ttu-id="ae335-345">Solucionar os erros encontrados antes de passar para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="ae335-345">Address any errors that are found before you move on to the next step.</span></span>
    1. <span data-ttu-id="ae335-346">No Painel de Ações, selecione **Lançar** para lançar o estoque no depósito.</span><span class="sxs-lookup"><span data-stu-id="ae335-346">On the Action Pane, select **Post** to post the inventory to the warehouse.</span></span>

### <a name="sample-scenario-run-zone-based-minmax-replenishment"></a><span data-ttu-id="ae335-347">Cenário de exemplo: executar reabastecimento mín./máx. baseado em zona</span><span class="sxs-lookup"><span data-stu-id="ae335-347">Sample scenario: Run zone-based min/max replenishment</span></span>

<span data-ttu-id="ae335-348">Quando todos os dados de exemplo de pré-requisito estiverem ativos, você poderá disparar o reabastecimento seguindo essas etapas.</span><span class="sxs-lookup"><span data-stu-id="ae335-348">After all the prerequisite sample data is in place, you can trigger replenishment by following these steps.</span></span>

1. <span data-ttu-id="ae335-349">Vá para **Gerenciamento de depósito \> Reabastecimento \> Reabastecimentos**.</span><span class="sxs-lookup"><span data-stu-id="ae335-349">Go to **Warehouse management \> Replenishment \> Replenishments**.</span></span>
1. <span data-ttu-id="ae335-350">Na caixa de diálogo **Reabastecimento**, na FastTab **Registros a serem incluídos**, selecione **Filtrar**.</span><span class="sxs-lookup"><span data-stu-id="ae335-350">In the **Replenishment** dialog box, on the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="ae335-351">Na caixa de diálogo **Consulta**, na guia **Intervalo**, edite a linha da tabela padrão da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ae335-351">In the **Inquiry** dialog box, on the **Range** tab, edit the default table row in the following way:</span></span>

    - <span data-ttu-id="ae335-352">**Tabela:** selecione _Modelos de reabastecimento_.</span><span class="sxs-lookup"><span data-stu-id="ae335-352">**Table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="ae335-353">**Tabela derivada:** selecione _Modelos de reabastecimento_.</span><span class="sxs-lookup"><span data-stu-id="ae335-353">**Derived table:** Select _Replenishment templates_.</span></span>
    - <span data-ttu-id="ae335-354">**Campo:** selecione _Modelo de reabastecimento_.</span><span class="sxs-lookup"><span data-stu-id="ae335-354">**Field:** Select _Replenishment template_.</span></span>
    - <span data-ttu-id="ae335-355">**Critérios:** selecione _Reabastecimento mín./máx. de zona_.</span><span class="sxs-lookup"><span data-stu-id="ae335-355">**Criteria:** Select _Zone min/max replen_.</span></span> <span data-ttu-id="ae335-356">Esse modelo de reabastecimento é o modelo de reabastecimento criado durante a preparação dos dados de demonstração para esse cenário.</span><span class="sxs-lookup"><span data-stu-id="ae335-356">This replenishment template is the replenishment template that you created while you were preparing the demo data for this scenario.</span></span>

1. <span data-ttu-id="ae335-357">Selecione **OK** para salvar a consulta e voltar à caixa de diálogo **Reabastecimento**.</span><span class="sxs-lookup"><span data-stu-id="ae335-357">Select **OK** to save the query and go back to the **Replenishment** dialog box.</span></span>
1. <span data-ttu-id="ae335-358">Selecione **OK** para executar o modelo de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="ae335-358">Select **OK** to run the replenishment template.</span></span>

<span data-ttu-id="ae335-359">O trabalho de reabastecimento agora é criado para separar o estoque da zona *MASSA* e reabastecê-lo para a zona *CHÃO*.</span><span class="sxs-lookup"><span data-stu-id="ae335-359">Replenishment work is now created to pick inventory from the *BULK* zone and replenish it to the *FLOOR* zone.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="ae335-360">Observações e dicas</span><span class="sxs-lookup"><span data-stu-id="ae335-360">Notes and tips</span></span>

<span data-ttu-id="ae335-361">Aqui estão algumas observações e dicas para trabalhar com o recurso:</span><span class="sxs-lookup"><span data-stu-id="ae335-361">Here are a few notes and tips for working with the feature:</span></span>

- <span data-ttu-id="ae335-362">Para configurar o trabalho de reabastecimento que segue para a zona desejada, você pode vincular as linhas do modelo de reabastecimento e as diretivas de localização das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="ae335-362">To set up replenishment work that goes to the desired zone, you can link the replenishment template lines and location directives in either of the following ways:</span></span>

    - <span data-ttu-id="ae335-363">Edite a consulta de cabeçalho da diretiva de localização e filtre as linhas do modelo de reabastecimento selecionado.</span><span class="sxs-lookup"><span data-stu-id="ae335-363">Edit the location directive header query, and filter the selected replenishment template lines.</span></span>
    - <span data-ttu-id="ae335-364">Use um código de diretiva na linha do modelo de reabastecimento e corresponda esse código com a diretiva de localização de colocação.</span><span class="sxs-lookup"><span data-stu-id="ae335-364">Use a directive code on the replenishment template line, and match it to the put location directive.</span></span>

- <span data-ttu-id="ae335-365">Se você estiver usando locais dinâmicos, o trabalho de reabastecimento será criado para o primeiro local disponível ou para um local que já contenha estoque, se a ação diretiva de localização estiver configurada para usar a estratégia **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="ae335-365">If you're using dynamic locations, replenishment work will be created either for the first available location or for a location that already contains inventory, if the location directive action is set up to use the **Consolidate** strategy.</span></span>
- <span data-ttu-id="ae335-366">Se você estiver usando locais fixos e não zonas, deverá usar o [reabastecimento mín./máx. padrão](tasks/set-up-min-max-replenishment-process.md).</span><span class="sxs-lookup"><span data-stu-id="ae335-366">If you're using fixed locations instead of zones, you should use [standard min/max replenishment](tasks/set-up-min-max-replenishment-process.md).</span></span>
