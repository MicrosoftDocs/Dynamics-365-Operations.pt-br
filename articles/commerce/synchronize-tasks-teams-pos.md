---
title: Sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o PDV do Dynamics 365 Commerce
description: Este tópico descreve como sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o ponto de venda (PDV) do Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 74d53a850113c83979fba6baa4ff3c3e5d9ca02d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020618"
---
# <a name="synchronize-task-management-between-microsoft-teams-and-dynamics-365-commerce-pos"></a><span data-ttu-id="f2581-103">Sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o PDV do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f2581-103">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2581-104">Este tópico descreve como sincronizar o gerenciamento de tarefas entre o Microsoft Teams e o ponto de venda (PDV) do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2581-104">This topic describes how to synchronize task management between Microsoft Teams and Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="f2581-105">Uma das principais finalidades da integração do Teams é habilitar a sincronização do gerenciamento de tarefas entre o aplicativo de PDV e o Teams.</span><span class="sxs-lookup"><span data-stu-id="f2581-105">One of the main purposes of Teams integration is to enable the synchronization of task management between the POS application and Teams.</span></span> <span data-ttu-id="f2581-106">Dessa forma, os funcionários do armazenamento podem usar o aplicativo de PDV ou o Teams para gerenciar tarefas e não precisam trocar os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="f2581-106">In this way, store employees can use either the POS application or Teams to manage tasks, and don't have to switch applications.</span></span>

<span data-ttu-id="f2581-107">Como o Planejador é usado como um repositório de tarefas no Teams, deve haver um link entre o Teams e o Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2581-107">Because Planner is used as a repository for tasks in Teams, there must be a link between Teams and Dynamics 365 Commerce.</span></span> <span data-ttu-id="f2581-108">Esse link é estabelecido usando uma ID de plano específica para uma determinada equipe de loja.</span><span class="sxs-lookup"><span data-stu-id="f2581-108">This link is established by using a specific plan ID for a given store team.</span></span>

<span data-ttu-id="f2581-109">Os procedimentos a seguir mostram como configurar a sincronização de gerenciamento de tarefas entre os aplicativos PDV e Teams.</span><span class="sxs-lookup"><span data-stu-id="f2581-109">The following procedures show how to set up task management synchronization between the POS and Teams applications.</span></span>

## <a name="publish-a-test-task-list-in-teams"></a><span data-ttu-id="f2581-110">Publicar uma lista de tarefas de teste no Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-110">Publish a test task list in Teams</span></span>

<span data-ttu-id="f2581-111">O procedimento a seguir supõe que as equipes de loja estejam usando a integração do gerenciamento de tarefas do Microsoft Teams com o Commerce pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="f2581-111">The following procedure assumes that your store teams are using Microsoft Teams task management integration with Commerce for the first time.</span></span>

<span data-ttu-id="f2581-112">Para publicar uma lista de tarefas de teste no Teams, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f2581-112">To publish a test task list in Teams, follow these steps.</span></span>

1. <span data-ttu-id="f2581-113">Entre no Teams como um gerente de comunicações.</span><span class="sxs-lookup"><span data-stu-id="f2581-113">Sign in to Teams as a communications manager.</span></span> <span data-ttu-id="f2581-114">Normalmente, os gerentes de comunicações são usuários com a função **Gerente regional** no Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2581-114">Typically, communications managers are users who have the **Regional manager** role in Commerce.</span></span>
1. <span data-ttu-id="f2581-115">No painel de navegação esquerdo, selecione **Tarefas do Planejador**.</span><span class="sxs-lookup"><span data-stu-id="f2581-115">In the left navigation pane, select **Tasks by Planner**.</span></span>
1. <span data-ttu-id="f2581-116">Na guia **Listas publicadas**, selecione **Nova lista** na parte inferior esquerda e nomeie a nova lista como **Lista de tarefas de teste**.</span><span class="sxs-lookup"><span data-stu-id="f2581-116">On the **Published lists** tab, select **New list** in the lower left, and name the new list **Test task list**.</span></span>
1. <span data-ttu-id="f2581-117">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="f2581-117">Select **Create**.</span></span> <span data-ttu-id="f2581-118">A nova lista aparece em **Rascunhos**.</span><span class="sxs-lookup"><span data-stu-id="f2581-118">The new list appears under **Drafts**.</span></span>
1. <span data-ttu-id="f2581-119">Em **Título da tarefa**, conceda à primeira tarefa o título **Testando a integração do Teams**.</span><span class="sxs-lookup"><span data-stu-id="f2581-119">Under **Task title**, give the first task the title **Testing Teams integration**.</span></span> <span data-ttu-id="f2581-120">Depois, selecione **Enter**.</span><span class="sxs-lookup"><span data-stu-id="f2581-120">Then select **Enter**.</span></span>
1. <span data-ttu-id="f2581-121">Na lista **Rascunhos**, selecione a lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f2581-121">In the **Drafts** list, select the task list.</span></span> <span data-ttu-id="f2581-122">Em seguida, selecione **Publicar** no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="f2581-122">Then select **Publish** in the upper-right corner.</span></span>
1. <span data-ttu-id="f2581-123">Na caixa de diálogo **Selecionar quem publicará em**, selecione as equipes que devem receber a lista de tarefas de teste.</span><span class="sxs-lookup"><span data-stu-id="f2581-123">In the **Select who to publish to** dialog box, select the teams that should receive the test task list.</span></span>
1. <span data-ttu-id="f2581-124">Selecione **Avançar** para revisar o plano de publicação.</span><span class="sxs-lookup"><span data-stu-id="f2581-124">Select **Next** to review your publication plan.</span></span> <span data-ttu-id="f2581-125">Se for necessário fazer alterações, selecione **Voltar**.</span><span class="sxs-lookup"><span data-stu-id="f2581-125">If you must make changes, select **Back**.</span></span> 
1. <span data-ttu-id="f2581-126">Selecione **Confirmar para continuar** e selecione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="f2581-126">Select **Confirm to proceed**, and then select **Publish**.</span></span>
1. <span data-ttu-id="f2581-127">Depois de concluída a publicação, uma mensagem na parte superior da guia **Listas publicadas** indica se a sua lista de tarefas foi entregue com êxito.</span><span class="sxs-lookup"><span data-stu-id="f2581-127">After publishing is completed, a message at the top of the **Published lists** tab indicates whether your task list was successfully delivered.</span></span>

<span data-ttu-id="f2581-128">Para obter mais informações, consulte [Publicar listas de tarefas para criar e rastrear trabalho em sua organização](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span><span class="sxs-lookup"><span data-stu-id="f2581-128">For more information, see [Publish task lists to create and track work in your organization](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df).</span></span>

## <a name="link-pos-and-teams-for-task-management"></a><span data-ttu-id="f2581-129">Vincular PDV e o Teams para o gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="f2581-129">Link POS and Teams for task management</span></span>

<span data-ttu-id="f2581-130">Para vincular os aplicativos de PDV e do Microsoft Teams para o gerenciamento de tarefas na sede do Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f2581-130">To link the POS and Microsoft Teams applications for task management in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="f2581-131">Vá para **Varejo e Comércio \> Gerenciamento de tarefas \> Integração de tarefas com o Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f2581-131">Go to **Retail and Commerce \> Task management \> Tasks integration with Microsoft Teams**.</span></span>
1. <span data-ttu-id="f2581-132">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f2581-132">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="f2581-133">Defina a opção **Habilitar a Integração do Gerenciamento de Tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f2581-133">Set the **Enable Task Management Integration** option to **Yes**.</span></span>
1. <span data-ttu-id="f2581-134">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f2581-134">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="f2581-135">No Painel de Ações, selecione **Gerenciamento de tarefas de configuração**.</span><span class="sxs-lookup"><span data-stu-id="f2581-135">On the Action Pane, select **Setup task management**.</span></span> <span data-ttu-id="f2581-136">Você deve receber uma notificação que indique que um trabalho em lotes chamado **Provisão do Teams** está sendo criado.</span><span class="sxs-lookup"><span data-stu-id="f2581-136">You should receive a notification that indicates that a batch job that is named **Teams provision** is being created.</span></span>
1. <span data-ttu-id="f2581-137">Vá para **Administração do sistema \> Consultas \> Trabalhos em lotes**, e localize o trabalho mais recente com a descrição **Provisão do Teams**.</span><span class="sxs-lookup"><span data-stu-id="f2581-137">Go to **System administration \> Inquiries \> Batch jobs**, and find the most recent job that has the description **Teams provision**.</span></span> <span data-ttu-id="f2581-138">Aguarde até que a execução do trabalho tenha sido concluída.</span><span class="sxs-lookup"><span data-stu-id="f2581-138">Wait until this job has finished running.</span></span>
1. <span data-ttu-id="f2581-139">Execute o **Trabalho CDX 1070** para publicar a ID do plano e as referências da loja no Retail Server.</span><span class="sxs-lookup"><span data-stu-id="f2581-139">Run the **CDX job 1070** to publish the plan ID and store references to Retail Server.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2581-140">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f2581-140">Additional resources</span></span>

[<span data-ttu-id="f2581-141">Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-141">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="f2581-142">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-142">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>](enable-teams-integration.md)

[<span data-ttu-id="f2581-143">Provisionar o Microsoft Teams desde o Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="f2581-143">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="f2581-144">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-144">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="f2581-145">Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-145">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="f2581-146">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2581-146">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
