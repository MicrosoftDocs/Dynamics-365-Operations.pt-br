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
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 876aef9f3f470490bb385e1861c837dcfa82db69
ms.sourcegitcommit: 1e615288db245f83c5d5e0cd45315400f8946beb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "5131784"
---
# <a name="creating-work-orders"></a><span data-ttu-id="90f9a-103">Criação de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="90f9a-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90f9a-104">Depois de agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para eles.</span><span class="sxs-lookup"><span data-stu-id="90f9a-104">After you've scheduled preventive maintenance jobs, the next step is to create work orders for them.</span></span> <span data-ttu-id="90f9a-105">Você pode concluir essa etapa usando um dos agendamentos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-105">You can complete this step by using one of the maintenance schedules.</span></span> <span data-ttu-id="90f9a-106">Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência, conforme descrito na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="90f9a-106">The scheduled jobs in a maintenance schedule can have different reference types, as described in the following table.</span></span>

| <span data-ttu-id="90f9a-107">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="90f9a-107">Reference type</span></span> | <span data-ttu-id="90f9a-108">descrição</span><span class="sxs-lookup"><span data-stu-id="90f9a-108">Description</span></span> |
|---|---|
| <span data-ttu-id="90f9a-109">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="90f9a-109">Maintenance plans</span></span> | <span data-ttu-id="90f9a-110">Trabalhos de manutenção que são baseadas com base no tipo de plano de manutenção *Tempo* ou *Contador*.</span><span class="sxs-lookup"><span data-stu-id="90f9a-110">Preventive maintenance jobs that are based on the *Time* or *Counter* maintenance plan type.</span></span> |
| <span data-ttu-id="90f9a-111">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="90f9a-111">Maintenance rounds</span></span> | <span data-ttu-id="90f9a-112">Trabalhos de manutenção preventiva que têm vários ativos que requerem um tipo semelhante de manutenção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-112">Preventive maintenance jobs that contain several assets that require a similar type of maintenance.</span></span> |
| <span data-ttu-id="90f9a-113">Solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="90f9a-113">Maintenance request</span></span> | <span data-ttu-id="90f9a-114">Uma solicitação criada manualmente para manutenção ou reparo de um ativo.</span><span class="sxs-lookup"><span data-stu-id="90f9a-114">A manually created request for maintenance or repair of an asset.</span></span> <span data-ttu-id="90f9a-115">Essa solicitação pode ser convertida em uma ordem de trabalho.</span><span class="sxs-lookup"><span data-stu-id="90f9a-115">This request can be converted to a work order.</span></span> |

## <a name="create-work-orders-based-on-your-maintenance-schedule"></a><span data-ttu-id="90f9a-116">Criar ordens de trabalho com base no seu plano de manutenção</span><span class="sxs-lookup"><span data-stu-id="90f9a-116">Create work orders based on your maintenance schedule</span></span>

<span data-ttu-id="90f9a-117">Para criar ordens de trabalho baseadas na sua agenda de manutenção, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-117">To create work orders that are based on your maintenance schedule, follow these steps.</span></span>

1. <span data-ttu-id="90f9a-118">Abra uma das seguintes páginas, dependendo de como você deseja selecionar itens de agendamento para suas ordens de trabalho:</span><span class="sxs-lookup"><span data-stu-id="90f9a-118">Open one of the following pages, depending on how you want to select schedule items for your work orders:</span></span>

    - <span data-ttu-id="90f9a-119">Todos os cronogramas de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Todos os agendamentos de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="90f9a-119">All maintenance schedule (**Asset management \> Management schedule \> All maintenance schedule**)</span></span>
    - <span data-ttu-id="90f9a-120">Abra as linhas do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir linhas do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="90f9a-120">Open maintenance schedule lines (**Asset management \> Management schedule \> Open maintenance schedule lines**)</span></span>
    - <span data-ttu-id="90f9a-121">Abra os pools do agendamento de manutenção (**Gerenciamento de ativos \> Agenda de gerenciamento \> Abrir pools do agendamento de manutenção**)</span><span class="sxs-lookup"><span data-stu-id="90f9a-121">Open maintenance schedule pools (**Asset management \> Management schedule \> Open maintenance schedule pools**)</span></span>

1. <span data-ttu-id="90f9a-122">Na grade, marque a caixa de seleção para cada trabalho de manutenção agendado para o qual você deseja criar uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="90f9a-122">In the grid, select the check box for every scheduled maintenance job that you want to create a work order for.</span></span> <span data-ttu-id="90f9a-123">Em seguida, no Painel de Ação, selecione **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="90f9a-123">Then, on the Action Pane, select **Work order**.</span></span>

    <span data-ttu-id="90f9a-124">A caixa de diálogo **Criar ordens de serviço** será exibida.</span><span class="sxs-lookup"><span data-stu-id="90f9a-124">The **Create work orders** dialog box appears.</span></span> <span data-ttu-id="90f9a-125">O campo **Horas de previsão de manutenção** exibe o número total de horas de previsão para as linhas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-125">The **Maintenance forecast hours** field shows the total number of forecast hours for the selected lines.</span></span>

    ![Caixa de diálogo Criar ordens de serviço](media/18-preventive-maintenance.png)

1. <span data-ttu-id="90f9a-127">Na seção **Parâmetros**, especifique o número de ordens de serviço que devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-127">In the **Parameters** section, specify the number of work orders that should be created.</span></span> <span data-ttu-id="90f9a-128">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="90f9a-128">Select one of the following options:</span></span>

    - <span data-ttu-id="90f9a-129">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-129">**One work order per line** – Create one work order per maintenance schedule line.</span></span>
    - <span data-ttu-id="90f9a-130">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-130">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="90f9a-131">No campo **Tipo de ordem de serviço**, selecione o tipo de ordem de serviço que será usado para todas as ordens de serviço criadas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-131">In the **Work order type** field, select the work order type to use for all the work orders that you create.</span></span>
1. <span data-ttu-id="90f9a-132">Selecione **OK** para criar as ordens de serviço de acordo com as configurações.</span><span class="sxs-lookup"><span data-stu-id="90f9a-132">Select **OK** to create the work orders according to your settings.</span></span>

## <a name="group-work-order-lines-that-are-automatically-created-while-a-maintenance-plan-runs"></a><span data-ttu-id="90f9a-133">Agrupar linhas de ordem de serviço que são criadas automaticamente enquanto um agendamento de manutenção é executado</span><span class="sxs-lookup"><span data-stu-id="90f9a-133">Group work order lines that are automatically created while a maintenance plan runs</span></span>

> [!IMPORTANT]
> <span data-ttu-id="90f9a-134">A funcionalidade que é descrita nesta seção está disponível como parte de uma versão preliminar.</span><span class="sxs-lookup"><span data-stu-id="90f9a-134">The functionality that is described in this section is available as part of a preview release.</span></span> <span data-ttu-id="90f9a-135">O conteúdo e a funcionalidade estão sujeitos a alterações.</span><span class="sxs-lookup"><span data-stu-id="90f9a-135">The content and the functionality are subject to change.</span></span> <span data-ttu-id="90f9a-136">Para obter informações sobre as versões prévias, consulte [Perguntas frequentes sobre as atualizações de serviço One Version](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).</span><span class="sxs-lookup"><span data-stu-id="90f9a-136">For more information about preview releases, see [One version service updates FAQ](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).</span></span>

<span data-ttu-id="90f9a-137">Esse recurso permite definir regras para agrupar linhas de ordem de serviço em uma única ordem de serviço quando o sistema é configurado para gerar ordens de serviço automaticamente, com base em um agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-137">This feature lets you define rules for grouping work order lines under a single work order when the system is set up to generate work orders automatically, based on a maintenance plan.</span></span> <span data-ttu-id="90f9a-138">Antes, as ordens de serviço geradas automaticamente podiam conter apenas uma linha.</span><span class="sxs-lookup"><span data-stu-id="90f9a-138">Previously, automatically generated work orders could contain only one line.</span></span> <span data-ttu-id="90f9a-139">No entanto, agora você pode agrupar ordens de serviço com base, por exemplo, no ativo, tipo de ativo ou local funcional.</span><span class="sxs-lookup"><span data-stu-id="90f9a-139">However, you can now group work orders by, for example, asset, asset type, or functional location.</span></span> <span data-ttu-id="90f9a-140">(As ordens de serviço criadas manualmente já podem ser agrupadas dessa forma, conforme descrito na seção anterior deste tópico.)</span><span class="sxs-lookup"><span data-stu-id="90f9a-140">(Manually generated work orders could already be grouped in this way, as described in the previous section of this topic.)</span></span>

### <a name="enable-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="90f9a-141">Habilitar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="90f9a-141">Enable grouping for automatically generated work orders</span></span>

<span data-ttu-id="90f9a-142">Antes de poder usar esse recurso, você deve habilitá-lo no seu sistema.</span><span class="sxs-lookup"><span data-stu-id="90f9a-142">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="90f9a-143">Os administradores podem usar as configurações de [gerenciamento de recursos](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo.</span><span class="sxs-lookup"><span data-stu-id="90f9a-143">Admins can use the [feature management](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="90f9a-144">No espaço de trabalho **Gerenciamento de recursos**, o recurso está listado da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="90f9a-144">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="90f9a-145">**Módulo:** *gerenciamento de ativos*</span><span class="sxs-lookup"><span data-stu-id="90f9a-145">**Module:** *Asset Management*</span></span>
- <span data-ttu-id="90f9a-146">**Nome do recurso:** *(Versão preliminar) Aplicar regras para agrupar ordens de serviço ao executar um agendamento de manutenção*</span><span class="sxs-lookup"><span data-stu-id="90f9a-146">**Feature name:** *(Preview) Apply rules for grouping work orders while running a maintenance plan*</span></span>

### <a name="set-up-grouping-for-automatically-generated-work-orders"></a><span data-ttu-id="90f9a-147">Configurar agrupamento para ordens de serviço geradas automaticamente</span><span class="sxs-lookup"><span data-stu-id="90f9a-147">Set up grouping for automatically generated work orders</span></span>

<span data-ttu-id="90f9a-148">Para configurar agrupamento para ordens de serviço geradas automaticamente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-148">To set up grouping for automatically generated work orders, follow these steps.</span></span>

1. <span data-ttu-id="90f9a-149">Vá para **Gerenciamento de ativos \> Configuração \> Manutenção preventiva \> Planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="90f9a-149">Go to **Asset management \> Setup \> Preventative maintenance \> Maintenance plans**.</span></span>
1. <span data-ttu-id="90f9a-150">Para cada plano em que você deseja gerar ordens de serviço agrupadas, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="90f9a-150">For each plan where you want to generate grouped work orders, follow these steps:</span></span>

    1. <span data-ttu-id="90f9a-151">No painel de lista, selecione o plano desejado.</span><span class="sxs-lookup"><span data-stu-id="90f9a-151">Select the plan in the list pane.</span></span>
    1. <span data-ttu-id="90f9a-152">Na guia rápida **Linhas**, certifique-se de que a caixa de seleção **Criação automática** esteja marcada em todas as linhas.</span><span class="sxs-lookup"><span data-stu-id="90f9a-152">On the **Lines** FastTab, make sure that the **Auto create** check box is selected on every line.</span></span>

1. <span data-ttu-id="90f9a-153">Vá para **Gerenciamento de ativos \> Periódico \> Manutenção preventiva \> Agendar planos de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="90f9a-153">Go to **Asset management \> Periodic \> Preventive maintenance \> Schedule maintenance plans**.</span></span>
1. <span data-ttu-id="90f9a-154">Na caixa de diálogo **Agendar planos de manutenção**, na seção **Período**, especifique o horizonte de tempo para o plano (até que ponto ele deve procurar ao localizar trabalhos de manutenção agendados para os quais gerar trabalho).</span><span class="sxs-lookup"><span data-stu-id="90f9a-154">In the **Schedule maintenance plans** dialog box, in the **Period** section, specify the time horizon for the plan (how far to look ahead when finding scheduled maintenance jobs to generate work for).</span></span>
1. <span data-ttu-id="90f9a-155">Defina a opção **Criar ordem de serviço com base no agendamento automaticamente** como *Sim*.</span><span class="sxs-lookup"><span data-stu-id="90f9a-155">Set the **Automatically create work order from schedule** option to *Yes*.</span></span>
1. <span data-ttu-id="90f9a-156">Na seção **Ordem de serviço**, selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="90f9a-156">In the **Work order** section, select one of the following options:</span></span>

    - <span data-ttu-id="90f9a-157">**Uma ordem de serviço por linha** – Cria uma ordem de serviço por linha do agendamento de manutenção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-157">**One work order per line** – Create one work order per maintenance schedule line.</span></span> <span data-ttu-id="90f9a-158">(Esta opção oferece a mesma funcionalidade disponível quando o recurso *Aplicar regras para agrupar ordens de serviço durante a execução de um plano de manutenção* está desativado.)</span><span class="sxs-lookup"><span data-stu-id="90f9a-158">(This option provides the same functionality that is available when the *Apply rules for grouping work orders while running a maintenance plan* feature is turned off.)</span></span>
    - <span data-ttu-id="90f9a-159">**Uma ordem de serviço por grupo** – Cria ordens de serviço que são agrupadas de acordo com as configurações das outras opções que ficam disponíveis quando você seleciona esta opção.</span><span class="sxs-lookup"><span data-stu-id="90f9a-159">**One work order per** – Create work orders that are grouped according to the settings of the other options that become available when you select this option.</span></span>

1. <span data-ttu-id="90f9a-160">Se você deseja que as opções sejam aplicadas ao executar apenas alguns dos planos de manutenção, na guia rápida **Registros que serão incluídos**, adicione filtros conforme necessário, da mesma forma que em outros trabalhos em lote no Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="90f9a-160">If you want the options to apply when you run only some of your maintenance plans, on the **Records to include** FastTab, add filters as you require, just as you might do for other batch jobs in Microsoft Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="90f9a-161">Na guia rápida **Executar em segundo plano**, configure as opções de lote e de agendamento conforme necessário, da mesma forma que em outros trabalhos em lote no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="90f9a-161">On the **Run in the background** FastTab, set up batch and scheduling options as you require, just as you might do for other batch jobs in Supply Chain Management.</span></span>
1. <span data-ttu-id="90f9a-162">Selecione **OK** para executar e/ou programar os planos de manutenção selecionados.</span><span class="sxs-lookup"><span data-stu-id="90f9a-162">Select **OK** to run and/or schedule the selected maintenance plans.</span></span>
