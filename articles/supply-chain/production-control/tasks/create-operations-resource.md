---
title: Criar um recurso de operações
description: Um recurso de operações executa as atividades de um projeto ou um processo de produção.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9ab91c449293338469fa2832156a85c4c32301fd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829033"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="ef7a4-103">Criar um recurso de operações</span><span class="sxs-lookup"><span data-stu-id="ef7a4-103">Create an operations resource</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef7a4-104">Um recurso de operações executa as atividades de um projeto ou um processo de produção.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="ef7a4-105">Estes procedimentos mostram como definir um recurso de operações.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="ef7a4-106">Você pode ver todo esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="ef7a4-107">Vá para Recursos.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-107">Go to Resources.</span></span>
2. <span data-ttu-id="ef7a4-108">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-108">Click New.</span></span>
3. <span data-ttu-id="ef7a4-109">No campo Recurso, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="ef7a4-110">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="ef7a4-111">Definir os parâmetros de capacidade e de consumo</span><span class="sxs-lookup"><span data-stu-id="ef7a4-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="ef7a4-112">Expandir a seção Operação.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="ef7a4-113">No campo de porcentagem de Sucata, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="ef7a4-114">No campo categoria de Configuração, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="ef7a4-115">Especifique a categoria de custo que define como contabilizar os custos de configuração.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="ef7a4-116">No campo categoria de Tempo de execução, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="ef7a4-117">Especifique a categoria de custo que define como contabilizar os custos de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="ef7a4-118">No campo categoria de Quantidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="ef7a4-119">Especifique a categoria de custo que define como contabilizar os custos do recurso com base na quantidade de saída.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="ef7a4-120">No campo Unidade de capacidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="ef7a4-121">Especifique a unidade na qual expressar a capacidade do recurso de operações.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="ef7a4-122">No campo Capacidade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="ef7a4-123">No campo Porcentagem de eficiência, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="ef7a4-124">Especifique a eficiência que você espera do recurso de operações.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="ef7a4-125">A porcentagem de eficiência ajusta a produtividade do recurso de operações e afeta o tempo que é reservado para o recurso.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="ef7a4-126">No campo percentual do plano de Operações, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="ef7a4-127">Especifique a porcentagem máxima de capacidade do recurso de operações que você deseja usar no plano de operações.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="ef7a4-128">Selecione Sim no campo da capacidade finita.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="ef7a4-129">Definir esta opção como Sim se o recurso de operações for planejado com base na capacidade real disponível e se as reservas de capacidade existentes forem consideradas.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="ef7a4-130">Se essa opção estiver definida como Não, o recurso de operações é considerado para que a capacidade infinita e o recurso possam ser reservados.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="ef7a4-131">Selecione Sim no campo Recurso de afunilamento.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="ef7a4-132">Definir horários de trabalho</span><span class="sxs-lookup"><span data-stu-id="ef7a4-132">Define working times</span></span>
1. <span data-ttu-id="ef7a4-133">Expandir a seção Calendários.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="ef7a4-134">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-134">Click Add.</span></span>
3. <span data-ttu-id="ef7a4-135">No campo Calendário, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="ef7a4-136">Especifique o calendário de produção que define a capacidade (em horas) do recurso.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="ef7a4-137">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="ef7a4-138">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="ef7a4-139">Definir capacidades do recurso</span><span class="sxs-lookup"><span data-stu-id="ef7a4-139">Define resource capabilities</span></span>
1. <span data-ttu-id="ef7a4-140">Expandir a seção Capacidades.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="ef7a4-141">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-141">Click Add.</span></span>
    * <span data-ttu-id="ef7a4-142">Um recurso é a capacidade de um recurso de operações de executar uma atividade específica.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="ef7a4-143">O mecanismo de planejamento aloca recursos correspondentes as requisições de recurso de cada atividade à capacidades dos recursos de operações disponíveis.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="ef7a4-144">No campo Capacidade, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="ef7a4-145">No campo Nível, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="ef7a4-146">Especifique o nível de proficiência para que o recurso processe a capacidade.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="ef7a4-147">No campo Prioridade, insira um número.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="ef7a4-148">Especifique a prioridade do recurso de operações em relação à capacidade.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="ef7a4-149">Ao planejar prioridade, o recurso de operações com prioridade mais alta (o menor valor numérico) é selecionado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="ef7a4-150">Atribuir um recurso ao grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="ef7a4-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="ef7a4-151">Expandir a seção Grupo de de recursos.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="ef7a4-152">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-152">Click Add.</span></span>
    * <span data-ttu-id="ef7a4-153">O grupo de recursos define o site, a unidade de produção e o contexto de depósito para recursos de operações.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="ef7a4-154">O recurso de operações só pode ser planejado quando atribuído a um grupo de recursos, e apenas o local no qual o grupo de recursos está localizado.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="ef7a4-155">No campo Grupo de recurso, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="ef7a4-156">No campo Local de entrada, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="ef7a4-157">Especifique o local no depósito de onde o recurso de operações está consumindo materiais.</span><span class="sxs-lookup"><span data-stu-id="ef7a4-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]