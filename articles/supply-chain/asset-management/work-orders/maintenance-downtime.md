---
title: Tempo de inatividade de manutenção
description: Este tópico descreve tempo de inatividade de manutenção no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918235"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="ffa29-103">Tempo de inatividade de manutenção</span><span class="sxs-lookup"><span data-stu-id="ffa29-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="ffa29-104">Você pode criar registros do tempo de inatividade de manutenção no ativo selecionado em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="ffa29-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="ffa29-105">Isso é útil se você quiser registrar tempo de inatividade de manutenção em uma ou mais máquinas na área de produção.</span><span class="sxs-lookup"><span data-stu-id="ffa29-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="ffa29-106">Primeiro, crie códigos de motivo do tempo de inatividade de manutenção que deseja usar, por exemplo, divisão e parada planejada.</span><span class="sxs-lookup"><span data-stu-id="ffa29-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="ffa29-107">Isso é feito em **Códigos de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="ffa29-108">Em seguida, você pode criar registros do tempo de inatividade de manutenção em **Tempo de Inatividade de Manutenção** e adicionar os códigos do motivo relevantes.</span><span class="sxs-lookup"><span data-stu-id="ffa29-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="ffa29-109">Criar códigos de motivo de tempo de inatividade de manutenção</span><span class="sxs-lookup"><span data-stu-id="ffa29-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="ffa29-110">Clique em **Gerenciamento de ativos** > **Configuração** > **Ordens de serviços** > **Códigos de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="ffa29-111">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-111">Click **New**.</span></span>

3. <span data-ttu-id="ffa29-112">Inserir um ID no campo **Código de motivo do tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="ffa29-113">Insira um nome para o código do motivo no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="ffa29-114">Marque a caixa de seleção **KPI incluído** se o código do motivo tiver que ser incluído nos cálculos de KPI do ativo.</span><span class="sxs-lookup"><span data-stu-id="ffa29-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="ffa29-115">Geralmente, as paradas de produção planejadas não devem se incluídas em cálculos de KPI porque não afetam o desempenho esperado.</span><span class="sxs-lookup"><span data-stu-id="ffa29-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="ffa29-116">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-116">Click **Save**.</span></span>

![Figura 1](media/15-work-orders.png)


<span data-ttu-id="ffa29-118">Quando você criar códigos de motivo do tempo de inatividade de manutenção que deseja usar, você pode criar registros do tempo de inatividade de manutenção para ordens de serviço e ativos.</span><span class="sxs-lookup"><span data-stu-id="ffa29-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="ffa29-119">Criar registros de tempo de inatividade de manutenção</span><span class="sxs-lookup"><span data-stu-id="ffa29-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="ffa29-120">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="ffa29-121">Selecione a ordem de serviço e clique em **Tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="ffa29-122">Clique em **Novo**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-122">Click **New**.</span></span>

4. <span data-ttu-id="ffa29-123">Insira o intervalo de data e hora para o registro de tempo de inatividade de manutenção nos campos **De** e **A**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="ffa29-124">Quando você sair do campo **A**, a duração em horas é inserida automaticamente no campo **Duração**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="ffa29-125">Selecione um código de motivo no campo **código de motivo de tempo de inatividade de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="ffa29-126">Repita as etapas 3 e 6 se quiser adicionar mais registros.</span><span class="sxs-lookup"><span data-stu-id="ffa29-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="ffa29-127">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-127">Click **Save**.</span></span>


![Figura 2](media/16-work-orders.png)


<span data-ttu-id="ffa29-129">O calendário usado para calcular um registro do tempo de inatividade de manutenção depende de sua seleção na configuração de ativos e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ffa29-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="ffa29-130">Se um recurso for selecionado em um ativo no campo **Todos os ativos** > **Ativo fixo** Guia Rápida > **Recurso**, será usada a configuração do calendário para o grupo de recursos associado, conforme mostrado na seguinte figura.</span><span class="sxs-lookup"><span data-stu-id="ffa29-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Figura 3](media/17-work-orders.png)


<span data-ttu-id="ffa29-132">Se nenhum recurso for selecionado no ativo, o calendário padrão selecionado em **Parâmetros de gerenciamento de ativos** é usado, conforme mostrado na seguinte figura.</span><span class="sxs-lookup"><span data-stu-id="ffa29-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Figura 4](media/18-work-orders.png)


<span data-ttu-id="ffa29-134">Clique **Gerenciamento de ativos da empresa** > **Consultas** > **Tempo de inatividade de manutenção** para exibir uma visão geral de todos os registros de tempo de inatividade de manutenção.</span><span class="sxs-lookup"><span data-stu-id="ffa29-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="ffa29-135">Todos os calendários usados no módulo **Gerenciamento de ativos** são configurados na **Administração da organização** > **Configuração** > **Calendários** > **Calendários**.</span><span class="sxs-lookup"><span data-stu-id="ffa29-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

