---
title: Estados de ciclo de vida de ativo
description: Este tópico explica os estados de ciclo de vida de ativo e os modelos do ciclo de vida no Asset Management.
author: josaw1
manager: AnnBe
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2dc72c61ed4dbb04122c6859123307dc79f2b233
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783059"
---
# <a name="asset-lifecycle-states"></a><span data-ttu-id="3e970-103">Estados de ciclo de vida de ativo</span><span class="sxs-lookup"><span data-stu-id="3e970-103">Asset lifecycle states</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="3e970-104">Este tópico explica os estados de ciclo de vida de ativo e os modelos do ciclo de vida no Asset Management.</span><span class="sxs-lookup"><span data-stu-id="3e970-104">This topic explains asset lifecycle states and lifecycle models in Asset Management.</span></span> <span data-ttu-id="3e970-105">Os estados de ciclo de vida de ativo são usados para definir se um ativo está ativo ou inativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-105">Asset lifecycle states are used to define whether an asset is active or inactive.</span></span> <span data-ttu-id="3e970-106">Por exemplo, você pode configurar os estados de ciclo de vida de ativo como **Criado**, **Ativo** e **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="3e970-106">For example, you can set up asset lifecycle states such as **Created**, **Active**, and **Terminated**.</span></span>

> [!NOTE]
> - <span data-ttu-id="3e970-107">Os estados de ciclo de vida da solicitação estão vinculados aos estados de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-107">Request lifecycle states are linked to asset lifecycle states.</span></span> <span data-ttu-id="3e970-108">Portanto, quando uma solicitação é alterada para um novo estado de ciclo de vida da solicitação, o ativo associado à solicitação é alterado para um novo estado de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-108">Therefore, when a request is changed to a new request lifecycle state, the asset that is attached to the request is changed to a new asset lifecycle state.</span></span> <span data-ttu-id="3e970-109">Por exemplo, se o estado de ciclo de vida de uma solicitação for alterado para **Entrada**, o estado de ciclo de vida de ativo associado será alterado para o estado de ciclo de vida selecionado no campo **Estado do ciclo de vida de entrada** na Guia Rápida **Estado de ciclo de vida de ativo** da página **Modelos de estado de ciclo de vida de ativo**.</span><span class="sxs-lookup"><span data-stu-id="3e970-109">For example, if the lifecycle state of a request is changed to **Inbound**, the lifecycle state of the attached asset is changed to the lifecycle state that is selected in the **Inbound lifecycle state** field on the **Asset lifecycle state** FastTab of the **Asset lifecycle state models** page.</span></span> 


<span data-ttu-id="3e970-110">Os estados de ciclo de vida de ativo podem ser configurados nos modelos de ciclo de vida de ativo, onde você pode definir os estados necessários do ciclo de vida para vários tipos de ativos.</span><span class="sxs-lookup"><span data-stu-id="3e970-110">Asset lifecycle states can be set up in asset lifecycle models, where you can define the required lifecycle states for various types of assets.</span></span> <span data-ttu-id="3e970-111">Primeiro, você configura os estados de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3e970-111">You first set up lifecycle states.</span></span> <span data-ttu-id="3e970-112">Então, v-Você cria um modelo no ciclo de vida e seleciona os estados de ciclo de vida para ele.</span><span class="sxs-lookup"><span data-stu-id="3e970-112">You then create a lifecycle model and select lifecycle states for it.</span></span>

1. <span data-ttu-id="3e970-113">Selecione **Gerenciamento de ativos** \> **Configuração** \> **Ativos** \> **Estados de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="3e970-113">Select **Asset management** \> **Setup** \> **Assets** \> **Lifecycle states**.</span></span>
2. <span data-ttu-id="3e970-114">Selecione **Novo** para criar um novo estado de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-114">Select **New** to create a new asset lifecycle state.</span></span>
3. <span data-ttu-id="3e970-115">No campo **Estado de ciclo de vida**, insira a ID do estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3e970-115">In the **Lifecycle state** field, enter the lifecycle state ID.</span></span>
4. <span data-ttu-id="3e970-116">No campo **Nome**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3e970-116">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="3e970-117">O campo **Modelos de ciclo de vida** mostra o número de modelos de ciclo de vida de ativo que usam o estado de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-117">The **Lifecycle models** field shows the number of asset lifecycle models that use the asset lifecycle state.</span></span>

5. <span data-ttu-id="3e970-118">Defina a opção **Ativo** como **Sim** se esse estado de ciclo de vida tiver de ser um estado de ciclo de vida ativo (ou seja, se as ordens de serviço podem ser criadas para ativos que estejam nesse estado de ciclo de vida).</span><span class="sxs-lookup"><span data-stu-id="3e970-118">Set the **Active** option to **Yes** if this lifecycle state should be an active lifecycle state (in other words, if work orders can be created for assets that are in this lifecycle state).</span></span>
6. <span data-ttu-id="3e970-119">Defina a opção **Excluir linhas do calendário em aberto** como **Sim** se as linhas do calendário de ativos em aberto com um estado de ciclo de vida **Criado** do ativo tiverem de ser excluídas quando estiverem nesse estado de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3e970-119">Set the **Delete open calendar lines** option to **Yes** if open asset calendar lines that have an asset lifecycle state of **Created** should be deleted when they are in this lifecycle state.</span></span> <span data-ttu-id="3e970-120">Essa configuração será útil se você quiser limpar qualquer agendamento de manutenção em aberto que não seja mais relevante para o ativo (por exemplo, se o ativo não estiver mais ativo).</span><span class="sxs-lookup"><span data-stu-id="3e970-120">This setting is useful if you want to clean up any open maintenance schedules that are no longer relevant for the asset (for example, if the asset is no longer active).</span></span>

> [!NOTE]
> <span data-ttu-id="3e970-121">Os estados de ciclo de vida de ativo, os modelos de ciclo de vida de ativo e o ativo estão relacionados.</span><span class="sxs-lookup"><span data-stu-id="3e970-121">Asset lifecycle states, asset lifecycle models, and asset types are related.</span></span> <span data-ttu-id="3e970-122">Eles são usados da mesma forma como os estados de ciclo de vida da ordem serviço, os modelos de ciclo de vida da ordem de serviço e os tipos de ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3e970-122">They are used in the same way as work order lifecycle states, work order lifecycle models, and work order types.</span></span> 


<span data-ttu-id="3e970-123">Após a criação dos estados de ciclo de vida do ativo necessários, você poderá configurá-los nos modelos de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-123">After you've created the required asset lifecycle states, you can set up lifecycle states in asset lifecycle models.</span></span>

1. <span data-ttu-id="3e970-124">Selecione **Gerenciamento de ativos** \> **Configuração** \> **ativos** \> **modelos de ciclo de vida**.</span><span class="sxs-lookup"><span data-stu-id="3e970-124">Select **Asset management** \> **Setup** \> **assets** \> **lifecycle models**.</span></span>
2. <span data-ttu-id="3e970-125">Selecione **Novo** para criar um novo modelo de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-125">Select **New** to create a new asset lifecycle model.</span></span>
3. <span data-ttu-id="3e970-126">No campo **Modelo de ciclo de vida**, insira a ID do modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3e970-126">In the **Lifecycle model** field, enter the lifecycle model ID.</span></span>
4. <span data-ttu-id="3e970-127">No campo **Nome**, insira uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3e970-127">In the **Name** field, enter a description.</span></span>

    <span data-ttu-id="3e970-128">O campo **Estados de ciclo de vida** mostra o número de estados de ciclo de vida de ativo selecionados no modelo de ciclo de vida de ativo.</span><span class="sxs-lookup"><span data-stu-id="3e970-128">The **Lifecycle states** field shows the number of asset lifecycle states that are selected in the asset lifecycle model.</span></span> <span data-ttu-id="3e970-129">O campo **Tipos de ativo** mostra o número de tipos de ativo que usam o modelo de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3e970-129">The **Asset types** field shows the number of asset types that use the lifecycle model.</span></span>

5. <span data-ttu-id="3e970-130">Na Guia Rápida **Estados de ciclo de vida**, selecione os estados de ciclo de vida de ativo que devem ser incluídos no modelo de ciclo de vida de ativo:</span><span class="sxs-lookup"><span data-stu-id="3e970-130">On the **Lifecycle states** FastTab, select the asset lifecycle states that should be included in the asset lifecycle model:</span></span>

    - <span data-ttu-id="3e970-131">Para usar um estado de ciclo de vida para o modelo, selecione-o na seção **Estados de ciclo de vida restantes** e selecione o botão de seta para a direita ![Seta para a direita](media/15-setup-for-objects.png) para movê-lo até a seção **Estados de ciclo de vida selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3e970-131">To use a lifecycle state for the model, select it in the **Lifecycle states remaining** section, and then select the right arrow button ![Right arrow](media/15-setup-for-objects.png) to move it to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="3e970-132">Para usar todos os estados de ciclo de vida disponíveis para o modelo, selecione o botão **Todos os estados de ciclo de vida disponíveis** ![Todos os estados de ciclo de vida disponíveis](media/20-setup-for-objects.png).</span><span class="sxs-lookup"><span data-stu-id="3e970-132">To use all the available lifecycle states for the model, select the **All available lifecycle states** button ![All available lifecycle states](media/20-setup-for-objects.png).</span></span> <span data-ttu-id="3e970-133">Todos os estados de ciclo de vida são transferidos para a seção **Estados de ciclo de vida selecionados**.</span><span class="sxs-lookup"><span data-stu-id="3e970-133">All lifecycle states are transferred to the **Lifecycle states selected** section.</span></span>
    - <span data-ttu-id="3e970-134">Para remover um estado de ciclo de vida do modelo, selecione-o na seção **estados de ciclo de vida selecionados** e selecione o botão de seta para a esquerda ![Seta para a esquerda](media/16-setup-for-objects.png) para movê-lo até a seção **Estados de ciclo de vida restantes**.</span><span class="sxs-lookup"><span data-stu-id="3e970-134">To remove a lifecycle state from the model, select it in the **lifecycle states selected** section, and then select the left arrow button ![Left arrow](media/16-setup-for-objects.png) to move it to the **Lifecycle states remaining** section.</span></span>

6. <span data-ttu-id="3e970-135">Selecione **Atualizações do estado de ciclo de vida** para definir os estados de ciclo de vida de ativo que possam acompanhar um estado de ciclo de vida selecionado.</span><span class="sxs-lookup"><span data-stu-id="3e970-135">Select **Lifecycle state updates** to define the asset lifecycle states that can follow a selected lifecycle state.</span></span>
7. <span data-ttu-id="3e970-136">Use a Guia Rápida **Estado de ativo** se você lidar com ativos recebidos para reparo.</span><span class="sxs-lookup"><span data-stu-id="3e970-136">You use the **Asset state** FastTab if you handle assets that you receive for repair.</span></span> <span data-ttu-id="3e970-137">Na seção **Entrada/saída**, é possível selecionar estados de ciclo de vida de ativo para indicar o fluxo de trabalho de um ativo recebido para reparo.</span><span class="sxs-lookup"><span data-stu-id="3e970-137">In the **Inbound/outbound** section, you can select asset lifecycle states to indicate the workflow of an asset that you receive for repair.</span></span> <span data-ttu-id="3e970-138">Se oferecer ativos de empréstimo a clientes ou departamentos, na seção **Empréstimo** , você poderá selecionar estados de ciclo de vida para ativos de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="3e970-138">If you offer loan assets to customers or departments, in the **Loan** section, you can select lifecycle states for loan assets.</span></span>
