---
title: Configurar recursos do projeto
description: Este tópico fornece informações sobre como configurar ou solicitar recursos de projeto.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760478"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="e9203-103">Configurar recursos do projeto</span><span class="sxs-lookup"><span data-stu-id="e9203-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e9203-104">Você deve configurar um calendário e associá-lo a um funcionário ou a um trabalhador.</span><span class="sxs-lookup"><span data-stu-id="e9203-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="e9203-105">O calendário é usado para agendar o projeto e o horário de trabalho dos recursos reservados para o projeto.</span><span class="sxs-lookup"><span data-stu-id="e9203-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="e9203-106">Durante a configuração de calendário, os gerentes de projeto podem fazer o nivelamento de recursos como parte da otimização de recursos.</span><span class="sxs-lookup"><span data-stu-id="e9203-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="e9203-107">Com base na agenda de calendário, as restrições podem ser colocadas nos recursos.</span><span class="sxs-lookup"><span data-stu-id="e9203-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="e9203-108">Você pode configurar um calendário na página **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="e9203-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="e9203-109">Quando você configura um trabalhador como um recurso de projeto, você pode selecionar os trabalhadores que trabalham na empresa para a qual você está configurando recursos.</span><span class="sxs-lookup"><span data-stu-id="e9203-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="e9203-110">Se preferir, você pode selecionar trabalhadores de outras empresas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="e9203-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="e9203-111">Esses trabalhadores são conhecidos como recursos intercompanhia.</span><span class="sxs-lookup"><span data-stu-id="e9203-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="e9203-112">Os procedimentos a seguir explicam como configurar um trabalhador como um recurso de projeto em sua empresa e como configurar um recurso intercompanhia do projeto.</span><span class="sxs-lookup"><span data-stu-id="e9203-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="e9203-113">Configurar um trabalhador como um recurso do projeto</span><span class="sxs-lookup"><span data-stu-id="e9203-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="e9203-114">Na página **Trabalhadores**, na lista **Trabalhadores**, selecione o trabalhador que você está adicionando como um recurso de projeto e abra o registro do trabalhador.</span><span class="sxs-lookup"><span data-stu-id="e9203-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="e9203-115">No Painel de Ação, selecione **Projeto** &gt; **Configuração** &gt; **Configuração do projeto**.</span><span class="sxs-lookup"><span data-stu-id="e9203-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="e9203-116">Selecione um calendário e feche a página.</span><span class="sxs-lookup"><span data-stu-id="e9203-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="e9203-117">Você também pode especificar projetos padrão para um recurso como um tipo de atribuição prévia.</span><span class="sxs-lookup"><span data-stu-id="e9203-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="e9203-118">As atribuições prévias podem ser usadas quando o gerente de recurso ou o gerente de projeto sabem com antecedência em quais projetos o recurso trabalhará.</span><span class="sxs-lookup"><span data-stu-id="e9203-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="e9203-119">As atribuições prévias também podem ser baseadas na solicitação de um patrocinador ou de um cliente do projeto.</span><span class="sxs-lookup"><span data-stu-id="e9203-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="e9203-120">Para atribuir um projeto previamente, na página **Atribuir projetos**, na guia **Projetos**, na lista **Projetos restantes**, selecione o projeto apropriado.</span><span class="sxs-lookup"><span data-stu-id="e9203-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="e9203-121">Configurar um recurso intercompanhia</span><span class="sxs-lookup"><span data-stu-id="e9203-121">Set up an intercompany resource</span></span>

<span data-ttu-id="e9203-122">Quando configurar um trabalhador como um recurso intercompanhia, você deve concluir a instalação na empresa de crédito e na empresa de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="e9203-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="e9203-123">Na empresa de crédito</span><span class="sxs-lookup"><span data-stu-id="e9203-123">In the lending company</span></span>

1. <span data-ttu-id="e9203-124">No Finance, verifique se a empresa de crédito está selecionada e conclua o procedimento da seção anterior, "Configurar um trabalhador como um recurso de projeto."</span><span class="sxs-lookup"><span data-stu-id="e9203-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="e9203-125">Na página **Contabilização intercompanhia** , selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e9203-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="e9203-126">No campo **ID de entidade legal**, selecione a empresa de crédito.</span><span class="sxs-lookup"><span data-stu-id="e9203-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="e9203-127">Preencha os campos restantes conforme apropriado e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e9203-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="e9203-128">Na página **Transferir preço** , selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="e9203-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="e9203-129">No campo **Entidade legal que toma o empréstimo**, selecione a empresa apropriada.</span><span class="sxs-lookup"><span data-stu-id="e9203-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="e9203-130">Para emprestar à empresa de empréstimo somente o recurso que você criou no início desta seção , no campo **Recurso**, selecione o nome do recurso criado.</span><span class="sxs-lookup"><span data-stu-id="e9203-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="e9203-131">Para tornar todos os recursos na empresa de crédito disponíveis para a empresa de empréstimo, deixe o campo **Recurso** em branco.</span><span class="sxs-lookup"><span data-stu-id="e9203-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="e9203-132">Na página **Parâmetros de gerenciamento e contabilidade de projetos.**, na guia **Intercompanhia**, defina a opção **Habilitar quadro de horários e agendamento de recursos intercompanhia** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="e9203-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="e9203-133">Na empresa de empréstimo</span><span class="sxs-lookup"><span data-stu-id="e9203-133">In the borrowing company</span></span>

- <span data-ttu-id="e9203-134">Na página **Lista de recursos**, no filtro de pesquisas, insira o nome do recurso que você criou para a empresa de crédito para verificar se o nome está incluído na lista de recurso da empresa de empréstimo.</span><span class="sxs-lookup"><span data-stu-id="e9203-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="e9203-135">Solicitar recursos de projeto</span><span class="sxs-lookup"><span data-stu-id="e9203-135">Request project resources</span></span>
<span data-ttu-id="e9203-136">A funcionalidade de agendamento do recurso de projeto permite apenas gerentes de recurso para distribuir recursos recrutados em compromissos ou projetos.</span><span class="sxs-lookup"><span data-stu-id="e9203-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="e9203-137">Para habilitar essa funcionalidade, conclua as seguintes tarefas ou verifique se elas foram preenchidas:</span><span class="sxs-lookup"><span data-stu-id="e9203-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="e9203-138">Configure as sequências numéricas.</span><span class="sxs-lookup"><span data-stu-id="e9203-138">Set up number sequences.</span></span>
- <span data-ttu-id="e9203-139">Configurar fluxos de trabalho para gerenciamento e contabilidade de projetos.</span><span class="sxs-lookup"><span data-stu-id="e9203-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="e9203-140">Habilitar fluxos de trabalho de solicitação de recurso.</span><span class="sxs-lookup"><span data-stu-id="e9203-140">Enable resource request workflows.</span></span>

<span data-ttu-id="e9203-141">Depois que as tarefas precedentes forem concluídas, você pode completar estas tarefas quando necessário:</span><span class="sxs-lookup"><span data-stu-id="e9203-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="e9203-142">Criar uma solicitação de um recurso recrutado de modo flexível</span><span class="sxs-lookup"><span data-stu-id="e9203-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="e9203-143">Monitorar solicitações de recurso.</span><span class="sxs-lookup"><span data-stu-id="e9203-143">Monitor resource requests.</span></span>
- <span data-ttu-id="e9203-144">Preencher solicitações de recurso.</span><span class="sxs-lookup"><span data-stu-id="e9203-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="e9203-145">Solicitar um recurso recrutado de uma WBS.</span><span class="sxs-lookup"><span data-stu-id="e9203-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="e9203-146">Inscrever recursos a um projeto sem ter uma solicitação de um recurso recrutado.</span><span class="sxs-lookup"><span data-stu-id="e9203-146">Book resources to a project without having a request for a staffed resource.</span></span>
