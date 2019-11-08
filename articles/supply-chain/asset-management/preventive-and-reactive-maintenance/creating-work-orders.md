---
title: Criação de ordens de serviço
description: Este tópico explica como criar ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/27/2019
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
ms.openlocfilehash: 6e910b2400106baf9f9dc06f6bc0d3daee8e4a43
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570067"
---
# <a name="creating-work-orders"></a><span data-ttu-id="dae49-103">Criação de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="dae49-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="dae49-104">Quando você agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="dae49-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="dae49-105">Isso é feito em um dos agendamentos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="dae49-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="dae49-106">Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência:</span><span class="sxs-lookup"><span data-stu-id="dae49-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="dae49-107">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="dae49-107">Reference type</span></span> | <span data-ttu-id="dae49-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="dae49-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="dae49-109">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="dae49-109">Maintenance plans</span></span>     | <span data-ttu-id="dae49-110">Trabalhos de manutenção preventiva com base nos tipos de plano de manutenção "Tempo" ou "Contador".</span><span class="sxs-lookup"><span data-stu-id="dae49-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="dae49-111">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="dae49-111">Maintenance rounds</span></span>    | <span data-ttu-id="dae49-112">Trabalhos de manutenção preventiva contendo vários ativos que requerem um tipo semelhante de manutenção.</span><span class="sxs-lookup"><span data-stu-id="dae49-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="dae49-113">Solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="dae49-113">Maintenance request</span></span>   | <span data-ttu-id="dae49-114">Solicitação criada manualmente para manutenção ou reparo de um ativo, que pode ser convertida em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="dae49-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="dae49-115">Clique em **Gerenciamento de ativos** > **Comum** > **Todos os planos de manutenção** ou **Abrir linhas do agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="dae49-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="dae49-116">Selecione os trabalhos de manutenção agendados para os quais deseja criar uma ordem de serviço e clique em **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="dae49-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="dae49-117">Na caixa de diálogo **Criar ordens de serviço**, o número total de horas de previsão das linhas selecionadas é mostrado no campo **Horas de previsão de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="dae49-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="dae49-118">Na seção **Parâmetros**, selecione quantas ordens de serviço devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="dae49-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="dae49-119">Você pode criar uma ordem de serviço por linha de programação de manutenção ou várias ordens de serviço com base nas suas seleções na seção **Uma ordem de serviço por**.</span><span class="sxs-lookup"><span data-stu-id="dae49-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="dae49-120">Selecione um **Tipo de ordem de trabalho** que será usado em todas as ordens de serviço que você criar.</span><span class="sxs-lookup"><span data-stu-id="dae49-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="dae49-121">A ilustração a seguir mostra um exemplo da caixa de diálogo **Criar ordens de serviço** .</span><span class="sxs-lookup"><span data-stu-id="dae49-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Figura 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="dae49-123">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="dae49-123">Click **OK**.</span></span> <span data-ttu-id="dae49-124">Uma ou mais ordens de serviço são criadas.</span><span class="sxs-lookup"><span data-stu-id="dae49-124">One or more work orders are created.</span></span>

