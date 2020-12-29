---
title: Agendar utilização da carga
description: Este tópico explica como configurar e agendar o carregamento para um depósito.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87455077c69834c9ace6409f4cc611ae6e14beb4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421974"
---
# <a name="schedule-load-utilization"></a><span data-ttu-id="ff908-103">Agendar utilização da carga</span><span class="sxs-lookup"><span data-stu-id="ff908-103">Schedule load utilization</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ff908-104">Você pode agendar a utilização de carga para tipos de localização selecionados e também pode projetar a utilização atual e futura de carga.</span><span class="sxs-lookup"><span data-stu-id="ff908-104">You can schedule load utilization for selected location types, and you can also project the current and future load utilization.</span></span> <span data-ttu-id="ff908-105">Você pode projetar a carga para um ou mais sites, para unidades de carga (zona ou depósito) ou para uma combinação de um depósito e uma zona.</span><span class="sxs-lookup"><span data-stu-id="ff908-105">You can project the load for one or more sites, for the load units (zone or warehouse), or for a combination of a zone and a warehouse.</span></span>

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a><span data-ttu-id="ff908-106">Agendar e exibir a carga de um depósito ou site</span><span class="sxs-lookup"><span data-stu-id="ff908-106">Schedule and view the load for a warehouse or site</span></span>

<span data-ttu-id="ff908-107">Ao agendar a carga para sites, depósitos ou zonas, crie uma configuração de utilização de espaço e a associe a um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="ff908-107">To schedule the load for sites, warehouses, or zones, you create a space utilization setup and associate it with a master plan.</span></span>

<span data-ttu-id="ff908-108">Na configuração de utilização do espaço, use os tipos de local, como **Localização de massa** e **Local de separação** para especificar como a utilização de espaço deve ser projetada.</span><span class="sxs-lookup"><span data-stu-id="ff908-108">In the space utilization setup, you use location types, such as **Bulk location** and **Picking location**, to specify how space utilization should be projected.</span></span> <span data-ttu-id="ff908-109">Você também pode especificar um modo da carga de armazenamento, como **Zona**.</span><span class="sxs-lookup"><span data-stu-id="ff908-109">You also specify a storage load mode, such as **Zone**.</span></span>

<span data-ttu-id="ff908-110">A projeção de utilização futura de espaço é baseada nas informações calculadas no plano mestre associado.</span><span class="sxs-lookup"><span data-stu-id="ff908-110">The projection of future space utilization is based on information that is calculated on the associated master plan.</span></span> <span data-ttu-id="ff908-111">Planos mestres preveem o planejamento de recurso para ordens de entrada e de saída para produção e operações.</span><span class="sxs-lookup"><span data-stu-id="ff908-111">Master plans forecast the resource planning for incoming and outgoing orders for production and operations.</span></span> <span data-ttu-id="ff908-112">A projeção de espaço disponível é baseada na relação entre a configuração de utilização de espaço e o plano mestre selecionado.</span><span class="sxs-lookup"><span data-stu-id="ff908-112">The projection of available space is based on the relation between the space utilization setup and the selected master plan.</span></span>

<span data-ttu-id="ff908-113">Usando o modo de carga de estoque que você selecionou na configuração de utilização de espaço, você pode especificar se o carregamento deve ser projetado para cada depósito ou zona, ou se as projeções devem incluir informações sobre os depósitos e as zonas.</span><span class="sxs-lookup"><span data-stu-id="ff908-113">By using the storage load mode that you selected in the space utilization setup, you can specify whether the load should be projected for each warehouse or zone, or whether the projections should include information about both warehouses and zones.</span></span> <span data-ttu-id="ff908-114">Você também pode especificar se as localizações bloqueadas devem ser excluídas do cálculo da utilização de carga.</span><span class="sxs-lookup"><span data-stu-id="ff908-114">You also specify whether blocked locations should be excluded from the calculation of load utilization.</span></span>

<span data-ttu-id="ff908-115">Você pode projetar a utilização do espaço gerando o relatório **Utilização de carga do depósito**.</span><span class="sxs-lookup"><span data-stu-id="ff908-115">You can project the space utilization by generating the **Warehouse load utilization** report.</span></span> <span data-ttu-id="ff908-116">Quando você gera esse relatório, você pode especificar se a utilização de carga deve ser projetada para cada site, entre os sites ou para a unidade de carga selecionada, como a zona ou o depósito.</span><span class="sxs-lookup"><span data-stu-id="ff908-116">When you generate this report, you can specify whether the load utilization should be projected for each site, across sites, or for the selected load unit, such as zone or warehouse.</span></span>

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a><span data-ttu-id="ff908-117">Criar uma configuração de utilização de espaço para um depósito</span><span class="sxs-lookup"><span data-stu-id="ff908-117">Create a space utilization setup for a warehouse</span></span>

1. <span data-ttu-id="ff908-118">Selecione **Gerenciamento de estoque** \> **Configuração** \> **Monitoramento de depósito** \> **Utilização de espaço**.</span><span class="sxs-lookup"><span data-stu-id="ff908-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Space utilization**.</span></span>
2. <span data-ttu-id="ff908-119">Selecione **Novo** para criar uma configuração de utilização de espaço.</span><span class="sxs-lookup"><span data-stu-id="ff908-119">Select **New** to create a space utilization setup.</span></span> <span data-ttu-id="ff908-120">Especifique uma ID e um nome para a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="ff908-120">Specify an ID and a name for the new setup.</span></span>
3. <span data-ttu-id="ff908-121">No campo **Modo da carga de armazenamento**, selecione se a visão geral da utilização de espaço deve mostrar informações por depósito, zona, ou depósito e zona.</span><span class="sxs-lookup"><span data-stu-id="ff908-121">In the **Storage load mode** field, select whether the overview of space utilization should show information by warehouse, zone, or warehouse and zone.</span></span>
4. <span data-ttu-id="ff908-122">Defina a opção **Excluir localizações bloqueadas** como **Sim** para excluir os locais de estoque bloqueados do cálculo de espaço disponível.</span><span class="sxs-lookup"><span data-stu-id="ff908-122">Set the **Exclude blocked locations** option to **Yes** to exclude blocked inventory locations from the calculation of available space.</span></span> <span data-ttu-id="ff908-123">Você pode bloquear uma localização de estoque para entrada e saída especificando uma causa de bloqueio para a localização no campo **Entrada bloqueada** ou **Saída bloqueada** na Guia Rápida **Outro** na página **Locais de estoque**.</span><span class="sxs-lookup"><span data-stu-id="ff908-123">You can block an inventory location for input and output by specifying a blocking cause for the location in the **Input blocked** or **Output blocked** field on the **Other** FastTab on the **Inventory locations** page.</span></span>
5. <span data-ttu-id="ff908-124">Na Guia Rápida **Tipo de local**, selecione os tipos de localização para incluir no cálculo de utilização de espaço.</span><span class="sxs-lookup"><span data-stu-id="ff908-124">On the **Location type** FastTab, select the location types to include in the space utilization calculation.</span></span> <span data-ttu-id="ff908-125">Você deve selecionar pelo menos um tipo de localização para a projeção.</span><span class="sxs-lookup"><span data-stu-id="ff908-125">You must select at least one location type for the projection.</span></span>

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a><span data-ttu-id="ff908-126">Associe uma configuração de utilização de espaço a um plano mestre</span><span class="sxs-lookup"><span data-stu-id="ff908-126">Associate a space utilization setup with a master plan</span></span>

1. <span data-ttu-id="ff908-127">Selecione **Gerenciamento de estoque** \> **Tarefas periódicas** \> **Agendar utilização da carga**.</span><span class="sxs-lookup"><span data-stu-id="ff908-127">Select **Inventory management** \> **Periodic tasks** \> **Schedule load utilization**.</span></span>
2. <span data-ttu-id="ff908-128">No campo **Plano mestre**, selecione um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="ff908-128">In the **Master plan** field, select a master plan.</span></span>
3. <span data-ttu-id="ff908-129">No campo **Número de dias**, especifique o número de dias que serão incluídos na projeção de cargas de trabalho atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="ff908-129">In the **Number of days** field, specify the number of days to include in the projection of current and future workloads.</span></span>
4. <span data-ttu-id="ff908-130">No campo **Utilização de espaço**, selecione a configuração de utilização de espaço para ser usada na projeção de cargas de trabalho atuais e futuros.</span><span class="sxs-lookup"><span data-stu-id="ff908-130">In the **Space utilization** field, select the space utilization setup to use for the projection of current and future workloads.</span></span>

### <a name="specify-the-load-utilization-projection-and-view-information"></a><span data-ttu-id="ff908-131">Especifique a projeção da utilização de carga e exiba as informações</span><span class="sxs-lookup"><span data-stu-id="ff908-131">Specify the load utilization projection and view information</span></span>

1. <span data-ttu-id="ff908-132">Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Relatórios de estoque físico** \> **Utilização de custo indireto de depósito**.</span><span class="sxs-lookup"><span data-stu-id="ff908-132">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Warehouse load utilization**.</span></span>
2. <span data-ttu-id="ff908-133">No campo **Mostrar por**, selecione o nível da projeção de utilização de espaço:</span><span class="sxs-lookup"><span data-stu-id="ff908-133">In the **Show by** field, select the level of the space utilization projection:</span></span>

    - <span data-ttu-id="ff908-134">**Site** – Projetar a utilização de espaço para cada site.</span><span class="sxs-lookup"><span data-stu-id="ff908-134">**Site** – Project the space utilization for each site.</span></span> <span data-ttu-id="ff908-135">Esta projeção é útil se, por exemplo, você desejar exibir todos os depósitos de um site para que possa equilibrar a utilização de espaço entre os depósitos.</span><span class="sxs-lookup"><span data-stu-id="ff908-135">This projection is useful if, for example, you want to view all the warehouses for a site so that you can balance the space utilization between the warehouses.</span></span>
    - <span data-ttu-id="ff908-136">**Unidade de carga** – Projetar a utilização de espaço para zonas ou depósitos.</span><span class="sxs-lookup"><span data-stu-id="ff908-136">**Load unit** – Project the space utilization for zones or warehouses.</span></span> <span data-ttu-id="ff908-137">O espaço disponível é então projetado de acordo com o valor que você selecionou no campo **Modo da carga de armazenamento** na página **Utilização de espaço** quando criou a configuração de utilização de espaço.</span><span class="sxs-lookup"><span data-stu-id="ff908-137">The available space is then projected according to the value that you selected in the **Storage load mode** field on the **Space utilization** page when you created the space utilization setup.</span></span>

3. <span data-ttu-id="ff908-138">Siga uma destas etapas, dependendo do valor selecionado na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="ff908-138">Follow one of these steps, depending on the value that you selected in the previous step:</span></span>

    - <span data-ttu-id="ff908-139">Se você selecionou **Site** no campo **Exibir por**, o campo **Site** está disponível.</span><span class="sxs-lookup"><span data-stu-id="ff908-139">If you selected **Site** in the **Show by** field, the **Site** field is available.</span></span> <span data-ttu-id="ff908-140">Selecione um ou mais sites para incluir na projeção.</span><span class="sxs-lookup"><span data-stu-id="ff908-140">Select one or more sites to include in the projection.</span></span>
    - <span data-ttu-id="ff908-141">Se você selecionou **Carregar unidade** no campo **Exibir por**, o campo **Carregar unidade** está disponível.</span><span class="sxs-lookup"><span data-stu-id="ff908-141">If you selected **Load unit** in the **Show by** field, the **Load unit** field is available.</span></span> <span data-ttu-id="ff908-142">Selecione a unidade de carga.</span><span class="sxs-lookup"><span data-stu-id="ff908-142">Select the load unit.</span></span>

4. <span data-ttu-id="ff908-143">No campo **Carregar tipo**, selecione **Volume** ou **Peso** para especificar o depósito operando a unidade para a qual você projeta espaço.</span><span class="sxs-lookup"><span data-stu-id="ff908-143">In the **Load type** field, select **Volume** or **Weight** to specify the warehouse operating unit to project space for.</span></span>
5. <span data-ttu-id="ff908-144">No campo **Configuração de utilização de espaço**, selecione a configuração de utilização de espaço na qual a projeção deve ser baseada.</span><span class="sxs-lookup"><span data-stu-id="ff908-144">In the **Space utilization setup** field, select the space utilization setup that the projection should be based on.</span></span>
