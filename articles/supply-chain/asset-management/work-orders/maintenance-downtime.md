---
title: Tempo de inatividade de manutenção para ordens de serviço
description: Este tópico descreve como criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
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
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53487a0173453ef7a8f5ea818672d999fe71cb65
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020902"
---
# <a name="maintenance-downtime-for-work-orders"></a><span data-ttu-id="10e85-103">Tempo de inatividade de manutenção para ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="10e85-103">Maintenance downtime for work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="10e85-104">Você pode criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="10e85-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="10e85-105">Esse recurso é útil se você quiser registrar o tempo de inatividade de manutenção em uma ou mais máquinas na área de produção.</span><span class="sxs-lookup"><span data-stu-id="10e85-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="10e85-106">Primeiro, crie códigos para o motivo do tempo de inatividade de manutenção que deseja usar, como **Travamento** e **Parada planejada**.</span><span class="sxs-lookup"><span data-stu-id="10e85-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="10e85-107">Isso é feito na página **Códigos de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="10e85-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="10e85-108">Em seguida, você pode criar registros do tempo de inatividade de manutenção na página **Tempo de inatividade de manutenção** e adicionar os códigos de motivo do tempo de inatividade de manutenção relevantes.</span><span class="sxs-lookup"><span data-stu-id="10e85-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="10e85-109">Criar códigos de motivo de tempo de inatividade de manutenção</span><span class="sxs-lookup"><span data-stu-id="10e85-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="10e85-110">Selecione **Gerenciamento de ativos** > **Configurar** > **Ordens de serviço** > **Códigos de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="10e85-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="10e85-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="10e85-111">Select **New**.</span></span>

3. <span data-ttu-id="10e85-112">No campo **Código de motivo do tempo de inatividade de manutenção**, insira uma ID para o código de motivo do tempo de inatividade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="10e85-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="10e85-113">No campo **Nome**, insira um nome.</span><span class="sxs-lookup"><span data-stu-id="10e85-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="10e85-114">Marque a caixa de seleção **Incluído no KPI** se desejar que o código de motivo seja incluído nos cálculos dos KPIs (Indicadores Chave de Desempenho) do ativo.</span><span class="sxs-lookup"><span data-stu-id="10e85-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="10e85-115">Em geral, as paradas de produção planejadas não devem ser incluídas em cálculos de KPI, pois não afetam o desempenho esperado.</span><span class="sxs-lookup"><span data-stu-id="10e85-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="10e85-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="10e85-116">Select **Save**.</span></span>

<span data-ttu-id="10e85-117">A ilustração a seguir mostra um exemplo da página **Códigos de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="10e85-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Figura 1](media/15-work-orders.png)

<span data-ttu-id="10e85-119">Depois de criar os códigos de motivo do tempo de inatividade de manutenção que deseja usar, você pode criar registros de tempo de inatividade de manutenção para ordens de serviço e ativos.</span><span class="sxs-lookup"><span data-stu-id="10e85-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="10e85-120">Criar registros de tempo de inatividade de manutenção</span><span class="sxs-lookup"><span data-stu-id="10e85-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="10e85-121">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="10e85-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="10e85-122">Selecione a ordem de serviço e, na guia **Ordem de serviço**, no grupo **Ativo**, selecione **Tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="10e85-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="10e85-123">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="10e85-123">Select **New**.</span></span>

4. <span data-ttu-id="10e85-124">Nos campos **De** e **A**, defina o intervalo de data e hora para o registro de tempo de inatividade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="10e85-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="10e85-125">Quando você sair do campo **A**, a duração em horas é inserida automaticamente no campo **Duração**.</span><span class="sxs-lookup"><span data-stu-id="10e85-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="10e85-126">No campo **código de motivo do tempo de inatividade de manutenção**, selecione um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="10e85-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="10e85-127">Repita as etapas 3 a 5 para adicionar mais registros.</span><span class="sxs-lookup"><span data-stu-id="10e85-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="10e85-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="10e85-128">Select **Save**.</span></span>

<span data-ttu-id="10e85-129">A ilustração a seguir mostra um exemplo de registro de tempo de inatividade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="10e85-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Figura 2](media/16-work-orders.png)

<span data-ttu-id="10e85-131">O calendário usado para calcular um registro de tempo de inatividade de manutenção depende da sua seleção na configuração de ativos e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="10e85-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="10e85-132">Se um recurso for selecionado em um ativo no campo **Recurso** da Guia Rápida **Ativo fixo** na página **Todos os ativos**, o calendário definido para o grupo de recursos associado será utilizado, conforme exibido na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="10e85-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Figura 3](media/17-work-orders.png)

<span data-ttu-id="10e85-134">Se nenhum recurso for selecionado no ativo, o calendário padrão selecionado na página **Parâmetros de gerenciamento de ativos** será utilizado, conforme mostrado na figura a seguir.</span><span class="sxs-lookup"><span data-stu-id="10e85-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Figura 4](media/18-work-orders.png)

<span data-ttu-id="10e85-136">Para obter uma visão geral de todos os registros de tempo de inatividade de manutenção, clique em **Gerenciamento de ativos** > **Consultas** > **Tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="10e85-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="10e85-137">Todos os calendários usados no módulo **Gerenciamento de ativos** são configurados em **Administração da organização** > **Configurar** > **Calendários** > **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="10e85-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

