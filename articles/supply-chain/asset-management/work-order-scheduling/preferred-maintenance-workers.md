---
title: Configurar funcionários de manutenção preferenciais
description: Este tópico explica como configurar funcionários de manutenção preferidos no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887402"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="b42bd-103">Funcionários de manutenção preferenciais</span><span class="sxs-lookup"><span data-stu-id="b42bd-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b42bd-104">Você pode criar uma preferência em relação a quais funcionários de manutenção estão alocados para concluir as ordens de serviço durante o agendamento da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b42bd-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="b42bd-105">O uso dessa funcionalidade é opcional, mas pode ajudá-lo a escolher o funcionário de manutenção mais qualificado para concluir um trabalho, com base nas habilidades e competências do funcionário.</span><span class="sxs-lookup"><span data-stu-id="b42bd-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="b42bd-106">Portanto, durante o agendamento da ordem de serviço, a configuração em **Funcionários de manutenção preferenciais** é usada para determinar se um funcionário de manutenção ou um grupo de funcionários deve ser agendado para uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b42bd-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="b42bd-107">Apenas os funcionários de manutenção disponíveis no momento do agendamento serão agendados.</span><span class="sxs-lookup"><span data-stu-id="b42bd-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="b42bd-108">Se uma configuração do funcionário de manutenção corresponder a uma ordem de serviço durante o agendamento, mas o funcionário de manutenção estiver alocado para outros trabalhos, a ordem de serviço será agendada para outro funcionário de manutenção disponível.</span><span class="sxs-lookup"><span data-stu-id="b42bd-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="b42bd-109">Antes de configurar funcionários de manutenção preferenciais, você deverá primeiro configurar os funcionários e grupos de funcionários de manutenção que devem estar disponíveis para seleção.</span><span class="sxs-lookup"><span data-stu-id="b42bd-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="b42bd-110">Consulte [Funcionários e grupos de funcionários de manutenção](../setup-for-objects/workers-and-worker-groups.md) para obter uma descrição de como configurar os funcionários e grupos de funcionários de manutenção.</span><span class="sxs-lookup"><span data-stu-id="b42bd-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="b42bd-111">Configurar funcionários preferenciais</span><span class="sxs-lookup"><span data-stu-id="b42bd-111">Set up preferred workers</span></span>

<span data-ttu-id="b42bd-112">Um funcionário ou grupo de funcionários de manutenção preferenciais podem estar relacionados a um determinado</span><span class="sxs-lookup"><span data-stu-id="b42bd-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="b42bd-113">comércio</span><span class="sxs-lookup"><span data-stu-id="b42bd-113">trade</span></span>  
- <span data-ttu-id="b42bd-114">grade do tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="b42bd-114">maintenance job type variant</span></span>  
- <span data-ttu-id="b42bd-115">tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="b42bd-115">maintenance job type</span></span>  
- <span data-ttu-id="b42bd-116">categoria do tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="b42bd-116">maintenance job type category</span></span>  
- <span data-ttu-id="b42bd-117">ativo</span><span class="sxs-lookup"><span data-stu-id="b42bd-117">asset</span></span>  
- <span data-ttu-id="b42bd-118">tipo de ativo</span><span class="sxs-lookup"><span data-stu-id="b42bd-118">asset type</span></span>  

<span data-ttu-id="b42bd-119">ou uma combinação dessas seleções.</span><span class="sxs-lookup"><span data-stu-id="b42bd-119">or a combination of those selections.</span></span> <span data-ttu-id="b42bd-120">Quanto mais seleções você fizer no mesmo registro, mais específica será sua configuração.</span><span class="sxs-lookup"><span data-stu-id="b42bd-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="b42bd-121">Clique **Gerenciamento de ativos** > **Configuração** > **Funcionários** > **Funcionários de manutenção preferenciais**.</span><span class="sxs-lookup"><span data-stu-id="b42bd-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="b42bd-122">Clique em **Novo** para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="b42bd-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="b42bd-123">Comece criando uma configuração de funcionário de manutenção ou grupo de funcionários "padrão" que não possui seleções nos campos mostrados na lista de marcadores acima.</span><span class="sxs-lookup"><span data-stu-id="b42bd-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="b42bd-124">Isso significa que você só faz uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou **Funcionário de manutenção preferencial**.</span><span class="sxs-lookup"><span data-stu-id="b42bd-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="b42bd-125">Na figura abaixo, você vê um exemplo no primeiro registro em que "Solicitações" é selecionado como grupo de funcionários de manutenção preferenciais.</span><span class="sxs-lookup"><span data-stu-id="b42bd-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="b42bd-126">A configuração padrão será usada durante o agendamento da ordem de serviço, caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço durante o agendamento da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b42bd-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="b42bd-127">Repita a etapa 2 para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="b42bd-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="b42bd-128">Faça seleções necessárias, dependendo do nível de detalhe do funcionário ou grupo de funcionários preferenciais.</span><span class="sxs-lookup"><span data-stu-id="b42bd-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="b42bd-129">*Exemplo:* Na figura abaixo, no sexto registro, o funcionário de manutenção Shawn Richardson foi selecionado como funcionário preferencial.</span><span class="sxs-lookup"><span data-stu-id="b42bd-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="b42bd-130">Ele será selecionado automaticamente durante o agendamento de uma ordem de serviço que inclua o ativo "CH-BP1-03-02 e o tipo de trabalho de manutenção geral" Avaliação de instalações ", se ele estiver disponível no horário agendado.</span><span class="sxs-lookup"><span data-stu-id="b42bd-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="b42bd-131">Geralmente, quando um funcionário de manutenção preferencial é selecionado durante o agendamento da ordem de serviço, o Gerenciamento de Ativos passa por todos os registros de **Funcionários de manutenção preferenciais** verifica a existência uma correspondência possível, verificando sempre a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="b42bd-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="b42bd-132">Se nenhuma correspondência for encontrada, o registro "padrão" com uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou o campo **Funcionário de manutenção preferencial** é usado.</span><span class="sxs-lookup"><span data-stu-id="b42bd-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="b42bd-134">Você também pode configurar os funcionários de manutenção responsáveis que podem ser selecionados quando a uma solicitação de manutenção ou uma ordem de serviço for criada.</span><span class="sxs-lookup"><span data-stu-id="b42bd-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="b42bd-135">Em **Todas as ordens de trabalho** e **Todas as solicitações de manutenção**, você pode editar a seleção, se necessário.</span><span class="sxs-lookup"><span data-stu-id="b42bd-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="b42bd-136">Consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="b42bd-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="b42bd-137">Durante o agendamento da ordem de serviço, diferentes pontuações são calculadas para determinar quais funcionários devem concluir os trabalhos relacionados a uma ordem de serviço (aquelas pontuações são configuradas no link **parâmetros do Gerenciamento de ativos** > **agendamento da Ordem de serviço**).</span><span class="sxs-lookup"><span data-stu-id="b42bd-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="b42bd-138">Se dois ou mais funcionários de manutenção preferenciais ou funcionários de manutenção responsáveis obtiverem a mesma pontuação durante o agendamento da ordem de serviço, um funcionário é selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="b42bd-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="b42bd-139">Caso contrário, é sempre o funcionário com a pontuação mais alta que é alocado para concluir uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="b42bd-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

