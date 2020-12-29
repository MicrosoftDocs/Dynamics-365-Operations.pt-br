---
title: Agendamento de manutenção
description: Este tópico explica o agendamento de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetObjectCalendarCreateWO, EntAssetObjectCalendarListPagePoolsOpen, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePreviewPart, EntAssetObjectCalendarEdit, EntAssetObjectCalendarAdjust, EntAssetObjectCalendarDiscard, EntAssetObjectCalendarInfoPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 351e088ece0512fee1bb5f9dad020f32f7728fe4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422214"
---
# <a name="maintenance-schedule"></a><span data-ttu-id="3dded-103">Agendamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="3dded-103">Maintenance schedule</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3dded-104">O agendamento de manutenção contém uma lista de todos os planos de manutenção preventiva esperados, solicitações de manutenção e rounds de manutenção a serem executados. Algumas linhas de agendamento podem ter sido convertidas em ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="3dded-104">The maintenance schedule contains a list of all the expected preventive maintenance plans, maintenance requests, and maintenance rounds to be carried out. Some schedule lines may have been converted to work orders.</span></span>

<span data-ttu-id="3dded-105">As quatro exibições do agendamento de manutenção são um pouco diferentes, dependendo de quais linhas de agendamento de manutenção você quer ver.</span><span class="sxs-lookup"><span data-stu-id="3dded-105">The four maintenance schedule views are slightly different, depending on which maintenance schedule lines you want to see.</span></span>

| <span data-ttu-id="3dded-106">Item de menu</span><span class="sxs-lookup"><span data-stu-id="3dded-106">Menu item</span></span>                  | <span data-ttu-id="3dded-107">Descrição do conteúdo</span><span class="sxs-lookup"><span data-stu-id="3dded-107">Description of contents</span></span>                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3dded-108">Todos os agendamentos de manutenção</span><span class="sxs-lookup"><span data-stu-id="3dded-108">All maintenance schedule</span></span>       | <span data-ttu-id="3dded-109">Todas as linhas de agendamento de manutenção são mostradas.</span><span class="sxs-lookup"><span data-stu-id="3dded-109">All maintenance schedule lines are shown.</span></span>     |
| <span data-ttu-id="3dded-110">Minha agenda de ativos</span><span class="sxs-lookup"><span data-stu-id="3dded-110">My asset schedule</span></span>        | <span data-ttu-id="3dded-111">Todas as linhas de agendamento de manutenção que contêm ativos instalados nos locais funcionais para os quais você está relacionado como trabalhador (configurar em [Trabalhadores de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md)) são mostrados nesta lista.</span><span class="sxs-lookup"><span data-stu-id="3dded-111">All maintenance schedule lines containing assets installed on functional locations to which you are related as a worker (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)) are shown in this list.</span></span> |
| <span data-ttu-id="3dded-112">Abrir linhas do agendamento de manutenção</span><span class="sxs-lookup"><span data-stu-id="3dded-112">Open maintenance schedule lines</span></span> | <span data-ttu-id="3dded-113">As linhas de agendamento de manutenção com status "Criado" - que significa que eles não foram convertidos para uma ordem de serviço ou descartados - são mostradas nesta lista.</span><span class="sxs-lookup"><span data-stu-id="3dded-113">Maintenance schedule lines with status "Created" - meaning they have not yet been converted to a work order or discarded - are shown in this list.</span></span>                                            |
| <span data-ttu-id="3dded-114">Abrir grupos de agendamentos de manutenção</span><span class="sxs-lookup"><span data-stu-id="3dded-114">Open maintenance schedule pools</span></span> | <span data-ttu-id="3dded-115">As linhas de agendamento de manutenção relacionadas ao pool da ordem de serviço são mostradas nesta lista.</span><span class="sxs-lookup"><span data-stu-id="3dded-115">Maintenance schedule lines related to a work order pool are shown in this list.</span></span>                                                                                                                  |

>[!NOTE]
><span data-ttu-id="3dded-116">Se uma linha do agendamento de manutenção for incluída em vários pools da ordem de serviço (consulte [Pools da ordem de serviço](../work-orders/work-order-pools.md)), um registro será mostrado para cada pool em **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="3dded-116">If a maintenance schedule line is included in several work order pools (refer to [Work order pools](../work-orders/work-order-pools.md)), one record is shown for each pool in **Open maintenance schedule pools**.</span></span> <span data-ttu-id="3dded-117">Isso é feito para otimizar opções de filtragem em grupos de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="3dded-117">This is done to optimize filtering options on work order pools.</span></span>

<span data-ttu-id="3dded-118">Para abrir um agendamento de manutenção:</span><span class="sxs-lookup"><span data-stu-id="3dded-118">To open a maintenance schedule:</span></span>

1. <span data-ttu-id="3dded-119">Clique em **Gerenciamento de ativos** > **Comum** > **Agendamento de manutenção** > **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="3dded-119">Click **Asset management** > **Common** > **Maintenance schedule** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="3dded-120">Para atualizar o agendamento de manutenção, clique em **Plano de manutenção** ou em **Rounds de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="3dded-120">To update the maintenance schedule, click **Maintenance plan** or **Maintenance rounds**.</span></span> 

3. <span data-ttu-id="3dded-121">Você pode editar uma linha do plano da manutenção, selecionando-a e clicando em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3dded-121">You can edit a maintenance schedule line by selecting it and clicking **Edit**.</span></span> <span data-ttu-id="3dded-122">Por exemplo, você pode atualizar rapidamente o nível de serviço ou o trabalhador responsável pelo trabalho.</span><span class="sxs-lookup"><span data-stu-id="3dded-122">For example, you can easily update the service level or the worker responsible for the job.</span></span> <span data-ttu-id="3dded-123">Você só poderá editar as linhas de agendamento de manutenção que ainda não foram associadas a uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="3dded-123">You can only edit maintenance schedule lines that have not yet been connected to a work order.</span></span>

4. <span data-ttu-id="3dded-124">Você pode excluir uma linha do plano de agendamento selecionando-a na página de listagem e clicando em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="3dded-124">You can delete a maintenance schedule line by selecting it in the list page and clicking **Delete**.</span></span>

5. <span data-ttu-id="3dded-125">Você pode descartar uma linha do agendamento de manutenção selecionando-a na página de listagem e clicando em **Descartar**.</span><span class="sxs-lookup"><span data-stu-id="3dded-125">You can discard a maintenance schedule line by selecting it in the list page and clicking **Discard**.</span></span> <span data-ttu-id="3dded-126">Esta função é útil, por exemplo, se um ativo tiver um plano de manutenção de 2.000 km e um plano hora de manutenção de 10.000 km.</span><span class="sxs-lookup"><span data-stu-id="3dded-126">This function is useful if, for example, an asset has a 2,000 km maintenance plan and a 10,000 km maintenance plan.</span></span> <span data-ttu-id="3dded-127">Depois, talvez você queira descartar a linha criada do plano de manutenção de 2.000 km quando ele coincidir com 10.000 km, 20.000 km, 30.000 km e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="3dded-127">Then, you may want to discard the line created from the 2,000 km maintenance plan when it coincides with 10,000 km, 20,000 km, 30,000 km, and so on.</span></span> <span data-ttu-id="3dded-128">Se você descartar uma linha do agendamento de manutenção relacionada a um plano de manutenção, essa linha nunca aparecerá novamente quando o plano de manutenção for agendado.</span><span class="sxs-lookup"><span data-stu-id="3dded-128">If you discard a maintenance schedule line related to a maintenance plan, that line will never again appear when that maintenance plan is scheduled.</span></span>

6. <span data-ttu-id="3dded-129">Você pode selecionar várias linhas de agendamento de manutenção em **Todo agendamento de manutenção** e clicar em **Grupo de ordens de serviço**, se quiser que todas as linhas sejam incluídas no mesmo grupo de ordens de serviço.</span><span class="sxs-lookup"><span data-stu-id="3dded-129">You can select a number of maintenance schedule lines in **All maintenance schedule** and click **Work order pool**, if you want all selected lines to be included in the same work order pool.</span></span>

7. <span data-ttu-id="3dded-130">Você pode selecionar várias linhas de agendamento de manutenção em **Todo agendamento de manutenção** ou **Abrir linhas de agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção** e clicar em **Ajustar agendamento** se quiser fazer os mesmos ajustes em várias linhas.</span><span class="sxs-lookup"><span data-stu-id="3dded-130">You can select a number of maintenance schedule lines in **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools** and click **Adjust schedule** if you want to make the same adjustments on several lines.</span></span> <span data-ttu-id="3dded-131">Você pode alterar as datas inicial e final esperadas, nível de serviço e o grupo do funcionário de manutenção ou o funcionário de manutenção responsável relacionado às linhas de agendamento de manutenção selecionadas.</span><span class="sxs-lookup"><span data-stu-id="3dded-131">You can change expected start and end dates, service level, and the responsible maintenance worker group or responsible maintenance worker related to the selected maintenance schedule lines.</span></span>

- <span data-ttu-id="3dded-132">Quando uma linha do agendamento de manutenção estiver relacionada a uma ordem de serviço, o ID da ordem de serviço será exibido no campo **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3dded-132">When a maintenance schedule line has been related to a work order, the work order ID will be displayed in the **Work order** field.</span></span>  
- <span data-ttu-id="3dded-133">Na guia **Todos os ativos** exibição de detalhes > **Planos de manutenção do ativo**, você pode selecionar os planos de manutenção do ativo.</span><span class="sxs-lookup"><span data-stu-id="3dded-133">In **All assets** details view > **Asset maintenance plans** FastTab, you can select maintenance plans for the asset.</span></span> <span data-ttu-id="3dded-134">Posteriormente, se você excluir uma linha do plano de manutenção relacionada a um ativo em **Todos os ativos**, você também excluirá todas as linhas de agendamento de manutenção com status "Criado" que foram criadas com base nesse plano de manutenção.</span><span class="sxs-lookup"><span data-stu-id="3dded-134">Later, if you delete a maintenance plan line related to an asset in **All assets**, you also automatically delete all maintenance schedule lines with status "Created" that have been created based on that maintenance plan.</span></span> <span data-ttu-id="3dded-135">Consulte também [Criar um ativo](../objects/create-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="3dded-135">See also [Create an asset](../objects/create-an-object.md).</span></span>

<span data-ttu-id="3dded-136">A ilustração a seguir mostra a página da lista **Todos os agendamentos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="3dded-136">The illustration below shows the **All maintenance schedule** list page.</span></span>

![Figura 1](media/16-preventive-maintenance.png)

