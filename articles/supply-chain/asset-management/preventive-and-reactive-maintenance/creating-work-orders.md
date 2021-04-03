---
title: Criação de ordens de serviço
description: Este tópico explica como criar ordens de serviço no Gerenciamento de Ativos.
author: johanhoffmann
manager: tfehr
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 76306fb31e7e5297e6a5d64b97b5bd09b64349ee
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "5500565"
---
# <a name="creating-work-orders"></a><span data-ttu-id="34a6d-103">Criação de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="34a6d-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34a6d-104">Depois de agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para eles.</span><span class="sxs-lookup"><span data-stu-id="34a6d-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="34a6d-105">Você pode concluir essa etapa usando um dos agendamentos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="34a6d-106">Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência, conforme descrito na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="34a6d-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="34a6d-107">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="34a6d-107">Reference type</span></span> | <span data-ttu-id="34a6d-108">descrição</span><span class="sxs-lookup"><span data-stu-id="34a6d-108">Description</span></span> |
|---|---|
| <span data-ttu-id="34a6d-109">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="34a6d-109">Maintenance plans</span></span> | <span data-ttu-id="34a6d-110">Trabalhos de manutenção que são baseadas com base no tipo de plano de manutenção *Tempo* ou *Contador*.</span><span class="sxs-lookup"><span data-stu-id="34a6d-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="34a6d-111">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="34a6d-111">Maintenance rounds</span></span> | <span data-ttu-id="34a6d-112">Trabalhos de manutenção preventiva que têm vários ativos que requerem um tipo semelhante de manutenção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="34a6d-113">Solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="34a6d-113">Maintenance request</span></span> | <span data-ttu-id="34a6d-114">Uma solicitação criada manualmente para manutenção ou reparo de um ativo.</span><span class="sxs-lookup"><span data-stu-id="34a6d-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="34a6d-115">Essa solicitação pode ser convertida em uma ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="34a6d-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="34a6d-116">Criar ordens de trabalho com base no seu plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="34a6d-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="34a6d-117">Para criar ordens de trabalho baseadas na sua agenda de manutenção, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="34a6d-118">Abra uma das seguintes páginas, dependendo de como você deseja selecionar itens de agendamento para suas ordens de trabalho:</span><span class="sxs-lookup"><span data-stu-id="34a6d-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="34a6d-119">Todos os cronogramas de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Todos os agendamentos de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="34a6d-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="34a6d-120">Abra as linhas do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir linhas do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="34a6d-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="34a6d-121">Abra os pools do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir pools do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="34a6d-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="34a6d-122">Na grade, marque a caixa de seleção para cada trabalho de manutenção agendado para o qual você deseja criar uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="34a6d-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="34a6d-123">Em seguida, no Painel de Ação, selecione **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="34a6d-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="34a6d-124">A caixa de diálogo **Criar ordens de serviço** será exibida.</span><span class="sxs-lookup"><span data-stu-id="34a6d-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="34a6d-125">O campo **Horas de previsão de manutenção** exibe o número total de horas de previsão para as linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Caixa de diálogo Criar ordens de serviço](media/18-preventive-maintenance.png)

1. <span data-ttu-id="34a6d-127">Na seção **Parâmetros**, especifique o número de ordens de serviço que devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="34a6d-128">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="34a6d-128">Select one of the following options:</span></span>

    - <span data-ttu-id="34a6d-129">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="34a6d-130">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="34a6d-131">No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço que será usado para todas as ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="34a6d-132">Selecione **OK** para criar as ordens de serviço de acordo com as configurações.</span><span class="sxs-lookup"><span data-stu-id="34a6d-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="34a6d-133">Agrupar linhas de ordem de serviço que são criadas automaticamente enquanto um agendamento de manutenção é executado</span><span class="sxs-lookup"><span data-stu-id="34a6d-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

<span data-ttu-id="34a6d-134">Esse recurso permite definir regras para agrupar linhas de ordem de serviço em uma única ordem de serviço quando o sistema é configurado para gerar ordens de serviço automaticamente, com base em um agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-134">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="34a6d-135">Antes, as ordens de serviço geradas automaticamente podiam conter apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="34a6d-135">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="34a6d-136">No entanto, agora você pode agrupar ordens de serviço com base, por exemplo, no ativo, tipo de ativo ou local funcional.</span><span class="sxs-lookup"><span data-stu-id="34a6d-136">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="34a6d-137">(As ordens de serviço criadas manualmente já podem ser agrupadas dessa forma, conforme descrito na seção anterior deste tópico.)</span><span class="sxs-lookup"><span data-stu-id="34a6d-137">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="34a6d-138">Habilitar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="34a6d-138">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="34a6d-139">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="34a6d-139">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="34a6d-140">Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="34a6d-140">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="34a6d-141">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="34a6d-141">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="34a6d-142">**Módulo:** *gerenciamento de ativos*</span><span class="sxs-lookup"><span data-stu-id="34a6d-142">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="34a6d-143">**Nome do recurso:** *(Versão preliminar) Aplicar regras para agrupar ordens de serviço ao executar um agendamento de manutenção*</span><span class="sxs-lookup"><span data-stu-id="34a6d-143">**Feature name:** *(Preview) Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="34a6d-144">Configurar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="34a6d-144">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="34a6d-145">Para configurar agrupamento para ordens de serviço geradas automaticamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-145">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="34a6d-146">Vá para **Gerenciamento de ativos \> Configuração \> Manutenção preventiva \> Planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="34a6d-146">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="34a6d-147">Para cada plano em que você deseja gerar ordens de serviço agrupadas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="34a6d-147">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="34a6d-148">No painel de lista, selecione o plano desejado.</span><span class="sxs-lookup"><span data-stu-id="34a6d-148">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="34a6d-149">Na guia rápida **Linhas**, certifique-se de que a caixa de seleção **Criação automática** esteja marcada em todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="34a6d-149">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="34a6d-150">Vá para **Gerenciamento de ativos \> Periódico \> Manutenção preventiva \> Agendar planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="34a6d-150">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="34a6d-151">Na caixa de diálogo **Agendar planos de manutenção**, na seção **Período**, especifique o horizonte de tempo para o plano (até que ponto ele deve procurar ao localizar trabalhos de manutenção agendados para os quais gerar trabalho).</span><span class="sxs-lookup"><span data-stu-id="34a6d-151">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="34a6d-152">Defina a opção **Criar ordem de serviço com base no agendamento automaticamente** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="34a6d-152">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="34a6d-153">Na seção **Ordem de serviço**, selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="34a6d-153">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="34a6d-154">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-154">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="34a6d-155">(Esta opção oferece a mesma funcionalidade disponível quando o recurso *Aplicar regras para agrupar ordens de serviço durante a execução de um plano de manutenção* está desativado.)</span><span class="sxs-lookup"><span data-stu-id="34a6d-155">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="34a6d-156">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="34a6d-156">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="34a6d-157">Se você deseja que as opções sejam aplicadas ao executar apenas alguns dos planos de manutenção, na guia rápida **Registros que serão incluídos**, adicione filtros conforme necessário, da mesma forma que em outros trabalhos em lote no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="34a6d-157">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="34a6d-158">Na guia rápida **Executar em segundo plano**, configure as opções de lote e de agendamento conforme necessário, da mesma forma que em outros trabalhos em lote no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="34a6d-158">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="34a6d-159">Selecione **OK** para executar e/ou programar os planos de manutenção selecionados.</span><span class="sxs-lookup"><span data-stu-id="34a6d-159">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]