---
title: Configurar funcionários de manutenção preferenciais
description: Este tópico explica como configurar funcionários de manutenção preferidos no Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c0637609a34890360a3b81355a8d21ef1b9faf8c
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888920"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="ead33-103">Configurar funcionários de manutenção preferenciais</span><span class="sxs-lookup"><span data-stu-id="ead33-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="ead33-104">Durante o agendamento da ordem de serviço, você pode criar uma preferência em relação a qual funcionário de manutenção ou grupo de funcionários está alocado para concluir a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ead33-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="ead33-105">O uso dessa funcionalidade é opcional, mas pode ajudá-lo a escolher o funcionário de manutenção mais qualificado para concluir um trabalho, com base nas habilidades e competências do funcionário.</span><span class="sxs-lookup"><span data-stu-id="ead33-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="ead33-106">Apenas os funcionários de manutenção disponíveis no momento do agendamento serão agendados.</span><span class="sxs-lookup"><span data-stu-id="ead33-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="ead33-107">Se uma configuração preferencial do funcionário de manutenção corresponder a uma ordem de serviço durante o agendamento, mas o funcionário de manutenção estiver alocado para outros trabalhos, a ordem de serviço será agendada para outro funcionário de manutenção disponível.</span><span class="sxs-lookup"><span data-stu-id="ead33-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="ead33-108">Para poder configurar funcionários de manutenção preferenciais, você deve primeiro configurar os funcionários de manutenção e os grupos de funcionários.</span><span class="sxs-lookup"><span data-stu-id="ead33-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="ead33-109">Para obter uma descrição de como configurar os funcionários de manutenção e os grupos de funcionários, consulte [Funcionários de manutenção e grupos de trabalhadores](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="ead33-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="ead33-110">Configurar funcionários preferenciais</span><span class="sxs-lookup"><span data-stu-id="ead33-110">Set up preferred workers</span></span>

<span data-ttu-id="ead33-111">Um funcionário de manutenção ou grupo de funcionários preferencial pode estar relacionado a um ou mais do seguinte:</span><span class="sxs-lookup"><span data-stu-id="ead33-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="ead33-112">comércio</span><span class="sxs-lookup"><span data-stu-id="ead33-112">trade</span></span>  
- <span data-ttu-id="ead33-113">grade do tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="ead33-113">maintenance job type variant</span></span>  
- <span data-ttu-id="ead33-114">tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="ead33-114">maintenance job type</span></span>  
- <span data-ttu-id="ead33-115">categoria do tipo de trabalho de manutenção</span><span class="sxs-lookup"><span data-stu-id="ead33-115">maintenance job type category</span></span>  
- <span data-ttu-id="ead33-116">ativo</span><span class="sxs-lookup"><span data-stu-id="ead33-116">asset</span></span>  
- <span data-ttu-id="ead33-117">tipo de ativo</span><span class="sxs-lookup"><span data-stu-id="ead33-117">asset type</span></span>  

<span data-ttu-id="ead33-118">Quanto mais seleções você fizer no mesmo registro, mais específica será sua configuração.</span><span class="sxs-lookup"><span data-stu-id="ead33-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="ead33-119">Clique **Gerenciamento de ativos** > **Configuração** > **Funcionários** > **Funcionários de manutenção preferenciais**.</span><span class="sxs-lookup"><span data-stu-id="ead33-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="ead33-120">Clique em **Novo** para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="ead33-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="ead33-121">Comece criando um funcionário de manutenção ou grupo de funcionários "padrão".</span><span class="sxs-lookup"><span data-stu-id="ead33-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="ead33-122">Isso significa que você só faz uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou **Funcionário de manutenção preferencial**.</span><span class="sxs-lookup"><span data-stu-id="ead33-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="ead33-123">Na captura de tela abaixo, é exibido um exemplo no primeiro registro em que "Solicitações" está selecionado como **Grupo de funcionários de manutenção preferencial**.</span><span class="sxs-lookup"><span data-stu-id="ead33-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="ead33-124">A configuração padrão será usada durante o agendamento da ordem de serviço caso nenhuma outra combinação mais específica corresponda ao conteúdo da ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ead33-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="ead33-125">Repita a etapa 2 para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="ead33-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="ead33-126">Faça seleções necessárias, dependendo do nível de detalhe do funcionário ou grupo de funcionários preferenciais.</span><span class="sxs-lookup"><span data-stu-id="ead33-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="ead33-127">*Exemplo:* na captura de tela a seguir, no sexto registro, o funcionário de manutenção Shawn Richardson foi selecionado como funcionário preferencial.</span><span class="sxs-lookup"><span data-stu-id="ead33-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="ead33-128">Ele será selecionado automaticamente durante o agendamento de uma ordem de serviço que inclua o ativo "CH-BP1-03-02" e o tipo de trabalho de manutenção "Avaliação de instalações", se ele estiver disponível no horário agendado.</span><span class="sxs-lookup"><span data-stu-id="ead33-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="ead33-129">Geralmente, quando um funcionário de manutenção preferencial é selecionado durante o agendamento da ordem de serviço, o Gerenciamento de Ativos passa por todos os registros de **Funcionários de manutenção preferenciais** verifica a existência uma correspondência possível, verificando sempre a combinação mais específica primeiro.</span><span class="sxs-lookup"><span data-stu-id="ead33-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="ead33-130">Se nenhuma correspondência for encontrada, o registro "padrão" com uma seleção no campo **Grupo de funcionários de manutenção preferenciais** ou o campo **Funcionário de manutenção preferencial** é usado.</span><span class="sxs-lookup"><span data-stu-id="ead33-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="ead33-132">Você também pode configurar funcionários de manutenção *responsáveis*, que podem ser selecionados quando uma solicitação de manutenção ou uma ordem de serviço for criada.</span><span class="sxs-lookup"><span data-stu-id="ead33-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="ead33-133">É possível editar a seleção em **Todas as ordens de serviço** e **Todas as solicitações de manutenção**, se necessário.</span><span class="sxs-lookup"><span data-stu-id="ead33-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="ead33-134">Para obter mais informações, consulte [Funcionários de manutenção responsáveis](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="ead33-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="ead33-135">Durante o agendamento da ordem de serviço, diferentes pontuações são calculadas para determinar quais funcionários devem concluir os trabalhos relacionados a uma ordem de serviço (aquelas pontuações são configuradas no link **parâmetros do Gerenciamento de ativos** > **agendamento da Ordem de serviço**).</span><span class="sxs-lookup"><span data-stu-id="ead33-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="ead33-136">Se dois ou mais funcionários de manutenção preferenciais ou funcionários de manutenção responsáveis obtiverem a mesma pontuação durante o agendamento da ordem de serviço, um funcionário é selecionado aleatoriamente.</span><span class="sxs-lookup"><span data-stu-id="ead33-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="ead33-137">Caso contrário, é sempre o funcionário com a pontuação mais alta que é alocado para concluir uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ead33-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

