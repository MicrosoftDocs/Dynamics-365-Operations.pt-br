---
title: Planejamento de produção
description: Este tópico descreve o planejamento de produção e explica como modificar as ordens de produção planejadas usando a Otimização de Planejamento.
author: ChristianRytt
manager: tfehr
ms.date: 12/15/2020
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
ms.search.validFrom: 2020-12-15
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: eda22aa6f1e8d665d8ef390f24b247a76d4c2956
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992386"
---
# <a name="production-planning"></a><span data-ttu-id="d7ae1-103">Planejamento de produção</span><span class="sxs-lookup"><span data-stu-id="d7ae1-103">Production planning</span></span>

<span data-ttu-id="d7ae1-104">A Otimização de Planejamento oferece suporte a vários cenários de produção.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-104">Planning Optimizations supports several production scenarios.</span></span> <span data-ttu-id="d7ae1-105">Se você estiver migrando do mecanismo de planejamento mestre interno existente, é importante estar ciente de alguns comportamentos alterados.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-105">If you're migrating from the existing, built-in master planning engine, it's important that you be aware of some changed behavior.</span></span>

<!-- The following video gives a short introduction to some of the current capabilities. 
KFM: Link to video for production functionality, coming soon... -->

## <a name="planned-production-orders"></a><span data-ttu-id="d7ae1-106">Ordens de Produção Planejadas</span><span class="sxs-lookup"><span data-stu-id="d7ae1-106">Planned production orders</span></span>

<span data-ttu-id="d7ae1-107">Quando o planejamento mestre cria ordens planejadas para atender a requisições, o tipo de ordem é determinado pelo valor do campo **Tipo de ordem planejada**.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-107">When master planning creates planned orders to fulfill requirements, the order type is determined by the value of the **Planned order type** field.</span></span> <span data-ttu-id="d7ae1-108">Se o campo **Tipo de ordem planejada** estiver definido como *Produção*, ordens de produção planejadas serão criadas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-108">If the **Planned order type** field is set to *Production*, planned production orders are created.</span></span> <span data-ttu-id="d7ae1-109">Essas ordens de produção planejadas incluem informações sobre a lista de materiais (BOM) ativa e a ID de roteiro da configuração de produção relacionada.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-109">These planned production orders include information about the active bill of materials (BOM) and the route ID from the related production setup.</span></span>

## <a name="requirements-from-boms"></a><span data-ttu-id="d7ae1-110">Requisições de BOMs</span><span class="sxs-lookup"><span data-stu-id="d7ae1-110">Requirements from BOMs</span></span>

<span data-ttu-id="d7ae1-111">As informações da BOM são respeitadas durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-111">BOM information is honored during master planning.</span></span> <span data-ttu-id="d7ae1-112">A saída do plano inclui o fornecimento de materiais para cobrir a demanda de materiais relacionada para produção.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-112">The plan output includes material supply to cover related material demand for production.</span></span>

<span data-ttu-id="d7ae1-113">Durante o planejamento mestre, a BOM ativa atual é usada para determinar os materiais necessários para a produção.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-113">During master planning, the current, active BOM is used to determine the materials that are required for production.</span></span> <span data-ttu-id="d7ae1-114">Essa etapa é realizada em todos os níveis da estrutura da BOM que está relacionada à ordem de produção necessária.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-114">This step is done through all levels of the BOM structure that is related to the required production order.</span></span> <span data-ttu-id="d7ae1-115">A requisição de materiais é atendida usando estoque disponível, fornecimento sob encomenda existente e ordens planejadas aprovadas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-115">Material requirement is fulfilled by using available on-hand inventory, existing on-order supply, and approved planned orders.</span></span> <span data-ttu-id="d7ae1-116">Se materiais adicionais forem necessários em qualquer lugar, uma ordem planejada será criada para cobrir a demanda.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-116">If additional material is required anywhere, a planned order is created to cover the demand.</span></span>

## <a name="scheduling-during-firming"></a><span data-ttu-id="d7ae1-117">Agendamento durante a confirmação</span><span class="sxs-lookup"><span data-stu-id="d7ae1-117">Scheduling during firming</span></span>

<span data-ttu-id="d7ae1-118">As ordens de produção planejadas incluem a ID de roteiro necessária para o agendamento de produção.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-118">Planned production orders include the route ID that is required for production scheduling.</span></span> <span data-ttu-id="d7ae1-119">No entanto, o suporte ao agendamento durante a execução de planejamento de ordens planejadas está pendente.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-119">However, scheduling support during the planning run for planned orders is pending.</span></span> <span data-ttu-id="d7ae1-120">A ID de roteiro é usada para agendar ordens de produção planejadas durante a confirmação.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-120">The route ID is used to schedule planned production orders during firming.</span></span> <span data-ttu-id="d7ae1-121">Portanto, o prazo de entrega das ordens de produção planejadas pode ser diferente do prazo de entrega das ordens de produção agendadas e confirmadas relacionadas, que são geradas a partir delas, conforme descrito aqui:</span><span class="sxs-lookup"><span data-stu-id="d7ae1-121">Therefore, the lead time on planned production orders can differ from the lead time on related scheduled, firmed production orders that are generated from them, as described here:</span></span>

- <span data-ttu-id="d7ae1-122">**Ordem de produção planejada** – o prazo de entrega baseia-se no prazo de entrega estático do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-122">**Planned production order** – The lead time is based on the static lead time from the released product.</span></span>
- <span data-ttu-id="d7ae1-123">**Ordem de produção confirmada** – o prazo de entrega baseia-se no agendamento que usa informações de roteiro e restrições de recursos relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-123">**Firmed production order** – The lead time is based on scheduling that uses route information and related resource constraints.</span></span>

<span data-ttu-id="d7ae1-124">Para obter mais informações sobre a disponibilidade esperada de recursos, consulte [Análise de ajuste da Otimização de Planejamento](planning-optimization-fit-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="d7ae1-124">For more information about expected feature availability, see [Planning Optimization fit analysis](planning-optimization-fit-analysis.md).</span></span>

<span data-ttu-id="d7ae1-125">Se você depender de uma funcionalidade de produção que ainda não está disponível para a Otimização de Planejamento, poderá continuar usando o mecanismo de planejamento mestre interno.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-125">If you depend on production functionality that isn't yet available for Planning Optimization, you can continue to use the built-in master planning engine.</span></span> <span data-ttu-id="d7ae1-126">Nenhuma exceção é necessária.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-126">No exception is required.</span></span>

## <a name="delays"></a><span data-ttu-id="d7ae1-127">Atrasos</span><span class="sxs-lookup"><span data-stu-id="d7ae1-127">Delays</span></span>

<span data-ttu-id="d7ae1-128">Se o prazo de entrega dos materiais requisitados for maior do que o período entre a data de hoje e a data de requisição dos materiais, a ordem planejada dos materiais requisitados e a ordem de produção relacionada serão atrasadas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-128">If the lead time for required material is longer than the period between today's date and the material requirement date, the planned order for the required material and the related production order will be delayed.</span></span> <span data-ttu-id="d7ae1-129">Para ordens planejadas, o atraso (em dias) é calculado com base no prazo de entrega do produto liberado.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-129">For planned orders, the delay (in days) is calculated based on the lead time from the released product.</span></span> <span data-ttu-id="d7ae1-130">Em seguida, as informações sobre o atraso são propagadas por todos os níveis da estrutura da BOM.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-130">The delay information is then propagated through all levels of the BOM structure.</span></span> <span data-ttu-id="d7ae1-131">Portanto, você pode seguir o impacto de uma matéria-prima atrasada até a ordem de venda do cliente.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-131">Therefore, you can follow the impact of delayed raw material all the way to the customer sales order.</span></span>

## <a name="modifying-planned-orders"></a><span data-ttu-id="d7ae1-132">Modificar ordens planejadas</span><span class="sxs-lookup"><span data-stu-id="d7ae1-132">Modifying planned orders</span></span>

<span data-ttu-id="d7ae1-133">Ao alterar as informações em uma ordem planejada, você receberá a seguinte mensagem: "Observe que o impacto das alterações manuais feitas nas ordens planejadas não será refletido no restante do plano até a próxima execução do planejamento mestre."</span><span class="sxs-lookup"><span data-stu-id="d7ae1-133">When you change information on a planned order, you receive the following message: "Note that the impact of manual changes on planned orders won't be reflected in the rest of the plan until the next master planning run."</span></span>

<span data-ttu-id="d7ae1-134">Se você quiser alterar as informações em uma ordem planejada e ver o impacto sobre as requisições de materiais relacionadas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-134">If you want to change information on a planned order and see the impact on the related material requirements, follow these steps.</span></span>

1. <span data-ttu-id="d7ae1-135">Atualize a ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-135">Update the planned order.</span></span>
2. <span data-ttu-id="d7ae1-136">Aprove a ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-136">Approve the planned order.</span></span>
3. <span data-ttu-id="d7ae1-137">Execute o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-137">Run master planning.</span></span>

<span data-ttu-id="d7ae1-138">Ao executar o planejamento mestre, você não deverá usar filtros se ordens de produção planejadas forem incluídas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-138">When you run master planning, you should not use filters if planned production orders are included.</span></span> <span data-ttu-id="d7ae1-139">Para obter mais informações, consulte a seção [Filtros](#filters) posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-139">For more information, see the [Filters](#filters) section later in this topic.</span></span>

> [!NOTE]
> <span data-ttu-id="d7ae1-140">Se a data de entrega da ordem planejada for alterada para uma data posterior, a demanda poderá ser vinculada a uma nova ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-140">If the delivery date of the planned order is changed to a later date, the demand might be pegged against a new planned order.</span></span> <span data-ttu-id="d7ae1-141">Esse comportamento ocorre quando a nova data de fornecimento causa um atraso para a demanda vinculada, mas, de acordo com as configurações de prazo de entrega, o atraso pode ser evitado.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-141">This behavior occurs when the new supply date causes a delay for the pegged demand but, according to the lead time settings, the delay can be avoided.</span></span>

## <a name="explosion-page"></a><span data-ttu-id="d7ae1-142">Página Detalhamento</span><span class="sxs-lookup"><span data-stu-id="d7ae1-142">Explosion page</span></span>

<span data-ttu-id="d7ae1-143">Você pode usar a página **Detalhamento** para analisar a demanda necessária para uma ordem de produção específica ou ordem de produção planejada, a cobertura relacionada e as informações de vinculação.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-143">You can use the **Explosion** page to analyze the demand that is required for a specific production order or planned production order, the related coverage, and pegging information.</span></span> <span data-ttu-id="d7ae1-144">As informações na página **Detalhamento** são atualizadas durante o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-144">Information on the **Explosion** page is updated during master planning.</span></span> <span data-ttu-id="d7ae1-145">Não é possível atualizar as informações diretamente na página **Detalhamento**.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-145">You can't update the information directly from the **Explosion** page.</span></span>

## <a name="filters"></a><a name="filters"></a><span data-ttu-id="d7ae1-146">Filtros</span><span class="sxs-lookup"><span data-stu-id="d7ae1-146">Filters</span></span>

<span data-ttu-id="d7ae1-147">Para cenários de planejamento que incluem produção, recomendamos evitar execuções de planejamento mestre filtrado.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-147">For planning scenarios that include production, we recommend that you avoid filtered master planning runs.</span></span> <span data-ttu-id="d7ae1-148">Para garantir que a Otimização de Planejamento tenha as informações necessárias para calcular o resultado correto, você deve incluir todos os produtos que tenham qualquer relação com produtos em toda a estrutura da BOM da ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-148">To ensure that Planning Optimization has the information that is required to calculate the correct result, you must include all products that have any relation to products in the whole BOM structure of the planned order.</span></span>

<span data-ttu-id="d7ae1-149">Embora itens filho dependentes sejam automaticamente detectados e incluídos nas execuções do planejamento mestre, quando o mecanismo de planejamento mestre interno é usado, a Otimização de Planejamento não executa essa ação.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-149">Although dependent child items are automatically detected and included in master planning runs when the built-in master planning engine is used, Planning Optimization doesn't perform this action.</span></span>

<span data-ttu-id="d7ae1-150">Por exemplo, se um único parafuso da estrutura da BOM do produto A também for usado para produzir o produto B, todos os produtos na estrutura da BOM dos produtos A e B deverão ser incluídos no filtro.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-150">For example, if a single bolt from the BOM structure of product A is also used to produce product B, all products in the BOM structure of products A and B must be included in the filter.</span></span> <span data-ttu-id="d7ae1-151">Como pode ser muito complexo garantir que todos os produtos façam parte do filtro, recomendamos evitar execuções de planejamento mestre filtrado quando ordens de produção estiverem envolvidas.</span><span class="sxs-lookup"><span data-stu-id="d7ae1-151">Because it can be very complex to ensure that all products are part of the filter, we recommend that you avoid filtered master planning runs when production orders are involved.</span></span>
