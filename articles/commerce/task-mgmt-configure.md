---
title: Configurar gerenciamento de tarefas
description: Este tópico descreve como configurar os recursos de gerenciamento de tarefas no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 9a4775c2dba2b9aa8e671ab6c246000303b3a37e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4410254"
---
# <a name="configure-task-management"></a><span data-ttu-id="f0432-103">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0432-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f0432-104">Este tópico descreve como configurar os recursos de gerenciamento de tarefas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f0432-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f0432-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="f0432-105">Overview</span></span>

<span data-ttu-id="f0432-106">Antes que os gerentes e funcionários do Dynamics 365 Commerce possam usar os recursos de gerenciamento de tarefas do Commerce, o gerenciamento de tarefas deve ser configurado.</span><span class="sxs-lookup"><span data-stu-id="f0432-106">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="f0432-107">As etapas de configuração incluem a concessão de permissões a gerentes e funcionários, a distribuição de permissões para clientes de ponto de venda (PDV), a configuração de notificações PDV e a configuração do bloco de **Tarefas** na página inicial de um aplicativo de PDV.</span><span class="sxs-lookup"><span data-stu-id="f0432-107">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="f0432-108">Configurar permissões para gerentes de armazenamento</span><span class="sxs-lookup"><span data-stu-id="f0432-108">Configure permissions for store managers</span></span>

<span data-ttu-id="f0432-109">Cada trabalhador em uma determinada loja pode exibir todas as tarefas atribuídas a essa loja.</span><span class="sxs-lookup"><span data-stu-id="f0432-109">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="f0432-110">Eles também podem atualizar o status das tarefas atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="f0432-110">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="f0432-111">No entanto, as pessoas como gerentes de armazenamento devem ter permissões de gerenciamento de tarefas para gerenciar as tarefas atribuídas à loja e criar tarefas de finalidade única.</span><span class="sxs-lookup"><span data-stu-id="f0432-111">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="f0432-112">Para configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0432-112">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="f0432-113">Vá para **Retail e Commerce \> Funcionários \> Grupos de permissão**.</span><span class="sxs-lookup"><span data-stu-id="f0432-113">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="f0432-114">Selecione um grupo de permissões específico (por exemplo **Gerente**) e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f0432-114">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="f0432-115">Na guia **Permissões**, defina a opção **Permitir gerenciamento de tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0432-115">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="f0432-116">Na Guia Rápida **Notificações**, adicione a operação **Gerenciamento de tarefas**, e insira um valor no campo **Exibir ordem**.</span><span class="sxs-lookup"><span data-stu-id="f0432-116">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="f0432-117">Por exemplo, digite **2** se a operação **Preenchimento da ordem** já tiver um valor **Exibir ordem** como **1**.</span><span class="sxs-lookup"><span data-stu-id="f0432-117">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f0432-118">Se uma pessoa que não é gerente deve ter permissões de gerenciamento de tarefas no PDV, você pode conceder permissão à pessoa.</span><span class="sxs-lookup"><span data-stu-id="f0432-118">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="f0432-119">Alternativamente, você pode criar um novo grupo de permissão para não-gerentes e definir a opção **Permitir gerenciamento de tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="f0432-119">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="f0432-120">A ilustração a seguir mostra como configurar permissões de gerenciamento de tarefas para gerentes de loja.</span><span class="sxs-lookup"><span data-stu-id="f0432-120">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="f0432-122">Configurar permissões para funcionários</span><span class="sxs-lookup"><span data-stu-id="f0432-122">Configure permissions for employees</span></span>

<span data-ttu-id="f0432-123">Os funcionários devem ter permissões para criar listas de tarefas, gerenciar critérios de atribuição e configurar a recorrência de qualquer lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="f0432-123">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="f0432-124">Para configurar essas permissões, você atribui aos funcionários a função **Gerenciador de tarefas de varejo**.</span><span class="sxs-lookup"><span data-stu-id="f0432-124">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="f0432-125">Para configurar permissões para um funcionário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0432-125">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="f0432-126">Vá para **Retail e Commerce \> Funcionários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="f0432-126">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="f0432-127">Selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="f0432-127">Select an employee.</span></span>
1. <span data-ttu-id="f0432-128">Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções**.</span><span class="sxs-lookup"><span data-stu-id="f0432-128">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="f0432-129">Na caixa de diálogo **Atribuir funções ao usuário**, selecione a função **Gerenciador de tarefas de varejo** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="f0432-129">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="f0432-130">Distribuir permissões para clientes de PDV</span><span class="sxs-lookup"><span data-stu-id="f0432-130">Distribute permissions to POS clients</span></span>

<span data-ttu-id="f0432-131">Para que os funcionários possam usar clientes de PDV, as permissões devem ser distribuídas e sincronizadas para esses clientes.</span><span class="sxs-lookup"><span data-stu-id="f0432-131">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="f0432-132">Para distribuir permissões para clientes de PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0432-132">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="f0432-133">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="f0432-133">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="f0432-134">Selecione a agenda de distribuição **1060** (**Equipe**) e selecione **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="f0432-134">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="f0432-135">Selecione a agenda de distribuição **1070** (**Configuração de canal**) e selecione **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="f0432-135">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="f0432-136">Configurar notificações de PDV para tarefas</span><span class="sxs-lookup"><span data-stu-id="f0432-136">Configure POS notifications for tasks</span></span>

<span data-ttu-id="f0432-137">O gerenciamento de tarefas deve ser configurado de forma que as notificações estejam disponíveis no aplicativo de PDV.</span><span class="sxs-lookup"><span data-stu-id="f0432-137">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="f0432-138">Para configurar notificações de PDV para tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0432-138">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="f0432-139">Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="f0432-139">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="f0432-140">Encontre a operação **1400** (**Gerenciamento de tarefas**), e marque a caixa de seleção **Habilitar notificações** da operação.</span><span class="sxs-lookup"><span data-stu-id="f0432-140">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="f0432-141">A ilustração a seguir mostra a operação **Gerenciamento de tarefas** na página **Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="f0432-141">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Operação de gerenciamento de tarefas na página operações de PDV](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="f0432-143">Para obter mais informações sobre como configurar notificações POS, consulte [Mostrar notificações de ordem no ponto de venda (PDV)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="f0432-143">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="f0432-144">Configurar o bloco de tarefas em uma home page do aplicativo de PDV</span><span class="sxs-lookup"><span data-stu-id="f0432-144">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="f0432-145">Antes de configurar o bloco **Tarefas** na página inicial de um aplicativo de PDV, consulte [Layouts de tela do ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar e adicionar novos botões a um layout de tela PDV.</span><span class="sxs-lookup"><span data-stu-id="f0432-145">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="f0432-146">Para configurar o bloco **Tarefas** em uma página inicial do aplicativo de PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f0432-146">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="f0432-147">Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="f0432-147">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="f0432-148">Selecione um layout de tela, selecione um tamanho de layout e selecione uma grade de botões.</span><span class="sxs-lookup"><span data-stu-id="f0432-148">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="f0432-149">Na Guia Rápida **Grades de botões**, selecione **Designer** para editar a grade de botões selecionada.</span><span class="sxs-lookup"><span data-stu-id="f0432-149">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="f0432-150">Adicione um bloco de **Tarefas** à seção apropriada da página inicial.</span><span class="sxs-lookup"><span data-stu-id="f0432-150">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="f0432-151">A ilustração a seguir mostra um exemplo de bloco **Tarefas** em uma página inicial do PDV.</span><span class="sxs-lookup"><span data-stu-id="f0432-151">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Bloco de tarefas em uma página inicial do PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="f0432-153">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="f0432-153">Additional resources</span></span>

[<span data-ttu-id="f0432-154">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="f0432-154">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="f0432-155">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="f0432-155">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="f0432-156">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="f0432-156">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="f0432-157">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="f0432-157">Task management in POS</span></span>](task-mgmt-POS.md)
