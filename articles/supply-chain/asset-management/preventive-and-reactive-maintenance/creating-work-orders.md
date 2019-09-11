---
title: Criação de ordens de serviço
description: Este tópico explica como criar ordens de serviço no Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875499"
---
# <a name="creating-work-orders"></a><span data-ttu-id="88667-103">Criação de ordens de serviço</span><span class="sxs-lookup"><span data-stu-id="88667-103">Creating work orders</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="88667-104">Quando você agendar trabalhos de manutenção preventiva, a próxima etapa é criar ordens de serviço para os trabalhos.</span><span class="sxs-lookup"><span data-stu-id="88667-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="88667-105">Isso é feito em um dos agendamentos de manutenção.</span><span class="sxs-lookup"><span data-stu-id="88667-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="88667-106">Os trabalhos agendados em um agendamento de manutenção podem ter diferentes tipos de referência:</span><span class="sxs-lookup"><span data-stu-id="88667-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="88667-107">Tipo de referência</span><span class="sxs-lookup"><span data-stu-id="88667-107">Reference type</span></span> | <span data-ttu-id="88667-108">Descrição</span><span class="sxs-lookup"><span data-stu-id="88667-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="88667-109">Planos de manutenção</span><span class="sxs-lookup"><span data-stu-id="88667-109">Maintenance plans</span></span>     | <span data-ttu-id="88667-110">Trabalhos de manutenção preventiva com base nos tipos de plano de manutenção "Tempo" ou "Contador".</span><span class="sxs-lookup"><span data-stu-id="88667-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="88667-111">Rounds de manutenção</span><span class="sxs-lookup"><span data-stu-id="88667-111">Maintenance rounds</span></span>    | <span data-ttu-id="88667-112">Trabalhos de manutenção preventiva contendo vários ativos que requerem um tipo semelhante de manutenção.</span><span class="sxs-lookup"><span data-stu-id="88667-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="88667-113">Solicitação de manutenção</span><span class="sxs-lookup"><span data-stu-id="88667-113">Maintenance request</span></span>   | <span data-ttu-id="88667-114">Solicitação criada manualmente para manutenção ou reparo de um ativo, que pode ser convertida em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="88667-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="88667-115">Clique em **Gerenciamento de ativos** > **Comum** > **Todos os planos de manutenção** ou **Abrir linhas do agendamento de manutenção** ou **Abrir grupos de agendamento de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="88667-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="88667-116">Selecione os trabalhos de manutenção agendados para os quais deseja criar uma ordem de serviço e clique em **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="88667-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="88667-117">O número total de horas de previsão para as linhas selecionadas é mostrado no campo **Horas de previsão de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="88667-117">The total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="88667-118">Na seção **Parâmetros**, selecione quantas ordens de serviço devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="88667-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="88667-119">Você pode criar uma ordem de serviço por linha de programação de manutenção ou várias ordens de serviço com base nas suas seleções na seção **Uma ordem de serviço por**.</span><span class="sxs-lookup"><span data-stu-id="88667-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="88667-120">Selecione um **Tipo de ordem de trabalho** que será usado em todas as ordens de serviço que você criar.</span><span class="sxs-lookup"><span data-stu-id="88667-120">Select a **Work order type** that will be used on all the work orders you create.</span></span>

5. <span data-ttu-id="88667-121">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="88667-121">Click **OK**.</span></span> <span data-ttu-id="88667-122">Uma ou mais ordens de serviço são criadas.</span><span class="sxs-lookup"><span data-stu-id="88667-122">One or more work orders are created.</span></span>

![Figura 1](media/18-preventive-maintenance.png)

