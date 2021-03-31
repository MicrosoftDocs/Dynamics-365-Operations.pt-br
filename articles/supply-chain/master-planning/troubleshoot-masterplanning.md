---
title: Solucionar problemas de planejamento mestre
description: Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com planejamento mestre.
author: SmithaNataraj
manager: tfehr
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: db336946873fa1b5cc3f669823541af8cab4115b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5216096"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="71f7d-103">Solucionar problemas de planejamento mestre</span><span class="sxs-lookup"><span data-stu-id="71f7d-103">Troubleshoot master planning</span></span>

<span data-ttu-id="71f7d-104">Este tópico descreve como corrigir problemas que podem ocorrer ao trabalhar com planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="71f7d-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="71f7d-105">O detalhamento da lista de materiais se comporta de maneira diferente para ordens de produção firmadas e para ordens de produção estimadas para trabalho criado manualmente.</span><span class="sxs-lookup"><span data-stu-id="71f7d-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="71f7d-106">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-106">Issue description</span></span>

<span data-ttu-id="71f7d-107">Quando uma ordem de produção é firmada, os itens não são detalhados quando você detalha a lista de materiais (BOM).</span><span class="sxs-lookup"><span data-stu-id="71f7d-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="71f7d-108">No entanto, quando você cria manualmente uma ordem de serviço e estima a ordem de produção, os itens são detalhados.</span><span class="sxs-lookup"><span data-stu-id="71f7d-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="71f7d-109">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-109">Issue resolution</span></span>

<span data-ttu-id="71f7d-110">O sistema está funcionando conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="71f7d-110">The system is working as expected.</span></span> <span data-ttu-id="71f7d-111">O detalhamento que ocorre quando a ordem de produção é firmada apontará para a ordem planejada, mas não parece que a ordem planejada está atualmente firmada neste caso.</span><span class="sxs-lookup"><span data-stu-id="71f7d-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="71f7d-112">No entanto, se a ordem de produção foi estimada, o detalhamento é acionado a partir da ordem de produção liberada, onde não existe ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="71f7d-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="71f7d-113">O valor de atraso não é atualizado quando eu reprogramo uma ordem planejado.</span><span class="sxs-lookup"><span data-stu-id="71f7d-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="71f7d-114">Para atualizar o atraso de ordens planejadas, abra a caixa de diálogo **Reprogramação** para a ordem planejada.</span><span class="sxs-lookup"><span data-stu-id="71f7d-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="71f7d-115">Na FastTab **Detalhamento**, verifique se a opção **Executar detalhamento após reprogramação** está definida como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="71f7d-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="71f7d-116">A programação da produção não considera as margens de segurança definidas na cobertura do item para fornecimento vinculado.</span><span class="sxs-lookup"><span data-stu-id="71f7d-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="71f7d-117">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-117">Issue description</span></span>

<span data-ttu-id="71f7d-118">O planejamento mestre considera as margens de segurança.</span><span class="sxs-lookup"><span data-stu-id="71f7d-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="71f7d-119">Contudo, as margens de segurança são ignoradas quando as ordens de produção planejadas são programadas.</span><span class="sxs-lookup"><span data-stu-id="71f7d-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="71f7d-120">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-120">Issue resolution</span></span>

<span data-ttu-id="71f7d-121">As margens são consideradas somente durante o planejamento mestre, não durante a programação manual.</span><span class="sxs-lookup"><span data-stu-id="71f7d-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="71f7d-122">As margens são projetadas para atuar como um buffer durante a fase de planejamento, para dar alguma "margem" para o processo real.</span><span class="sxs-lookup"><span data-stu-id="71f7d-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="71f7d-123">Para obter o resultado desejado, você pode remover a margem.</span><span class="sxs-lookup"><span data-stu-id="71f7d-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="71f7d-124">A rota deve ser atualizada para incluir o tempo desejado (por exemplo, como tempo de fila).</span><span class="sxs-lookup"><span data-stu-id="71f7d-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="71f7d-125">O planejamento mestre e a programação manual devem produzir o mesmo resultado.</span><span class="sxs-lookup"><span data-stu-id="71f7d-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="71f7d-126">As ordens planejadas são geradas mesmo que tenhamos itens em estoque e já existam ordens de produção para eles.</span><span class="sxs-lookup"><span data-stu-id="71f7d-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="71f7d-127">É possível consertar esse problema aumentando o valor de **Dias positivos** para os grupos relevantes na página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="71f7d-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="71f7d-128">Essa alteração fará com que o sistema determine se o estoque disponível pode ser usado para a demanda.</span><span class="sxs-lookup"><span data-stu-id="71f7d-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="71f7d-129">Depois, uma nova ordem planejada não será gerada para os itens que estão em estoque.</span><span class="sxs-lookup"><span data-stu-id="71f7d-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="71f7d-130">O planejamento mestre não parece respeitar as limitações de capacidade e está programando mais do que a capacidade disponível.</span><span class="sxs-lookup"><span data-stu-id="71f7d-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="71f7d-131">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-131">Issue description</span></span>

<span data-ttu-id="71f7d-132">Quando você usa a programação de operação em que há capacidade finita e a rota especifica uma combinação de requisitos para um grupo de recursos e recursos individuais, existe uma pequena chance de reserva excessiva devida à forma como o algoritmo valida os conflitos de capacidade.</span><span class="sxs-lookup"><span data-stu-id="71f7d-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="71f7d-133">Essa reserva excessiva pode ocorrer quando você usa auxiliares para executar o planejamento mestre.</span><span class="sxs-lookup"><span data-stu-id="71f7d-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="71f7d-134">É mais provável que ela ocorra se houver muitos trabalhos com um tempo de execução relativamente curto.</span><span class="sxs-lookup"><span data-stu-id="71f7d-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="71f7d-135">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-135">Issue resolution</span></span>

<span data-ttu-id="71f7d-136">Se for essencial que nenhuma reserva reserva excessiva ocorra na programação da operação, você pode tornar a parte da programação do planejamento mestre em thread único ativando a opção **Capacidade finita precisa para programação de operação** na página **Parâmetros de planejamento mestre**.</span><span class="sxs-lookup"><span data-stu-id="71f7d-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="71f7d-137">Essa opção não está disponível por padrão.</span><span class="sxs-lookup"><span data-stu-id="71f7d-137">This option isn't available by default.</span></span> <span data-ttu-id="71f7d-138">Você deve adicioná-la manualmente à página usando recursos de personalização.</span><span class="sxs-lookup"><span data-stu-id="71f7d-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="71f7d-139">Quando você usa essa opção, a programação será executada mais lentamente pela falta de processamento paralelo.</span><span class="sxs-lookup"><span data-stu-id="71f7d-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="71f7d-140">As ordens planejadas demoram muito para serem atualizadas.</span><span class="sxs-lookup"><span data-stu-id="71f7d-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="71f7d-141">Descrição do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-141">Issue description</span></span>

<span data-ttu-id="71f7d-142">Ao atualizar a quantidade necessária e/ou data de entrega em uma ordem planejada, normalmente leva pelo menos 30 segundos por ordem para salvar a atualização.</span><span class="sxs-lookup"><span data-stu-id="71f7d-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="71f7d-143">Resolução do problema</span><span class="sxs-lookup"><span data-stu-id="71f7d-143">Issue resolution</span></span>

<span data-ttu-id="71f7d-144">Esse é um problema conhecido com o mecanismo de planejamento mestre integrado.</span><span class="sxs-lookup"><span data-stu-id="71f7d-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="71f7d-145">Ele é causado pela explosão automática subjacente por meio da estrutura da BOM durante as edições.</span><span class="sxs-lookup"><span data-stu-id="71f7d-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="71f7d-146">Esse problema é abordado na Otimização de Planejamento, onde um planejador pode atualizar e aprovar os pedidos relevantes e, quando desejado, acionar uma execução de planejamento para atualizar as ordens planejadas para a estrutura de BOM subjacente.</span><span class="sxs-lookup"><span data-stu-id="71f7d-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="71f7d-147">Uma maneira de melhorar o desempenho com o mecanismo de planejamento mestre integrado é fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="71f7d-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="71f7d-148">Vá para **Planejamento mestre \> Configuração \> Planos \> Planos mestres**.</span><span class="sxs-lookup"><span data-stu-id="71f7d-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="71f7d-149">Selecione um plano.</span><span class="sxs-lookup"><span data-stu-id="71f7d-149">Select a plan.</span></span>
1. <span data-ttu-id="71f7d-150">Expanda a FastTab **Limite de tempo em dias**.</span><span class="sxs-lookup"><span data-stu-id="71f7d-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="71f7d-151">Defina **Detalhamento** como *Sim* e defina o campo abaixo dessa configuração como 0 (zero).</span><span class="sxs-lookup"><span data-stu-id="71f7d-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="71f7d-152">Isso limitará o período de detalhamentos realizados desse plano mestre a um único dia.</span><span class="sxs-lookup"><span data-stu-id="71f7d-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]