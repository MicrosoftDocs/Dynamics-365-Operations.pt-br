---
title: Criação de ordens de serviço
description: Este tópico explica como criar ordens de serviço no Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetMaintenancePlan, EntAssetObjectCalendarListPage, EntAssetObjectCalendarListPagePoolsOpen
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 3982232e5008d6f8c283d6cecfaf2fa6e66150a1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836725"
---
# <a name="creating-work-orders"></a><span data-ttu-id="f6c72-103">Criação de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="f6c72-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f6c72-104">Depois de agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para eles.</span><span class="sxs-lookup"><span data-stu-id="f6c72-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="f6c72-105">Você pode concluir essa etapa usando um dos agendamentos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="f6c72-106">Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência, conforme descrito na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="f6c72-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="f6c72-107">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="f6c72-107">Reference type</span></span> | <span data-ttu-id="f6c72-108">descrição</span><span class="sxs-lookup"><span data-stu-id="f6c72-108">Description</span></span> |
|---|---|
| <span data-ttu-id="f6c72-109">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="f6c72-109">Maintenance plans</span></span> | <span data-ttu-id="f6c72-110">Trabalhos de manutenção que são baseadas com base no tipo de plano de manutenção *Tempo* ou *Contador*.</span><span class="sxs-lookup"><span data-stu-id="f6c72-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="f6c72-111">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="f6c72-111">Maintenance rounds</span></span> | <span data-ttu-id="f6c72-112">Trabalhos de manutenção preventiva que têm vários ativos que requerem um tipo semelhante de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="f6c72-113">Solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="f6c72-113">Maintenance request</span></span> | <span data-ttu-id="f6c72-114">Uma solicitação criada manualmente para manutenção ou reparo de um ativo.</span><span class="sxs-lookup"><span data-stu-id="f6c72-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="f6c72-115">Essa solicitação pode ser convertida em uma ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f6c72-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="f6c72-116">Criar ordens de trabalho com base no seu plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="f6c72-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="f6c72-117">Para criar ordens de trabalho baseadas na sua agenda de manutenção, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="f6c72-118">Abra uma das seguintes páginas, dependendo de como você deseja selecionar itens de agendamento para suas ordens de trabalho:</span><span class="sxs-lookup"><span data-stu-id="f6c72-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="f6c72-119">Todos os cronogramas de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Todos os agendamentos de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="f6c72-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="f6c72-120">Abra as linhas do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir linhas do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="f6c72-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="f6c72-121">Abra os pools do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir pools do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="f6c72-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="f6c72-122">Na grade, marque a caixa de seleção para cada trabalho de manutenção agendado para o qual você deseja criar uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="f6c72-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="f6c72-123">Em seguida, no Painel de Ação, selecione **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="f6c72-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="f6c72-124">A caixa de diálogo **Criar ordens de serviço** será exibida.</span><span class="sxs-lookup"><span data-stu-id="f6c72-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="f6c72-125">O campo **Horas de previsão de manutenção** exibe o número total de horas de previsão para as linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Caixa de diálogo Criar ordens de serviço](media/18-preventive-maintenance.png)

1. <span data-ttu-id="f6c72-127">Na seção **Parâmetros**, especifique o número de ordens de serviço que devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="f6c72-128">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="f6c72-128">Select one of the following options:</span></span>

    - <span data-ttu-id="f6c72-129">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="f6c72-130">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="f6c72-131">No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço que será usado para todas as ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="f6c72-132">Selecione **OK** para criar as ordens de serviço de acordo com as configurações.</span><span class="sxs-lookup"><span data-stu-id="f6c72-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="f6c72-133">Agrupar linhas de ordem de serviço que são criadas automaticamente enquanto um agendamento de manutenção é executado</span><span class="sxs-lookup"><span data-stu-id="f6c72-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

<span data-ttu-id="f6c72-134">Esse recurso permite definir regras para agrupar linhas de ordem de serviço em uma única ordem de serviço quando o sistema é configurado para gerar ordens de serviço automaticamente, com base em um agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="f6c72-135">Antes, as ordens de serviço geradas automaticamente podiam conter apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="f6c72-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="f6c72-136">No entanto, agora você pode agrupar ordens de serviço com base, por exemplo, no ativo, tipo de ativo ou local funcional.</span><span class="sxs-lookup"><span data-stu-id="f6c72-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="f6c72-137">(As ordens de serviço criadas manualmente já podem ser agrupadas dessa forma, conforme descrito na seção anterior deste tópico.)</span><span class="sxs-lookup"><span data-stu-id="f6c72-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="f6c72-138">Habilitar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="f6c72-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="f6c72-139">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="f6c72-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="f6c72-140">Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="f6c72-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="f6c72-141">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="f6c72-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="f6c72-142">**Módulo:** *gerenciamento de ativos*</span><span class="sxs-lookup"><span data-stu-id="f6c72-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="f6c72-143">**Nome do recurso:** *Aplicar regras para agrupar ordens de serviço ao executar um plano de manutenção*</span><span class="sxs-lookup"><span data-stu-id="f6c72-143">**Feature name:** *Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="f6c72-144">Configurar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="f6c72-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="f6c72-145">Para configurar agrupamento para ordens de serviço geradas automaticamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="f6c72-146">Vá para **Gerenciamento de ativos \> Configuração \> Manutenção preventiva \> Planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="f6c72-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="f6c72-147">Para cada plano em que você deseja gerar ordens de serviço agrupadas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="f6c72-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="f6c72-148">No painel de lista, selecione o plano desejado.</span><span class="sxs-lookup"><span data-stu-id="f6c72-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="f6c72-149">Na guia rápida **Linhas**, certifique-se de que a caixa de seleção **Criação automática** esteja marcada em todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="f6c72-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="f6c72-150">Vá para **Gerenciamento de ativos \> Periódico \> Manutenção preventiva \> Agendar planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="f6c72-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="f6c72-151">Na caixa de diálogo **Agendar planos de manutenção**, na seção **Período**, especifique o horizonte de tempo para o plano (até que ponto ele deve procurar ao localizar trabalhos de manutenção agendados para os quais gerar trabalho).</span><span class="sxs-lookup"><span data-stu-id="f6c72-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="f6c72-152">Defina a opção **Criar ordem de serviço com base no agendamento automaticamente** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="f6c72-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="f6c72-153">Na seção **Ordem de serviço**, selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="f6c72-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="f6c72-154">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="f6c72-155">(Esta opção oferece a mesma funcionalidade disponível quando o recurso *Aplicar regras para agrupar ordens de serviço durante a execução de um plano de manutenção* está desativado.)</span><span class="sxs-lookup"><span data-stu-id="f6c72-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="f6c72-156">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="f6c72-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="f6c72-157">Se você deseja que as opções sejam aplicadas ao executar apenas alguns dos planos de manutenção, na guia rápida **Registros que serão incluídos**, adicione filtros conforme necessário, da mesma forma que em outros trabalhos em lote no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f6c72-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="f6c72-158">Na guia rápida **Executar em segundo plano**, configure as opções de lote e de agendamento conforme necessário, da mesma forma que em outros trabalhos em lote no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f6c72-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="f6c72-159">Selecione **OK** para executar e/ou programar os planos de manutenção selecionados.</span><span class="sxs-lookup"><span data-stu-id="f6c72-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]