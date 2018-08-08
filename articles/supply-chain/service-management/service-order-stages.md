---
title: "Estágios de ordem de serviço"
description: "Definindo fases de uma ordem de serviço e as atribuindo aos trabalhadores, você controla o fluxo de uma ordem de serviço por meio de tarefas que várias pessoas executam na organização de serviço."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 3b924be95c7e60598879e4d0cfd03193fe888dd7
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---

# <a name="service-order-stages"></a><span data-ttu-id="18a19-103">Estágios de ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="18a19-103">Service order stages</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="18a19-104">Você pode configurar fases de uma ordem de serviço para definir as tarefas que devem ser concluídas, a ordem em que são concluídas e os trabalhadores responsáveis pela conclusão delas.</span><span class="sxs-lookup"><span data-stu-id="18a19-104">You can set up stages for a service order to define the tasks that must be completed, the order in which they are completed, and the workers who are responsible for completing them.</span></span> <span data-ttu-id="18a19-105">Definindo fases de uma ordem de serviço e as atribuindo aos trabalhadores, você poderá controlar o fluxo de uma ordem de serviço por meio de tarefas que várias pessoas executam na organização de serviço.</span><span class="sxs-lookup"><span data-stu-id="18a19-105">By defining the stages for a service order and assigning them to workers, you can control the flow of a service order through the tasks that various people perform in the service organization.</span></span> <span data-ttu-id="18a19-106">A sequência de fases deve incluir uma fase inicial.</span><span class="sxs-lookup"><span data-stu-id="18a19-106">The sequence of stages must include an initial stage.</span></span>

<span data-ttu-id="18a19-107">Você também pode definir as ações que são permitidas em cada fase.</span><span class="sxs-lookup"><span data-stu-id="18a19-107">You can also define the actions that are permitted at each stage.</span></span> <span data-ttu-id="18a19-108">Por exemplo, se você desmarcar a caixa de seleção **Lançar** para todas as fases, exceto a fase final, você impedirá que as ordens de serviço sejam lançadas antes de terem percorrido toda a sequência completa de fases.</span><span class="sxs-lookup"><span data-stu-id="18a19-108">For example, if you clear the **Post** check box for all stages except the final stage, you prevent any service orders from being posted before the service orders are processed through the complete sequence of stages.</span></span>

## <a name="branching-in-service-order-stages"></a><span data-ttu-id="18a19-109">Ramificação nas fases da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="18a19-109">Branching in service order stages</span></span>

<span data-ttu-id="18a19-110">Ao configurar uma fase de serviço, você poderá criar várias opções ou ramificações, a serem selecionadas para a próxima fase de serviço.</span><span class="sxs-lookup"><span data-stu-id="18a19-110">When you set up a service stage, you can create multiple options, or branches, to select from for the next service stage.</span></span> <span data-ttu-id="18a19-111">Todas as ramificações que você criar estarão disponíveis para seleção, quando a fase inicial for concluída.</span><span class="sxs-lookup"><span data-stu-id="18a19-111">All the branches that you create are available to select from when the initial stage is completed.</span></span> <span data-ttu-id="18a19-112">Por exemplo, você configura **Planejamento** como uma fase inicial.</span><span class="sxs-lookup"><span data-stu-id="18a19-112">For example, you set up **Planning** as an initial stage.</span></span> <span data-ttu-id="18a19-113">Você cria duas fases denominadas **Em andamento** e **Cancelar** e, em seguida, seleciona **Planejar** como pai delas.</span><span class="sxs-lookup"><span data-stu-id="18a19-113">You create two stages named **In process** and **Cancel**, and then select **Planning** as the parent for them.</span></span> <span data-ttu-id="18a19-114">Você atribui a fase de **Planejamento** à ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="18a19-114">You assign the **Planning** stage to sales order.</span></span> <span data-ttu-id="18a19-115">Quando a fase de planejamento da ordem de venda for concluída, você poderá selecionar a fase **Em andamento** se a ordem de venda estiver pronta ou poderá selecionar a fase **Cancelar** se a ordem de venda for cancelada.</span><span class="sxs-lookup"><span data-stu-id="18a19-115">When the planning stage for the sales order is completed, you can select the **In process** stage if the sales order is ready to work on, or you can select the **Cancel** stage if the sales order is canceled.</span></span>

## <a name="see-also"></a><span data-ttu-id="18a19-116">Consulte também</span><span class="sxs-lookup"><span data-stu-id="18a19-116">See also</span></span>

[<span data-ttu-id="18a19-117">Configurar estágios da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="18a19-117">Set up service order stages</span></span>](set-up-service-order-stages.md)

[<span data-ttu-id="18a19-118">Alterar a fase da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="18a19-118">Change the service order stage</span></span>](change-service-order-stage.md)

  



