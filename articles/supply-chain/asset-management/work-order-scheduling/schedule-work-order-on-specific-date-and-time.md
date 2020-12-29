---
title: Agendar ordem de serviço em data e hora específicas
description: Este tópico explica como programar uma ordem de trabalho em uma data e hora específicas em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e81ea13a3463965c6e4785dac32f536d2e94a7ba
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4422085"
---
# <a name="schedule-work-order-on-specific-date-and-time"></a><span data-ttu-id="f6a33-103">Agendar ordem de serviço em data e hora específicas</span><span class="sxs-lookup"><span data-stu-id="f6a33-103">Schedule work order on specific date and time</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f6a33-104">Se uma ordem de trabalho tiver de ser agenda em uma data *e* hora específicas, você pode substituir o processo de agendamento padrão no Gerenciamento de ativo e criar um agendamento específico para uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="f6a33-104">If a work order must be scheduled on a specific date *and* time, you can override the standard scheduling process in Asset Management and create a specific schedule for a work order.</span></span>

1. <span data-ttu-id="f6a33-105">Clique em **Gerenciamento de ativos** > **Comum** > **Ordens de serviço** > **Todas as ordens de serviço** ou **Ordens de serviço ativas**.</span><span class="sxs-lookup"><span data-stu-id="f6a33-105">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="f6a33-106">Na lista de trabalho, clique na ID da ordem de trabalho na coluna **Ordem de trabalho**.</span><span class="sxs-lookup"><span data-stu-id="f6a33-106">In the work order list, click on the Work order ID in the **Work order** column.</span></span>

3. <span data-ttu-id="f6a33-107">Clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f6a33-107">Click **Edit**.</span></span>

4. <span data-ttu-id="f6a33-108">Na Guia Rápida **Cabeçalho da ordem de serviço**, insira as datas e horas e início e término nos campos **Início esperado** e **Término esperado**.</span><span class="sxs-lookup"><span data-stu-id="f6a33-108">On the **Work order header** FastTab, insert start and end dates and times in the **Expected start** and **Expected end** fields.</span></span>

    ![Figura 1](media/05-work-order-scheduling.png)

5. <span data-ttu-id="f6a33-110">Na guia **Geral**, clique em **Agendar** para usar o processo de agendamento padrão, ou clique em **Expedir** se quiser atribuir a ordem de serviço para um trabalhador específico.</span><span class="sxs-lookup"><span data-stu-id="f6a33-110">On the **General** tab, click **Schedule** to use the standard scheduling process, or click **Dispatch** if you want to assign the work order to a specific worker.</span></span>

6. <span data-ttu-id="f6a33-111">Para substituir quaisquer reservas de capacidade existentes para garantir que a ordem de serviço está agendada no período esperado, realize as seleções como exibido na figura abaixo na seção da caixa de diálogo **Agendar ordem de serviço** > **Capacidade finita**.</span><span class="sxs-lookup"><span data-stu-id="f6a33-111">In order to override any existing capacity reservations to ensure that the work order is scheduled in the expected period, make the selections as shown in the figure below in the **Schedule work order** dialog > **Finite capacity** section.</span></span> <span data-ttu-id="f6a33-112">Isso significa que o processo de agendamento ignorará as reservas de capacidade existentes porque a ordem de serviço deve iniciar na hora de início esperada.</span><span class="sxs-lookup"><span data-stu-id="f6a33-112">This means that the scheduling process will ignore existing capacity reservations because the work order must start on the expected start time.</span></span>

    ![Figura 2](media/06-work-order-scheduling.png)

7. <span data-ttu-id="f6a33-114">Clique em **OK** para iniciar o agendamento.</span><span class="sxs-lookup"><span data-stu-id="f6a33-114">Click **OK** to start scheduling.</span></span>

8. <span data-ttu-id="f6a33-115">Se o processo de agendamento resultar em duplas reservas, você verá uma mensagem na tela e poderá ajudar as ordens de serviço relacionadas.</span><span class="sxs-lookup"><span data-stu-id="f6a33-115">If the scheduling process results in double bookings, you will see a message on the screen, and you can adjust the related work orders.</span></span>

>[!NOTE]
><span data-ttu-id="f6a33-116">Para agendar um funcionário de manutenção para a ordem de serviço, o funcionário de manutenção deve estar disponível na data e hora de início esperada.</span><span class="sxs-lookup"><span data-stu-id="f6a33-116">In order to schedule a maintenance worker for the work order, that maintenance worker must be available at the expected start date and time.</span></span> <span data-ttu-id="f6a33-117">A disponibilidade do trabalhador é configurada em [calendário do trabalhador](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span><span class="sxs-lookup"><span data-stu-id="f6a33-117">Worker availability is set up in the [worker calendar](../work-order-scheduling/maintenance-worker-calendar-and-scheduling.md).</span></span> 

