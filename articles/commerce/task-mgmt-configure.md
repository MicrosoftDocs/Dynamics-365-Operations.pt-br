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
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ba2283bbfa2fdce75d3fbef6fcff47dd872c7998
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478035"
---
# <a name="configure-task-management"></a><span data-ttu-id="d1881-103">Configurar gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="d1881-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d1881-104">Este tópico descreve como configurar os recursos de gerenciamento de tarefas no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d1881-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d1881-105">Antes que os gerentes e funcionários do Dynamics 365 Commerce possam usar os recursos de gerenciamento de tarefas do Commerce, o gerenciamento de tarefas deve ser configurado.</span><span class="sxs-lookup"><span data-stu-id="d1881-105">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="d1881-106">As etapas de configuração incluem a concessão de permissões a gerentes e funcionários, a distribuição de permissões para clientes de ponto de venda (PDV), a configuração de notificações PDV e a configuração do bloco de **Tarefas** na página inicial de um aplicativo de PDV.</span><span class="sxs-lookup"><span data-stu-id="d1881-106">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="d1881-107">Configurar permissões para gerentes de armazenamento</span><span class="sxs-lookup"><span data-stu-id="d1881-107">Configure permissions for store managers</span></span>

<span data-ttu-id="d1881-108">Cada trabalhador em uma determinada loja pode exibir todas as tarefas atribuídas a essa loja.</span><span class="sxs-lookup"><span data-stu-id="d1881-108">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="d1881-109">Eles também podem atualizar o status das tarefas atribuídas a eles.</span><span class="sxs-lookup"><span data-stu-id="d1881-109">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="d1881-110">No entanto, as pessoas como gerentes de armazenamento devem ter permissões de gerenciamento de tarefas para gerenciar as tarefas atribuídas à loja e criar tarefas de finalidade única.</span><span class="sxs-lookup"><span data-stu-id="d1881-110">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="d1881-111">Para configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d1881-111">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="d1881-112">Vá para **Retail e Commerce \> Funcionários \> Grupos de permissão**.</span><span class="sxs-lookup"><span data-stu-id="d1881-112">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="d1881-113">Selecione um grupo de permissões específico (por exemplo **Gerente**) e, em seguida, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d1881-113">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="d1881-114">Na guia **Permissões**, defina a opção **Permitir gerenciamento de tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d1881-114">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="d1881-115">Na Guia Rápida **Notificações**, adicione a operação **Gerenciamento de tarefas**, e insira um valor no campo **Exibir ordem**.</span><span class="sxs-lookup"><span data-stu-id="d1881-115">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="d1881-116">Por exemplo, digite **2** se a operação **Preenchimento da ordem** já tiver um valor **Exibir ordem** como **1**.</span><span class="sxs-lookup"><span data-stu-id="d1881-116">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="d1881-117">Se uma pessoa que não é gerente deve ter permissões de gerenciamento de tarefas no PDV, você pode conceder permissão à pessoa.</span><span class="sxs-lookup"><span data-stu-id="d1881-117">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="d1881-118">Alternativamente, você pode criar um novo grupo de permissão para não-gerentes e definir a opção **Permitir gerenciamento de tarefas** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="d1881-118">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="d1881-119">A ilustração a seguir mostra como configurar permissões de gerenciamento de tarefas para gerentes de loja.</span><span class="sxs-lookup"><span data-stu-id="d1881-119">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Configurar permissões de gerenciamento de tarefas para os gerentes de armazenamento](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="d1881-121">Configurar permissões para funcionários</span><span class="sxs-lookup"><span data-stu-id="d1881-121">Configure permissions for employees</span></span>

<span data-ttu-id="d1881-122">Os funcionários devem ter permissões para criar listas de tarefas, gerenciar critérios de atribuição e configurar a recorrência de qualquer lista de tarefas.</span><span class="sxs-lookup"><span data-stu-id="d1881-122">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="d1881-123">Para configurar essas permissões, você atribui aos funcionários a função **Gerenciador de tarefas de varejo**.</span><span class="sxs-lookup"><span data-stu-id="d1881-123">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="d1881-124">Para configurar permissões para um funcionário, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d1881-124">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="d1881-125">Vá para **Retail e Commerce \> Funcionários \> Usuários**.</span><span class="sxs-lookup"><span data-stu-id="d1881-125">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="d1881-126">Selecione um funcionário.</span><span class="sxs-lookup"><span data-stu-id="d1881-126">Select an employee.</span></span>
1. <span data-ttu-id="d1881-127">Na Guia Rápida **Funções do usuário**, selecione **Atribuir funções**.</span><span class="sxs-lookup"><span data-stu-id="d1881-127">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="d1881-128">Na caixa de diálogo **Atribuir funções ao usuário**, selecione a função **Gerenciador de tarefas de varejo** e, em seguida, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="d1881-128">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="d1881-129">Distribuir permissões para clientes de PDV</span><span class="sxs-lookup"><span data-stu-id="d1881-129">Distribute permissions to POS clients</span></span>

<span data-ttu-id="d1881-130">Para que os funcionários possam usar clientes de PDV, as permissões devem ser distribuídas e sincronizadas para esses clientes.</span><span class="sxs-lookup"><span data-stu-id="d1881-130">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="d1881-131">Para distribuir permissões para clientes de PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d1881-131">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="d1881-132">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="d1881-132">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="d1881-133">Selecione a agenda de distribuição **1060** (**Equipe**) e selecione **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="d1881-133">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="d1881-134">Selecione a agenda de distribuição **1070** (**Configuração de canal**) e selecione **Executar agora**.</span><span class="sxs-lookup"><span data-stu-id="d1881-134">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="d1881-135">Configurar notificações de PDV para tarefas</span><span class="sxs-lookup"><span data-stu-id="d1881-135">Configure POS notifications for tasks</span></span>

<span data-ttu-id="d1881-136">O gerenciamento de tarefas deve ser configurado de forma que as notificações estejam disponíveis no aplicativo de PDV.</span><span class="sxs-lookup"><span data-stu-id="d1881-136">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="d1881-137">Para configurar notificações de PDV para tarefas, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d1881-137">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="d1881-138">Vá para **Retail e Commerce \> Configuração de canal \> Configuração do PDV \> PDV \> Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="d1881-138">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="d1881-139">Encontre a operação **1400** (**Gerenciamento de tarefas**), e marque a caixa de seleção **Habilitar notificações** da operação.</span><span class="sxs-lookup"><span data-stu-id="d1881-139">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="d1881-140">A ilustração a seguir mostra a operação **Gerenciamento de tarefas** na página **Operações de PDV**.</span><span class="sxs-lookup"><span data-stu-id="d1881-140">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Operação de gerenciamento de tarefas na página operações de PDV](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="d1881-142">Para obter mais informações sobre como configurar notificações POS, consulte [Mostrar notificações de ordem no ponto de venda (PDV)](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="d1881-142">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="d1881-143">Configurar o bloco de tarefas em uma home page do aplicativo de PDV</span><span class="sxs-lookup"><span data-stu-id="d1881-143">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="d1881-144">Antes de configurar o bloco **Tarefas** na página inicial de um aplicativo de PDV, consulte [Layouts de tela do ponto de venda (PDV)](pos-screen-layouts.md) para obter informações sobre como configurar e adicionar novos botões a um layout de tela PDV.</span><span class="sxs-lookup"><span data-stu-id="d1881-144">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="d1881-145">Para configurar o bloco **Tarefas** em uma página inicial do aplicativo de PDV, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="d1881-145">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="d1881-146">Vá para **Varejo e Comércio \> Configuração de canal \> Configuração do PDV \> PDV \> Layouts da tela**.</span><span class="sxs-lookup"><span data-stu-id="d1881-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="d1881-147">Selecione um layout de tela, selecione um tamanho de layout e selecione uma grade de botões.</span><span class="sxs-lookup"><span data-stu-id="d1881-147">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="d1881-148">Na Guia Rápida **Grades de botões**, selecione **Designer** para editar a grade de botões selecionada.</span><span class="sxs-lookup"><span data-stu-id="d1881-148">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="d1881-149">Adicione um bloco de **Tarefas** à seção apropriada da página inicial.</span><span class="sxs-lookup"><span data-stu-id="d1881-149">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="d1881-150">A ilustração a seguir mostra um exemplo de bloco **Tarefas** em uma página inicial do PDV.</span><span class="sxs-lookup"><span data-stu-id="d1881-150">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Bloco de tarefas em uma página inicial do PDV](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="d1881-152">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="d1881-152">Additional resources</span></span>

[<span data-ttu-id="d1881-153">Visão geral do gerenciamento de tarefas</span><span class="sxs-lookup"><span data-stu-id="d1881-153">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="d1881-154">Criar listas de tarefas e adicionar tarefas</span><span class="sxs-lookup"><span data-stu-id="d1881-154">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="d1881-155">Atribuir listas de tarefas a lojas ou funcionários</span><span class="sxs-lookup"><span data-stu-id="d1881-155">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="d1881-156">Gerenciamento de tarefas em PDV</span><span class="sxs-lookup"><span data-stu-id="d1881-156">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
