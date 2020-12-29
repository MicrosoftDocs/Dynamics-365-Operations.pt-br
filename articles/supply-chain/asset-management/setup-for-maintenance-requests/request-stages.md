---
title: Estados do ciclo de vida de solicitação de manutenção
description: Este tópico descreve como configurar estados do ciclo de vida de solicitação de manutenção no Asset Management.
author: josaw1
manager: tfehr
ms.date: 04/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetRequestLifecycleState, EntAssetRequestLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5849e3a8c3c619916c718032579d4fe6444fa49b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422479"
---
# <a name="maintenance-request-lifecycle-states"></a><span data-ttu-id="d890d-103">Estados do ciclo de vida da solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="d890d-103">Maintenance request lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="d890d-104">Os estados do ciclo de vida de solicitação de manutenção definem os estágios pelos quais uma solicitação pode passar.</span><span class="sxs-lookup"><span data-stu-id="d890d-104">Maintenance request lifecycle states define the stages that a request can go through.</span></span> <span data-ttu-id="d890d-105">Os exemplos incluem **Criada**, **Ativa** e **Concluída**.</span><span class="sxs-lookup"><span data-stu-id="d890d-105">Examples include **Created**, **Active**, and **Ended**.</span></span> <span data-ttu-id="d890d-106">Quando uma solicitação de manutenção é convertida em uma ordem de serviço, o estado do ciclo de vida de solicitação de manutenção deve ser atualizado para **Concluída** ou **Fechada** para indicar que a solicitação de manutenção não está mais ativa.</span><span class="sxs-lookup"><span data-stu-id="d890d-106">When a maintenance request is converted to a work order, the maintenance request lifecycle state should be updated to **Ended** or **Closed** to indicate that the maintenance request is no longer active.</span></span> <span data-ttu-id="d890d-107">Na página de listagem **Todas as solicitações de manutenção**, você pode exibir todas as solicitações de manutenção, independentemente do estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-107">On the **All maintenance requests** list page, you can view all maintenance requests, regardless of their lifecycle state.</span></span>

## <a name="set-up-maintenance-request-lifecycle-states"></a><span data-ttu-id="d890d-108">Configurar estados de ciclo de vida de solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="d890d-108">Set up maintenance request lifecycle states</span></span>

1. <span data-ttu-id="d890d-109">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Estados de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="d890d-109">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="d890d-110">Selecione **Novo** para criar um estado de ciclo de vida de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d890d-110">Select **New** to create a maintenance request lifecycle state.</span></span>
3. <span data-ttu-id="d890d-111">No campo **Estado de ciclo de vida**, insira uma ID para o estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-111">In the **Lifecycle state** field, enter an ID for the lifecycle state.</span></span>
4. <span data-ttu-id="d890d-112">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="d890d-112">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="d890d-113">Na Guia Rápida **Detalhes**, o campo **Modelos de ciclo de vida** mostra o número de modelos de ciclo de vida de solicitação de manutenção que usam o estado de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="d890d-113">On the **Details** FastTab, the **Lifecycle models** field shows the number of maintenance request lifecycle models that use this lifecycle state.</span></span>

5. <span data-ttu-id="d890d-114">Na Guia Rápida **Geral** , defina a opção **Ativa** como **Sim** se uma solicitação de manutenção estiver ativa neste estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-114">On the **General** FastTab, set the **Active** option to **Yes** if a maintenance request should be active while it's in this lifecycle state.</span></span>
6. <span data-ttu-id="d890d-115">Defina a opção **Definir término real** como **Sim** se uma data e hora de término reais são inseridas automaticamente em uma solicitação de manutenção que esteja nesse estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-115">Set the **Set actual end** option to **Yes** if an actual end date and time should automatically be entered on a maintenance request that is in this lifecycle state.</span></span>
7. <span data-ttu-id="d890d-116">Defina a opção **Criar ordem de serviço** como **Sim** se uma ordem de serviço puder ser criada de uma solicitação de manutenção que esteja nesse estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-116">Set the **Create work order** option to **Yes** if a work order can be created from a maintenance request that is in this lifecycle state.</span></span>
8. <span data-ttu-id="d890d-117">Defina a opção **Excluir** como **Sim** se uma solicitação de manutenção puder ser excluída quando estiver nesse estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-117">Set the **Delete** option to **Yes** if a maintenance request can be deleted while it's in this lifecycle state.</span></span>
9. <span data-ttu-id="d890d-118">Na Guia Rápida **Atualizar**, as opções **Entrada** e **Saída** na seção **Ativo** são relevantes se você usar o reparo do depósito.</span><span class="sxs-lookup"><span data-stu-id="d890d-118">On the **Update** FastTab, the **Inbound** and **Outbound** options in the **Asset** section are relevant if you use depot repair.</span></span> <span data-ttu-id="d890d-119">Defina a opção adequada como **Sim** se o estado do ciclo de vida do ativo selecionado em uma solicitação de manutenção for atualizado automaticamente para **Entrada** ou **Saída** quando o estado do ciclo de vida da solicitação de manutenção dessa solicitação de manutenção está definida como **Entrada** ou **Saída**.</span><span class="sxs-lookup"><span data-stu-id="d890d-119">Set the appropriate option to **Yes** if the asset lifecycle state of assets that are selected on a maintenance request should automatically be updated to **Inbound** or **Outbound** when the maintenance request lifecycle state of that maintenance request is set to **Inbound** or **Outbound**.</span></span>

<span data-ttu-id="d890d-120">A ilustração a seguir mostra um exemplo da página **Estados de ciclo de vida de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d890d-120">The follow illustration shows an example of the **Maintenance request lifecycle states** page.</span></span>

![Página de estados do ciclo de vida da solicitação de manutenção](media/02-setup-for-requests.png)

> [!NOTE]
> <span data-ttu-id="d890d-122">Os estados do ciclo de vida de solicitação de manutenção, os grupos do estado de ciclo de vida e os tipos estão relacionados a, e são usados da mesma forma que, estados de ciclo de vida da ordem de serviço, grupos de estados de ciclo de vida e tipos.</span><span class="sxs-lookup"><span data-stu-id="d890d-122">Maintenance request lifecycle states, lifecycle state groups, and types are related to, and used in the same way as, work order lifecycle states, lifecycle state groups, and types.</span></span> 

## <a name="set-up-maintenance-request-lifecycle-models"></a><span data-ttu-id="d890d-123">Configurar modelos de ciclo de vida de solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="d890d-123">Set up maintenance request lifecycle models</span></span>

<span data-ttu-id="d890d-124">Depois de você criar os estados de ciclo de vida que são necessários para as solicitações de manutenção, eles poderão ser divididos em grupos de estados de ciclo de vida, ou modelos de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-124">After you've created the lifecycle states that are required for your maintenance requests, they can be divided into lifecycle state groups, or lifecycle models.</span></span> <span data-ttu-id="d890d-125">Os modelos de ciclo de vida de solicitação de manutenção são usados para criar o fluxo que pode ser usado para diferentes tipos de solicitações de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d890d-125">Maintenance request lifecycle models are used to create the flow that can be used for different types of maintenance requests.</span></span> <span data-ttu-id="d890d-126">Pelo menos um modelo padrão de ciclo de vida de solicitação de manutenção deve ser criado.</span><span class="sxs-lookup"><span data-stu-id="d890d-126">At a minimum, one standard maintenance request lifecycle model should be created.</span></span>

1. <span data-ttu-id="d890d-127">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Solicitações de manutenção** \> **Modelos de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="d890d-127">Select **Asset management** \> **Setup** \> **Maintenance requests** \> **Lifecycle models**.</span></span>
2. <span data-ttu-id="d890d-128">Selecione **Novo** para criar um modelo de ciclo de vida de solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="d890d-128">Select **New** to create a maintenance request lifecycle model.</span></span>
3. <span data-ttu-id="d890d-129">No campo **Modelo de ciclo de vida**, insira a ID do modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-129">In the **Lifecycle model** field, enter an ID for the lifecycle model.</span></span>
4. <span data-ttu-id="d890d-130">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="d890d-130">In the **Name** field, enter a name.</span></span>

    <span data-ttu-id="d890d-131">Na Guia Rápida **Detalhes**, **Estados de ciclo de vida** mostra o número de estados de ciclo de vida de ativo selecionados no modelo de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="d890d-131">On the **Details** FastTab, the **Lifecycle states** shows the number of lifecycle states that are selected in this lifecycle model.</span></span> <span data-ttu-id="d890d-132">O campo **Tipos de solicitação de manutenção** mostra o número de tipos de solicitação de manutenção que usam esse modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="d890d-132">The **Maintenance request types** field shows the number of maintenance request types that use this lifecycle model.</span></span>

5. <span data-ttu-id="d890d-133">Na Guia Rápida **Estados de ciclo de vida**, selecione os estados de ciclo de vida que devem ser incluídos no modelo de ciclo de vida:</span><span class="sxs-lookup"><span data-stu-id="d890d-133">On the **Lifecycle states** FastTab, select the lifecycle states that should be included in the lifecycle model:</span></span>

    - <span data-ttu-id="d890d-134">Para incluir um estado de ciclo de vida no modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida restantes** e selecione o botão de seta para a direita ![Seta para a direita](media/03-setup-for-requests.png) para movê-lo até a seção **Estados de ciclo de vida selecionados**.</span><span class="sxs-lookup"><span data-stu-id="d890d-134">To include a lifecycle state in the lifecycle model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/03-setup-for-requests.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="d890d-135">Para incluir todos os estados de ciclo de vida disponíveis no modelo de ciclo de vida, selecione o botão **Selecionar todos os estados de ciclo de vida disponíveis** ![Selecionar todos os estados de ciclo de vida disponíveis](media/04-setup-for-requests.png).</span><span class="sxs-lookup"><span data-stu-id="d890d-135">To include all the available lifecycle states in the lifecycle model, select the **Select all available states** button ![Select all available states](media/04-setup-for-requests.png).</span></span> <span data-ttu-id="d890d-136">Todos os estados de ciclo de vida são movidos para a seção **Estados de ciclo de vida selecionados**.</span><span class="sxs-lookup"><span data-stu-id="d890d-136">All lifecycle states are moved to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="d890d-137">Para remover um estado de ciclo de vida do modelo de ciclo de vida, selecione-o na seção **Estados de ciclo de vida selecionados** e selecione o botão de seta para a esquerda ![Seta para a esquerda](media/05-setup-for-requests.png) para movê-lo até a seção **Estados de ciclo de vida restantes**.</span><span class="sxs-lookup"><span data-stu-id="d890d-137">To remove a lifecycle state from the lifecycle model, select it in the **Lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/05-setup-for-requests.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="d890d-138">Na Guia Rápida **Geral**, os campos da seção **Atualizações** serão relevantes se você usar o reparo de depósito.</span><span class="sxs-lookup"><span data-stu-id="d890d-138">On the **General** FastTab, the fields in the **Updates** section are relevant if you use depot repair.</span></span>

    - <span data-ttu-id="d890d-139">No campo **Estado de ciclo de vida para o ativo recebido**, selecione o estado de ciclo de vida de ativo para o qual os ativos selecionados em uma solicitação de manutenção deverão ser automaticamente atualizados quando forem recebidos para reparo de depósito.</span><span class="sxs-lookup"><span data-stu-id="d890d-139">In the **Lifecycle state for asset received** field, select the asset lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are received for depot repair.</span></span>
    - <span data-ttu-id="d890d-140">No campo **Estado de ciclo de vida para o ativo entregue**, selecione o estado de ciclo de vida de ativo para o qual os ativos selecionados em uma solicitação de manutenção deverão ser automaticamente atualizados quando forem devolvidos após o reparo.</span><span class="sxs-lookup"><span data-stu-id="d890d-140">In the **Lifecycle state for asset delivered** field, select the lifecycle state that assets that are selected on a maintenance request should automatically be updated to when they are returned after repair.</span></span>

<span data-ttu-id="d890d-141">A ilustração a seguir mostra um exemplo da página **Modelos de ciclo de vida de solicitação de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="d890d-141">The following illustration shows an example of the **Maintenance request lifecycle models** page.</span></span>

![Página dos modelos de ciclo de vida de solicitação de manutenção](media/06-setup-for-requests.png)
