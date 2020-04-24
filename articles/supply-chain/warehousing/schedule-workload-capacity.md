---
title: Agendar a capacidade da carga de trabalho
description: Este tópico explica como definir e planejar a capacidade de carga de trabalho para trabalhadores em um depósito ou para um depósito completo.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd4225d9e7ad65939c57cb770ba521377c87dea3
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217255"
---
# <a name="schedule-workload-capacity"></a><span data-ttu-id="d9e87-103">Agendar capacidade da carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="d9e87-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="d9e87-104">É possível programar a capacidade de carga de trabalho para depósitos, e você também pode projetar cargas de trabalho atuais e futuras para os trabalhadores em depósitos individuais.</span><span class="sxs-lookup"><span data-stu-id="d9e87-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="d9e87-105">É possível projetar a carga de trabalho para todo o depósito ou projetar a carga de trabalho separadamente para as cargas de trabalho de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="d9e87-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="d9e87-106">Para projetar a carga de trabalho de saída para os depósitos selecionados, os dados do agendamento do planejamento mestre devem estar disponíveis para esses depósitos selecionados.</span><span class="sxs-lookup"><span data-stu-id="d9e87-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="d9e87-107">Para obter mais informações, consulte [Visão geral de Planos mestre](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d9e87-107">For more information, see [Master plans overview](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="d9e87-108">Programar e exibir cargas de trabalho para um depósito</span><span class="sxs-lookup"><span data-stu-id="d9e87-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="d9e87-109">Para programar a capacidade de carga de trabalho para um depósito, crie uma configuração de carga de trabalho para um ou mais depósitos e, em seguida, associe a configuração de carga de trabalho a um plano mestre.</span><span class="sxs-lookup"><span data-stu-id="d9e87-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="d9e87-110">Na configuração da capacidade de carga de trabalho, é possível definir limites para o peso ou em volume para as transações de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="d9e87-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="d9e87-111">É possível também criar mais de uma configuração para cada depósito e, em seguida, associar a configuração aos planos mestres individuais.</span><span class="sxs-lookup"><span data-stu-id="d9e87-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="d9e87-112">Por exemplo, é possível usar essa abordagem para acomodar as alterações sazonais na força de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9e87-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="d9e87-113">Se os trabalhadores de um depósito trabalharem com transações de cargas de trabalho de entrada e saída, você pode definir a configuração da capacidade do depósito de forma a projetar a carga de trabalho em uma exibição combinada.</span><span class="sxs-lookup"><span data-stu-id="d9e87-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="d9e87-114">Para planejar e visualizar cargas de trabalho de depósitos, é necessário concluir as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="d9e87-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="d9e87-115">Criar uma configuração de capacidade de carga de trabalho e definir limites de capacidade de carga de trabalho para um ou mais depósitos.</span><span class="sxs-lookup"><span data-stu-id="d9e87-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="d9e87-116">Associar a configuração da capacidade da carga de trabalho a um plano mestre para criar projeções da carga de trabalho e especificar por quanto tempo essas projeções serão aplicadas.</span><span class="sxs-lookup"><span data-stu-id="d9e87-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="d9e87-117">Criar uma configuração de capacidade de carga de trabalho para um depósito</span><span class="sxs-lookup"><span data-stu-id="d9e87-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="d9e87-118">Selecione **Gerenciamento de estoque** \> **Configuração** \> **Monitoramento de depósito** \> **Capacidade de carga de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d9e87-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="d9e87-119">No Painel de Ação, selecione **Novo** para criar uma configuração da capacidade de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9e87-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="d9e87-120">Na Guia Rápida **Depósitos**, selecione **Novo** e, em seguida, insira os valores na linha para associar um depósito à configuração da capacidade de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9e87-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="d9e87-121">Marque a caixa de seleção **Cargas de trabalho de entrada e saída combinadas** se o relatório **Capacidade de carga de trabalho** deve ter a carga de trabalho total para transações de entrada e saída em uma exibição.</span><span class="sxs-lookup"><span data-stu-id="d9e87-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="d9e87-122">Na Guia Rápida **Tipos de transação**, selecione os tipos de transação de entrada e saída aos quais os limites de carga de trabalho serão aplicados.</span><span class="sxs-lookup"><span data-stu-id="d9e87-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9e87-123">É necessário selecionar pelo menos um tipo de transação para as cargas de trabalho de entrada e de saída.</span><span class="sxs-lookup"><span data-stu-id="d9e87-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="d9e87-124">Definir limites para volume ou peso</span><span class="sxs-lookup"><span data-stu-id="d9e87-124">Define limits for volume or weight</span></span>

<span data-ttu-id="d9e87-125">É possível configurar limites para volume ou peso, dependendo de quais limitações são relevantes para a força de trabalho do depósito.</span><span class="sxs-lookup"><span data-stu-id="d9e87-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="d9e87-126">Os limites especificados são incluídos na projeção de capacidade de carga de trabalho que pode ser exibida no relatório **Capacidade de carga de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d9e87-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="d9e87-127">Para projetar informações sobre volume e peso dos itens, o volume padrão de um item de estoque e o peso de um item de estoque devem ser especificados para todos os produtos.</span><span class="sxs-lookup"><span data-stu-id="d9e87-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="d9e87-128">Os campos necessários estão disponíveis nos seguintes grupos de campos na Guia Rápida **Gerenciar Estoque** da página **Detalhes do produto liberado**:</span><span class="sxs-lookup"><span data-stu-id="d9e87-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="d9e87-129">Manuseio</span><span class="sxs-lookup"><span data-stu-id="d9e87-129">Handling</span></span>
- <span data-ttu-id="d9e87-130">Dimensões físicas</span><span class="sxs-lookup"><span data-stu-id="d9e87-130">Physical dimensions</span></span>
- <span data-ttu-id="d9e87-131">Medidas de peso</span><span class="sxs-lookup"><span data-stu-id="d9e87-131">Weight measurements</span></span>

<span data-ttu-id="d9e87-132">Se essas informações não forem especificadas corretamente, uma mensagem será recebida ao gerar o relatório **Capacidade de carga de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d9e87-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="d9e87-133">A partir do relatório, é possível fazer uma busca detalhada para identificar as informações que estão faltando para projetar a carga de trabalho futura.</span><span class="sxs-lookup"><span data-stu-id="d9e87-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="d9e87-134">Associe uma configuração de capacidade de carga de trabalho a um plano mestre</span><span class="sxs-lookup"><span data-stu-id="d9e87-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="d9e87-135">Selecione **Gerenciamento de estoque** \> **Periódico** \> **Agendar carga de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d9e87-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="d9e87-136">No campo **Plano mestre**, selecione o plano mestre a ser usado para as projeções de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9e87-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="d9e87-137">No campo **Número de dias**, especifique o número de dias que a projeção de carga de trabalho abrange.</span><span class="sxs-lookup"><span data-stu-id="d9e87-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="d9e87-138">No campo **Carga de trabalho**, selecione a configuração de carga de trabalho a ser associada ao plano mestre.</span><span class="sxs-lookup"><span data-stu-id="d9e87-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="d9e87-139">Visualização da capacidade de carga de trabalho</span><span class="sxs-lookup"><span data-stu-id="d9e87-139">View workload capacity</span></span>

1. <span data-ttu-id="d9e87-140">Selecione **Gerenciamento de estoque** \> **Consultas e relatórios** \> **Relatórios de estoque físico** \> **Capacidade de carga de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="d9e87-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="d9e87-141">No campo **Número de colunas**, especifique o número de colunas a serem exibidas no relatório.</span><span class="sxs-lookup"><span data-stu-id="d9e87-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="d9e87-142">No campo **Tipo da ordem**, selecione **Confirmado e planejado**, **Planejado** ou **Confirmado** para indicar o tipo do projeto no relatório.</span><span class="sxs-lookup"><span data-stu-id="d9e87-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="d9e87-143">No campo **Tipo de carga**, selecione um tipo de carga para especificar se a capacidade de carga de trabalho deve ser projetada por volume ou peso.</span><span class="sxs-lookup"><span data-stu-id="d9e87-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="d9e87-144">No campo **Capacidade de carga de trabalho**, selecione uma configuração de capacidade de carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d9e87-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>
