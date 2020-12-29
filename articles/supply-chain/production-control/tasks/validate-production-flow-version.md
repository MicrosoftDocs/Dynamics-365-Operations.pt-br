---
title: Validar um fluxo de produção e versão
description: Este procedimento mostra como criar um fluxo de produção e uma primeira versão para lean manufacturing.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c30947d01cfb85ea3dbf1aa3e4ea8e092efd18cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422282"
---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="b5590-103">Validar um fluxo de produção e versão</span><span class="sxs-lookup"><span data-stu-id="b5590-103">Validate a production flow and version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b5590-104">Este procedimento mostra como criar um fluxo de produção e uma primeira versão para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="b5590-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="b5590-105">Pré-requisitos: nesse procedimento, os parâmetros de produção para lean manufacturing e as unidades de medida para tempo de classe devem ser definidos.</span><span class="sxs-lookup"><span data-stu-id="b5590-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="b5590-106">Você também pode definir um fluxo de valor e um perfil de produção.</span><span class="sxs-lookup"><span data-stu-id="b5590-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="b5590-107">Consulte os white papers sobre Lean manufacturing para se familiarizar com os conceitos de atividades e fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="b5590-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="b5590-108">Este procedimento refere-se à entidade legal USMF nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="b5590-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="b5590-109">No entanto, ao assumir que a entidade legal está configurada para lean manufacturing, outras entidades legais podem ser usadas.</span><span class="sxs-lookup"><span data-stu-id="b5590-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="b5590-110">Criar um fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="b5590-110">Create a production flow</span></span>
1. <span data-ttu-id="b5590-111">Vá para Controle de produção > Configuração > Fluxo de produção de lean manufacturing > Fluxos de produção.</span><span class="sxs-lookup"><span data-stu-id="b5590-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="b5590-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="b5590-112">Click New.</span></span>
3. <span data-ttu-id="b5590-113">No campo Nome, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b5590-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="b5590-114">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b5590-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="b5590-115">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b5590-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b5590-116">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b5590-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b5590-117">O fluxo de valor é uma unidade operacional que abrange todos os fluxos e atividades do fluxo de valor.</span><span class="sxs-lookup"><span data-stu-id="b5590-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="b5590-118">Nessa fase, as unidades operacionais se limitam a uma entidade legal e não apresentam funcionalidade adicional.</span><span class="sxs-lookup"><span data-stu-id="b5590-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="b5590-119">No campo Perfil de produção, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="b5590-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="b5590-120">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b5590-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="b5590-121">Perfis de produção permitem a definição de material, trabalho e contas WIP para um processo de produção.</span><span class="sxs-lookup"><span data-stu-id="b5590-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="b5590-122">Para associar o contexto de contabilidade a um fluxo de produção, um perfil de produção deve ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="b5590-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="b5590-123">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b5590-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="b5590-124">Criar uma versão de fluxo de produção</span><span class="sxs-lookup"><span data-stu-id="b5590-124">Create a production flow version</span></span>
1. <span data-ttu-id="b5590-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="b5590-125">Click Add.</span></span>
2. <span data-ttu-id="b5590-126">No campo Data de vencimento, insira uma data e hora.</span><span class="sxs-lookup"><span data-stu-id="b5590-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="b5590-127">Você pode atualizar a data de vencimento da versão a qualquer momento, mesmo a de versões ativas.</span><span class="sxs-lookup"><span data-stu-id="b5590-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="b5590-128">Use o vencimento da versão para planejar a retirada gradual de uma versão.</span><span class="sxs-lookup"><span data-stu-id="b5590-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="b5590-129">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="b5590-129">Click OK.</span></span>
4. <span data-ttu-id="b5590-130">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="b5590-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="b5590-131">No campo Unidade, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="b5590-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="b5590-132">Selecione a unidade Takt.</span><span class="sxs-lookup"><span data-stu-id="b5590-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="b5590-133">No campo Takt time médio, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b5590-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5590-134">Para o controle de takt da versão do fluxo de produção, defina um takt time médio de destino.</span><span class="sxs-lookup"><span data-stu-id="b5590-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="b5590-135">O takt é definido como quantidade por período de tempo.</span><span class="sxs-lookup"><span data-stu-id="b5590-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="b5590-136">No exemplo apresentado, o takt time é 0,2 horas por 10 unidades.</span><span class="sxs-lookup"><span data-stu-id="b5590-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="b5590-137">Para um tempo de trabalho de 8 horas, isso corresponde a uma capacidade de produtividade diária de 400 unidades.</span><span class="sxs-lookup"><span data-stu-id="b5590-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="b5590-138">No campo Quantidade por ciclo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b5590-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="b5590-139">Expanda ou recolha a seção Detalhes da versão.</span><span class="sxs-lookup"><span data-stu-id="b5590-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="b5590-140">No campo Takt time mínimo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b5590-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5590-141">O takt time mínimo deve ser menor que ou igual ao takt time médio.</span><span class="sxs-lookup"><span data-stu-id="b5590-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="b5590-142">No campo Takt time máximo, insira um número.</span><span class="sxs-lookup"><span data-stu-id="b5590-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="b5590-143">O takt time máximo deve ser maior que ou igual ao takt time médio.</span><span class="sxs-lookup"><span data-stu-id="b5590-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="b5590-144">Inserir um número de dias no Período para tempo de ciclo real</span><span class="sxs-lookup"><span data-stu-id="b5590-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="b5590-145">O período para tempo de ciclo real é o número de dias em que os trabalhos são agregados do minuto real regressivamente para calcular o tempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="b5590-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="b5590-146">O valor pode ser alterado a qualquer momento e só é usado para o cálculo dos tempos de ciclo reais.</span><span class="sxs-lookup"><span data-stu-id="b5590-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="b5590-147">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="b5590-147">Click Save.</span></span>

