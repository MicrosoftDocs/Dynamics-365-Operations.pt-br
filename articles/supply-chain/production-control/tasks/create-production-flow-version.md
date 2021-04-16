---
title: Criar uma versão de fluxo de produção
description: Esse procedimento tem como foco a criação de uma versão de fluxo de produção.
author: cvocph
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6a4b4847046af541644338157d95e6fcba315f9c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828985"
---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="417ce-103">Criar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="417ce-103">Create a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="417ce-104">Esse procedimento tem como foco a criação de uma versão de fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="417ce-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="417ce-105">Nesse procedimento, os parâmetros de produção para lean manufacturing e as unidades de medida para tempo de classe devem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="417ce-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="417ce-106">Também pode ser necessário definir um fluxo de valor e um perfil de produção.</span><span class="sxs-lookup"><span data-stu-id="417ce-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="417ce-107">Para saber mais sobre fluxos e atividades de produção em lean manufacturing, consulte os white papers a respeito de Lean manufacturing para Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="417ce-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="417ce-108">A empresa de dados demo usada para criar este procedimento é USMF.</span><span class="sxs-lookup"><span data-stu-id="417ce-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="417ce-109">Criar um fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="417ce-109">Create a production flow</span></span>
1. <span data-ttu-id="417ce-110">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="417ce-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="417ce-111">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="417ce-111">Click New.</span></span>
3. <span data-ttu-id="417ce-112">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="417ce-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="417ce-113">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="417ce-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="417ce-114">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="417ce-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="417ce-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="417ce-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="417ce-116">Selecione uma unidade operacional de fluxo de valor de tipo.</span><span class="sxs-lookup"><span data-stu-id="417ce-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="417ce-117">O fluxo de valor é uma unidade operacional que abrange todos os fluxos e atividades do fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="417ce-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="417ce-118">Nessa fase, as unidades operacionais se limitam a uma entidade legal e não apresentam funcionalidade adicional.</span><span class="sxs-lookup"><span data-stu-id="417ce-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="417ce-119">No campo Perfil de produção, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="417ce-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="417ce-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="417ce-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="417ce-121">Selecione um perfil de produção para o fluxo de produção.</span><span class="sxs-lookup"><span data-stu-id="417ce-121">Select a production group for the production flow.</span></span> <span data-ttu-id="417ce-122">Perfis de produção permitem a definição de material, trabalho e contas WIP para um processo de produção.</span><span class="sxs-lookup"><span data-stu-id="417ce-122">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="417ce-123">Para associar o contexto de contabilidade a um fluxo de produção, um perfil de produção deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="417ce-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="417ce-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="417ce-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="417ce-125">Criar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="417ce-125">Create a production flow version</span></span>
1. <span data-ttu-id="417ce-126">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="417ce-126">Click Add.</span></span>
2. <span data-ttu-id="417ce-127">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="417ce-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="417ce-128">Se necessário, defina uma data de vencimento para a versão.</span><span class="sxs-lookup"><span data-stu-id="417ce-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="417ce-129">É possível atualizá-la a qualquer momento, mesmo para versões ativas.</span><span class="sxs-lookup"><span data-stu-id="417ce-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="417ce-130">É possível usá-la para planejar a retirada gradual de uma versão.</span><span class="sxs-lookup"><span data-stu-id="417ce-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="417ce-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="417ce-131">Click OK.</span></span>
4. <span data-ttu-id="417ce-132">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="417ce-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="417ce-133">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="417ce-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="417ce-134">Resolver altera a unidade Takt.</span><span class="sxs-lookup"><span data-stu-id="417ce-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="417ce-135">No campo Takt time médio, insira um número.</span><span class="sxs-lookup"><span data-stu-id="417ce-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="417ce-136">Defina o takt time médio da versão.</span><span class="sxs-lookup"><span data-stu-id="417ce-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="417ce-137">Para o controle de takt da versão do fluxo de produção, defina um takt time médio de destino.</span><span class="sxs-lookup"><span data-stu-id="417ce-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="417ce-138">O takt é definido como quantidade por período de tempo.</span><span class="sxs-lookup"><span data-stu-id="417ce-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="417ce-139">No exemplo, o takt time é 0,2 horas por 10 unidades.</span><span class="sxs-lookup"><span data-stu-id="417ce-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="417ce-140">Para um tempo de trabalho de 8 horas, isso corresponde a uma capacidade de produtividade diária de 400 unidades.</span><span class="sxs-lookup"><span data-stu-id="417ce-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="417ce-141">No campo Quantidade por ciclo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="417ce-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="417ce-142">Defina a quantidade por ciclo relacionada ao takt time médio.</span><span class="sxs-lookup"><span data-stu-id="417ce-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="417ce-143">Alterne a expansão da seção Detalhes da versão.</span><span class="sxs-lookup"><span data-stu-id="417ce-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="417ce-144">No campo Takt time mínimo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="417ce-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="417ce-145">Defina o takt time mínimo.</span><span class="sxs-lookup"><span data-stu-id="417ce-145">Define the minimum takt time.</span></span> <span data-ttu-id="417ce-146">O takt time mínimo deve ser menor que ou igual ao takt time médio.</span><span class="sxs-lookup"><span data-stu-id="417ce-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="417ce-147">No campo Takt time máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="417ce-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="417ce-148">O takt time máximo deve ser maior que ou igual ao takt time médio.</span><span class="sxs-lookup"><span data-stu-id="417ce-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="417ce-149">No campo Período para tempo de ciclo real (dias), insira um número.</span><span class="sxs-lookup"><span data-stu-id="417ce-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="417ce-150">Insira o número de dias no Período para tempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="417ce-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="417ce-151">O período para tempo de ciclo real é o número de dias em que os trabalhos são agregados do minuto real regressivamente para calcular o tempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="417ce-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="417ce-152">O valor pode ser alterado a qualquer momento e só é usado para o cálculo dos tempos de ciclo reais.</span><span class="sxs-lookup"><span data-stu-id="417ce-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="417ce-153">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="417ce-153">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]