---
title: Requisições de Compra
description: Este tópico descreve como as requisições de compra têm suporte na Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 8075f8d7c3868c6d6012edbce17dbbb4749209ab
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992335"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="d38f2-103">Requisições de Compra</span><span class="sxs-lookup"><span data-stu-id="d38f2-103">Purchase requisitions</span></span>

<span data-ttu-id="d38f2-104">O planejamento mestre pode reabastecer requisições de compra aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d38f2-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="d38f2-105">Portanto, ao cobrir requisições de compra, os usuários não precisam usar um fluxo de trabalho para criar ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="d38f2-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="d38f2-106">Em vez disso, as requisições de compra podem ser cobertas pelo planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="d38f2-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="d38f2-107">Por causa dessa funcionalidade, uma requisição de compra pode produzir uma ordem de compra, uma ordem de transferência ou uma ordem de produção, dependendo do valor **Tipo de ordem planejada** definido para o produto relacionado.</span><span class="sxs-lookup"><span data-stu-id="d38f2-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="d38f2-108">Habilitar planos mestres para incluir requisições</span><span class="sxs-lookup"><span data-stu-id="d38f2-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="d38f2-109">Para incluir requisições durante o cálculo de cobertura de um plano mestre, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d38f2-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="d38f2-110">Vá para **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres**.</span><span class="sxs-lookup"><span data-stu-id="d38f2-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="d38f2-111">Crie ou selecione um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="d38f2-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="d38f2-112">Na FastTab **Geral**, defina a opção **Incluir requisições** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="d38f2-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="d38f2-113">Repita as etapas 2 e 3 para cada plano mestre adicional no qual você deseja incluir requisições.</span><span class="sxs-lookup"><span data-stu-id="d38f2-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="d38f2-114">Limite de tempo de requisições aprovadas</span><span class="sxs-lookup"><span data-stu-id="d38f2-114">Approved requisitions time fence</span></span>

<span data-ttu-id="d38f2-115">O *limite de tempo de requisições aprovadas* estabelece até quando (em dias) um plano mestre incluirá a demanda de requisições de reabastecimento aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d38f2-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="d38f2-116">Você pode definir um limite de tempo de requisições aprovadas no nível do grupo de cobertura e do plano mestre.</span><span class="sxs-lookup"><span data-stu-id="d38f2-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="d38f2-117">Definir o limite de tempo de requisições aprovadas para um grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="d38f2-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="d38f2-118">Vá para **Planejamento mestre** \> **Configuração** \> **Cobertura** \> **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="d38f2-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage group**.</span></span>
1. <span data-ttu-id="d38f2-119">Crie ou selecione um grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d38f2-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="d38f2-120">Na FastTab **Outro**, defina o campo **Limite de tempo de requisições aprovadas (dias)** como o número de dias a ser incluído no limite de tempo.</span><span class="sxs-lookup"><span data-stu-id="d38f2-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="d38f2-121">Repita as etapas 2 e 3 para cada grupo de cobertura adicional no qual você deseja definir um limite de tempo de requisições aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d38f2-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="d38f2-122">Definir o limite de tempo de requisições aprovadas para planos mestres individuais</span><span class="sxs-lookup"><span data-stu-id="d38f2-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="d38f2-123">Ao definir um limite de tempo de requisições aprovadas para um plano mestre individual, a configuração de limite de tempo é substituída para qualquer grupo de cobertura aplicável.</span><span class="sxs-lookup"><span data-stu-id="d38f2-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="d38f2-124">Vá para **Planejamento mestre** \> **Configuração** \> **Planos** \> **Planos mestres**.</span><span class="sxs-lookup"><span data-stu-id="d38f2-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="d38f2-125">Crie ou selecione um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="d38f2-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="d38f2-126">Na FastTab **Limites de tempo em dias**, defina o campo **Limite de tempo de requisições aprovadas (dias)** como o número de dias a ser incluído no limite de tempo.</span><span class="sxs-lookup"><span data-stu-id="d38f2-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="d38f2-127">Repita as etapas 2 e 3 para cada plano mestre adicional no qual você deseja definir um limite de tempo de requisições aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d38f2-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d38f2-128">**Em breve:** os limites de tempo de requisições aprovadas ainda não têm suporte para a Otimização de Planejamento.</span><span class="sxs-lookup"><span data-stu-id="d38f2-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="d38f2-129">Até que tenham suporte, todos os valores inseridos no campo **Limite de tempo de requisições aprovadas (dias)** serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="d38f2-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="d38f2-130">Fornecimento autônomo, independentemente do código de cobertura</span><span class="sxs-lookup"><span data-stu-id="d38f2-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="d38f2-131">As requisições de compra são sempre cobertas por ordens planejadas autônomas, independentemente do código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="d38f2-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="d38f2-132">Esse comportamento garante rastreabilidade e fluxos de trabalho claros entre requisições de compra e ordens de reabastecimento.</span><span class="sxs-lookup"><span data-stu-id="d38f2-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="d38f2-133">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d38f2-133">Example 1</span></span>

<span data-ttu-id="d38f2-134">Um produto é configurado para ter um valor **Código de cobertura** de *Mín./Máx.*. Ele tem os seguintes status de estoque e requisição:</span><span class="sxs-lookup"><span data-stu-id="d38f2-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="d38f2-135">Quantidade disponível de estoque = 10.</span><span class="sxs-lookup"><span data-stu-id="d38f2-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="d38f2-136">Quantidade mínima de estoque = 15.</span><span class="sxs-lookup"><span data-stu-id="d38f2-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="d38f2-137">Quantidade máxima de estoque = 20.</span><span class="sxs-lookup"><span data-stu-id="d38f2-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="d38f2-138">Há uma requisição de compra para uma peça.</span><span class="sxs-lookup"><span data-stu-id="d38f2-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="d38f2-139">Sua data de solicitação é hoje.</span><span class="sxs-lookup"><span data-stu-id="d38f2-139">It has a requested date of today.</span></span>

<span data-ttu-id="d38f2-140">Quando o planejamento mestre é executado, duas ordens planejadas são criadas: uma para 10 peças a fim de reabastecer o estoque até a quantidade máxima e outra para uma peça a fim de reabastecer a requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="d38f2-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="d38f2-141">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d38f2-141">Example 2</span></span>

<span data-ttu-id="d38f2-142">Um produto é configurado para ter um valor **Código de cobertura** de *Mín./Máx.*. Ele tem os seguintes status de estoque e requisição:</span><span class="sxs-lookup"><span data-stu-id="d38f2-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="d38f2-143">Quantidade disponível de estoque = 17.</span><span class="sxs-lookup"><span data-stu-id="d38f2-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="d38f2-144">Quantidade mínima de estoque = 15.</span><span class="sxs-lookup"><span data-stu-id="d38f2-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="d38f2-145">Quantidade máxima de estoque = 20.</span><span class="sxs-lookup"><span data-stu-id="d38f2-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="d38f2-146">Há uma requisição de compra para uma peça.</span><span class="sxs-lookup"><span data-stu-id="d38f2-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="d38f2-147">Sua data de solicitação é hoje.</span><span class="sxs-lookup"><span data-stu-id="d38f2-147">It has a requested date of today.</span></span>

<span data-ttu-id="d38f2-148">Quando o planejamento mestre é executado, uma ordem planejada para uma peça é criada para reabastecer a requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="d38f2-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="d38f2-149">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="d38f2-149">Example 3</span></span>

<span data-ttu-id="d38f2-150">Um produto é configurado para ter um valor **Código de cobertura** de *Período* e um período de sete dias.</span><span class="sxs-lookup"><span data-stu-id="d38f2-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="d38f2-151">Ele tem os seguintes status de estoque, ordem de venda e requisição:</span><span class="sxs-lookup"><span data-stu-id="d38f2-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="d38f2-152">Quantidade disponível de estoque = 0.</span><span class="sxs-lookup"><span data-stu-id="d38f2-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="d38f2-153">Há uma ordem de venda para cinco peças.</span><span class="sxs-lookup"><span data-stu-id="d38f2-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="d38f2-154">Sua data de remessa esperada é hoje mais um dia.</span><span class="sxs-lookup"><span data-stu-id="d38f2-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="d38f2-155">Há uma requisição de compra para três peças.</span><span class="sxs-lookup"><span data-stu-id="d38f2-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="d38f2-156">Sua data de solicitação é hoje mais três dias.</span><span class="sxs-lookup"><span data-stu-id="d38f2-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="d38f2-157">Quando o planejamento mestre é executado, duas ordens planejadas são criadas: uma para três peças a fim de reabastecer a requisição de compra e outra para cinco peças a fim de reabastecer a demanda da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="d38f2-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="d38f2-158">Depois que uma ordem planejada vinculada a uma requisição de compra é confirmada, o mecanismo de planejamento mantém a vinculação à requisição de compra.</span><span class="sxs-lookup"><span data-stu-id="d38f2-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="d38f2-159">Se, posteriormente, na ordem confirmada, estiver faltando alguma quantidade necessária para atender à requisição de compra, o sistema criará uma nova ordem planejada para a diferença.</span><span class="sxs-lookup"><span data-stu-id="d38f2-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="d38f2-160">Para obter mais informações sobre requisições de compra, consulte [Visão geral de requisições de compra](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d38f2-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>
