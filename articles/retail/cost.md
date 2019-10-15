---
title: Configuração de custo para gerenciamento de ordem distribuído (GOD)
description: Este tópico descreve a funcionalidade de configuração de custo para o gerenciamento de ordem distribuído (GOD) do Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b5e3e1997f3d3b61b7b3c7486f5531e386293537
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2019
ms.locfileid: "2019430"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="f08c1-103">Configuração de custo para gerenciamento de ordem distribuído (GOD)</span><span class="sxs-lookup"><span data-stu-id="f08c1-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f08c1-104">As organizações consideram vários componentes de custo para determinar o local ideal do qual atender uma ordem.</span><span class="sxs-lookup"><span data-stu-id="f08c1-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="f08c1-105">Alguns desses componentes de custo são os custos de remessa, os custos de manutenção e os custos de embalagem.</span><span class="sxs-lookup"><span data-stu-id="f08c1-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="f08c1-106">Uma combinação desses custos é calculada para determinar o local de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="f08c1-107">Quando a primeira iteração do gerenciamento de ordem distribuído (GOD) no Dynamics 365 Retail otimizou a atribuição de ordens para os locais de atendimento, somente a distância foi fatorada.</span><span class="sxs-lookup"><span data-stu-id="f08c1-107">When the first iteration of distributed order management (DOM) in Dynamics 365 Retail optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="f08c1-108">Embora a distância possa ser correlacionada com o custo, não é o mesmo que o custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="f08c1-109">Por exemplo, um método de remessa de entrega em 24 horas custa mais que a remessa em três ou sete três dias para a mesma distância.</span><span class="sxs-lookup"><span data-stu-id="f08c1-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="f08c1-110">O recurso de configuração de custo permite que os varejistas definam e configurem componentes de custo adicionais de que serão calculados e fatorados para determinar o local ideal para atender linhas da ordem.</span><span class="sxs-lookup"><span data-stu-id="f08c1-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="f08c1-111">Quando os componentes de custo são configurados, o agente de resolução do GOD usa somente essas definições de custo para determinar o local ideal para o atendimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="f08c1-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="f08c1-112">Ele não considera o componente de distância como custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="f08c1-113">No entanto, se nenhum componente de custo for configurado, o agente de resolução do GOD usará o componente de distância como um custo para determinar o local ideal para o atendimento da ordem.</span><span class="sxs-lookup"><span data-stu-id="f08c1-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="f08c1-114">Configurar componentes de custo</span><span class="sxs-lookup"><span data-stu-id="f08c1-114">Set up cost components</span></span>

<span data-ttu-id="f08c1-115">Dois tipos principais de componentes de custo podem ser definidos no sistema: **Remessa** e **Outro**.</span><span class="sxs-lookup"><span data-stu-id="f08c1-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="f08c1-116">Ambos os tipos de componente de custo oferecem suporte a várias bases de cálculo, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="f08c1-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="f08c1-117">Tipo de componente de custo</span><span class="sxs-lookup"><span data-stu-id="f08c1-117">Cost component type</span></span></th>
<th><span data-ttu-id="f08c1-118">Base de cálculo</span><span class="sxs-lookup"><span data-stu-id="f08c1-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="f08c1-119">Remessa</span><span class="sxs-lookup"><span data-stu-id="f08c1-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="f08c1-120">Simples</span><span class="sxs-lookup"><span data-stu-id="f08c1-120">Simple</span></span></li>
<li><span data-ttu-id="f08c1-121">Em Camadas</span><span class="sxs-lookup"><span data-stu-id="f08c1-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="f08c1-122">Outro</span><span class="sxs-lookup"><span data-stu-id="f08c1-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="f08c1-123">Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f08c1-123">Sales order</span></span></li>
<li><span data-ttu-id="f08c1-124">Linha de venda</span><span class="sxs-lookup"><span data-stu-id="f08c1-124">Sales line</span></span></li>
<li><span data-ttu-id="f08c1-125">Local</span><span class="sxs-lookup"><span data-stu-id="f08c1-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="f08c1-126">Tipo de componente de custo de remessa</span><span class="sxs-lookup"><span data-stu-id="f08c1-126">Shipping cost component type</span></span>

<span data-ttu-id="f08c1-127">Esta seção explica como configurar cada combinação do tipo de componente de custo **Remessa** e uma base de cálculo para os custos de remessa.</span><span class="sxs-lookup"><span data-stu-id="f08c1-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="f08c1-128">Ele também explica como o agente de resolução do GOD usa cada combinação.</span><span class="sxs-lookup"><span data-stu-id="f08c1-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="f08c1-129">Tipo de componente de custo = Remessa e Base de cálculo = Simples</span><span class="sxs-lookup"><span data-stu-id="f08c1-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="f08c1-130">Se uma combinação do tipo de componente de custo **Remessa** e a base de cálculo **Simples** for usada, os custos de remessa para um modo de entrega serão baseados em um custo ou uma distância simples.</span><span class="sxs-lookup"><span data-stu-id="f08c1-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="f08c1-131">Você deve configurar os seguintes campos para essa combinação:</span><span class="sxs-lookup"><span data-stu-id="f08c1-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="f08c1-132">**Fator de custo** — insira um identificador exclusivo para o fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="f08c1-133">**Descrição** — insira o nome e a descrição do fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="f08c1-134">**Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="f08c1-135">Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="f08c1-136">**Ativo** — indicar se o fator de custo está ativo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="f08c1-137">O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="f08c1-138">**Empresa** — especifique a entidade legal para a qual o fator de custo está configurado.</span><span class="sxs-lookup"><span data-stu-id="f08c1-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="f08c1-139">Todas as linhas dos critérios de cálculo devem estar para a mesma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="f08c1-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="f08c1-140">**Modos de entrega** — especifique os modos de entrega para os quais o custo está configurado.</span><span class="sxs-lookup"><span data-stu-id="f08c1-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="f08c1-141">**Tipo de cálculo** — especifique como o custo deve ser calculado para um modo de entrega específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="f08c1-142">Há suporte para dois tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="f08c1-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="f08c1-143">**Fixo** — um custo simples é usado para o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="f08c1-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="f08c1-144">Se você selecionar este tipo de cálculo, o campo **Custo** definirá o custo simples.</span><span class="sxs-lookup"><span data-stu-id="f08c1-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="f08c1-145">**Por unidade de distância** — os custos para o modo de entrega serão calculados como o valor de custo que é especificado no campo **Custo** vezes a distância entre o endereço de entrega e os locais.</span><span class="sxs-lookup"><span data-stu-id="f08c1-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="f08c1-146">**Custo** — especifique o valor do custo que é usado em conjunto com o campo **Tipo de cálculo** para calcular o custo para um modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="f08c1-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="f08c1-147">Tipo de componente de custo = Remessa e Base de cálculo = Em camadas</span><span class="sxs-lookup"><span data-stu-id="f08c1-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="f08c1-148">Se uma combinação do tipo de componente de custo **Remessa** e a base de cálculo **Em camadas** for usada, os custos de remessa para um modo de entrega serão baseados no custo ou na distância.</span><span class="sxs-lookup"><span data-stu-id="f08c1-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="f08c1-149">No entanto, nessa combinação, a distância é baseada em um intervalo em camadas de distâncias.</span><span class="sxs-lookup"><span data-stu-id="f08c1-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="f08c1-150">Você deve configurar os seguintes campos para essa combinação:</span><span class="sxs-lookup"><span data-stu-id="f08c1-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="f08c1-151">**Fator de custo** — insira um identificador exclusivo para o fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="f08c1-152">**Descrição** — insira o nome e a descrição do fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="f08c1-153">**Custo padrão**— especifique o custo que deve ser usado para um modo de entrega se a distância entre o endereço de entrega e o local não estiver em nenhuma das distâncias em camadas para o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="f08c1-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="f08c1-154">**Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="f08c1-155">Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="f08c1-156">**Ativo** — indicar se o fator de custo está ativo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="f08c1-157">O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="f08c1-158">**Empresa** — especifique a entidade legal para a qual o fator de custo está configurado.</span><span class="sxs-lookup"><span data-stu-id="f08c1-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="f08c1-159">Todas as linhas dos critérios de cálculo devem estar para a mesma entidade legal.</span><span class="sxs-lookup"><span data-stu-id="f08c1-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="f08c1-160">**Modos de entrega** — especifique os modos de entrega para os quais o custo está configurado.</span><span class="sxs-lookup"><span data-stu-id="f08c1-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="f08c1-161">**Tipo de distância** — especifique se a definição de distância em camadas é uma distância aérea ou uma distância rodoviária.</span><span class="sxs-lookup"><span data-stu-id="f08c1-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="f08c1-162">**Unidades de distância** — especifique a unidade na qual a distância em camadas é medida.</span><span class="sxs-lookup"><span data-stu-id="f08c1-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="f08c1-163">**Distância de** — especifique o intervalo de início da distância em camadas.</span><span class="sxs-lookup"><span data-stu-id="f08c1-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="f08c1-164">**Distância para** — especifique o intervalo de término da distância em camadas.</span><span class="sxs-lookup"><span data-stu-id="f08c1-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="f08c1-165">**Tipo de cálculo** — especifique como o custo deve ser calculado para um modo de entrega específico e a distância em camadas.</span><span class="sxs-lookup"><span data-stu-id="f08c1-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="f08c1-166">Há suporte para dois tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="f08c1-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="f08c1-167">**Fixo** — um custo simples é usado para o modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="f08c1-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="f08c1-168">Se você selecionar este tipo de cálculo, o campo **Custo** definirá o custo simples.</span><span class="sxs-lookup"><span data-stu-id="f08c1-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="f08c1-169">**Por unidade de distância** — o custo para o modo de entrega e a distância em camadas será calculados como o valor de custo que é especificado no campo **Custo** vezes a distância entre o endereço de entrega e os locais.</span><span class="sxs-lookup"><span data-stu-id="f08c1-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="f08c1-170">**Custo** — especifique o valor do custo que é usado em conjunto com o campo **Tipo de cálculo** para calcular o custo para um modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="f08c1-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="f08c1-171">Quando você define distâncias em camadas, o sistema valida se não há distâncias ausentes ou sobrepostas.</span><span class="sxs-lookup"><span data-stu-id="f08c1-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="f08c1-172">O tipo de distância usado para um modo de entrega deve ser igual em todas as distâncias em camadas.</span><span class="sxs-lookup"><span data-stu-id="f08c1-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="f08c1-173">Tipo de componente de custo Outro</span><span class="sxs-lookup"><span data-stu-id="f08c1-173">Other cost component type</span></span>

<span data-ttu-id="f08c1-174">Esta seção explica como configurar cada combinação do tipo de componente de custo **Outro** e outro tipo de custo para custos que não sejam de remessa.</span><span class="sxs-lookup"><span data-stu-id="f08c1-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="f08c1-175">Ele também explica como o agente de resolução do GOD usa cada combinação.</span><span class="sxs-lookup"><span data-stu-id="f08c1-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="f08c1-176">Tipo de componente de custo = Outro e Outro tipo de custo = Ordem de venda</span><span class="sxs-lookup"><span data-stu-id="f08c1-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="f08c1-177">Uma combinação de tipo de componente de custo **Outro** e o outro tipo de custo **Ordem de venda** é usada para definir custos que não sejam de remessa no nível da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f08c1-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="f08c1-178">Você deve configurar os seguintes campos para essa combinação:</span><span class="sxs-lookup"><span data-stu-id="f08c1-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="f08c1-179">**Fator de custo** — insira um identificador exclusivo para o fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="f08c1-180">**Descrição** — insira o nome e a descrição do fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="f08c1-181">**Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="f08c1-182">Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="f08c1-183">**Ativo** — indicar se o fator de custo está ativo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="f08c1-184">O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="f08c1-185">**Custo** — especifique o valor de custo para um custo que não seja de remessa no nível da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f08c1-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="f08c1-186">Tipo de componente de custo = Outro e Outro tipo de custo = Linha de venda</span><span class="sxs-lookup"><span data-stu-id="f08c1-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="f08c1-187">Uma combinação de tipo de componente de custo **Outro** e o outro tipo de custo **Linha de venda** é usada para definir custos que não sejam de remessa no nível da linha ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f08c1-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="f08c1-188">Você deve configurar os seguintes campos para essa combinação:</span><span class="sxs-lookup"><span data-stu-id="f08c1-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="f08c1-189">**Fator de custo** — insira um identificador exclusivo para o fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="f08c1-190">**Descrição** — insira o nome e a descrição do fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="f08c1-191">**Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="f08c1-192">Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="f08c1-193">**Ativo** — indicar se o fator de custo está ativo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="f08c1-194">O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="f08c1-195">**Custo** — especifique o valor do custo para um custo que não seja de remessa no nível da linha da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="f08c1-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="f08c1-196">Tipo de componente de custo = Outro e Outro tipo de custo = Local</span><span class="sxs-lookup"><span data-stu-id="f08c1-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="f08c1-197">Uma combinação de tipo componente de custo **Outro** e o outro tipo de custo **Local** é usada para definir custos que não sejam de remessa para um grupo de locais ou de um local individual.</span><span class="sxs-lookup"><span data-stu-id="f08c1-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="f08c1-198">Você deve configurar os seguintes campos para essa combinação:</span><span class="sxs-lookup"><span data-stu-id="f08c1-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="f08c1-199">**Fator de custo** — insira um identificador exclusivo para o fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="f08c1-200">**Descrição** — insira o nome e a descrição do fator de custo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="f08c1-201">**Data inicial** e **Data final** — você pode usar esses campos para limitar o fator de custo para um intervalo de datas específico.</span><span class="sxs-lookup"><span data-stu-id="f08c1-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="f08c1-202">Se você deixar esses campos em branco, o fator de custo será válido por um período indefinido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="f08c1-203">**Ativo** — indicar se o fator de custo está ativo.</span><span class="sxs-lookup"><span data-stu-id="f08c1-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="f08c1-204">O GOD considera somente os fatores de custo ativos associados com o perfil de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="f08c1-205">**Grupo de atendimento** — especifique o grupo de locais para o qual o custo que não seja de remessa está definido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="f08c1-206">**Local de atendimento** — especifique o local para o qual o custo que não seja de remessa está definido.</span><span class="sxs-lookup"><span data-stu-id="f08c1-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f08c1-207">Não é possível especificar um grupo de atendimento e um local de atendimento na mesma linha de critérios de base de cálculo do local.</span><span class="sxs-lookup"><span data-stu-id="f08c1-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="f08c1-208">**Custo** — especifique o valor do custo para um custo que não seja de remessa no nível do grupo de atendimento ou no nível do local de atendimento.</span><span class="sxs-lookup"><span data-stu-id="f08c1-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f08c1-209">Para que o GOD considere esses custos quando for executado, você deverá adicionar o fator de custo ao perfil de atendimento relevante.</span><span class="sxs-lookup"><span data-stu-id="f08c1-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>
